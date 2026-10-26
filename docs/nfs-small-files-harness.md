# NFS 海量小文件场景：Agent Harness 落地方案

> **适用场景**：sandbox 通过 NFS 挂载数据目录，目录下有几十万个小文件。agent 在 harness（Claude Code、Agent SDK 或自研）里执行 `find` 一类的遍历命令时经常超时，还会把进程卡住。
>
> **版本**：v2（2026-10-26）。v1 是上一轮讨论给出的口头方案，本版逐条复核后做了修订，修订点见 §2。
>
> **验证情况**：附录里的脚本都在 Linux 6.18、Python 3.13、GNU findutils 4.9、bash 5.2 上实测过，结果见附录开头的测试摘要。**没有在真实 NFS 上压测过**：文中涉及 NFS 的耗时都是估算，上线前请先按 §1.3 测出你们环境的基线。

## 0. 结论

问题有两个，要分开解决：

| 现象 | 根因 | 解决思路 |
|---|---|---|
| **慢** | 遍历时每个目录、经常还有每个文件，都要发一次元数据 RPC；几十万次串行网络往返，每次 0.3–3 ms | 运行时不遍历，改查索引；必须遍历时并行遍历；只读数据做成镜像 |
| **卡死** | 超时只杀了直接子进程，管道里的 find 继续运行并占着输出管道；Claude Code 会把超时命令转到后台继续跑；NFS 无响应时进程进入 D 状态，而调用方还在同步等它 | 执行层兜底：按进程组/cgroup 清理，输出写文件，杀不掉的进程不等，探活熔断 |

落地顺序：

| 阶段 | 内容 | 工作量 | 目标 |
|---|---|---|---|
| **P0** | 执行层兜底（`nfs-run`）+ hook 拦截 + CLAUDE.md 规则 + 探活熔断 | 1–2 天 | 任何命令都卡不住会话 |
| **P1** | 服务端建索引 + `nfs-find`（可选 MCP 工具） | 3–5 天 | 大部分"找文件"请求改为查索引，1 秒内返回 |
| **P2** | 数据布局：只读数据做成 squashfs/erofs 镜像或启动时预拉取；大目录分片 | 按数据集推进 | 剩下的遍历需求变成本地遍历 |
| **P3** | 挂载参数和服务端调优 | 以测量结果为准 | 降低每次 RPC 的成本 |

调参放在最后，是因为它只能降低每次 RPC 的成本，改变不了"几十万次 RPC"这个量级。

## 1. 根因分析

### 1.1 为什么 find 在 NFS 上慢

粗略估算：

```
耗时 ≈ (目录数 × 每个目录的 READDIR 次数 + 需要单独 stat 的条目数) × RTT ÷ 有效并发
```

- **READDIR**：每个目录至少一次，大目录要分页多次。
- **单独 stat**：满足下面任一条件，find 就要对每个条目调用 `lstat`。在 NFS 上，没命中属性缓存的 stat 就是一次 GETATTR 或 LOOKUP 往返：
  - 用了需要读 inode 的谓词：`-size`、`-mtime`/`-newer`、`-perm`、`-user`，以及 `-printf` 里的属性字段；
  - 拿不到条目类型（`d_type` 为 `DT_UNKNOWN`）。这时 find 为了判断"是不是目录、要不要进去"，只能逐个 stat。NFSv3 的普通 READDIR 不返回文件类型，READDIRPLUS 会把属性随目录项一起带回；但 Linux 客户端默认只在小目录、或者检测到"readdir 之后紧跟 stat"的访问模式时才用 READDIRPLUS（见 `man 5 nfs` 的 `rdirplus` 一节），所以大目录在 v3 上常常退化成逐条 stat。
- **RTT**：机房内 NFS 一般在 0.3–1 ms，云上托管 NFS 的元数据操作常见 1–3 ms 甚至更高。

举例：30 万个条目，每个条目一次 RPC，RTT 1 ms，单线程，就是 300 秒。这还没算大目录被并发写入时 readdir 缓存失效带来的重读。

下面是本地 ext4 上的实测（12407 个条目、336 个目录，用 `strace` 统计系统调用次数），可以直观看出谓词的代价：

| 命令 | stat 类调用 | getdents64 |
|---|---|---|
| `find -name '*.json'` | 670（只对目录） | 670 |
| `find -type f -name '*.json'` | 670（d_type 可用，不用额外 stat） | 670 |
| `find -size +1k` | 12739（每个条目一次） | 670 |
| `find -mtime -1` | 12739（每个条目一次） | 670 |

换到 NFS 上，第 3、4 行的每次 stat 都可能是一次网络往返；如果 d_type 不可用，第 2 行也会变成逐条 stat。

### 1.2 为什么会"卡死"

慢只会导致超时。"卡死"另有三个来源，经常同时出现：

