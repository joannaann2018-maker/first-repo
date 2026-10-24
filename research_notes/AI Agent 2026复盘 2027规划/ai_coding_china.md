# 中国 AI Coding 市场 2026 回顾（2026年1–10月，中国视角）

> 研究说明：时间截至 2026-10-23。研究中途本轮 WebSearch 配额（多 agent 共享）已耗尽，之后只对已检索到的 URL 做了抓取。因此百度文心快码/秒哒、蚂蚁 CodeFuse、aiXcoder、运营商/央国企案例、AI 编程专项招投标这几个方向覆盖不足，详见各节 Gaps。凡是只有单一二手来源、或原文乱码的条目，都已标"未核实"。货币换算统一按约 7.1 RMB/USD 粗估，仅作推算用。

---

## 一、主要产品与 2026 年进展（发布时间、用户、收入、定价）

### Takeaway
2026 年中国 AI Coding 的主线是三件事。一是模型层快速追赶：智谱 GLM-5→5.3、Kimi K2.5→K3、DeepSeek V4、Qwen3.5→3.8、MiniMax M2.5→M3。二是工具层从 IDE 插件走向 CLI、Agent，再到"智能体工作台/Cowork"：Qoder 1.0（5月）、新 Qoder（8月）、TRAE 合并（10月）、CodeBuddy 2.0 加 WorkBuddy。三是商业化从低价获客转向在算力约束下提价。按 IDC 口径，工具市场 2025 年只有 3.99 亿元，阿里占 47.6%；但模型厂商的 API/Coding Plan 收入规模已远超这个数（智谱 2026H1 API 收入 8.25 亿元，8月 ARR 16 亿美元）。

### Cited Findings