1. **超时只杀了直接子进程。** harness 用 `sh -c "find ... | grep ..."` 执行命令，超时后只杀了 `sh`，`find` 和 `grep` 继续运行，并且还持有 stdout 管道。harness 等不到 EOF，就一直等下去。很多 executor 都有这个问题，例如 Node `child_process.exec` 的 timeout 只向直接子进程发信号。泄漏出去的 find 还会继续压 NFS，让后续命令更慢，最后形成雪崩。
2. **Claude Code 不会杀掉超时的前台命令。** 按当前文档，前台 Bash 命令到达超时后会被**转入后台继续运行**：无人值守的会话里还能再跑 30 分钟，本地交互式会话里则没有时间上限（[Bash tool behavior](https://code.claude.com/docs/en/tools-reference#foreground-commands-that-move-to-the-background)）。agent 通常会换个写法重试，于是同一批数据上会同时跑着好几个 find。
3. **D 状态（不可中断睡眠）。** 默认的 `hard` 挂载在服务端慢或无响应时会无限重试 RPC，进程在 `ps` 里显示为 `D`。这里要区分两种情况：
   - 从 Linux 2.6.25 起，NFS 的大部分等待是 `TASK_KILLABLE`，**SIGKILL 可以打断**；未被进程捕获的 SIGTERM 也会被内核当作致命信号处理。`intr`/`nointr` 挂载选项已经废弃，不起作用。
   - 仍有一些等待真正不可中断，例如等待一个被其他卡住进程持有的 inode 锁、页回写、`close()` 时刷脏页。这时 SIGKILL 也无效，**谁去 `wait()` 它，谁就一起卡住**。GNU `timeout -k` 也会卡在 `waitpid` 上。

结论：只加一个 timeout 不够。执行层必须做到三点：杀整个进程组（或整个 cgroup）；输出不走管道；进程杀不掉就不再等它。

### 1.3 先测量，记录基线

做任何改动之前，先在一台测试节点上记录下面这些数据，后面每一步都用同一组数据验收。

```bash
# 环境：内核版本、NFS 版本和实际生效的挂载参数
uname -r; grep -E ' nfs4? ' /proc/mounts

# 数据形态（在 NFS 服务端执行）：文件数、目录数、条目最多的目录
find /export/data | wc -l; find /export/data -type d | wc -l
find /export/data -mindepth 1 -printf '%h\n' | sort | uniq -c | sort -rn | head

# 冷缓存遍历耗时（需要 root；会清掉本机的 dentry/inode 缓存，只在测试节点上做）
sync; echo 2 > /proc/sys/vm/drop_caches
time find /mnt/nfs/data -mindepth 1 | wc -l

# RPC 构成：遍历前后各执行一次，对比 getattr / lookup / readdir / readdirplus 的增量
nfsstat -c

# 每类操作的平均 RTT 和排队时间（mountstats 来自 nfs-utils，也可以直接读 /proc/self/mountstats）
mountstats /mnt/nfs

# 系统调用层面：stat 和 getdents 各调用了多少次
strace -f -c -e trace=newfstatat,statx,getdents64 find /mnt/nfs/data/<子目录> > /dev/null

# 有没有卡在 D 状态的进程，卡在哪个内核函数
ps -eo pid,stat,wchan:32,etime,args | awk '$2 ~ /D/'
cat /proc/<pid>/stack    # 需要 root
```

| 基线指标 | 记录值 |
|---|---|
| 内核版本 / NFS 版本 / 挂载参数 | |
| 文件数 / 目录数 / 单目录最大条目数 | |
| 冷缓存 `find \| wc -l` 耗时 | |
| 一次遍历中 GETATTR / LOOKUP / READDIR(PLUS) 的次数 | |
| 元数据操作平均 RTT | |
| 每天 find 超时次数 / 会话卡死次数 / D 状态进程峰值 | |

## 2. 对 v1 方案的 review

| # | v1 的说法 | 问题 | v2 的修订 |
|---|---|---|---|
| 1 | hard 挂载下进程进入 D 状态，SIGTERM 杀不掉，timeout 无效 | 说得太绝对。2.6.25 起大部分 NFS 等待能被 SIGKILL 打断；实际更常见的"卡死"是只杀了 shell，孙进程占着管道 | 根因拆成三类（§1.2）；执行层改为杀进程组 + 输出写文件 + 杀不掉就不等（§4.1） |
| 2 | 没考虑 Claude Code 自身的超时行为 | 当前版本前台命令超时后会转入后台继续跑，超时的 find 并没有停 | 用 `nfs-run` 包一层，让它的超时短于 Bash 工具的超时（§4.1） |
| 3 | 用 `ls -f dir \| xargs -P 32 -I{} find dir/{}` 并行 | 有 bug：`ls -f` 会输出 `.` 和 `..`，导致整棵树和父目录被重复遍历；多个进程写同一个管道会把行切碎；文件名含空格会出错 | 改用 `pwalk`（附录 B）或 fd（§8） |
| 4 | 只要文件名时用 `nordirplus` | 对递归遍历反而可能更慢：v3 普通 READDIR 不带类型，find 只能逐个 stat 才知道要不要进子目录 | 保持默认；只有对单层大目录做 `ls -f` 的场景才考虑，而且要实测（§7） |
| 5 | 推荐 `lookupcache=all` | 这本来就是默认值 | 删除 |
| 6 | 推荐 `rsize/wsize=1M` 和客户端 `noatime` | 小文件场景的瓶颈在元数据，这两项几乎没有影响；atime 由服务端维护 | 降为可选；改为在服务端底层文件系统上设 `noatime`/`relatime`（§7） |
| 7 | 推荐 `fsc` + cachefilesd | FS-Cache 只缓存文件内容，不缓存目录项和属性，对 find 没有帮助 | 只用于"反复读同一批文件内容"的场景（§7） |
| 8 | 用 cgroup 限制 sandbox 的 RPC 数和 IO | cgroup v2 的 `io.max` 只作用于块设备，NFS 流量不经过块层，限不住；cgroup 也限制不了 RPC 数 | 改为工具级并发预算（`nfs-run --slots`、`pwalk -j`）+ `pids.max` 防进程堆积；cgroup 用来杀干净（`cgroup.kill`）（§4.1） |
| 9 | 用 `fd -j 32` / `rg --files` 代替 find | 两者默认跳过隐藏文件和 .gitignore 里的文件，结果和 find 不一致；`fd --type` 在 d_type 未知时同样要 stat | 需要完整结果时加 `-HI`（fd）或 `-uu`（rg），并显式排除 `.snapshot` 等存储快照目录（§8） |
| 10 | 服务端用 inotify 做增量 | inotify 每个目录一个 watch，目录多时要调 `max_user_watches`；重启或队列溢出会丢事件 | 默认在服务端周期性全量重建（本地遍历很便宜）；要秒级新鲜度再考虑 fanotify 或由写入方维护清单（§5.4） |
| 11 | 在 sandbox 里直接 `mount -o loop` squashfs 镜像 | sandbox 通常没有 CAP_SYS_ADMIN 和 loop 设备 | 在宿主机上挂载后 bind 进 sandbox，或用 squashfuse（§6.1） |
| 12 | hook 用一条正则匹配 `find.*/mnt/nfs` | 漏掉 `cd /mnt/nfs && find .`、`bash -c '...'`、`-maxdepth 100`、Glob/Grep 工具和脚本里的 `os.walk`；同时会误拦对索引文件的 rg | 换成按 shell 分段解析的实现（附录 C），附 45 个测试用例（附录 G）；并明确 hook 只是护栏，兜底靠执行层 |
| 13 | `soft,timeo=50,retrans=2` 可以快速失败 | TCP 下超时是线性退避，大约 5+10+15≈30 秒才返回错误；soft 用在可写挂载上有静默丢写的风险 | 只用于只读挂载，并写明实际的超时时长（§7） |
| 14 | 只提了"建索引" | 缺少新鲜度标识、原子替换和空索引保护 | 索引带构建时间，rename 原子替换，条数骤降时拒绝发布，查询时提示索引年龄（§5） |
| 15 | （遗漏） | 没讲单目录过大、存储快照目录、服务端 nfsd 线程数、多个 sandbox 并发叠加的问题 | 补充到 §6.3、§7、§8 |

## 3. 总体方案

```
agent 发出命令
  │
  ├─ ① nfs-guard hook：拦截对 NFS 的无界递归遍历，拒绝理由里给出下面三条路
  │
  ├─ ② 找文件      → nfs-find / MCP nfs_search → 读 /mnt/nfs/.index/files.tsv   大部分请求，<1 s
  ├─ ③ 看一个目录  → ls -f <目录> / find <目录> -maxdepth 1                      小范围实时确认
  └─ ④ 必须实时扫  → nfs-run -- pwalk --deadline 80 <目录>                       少数情况，有上限
        nfs-run：超时短于 Bash 工具超时；杀整个进程组；输出写文件；探活熔断；并发槽位

NFS 服务端
  ├─ cron 每 5 分钟执行 build-nfs-index.sh（服务端本地遍历）
  └─ 只读数据集：发布 squashfs/erofs 镜像，宿主机挂载后 bind 进 sandbox
```

按你们的情况选组合：

| 情况 | 推荐组合 |
|---|---|
| 数据只读或按批次更新（训练集、语料、归档） | P0 + 镜像（§6.1）或启动时预拉取（§6.2） |
| 读写，NFS 服务端可控 | P0 + 服务端索引（§5）+ 大目录分片（§6.3） |
| 读写，服务端不可控（托管 NAS） | P0 + 专用 indexer 节点用 `WALKER=pwalk` 建索引（§5.2）；能改写入方的话由写入方维护清单（§5.4） |
| 需要频繁搜索文件内容 | 以上任一组合 + 近数据查询服务或全文索引（§5.5） |

## 4. P0：执行层兜底 + agent 引导（1–2 天）

### 4.1 执行层必须满足的六条约束

不管用哪种 harness，执行 tool 命令的那一层都要满足：

1. **每条命令有硬上限**，而且这个上限要短于上层（harness 或 Claude Code Bash 工具）的超时。这样命令是被自己的执行器结束的，而不是被上层转入后台。
2. **杀整个进程组**：用 `setsid`/`start_new_session` 启动子进程，超时后 `killpg(SIGTERM)`，等待宽限期，再 `killpg(SIGKILL)`。有条件的话给每条命令单独建一个 cgroup，用 `cgroup.kill`（Linux 5.14+）把用 `setsid` 逃出进程组的进程也一起杀掉。
3. **输出写文件，不走管道**：子进程的 stdout/stderr 直接写到文件，返回给模型的是前若干行加文件路径。这样孙进程卡住时调用方不会等 EOF，也不会把几十万行塞进上下文。
4. **杀不掉就不等**：SIGKILL 之后宽限期内还没退出（真正的 D 状态），就记录 pid，放弃 `wait()`，立即返回，并触发熔断。
5. **熔断**：执行 NFS 命令前用 `stat -f <挂载点>` 探活（statfs 每次都会发一次 RPC，适合用来探测）。探测失败就在冷却期内直接拒绝 NFS 命令，避免卡死的进程越积越多。另外用 `pids.max` 给 sandbox 设进程数上限。
6. **并发预算**：限制同一台宿主机上同时进行的重型扫描数（`nfs-run --slots`）和每次扫描的线程数（`pwalk -j`）。打到 NFS 上的总并发约等于 宿主机数 × 槽位数 × 线程数，这个数要和服务端 nfsd 线程数匹配。

参考实现是附录 A 的 `nfs-run`（只用 Python 标准库，约 200 行）。它可以作为命令行工具让 agent 调用，也可以把 `main()` 的逻辑移植到自研 harness 的 executor 里。实测行为：

| 场景 | 结果 |
|---|---|
| `nfs-run --timeout 2 -- 'sleep 31 \| cat'` | 2.06 s 返回，退出码 124，管道两端的进程都被清理 |
| 命令正常结束，但留下后台任务 `'sleep 32 & echo started'` | 立即返回 0，后台的 sleep 被清理 |
| 子进程忽略 SIGTERM | 等宽限期后 SIGKILL，2.06 s 返回 124 |
| 子进程用 `setsid` 逃出进程组 | nfs-run 照常在 1.1 s 返回（输出不走管道，所以不会被拖住）；逃逸的进程仍在运行，需要 cgroup 才能清理 |
| 模拟 SIGKILL 后仍卡在 D 状态 | 1.5 s 返回 125，报告卡住的 pid，写入熔断标记 |
| `--probe` 指向不可用的挂载点 | 立即返回 75；冷却期内后续调用直接失败；其他挂载点不受影响 |
| `--slots 1` 时再并发一个 | 等待 `--slot-wait` 秒后返回 75 |

**如果 harness 是 Claude Code / Agent SDK：**

- 把 `nfs-run`、`nfs-find`、`pwalk` 装进 sandbox 镜像的 PATH（部署见 §9）。
- `nfs-run` 默认超时 90 秒。最坏情况下总耗时 = timeout + 3×grace + slot-wait + probe-timeout ≈ 90 + 9 + 10 + 3 = 112 秒，小于 Bash 工具默认的 120 秒（`BASH_DEFAULT_TIMEOUT_MS`）。命令会被 nfs-run 自己结束，而不是被转入后台。
- 如果希望所有超时命令都直接停止而不是转入后台，可以设置 `CLAUDE_CODE_DISABLE_BACKGROUND_TASKS=1`，代价是 agent 也用不了 `run_in_background`。一般不需要，有 nfs-run 就够了。
- Claude Code 本身已经把命令输出写到文件，超过约 3 万字符时只给模型文件路径和开头 2000 字符的预览，所以第 3 条在 Claude Code 里已经部分满足；自研 harness 需要自己实现。

### 4.2 用 hook 拦截无界遍历

`nfs-guard.py`（附录 C）作为 PreToolUse hook，在命令执行前做字符串分析，不访问任何文件系统，所以 hook 自己不会被 NFS 卡住。拒绝理由会原样展示给模型，理由里直接写了替代命令。

| 拦截 | 放行 |
|---|---|
| `find`/`bfs` 不带 `-maxdepth`，或 `-maxdepth` 大于 3 | `find <目录> -maxdepth 1 ...` |
| `fd`/`rg` 不带 `--max-depth`；`tree` 不带 `-L` | `rg <模式> /mnt/nfs/.index/files.tsv`（放行前缀下的任何操作） |
| `du`（`--max-depth` 只限制输出层级，仍然会遍历整棵树） | `ls -f <目录>`；对单个文件的 `cat`/`grep`/`jq` |
| `ls -R`；`grep -r`/`-R`/`--recursive` | 用 `nfs-run` 包裹的命令（自带超时和清理） |
| `bash -c '...'`、`$(...)` 里的上述命令 | `pwalk --deadline N ...` |
| Python/Node 脚本里的 `os.walk`、`.rglob`、`recursive=True`、`walkSync` | `nfs-find ... \| xargs -d '\n' grep -l ...` |
| `cd /mnt/nfs/...` 之后，或 cwd 在 NFS 上时，对相对路径的遍历 | 显式指向非 NFS 绝对路径的遍历 |
| 指向 NFS 的 Glob / Grep 工具调用 | 指向索引文件的 Grep 工具调用 |

配置（单个项目放 `.claude/settings.json`；整批 sandbox 建议放 `/etc/claude-code/managed-settings.json`，见 §9）：

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash|Glob|Grep",
        "hooks": [
          {
            "type": "command",
            "command": "NFS_GUARD_PREFIXES=/mnt/nfs NFS_GUARD_LOG=/var/log/nfs-guard.jsonl python3 /opt/nfs-tools/nfs-guard.py",
            "timeout": 5
          }
        ]
      }
    ]
  }
}
```

说明：

- 没有 `args` 字段时，hook 的 `command` 通过 `sh -c` 执行，所以可以在前面内联环境变量。`timeout` 的单位是秒。hook 失败或超时时默认放行（fail-open），这对护栏来说是合适的。
- 在 Linux 上，Claude Code 默认不提供 Glob/Grep 工具，`find`/`grep` 会以 Bash 调用的形式经过 hook（底层是内置的 bfs/ugrep）。matcher 里保留 `Glob|Grep`，是为了覆盖通过 `--tools` 或 Agent SDK 显式启用这两个工具的情况。
- hook 是护栏，不是安全边界：写成脚本文件执行、用变量拼路径等都能绕过。真正的兜底是 §4.1 的执行层。
- Grep 工具指向 NFS 上单个文件的调用也会被拦（hook 不 stat，无法区分文件和目录），模型可以改用 Bash 里的 `grep 模式 文件`。
- 每次调用约 30 ms（主要是 Python 启动时间）。
- 调整规则（`NFS_GUARD_MAXDEPTH`、放行前缀、命令列表）之后，先跑一遍附录 G 的测试，再补上对应的新用例。

### 4.3 写进 CLAUDE.md 的规则

```markdown
## /mnt/nfs 使用规则（网络文件系统，几十万个小文件）
- 找文件一律先查索引：`nfs-find --name '*.json' --under /mnt/nfs/<目录> --limit 200`；只要数量加 `--count`；按修改时间筛选用 `--newer 2h`。
- 索引每 5 分钟更新一次，输出末尾有 index_age。要确认某个目录的最新状态，只看那一个目录：`ls -f /mnt/nfs/<目录> | head -200`。
- 不要对 /mnt/nfs 做无界递归：不带 -maxdepth 的 find、du、ls -R、tree、grep -r、对整个目录的 rg/fd、Python os.walk。这些会被 hook 拦截。
- 搜索文件内容：先用 nfs-find 把范围缩小到几百个文件以内，再 `| xargs -d '\n' grep -l <模式>`。
- 确实需要实时扫描：`nfs-run --timeout 90 -- pwalk -j 16 --deadline 80 /mnt/nfs/<目录>`。pwalk 退出码 3 表示结果不完整；完整输出在 nfs-run 打印的文件路径里，用 head/rg 分页查看。
- nfs-run 返回 75（NFS 不健康）或 125（进程卡死）时，不要马上重试同类命令，改用索引，或者向用户报告。
```

### 4.4 P0 验收

- **故障注入**：在一台隔离的测试节点上用 `iptables -A OUTPUT -d <NFS 服务器> -p tcp --dport 2049 -j DROP` 模拟 NFS 无响应，然后让 agent 执行一次扫描。要求：会话在 nfs-run 超时 + 15 秒内拿到结果（124/125/75），之后的 NFS 命令被熔断快速拒绝；删除这条规则后，冷却期（30 秒）过后自动恢复。注意 hard 挂载下这会在该节点上留下 D 状态进程，网络恢复后才会退出，所以只在测试节点上做。
- 超时后 `ps` 里没有残留的 find/pwalk。真正处于 D 状态的进程允许存在，但数量不能持续增长。
- 上线一周后对比基线：Bash 工具超时次数、"moved to the background" 次数、会话卡死次数都应明显下降。

## 5. P1：索引（3–5 天）

### 5.1 格式

索引文件在 `/mnt/nfs/.index/files.tsv`（服务端路径是 `<导出根目录>/.index/files.tsv`）：

```
#nfs-index v1	built_at=1792996254	duration=3	count=312345	errors=0	root=/export/data
d	4096	1792990000.123456	ds001
f	1834	1792991234.000000	ds001/shard000/sample_001_000_0000.json
```

- 首行是元信息：构建开始时间、耗时、条数、遍历错误数、服务端根路径。
- 其余每行是 `类型<TAB>大小<TAB>mtime<TAB>相对路径`，按路径排序，方便对比两次构建得到增删列表。路径放在最后一列，所以路径里有 tab 也能正确解析；名字里含换行的条目会被跳过。
- 31 万行大约 20 MB。客户端第一次读取是一次顺序大读，之后留在页缓存里，每次查询只多一次属性校验。实测在 31 万行的索引上，`nfs-find` 查询耗时 0.16–0.32 秒，直接用 `rg` 计数是 0.02 秒（本地磁盘、页缓存已热）。

### 5.2 构建（附录 D）

**服务端可控（推荐）**：在 NFS 服务端本地遍历，不经过网络。

```bash
install -m 0755 build-nfs-index.sh /opt/nfs-tools/
time /opt/nfs-tools/build-nfs-index.sh /export/data      # 先手动跑一次，看耗时
```

```
# /etc/cron.d/nfs-index：每 5 分钟重建一次；flock 防止上一次还没跑完时重入
*/5 * * * * root flock -n /run/nfs-index.lock /opt/nfs-tools/build-nfs-index.sh /export/data >> /var/log/nfs-index.log 2>&1
```

脚本内置的保护：

- 先写临时文件，再在同一目录内 rename，读者看到的要么是旧索引，要么是新索引，不会读到写了一半的文件；
- 新索引条数低于旧索引的 50% 时拒绝发布（例如底层存储挂载异常导致遍历结果为空），确认无误后可以用 `FORCE=1` 强制发布；
- 剪掉索引目录本身和 `.snapshot`、`.zfs` 这类存储快照目录（否则会把快照里的历史版本也遍历一遍）；
- 遍历出错（例如文件在遍历过程中被删除）不会中断构建，只计入 `errors`。

**服务端不可控（托管 NAS）**：选一台专用的 indexer 节点（不要在 agent 的 sandbox 里跑），用 pwalk 并行遍历，产出格式完全相同：

```bash
WALKER=pwalk THREADS=32 /opt/nfs-tools/build-nfs-index.sh /mnt/nfs
```

这需要 pwalk 在 PATH 中，并且对 `/mnt/nfs/.index` 有写权限；也可以把第二个参数指向别的目录，再分发到各节点。重建频率按实测耗时定（例如 15–30 分钟一次）。只有这一台节点扫描，所有 sandbox 共用结果。

### 5.3 查询（附录 E）

```bash
nfs-find --name '*.json' --under /mnt/nfs/data/2026 --limit 100
nfs-find --iname 'readme*' --type f
nfs-find --path 'logs/*/error-*.txt' --newer 2h --long       # --path 是相对 NFS_ROOT 的 glob，* 可以跨目录
nfs-find --regex '/user_[0-9]+/profile\.json$' --count
nfs-find --under /mnt/nfs/data --min-size 1048576 --long     # 大于 1 MB 的文件
nfs-find --name '*.log' --under /mnt/nfs/app --newer 1d | xargs -d '\n' grep -l ERROR
rg -c '\.parquet$' /mnt/nfs/.index/files.tsv                 # 临时的模式也可以直接 rg 索引文件
```

- 结果写 stdout，每行一个绝对路径，方便接 `xargs`；统计信息写 stderr，例如 `[nfs-find] matched=797 shown=50（已截断……） index_age=2m10s`。
- 索引超过 `NFS_INDEX_MAX_AGE`（默认 900 秒）没更新时，会额外输出警告，提醒模型对具体目录复核。
- 退出码：0 有匹配，1 无匹配，2 用法错误或索引不存在。

### 5.4 新鲜度

| 方式 | 新鲜度 | 前提和代价 | 建议 |
|---|---|---|---|
| 服务端周期性全量重建 | 1–5 分钟 | 服务端本地遍历 | 默认 |
| 写入方维护清单（生产者写文件时顺便追加一行记录） | 实时 | 能改写入方代码 | 数据由自己的 pipeline 产生时最好 |
| fanotify 文件系统级监听（`FAN_MARK_FILESYSTEM` + `FAN_REPORT_DFID_NAME`，Linux 5.9+，需要 CAP_SYS_ADMIN） | 秒级 | 只能在服务端跑；重启或溢出会丢事件，仍要周期性全量重建兜底 | 对秒级新鲜度有硬要求时再用 |
| inotify 递归监听 | 秒级 | 每个目录一个 watch，要调 `fs.inotify.max_user_watches`；同样会丢事件 | 不推荐 |

无论用哪种方式，在 agent 侧都要遵守一条规则：做删除、覆盖这类关键操作之前，对具体目录 `ls -f` 复核，不要只凭索引（已写进 §4.3 的 CLAUDE.md 规则）。

### 5.5 可选扩展

- **MCP 工具**（附录 F）：把 nfs-find 封装成 `nfs_search` 工具，参数有类型，返回条数上限固定为 2000，模型不用自己拼 shell。已经用 MCP SDK 客户端在 mcp 1.30.0 和 2.3.0 上端到端测过。注册方式：`claude mcp add nfs-index -- python3 /opt/nfs-tools/nfs-index-mcp.py`。
- **近数据查询服务**：服务端可控而且经常要搜文件内容时，可以在 NFS 服务端上跑一个只读查询服务，只提供固定的几种操作（按名字查找、按内容 grep），带结果条数上限和超时，在服务端本地执行，再通过 MCP 暴露给 agent。不要开放任意 shell。
- **全文索引**：如果内容搜索是主要需求，用专门的代码/全文搜索引擎建内容索引，不要指望每次 grep 几十万个文件。

### 5.6 P1 验收

- "找文件"类请求有 90% 以上走索引（看 nfs-guard 拦截日志和 nfs-find 调用量）；
- nfs-find 查询 p95 < 1 秒；
- 索引年龄 p95 < 10 分钟（看 `files.tsv` 首行的 `built_at`）。

## 6. P2：数据布局（按数据集推进）

### 6.1 只读数据：做成镜像

```bash
# 在服务端构建镜像（zstd 压缩需要 squashfs-tools ≥ 4.4、内核 ≥ 4.14）
mksquashfs /export/data/corpus /export/images/corpus-20261026.sqfs -comp zstd -noappend -processors 8

# 在宿主机上挂载，再 bind 进 sandbox（sandbox 里通常没有 CAP_SYS_ADMIN 和 loop 设备）
mount -t squashfs -o loop,ro /mnt/nfs/images/corpus-20261026.sqfs /srv/corpus/20261026
docker run ... -v /srv/corpus/20261026:/data/corpus:ro ...

# 不想用特权的话用 squashfuse（需要 /dev/fuse）
squashfuse /mnt/nfs/images/corpus-20261026.sqfs /data/corpus
```

- NFS 上只有一个大文件。目录遍历和 stat 都在本地内核里完成，只有读到数据块时才会产生 NFS 读请求，而且是大块读，有页缓存。
- 镜像不可变，文件名带版本号。sandbox 启动时固定使用某个版本；数据更新时发布新镜像，不影响正在运行的会话。
- 镜像挂载点不要加进 `NFS_GUARD_PREFIXES`，agent 在里面可以直接用 find。
- erofs（内核 5.4+，用 `mkfs.erofs` 构建）的随机读性能通常更好，可以替代 squashfs。

### 6.2 启动时预拉取

适合每个 sandbox 只用到数据的一个子集、而且本地盘放得下的情况：

```bash
# 服务端按 sandbox 用到的粒度预先打包，例如每个项目一个包
tar -C /export/data -cf - proj042 | zstd -T0 -3 > /export/snapshots/proj042.tar.zst
# sandbox 启动时一次顺序大读，代替几十万次小文件元数据操作
zstd -dc /mnt/nfs/snapshots/proj042.tar.zst | tar -C /local/work -xf -
```

这种方式下产出的结果要显式写回 NFS，适合"读多写少、写的文件不多"的任务。

### 6.3 大目录分片

单个目录里放几万到几十万个文件，是 NFS 上最糟的组织方式：

- 列一次目录要几百次 READDIR 分页；
- 在一些内核版本上，遍历过程中目录被修改会让客户端反复重读目录，一个持续被写入的大目录可能很难列完；
- 服务端本地文件系统在超大目录上的查找也会变慢。

建议单个目录不超过 1 万个条目。按 ID 的哈希值建两级目录，例如 `ab/cd/abcdef123.json`（256×256 = 65536 个桶）。迁移期间新旧路径并存，读取方先查新路径，查不到再回退到旧路径。

## 7. P3：挂载参数与服务端调优（测量之后再改）

每一项都要对照 §1.3 的基线做 A/B 测试，没有收益的不上。

| 参数 | 作用 | 适用 | 代价和风险 |
|---|---|---|---|
| `nconnect=4~16`（内核 5.3+） | 用多条 TCP 连接并发收发 RPC，配合并行遍历通常有帮助 | 多线程/多进程访问 | 服务端连接数增加 |
| `vers=4.1/4.2` vs `vers=3` | v4 的复合请求能减少部分往返；但 v4 打开文件要多发有状态的 OPEN/CLOSE，大量读小文件时可能比 v3 慢 | 看服务端支持情况 | 锁和权限语义不同，必须实测 |
| `actimeo=60` 或更大（也可分别设 `acregmin` 等） | 属性缓存保留更久，重复访问时少发 GETATTR | 读多写少 | 其他客户端的修改要更晚才能看到 |
| `nocto` | 打开文件时不强制重新校验属性，每次 open 少一次 GETATTR | 只读或单写者 | 可能读到旧内容 |
| `ro,soft,timeo=50,retrans=2`（较新内核还可加 `softerr`） | 服务端无响应时大约 30 秒（5+10+15，线性退避）返回错误，而不是无限挂起 | **只读**挂载 | 可写挂载用 soft 可能静默丢写，不要用 |
| `rdirplus`（默认）/ `nordirplus` | 是否使用 READDIRPLUS | 保持默认 | `nordirplus` 会让 v3 上的递归遍历变成逐条 stat |
| `lookupcache=all` | — | 已经是默认值 | 不用设置 |
| `rsize/wsize=1M` | 提升大文件吞吐 | 对小文件元数据没有影响，一般协商结果已经是 1M | — |
| `fsc` + cachefilesd | 在本地盘缓存**文件内容** | 反复读同一批文件的内容 | 不缓存目录项和属性，对 find 没有帮助 |

客户端内核参数：`vm.vfs_cache_pressure=50`（默认 100）让 dentry/inode 缓存保留更久，重复遍历时能更多命中本地缓存（仍然受 actimeo 约束）。

服务端：

- **nfsd 线程数**：`/proc/fs/nfsd/threads`，或 `/etc/nfs.conf` 里 `[nfsd]` 段的 `threads=`。默认值偏小（常见 8 或 16），多个 sandbox 并行遍历时请求会排队。按"同时在途的 RPC 数"估算，例如 64–256，同时观察 CPU。
- 底层文件系统用 `noatime`（至少 `relatime`）挂载，避免读操作触发 atime 写入。
- 内存要足够，让 inode/dentry 缓存能装下全部元数据（30 万个文件大约需要几百 MB）。

## 8. 必须实时扫描时怎么做

- **首选 pwalk**（附录 B）：多个线程同时读多个目录，耗时近似按线程数缩短，直到服务端或连接成为瓶颈（这一点需要在你们的 NFS 上实测）。支持截止时间和条数上限，到点返回已拿到的部分结果（退出码 3）。不跟随符号链接；默认不对条目 stat，只在 d_type 未知时回退。和 GNU find 逐条对比过，结果一致。
  ```bash
  # agent 在 sandbox 里用（这两种写法 hook 都会放行）
  nfs-run --timeout 90 -- pwalk -j 16 --deadline 80 --exclude .snapshot /mnt/nfs/data/proj042
  pwalk -j 16 --max-depth 2 /mnt/nfs/data                    # 只看两层
  # 运维在 indexer 节点上用：附带类型/大小/mtime，每个条目多一次 lstat，不设截止时间
  pwalk -j 32 --format index /mnt/nfs/data > list.tsv
  ```
- **用 fd 时**：`fd -HI -j 16 --exclude .snapshot . /mnt/nfs/data`。`-H` 包含隐藏文件，`-I` 不读 .gitignore，否则结果和 find 不一致。
- **用 find 时**：只用 `-name`、`-path`、`-type` 这类不需要读 inode 的谓词，`-size`、`-mtime` 这类过滤交给索引；一定要加 `-maxdepth`，并且 `-prune` 掉 `.snapshot`。
- 不要用 `ls -l`、`ls -R`、`du` 做统计，数量和大小都从索引里取。
- 线程数不是越大越好：NFS 上的总并发 = 同时进行的扫描数 × 每次扫描的线程数。建议单次 `-j 16`，再用 `nfs-run --slots` 限制同一宿主机上同时进行的扫描数。

## 9. 部署清单

**sandbox 镜像**：

```dockerfile
COPY nfs-tools/ /opt/nfs-tools/
RUN chmod 0755 /opt/nfs-tools/* \
 && ln -s /opt/nfs-tools/nfs-run /opt/nfs-tools/nfs-find /opt/nfs-tools/pwalk /usr/local/bin/
# managed-settings.json 的内容是 §4.2 的 hooks 配置
COPY managed-settings.json /etc/claude-code/managed-settings.json
ENV NFS_ROOT=/mnt/nfs \
    NFS_RUN_PROBE=/mnt/nfs \
    NFS_RUN_SLOTS=2 \
    NFS_RUN_SLOT_DIR=/run/nfs-run \
    NFS_RUN_LOG=/var/log/nfs-run.jsonl
```

- `NFS_RUN_SLOT_DIR` 要用宿主机目录 bind 进同一宿主机上的所有 sandbox（例如 `-v /run/nfs-run:/run/nfs-run`），槽位才是按宿主机计算的；否则只在单个 sandbox 内生效。
- 日志路径（`NFS_RUN_LOG`、`NFS_GUARD_LOG`）必须在本地盘上（不能放在 NFS 上），并且运行 agent 的用户要有写权限；写不进去时脚本会静默跳过，不影响执行。
- 运行 sandbox 时设置进程数上限，例如 `docker run --pids-limit 512`，防止卡死的进程无限堆积。
- 如果要防止项目里的配置绕过这个 hook，可以在 managed settings 里同时开启 `allowManagedHooksOnly`。它会限制非托管 hook 的运行，开启前先评估对其他 hook 的影响。
- CLAUDE.md 规则（§4.3）放进 sandbox 的用户级或项目级 CLAUDE.md。

**NFS 服务端**：安装 `build-nfs-index.sh` 并配置 cron（§5.2）；按 §7 调整 nfsd 线程数和底层文件系统的 atime 设置。

**可选**：MCP 工具（§5.5）；只读数据集的镜像发布流程（§6.1）。

## 10. 上线计划、监控与回滚

| 步骤 | 交付 | 验收 |
|---|---|---|
| 0 | 按 §1.3 记录基线 | 基线表填完 |
| P0 | 镜像加入 nfs-tools；下发 hook；CLAUDE.md 规则；自研 executor 满足 §4.1 的六条约束 | §4.4 |
| P1 | 服务端 cron 建索引；nfs-find；可选 MCP | §5.6 |
| P2 | 只读数据集镜像化；大目录分片计划 | 对应数据集上的 find 超时降为 0 |
| P3 | 参数逐项 A/B | 每项都有前后对比数据 |

持续监控：

- `nfs-run.jsonl`：按 status 统计（ok / timeout / stuck / unhealthy / no-slot）和耗时分布；
- `nfs-guard.jsonl`：按拦截动作统计。如果某类命令被反复拦截，说明规则或工具还缺一条好用的替代路径；
- D 状态进程数（node_exporter 的 `node_procs_blocked`，或 `ps -eo stat | grep -c '^D'`）；
- NFS 每类操作的 RTT（`/proc/self/mountstats`，node_exporter 有 mountstats collector）；
- 索引年龄（`files.tsv` 首行的 `built_at`）。

回滚：所有改动都是增量的、相互独立的。从 managed settings 里删掉 hook 即可取消拦截；工具是独立命令；索引只是一个只读文件。

## 11. 风险与取舍

| 风险 | 缓解 |
|---|---|
| 索引滞后，agent 基于旧数据做判断 | 输出带 index_age，超过 15 分钟会警告；关键操作前对具体目录 `ls -f` 复核（已写进 CLAUDE.md） |
| hook 误拦合法命令 | 拒绝理由里给出替代写法；用 `nfs-run` 包裹就会放行；`NFS_GUARD_MAXDEPTH`、`NFS_GUARD_ALLOW` 可调；定期回看拦截日志 |
| hook 被绕过（脚本文件、变量拼路径） | hook 只是护栏，执行层的超时、进程组清理和熔断是兜底 |
| 熔断误伤（探测偶发失败） | 冷却期默认 30 秒，探测成功立即恢复；按挂载点分别熔断 |
| 并行扫描把服务端打满 | `--slots` 和 `-j` 控制总并发；服务端 nfsd 线程数与之匹配；监控 RTT |
| soft / nocto / 长 actimeo 带来一致性问题 | 只用于只读或单写者的数据集，按挂载点分别配置 |
| 镜像方案需要特权 | 在宿主机上挂载后 bind 进 sandbox，或用 squashfuse |

---

## 附录：脚本

所有脚本只依赖 Python 3.8+ 标准库或 bash + GNU coreutils/findutils（MCP 封装除外）。建议统一放在 `/opt/nfs-tools/`。

测试摘要：

| 组件 | 测了什么 | 结果 |
|---|---|---|
| pwalk | 与 GNU find 逐条对比全部条目（文件名含空格、换行、tab、非 UTF-8 字节，符号链接环，断链）；`--max-depth`、`--exclude`/`--prune` 与 find 等价写法对比；条数截断、截止时间、管道提前关闭 | 12401 个条目完全一致；各项一致；退出码符合预期 |
| build-nfs-index.sh | find 和 pwalk 两种 walker 的产出对比；剪枝；文件权限；空索引保护 | 12346 行一致；`.snapshot`、`.index`、含换行的名字都被排除；权限 0644；条数骤降时拒绝发布，`FORCE=1` 可以覆盖 |
| nfs-find | 9 类查询与等价的 find 命令对比；截断提示、过期警告、退出码、管道提前关闭；31 万行索引上的耗时 | 结果全部一致；单次查询 0.16–0.32 秒 |
| nfs-run | 管道超时、后台残留、忽略 SIGTERM、setsid 逃逸、退出码透传、探活熔断、并发槽位、模拟 D 状态 | 见 §4.1 表格 |
| nfs-guard.py | 45 个用例（各类拦截和放行写法）+ 非法输入，测试脚本见附录 G；另做了变异测试（故意删掉一条规则，测试能发现） | 全部通过；单次调用约 30 ms |
| nfs-index-mcp.py | 用 MCP SDK 客户端经 stdio 端到端调用 | mcp 1.30.0 和 2.3.0 都通过 |

### 附录 A：nfs-run（执行层兜底）

安装位置：sandbox 镜像 `/opt/nfs-tools/nfs-run`，并链接到 PATH。

```python
#!/usr/bin/env python3
"""nfs-run: 给一条命令加硬性时间上限的执行器（只依赖 Python 3.8+ 标准库）。

- 子进程放进独立会话/进程组，超时后对整个进程组 TERM -> KILL，不留孤儿 find/grep；
- stdout/stderr 直接写到落盘文件而不是管道：孙进程卡住也不会让调用方等 EOF；
- KILL 后仍不退出（不可中断的 D 状态）就放弃等待并报告，绝不阻塞调用方；
- 可选：执行前对 NFS 做 statfs 健康探测并熔断；可选：主机级并发槽位。

用法: nfs-run [--timeout 100] [--head 200] [--probe /mnt/nfs] [--slots 4] -- CMD [ARGS...]
      只给一个参数时按 bash -c 执行，管道写在引号里: nfs-run -- 'find /mnt/nfs/a -maxdepth 2 | wc -l'
退出码: 命令自身退出码; 124 超时已杀掉; 125 超时且杀不掉(D 状态); 75 NFS 不健康/无空闲槽位
"""
import argparse
import fcntl
import json
import os
import signal
import subprocess
import sys
import tempfile
import time


def log_event(**fields):
    """NFS_RUN_LOG 指向本地文件时，每次执行追加一行 JSON，便于统计超时/卡死。"""
    path = os.environ.get("NFS_RUN_LOG")
    if path:
        try:
            with open(path, "a") as f:
                f.write(json.dumps({"ts": round(time.time(), 3), **fields}, ensure_ascii=False) + "\n")
        except OSError:
            pass


def killpg(pgid, sig):
    try:
        os.killpg(pgid, sig)
    except (ProcessLookupError, PermissionError):
        pass


def group_members(pgid):
    """扫描 /proc 找出进程组里还活着的进程 [(pid, state, comm)]；不碰 NFS。"""
    members = []
    for name in os.listdir("/proc"):
        if not name.isdigit():
            continue
        try:
            with open(f"/proc/{name}/stat", "rb") as f:
                data = f.read().decode(errors="replace")
        except OSError:
            continue
        rparen = data.rfind(")")
        fields = data[rparen + 2:].split()  # state ppid pgrp ...
        if len(fields) > 2 and int(fields[2]) == pgid and fields[0] not in ("Z", "X"):
            members.append((int(name), fields[0], data[data.find("(") + 1:rparen]))
    return members


def breaker(state_dir, path):
    """每个挂载点一个熔断标记文件，mtime 即最近一次失败时间。"""
    return os.path.join(state_dir, "unhealthy" + (path.rstrip("/") or "/").replace("/", "_"))


def nfs_healthy(path, timeout, state_dir, cooldown):
    """statfs 在 NFS 上每次都会发 RPC，适合做探活；探测进程卡住就丢下不等。"""
    marker = breaker(state_dir, path)
    try:
        if time.time() - os.stat(marker).st_mtime < cooldown:
            return False  # 熔断期内直接失败，避免再堆积卡死的进程
    except FileNotFoundError:
        pass
    probe = subprocess.Popen(["stat", "-f", path], stdin=subprocess.DEVNULL,
                             stdout=subprocess.DEVNULL, stderr=subprocess.DEVNULL,
                             start_new_session=True)
    try:
        ok = probe.wait(timeout=timeout) == 0
    except subprocess.TimeoutExpired:
        killpg(probe.pid, signal.SIGKILL)
        ok = False
    if ok:
        try:
            os.unlink(marker)
        except FileNotFoundError:
            pass
    else:
        open(marker, "w").close()
    return ok


def acquire_slot(slot_dir, slots, wait):
    """flock 实现的计数信号量；返回的 fd 持有到本进程退出（子进程不会继承）。"""
    os.makedirs(slot_dir, exist_ok=True)
    deadline = time.monotonic() + wait
    while True:
        for i in range(slots):
            fd = os.open(os.path.join(slot_dir, f"slot{i}"), os.O_CREAT | os.O_RDWR, 0o666)
            try:
                fcntl.flock(fd, fcntl.LOCK_EX | fcntl.LOCK_NB)
                return fd
            except BlockingIOError:
                os.close(fd)
        if time.monotonic() >= deadline:
            return None
        time.sleep(0.5)


def main():
    env = os.environ.get
    ap = argparse.ArgumentParser(prog="nfs-run", description=__doc__.split("\n")[0])
    ap.add_argument("--timeout", type=float, default=float(env("NFS_RUN_TIMEOUT", "90")),
                    help="秒；timeout+3*grace+slot-wait+probe-timeout 应小于 harness 的工具超时"
                         "（Claude Code 默认 120s）")
    ap.add_argument("--grace", type=float, default=3.0, help="TERM 与 KILL 之间等待的秒数")
    ap.add_argument("--head", type=int, default=200, help="直接打印的输出行数")
    ap.add_argument("--spill-dir", default=env("NFS_RUN_SPILL_DIR",
                                               os.path.join(tempfile.gettempdir(), "nfs-run")))
    ap.add_argument("--probe", default=env("NFS_RUN_PROBE"), help="执行前对该路径做 statfs 探活")
    ap.add_argument("--probe-timeout", type=float, default=3.0)
    ap.add_argument("--cooldown", type=float, default=30.0, help="探活失败后的熔断秒数")
    ap.add_argument("--slots", type=int, default=int(env("NFS_RUN_SLOTS", "0")),
                    help="同一 slot-dir 下最多同时运行的 nfs-run 数，0 不限制")
    ap.add_argument("--slot-dir", default=env("NFS_RUN_SLOT_DIR", "/run/nfs-run"))
    ap.add_argument("--slot-wait", type=float, default=10.0)
    ap.add_argument("cmd", nargs=argparse.REMAINDER)
    a = ap.parse_args()
    cmd = a.cmd[1:] if a.cmd[:1] == ["--"] else a.cmd
    if not cmd:
        ap.error("缺少要执行的命令")
    argv = ["bash", "-c", cmd[0]] if len(cmd) == 1 else cmd
    os.makedirs(a.spill_dir, exist_ok=True)

    if a.probe and not nfs_healthy(a.probe, a.probe_timeout, a.spill_dir, a.cooldown):
        print(f"[nfs-run] {a.probe} 探活失败或处于熔断期（{a.cooldown:.0f}s），未执行命令。"
              "NFS 可能不健康：稍后重试，或先用 nfs-find 查索引。", file=sys.stderr)
        log_event(status="unhealthy", code=75, cmd=" ".join(cmd)[:300])
        return 75
    if a.slots > 0 and acquire_slot(a.slot_dir, a.slots, a.slot_wait) is None:
        print(f"[nfs-run] 等待 {a.slot_wait:.0f}s 仍无空闲槽位（上限 {a.slots}），未执行命令。",
              file=sys.stderr)
        log_event(status="no-slot", code=75, cmd=" ".join(cmd)[:300])
        return 75

    fd, spill = tempfile.mkstemp(prefix="out-", suffix=".log", dir=a.spill_dir)
    t0 = time.monotonic()
    try:
        proc = subprocess.Popen(argv, stdin=subprocess.DEVNULL, stdout=fd,
                                stderr=subprocess.STDOUT, start_new_session=True)
    except OSError as e:
        print(f"[nfs-run] 无法启动 {argv[0]}: {e}", file=sys.stderr)
        return 127
    finally:
        os.close(fd)

    status, rc = "ok", None
    try:
        rc = proc.wait(timeout=a.timeout)
    except subprocess.TimeoutExpired:
        status = "timeout"
        for sig in (signal.SIGTERM, signal.SIGKILL):
            killpg(proc.pid, sig)
            try:
                rc = proc.wait(timeout=a.grace)
                break
            except subprocess.TimeoutExpired:
                pass
    killpg(proc.pid, signal.SIGKILL)  # 清理组内残留：管道其他成员、后台任务
    settle = time.monotonic() + (a.grace if status != "ok" else 0.5)
    while True:
        stuck = group_members(proc.pid)
        if not stuck or time.monotonic() >= settle:
            break
        time.sleep(0.1)
    if stuck or rc is None:
        status = "stuck"
        if a.probe:
            open(breaker(a.spill_dir, a.probe), "w").close()  # 触发熔断
    elapsed = time.monotonic() - t0

    lines, shown = 0, []
    with open(spill, "rb") as f:
        for line in f:
            if lines < a.head:
                shown.append(line if len(line) <= 2000 else line[:2000] + b"...[line truncated]\n")
            lines += 1
    out = sys.stdout.buffer
    out.writelines(shown)
    if shown and not shown[-1].endswith(b"\n"):
        out.write(b"\n")
    out.flush()

    size = os.path.getsize(spill)
    msg = f"[nfs-run] status={status} elapsed={elapsed:.1f}s output={lines} lines/{size} bytes"
    if lines > len(shown) or status != "ok":
        msg += f" (shown {len(shown)}) full output: {spill}"
    else:
        os.unlink(spill)
    if status == "timeout":
        msg += (f"\n[nfs-run] 超过 {a.timeout:.0f}s，已终止整个进程组。以上是部分输出。"
                "建议：nfs-find 查索引 / 缩小目录范围 / pwalk --deadline 拿部分结果。")
    elif status == "stuck":
        procs = ", ".join(f"{pid}({comm},{st})" for pid, st, comm in stuck) or str(proc.pid)
        msg += (f"\n[nfs-run] SIGKILL 后仍有进程未退出: {procs}。通常是 NFS 无响应导致的"
                f" D 状态；已放弃等待{'并触发熔断' if a.probe else ''}，请不要立即重试同类命令。")
    print(msg, file=sys.stderr)

    code = 124 if status == "timeout" else 125 if status == "stuck" else (rc if rc >= 0 else 128 - rc)
    log_event(status=status, code=code, elapsed=round(elapsed, 1), lines=lines, cmd=" ".join(cmd)[:300])
    return code


if __name__ == "__main__":
    sys.exit(main())
```

### 附录 B：pwalk（并行遍历）

安装位置：sandbox 镜像和 indexer 节点的 `/opt/nfs-tools/pwalk`，并链接到 PATH。

```python
#!/usr/bin/env python3
"""pwalk: 面向 NFS 等高延迟文件系统的并行目录遍历（只依赖 Python 3.8+ 标准库）。

NFS 上遍历慢在"串行往返"而不是带宽，多线程同时读多个目录可以把耗时近似除以并发数。
- 不跟随符号链接；默认不对条目做 stat（只在 d_type 未知时由内核/Python 回退 lstat）；
- --deadline / --max-entries 到点即停，输出已拿到的部分并以退出码 3 标明"不完整"；
- --format index 输出与 build-nfs-index.sh 相同的 TSV（会对每个条目 lstat）。

用法: pwalk [-j 32] [--deadline 90] [--max-entries N] [--max-depth N]
            [--exclude NAME]... [--prune PATH]... [--format path|index] [-0] ROOT
退出码: 0 完成; 1 完成但有目录读取失败; 3 因 deadline/max-entries 截断; 130 被中断
"""
import argparse
import os
import queue
import stat
import sys
import threading
import time

TYPES = {stat.S_IFREG: b"f", stat.S_IFDIR: b"d", stat.S_IFLNK: b"l", stat.S_IFIFO: b"p",
         stat.S_IFSOCK: b"s", stat.S_IFCHR: b"c", stat.S_IFBLK: b"b"}


def main():
    ap = argparse.ArgumentParser(prog="pwalk", description=__doc__.split("\n")[0])
    ap.add_argument("root")
    ap.add_argument("-j", "--threads", type=int, default=32)
    ap.add_argument("--deadline", type=float, default=0, help="秒，0 表示不限")
    ap.add_argument("--max-entries", type=int, default=0, help="0 表示不限")
    ap.add_argument("--max-depth", type=int, default=0, help="同 find -maxdepth，0 表示不限")
    ap.add_argument("--exclude", action="append", default=[], help="按名字剪枝（任意层级），可重复")
    ap.add_argument("--prune", action="append", default=[], help="按完整路径剪枝，可重复")
    ap.add_argument("--format", choices=("path", "index"), default="path")
    ap.add_argument("-0", dest="nul", action="store_true", help="以 NUL 分隔输出")
    a = ap.parse_args()

    root = os.fsencode(a.root).rstrip(b"/") or b"/"
    cut = len(root.rstrip(b"/")) + 1  # 截掉 "root/" 得到相对路径
    exclude = {os.fsencode(x) for x in a.exclude}
    prune = {os.fsencode(x).rstrip(b"/") for x in a.prune}
    end = b"\0" if a.nul else b"\n"
    out = sys.stdout.buffer
    lock = threading.Lock()
    stop = threading.Event()
    st = {"entries": 0, "dirs": 0, "errors": 0, "skipped": 0, "why": ""}
    q = queue.Queue()

    def halt(why):
        if not stop.is_set():
            st["why"] = why
            stop.set()

    def scan(path, depth):
        lines, subdirs, errors, skipped = [], [], [], 0
        try:
            with os.scandir(path) as it:
                for e in it:
                    if e.name in exclude or e.path in prune:
                        continue
                    if a.format == "index":
                        rel = e.path[cut:]
                        if b"\n" in rel:
                            skipped += 1  # 名字含换行会破坏按行格式
                            continue
                        try:
                            s = e.stat(follow_symlinks=False)
                        except OSError as err:  # 遍历期间被删除等
                            errors.append(err)
                            continue
                        lines.append(b"%s\t%d\t%.6f\t%s" % (
                            TYPES.get(stat.S_IFMT(s.st_mode), b"?"), s.st_size, s.st_mtime, rel))
                    else:
                        lines.append(e.path)
                    if e.is_dir(follow_symlinks=False) and (not a.max_depth or depth + 1 < a.max_depth):
                        subdirs.append(e.path)
        except OSError as err:
            errors.append(err)
        for d in subdirs:
            q.put((d, depth + 1))
        with lock:
            if stop.is_set():
                return
            st["dirs"] += 1
            st["skipped"] += skipped
            for err in errors:
                st["errors"] += 1
                if st["errors"] <= 20:
                    print(f"pwalk: {os.fsdecode(err.filename or b'')}: {err.strerror}", file=sys.stderr)
            if a.max_entries and st["entries"] + len(lines) > a.max_entries:
                lines = lines[:a.max_entries - st["entries"]]
                halt("max-entries")
            st["entries"] += len(lines)
            if lines:
                try:
                    out.write(end.join(lines) + end)
                except BrokenPipeError:
                    halt("broken-pipe")

    def worker():
        while True:
            path, depth = q.get()
            try:
                if not stop.is_set():
                    scan(path, depth)
            finally:
                q.task_done()

    t0 = time.monotonic()
    q.put((root, 0))
    for _ in range(max(1, a.threads)):
        threading.Thread(target=worker, daemon=True).start()
    done = threading.Event()
    threading.Thread(target=lambda: (q.join(), done.set()), daemon=True).start()
    try:
        if not done.wait(a.deadline or None):
            halt("deadline")  # 卡在系统调用里的线程不再等待，直接带部分结果退出
    except KeyboardInterrupt:
        halt("interrupted")
    with lock:  # 持锁退出，保证不会有线程写出半截输出
        try:
            out.flush()
        except BrokenPipeError:
            pass
        why = st["why"]
        msg = (f"[pwalk] entries={st['entries']} dirs={st['dirs']} errors={st['errors']} "
               f"elapsed={time.monotonic() - t0:.2f}s threads={a.threads}")
        if st["skipped"]:
            msg += f" skipped_newline_names={st['skipped']}"
        if why in ("deadline", "max-entries", "interrupted"):
            msg += f" TRUNCATED({why}): 结果不完整"
        print(msg, file=sys.stderr, flush=True)
        code = {"deadline": 3, "max-entries": 3, "interrupted": 130}.get(
            why, 1 if st["errors"] else 0)
        os._exit(code)


if __name__ == "__main__":
    main()
```

### 附录 C：nfs-guard.py（PreToolUse hook）

安装位置：sandbox 镜像 `/opt/nfs-tools/nfs-guard.py`；配置见 §4.2。

```python
#!/usr/bin/env python3
"""Claude Code PreToolUse hook: 拦截对 NFS 路径的无界递归遍历，引导到 nfs-find / nfs-run。

- 只做字符串分析，绝不访问文件系统（hook 自己不能被 NFS 卡住）；
- 这是护栏不是安全边界：脚本文件、变量拼路径等都能绕过，兜底靠 nfs-run / 执行层；
- 输入解析失败一律放行（fail-open），避免 hook 故障挡住正常工作。
环境变量: NFS_GUARD_PREFIXES  冒号分隔的 NFS 挂载点，默认 /mnt/nfs
          NFS_GUARD_ALLOW     冒号分隔的放行前缀，默认 <每个挂载点>/.index
          NFS_GUARD_MAXDEPTH  允许的最大遍历深度（find -maxdepth、fd/rg --max-depth、tree -L），默认 3
          NFS_GUARD_LOG       可选，本地日志文件；每次拦截追加一行 JSON
"""
import json
import os
import re
import shlex
import sys
import time

PREFIXES = [p.rstrip("/") for p in os.environ.get("NFS_GUARD_PREFIXES", "/mnt/nfs").split(":") if p]
ALLOW = [p.rstrip("/") for p in os.environ.get(
    "NFS_GUARD_ALLOW", ":".join(p + "/.index" for p in PREFIXES)).split(":") if p]
MAXDEPTH = int(os.environ.get("NFS_GUARD_MAXDEPTH", "3"))

SEPARATORS = {"|", "||", "&", "&&", ";", ";;", "|&"}
DEPTH_FLAGS = {"find": ("-maxdepth",), "bfs": ("-maxdepth",), "fd": ("-d", "--max-depth"),
               "fdfind": ("-d", "--max-depth"), "rg": ("-d", "--max-depth"), "tree": ("-L",),
               "pwalk": ("--max-depth",)}
ALWAYS_HEAVY = {"du"}  # du --max-depth 只限制输出层级，仍会遍历整棵树
GREPS = {"grep", "egrep", "fgrep", "ugrep"}
GREP_RECURSIVE = re.compile(r"-[a-zA-Z]*[rR][a-zA-Z]*|--recursive|--dereference-recursive|--directories=recurse")
LS_RECURSIVE = re.compile(r"-[a-zA-Z]*R[a-zA-Z]*|--recursive")
SCRIPT_WALK = re.compile(r"os\.walk|\.rglob\b|recursive\s*=\s*True|walkSync|readdirSync")
PATH_RE = re.compile(r"/[^\s'\"`(),;|&<>=]*")

REASON = """已拦截：{what} 会在 NFS（{where}）上做无界递归遍历。几十万个文件意味着几十万次元数据 RPC，容易超时并卡住会话。
请改用：
1) 按名字/路径找文件：nfs-find --name '*.json' --under <目录> --limit 200（查预建索引，通常 1 秒内；只要数量加 --count）
2) 只看某一个目录：ls -f <目录> | head -100，或 find <目录> -maxdepth 1 ...
3) 必须实时扫描：nfs-run --timeout 90 -- pwalk -j 16 --deadline 80 <目录>（有时间上限，输出落盘，超时返回部分结果）
内容搜索：先用 nfs-find 缩小文件列表，再 | xargs -d '\\n' grep -l <模式>，不要 grep -r / rg 整个目录。"""


def under(path, prefixes):
    return any(path == p or path.startswith(p + "/") for p in prefixes)


def is_nfs(path):
    path = path.rstrip("/") or "/"
    return under(path, PREFIXES) and not under(path, ALLOW)


def lex(cmd):
    try:
        lx = shlex.shlex(cmd, posix=True, punctuation_chars=True)
        lx.whitespace_split = True
        return list(lx)
    except ValueError:  # 引号不配对等：退化为按空白切分
        return cmd.split()


def segments(tokens):
    seg = []
    for t in tokens:
        if t in SEPARATORS:
            if seg:
                yield seg
            seg = []
        else:
            seg.append(t)
    if seg:
        yield seg


def word(token):
    return os.path.basename(token.strip("`$(){}\"'"))


def has_flag(args, flag):
    return any(x == flag or x.startswith(flag + "=") for x in args)


def depth_ok(args, flags):
    for j, t in enumerate(args):
        for f in flags:
            val = args[j + 1] if t == f and j + 1 < len(args) else (
                t[len(f) + 1:] if t.startswith(f + "=") else None)
            if val is not None and val.isdigit():
                return int(val) <= MAXDEPTH
    return False


def walker(seg):
    """返回这一段命令里的无界遍历动作名，没有则返回 None。"""
    for i, t in enumerate(seg):
        w, args = word(t), seg[i + 1:]
        if w in DEPTH_FLAGS:
            if w == "pwalk" and has_flag(args, "--deadline"):
                continue
            if not depth_ok(args, DEPTH_FLAGS[w]):
                return w
        elif w in ALWAYS_HEAVY:
            return w
        elif w == "ls" and any(LS_RECURSIVE.fullmatch(x) for x in args):
            return "ls -R"
        elif w in GREPS and any(GREP_RECURSIVE.fullmatch(x) for x in args):
            return w + " -r"
        elif m := SCRIPT_WALK.search(t):
            return f"脚本递归遍历({m.group(0)})"
    return None


def analyze(cmd, ctx_nfs, depth=0):
    """返回 (遍历动作, 目标路径) 或 None。ctx_nfs 表示当前工作目录是否在 NFS 上。"""
    for seg in segments(lex(cmd)):
        if any(word(t) == "nfs-run" for t in seg):
            continue  # 已经有时间上限和进程组清理
        if word(seg[0]) in ("cd", "pushd") and len(seg) > 1 and seg[1].startswith("/"):
            ctx_nfs = is_nfs(seg[1])
            continue
        w = walker(seg)
        if w:
            paths = [m for t in seg for m in PATH_RE.findall(t) if is_nfs(m)]
            relative = not any(t.startswith("/") for t in seg[1:])
            if paths or (ctx_nfs and relative):
                return w, paths[0] if paths else "当前工作目录"
        if depth < 3:  # bash -c '...'、python -c '...' 之类的内层命令
            for t in seg:
                if re.search(r"[\s;|&]", t):
                    hit = analyze(t, ctx_nfs, depth + 1)
                    if hit:
                        return hit
    return None


def main():
    try:
        data = json.load(sys.stdin)
    except ValueError:
        return 0
    tool, ti = data.get("tool_name"), data.get("tool_input") or {}
    cwd_nfs = is_nfs(data.get("cwd") or "")
    hit = None
    if tool == "Bash":
        hit = analyze(ti.get("command") or "", cwd_nfs)
    elif tool in ("Glob", "Grep"):  # 这两个工具底层都是递归遍历
        pattern, path = ti.get("pattern") or "", ti.get("path") or ""
        target = pattern if tool == "Glob" and pattern.startswith("/") else path
        on_nfs = is_nfs(target) if target.startswith("/") else cwd_nfs
        if on_nfs:
            hit = (f"{tool} 工具", target or "当前工作目录")
    if hit:
        if os.environ.get("NFS_GUARD_LOG"):
            try:
                with open(os.environ["NFS_GUARD_LOG"], "a") as f:
                    f.write(json.dumps({"ts": round(time.time(), 3), "tool": tool, "what": hit[0],
                                        "where": hit[1], "input": json.dumps(ti, ensure_ascii=False)[:300]},
                                       ensure_ascii=False) + "\n")
            except OSError:
                pass
        json.dump({"hookSpecificOutput": {
            "hookEventName": "PreToolUse",
            "permissionDecision": "deny",
            "permissionDecisionReason": REASON.format(what=hit[0], where=hit[1]),
        }}, sys.stdout, ensure_ascii=False)
    return 0


if __name__ == "__main__":
    sys.exit(main())
```

### 附录 D：build-nfs-index.sh（建索引）

安装位置：NFS 服务端（或 indexer 节点）的 `/opt/nfs-tools/build-nfs-index.sh`；cron 配置见 §5.2。

```bash
#!/usr/bin/env bash
# build-nfs-index.sh: 在 NFS 服务端（或一台专用 indexer 客户端）上生成文件索引。
#   用法: build-nfs-index.sh <数据根目录> [索引目录，默认 <根>/.index]
#   产物: <索引目录>/files.tsv，首行 "#nfs-index v1 ..." 为元信息，其余每行:
#         类型<TAB>大小<TAB>mtime(epoch)<TAB>相对路径    （按路径排序，rename 原子替换）
#   环境变量:
#     WALKER=find|pwalk  默认 find（服务端本地遍历很快）；在 NFS 客户端上建索引请用 pwalk 并行
#     THREADS=32         pwalk 并发数
#     MIN_RATIO=0.5      新索引条数低于旧索引的该比例时拒绝发布（防止挂载异常产出空索引）
#     FORCE=1            跳过上述检查
set -euo pipefail
ROOT=$(realpath "${1:?usage: $0 <root> [index_dir]}")
INDEX_DIR=${2:-$ROOT/.index}
mkdir -p "$INDEX_DIR"
INDEX_DIR=$(realpath "$INDEX_DIR")
OUT="$INDEX_DIR/files.tsv"
TMP=$(mktemp "$INDEX_DIR/.files.tsv.XXXXXX")
trap 'rm -f "$TMP" "$TMP.body" "$TMP.err"' EXIT
START=$(date +%s)

if [[ ${WALKER:-find} == pwalk ]]; then
  { pwalk -j "${THREADS:-32}" --format index --prune "$INDEX_DIR" \
      --exclude .snapshot --exclude .zfs "$ROOT" 2>"$TMP.err" || true; }
else
  # 剪掉索引目录自身、存储快照目录（NetApp .snapshot / ZFS .zfs）、名字含换行的条目
  { LC_ALL=C nice -n 10 find "$ROOT" -mindepth 1 \
      \( -path "$INDEX_DIR" -o -name .snapshot -o -name .zfs -o -name $'*\n*' \) -prune \
      -o -printf '%y\t%s\t%T@\t%P\n' 2>"$TMP.err" || true; }
fi | LC_ALL=C sort -t $'\t' -k4 > "$TMP.body"

COUNT=$(wc -l < "$TMP.body")
ERRS=$(grep -vc '^\[pwalk\]' "$TMP.err" || true)
PREV=0
if [[ -f $OUT ]]; then
  PREV=$(head -n 1 "$OUT" | tr '\t' '\n' | sed -n 's/^count=//p')
  PREV=${PREV:-0}
fi
if [[ ${FORCE:-0} != 1 ]] && (( PREV > 0 )) &&
   awk -v n="$COUNT" -v p="$PREV" -v r="${MIN_RATIO:-0.5}" 'BEGIN { exit !(n < p * r) }'; then
  echo "nfs-index: 拒绝发布: 新索引 $COUNT 条 < ${MIN_RATIO:-0.5} x 旧索引 $PREV 条（确认无误可 FORCE=1）" >&2
  head -n 5 "$TMP.err" >&2
  exit 1
fi

{
  printf '#nfs-index v1\tbuilt_at=%s\tduration=%s\tcount=%s\terrors=%s\troot=%s\n' \
    "$START" "$(( $(date +%s) - START ))" "$COUNT" "$ERRS" "$ROOT"
  cat "$TMP.body"
} > "$TMP"
chmod 0644 "$TMP"
mv -f "$TMP" "$OUT"  # 同目录 rename：读者要么读到旧索引，要么读到新索引，不会读到半截
echo "nfs-index: $COUNT entries, $ERRS errors, $(( $(date +%s) - START ))s -> $OUT"
```

### 附录 E：nfs-find（查索引）

安装位置：sandbox 镜像 `/opt/nfs-tools/nfs-find`，并链接到 PATH。

```python
#!/usr/bin/env python3
"""nfs-find: 在预建索引里查找 NFS 上的文件，不触发任何目录遍历（只依赖 Python 3.8+ 标准库）。

例: nfs-find --name '*.json' --under /mnt/nfs/data/2026 --newer 2h --limit 100
    nfs-find --path 'logs/*/error-*.txt' --count
    nfs-find --regex '/user_[0-9]+/profile\\.json$' --long