#### 市场总盘子与格局
- IDC《中国AI编程市场份额，2025》于 2026-07-16 发布。2025 年中国 AI 编程市场规模为 3.99 亿元人民币，预计 2026 年底增至 11.73 亿元（约 2.9 倍）。阿里份额 47.6% 居第一，超过第 2–5 名之和 — [每日经济新闻/新浪财经](https://finance.sina.com.cn/stock/t/2026-07-16/doc-inihyiym7977683.shtml)；[IDC 报告页](https://my.idc.com/getdoc.jsp?containerId=CHC54607526)
- 量子位（2026-07-17）称 47.6% 是"营收份额"，对应产品为 Qoder。第 2–5 名的厂商名称和份额在公开报道中都没有披露 — [量子位](https://www.qbitai.com/2026/07/452914.html)
- 有转载报道称，该报告从"企业营收与 Token"两个维度衡量市场，覆盖腾讯、百度、阿里、智谱、商汤等厂商（未见报告原文）— [网易转载](https://www.163.com/dy/article/L1V2A4EI0512B07B.html)
- Gartner 2026《企业级 AI 代码智能体魔力象限》（2026-06）共收录 12 家厂商。阿里云连续三年位于"挑战者"象限，是唯一入选的中国厂商 — [量子位](https://www.qbitai.com/2026/07/452914.html)

#### 字节：TRAE / 火山方舟 Coding Plan / Doubao-Seed-Code
- 【2025 背景】2025-06，字节技术副总裁洪定坤称 TRAE 整体月活超过 100 万 — [财联社](https://www.cls.cn/detail/2055491)
- 【2025 背景】TRAE 于 2025-12-26 发布首份年度报告，主要数据如下 — [极客公园/腾讯新闻](https://news.qq.com/rain/a/20251229A065ZX00)
  - 规模：全球累计用户超 600 万，覆盖近 200 个国家/地区，月活 160 万；累计生成近 1000 亿行代码、处理 5 亿次开发问答；Token 消耗半年增长约 700%；全年更新 200 多次。
  - 版本节奏：7月发布 1.0，同月发布 2.0 SOLO Beta，11月发布 3.0 SOLO 正式版。
  - SOLO 采用：国际版累计渗透率 44%，国内版约 3/10 的开发者使用 SOLO。
  - 字节内部：92% 的工程师使用 TRAE；抖音生活服务的 DevOps 流水线中，AI 贡献了 43% 的代码。
- 【2025 背景】2025-11 TRAE SOLO 中国版上线，全部功能免费，包括 SOLO Coder、Plan 模式、多任务并行、DiffView 和上下文压缩 — [新浪财经](https://finance.sina.com.cn/stock/t/2025-11-26/doc-infytcth1101217.shtml)
- 2026-02-01 起，国际版收费结构调整，以下信息来自火山引擎官网的一篇营销性文章，内容引自第三方 — [火山引擎文章](https://www.volcengine.com/article/2844592)
  - 五档价格：Free / Lite $3 / Pro $10 / Pro+ $30 / Ultra $100，分别赠送 $3 / $5 / $20 / $90 / $400 额度。
  - SOLO 并发：Lite 2、Pro 10、Pro+ 15、Ultra 20。
  - 新用户试用改为 14 天 Pro，需绑定信用卡。
  - 国内版：个人免费；企业版 49 / 99 / 199 元/席/月。这组企业版价格与知乎文章所列"团队版 ¥149/席/月、旗舰版 ¥259/席/月"不一致 — [知乎](https://zhuanlan.zhihu.com/p/2004590797450921359)
- 据称国内版自 2026-07-31 起由"速通次数制"改为积分制，常见套餐 99 元/月（优惠后 49–59 元）。这只有单一知乎来源，原文抓取被拒，未核实 — [知乎](https://zhuanlan.zhihu.com/p/2066687263707238910)。IT之家 10 月报道提到合并时"商业积分"会迁移，间接说明国内版确有积分体系 — [IT之家](https://www.ithome.com/1/011/176.htm)
- 2026-06，TRAE IDE（国内版）与扣子合计月访问量约 1441 万，在办公智能体榜单列第二。业内人士认为 TRAE Work 表现一般，并称字节可能转向豆包与飞书的深度整合 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
- 2026-10-09，TraeWork 与 TraeCode 合并为全新 TRAE，定位"全链路开发平台"。新版可在 Agent 模式与 IDE 模式间切换，覆盖桌面、Web 和移动端，目前灰度推送中 — [IT之家](https://www.ithome.com/1/011/176.htm)。官方更新日志显示 v3.4.4 于 2026-10-15 发布 — [TRAE changelog](https://www.trae.cn/changelog)
- 【2025 背景】火山方舟 Coding Plan 于 2025-11 前后上线，初期集成 Doubao-Seed-Code、GLM-4.7、DeepSeek-V3.2、Kimi-K2-Thinking — [苏米客](https://www.xmsumi.com/detail/2297)；[InfoQ](https://www.infoq.cn/article/rpscltoqxo75kmjerzfb)
- 2026-02 的价格为 Lite ¥40/月、Pro ¥200/月，首月促销 ¥8.91，含 Auto 模型路由 — [GitHub Gist 对比（2026-02-22）](https://gist.github.com/junbaor/171023a696acb06968056a4e62e98255)
- 火山引擎官网 2026-04-09 的文章介绍了 Coding Plan 的额度与模型，但没有披露用户数 — [火山引擎](https://www.volcengine.com/article/37522)
  - 额度：Lite 每月最多 18,000 次请求，token 成本约为同等 API 的 10%；Pro 为 Lite 的 5 倍。
  - 模型：Doubao-Seed-2.0-Code、Doubao-Seed-Code、Doubao-Seed-2.0-pro/lite；页面侧栏称支持 DeepSeek-V4 系列和 GLM-5.3 系列。
  - 工具：支持 Claude Code、Cursor、Cline、OpenCode 等十余款工具。
- 社区对比称火山方舟 Lite 每日 0 点限量放售，经常售罄（页面未注明日期）— [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)

#### 阿里：Qoder（含原通义灵码）/ Qwen Code / Qwen3.x / 百炼 Coding Plan 与 Token Plan
- 2026-02-02 发布 Qwen3-Coder-Next，这是面向 coding agent 和本地开发的开放权重模型 — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)；[财联社](https://www.cls.cn/detail/2285957)
- 2026-02-16 发布开放权重的 Qwen3.5，同时发布闭源的 Qwen3.5-Plus。2026-03，千问模型负责人林俊旸离职；同月阿里成立 Alibaba Token Hub — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- 2026-04 发布闭源的 Qwen3.6-Plus，上线 OpenRouter 3 天内日 Token 达 1.4 万亿 — [投中网](https://m.chinaventure.com.cn/news/78-20260629-392056.html)。同月 Qwen3.6 以 Apache 2.0 开源 — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- 2026-05 发布闭源的 Qwen3.7-Max。量子位引用的分数为 SWE-Pro 60.6、SWE-Multilingual 78.3、Terminal Bench 2.0（Terminus）69.7 — [量子位](https://www.qbitai.com/2026/07/452914.html)
- Qwen3.8 系列于 2026-08 密集发布 — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
  - 08-03：Qwen3.8-Max 云端版上线。
  - 08-12：公开 2.4T 参数权重，许可要求年收入超 5000 万美元的服务商另签商业条款。
  - 08-14：Qwen3.8-27B 发布（Apache 2.0）。
  - 08-26：Qwen3.8-Flash 发布。
- 2026-05-15 发布 Qoder 1.0，定位从 AI IDE 升级为"智能体自主开发工作台"。主要功能包括 Quest 独立窗口、跨 Workspace/代码库并行、任务状态与 Summary 交付清单、自定义专家智能体，支持 Win/macOS/Linux — [IT之家/新浪科技](https://finance.sina.com.cn/tech/digi/2026-05-15/doc-inhxyccp3381248.shtml)
- 据称 2026-05 起原"通义灵码"更名为"Qoder CN"。来源为 CSDN/知乎二手文章，未见阿里官方确认 — [CSDN](https://blog.csdn.net/Qzyecho/article/details/151323891)
- 2026-08-27 阿里发布全新 Qoder，从 AI 编程工具升级为智能体工作台，支持 Goal/Plan、长链路任务、Browser Use、Computer Use、长期记忆、分级权限和多模型协同 — [IT之家](https://www.ithome.com/0/994/977.htm)；[OpenAI Hub](https://www.openai-hub.net/news/1559/)
- Qoder 用户规模说法不一，均未核实：量子位称"约 500 万"（原文带问号）— [量子位](https://www.qbitai.com/2026/07/452914.html)；第三方博客称"600 万用户"，并称内置 Qwen3.8-Max 与 Auto 调度（单一来源）— [huanghaiwan.com](https://huanghaiwan.com/ai/qoder-agent-workbench-guide-2026/)
- 量子位报道了 Qoder 的实测数据和企业功能 — [量子位](https://www.qbitai.com/2026/07/452914.html)
  - 知识引擎实测：代码留存率 +11%，输入 Token −40%，对话轮次 −33%。
  - 企业版：可按人、组、仓库配置模型权限；提供企业 Plugin/Skill 市场；有 L1–L4 四级代码防护。
- 百炼同时提供两种订阅：Coding Plan 为固定月费，Token Plan 按 Credits 计费，分个人版和团队坐席版。Coding Plan 推荐模型包括 qwen3.7-plus、qwen3.6-plus、kimi-k2.5，即阿里平台也分销友商模型 — [阿里云帮助中心](https://help.aliyun.com/zh/model-studio/coding-plan)；[阿里云开发者社区](https://developer.aliyun.com/article/1749301)
- 百炼价格变化如下：
  - 2026-02：Coding Plan Lite ¥40 / Pro ¥200，首月 ¥7.9，次月半价续费 — [Gist](https://gist.github.com/junbaor/171023a696acb06968056a4e62e98255)
  - 之后：Lite 档（qwen-3.5-plus）已下线 — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)
  - 2026-09：Token Plan 为 Lite ¥39（11,500 Credits）/ Standard ¥139（45,000）/ Pro ¥499（180,000），模型含 Qwen3.8-Max、Qwen3.8-Flash、Kimi-K3、DeepSeek-v4-pro — [codingplan.org（2026-09-24 更新）](https://codingplan.org/en)
- 2026-06 QoderWork 月访问量 788 万，在办公智能体榜列第三。据《财经》2026-07 报道，阿里拟把 QoderWork、悟空、MuleRun 合并为"千问办公" — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
- 2026-09，Accio Work 团队自测 107 项任务的成本约 $3.69，对比 Codex 的 $9.27 和 Claude Code 的 $9.51（厂商自测）— [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)

#### 腾讯：CodeBuddy（插件/IDE/CLI）/ WorkBuddy / 混元 Hy3
- 【背景】2025-10-24 发布的《2025腾讯研发大数据报告》显示：50% 的新增代码由 AI 辅助生成；超过 90% 的工程师使用 CodeBuddy；月均新增代码 3.25 亿行 — [腾讯云开发者](https://cloud.tencent.com/developer/news/3143570)
- 2026-01-22 发布 CodeBuddy Code 2.0，新增 Plan 模式、自定义模型和插件市场，并上线国内企业版 — [CSDN](https://blog.csdn.net/qq_17859117/article/details/163939302)
- 财联社 2026-02-10 补充了 2.0 的细节 — [财联社](https://www.cls.cn/detail/2285957)
  - 2.0 版本 99.9% 的代码由 CodeBuddy 自身生成；腾讯内部超过 1.2 万名工程师使用 CodeBuddy Code。
  - 支持 GLM-4.7、GPT-5.2 Codex 等自定义模型，并率先引入 Skills。
  - CodeBuddy 是首个同时提供插件、IDE、CLI 三种形态的 AI 编程工具。
- 2026-03 WorkBuddy 发布。2026-03-09，CodeBuddy 团队致歉：WorkBuddy 公测流量远超预期，导致 CodeBuddy 登录和服务不稳定 — [百度百科](https://baike.baidu.com/en/item/CodeBuddy/1432154)
- 2026-04-08 起，CodeBuddy 全系产品（含 CLI）内置 GLM-5.1。这条来自搜索摘要，百科正文未能抓取 — [百度百科](https://baike.baidu.com/item/CodeBuddy%20Code/66744822)。另有单一来源称 8-13 起升级到 DeepSeek-V4-Pro 正式版，未核实。
- 腾讯云 2026-04-28 发布调价公告，2026-05-15 生效 — [财联社](https://www.cls.cn/detail/2357934)
  - 企业旗舰版更名"SaaS 企业版"，价格由 78 元/人/月调至 198 元/人/月。
  - 企业专享版更名"专有云企业版"，价格由 158 元/人/月调至 316 元/人/月。
- 个人专业版 ¥59/月，含 2,000 Credits，按量扣减，首月加赠 — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)
- 2026-06 WorkBuddy 月访问量 2097 万（四个月前约 800 万），在易观 2026Q2 的 17 家桌面办公智能体中排第一。2026-07-06 混元 Hy3 发布并首发于 WorkBuddy，自选模型的用户中超过 60% 选择 Hy3 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
- 2026-06 的 OpenRouter 数据中，腾讯周 Token 2.36T、份额 8.1%；Hy3 Preview 日 Token 451B，在模型中排第二。这组数据来自供应商博客的整理 — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)

#### 百度：文心快码 Comate / 秒哒
- 【2025 背景】2025-06-23 文心快码发布 Comate AI IDE，百度每日新增代码中由文心快码生成的占比超过 43% — [量子位](https://www.qbitai.com/2025/06/300135.html)
- 2025 年金融大模型中标中，百度以 38 个项目、6021 万元居首。这是大模型整体中标，并非编程专项 — [经济观察网](http://www.eeo.com.cn/2026/0115/779399.shtml)
- 2026 年文心快码和秒哒的用户数、收入、定价均未检索到，官网页面只抓到标题（见 Gaps）— [文心快码官网](https://comate.baidu.com/zh)

#### 智谱：GLM-5 系列 / GLM Coding Plan / ZCode
- 2026 年关键时间线如下 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Zhipu_AI)
  - 01-08：港交所上市（02513）。
  - 02-12：发布 GLM-5。
  - 2 月下旬：因算力短缺和用户投诉，股价跌约 23%，并限制新用户注册。
  - 3 月下旬：GLM-5.1 先向订阅用户开放。
  - 04-07：GLM-5.1 开源，API 同时涨价 10%。
  - 06-16：发布 GLM-5.2（1M 上下文）。
  - 07-02：推出桌面 AI 编程应用 ZCode，支持 OpenAI、Anthropic、Moonshot、OpenRouter 的模型。
  - 08-14：发布 GLM-5.3（与 5.2 同一 743B 基座，强化后训练）。
  - 2026-08：市值约 620 亿美元。
- 2026-02-06，匿名模型"Pony Alpha"登陆 OpenRouter，接近智谱的人士称即 GLM-5。同期智谱因算力暂时紧张，宣布 GLM Coding Plan 限量销售 — [财联社](https://www.cls.cn/detail/2285957)
- 2025 全年收入 7.24 亿元，同比 +132% — [量子位](https://www.qbitai.com/2026/03/394135.html)
- 2026H1（中报，2026-08-31）财务数据如下 — [Winter Research 纪要](https://winterresearch.com/zhipu_interim_2026_0901)；[新浪财经](https://finance.sina.cn/hkstock/gsxw/2026-08-31/detail-iniqfkkr8831601.d.html?vt=4)
  - 收入 9.54 亿元，同比 +399.7%。
  - 开放平台及 API 收入 8.25 亿元（+2736%），占比 86.5%（上年同期 15.2%）；本地化部署 1.62 亿元（−20.5%）。
  - 整体毛利率 26.4%（上年同期 50%）；API 毛利率 24.6%（上年同期 −0.4%）。
  - 净亏损 20.72 亿元；研发 21.31 亿元。
- MaaS ARR 由 7 月的 10 亿美元增至 8 月的 16 亿美元（月收入×12）；若按最近一周×52 计算，超过 20 亿美元。年底目标为 24 亿美元。董秘肖磊承认 ARR 呈"脉冲式"增长 — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)；[财联社](https://m.cls.cn/detail/2470120)
- 截至 2026-08，智谱的平台与编程数据如下 — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)；[腾讯新闻](https://news.qq.com/rain/a/20260904A042IS00)
  - 调用量：Coding Plan 较年初增长超 23 倍；MaaS Token 调用量增长超 40 倍。
  - 用户：注册用户超 740 万（+144%）；付费日活 +603%，覆盖 233 个国家/地区。
  - 价格与成本：API 平均售价 +101%；单位推理成本 −80%（10 万卡国产芯片集群）。
  - 管理层表态：编程已是最主要的收入来源，公司正从 Coding 走向 Cowork。
- GLM-5.3-Flash（320B 总参/18B 激活，MIT 开源）以"Ox-Alpha"匿名测试时登顶 OpenRouter，6 天处理超过 62 万亿 Token，带动平台总调用量增长 20% 以上。其定价约为 GLM-5.2 的 1/10 — [腾讯新闻](https://news.qq.com/rain/a/20260904A042IS00)；[Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
- GLM Coding Plan 国内版于 2026-07-30 改版为积分制 — [腾讯云开发者社区](https://cloud.tencent.com/developer/article/2718987)；[IT之家](https://www.ithome.com/0/983/934.htm)；[知乎指南](https://zhuanlan.zhihu.com/p/2015468530938693485)；[新浪财经](https://finance.sina.com.cn/stock/t/2026-07-31/doc-iniksxpi1210399.shtml)
  - 月费：Lite / Pro / Max 由 ¥49 / ¥149 / ¥469 调至标价 ¥118 / ¥538 / ¥1078。腾讯云社区文章列的 ¥94.4 / ¥430.4 / ¥862.4 恰好是标价 8 折。
  - 涨幅：按年付口径，Pro +152%、Max +61%、Lite +68%。
  - 高峰计费：工作日 14:00–18:00，GLM-5.2 和 GLM-5-Turbo 按 3 倍扣积分；GLM-4.7 全天 1 倍。
  - 老用户：V1/V2 及团队版权益不受影响。
- 国际版（Z.ai）2026-09 的价格为 Lite $18 / Pro $80 / Max $168（年付 7 折），模型为 GLM-5.3 和 GLM-5.3-Flash — [codingplan.org](https://codingplan.org/en)

#### 月之暗面：Kimi K2.5 → K3 / Kimi Code
- 2026-01 发布 Kimi K2.5，新增多模态和 Agent Swarm（最多 100 个子智能体），同时推出命令行编程智能体 Kimi Code — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
- 截至 2026-02-09，K2.5 已连续约两周在 OpenRouter 多个榜单居首，包括周榜总榜、编程、工具调用、Python、OpenClaw 调用 — [财联社](https://www.cls.cn/detail/2285957)
- 收入：ARR 2026-03 超 1 亿美元，05 达 2 亿美元，6 月中达 3 亿美元；API 占收入 70% 以上。野村预计年底 ARR 超过 10 亿美元 — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
- 2026-07-16/17 发布 Kimi K3 — [财联社](https://www.cls.cn/detail/2429127)；[新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
  - 规格：2.8T 参数，为最大的开源模型；1M 上下文；原生多模态；采用 KDA 混合线性注意力。
  - 编程排名：Arena AI 编程盲测 1679 分第一，高于 Claude Fable 5（1631）和 GPT-5.6 Sol（1618）。但官方承认整体仍略逊于这两款美国闭源模型。
  - API：$3/$15 每百万 tokens；权重在 07-27 前开源。
- K3 输出价约 100 元/百万 tokens，远高于 DeepSeek V4-Pro 和小米 MiMo V2（6 元）、GLM-5.2（28 元）、Qwen3.7-Max（36 元）— [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
- 2026-07-19，月之暗面因 K3 发布后请求量远超预期、集群逼近上限，暂停 C 端新用户订阅。今后订阅将拆分为 Kimi 主权益（Web/APP/Work）和 Kimi Code 权益两部分 — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
- Kimi 会员与 Kimi Code 定价变化如下：
  - 2026-09：Go ¥49（不含 Kimi Code）/ Plus ¥99 / Pro ¥199 / Max ¥699，模型含 K3、K3-256K、K2.7 Code HighSpeed — [codingplan.org](https://codingplan.org/en)
  - 2026-02：Kimi Code 档位为 Andante ¥49 / Moderato ¥99（K2.5）— [Gist](https://gist.github.com/junbaor/171023a696acb06968056a4e62e98255)
  - 社区反馈：Allegretto ¥199 档算力紧张、TPS 下降、频繁 429 — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)
- 中关村在线文章称 Kimi Code CLI 以 MIT 协议开源，桌面版于 2026-09-17 上线。该文原文乱码，未核实 — [中关村在线](https://news.zol.com.cn/1251/12519211.html)
- 融资与上市：2026-05 融资 20 亿美元、估值 200 亿美元；06-30 新一轮投前估值 315 亿美元；计划最快 6 个月内港股 IPO — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)。2026-07-30 以 350 亿美元估值完成融资 — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)

#### MiniMax：M2.5 → M3 / Coding Plan → Token Plan
- 2026-01 港股上市。市值 3 月峰值约 4300 亿港元，8 月中报后约 1098 亿港元，5 个月蒸发约 76% — [虎嗅](https://www.huxiu.com/article/4886381.html)
- 2026-02 的 M2.5 数据如下 — [Dataconomy](https://dataconomy.com/2026/02/25/chinese-ai-models-hit-61-market-share-on-openrouter/)
  - 用量：OpenRouter 单周 2.45T tokens 居首，受 Kilo Code、Cline 免费推广带动。
  - 性能与价格：SWE-Bench Verified 80.2%，价格 $0.30/$1.10。
- 据虎嗅，2026-03 MiniMax 把 Coding Plan 改为按 Token 计费的 Token Plan，因沟通不足引发用户反弹，随后永久降价 50%，并发放 Token 补偿，侵蚀了毛利 — [虎嗅](https://www.huxiu.com/article/4886381.html)
- 官方按量计费文档：M3（≤512k 输入）标准价 ¥4.2/¥16.8 每百万 tokens，永久五折后为 ¥2.1/¥8.4 — [MiniMax 开放平台](https://platform.minimaxi.com/docs/guides/pricing-paygo)
- M3（428B 总参）于上半年发布。按"GLM-5.2 晚于 M3 12 天"推算，约在 6 月初。虎嗅评价其编程表现"不尽如人意" — [虎嗅](https://www.huxiu.com/article/4886381.html)；[MiniMax 中报新闻稿](https://www.prnasia.com/story/545325-1.shtml)
- Token Plan 价格：
  - 国内（2026-06）：Plus ¥49 / Max ¥119 / Ultra ¥469 — [GitCode](https://gitcode.csdn.net/6a20c8b4662f9a54cb79515a.html)
  - 国际：Plus $20 / Max $50 / Ultra $120，对应约 1.7B / 5.1B / 12.5B tokens/月，含 M3 和 M2.7 — [codingplan.org](https://codingplan.org/en)
- 2026H1 中报（2026-08-26）— [美通社](https://www.prnasia.com/story/545325-1.shtml)；[虎嗅](https://www.huxiu.com/article/4886381.html)
  - 收入 1.166 亿美元，同比 +283%。其中开放平台及企业服务 7390 万美元（+703%，占 63.4%）；AI 原生产品 4260 万美元（+101%）。
  - 毛利率 17.9%；净亏损 3.58 亿美元；经调整净亏损 2.93 亿美元（+111%）。
  - 7 月 Token 消耗为 1 月的 20 倍；"MiniMax Code"产品与 Token Plan"迅速获采用"。
  - 海外收入 7083 万美元，占 60.8%（虎嗅）。
- 8 月 ARR 超过 8 亿美元，To B 约占 80%，按周收入×52 计算；全年 10 亿美元的目标未上调 — [新浪科技](https://finance.sina.com.cn/tech/roll/2026-08-28/doc-inipwnxp9010342.shtml)；[虎嗅](https://www.huxiu.com/article/4886381.html)

#### DeepSeek：V4
- 2026-04-24 发布 V4 预览版并开源 — [澎湃新闻](https://www.thepaper.cn/newsDetail_forward_33042587)；[阿里云开发者社区](https://developer.aliyun.com/article/1730877)
  - 规格：V4-Pro 1.6T 总参/49B 激活；V4-Flash 284B/13B；均为 1M 上下文。
  - 编程能力（官方说法）：V4-Pro 的 Agentic Coding 达到开源最佳，已成为公司内部员工的主力 Agentic Coding 模型；体验优于 Sonnet 4.5，接近 Opus 4.6 非思考模式。
  - 生态适配：针对 Claude Code、OpenClaw、OpenCode、CodeBuddy 做了适配；API 同时支持 OpenAI 和 Anthropic 接口。
- 2026-06-29 有报道称 DeepSeek 将实行峰谷定价，高峰时段（9–12 点、14–18 点）为 2 倍价格 — [阿里云开发者社区](https://developer.aliyun.com/article/1744772)
- 正式版上线，以下分数为第三方转述的官方数据 — [卡码笔记](https://notes.kamacoder.com/llm/news/deepseek-v4-flash-official.html)；[DeepSeek 技术社区](https://deepseek.csdn.net/6a7d68a7662f9a54cb9c48b5.html)；[TechOrange](https://techorange.com/2026/08/14/deepseek-harness-launches-open-source-ai-rival-claude-code/)
  - 2026-07-31：V4-Flash 正式版 API 公测，Terminal Bench 2.1 得分 82.7。
  - 约 2026-08-13：V4-Pro 正式版上线，Terminal Bench 2.1 得分 87.9，原生支持 Responses API 和 Codex。
- V4-Pro 输出价约 6 元/百万 tokens — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
- 2026-06 的 OpenRouter 数据中，DeepSeek 周 Token 5.13T、份额 17.6%，居厂商第一；V4 Flash 日 Token 619B，居模型第一。数据来自供应商博客整理 — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)

#### 华为：码道 CodeArts
- 2026-01-16 华为云发布 CodeArts 代码智能体个人版，包含 AI IDE、Code Agent 和 Codebase — [aiproducthub](https://aiproducthub.cn/sites/huaweicloud-codearts.html)
- 2026-02-26 "码道（CodeArts）"代码智能体开启公测 — [科创板日报/新浪科技](https://finance.sina.com.cn/tech/discovery/2026-02-27/doc-inhpefha7144059.shtml)
  - 基础与模型：基于华为"千亿级"代码库；接入 GLM-5.0、DeepSeek-V3.2 和华为自研模型，并提供鸿蒙 ArkTS 专属模型。
  - 形态：覆盖 IDE、VS Code、JetBrains、CLI。
  - 效率：官方称 Codebase 索引在同等任务下可节省 30% Token。
  - 定价：公测免费，企业版尚未推出。
- 第三方评测称码道 8 月底在亚太上线，Agent Team 内置 16 个 Agent，Basic 版 $20/席/月（未核实）— [AI之家](https://aiho.net/coding/agent/codearts-agent.html)

#### 快手 / 美团 / 小米 / 其他
- 快手的 AI 编程矩阵包括 CodeFlicker（由内部 Kwaipilot 升级而来）、KAT-Coder 模型和万擎平台。2026-02 CodeFlicker 接入 MiniMax M2.5 和 GLM-5 — [百度百科](https://baike.baidu.com/item/CodeFlicker/67380370)
- KAT-Coder-V2 技术报告（2026-03）显示 SWE-bench Verified 79.6%，Opus 4.6 为 80.8% — [arXiv 2603.27703](https://arxiv.org/abs/2603.27703)
- 2026-07-26 发布 KAT-Coder-V2.5，用 10 万多个可验证仓库环境训练；PinchBench 94.9，SWE-Bench Pro 第二。这条经搜索摘要转述，原文抓取被拒 — [MarkTechPost](https://www.marktechpost.com/2026/07/26/kwaikat-team-releases-kat-coder-v2-5-an-agentic-coding-model-trained-on-100000-verifiable-repository-environments/)
- 美团于 2026-07-28 正式发布全场景 AI Agent 平台 CatPaw — [美团技术团队](https://tech.meituan.com/2026/07/28/CatPaw-LongCat.html)
  - 模型：搭载 LongCat 2.0（1.6T 总参、约 48B 激活、1M 上下文），官方称是首个在 5 万张国产卡上端到端训练和推理的万亿参数模型。
  - 内部使用：覆盖 9 万名员工，员工已搭建 3 万个 Agent。
  - 企业版：提供支持私有化部署的 CatPaw Managed Agents。
- CatPaw 早在 2025-11 就以 IDE 形式开放内测 — [CSDN](https://blog.csdn.net/Ashtar_katay/article/details/154615561)
- 小米：2026-06 OpenRouter 周 Token 2.42T、份额 8.3%；MiMo-V2.5 日 Token 327B — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)。MiMo Token Plan Pro 为 ¥329/月 — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)
- 摩尔线程于 2026-02 初推出 AI Coding Plan，兼容 Claude Code、Cursor、OpenCode，算是国产芯片厂商直接卖编程算力的例子 — [财联社](https://www.cls.cn/detail/2285957)

### Inferences
- **价值主要沉淀在模型/API 层，而非工具层。** IDC 口径下，2025 年全年工具市场只有 3.99 亿元，阿里约 1.9 亿元（3.99×47.6%）。相比之下，智谱仅 2026 上半年 API 收入就达 8.25 亿元，且编程是最大来源。8 月 ARR 16 亿美元意味着 8 月单月收入约 1.33 亿美元，约合 9.5 亿元，接近整个上半年的收入（推算）。IDC 统计的工具口径可能严重低估了实际的经济活动。
- **分工格局已经成形。** 大厂工具（TRAE、Qoder、CodeBuddy、码道）普遍采用"免费或低价获客 + 企业版收费 + 多模型（含友商模型）"的打法，目的是拉动云和 Token 消耗。模型创业公司（智谱、Kimi、MiniMax、DeepSeek）则通过 Coding Plan、Token Plan 和 API，承接第三方工具的流量，尤其是 Claude Code、OpenCode、Cline、Kilo Code、OpenClaw。
- **产品形态快速"去 IDE 化"。** 演进路径是插件/IDE → CLI/Agent → 智能体工作台/Cowork。例子包括 Qoder 1.0 与新 Qoder、TRAE 合并 TraeWork、CodeBuddy 延伸到 WorkBuddy、智谱提出"Coding→Cowork"、阿里规划千问办公、美团 CatPaw。"AI 编程"作为独立品类，正在和通用 Agent 工作台融合。
- **模型迭代极快，头部格局在月度尺度上变化。** 智谱 11 个月发布 6 代；Qwen 半年从 3.5 迭代到 3.8。2026 年下半年 MiniMax 掉队，智谱和 DeepSeek 加速。

### Gaps
- TRAE 2026 年的 MAU、付费用户和收入均未披露（最新官方数字仍是 2025-12 的 600 万累计用户和 160 万 MAU）。火山方舟 Coding Plan 的订阅数也未披露；Doubao-Seed-Code、Seed-2.0-Code 的确切发布日期没有查到。
- 百度文心快码和秒哒 2026 年的进展、用户与定价未检索到（WebSearch 配额耗尽，官网无法抓到正文）。
- 蚂蚁 CodeFuse、aiXcoder（硅心科技）等 2026 年的数据未检索到。
- IDC 报告中第 2–5 名厂商及其份额、统计口径的细节都未公开。
- Qoder 用户数（500 万还是 600 万）、"通义灵码更名 Qoder CN"都没有官方确认。
- 智谱 Coding Plan 的订阅人数和收入占比，以及 MiniMax Code、Kimi Code 的独立 ARR，都没有单独披露。

---

## 二、中国模型在全球 Coding 生态中的角色

### Takeaway
2026 年中国开源权重模型已成为全球 Agentic Coding 的"低价 token 层和基座层"。直接渠道是 OpenRouter、OpenCode、Cline/Kilo 等平台，中国模型的 token 份额常被报道为约 61%。间接渠道是美国产品在中国模型上做后训练：Cursor Composer 2 基于 Kimi K2.5，Devin 和 Fireworks Ember-1 基于 K3。与此同时，下半年中国厂商开始用许可条款向海外托管方收费（K3 最高分成 30%，Qwen3.8-Max 设 5000 万美元门槛），美国国会也开始审查美企使用中国模型的情况。

### Cited Findings
- OpenRouter 2026-02-24 的数据显示，中国模型占 61% 的 token 消耗 — [Dataconomy](https://dataconomy.com/2026/02/25/chinese-ai-models-hit-61-market-share-on-openrouter/)
  - 口径：当周中国模型 5.3T，前十模型合计 8.7T，全平台约 12.1T tokens/周。
  - 头部模型：MiniMax M2.5 为 2.45T（周环比 +197%）；Kimi K2.5 为 1.21T；GLM-5 为 780B；DeepSeek V3.2 排第五。
  - 编程占比：编程占 OpenRouter token 的比例，由 2025 年初的 11% 升至 50% 以上。
  - 引语：OpenRouter COO Chris Clark 称中国开源模型"disproportionately heavy in agentic flows run by U.S. firms"；a16z 的 Martin Casado 估计，使用开源栈的创业公司中约 80% 在用中国模型。
- 2026-06 的数据来自供应商博客整理，并非 OpenRouter 官方发布 — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)
  - 总体：中国模型约占开发者 token 的 61%；美国三巨头的份额在 12 个月内从约 70% 降至 30%（引 Bloomberg）。
  - 厂商份额：DeepSeek 17.6%、Anthropic 14.8%、Google 12.5%、OpenAI 8.4%、小米 8.3%、MiniMax 8.1%、腾讯 8.1%、Qwen 4.3%。
- 中国厂商把 OpenRouter 当作新模型的"匿名打榜/冷启动"渠道：
  - Pony Alpha 即 GLM-5（2026-02）— [财联社](https://www.cls.cn/detail/2285957)
  - Ox-Alpha 即 GLM-5.3-Flash（2026-08），6 天跑了 62 万亿 tokens — [腾讯新闻](https://news.qq.com/rain/a/20260904A042IS00)
  - Qwen3.6-Plus 上线 3 天，日 Token 达 1.4 万亿（2026-04）— [投中网](https://m.chinaventure.com.cn/news/78-20260629-392056.html)
- Cursor Composer 2（2026-03）基于 Kimi K2.5，做了续训和大规模 RL — [Cursor 技术报告](https://cursor.com/blog/composer-2-technical-report)；[Wikipedia: Cursor](https://en.wikipedia.org/wiki/Cursor_(company))；[Trending Topics](https://www.trendingtopics.eu/cursor-admits-composer-2-is-built-on-chinese-ai-model-kimi-k2-5/)
  - 披露经过：Cursor 发布时未说明基座，被用户发现后，Lee Robinson 承认，并称最终模型只有约 1/4 的算力来自基座；联合创始人 Aman Sanger 称未提及是"失误"。
  - 授权：Moonshot 称 Cursor 经 Fireworks AI 获得授权商用。
  - 背景推测：TechCrunch（2026-03-22）推测 Cursor 不披露与中美 AI 紧张关系有关，这只是推测 — [Wikipedia: Cursor](https://en.wikipedia.org/wiki/Cursor_(company))
- 2026-09，Cognition 的 Devin 和 Fireworks AI 的 Ember-1 被报道基于 Kimi K3 做后训练，引用的是 Cognition 2026-09-10 与 Fireworks 2026-09-23 的文章 — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
- 许可条款开始向海外托管方收费：
  - Kimi K3：年收入超 2000 万美元的托管商须与 Moonshot 签商业协议，分成最高 30% — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
  - Qwen3.8-Max 权重（2026-08-12）：年收入超 5000 万美元的服务商须签商业条款 — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- 美国审查：自 2026-04 起，美国众议院国土安全委员会就 DoorDash 和 Anysphere（Cursor 母公司）在部分工程任务中使用 Kimi 模型施压。2026-07-31 有报道称 DoorDash 收到传票 — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
- API 价格对比：
  - 2026-02：M2.5 $0.30/$1.10，GLM-5 $0.30/$2.55，Claude Opus 4.6 $5/$25，相差约 10–20 倍 — [Dataconomy](https://dataconomy.com/2026/02/25/chinese-ai-models-hit-61-market-share-on-openrouter/)
  - 2026-06：M3 输入 $0.60，Opus 4.8 输入 $5.00 — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)
  - 2026-07：K3 为 $3/$15，Wikipedia 称其与 Claude Sonnet 价格相当，说明头部中国模型开始放弃"超低价" — [财联社](https://www.cls.cn/detail/2429127)；[Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
- 订阅价格对比（2026-09-24）— [codingplan.org](https://codingplan.org/en)
  - Claude：Pro $20 / Max 5x $100 / Max 20x $200。
  - 中国厂商：GLM $18 / $80 / $168；MiniMax $20 / $50 / $120。
  - 聚合器：OpenCode Go 售价 $10，含 Kimi K3、MiniMax M3、Qwen3.7 Plus、DeepSeek V4.1 Flash、MiMo-V2.6-Flash 等 32 个模型。
- 海外收入：MiniMax 2026H1 海外收入占 60.8% — [虎嗅](https://www.huxiu.com/article/4886381.html)。智谱的付费日活覆盖 233 个国家/地区，海外主要通过与海外云厂商合作、托管开源模型分成推进 — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
- DeepSeek V4-Pro 正式版原生支持 OpenAI Responses API，并针对 Codex 做了优化，即直接接入美国厂商的 Agent 外壳 — [TechOrange](https://techorange.com/2026/08/14/deepseek-harness-launches-open-source-ai-rival-claude-code/)
- Anthropic 称三家中国实验室的蒸馏集中在 agentic reasoning、tool use 和 coding — [TechCrunch](https://techcrunch.com/2026/02/23/anthropic-accuses-chinese-ai-labs-of-mining-claude-as-us-debates-ai-chip-exports/)

### Inferences
- **注意 61% 的口径。** 按 Dataconomy 给的数字，5.3T/8.7T≈61%，这更像是"前十模型中的份额"；若以全平台约 12.1T 计，中国模型约占 44%（推算）。token 份额也不等于收入份额，中国模型单价低 10–20 倍，按收入算份额会低得多。报告中引用"61%"时建议注明口径。
- **2026 年中国模型在全球形成"双通道"渗透。** 一条是通过路由平台和开源 Agent 工具直接卖 token；另一条是作为美国产品的后训练基座（Cursor、Cognition、Fireworks）。后一条在品牌上不可见，但价值更高，这也是 K3、Qwen3.8 在许可中加入收费门槛的原因。
- **2027 年的主要风险是地缘政治与合规。** 美国国会传票、Anthropic 蒸馏指控和中国网信办调查（见第三节）同时出现，可能限制受监管行业和政府承包商的美企使用中国模型。中国厂商的海外收入（MiniMax 超过 60%）面临政策尾部风险。

### Gaps
- 没有找到 OpenRouter 官方"Programming 类别"中中国模型份额的一手数据；61% 的计算口径也存疑。
- 2025 年 Windsurf/Cognition SWE-1.5 疑似基于 GLM 的说法，以及 Airbnb 等美企采用 Qwen 的案例，本轮未核实。
- Cursor 后续版本（Composer 2.5 等）的基座只有二手来源，未核实。
- 中国厂商海外 Coding Plan 的订阅人数没有任何披露。

---

## 三、访问限制的影响（Anthropic 政策、Claude Code 封号、出口管制）与国产替代

### Takeaway
2025-09 Anthropic 停止向中国控股（持股超过 50%）的实体销售，这条政策在 2026 年没有放松。此后又出现了几层新的限制：2026-02 起针对 DeepSeek、Moonshot、MiniMax、阿里云、Z.ai 的一系列蒸馏指控；2026-06 底针对中国开发者的 Claude Code 封号潮；据二手来源，6 月中旬还有美国出口管制导致的新模型对外暂停。这些因素强化了"Claude Code 等外壳 + 国产模型 Coding Plan（Anthropic 兼容接口）"的替代路径。但高端开发者仍在设法使用 Claude Code 和 Codex，国产模型在复杂任务上的差距依然被行业人士公开承认。

### Cited Findings
- 【2025 背景】2025-09，Anthropic 宣布停止向中国、俄罗斯、伊朗、朝鲜等地实体直接或间接持股超过 50% 的公司销售产品（FT，2025-09-04/05）— [Wikipedia: Anthropic](https://en.wikipedia.org/wiki/Anthropic)；[阿里云开发者社区](https://developer.aliyun.com/article/1744772)
- 2026-02-23，Anthropic 指控 DeepSeek、Moonshot、MiniMax 用约 2.4 万个虚假账号、超过 1600 万次对话蒸馏 Claude — [Anthropic X](https://x.com/AnthropicAI/status/2025997928242811253)；[TechCrunch](https://techcrunch.com/2026/02/23/anthropic-accuses-chinese-ai-labs-of-mining-claude-as-us-debates-ai-chip-exports/)；[CNN](https://www.cnn.com/2026/02/24/tech/anthropic-chinese-ai-distillation-intl-hnk)。二手摘要称其中 MiniMax 约 1300 万次、DeepSeek 约 15 万次 — [Edward Conard 摘要](https://www.edwardconard.com/macro-roundup/anthropic-reported-that-three-leading-chinese-ai-developers-illicitly-extracted-results-from-claude-by-training-their-own-models-on-the-outputs-from-the-more-powerful-system-a-tactic-known-as/)
- 2026-06，Anthropic 指控阿里云有类似行为（BBC，2026-06-25）。Z.ai 也在 2026 年被指控，具体日期不详 — [Wikipedia: Anthropic](https://en.wikipedia.org/wiki/Anthropic)
- 2026-09-10，Anthropic 再次指控 Moonshot：经新加坡、日本代理服务器的 5,380 个账号，与 Claude（主要是 Opus）进行了超过 2300 万次交互并用于训练。2026-09-22（Gizmodo 报道）中国网信办就相关指控启动调查，同时审查针对 DeepSeek 的类似指控 — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)
- 2026-06 底，大量国内开发者反馈 Claude Code 账号被封，杭州 IP 受影响最重，新老账号都有。社区逆向分析称风控会参考系统时区（Asia/Shanghai 等）和中转域名（内置 147 个域名清单），而不只看 IP。Anthropic 从未公开说明检测机制，以上说法未核实 — [阿里云开发者社区（2026-07-01）](https://developer.aliyun.com/article/1744772)
- 同一篇文章还称：2026-06-09 Anthropic 发布 Claude Fable 5 和 Mythos 5；06-12 美国政府下令暂停所有外国用户的访问，后经商务部审查解除限制后恢复；但 Anthropic 自身的 50% 政策仍使中国用户无法使用。这是二手来源，未核实 — [阿里云开发者社区](https://developer.aliyun.com/article/1744772)。另一篇供应商博客也称 Fable 5 在 6 月中旬因出口管制全球下线、状态不明 — [MESHLAUNCH](https://meshlaunch.com/en/blog/2026-openrouter-rankings-june-2026.html)
- 国内媒体梳理的替代路径主要有三类 — [IT之家（经搜索摘要，原文抓取 404）](https://www.ithome.com/1/001/608.htm)
  - 通过 Anthropic 兼容协议，让 Claude Code 接入国产模型。
  - 改用国产原生工具，如 Kimi Code、Qoder、TRAE。
  - 使用中转平台，但有封号和合规风险。
- 供给侧已普遍兼容 Claude Code：
  - 火山方舟 Coding Plan 提供 Claude Code 专用 Base URL — [火山引擎](https://www.volcengine.com/article/37522)
  - DeepSeek V4 API 支持 Anthropic 接口，并专门适配 Claude Code — [澎湃新闻](https://www.thepaper.cn/newsDetail_forward_33042587)
  - 摩尔线程 AI Coding Plan 兼容 Claude Code、Cursor、OpenCode — [财联社](https://www.cls.cn/detail/2285957)
  - 智谱 ZCode（2026-07-02）可同时接入 OpenAI、Anthropic、Moonshot、OpenRouter 的模型 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Zhipu_AI)
  - CodeBuddy Code 2.0 支持自定义模型，如 GLM-4.7、GPT-5.2 Codex — [财联社](https://www.cls.cn/detail/2285957)
- 需求侧仍依赖海外工具：2026-07，Agent 开发者蒋青云称，有复杂编码需求的专业开发者多数不用国产桌面 Agent，而是花更多钱用 Claude Code、Codex，甚至多账号 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)。2026-02，AI 产品经理张亮称国产编程模型在实际使用中仍落后于 Claude — [财联社](https://www.cls.cn/detail/2285957)。月之暗面也承认 K3 整体略逊于 Claude Fable 5 和 GPT-5.6 Sol — [财联社](https://www.cls.cn/detail/2429127)
- 中关村在线文章称 2026-07 工信部相关安全平台对 Claude Code 特定版本发布了风险提示。原文乱码，未核实 — [中关村在线](https://news.zol.com.cn/1251/12519211.html)

### Inferences
- **限制起到"推一把"的作用。** 正规渠道接近封死（政策 + 封号 + 支付与注册门槛），推动国内形成"海外 Agent 外壳 + 国产模型后端"的事实标准。几乎所有国产 Coding Plan 都以"兼容 Claude Code"为卖点，这让 Claude Code 在中国的"协议地位"高于它的实际付费渗透。
- **替代需求叠加 Agent 编程的高 token 消耗，导致国产算力被挤兑。** 智谱 2 月限售、Kimi 7 月暂停新订阅、火山方舟每日限量，都是直接后果，也为下半年的集体提价和峰谷计价提供了条件（见第五节）。
- **蒸馏指控会提高国产模型的数据成本。** 指控本身有争议，但它意味着通过 Claude 输出合成编程训练数据的渠道在收紧。2027 年国产模型在编程上的追赶，可能更依赖自建 RL 环境，例如快手 KAT-Coder-V2.5 用了 10 万多个可验证仓库环境（推断）。

### Gaps
- 没有找到 Anthropic 在 2026 年对华政策的官方修订文本；"6 月美国政府暂停外国用户访问"只有二手来源。
- Cursor 在 2026 年对中国区 Claude/GPT 模型访问的变化未检索到；TRAE 国际版 2025 年下架 Claude 一事本轮未核实。
- 封号潮的规模（账号数）没有任何可靠统计。

---

## 四、中国企业落地（金融/运营商/央国企/互联网；私有化与一体机；AI 代码占比；招投标）

### Takeaway
互联网大厂的 AI 生成代码占比在 2025 年已达到 40–50% 区间（腾讯 50%、百度超过 43%、字节 92% 的工程师使用 TRAE），2026 年腾讯开始称"大部分代码由 AI 生成"。金融业大模型采购在 2026 上半年同比增长 110%，私有化部署和一体机是受监管行业的主流选择。但公开招投标中，AI 编程很少单独立项，相关采购多以研发效能平台、云框架协议或大模型平台子项的形式出现。

### Cited Findings
- 智能超参数《中国大模型中标项目监测与洞察报告（2025）》（2026-01-15 报道）— [经济观察网](http://www.eeo.com.cn/2026/0115/779399.shtml)
  - 总量：2025 年金融大模型中标 587 个项目、15.06 亿元，项目数 +341%、金额 +527%。
  - 机构分布：银行 290 个、11.32 亿元（占 75.2%）；证券 96 个；保险 82 个。
  - 前五厂商：百度 38 个/6021 万元；科大讯飞 37 个/5881 万元；火山引擎 31 个/5300 万元；中关村科金 20 个；阿里云 17 个/3080 万元。
  - 编程场景：阿里云以通义灵码"智能编程"切入金融机构研发，称可减少 30% 以上的重复代码工作。
- 2026H1 金融大模型中标 406 个，同比 +110%，银行在项目数和金额中都接近一半。自 2025H2 起，以智能体为主的应用类项目中标数已超过算力类。报道没有提到 AI 编程专项 — [21世纪经济报道/新浪](https://finance.sina.com.cn/roll/2026-08-11/doc-inimxvun5828801.shtml)
- 2026-08，银行业 AI 相关中标 43 个，涉及 35 家银行，其中城商行 19 家（第三方统计）— [银行联合信息网](http://www.unbank.info/static/pages/2064/651971.html)
- 2026-04，某银行采购两套大模型一体机，预算 1658 万元，科大讯飞为拟中标方（非编程专项）— [新浪科技](https://finance.sina.com.cn/tech/roll/2026-04-08/doc-inhtuyvy1467238.shtml)。中国银行上海分行的风险管理智能体项目三个月内四次发布，前三次流标；大型国有银行的大模型多以自建为主 — [腾讯新闻](https://news.qq.com/rain/a/20260512A04OCV00)
- 2026 年大模型一体机招采活跃，公安、金融、医疗、政务等行业因合规要求首选本地化部署 — [智研咨询](https://www.chyxx.com/industry/1277383.html)
- 私有化和企业级供给：
  - 腾讯 CodeBuddy 专有云企业版 316 元/人/月（2026-05-15 起）— [财联社](https://www.cls.cn/detail/2357934)
  - Qoder 企业版可按人、组、仓库管控模型权限，提供 L1–L4 代码防护 — [量子位](https://www.qbitai.com/2026/07/452914.html)
  - 美团 CatPaw Managed Agents 支持私有化部署 — [美团技术团队](https://tech.meituan.com/2026/07/28/CatPaw-LongCat.html)
  - 华为码道主打"自主可控"，基于千亿级代码库 — [新浪科技](https://finance.sina.com.cn/tech/discovery/2026-02-27/doc-inhpefha7144059.shtml)
  - 智谱 2026H1 本地化部署收入 1.62 亿元，同比 −20.5%，收入结构正从项目制转向 API — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
- 中国信通院《AI4SE 行业报告 2026》经中关村在线转引，原文乱码，以下数字需对照原报告核实 — [中关村在线](https://news.zol.com.cn/1251/12519211.html)
  - 企业使用：企业使用 AI 编程的比例由 19.65% 升至 46.09%；深度使用由 26.81% 升至 42.61%；处于 L3 阶段的企业由 17.62% 升至 29.75%。
  - AI 代码占比：AI 编写代码超过 90% 的企业，由 5.71%（2024）升至 27.65%；全球新增代码中 AI 辅助的占比超过 42%。
- 各企业公开的 AI 代码占比：
  - 腾讯：50% 的新增代码由 AI 辅助生成，超过 90% 的工程师使用 CodeBuddy（2025-10）— [腾讯云开发者](https://cloud.tencent.com/developer/news/3143570)。CodeBuddy Code 在内部有超过 1.2 万名工程师使用（2026-02）— [财联社](https://www.cls.cn/detail/2285957)。汤道生 2026-06 称"今年大部分代码由 AI 生成"（二手转述，未给比例）— [openinstall](https://www.openinstall.com/article/news/tencent-ai-daima-shengcheng-kaifa-menkan)
  - 字节：92% 的工程师使用 TRAE；抖音生活服务 AI 代码贡献占 43%（2025-12）— [极客公园/腾讯新闻](https://news.qq.com/rain/a/20251229A065ZX00)
  - 百度：每日新增代码中，文心快码生成的占比超过 43%（2025-06）— [量子位](https://www.qbitai.com/2025/06/300135.html)
  - 阿里：蔡崇信称阿里约 30% 的代码由 AI 生成（时间与口径不详）— [36氪](https://eu.36kr.com/zh/p/3512870506158984)。另有帖子称阿里云内部 AI 辅助代码比例为 40%（2025-05，未核实）— [雪球](https://xueqiu.com/6955840256/378226508)
  - 美团：CatPaw 覆盖 9 万名员工，员工已建 3 万个 Agent（2026-07）— [美团技术团队](https://tech.meituan.com/2026/07/28/CatPaw-LongCat.html)
  - DeepSeek：V4 已成为内部员工的主力 Agentic Coding 模型（2026-04）— [澎湃新闻](https://www.thepaper.cn/newsDetail_forward_33042587)
  - 启明星辰（安全厂商，002439）：2025 年编码工作中 AI 占 80%，预计 2026 年达 95%，新产品中 AI 生成代码超过 50% — [财联社](https://www.cls.cn/detail/2285957)

### Inferences
- **大厂 AI 代码占比只能作方向性指标。** 统计口径不一（新增代码还是全部代码，辅助生成还是完全生成），无法横向比较。但趋势很清楚：2025 年各大厂在 40–50%，2026 年进入"大部分"区间，且由 CLI/Agent 驱动，而不再是补全。
- **金融和政企的 AI 编程采购很少以"AI 编程"名义单独招标。** 更常见的形式是：大模型平台或一体机的子项；云厂商框架协议（例如阿里云在金融业以通义灵码切入）；或厂商的私有化、专有云版本。这能部分解释为什么 IDC 统计的工具市场规模偏小（推断）。
- **私有化需求与国产算力绑定。** 华为码道、智谱的 10 万卡国产集群、美团 LongCat 的 5 万国产卡训练，说明"国产芯片 + 私有化"在金融、政务、央企有可能成为 2027 年企业版 AI 编程的准入门槛（推断）。

### Gaps
- 没有检索到运营商（中国移动、电信、联通）和央国企的 AI 编程采购或自研案例。
- 智能超参数等机构的 AI 编程专项招投标数据（项目数、金额、中标厂商）没有检索到。
- 代码大模型一体机的出货量和中标规模没有检索到。
- 字节、阿里、百度 2026 年的官方 AI 代码占比没有检索到。
- 信通院 AI4SE 2026 的原始数字需核对原报告（转引文本乱码）。

---

## 五、竞争格局、商业模式难题与 2027 展望

### Takeaway
2026 年国内 AI Coding 的核心矛盾，已从"免费/低价获客"变成"在算力约束下争夺定价权"。Agentic Coding 带来 token 需求暴增，而算力供给受限，于是出现了限售、暂停订阅、峰谷计价和集体涨价。智谱、Kimi 实现了量价齐升；MiniMax 陷入量增价跌，市值大幅回撤；大厂工具层继续靠免费换生态。整个行业仍是高亏损、低毛利：智谱 API 毛利率 24.6%，MiniMax 整体毛利率 17.9%。对 2027 年，可预期的方向包括：Coding 扩展到 Cowork/通用 Agent、ARR 继续高增但口径和留存需验证、Kimi 等公司上市、海外许可分成，以及地缘合规风险。

### Cited Findings
- **竞争格局：**
  - 工具营收份额：阿里占 47.6%，超过第 2–5 名之和（IDC，2025 年）— [新浪财经](https://finance.sina.com.cn/stock/t/2026-07-16/doc-inihyiym7977683.shtml)
  - 办公/Agent 流量（2026-06）：WorkBuddy 2097 万 > TRAE + 扣子 1441 万 > QoderWork 788 万 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
  - 编程模型：虎嗅称智谱 GLM 和 DeepSeek 在编程上份额提升，MiniMax M3 表现不佳 — [虎嗅](https://www.huxiu.com/article/4886381.html)
- **算力瓶颈：**
  - 智谱：2026-02 Coding Plan 限量销售 — [财联社](https://www.cls.cn/detail/2285957)；同月限制新用户注册，股价跌约 23% — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Zhipu_AI)
  - Kimi：2026-07-19 暂停 C 端新订阅 — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
  - 火山方舟：Lite 档每日限量放售；Kimi 和 GLM 的套餐频繁出现 429 — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)
  - 腾讯：2026-03 CodeBuddy 因 WorkBuddy 流量冲击服务不稳定 — [百度百科](https://baike.baidu.com/en/item/CodeBuddy/1432154)
- **涨价与计价改革：**
  - 智谱：API 涨价 10%（2026-04-07）— [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Zhipu_AI)；上半年 API 均价 +101% — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)；Coding Plan 07-30 涨价 61–152%，并引入高峰 3 倍计费 — [腾讯云开发者社区](https://cloud.tencent.com/developer/article/2718987)。媒体评论为"价格向海外看齐" — [新浪财经](https://finance.sina.com.cn/stock/t/2026-07-31/doc-iniksxpi1210399.shtml)
  - DeepSeek：峰谷定价，高峰 2 倍（2026-06-29 报道）— [阿里云开发者社区](https://developer.aliyun.com/article/1744772)
  - 腾讯 CodeBuddy：企业版涨价约 2–2.5 倍（2026-05-15 生效）— [财联社](https://www.cls.cn/detail/2357934)
  - Kimi K3：定价偏高（输出约 100 元/百万 tokens），摩根士丹利认为可能引导国内模型定价 — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
  - MiniMax：Coding Plan 改为 Token Plan 后遭用户反弹，永久降价 50% 并发放补偿，毛利受损 — [虎嗅](https://www.huxiu.com/article/4886381.html)
  - TRAE：国际版 2026-02 起改为五档付费并收紧试用；国内个人版仍免费，或已改为积分制 — [火山引擎文章](https://www.volcengine.com/article/2844592)
  - 阿里：百炼 Coding Plan Lite 下线，转向按 Credits 计费的 Token Plan — [awesome-coding-plan](https://github.com/mahonzhan/awesome-coding-plan)；[codingplan.org](https://codingplan.org/en)
- **盈利压力：**
  - 智谱：2026H1 净亏损 20.72 亿元；API 毛利率 24.6%，管理层目标是 12–18 个月内达到约 50% — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
  - MiniMax：毛利率 17.9%，净亏损 3.58 亿美元。Token Plan 量大价低，拉低了毛利；管理层称下半年毛利只会环比改善，难以回到 2025H2 的 33.5% — [虎嗅](https://www.huxiu.com/article/4886381.html)；[美通社](https://www.prnasia.com/story/545325-1.shtml)
- **ARR 口径争议：**
  - 智谱：16 亿美元按月收入×12；超 20 亿美元按周收入×52。有分析认为口径激进，且恰逢新品流量峰值，留存待验证 — [X @shao__meng](https://x.com/shao__meng/status/2094578840723210482)；[Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
  - MiniMax：8 亿美元按周收入×52 计算 — [虎嗅](https://www.huxiu.com/article/4886381.html)
- **付费意愿：** 艾媒调查显示近 60% 的用户愿为 AI 办公智能体付费，超过 30% 仍在观望；专业开发者则愿为海外工具多付费 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
- **Agent 需求驱动：** OpenClaw（"龙虾"）热潮推高了 Agent 调用。Kimi K2.5 曾登 OpenRouter OpenClaw 调用榜首 — [财联社](https://www.cls.cn/detail/2285957)；WorkBuddy 的增长被认为主要靠"龙虾"热潮 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)；DeepSeek V4 也专门适配了 OpenClaw — [澎湃新闻](https://www.thepaper.cn/newsDetail_forward_33042587)
- **资本市场：**
  - 智谱：2026-08 市值约 620 亿美元 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Zhipu_AI)
  - Moonshot：2026-07-30 估值 350 亿美元 — [Wikipedia: Moonshot AI](https://en.wikipedia.org/wiki/Moonshot_AI)；计划最快 6 个月内港股 IPO — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
  - MiniMax：市值从约 4300 亿港元跌到约 1098 亿港元 — [虎嗅](https://www.huxiu.com/article/4886381.html)
- **2027 及之后的前瞻指标（均为管理层指引或机构预测，非事实）：**
  - IDC：预计 2026 年底中国 AI 编程市场规模 11.73 亿元，未见 2027 年预测 — [新浪财经](https://finance.sina.com.cn/stock/t/2026-07-16/doc-inihyiym7977683.shtml)
  - 智谱：2026 年底 ARR 目标 24 亿美元；GLM-6.0 在年底实现全自研训练；API 毛利率 12–18 个月内达到约 50%；国产芯片 3–6 个月内扩容；海外云合作 1–2 个月内见进展 — [Winter Research](https://winterresearch.com/zhipu_interim_2026_0901)
  - Kimi：野村预计 2026 年底 ARR 超过 10 亿美元 — [新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-07-22/doc-iniirfsq9008030.shtml)
  - MiniMax：全年 ARR 目标 10 亿美元，未上调 — [虎嗅](https://www.huxiu.com/article/4886381.html)
  - 艾媒：中国 AI 智能体市场 2025 年为 804 亿元，预计 2030 年达 6968 亿元 — [21世纪经济报道](https://m.21jingji.com/article/20260722/herald/c96f8ec72d3fa36c6300b52646d32921.html)
  - 中关村在线文章称 2026-09 有政府文件提出到 2028 年推广 AI 编程，但发文机关和目标因乱码无法辨认，未核实 — [中关村在线](https://news.zol.com.cn/1251/12519211.html)

### Inferences
- **2026 年下半年是国内 AI Coding 定价的拐点。** 国内 Coding Plan 从"首月 ¥7.9–8.91、Lite ¥40"的补贴价，走向与海外接近的价格：智谱国内 Pro 标价 ¥538，约合 $76，海外 Pro 为 $80；Kimi Max ¥699，约合 $98，接近 Claude Max 5x 的 $100。驱动因素有三个：Agent 编程的 token 消耗呈指数级增长、算力约束（国产芯片和进口 GPU 都受限）、头部模型能力接近海外。"中国开发者付费意愿低"的说法在模型层正在被部分改写，但在工具层（IDE 免费）还没有。
- **分化加剧。** 能力处于第一梯队的模型（GLM-5.x、K3、DeepSeek V4）有定价权；跟不上的厂商（MiniMax M3）陷入"量增价跌、毛利下滑"。这印证了虎嗅的判断："模型智能仍是主要竞争因素，价格只在性能相当时才起作用"。
- **2027 年的可能走向（推断）：**
  1. 品类进一步扩展为"Coding + Cowork + 通用 Agent 工作台"，大厂的 IDE、办公 Agent 和云平台捆绑销售。
  2. 计价普遍改为积分/Token、峰谷、分档，按席位定价的纯工具订阅弱化。
  3. 模型厂商 ARR 继续高增，但市场会更关注口径（×12 还是 ×52）、留存和毛利。智谱"API 毛利率达 50%"能否兑现是关键观察点。
  4. 上市潮：Kimi 港股 IPO 可能在 2026 年底到 2027 年初进行；行业估值与 ARR 倍数将接受公开市场检验。
  5. 海外：许可分成（K3 最高 30%、Qwen3.8 有门槛）加上海外云合作，可能成为新的收入来源；但美国国会审查、蒸馏指控和网信办调查构成双向的合规风险。
  6. 私有化与国产算力适配，可能成为金融、政务、央企采购企业版的门槛。
- **IDC 预测与模型厂商数据之间有数量级差距。** 预测 2026 年工具市场 11.73 亿元，而智谱一家 8 月单月收入就约 9.5 亿元（推算）。这说明"中国 AI 编程市场规模"按工具口径和按模型/API 口径相差一个数量级以上，规划报告引用时必须注明口径。

### Gaps
- 没有找到第三方机构对 2027 年中国 AI 编程市场规模的预测。
- 工具层（TRAE、Qoder、CodeBuddy、文心快码）的付费转化率和 ARPU 均未披露。
- 晚点 LatePost、36氪、极客公园等关于国内 AI Coding 商业模式的深度报道（比如免费模式的亏损规模、补贴力度）未能检索，WebSearch 配额已耗尽；如需补充，可在后续继续检索。
- 沙丘智库的 AI 编程相关报告未检索到。