结果写 stdout（每行一个绝对路径，便于 | xargs）；统计与索引新鲜度写 stderr。
退出码: 0 有匹配; 1 无匹配; 2 用法错误或索引不存在
"""
import argparse
import fnmatch
import os
import re
import sys
import time


def parse_age(s):
    units = {"s": 1, "m": 60, "h": 3600, "d": 86400}
    return float(s[:-1]) * units[s[-1]] if s[-1] in units else float(s)


def human(sec):
    sec = int(sec)
    if sec >= 86400:
        return f"{sec // 86400}d{sec % 86400 // 3600}h"
    if sec >= 3600:
        return f"{sec // 3600}h{sec % 3600 // 60}m"
    if sec >= 60:
        return f"{sec // 60}m{sec % 60}s"
    return f"{sec}s"


def main():
    root = os.environ.get("NFS_ROOT", "/mnt/nfs").rstrip("/")
    ap = argparse.ArgumentParser(prog="nfs-find", description=__doc__.split("\n")[0],
                                 formatter_class=argparse.RawDescriptionHelpFormatter)
    ap.add_argument("--index", default=os.environ.get("NFS_INDEX", root + "/.index/files.tsv"))
    ap.add_argument("--name", help="文件名 glob，区分大小写，如 '*.json'")
    ap.add_argument("--iname", help="文件名 glob，不区分大小写")
    ap.add_argument("--path", help="相对 NFS_ROOT 的路径 glob（* 可跨目录），如 'logs/*/err-*.txt'")
    ap.add_argument("--regex", help="对相对路径做 re.search")
    ap.add_argument("--under", help="只看该目录下（绝对路径，或相对 NFS_ROOT）")
    ap.add_argument("--type", choices=["f", "d", "l"])
    ap.add_argument("--newer", metavar="AGE", help="mtime 在 AGE 之内，如 90s/30m/2h/7d")
    ap.add_argument("--min-size", type=int, metavar="BYTES")
    ap.add_argument("--max-size", type=int, metavar="BYTES")
    ap.add_argument("--limit", type=int, default=200, help="最多输出条数，默认 200")
    ap.add_argument("--count", action="store_true", help="只输出匹配条数")
    ap.add_argument("--long", action="store_true", help="输出 类型/大小/mtime/路径")
    a = ap.parse_args()

    prefix = ""
    if a.under:
        under = a.under.rstrip("/")
        if under == root:
            under = ""
        elif under.startswith(root + "/"):
            under = under[len(root) + 1:]
        elif under.startswith("/"):
            ap.error(f"--under 必须位于 NFS_ROOT={root} 之下")
        prefix = under + "/" if under else ""
    name_re = re.compile(fnmatch.translate(a.name)) if a.name else None
    iname_re = re.compile(fnmatch.translate(a.iname), re.IGNORECASE) if a.iname else None
    path_re = re.compile(fnmatch.translate(a.path)) if a.path else None
    rx = re.compile(a.regex) if a.regex else None
    min_mtime = time.time() - parse_age(a.newer) if a.newer else None

    sys.stdout.reconfigure(errors="surrogateescape")
    meta, matched, shown = {}, 0, 0
    try:
        f = open(a.index, encoding="utf-8", errors="surrogateescape", newline="\n")
    except OSError as e:
        print(f"[nfs-find] 无法打开索引 {a.index}: {e}", file=sys.stderr)
        return 2
    with f:
        for line in f:
            if line.startswith("#"):
                meta.update(kv.split("=", 1) for kv in line.rstrip("\n").split("\t")[1:] if "=" in kv)
                continue
            ftype, size, mtime, rel = line.rstrip("\n").split("\t", 3)
            if prefix and not rel.startswith(prefix):
                continue
            if a.type and ftype != a.type:
                continue
            base = rel.rsplit("/", 1)[-1]
            if (name_re and not name_re.match(base)) or (iname_re and not iname_re.match(base)):
                continue
            if (path_re and not path_re.match(rel)) or (rx and not rx.search(rel)):
                continue
            if min_mtime is not None and float(mtime) < min_mtime:
                continue
            if (a.min_size is not None and int(size) < a.min_size) or \
               (a.max_size is not None and int(size) > a.max_size):
                continue
            matched += 1
            if not a.count and shown < a.limit:
                shown += 1
                path = f"{root}/{rel}"
                if a.long:
                    ts = time.strftime("%Y-%m-%dT%H:%M:%S", time.localtime(float(mtime)))
                    print(f"{ftype}\t{size}\t{ts}\t{path}")
                else:
                    print(path)
    if a.count:
        print(matched)

    age = time.time() - float(meta.get("built_at", 0))
    msg = f"[nfs-find] matched={matched}"
    if not a.count:
        msg += f" shown={shown}"
        if matched > shown:
            msg += "（已截断：加 --limit N 或收紧条件；只要数量用 --count）"
    msg += f" index_age={human(age)}"
    print(msg, file=sys.stderr)
    max_age = float(os.environ.get("NFS_INDEX_MAX_AGE", "900"))
    if age > max_age:
        print(f"[nfs-find] 警告: 索引已 {human(age)} 未更新，最近的增删可能缺失；"
              "做关键判断前请对具体目录 ls -f 复核", file=sys.stderr)
    return 0 if matched else 1


if __name__ == "__main__":
    try:
        sys.exit(main())
    except BrokenPipeError:  # 例如 | head 提前关闭管道
        os.dup2(os.open(os.devnull, os.O_WRONLY), sys.stdout.fileno())
        sys.exit(0)
```

### 附录 F：nfs-index-mcp.py（可选的 MCP 封装）

安装位置：sandbox 镜像 `/opt/nfs-tools/nfs-index-mcp.py`；依赖 `pip install mcp`。

```python
#!/usr/bin/env python3
"""nfs-index MCP server（可选）：把 nfs-find 暴露成结构化工具，参数和上限都由工具定义约束。

依赖: pip install mcp（兼容 1.x 的 FastMCP 与 2.x 的 MCPServer）；nfs-find 需在 PATH 中。
注册: claude mcp add nfs-index -- python3 /opt/nfs-tools/nfs-index-mcp.py
"""
import subprocess

try:  # mcp 2.x
    from mcp.server.mcpserver import MCPServer as Server
except ImportError:  # mcp 1.x
    from mcp.server.fastmcp import FastMCP as Server

mcp = Server("nfs-index")


@mcp.tool()
def nfs_search(name: str = "", under: str = "", path_glob: str = "", regex: str = "",
               file_type: str = "", newer: str = "", limit: int = 200,
               count_only: bool = False) -> str:
    """在 NFS 文件索引中查找文件，不遍历文件系统，通常 1 秒内返回。
    name: 文件名 glob，如 *.json；under: 目录绝对路径；path_glob: 相对路径 glob；
    regex: 对相对路径的正则；file_type: f/d/l；newer: 如 30m、2h、7d；
    limit: 最多返回条数（上限 2000）；count_only: 只返回数量。
    结果末尾附匹配总数和索引年龄；索引有分钟级延迟，关键判断前对具体目录 ls -f 复核。"""
    args = ["nfs-find", "--limit", str(max(1, min(limit, 2000)))]
    for flag, value in (("--name", name), ("--under", under), ("--path", path_glob),
                        ("--regex", regex), ("--type", file_type), ("--newer", newer)):
        if value:
            args += [flag, value]
    if count_only:
        args.append("--count")
    r = subprocess.run(args, capture_output=True, text=True, timeout=30)
    return (r.stdout + r.stderr).strip()


if __name__ == "__main__":
    mcp.run()  # stdio transport
```

### 附录 G：test-nfs-guard.py（hook 回归测试）

用法：`python3 test-nfs-guard.py /opt/nfs-tools/nfs-guard.py`，全部通过时输出 `46/46 passed`。

```python
#!/usr/bin/env python3
"""nfs-guard.py 的表驱动测试：像 Claude Code 一样以子进程方式调用 hook，喂 JSON、读决策。

用法: python3 test-nfs-guard.py [/opt/nfs-tools/nfs-guard.py]
按默认配置（NFS_GUARD_PREFIXES=/mnt/nfs）测试；修改规则后先跑一遍，再补充对应用例。
"""
import json
import os
import subprocess
import sys

HOOK = sys.argv[1] if len(sys.argv) > 1 else "/opt/nfs-tools/nfs-guard.py"
ENV = {k: v for k, v in os.environ.items() if not k.startswith("NFS_GUARD_")}
P = "/home/user/proj"   # 不在 NFS 上的 cwd
N = "/mnt/nfs/data"     # 在 NFS 上的 cwd
D, A = "deny", "allow"

CASES = [
    # (期望, 工具, 输入, cwd)
    (D, "Bash", "find /mnt/nfs/data -name '*.json'", P),
    (D, "Bash", "find /mnt/nfs -maxdepth 10 -type f", P),
    (A, "Bash", "find /mnt/nfs/data -maxdepth 1 -name '*.json'", P),
    (A, "Bash", "find /mnt/nfs/data -maxdepth 3", P),
    (D, "Bash", "cd /mnt/nfs/data && find . -name x", P),
    (A, "Bash", "cd /mnt/nfs/.index && rg foo files.tsv", P),
    (D, "Bash", "find . -type f | wc -l", N),
    (A, "Bash", "find /tmp -name x", N),                    # cwd 在 NFS 上，但显式指向非 NFS 路径
    (A, "Bash", "find . -name x", P),
    (D, "Bash", "du -sh /mnt/nfs/data", P),
    (D, "Bash", "du -d 1 /mnt/nfs/data", P),                # du 仍然遍历整棵树
    (D, "Bash", "ls -laR /mnt/nfs/data", P),
    (A, "Bash", "ls -f /mnt/nfs/data/sub | head -100", P),
    (A, "Bash", "ls -lr /mnt/nfs/data", P),                 # -r 是倒序，不是递归
    (D, "Bash", "grep -rn ERROR /mnt/nfs/data/logs", P),
    (D, "Bash", "grep --recursive ERROR /mnt/nfs/data", P),
    (A, "Bash", "grep ERROR /mnt/nfs/data/logs/a.log", P),
    (D, "Bash", "rg -l TODO /mnt/nfs/data", P),
    (A, "Bash", "rg 'proj0' /mnt/nfs/.index/files.tsv", P),
    (A, "Bash", "rg --max-depth 1 foo /mnt/nfs/data", P),
    (D, "Bash", "fd -e json . /mnt/nfs/data", P),
    (D, "Bash", "tree /mnt/nfs/data", P),
    (A, "Bash", "tree -L 2 /mnt/nfs/data", P),
    (D, "Bash", "bash -c \"find /mnt/nfs/data -name x\"", P),
    (D, "Bash", "echo $(find /mnt/nfs/data | wc -l)", P),
    (D, "Bash", "timeout 60 find /mnt/nfs/data", P),
    (D, "Bash", "python3 -c \"import os; print(sum(1 for _ in os.walk('/mnt/nfs/data')))\"", P),
    (D, "Bash", "python3 -c \"import pathlib; print(len(list(pathlib.Path('/mnt/nfs/data').rglob('*'))))\"", P),
    (A, "Bash", "nfs-run --timeout 90 -- 'find /mnt/nfs/data -name x | wc -l'", P),
    (A, "Bash", "nfs-run --timeout 90 -- pwalk -j 16 /mnt/nfs/data", P),
    (D, "Bash", "nfs-run -- true; find /mnt/nfs/data", P),  # nfs-run 只覆盖它自己那一段
    (A, "Bash", "pwalk --deadline 60 /mnt/nfs/data | head", P),
    (D, "Bash", "pwalk /mnt/nfs/data", P),
    (A, "Bash", "nfs-find --name '*.log' --under /mnt/nfs/data | xargs -d '\\n' grep -l ERROR", P),
    (A, "Bash", "cat /mnt/nfs/data/a.json | jq .", P),
    (A, "Bash", "find /mnt/nfs2/data -name x", P),          # 另一个挂载点：前缀要按 / 边界匹配
    (D, "Bash", "find /mnt/nfs/data -name 'it'\"'\"'s", P),   # 复杂引号仍能解析
    (D, "Bash", "find /mnt/nfs/data -name \"unterminated", P),  # 引号不配对时退化为按空白切分
    (D, "Glob", {"pattern": "**/*.json", "path": "/mnt/nfs/data"}, P),
    (D, "Glob", {"pattern": "/mnt/nfs/data/**/*.json"}, P),
    (D, "Glob", {"pattern": "**/*.json"}, N),
    (A, "Glob", {"pattern": "**/*.py"}, P),
    (D, "Grep", {"pattern": "ERROR", "path": "/mnt/nfs/data/logs"}, P),
    (A, "Grep", {"pattern": "proj0", "path": "/mnt/nfs/.index/files.tsv"}, P),
    (A, "Read", {"file_path": "/mnt/nfs/data/a.json"}, P),
]


def decide(tool, tool_input, cwd):
    if isinstance(tool_input, str):
        tool_input = {"command": tool_input, "description": "test"}
    payload = {"session_id": "t", "cwd": cwd, "hook_event_name": "PreToolUse",
               "tool_name": tool, "tool_input": tool_input, "tool_use_id": "toolu_test"}
    r = subprocess.run([sys.executable, HOOK], input=json.dumps(payload), capture_output=True,
                       text=True, timeout=10, env=ENV)
    assert r.returncode == 0, r.stderr
    if not r.stdout.strip():
        return A
    out = json.loads(r.stdout)["hookSpecificOutput"]
    assert out["hookEventName"] == "PreToolUse" and out["permissionDecisionReason"]
    return out["permissionDecision"]


fails = 0
for expected, tool, tool_input, cwd in CASES:
    got = decide(tool, tool_input, cwd)
    if got != expected:
        fails += 1
        print(f"FAIL 期望 {expected} 实际 {got}: {tool} {tool_input} (cwd={cwd})")
r = subprocess.run([sys.executable, HOOK], input="not json", capture_output=True, text=True, env=ENV)
if r.returncode != 0 or r.stdout:
    fails += 1
    print("FAIL 非法输入应当放行（fail-open）")
print(f"{len(CASES) + 1 - fails}/{len(CASES) + 1} passed")
sys.exit(1 if fails else 0)
```
