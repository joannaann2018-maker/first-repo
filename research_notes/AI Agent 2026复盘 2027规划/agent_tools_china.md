# 中国 Agent 工具 / 智能体平台 / 智能体产品：2026 年（1–10 月）回顾与 2027 信号

> 调研日期：2026-10-23。说明：本轮调研中途共享 WebSearch 额度用尽，后半程仅通过抓取已检索到的原文页面补证。标注"（搜索摘要）"的条目只来自搜索引擎摘要、未能打开原文逐字核对；标注"（厂商口径）"的为公司自报、未经第三方验证。2025 年信息仅作背景并已注明。

---

## 一、大厂智能体平台：2026 年的发布、规模与变现（字节 / 阿里 / 腾讯 / 百度 / 华为）

### Takeaway
2026 年大厂平台的竞争重心从"低代码搭 Bot"转向**企业级 AgentOps + 云上 Agent 运行时/沙箱/治理 + 办公入口**：字节（扣子 3.0、HiAgent 3.0、AgentKit、ArkClaw）、阿里（AgentCore/Agent Sandbox、钉钉悟空、千问办公）、腾讯（ADP 4.0、WorkBuddy、QClaw）、百度（千帆 130 万+ Agent、百度搭子、秒哒、伐谋）、华为（HMAF 2.0）都在补"可控执行与治理"这一层。规模普遍用 Token 调用量来讲（豆包日均 180 万亿 tokens、火山 MaaS 份额 49.5%）；平台本身几乎不披露单独收入，变现主要靠模型 Token、云资源和订阅（Token Plan）。

### Cited Findings

#### 字节跳动 / 火山引擎（扣子 Coze、HiAgent、AgentKit、ArkClaw、飞书 aily）
- **扣子 3.0（2026 年 5 月底）**：官方 FAQ 记为 2026-05-29 发布（搜索摘要）；IT之家 6 月 1 日报道称"前天"发布。核心功能：一人+多 Agent / 多人+多 Agent 协作、多项目独立管理、资产自动沉淀；可接入 Claude Code、Codex CLI、OpenClaw 等本地 Agent；手机与电脑同步，可授权 Agent 处理本地文件；提供行业专家模板（自媒体、法律、金融、互联网、医疗）— [新浪科技/IT之家 2026-06-01](https://finance.sina.com.cn/tech/digi/2026-06-01/doc-inhzwyqr2443757.shtml)；[扣子 FAQ](https://docs.coze.cn/cozespace_coze_app_faq)
- 扣子 3.0 号称"正式全球上线"，上百个行业模板，称"3 分钟"可搭一个 Agent（推广性质的文章，未独立核实）— [新浪财经 2026-06-03](https://finance.sina.com.cn/wm/2026-06-03/doc-inhzzyte2869078.shtml)
- 3.0 在 iOS/Android、Mac/Windows 和网页端全量更新 — [观猹产品页](https://watcha.cn/products/coze)（搜索摘要）
- 扣子官方更新日志：**2026-03** 扣子编程支持"三方知识库连接器"，可接入企业自建、本地或内部系统知识库；**2026-07-01** 起下线"低代码智能体发布至豆包渠道"的入口，理由是服务稳定性，已发布的不受影响 — [扣子更新动态](https://docs.coze.cn/recent-updates)
- 规模（厂商口径）：火山引擎产品页称扣子开发平台有"上万家企业、数百万开发者"使用；AgentKit 定位企业级 AI Agent 平台，提供身份控制、工具链、运行时和治理 — [火山引擎产品列表](https://www.volcengine.com/product/list)
- 背景（2025 年度）：IDC《2025 中国智能体开发平台市场份额报告》显示，火山引擎在私有化部署和公有云两个细分市场分别以 17.8% 和 19.3% 的份额排第一（HiAgent + 扣子）— [知乎转述](https://zhuanlan.zhihu.com/p/2050221892016067387)
- **FORCE 原动力大会（2026-06-23）**：豆包大模型日均 tokens 调用量达 180 万亿，2024 年 5 月发布时为 1200 亿，两年增长超 1500 倍，过去一年增长超 10 倍；2026 年 3 月时为 120 万亿；火山引擎在中国公有云 MaaS 市场的 Token 份额为 49.5%（IDC）— [界面新闻](https://www.jiemian.com/article/14629207.html)；[证券时报](https://www.stcn.com/article/detail/3973835.html)；[SegmentFault 解读](https://segmentfault.com/a/1190000047897953)
- 同场 Agent 工具升级：AgentKit、HiAgent 3.0、ArkClaw 企业版 Agent 工作台、AI Trust 安全体系；年累计 Token 消耗超 1 万亿的企业客户从 2025 年 12 月约 100 家增至 2026 年 6 月 200 多家 — [SegmentFault](https://segmentfault.com/a/1190000047897953)
- 豆包 2.1 Pro 定价：每百万 tokens 输入 6 元、输出 30 元、缓存命中 1.2 元；2.1 Turbo 价格为 Pro 的一半；官方称综合使用成本比 Claude Opus 4.6 低近 80%；Doubao-Seed-Evolving 通道面向 Coding/Agent，每月迭代 2–4 次。演示内容：连续运行近 18 小时完成芯片 RTL 流程；驱动 500 多个 Agent 协作（厂商演示）— [SegmentFault](https://segmentfault.com/a/1190000047897953)
- HiAgent 面向中大型政企、制造、金融、政务（偏私有化），与面向个人和中小企业的扣子是两条产品线；HiAgent 3.0 于 2026-06-23 发布 — [CSDN 解读](https://blog.csdn.net/lpfasd123/article/details/162229660)
- 背景（2025-12）：FORCE 开发者日启动"Agent 核心开发者计划"，在北京、上海、深圳、成都成立 Agent 开发者城市社区 — [知乎](https://zhuanlan.zhihu.com/p/1986770529043116428)
- **飞书 aily（2026-03-19 升级）**：用自然语言创建 Agent，以对话机器人形态常驻联系人列表，可主动交付结果，有技能库；同期发布飞书妙搭和多维表格 AI，并开源官方 OpenClaw 插件（火山引擎、Kimi、智谱等已接入）。飞书 CEO 谢欣："个人用 Agent 是探索，企业用 Agent 要担责" — [每日经济新闻 2026-03-21](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)
- 飞书多维表格智能体于 2026-07 发布；厂商案例：德赛西威基于 aily 搭建的产研智能体，需求查找效率提升超 90%，需求缺陷减少 80% — [网易号选型文](https://www.163.com/dy/article/L21DS91E0556BHK5.html)
- 火山引擎 ArkClaw：云端 SaaS 版 OpenClaw，深度集成飞书，另有 ECS 预装镜像 — [搜狐汇总](https://www.sohu.com/a/996661629_121124363)；[codepick](https://codepick.dev/zh/practices/openclaw-cloud-deploy/)

#### 阿里巴巴 / 阿里云（百炼、AgentCore、钉钉悟空、千问办公）
- 组织调整：阿里于 **2026-03-16** 成立 Alibaba Token Hub（ATH）事业群，"悟空"事业部首次出现在架构中；吴泳铭提出五年内云和 AI 年商业化收入超 1000 亿美元（全公司目标）— [每日经济新闻](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)
- **钉钉"悟空"（2026-03-17）**：自称"全球首个企业级 AI 原生工作平台"，内置于服务超 2000 万企业组织的钉钉；底层经过 CLI 化改造，可原生操作钉钉上千项能力，不靠模拟点击；Agent 自动继承企业权限规则，在安全沙箱中运行；兼容开源 Skill 体系 — [每日经济新闻](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)；[网易号选型文](https://www.163.com/dy/article/L21DS91E0556BHK5.html)
- **2026 云栖大会（9 月 22–24 日，杭州）**：主题"智以致用"，以 Agentic AI 为核心，串联芯片、云基础设施、模型和模型服务 — [21 世纪经济报道](https://m.21jingji.com/article/20260922/herald/d37175fdc7862df8652e2160b6e8f86d_zaker.html)
- 云栖 Agent 发布（以下据网易号 5 万字长文整理，非官方原文）：
  - **AgentCore**：负责长任务执行、失败重试、断点恢复、安全沙箱和审计，官方称 TCO 降低 70%。
  - **Agent Sandbox**：一分钟可创建 10 万个，深休眠唤醒不到 600 毫秒。
  - **Agentic OS**：称可节省 30% 以上 Token。
  - **Agentic Computer**：为 Agent 提供可操作 GUI 的常驻云电脑。
  - **百炼 MaaS**：过去一年客户数增长 6 倍；Prompt Caching 最高省 95%；Token Plan 订阅覆盖 Qwen、Kimi、GLM、DeepSeek 等模型。
  - **Agent Studio**：自动选模型、24 小时托管、50 多个原子 API。
  - **One Key MCP**：一个 API Key 连接 100 多项生态服务。

  — [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
- **千问办公**（同一长文）：上线一个月用户超 3000 万，企业用户占一半以上；推出企业上下文、"带编制的数字员工"和安全中心；益海嘉里金龙鱼、一汽丰田、方达律所宣布接入 — [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
- **Qwen Book（智能体电脑）**在云栖首次亮相，理念是"OS as Harness"，与开源项目 Omarchy 合作，打通支付宝和千问输入法。同场：Smart Fusion 多模型路由称可减少约 50% Token 支出；Qoder 与 Qwen Work 国际版把 Agent 延伸到开发和办公；语音模型全线降价，最高降幅 95% — [每日商报 2026-09-24](https://hzdaily.hangzhou.com.cn/mrsb/2026/09/24/article_detail_3_20260924A116.html)
- Qwen Book 正在招募 100 名深度体验官，12 月开始首批体验，尚未量产；Qwen Intelligence 手机方案包含 Mobile Planner、Mobile-Use、Mobile Creative 三个 Agent，官方称综合任务准确率 91.8%（自家评测集）— [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
- 阿里云 OpenClaw 方案：轻量应用服务器 + 百炼，首月约 9.9 元（促销价），也可通过计算巢或无影云电脑部署 — [搜狐汇总](https://www.sohu.com/a/996661629_121124363)

#### 腾讯（腾讯云智能体开发平台 ADP、WorkBuddy、QClaw）
- **2026-01 合作伙伴大会**：ADP 新增自然语言创建应用，开放模型广场和插件生态；称已在 20 多个行业落地，合作伙伴数量增长 3 倍 — [CSDN](https://www.csdn.net/article/2026-01-23/157285706)（搜索摘要）
- **2026-04-29（重庆峰会）**：ADP 上线"智能工作台"，一句话生成企业级应用，可嵌入企业已有系统；支持 Hy3 preview、DeepSeek-V4 和 Kimi、GLM、MiniMax 等模型 — [中国日报网](https://cn.chinadaily.com.cn/a/202604/29/WS69f1ad77a310942cc49aa199.html)
- **ADP 4.0（2026-06-05 腾讯云 AI 产业应用大会，搜索摘要）**：定位"企业级 AgentOps 平台 / 企业原生智能体中枢"。功能包括 Claw 模式（云端 Agent Loop + 沙箱隔离）；Skill 三级权限（Skill 市场、企业专区、个人专区），上传后自动静态扫描并安检审批；一键发布为 API/SDK，覆盖 H5、微信、企微。已沉淀 130 多个企业级核心 Skills；安全检测覆盖 6 大类 19 种风险，召回率 >95%（社区作者文章，厂商口径）；页面未披露客户数和定价 — [腾讯云开发者社区 2026-06-09](https://cloud.tencent.com/developer/article/2685456)
- ADP 4.0 海外版（2026-07-18，第三方工具站记录）：新增 LINE、Telegram、Google Workspace、Confluence、Jira 集成 — [ai-equal](https://ai-equal.com/tools/adp)（搜索摘要）
- 背景：ADP 3.0 于 2025-09-17 发布 — [百度百科](https://baike.baidu.com/item/%E8%85%BE%E8%AE%AF%E4%BA%91%E6%99%BA%E8%83%BD%E4%BD%93%E5%BC%80%E5%8F%91%E5%B9%B3%E5%8F%B0/67814125)（搜索摘要）
- 智能体平台套餐特惠活动截至 2026-08-31 — [腾讯云活动页](https://cloud.tencent.com/act/pro/adp-pu-activity)（搜索摘要）
- **WorkBuddy（2026-03-09 上线）**：桌面 AI 执行助手，马化腾称其为"中国使用最广的效率智能体服务"；上线三个月月访问量 885 万，是第二名的 2.6 倍；"专家团"覆盖 100 多个领域；技能生态兼容 ClawHub。腾讯 SkillHub 收录 8 万多个 Skills，支持 WorkBuddy、QClaw、ima、Claude Code、Cursor（选型文，数据来源未注明）— [网易号选型文](https://www.163.com/dy/article/L21DS91E0556BHK5.html)
- **QClaw（2026-03-09 报道内测）**：腾讯电脑管家团队做的 OpenClaw 本地一键启动包，默认集成 Kimi、MiniMax、GLM、DeepSeek；微信、QQ 直连，可在聊天窗口 @AI 远程操作电脑 — [新浪财经](https://finance.sina.com.cn/stock/t/2026-03-09/doc-inhqknrq6967657.shtml)

#### 百度（千帆、文心、百度搭子、秒哒、伐谋）
- **2026-01-22 文心 5.0 正式版**（2.4 万亿参数，原生全模态）；千帆平台累计开发的 Agent 超 130 万个 — [新浪财经](https://finance.sina.com.cn/jjxw/2026-01-22/doc-inhietyr7209573.shtml)
- **2026-05 文心 5.1** 发布，Agent 能力提升明显 — [量子位](https://www.qbitai.com/2026/05/414496.html)
- **WAIC 2026（7 月 17–20 日）**：
  - **百度搭子**（通用智能体）：集成百度搜索 AI API、秒哒、伐谋，日提问量比上线时增长 20 倍，并发布企业版。
  - **秒哒**（无代码智能体）：聚焦增长和结果交付。
  - **伐谋**（自我演化的决策智能体）：用于生产排程和流程优化。
  - **百度一镜**（数字人智能体，原慧播星）。
  - **GenFlow 4.0**（文库、网盘）：月活超 1 亿。

  — [解放日报 2026-07-12](https://www.jfdaily.com/wx/detail.do?id=1143071)
- 百度搭子进入 QuestMobile 2026 年 9 月 AI 原生 App 月活 Top10，排第 10 — [新浪](https://www.sina.cn/weibo/detail/5356063135372162.html)（搜索摘要）

#### 华为（小艺、鸿蒙智能体框架 HMAF）
- **HDC 2026（2026 年 6 月 12 日前后）**：鸿蒙智能全面转向 Agent 架构，发布 HMAF 2.0，主打"意图即服务"；小艺与系统深度融合，定位"系统智慧大脑" — [千龙网 2026-06-12](https://china.qianlong.com/2026/0612/8682614.shtml)；[C114](https://www.c114.com.cn/news/126/a1312135.html)
- 生态数字（厂商口径）：
  - 上架鸿蒙智能体 2000 多个，精选伙伴 Skill 500 多个。
  - 小艺可调用 2100 多项系统能力，200 多项系统级数据接入其上下文。
  - AI 子系统累计开放 20 多项能力，日调用 36.8 亿次。
  - 协议：A2A 升级后支持端侧直连（腾讯视频已接入），兼容 MCP，并提出 A2UI。
  - "天工计划"（2025 年启动，投入 10 亿元）目标孵化 10000 多个 AI 元服务、1000 多个意图框架及 MCP、5000 多个 Agent。
  - "小艺 Claw"获信通院认证。

  — [爱范儿 2026-06-14](https://www.ifanr.com/1668931)
- 复杂任务成功率超 90%（厂商口径）；HarmonyOS 7 属于 2026 年各厂商密集推出的新系统之一 — [蓝鲸新闻/网易 2026-09-21](https://www.163.com/dy/article/L7C1HESD05198R91.html)

### Inferences
- **平台层已从"搭建工具"转向"运行与治理"**：AgentCore 的断点恢复和审计、Agent Sandbox、ADP 4.0 的 Skill 安检和 AgentOps、火山 AI Trust、钉钉悟空的权限继承和沙箱，指向同一个结论：企业买单的是可控执行，不再是搭 Bot 的能力。
- **"Claw 化"是 2026 年平台形态的最大变化**：OpenClaw 热潮之后，几乎所有大厂都推出了"本地/云端常驻执行 Agent"形态，如 ArkClaw、QClaw、WorkBuddy、ADP Claw 模式、小艺 Claw，以及扣子 3.0 接入 Claude Code/Codex/OpenClaw。平台角色从"自己托管 Bot"变成"编排外部 Agent"。
- **变现仍靠 Token**：平台本身缺少独立收费披露；火山用 Token 份额、200 多家万亿 Token 客户来讲故事，阿里云卖 Token Plan 订阅。可以推断智能体平台在大厂内部主要被当作拉动 MaaS 和云消耗的入口。
- **办公协同成为企业 Agent 的第一入口**：钉钉悟空、飞书 aily、WorkBuddy、千问办公、企业微信都集中在 3–9 月发布，字节、阿里、腾讯在 To B Agent 上直接用办公软件正面竞争。

### Gaps
- 扣子空间（Coze Space）2026 年的具体进展、扣子用户/付费数据、Coze Studio/Coze Loop 开源后续均未检索到；"扣子 2.0 于 2026 年 1 月升级"只见于低权威第三方文章，未核实。
- 阿里百炼平台的智能体数和开发者数、千问办公的确切上线日期未获取；云栖细节多来自自媒体长文，建议以阿里云官方稿核对。
- 腾讯元器在 2026 年的动态未检索到；ADP 客户数和定价未披露。
- 百度心响 2026 年进展、千帆 Agent 数的后续更新、百度世界大会 2026 相关内容均未检索到（搜索额度用尽）。
- 小艺 DAU：搜索摘要称约 1.8 亿，但各来源口径和时间不一致，未核实。
- 腾讯、百度、阿里 2026 年各季度财报中与智能体相关的数字未系统检索。

---

## 二、创业公司与独立产品（Manus、Genspark、MiniMax、Kimi、智谱、阶跃等）

### Takeaway
2026 年中国背景的独立 Agent 公司走向分化。**Manus** 以约 20 亿美元卖给 Meta 后，先遭商务部审查（1 月），再被发改委限制创始人出境（据 FT），CNBC 4 月报道中国叫停交易，成为"出海搬家"模式的监管分水岭。**Genspark** 在美国 12 个月做到 2.5 亿美元 ARR（公司口径）。国内大模型公司（智谱、MiniMax 1 月港股上市；Kimi、阶跃冲刺 IPO）的收入大头来自 API/Coding 等 Token 业务，Agent 产品收入占比仍小：智谱"企业级智能体"收入只占 5.8%，MiniMax C 端付费转化率不足 1%。

### Cited Findings

#### Manus（Butterfly Effect / 蝴蝶效应）
- 背景：
  - 2022 年肖弘创立。
  - 2025-03 推出海外 AI Agent 产品。
  - 2025-04 获 Benchmark 领投 7500 万美元，估值 5 亿美元。
  - 2025-07 团队迁至新加坡，关闭国内社媒账号。
  - 海外上线 8 个月 ARR 超 1 亿美元。

  — [财新 Global 2026-01-08](https://www.caixinglobal.com/2026-01-08/china-to-review-metas-acquisition-of-ai-startup-manus-102401786.html)
- **2025-12-29** Meta 宣布收购 Manus，报道金额约 20 亿美元（另一来源称"不低于 20 亿美元"）— [财新 Global](https://www.caixinglobal.com/2026-01-08/china-to-review-metas-acquisition-of-ai-startup-manus-102401786.html)；[registrationchina](https://www.registrationchina.com/articles/meta-acquisition-of-manus/)
- **2026-01-08** 商务部宣布评估调查该交易，审查其是否符合出口管制、技术进出口和对外投资规定。中伦律师认为，部分数据分析和用户偏好学习技术可能属于限制出口类别，但 Manus 已不在中国运营，执行有难度 — [财新 Global](https://www.caixinglobal.com/2026-01-08/china-to-review-metas-acquisition-of-ai-startup-manus-102401786.html)；[CNBC 2026-01-07](https://www.cnbc.com/2026/01/07/china-reviews-metas-purchase-of-ai-startup-manus-ft-reports.html)；[国新办英文网](http://english.scio.gov.cn/pressroom/2026-01/09/content_118270474.html)；[环球时报](https://www.globaltimes.cn/page/202601/1352665.shtml)
- 据 FT（Inferred Research 2026-04-11 转述）：国家发改委对联合创始人肖弘、季逸超实施出境限制，审查这笔出售是否违反技术转让规定；文章称这是北京首次对已完成的跨境 AI 收购动用人身出行管控 — [Inferred Research](https://inferredresearch.com/analysis/china-bars-manus-founders-as-ndrc-reviews-meta-acquisition)
- **2026-04-27** CNBC 报道标题为"China blocks Meta's $2 billion takeover of AI startup Manus"；据搜索摘要，Meta 称交易"完全符合适用法律"。正文无法抓取（403），叫停的具体机关和后续处置未核实 — [CNBC](https://www.cnbc.com/2026/04/27/meta-manus-china-blocks-acquisition-ai-startup.html)
- SCMP 援引分析人士：此案可能是"中国版 CFIUS"的试金石，表明北京要加强对把公司迁往海外的 AI 创始人的监管 — [SCMP](https://www.scmp.com/tech/big-tech/article/3339335/review-meta-manus-deal-underlines-chinas-tightening-grip-ai-exports)（搜索摘要）

#### Genspark（美国 Palo Alto，CEO Eric Jing）
- **2026-06-18**：B 轮扩展 1 亿美元，投后估值 26 亿美元（3 月时为 16 亿美元）；B 轮总额 4.85 亿美元，累计融资 6.45 亿美元。公司称 2026 Q1 新增 1.5 亿美元 ARR，12 个月内从 0 做到 2.5 亿美元 ARR（公司口径）。Genspark for Business 上线 6 个月企业客户超 6000 家。2026-03 推出 Genspark Claw（端到端执行层），并任命 monday.com 前高管 Jamison Powell 为 CRO，推进企业市场 — [TechIntelPro](https://techintelpro.com/news/ai/agentic-ai/gensparkai-extends-series-b-to-485m-at-26b-valuation-appoints-cro)
- 2026-01 B 轮增至 3 亿美元时，ARR 已超 1 亿美元 — [Techleap](https://finder.techleap.nl/news/note/genspark-takes-series-b-to-300m-as-arr-passes-100m)（标题）

#### MiniMax
- 2026-01 港股上市，发行价上限 165 港元，募资约 55.4 亿港元，首日涨 109%；3-18 盘中高点 1330 港元 — [钛媒体](https://www.tmtpost.com/8121654.html)
- **2026 年上半年**：
  - 收入 1.166 亿美元，同比 +283.1%；开放平台及企业服务收入 7393 万美元（+703.1%，占 63.4%），首次超过 C 端。
  - C 端累计用户超 2.12 亿，付费转化率不足 1%。
  - 经调整净亏损 2.93 亿美元，研发投入 2.97 亿美元。
  - 8 月宣布 ARR 突破 8 亿美元（年化运行率，未审计，虎嗅质疑其算法），管理层称有信心年底达到 10 亿美元。
  - 企业和开发者客户超 200 万，约为 2025 年底的 10 倍；7 月 Token 消耗为 1 月的 20 倍。
  - M3 于 6-1 发布，API 价格较 M2.7 翻倍，约一周后宣布永久半价。

  — [钛媒体](https://www.tmtpost.com/8121654.html)；[新浪财经](https://finance.sina.com.cn/stock/relnews/hk/2026-08-26/doc-iniprytr6046923.shtml)
- 10-22 收盘 160.7 港元，跌破发行价，较 3 月历史高点最大跌幅约 88% — [虎嗅](https://www.huxiu.com/article/4899672.html)（搜索摘要）

#### 智谱（GLM / AutoGLM）
- **2026-01-08** 港股上市（02513.HK，发行价 116.1 港元）；6-22 盘中最高 2980 港元，市值破万亿元 — [凤凰网](https://finance.ifeng.com/c/8w2xJM1uWhU)
- **2026 年上半年**：
  - 收入 9.54 亿元，同比 +399.7%；开放平台及 API 收入 8.25 亿元，占 86.5%。
  - **企业级智能体收入 5556 万元**，同比 +304.4%，占总收入 5.8%；企业级通用大模型收入 6703.7 万元，同比 -54.6%。
  - MaaS 用户超 740 万；截至 8-31，MaaS ARR 按月度口径为 16 亿美元、按周度口径为 20 亿美元。
  - 期内三次涨价，API 均价 +101%。
  - GLM-5.3 号称国内首个以订阅制交付编码智能体能力的模型服务。

  — [凤凰网](https://finance.ifeng.com/c/8w2xJM1uWhU)；[腾讯新闻](https://news.qq.com/rain/a/20260902A000NP00)
- 中报收入不及预期：多家机构此前预测全年收入超 50 亿元 — [东方财富](https://finance.eastmoney.com/a/202609013861301675.html)（搜索摘要）

#### 月之暗面 Kimi
- **2026-04-20** 发布并开源 K2.6；**2026-06-03** 内测 Kimi Work，这是面向知识工作者的本地通用 Agent，可拆解任务、调用工具和浏览器、产出文档/表格/PPT。据华峰资本，4 月 ARR 超 2 亿美元 — [36氪 2026-06-08](https://www.36kr.com/p/3844092401666564)
- **2026-05** D 轮约 20 亿美元，美团龙珠领投，投后估值超 200 亿美元 — [21 世纪经济报道](https://www.21jingji.com/article/20260507/herald/6b95422e2eeccacae3176f0a4206eff7.html)
- **2026-08** 启动 G 轮（Pre-IPO），估值 500 亿美元，K3 发布后额度"骤然紧俏"；据报道最快 6 个月内赴港上市 — [腾讯新闻/科创板日报](https://news.qq.com/rain/a/20260805A0AB6300)；[IT之家](https://www.ithome.com/0/979/817.htm)（搜索摘要）
- 搜索摘要转引彭博：ARR 3 月首次破 1 亿美元，6 月达 3 亿美元。这与华峰资本"4 月 ARR 超 2 亿美元"的说法节奏不一致 — [IT之家](https://www.ithome.com/0/979/817.htm)（搜索摘要）
- Kimi K3 于 2026 年 7 月中旬发布，此后两个交易日 MiniMax 股价累跌约 25% — [钛媒体](https://www.tmtpost.com/8121654.html)

#### 阶跃星辰
- 2026-01 完成 B+ 轮，超 50 亿元；旷视创始人印奇出任董事长 — [腾讯新闻](https://news.qq.com/rain/a/20260215A06UCP00)（搜索摘要）；[财新](https://m.caixin.com/m/2026-05-08/102442074.html)
- 2026-05 将完成近 25 亿美元融资，新进产业资本华勤、龙旗、豪威、中兴，以及港投公司；已拆除红筹，2026-04-03 改制为股份公司，推进港股上市 — [财新 2026-05-08](https://m.caixin.com/m/2026-05-08/102442074.html)
- 战略为"AI+终端"。WAIC 2026 展示 STEPX Neo 和智能体原生操作系统 **Step AOS**（以个人智能体 Amoo 为入口，跨应用语义记忆，系统能力原子化）。印奇称要从"过程交互"走向"结果交互" — [腾讯新闻/雷科技 2026-07-19](https://news.qq.com/rain/a/20260719A009GB00)
- STEPX Neo 预览版走纯 API 路线，据称约 100 家合作方，包括支付宝、滴滴、美团（仅跑腿）和部分腾讯产品，不含微信 — [投资界 2026-10](https://news.pedaily.cn/202610/570372.shtml)

### Inferences
- **Manus 案改写了"中国团队 + 海外主体"的出海与退出路径**：迁往新加坡也无法规避出口管制和技术转让审查，加上创始人出境限制，后来者的海外并购退出风险大幅上升。可以推断，中国背景的 Agent 创业公司会更早决定"留在国内"还是"彻底海外化"。
- **Agent 价值大部分被模型和 Token 层拿走**：智谱、MiniMax 的增长几乎全部来自 API/开放平台，Agent 产品收入很小；而 Kimi Work、Genspark Claw 这类通用 Agent 本质上也是 Token 消耗放大器。
- **资本市场对"Agent 叙事"波动剧烈**：MiniMax 从高点下跌约 88%，智谱市值一度破万亿后回落，Kimi 估值半年涨约 6–7 倍。2027 年 IPO 窗口（Kimi、阶跃）会让估值更多由 ARR 和亏损来检验。

### Gaps
- Manus 2026 年的 ARR、目前的运营状态、交易是否已解除或被迫重组：CNBC 4 月正文未能获取，其他后续报道未检索到。
- MiniMax Agent、Kimi OK Computer/Agent 模式、智谱 AutoGLM/沉思的单独用户和收入数据均未披露或未检索到。AutoGLM 只在搜索摘要中出现一次：某 2026 年 8 月 GUI 智能体榜单上，"Open AutoGLM 76.75 分，次于 vivo 蓝心小V"，榜单来源不明，未核实。
- 面壁智能、实在智能、澜码在 2026 年的融资、收入和产品动态未检索到。
- 阶跃收入：搜索摘要称"2025 年近 5 亿元、2026 年预计 12 亿元"，未能定位原文。
- 一条搜索摘要称 Kimi"招股书显示 2025 年营收 16.99 亿元、净利润 2.78 亿元"，与 Kimi 尚未递表、且普遍亏损的事实相冲突，疑为错误信息，已排除。

---

## 三、消费级超级 App 内嵌 Agent 与 Agentic Commerce（豆包 / 千问 / 元宝 / 支付宝 / 微信等）

### Takeaway
2026 年 C 端 Agent 的主战场是**"AI 助手办事化 + 支付闭环 + 手机系统入口"**：
- **千问**：1 月接入淘宝、支付宝、高德、飞猪，春节约 60 亿元投入让 1.4 亿人首次体验 AI 购物。
- **豆包**：月活 4.19 亿（9 月，QuestMobile）断层领先；"豆包手机助手"走 GUI 路线，被 155 款 App 拒绝。
- **支付宝**：AI 付累计 3 亿笔，推出 AI 钱包、Token Pay 和"阿宝"。
- **微信**：以 A2A 授权方式有限开放（只开放发消息和通话），并开放 AI 开放平台。

春节红包战说明流量能买、留存难买：元宝 DAU 一周内从峰值回落 81%。

### Cited Findings

#### 豆包（字节）与豆包手机助手
- QuestMobile 豆包月活：2026-03 为 3.45 亿；2026-06 为 3.82 亿（同比 +172.1%，人均使用 76.7 次、143.7 分钟）；2026-09 为 4.19 亿，断层第一 — [腾讯云开发者](https://cloud.tencent.com/developer/news/3863764)；[腾讯新闻](https://news.qq.com/rain/a/20260805A0E4JF00)；[新浪](https://www.sina.cn/weibo/detail/5356063135372162.html)（搜索摘要）
- 2026 春节：豆包是央视春晚独家 AI 云合作伙伴，"豆包过年"活动 2-10 启动；DAU 峰值 1.45 亿（2-16），2-23 回落到 1.03 亿（-28.8%）；投入约 15–20 亿元，单个 DAU 成本 84.6–112.8 元 — [新浪财经 2026-03-02](https://finance.sina.com.cn/roll/2026-03-02/doc-inhprmye7983948.shtml)
- **豆包手机**：
  - 一代为努比亚 M153 工程样机（3499 元，2025-12 发售），靠读屏加模拟点击，被微信、淘宝封堵；豆包随后承诺"不碰游戏刷分、不碰金融交易、不碰竞技操作"。
  - 二代为**努比亚 NaviX Ultra**，2026 年 9 月中旬开售，优先使用 MCP/A2A，没有接口时回退到模拟点击；京东预约超 38 万，努比亚称首销日销售额破 1 亿元。

  — [投资界 2026-10](https://news.pedaily.cn/202610/570372.shtml)
- **SAEP（屏幕自动化操作声明协议）**：30 天公示期于 **2026-10-14** 结束，155 款 App 明确拒绝。按集团分：腾讯系 66、阿里系 23、快手 14、美团 11，四家合计约 73%。名单包括微信、QQ、淘宝、支付宝、美团、拼多多、小红书、DeepSeek、Kimi 等。没有拒绝的 App 将按风险分级逐步开放，拒绝的永不操作 — [虎嗅](https://www.huxiu.com/article/4898843.html)；[投资界](https://news.pedaily.cn/202610/570372.shtml)；[新浪财经](https://finance.sina.com.cn/jjxw/2026-10-14/doc-inivffth4457105.shtml)
- 目前稳定可用的只有字节系和中兴自家应用，第三方中仅携程、曹操出行等部分可用 — [投资界](https://news.pedaily.cn/202610/570372.shtml)

#### 千问 App（阿里）
- 2025-11 上线。**2026-01-15 发布 6.0**：
  - 全面接入淘宝、支付宝、淘宝闪购、飞猪、高德，上线 400 多项 AI 办事功能，可在端内完成 AI 支付。
  - 推出"任务助理"（Agent，可一次处理上百张电子发票并生成报销台账），在 App 和 Web 端定向邀测。
  - 同日宣布 C 端月活破 1 亿。

  — [甲子光年 2026-01-15](https://www.jazzyear.com/article_info.html?id=1697)；[解放日报](https://www.jfdaily.com/wx/detail.do?id=1052590)
- 阿里 FY2026 Q3 财报：2026 年 2 月千问 C 端月活超 3 亿；春节推广从 2-6 开始，到 2 月底约 1.4 亿用户通过千问的智能体功能首次体验 AI 购物 — [21 世纪经济报道 2026-03-20](https://www.21jingji.com/article/20260320/herald/feb0f236398fac8c93580ad317c01a7b.html)
- 第三方口径差异很大：QuestMobile 千问移动端月活 2026-03 为 1.65–1.66 亿、2026-06 为 1.67 亿 — [腾讯云开发者](https://cloud.tencent.com/developer/news/3863764)；[腾讯新闻](https://news.qq.com/rain/a/20260805A0E4JF00)（搜索摘要）
- 春节：投入约 60 亿元（含"30 亿大免单"）；DAU 峰值 7352 万（2-7），2-23 为 3245 万；单个 DAU 成本约 144 元；奶茶活动 5 小时 500 万单、9 小时 1000 万单 — [新浪财经](https://finance.sina.com.cn/roll/2026-03-02/doc-inhprmye7983948.shtml)
- IT之家标题："阿里千问 6 天 AI 订单量破 1.2 亿单，支付宝达成全球首个笔数过亿'AI 付'" — [IT之家](https://www.ithome.com/0/921/358.htm)（标题）
- 2026-04 千问 AI 眼镜首次 OTA，接入淘宝闪购和支付宝，上线话费充值、扫码骑车、停车缴费、点外卖等 AI 办事能力 — [电商派](https://www.pai.com.cn/p/01kn63sw5n0j6h8gcvdwb307bk)（搜索摘要）
- 千问运营主体为上海智信普惠科技；2026 年 3 月报道称"目前尚未考虑商业化"，计划年内上线国际版；吴泳铭称阿里"必须要有一个 AI 原生的 C 端超级入口" — [解放日报](https://www.jfdaily.com/wx/detail.do?id=1052590)
- 高德"扫街榜"让千问代打餐厅电话 — [甲子光年](https://www.jazzyear.com/article_info.html?id=1697)

#### 腾讯元宝 / 微信
- 元宝春节官方数据（2-18）：DAU 超 5000 万，MAU 1.14 亿；21 天迭代 159 项功能；"元宝派"社交红包玩法 — [搜狐/IT之家](https://www.sohu.com/a/988425264_211762)
- QuestMobile 口径：元宝 DAU 峰值 4054 万（2-16 除夕），2-23 仅 768.5 万（-81%），回到活动前水平；投入约 10 亿元，单个 DAU 成本 69 元 — [新浪财经](https://finance.sina.com.cn/roll/2026-03-02/doc-inhprmye7983948.shtml)
- 微信：
  - **2026-06-08** 开放"微信 AI 开放平台"，京东、美团、携程、滴滴首批接入。
  - 4 月发布用于支付接入的 AI Skill。
  - 内嵌 AI 智能体在研发中，已接入美团 AI 助手"小美"。
  - 与 WorkBuddy 联测 AI 支付，微信钱包新增"AI 专属卡"。

  — [金融界 2026-06](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)
- 腾讯总裁刘炽平（2026 Q1 财报电话会）：系统级智能体必须获得第三方应用授权，否则会挤压第三方应用的生存空间 — [新浪财经 2026-06-07](https://finance.sina.com.cn/wm/2026-06-07/doc-iniaqpeu4740245.shtml)

#### 支付宝 / 蚂蚁（Agent 支付基础设施）
- AI 付于 2025-09 上线；2026 春节期间用户数和笔数双双破亿。**2026-05-26** 宣布：
  - 累计完成 3 亿笔 AI 智能体支付。
  - 支持 95% 的通用智能体框架，包括千问、Claude Code、Hermes Agent，以及理想、奇瑞的智能座舱。
  - 发布个人"AI 钱包"和面向大模型订阅/充值的"Token Pay"。

  — [赛迪网](https://www.ccidnet.com/news/1105103.jhtml)；[移动支付网](https://m.mpaypass.com.cn/news/202605/26144313.html)；[金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)
- 后续动作：
  - 2026-03 底发布"支付集成 Skill"。
  - 2026-06-15 MiniMax M3 接入 Token Pay。
  - 2026-06-16 AI 版支付宝"阿宝"邀测上线，每月迭代两次，将同步启动 AI 开放平台。
  - 面向全球推出移动智能体协议 AMP。

  — [金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)
- OPPO 小布已接入阿宝，阿宝可调用支付宝内近 200 项服务，账号和支付信息留在各自的可信系统中 — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)
- 蚂蚁阿福位列 QuestMobile 2026 年 9 月 AI 原生 App 月活第 5（前十依次为豆包、千问、DeepSeek、元宝、蚂蚁阿福等）— [新浪](https://www.sina.cn/weibo/detail/5356063135372162.html)（搜索摘要）

#### 行业整体
- 春节大战：阿里、腾讯、字节合计投入约 90 亿元，DataEye 估计所有 AI 产品节前后的投放超 100 亿元。QuestMobile 数据显示，2025-12 到 2026-01 通用 AI App 月人均使用时长增长 22.3% — [新浪财经](https://finance.sina.com.cn/roll/2026-03-02/doc-inhprmye7983948.shtml)
- QuestMobile：2026 Q1 AI 原生 App 月活规模 4.4 亿；DeepSeek 6 月月活 1.30 亿，同比下降 20.3% — [腾讯云开发者](https://cloud.tencent.com/developer/news/3863764)；[腾讯新闻](https://news.qq.com/rain/a/20260805A0E4JF00)（搜索摘要）

### Inferences
- **三种 C 端 Agent 路线已经成形**：
  - 阿里"前店后厂"：千问做"店"，淘宝、闪购、飞猪、高德、支付宝做"厂"，在自家生态内闭环，没有跨公司授权问题。
  - 字节"系统级 GUI Agent"：靠豆包手机抢 OS 入口，但被腾讯、阿里、美团、快手系集体拒绝。
  - 腾讯"授权式 A2A + 开放平台"：微信只开放低风险动作，同时通过 AI 开放平台把服务方拉进来。
- **GUI 模拟点击在中国的商业可行性基本被平台方否决**：SAEP 拒绝名单加上二代机"优先 MCP/A2A"，说明 2027 年手机 Agent 的主路径会转向 API/协议授权，GUI 只做兜底。
- **支付是 Agent 商业闭环最硬的基础设施**：支付宝在 AI 付、AI 钱包、Token Pay、AMP 上先发，微信用"AI 专属卡"跟进，"Agent 替人花钱"已进入规模化（3 亿笔）阶段。
- 补贴拉新的单个 DAU 成本是常规 App 的 7–14 倍，留存差异很大。豆包的粘性优势说明，C 端 Agent 的胜负取决于高频刚需场景，不在补贴强度。

### Gaps
- 淘宝/天猫自有 AI 购物 Agent（千问之外）、美团"小美"的用户数和订单数、高德 Agent 数据未检索到；"美团发布跑腿 Skill"只见于搜索摘要。
- 豆包 App 内 Agent 功能（如任务/办事类）在 2026 年的具体更新、豆包 DAU 的最新数据未核实。
- 文心助手、百度 App 的 AI 用户数，以及元宝 9 月月活的具体数值未获取。
- 千问 3 亿 MAU（阿里全端口径）与 QuestMobile 1.6 亿级（移动端口径）差距接近一倍，具体统计口径不明。

---

## 四、生态与协议：MCP / A2A / Skills / 国家标准 / OS 与手机 Agent

### Takeaway
2026 年中国 Agent 生态在协议层快速补课，分两条线：
- **事实标准被全面兼容**：MCP、A2A、Skills、OpenClaw 生态被各大厂接入。
- **国家层面另起治理框架**：6 月发布 GB/Z 185《人工智能 智能体互联》7 部分指导性标准，重点是身份码、能力描述、发现、交互和工具调用；信通院发起 ATH 握手协议；AIP 互联协议声称兼容 MCP/A2A。

终端侧，HarmonyOS 7/HMAF 2.0、荣耀 Agentic OS、vivo 蓝心 Harness 让"系统级 Agent"成为手机标配。年度焦点是 **GUI 模拟点击与"App 授权 + A2A/API"两条路线之争**。

### Cited Findings

#### OpenClaw"养龙虾"热潮与 Skills 生态
- 2026 年 2–3 月 OpenClaw（"龙虾"）爆火：阿里云、腾讯云、火山引擎（ArkClaw）、华为云、京东云、百度智能云都推出了一键部署方案 — [搜狐汇总](https://www.sohu.com/a/996661629_121124363)；[codepick](https://codepick.dev/zh/practices/openclaw-cloud-deploy/)
- 工信部和国家互联网应急中心就 OpenClaw 默认配置的风险发出警示 — [每日经济新闻](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)
- Skills 成为新的分发单位：
  - 腾讯 SkillHub 收录 8 万多个 Skills，WorkBuddy 兼容 ClawHub — [网易号选型文](https://www.163.com/dy/article/L21DS91E0556BHK5.html)
  - 腾讯云 ADP 沉淀 130 多个企业 Skills — [腾讯云开发者社区](https://cloud.tencent.com/developer/article/2685456)
  - 华为有 500 多个伙伴 Skill，系统应用全面 Skill 化 — [爱范儿](https://www.ifanr.com/1668931)
  - 支付宝"支付集成 Skill"（3 月底）、微信支付 AI Skill（4 月）— [金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)

#### MCP / A2A 在中国
- 背景（2025-10-28）：国家数据局综合司方案支持标准化 MCP 接口，用于安全接入、跨系统调用和流程自动化 — [CERNET](https://www.cernet.edu.cn/xxh/focus/zc/202605/t20260528_2738385.shtml)
- 阿里云百炼"One Key MCP"：一个 API Key 连接 100 多项生态服务（云栖，2026-09）— [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
- 鸿蒙兼容 MCP；A2A 支持端侧直连（腾讯视频已接入）— [爱范儿](https://www.ifanr.com/1668931)
- **微信与华为、荣耀、小米、OPPO、vivo 推出 A2A 助手（2026-06）**：经 App 授权后通过 API 调用服务，不再读屏和模拟点击；只开放发消息和音视频通话，不能发朋友圈或红包；每次操作前需用户确认。6-5 实测只有荣耀 YOYO 能用，OPPO、vivo 提示当前微信 8.0.72 版本不支持 — [新浪财经 2026-06-07](https://finance.sina.com.cn/wm/2026-06-07/doc-iniaqpeu4740245.shtml)
- 微信正与多家手机厂商推进合作：手机助手可把发消息、打微信电话等结构化任务交给微信"小微"执行 — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)
- 支付宝面向全球推出移动智能体协议 AMP — [金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)

#### 国家标准与信通院
- **GB/Z 185—2026《人工智能 智能体互联》系列**：
  - 发布：据搜索摘要，2026-06-26 由市场监管总局、国标委发布 — [知乎](https://zhuanlan.zhihu.com/p/2072598967448294131)（搜索摘要）
  - 组织：工信部指导，中国电子技术标准化研究院组织，70 余家企业参与 — [21 世纪经济报道 2026-07-03](https://m.21jingji.com/article/20260703/herald/13dad377fc6c2b19fa03ad468af19f1b.html)
  - 7 个部分：总体架构；身份码编码、分配与管理；身份注册、账户、凭证和鉴别；能力描述及其注册、发布与变更；发现流程；交互模式（点对点、群组、混合）；外部工具调用的架构、流程和数据格式。一个身份码对应一个智能体 — [21 世纪经济报道](https://m.21jingji.com/article/20260703/herald/13dad377fc6c2b19fa03ad468af19f1b.html)
- 口径冲突：
  - 网易报道称公告批准的是 8 项国家标准化指导性技术文件，百余家头部企业参与倡议，50 多家企业正在试点；市场监管总局标准技术司副司长朱美娜称要解决智能体"信息孤岛"问题 — [网易 2026-06-30](https://c.m.163.com/news/a/L0LMEEBN0550B1DU.html)
  - 新浪称由中国电子标准院牵头，华为、阿里、浪潮、清华等 30 余家单位制定 — [新浪](https://www.sina.cn/news/detail/5314864786706665.html)（搜索摘要）
  - 结论：参与单位数（30 余家 / 70 余家）和文件数（7 / 8）各报道不一致。
- 中国信通院于 2026 年发起智能体可信握手协议 **ATH**；**AIP**（智能体互联协议）明确兼容 MCP 和 A2A，定位是补齐身份、安全、治理，不另起炉灶 — [网易](https://c.m.163.com/news/a/L0LMEEBN0550B1DU.html)
- GB/Z 185 第一轮评测已启动 — [知乎](https://zhuanlan.zhihu.com/p/2072598967448294131)（标题）

#### 手机 / OS 级 Agent
- **荣耀**：MagicOS 升级为"伙伴型多模态智能体操作系统 Agentic OS"，采用与阿里共同研发的 Magic 智能体大模型矩阵；Robot Phone 预计 2026-08 发布，后续上线智能体能力 — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)。新一代 YOYO 支持执行 100 步以上的任务；CEO 李健称 MagicOS 11 要融合"自动执行"和"主动服务" — [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)
- **vivo** 蓝心 Harness：把 6000 多项手机原子能力转成 Agent 可调用的工具，支持 10000 多类任务 — [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)
- **OPPO** 小布接入支付宝阿宝；**小米**下一代系统传闻将进化为 AgentOS（无细节）— [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)
- 2026-07，7 款端侧生成式 AI 服务完成备案：Apple 智能、华为小艺、OPPO AndesGPT、vivo 蓝心、小米澎湃 AI、三星盖乐世 AI、努比亚豆包手机大模型 — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)
- IDC：2026 年中国新一代 AI 手机预计 1.47 亿部，首次超过出货量的一半；中国 2026 年手机出货约 2.78 亿部（-2.2%）— [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)
- 2026-04-30 广州互联网法院的判决认可"用户与应用方双重授权"原则，但业内认为这只解决了访问问题，没有解决责任问题，控制标准仍缺失 — [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)
- 调度权之争：业内人士认为真正的竞争在生态控制权；有厂商高管称，Agent 可以让手机厂从卖硬件转向卖服务或订阅 — [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)

### Inferences
- **中国 Agent 协议格局是"国际事实标准 + 国内治理层"**：MCP、A2A、Skills 解决连接问题，GB/Z 185 和 AIP/ATH 主要解决身份、注册、发现和追溯，偏监管可控。2027 年企业和政务采购很可能把"身份码/注册"列为准入条件。
- **"授权"正在成为新的平台权力**：微信只开放低风险动作，SAEP 拒绝名单，以及刘炽平"必须获得第三方授权"的表态，说明超级 App 正把"是否允许 Agent 操作"变成议价筹码。手机厂、AI 助手和超级 App 之间的接口协议会成为 2027 年的核心谈判对象。
- **Skills 和 Claw 生态可能复制小程序和插件的分发逻辑**：SkillHub 有 8 万多个 Skills，华为有 500 多个伙伴 Skill，支付宝和微信也做了支付 Skill，说明能力封装的单位正在从"App/小程序"转向"Skill"。

### Gaps
- 魔搭 ModelScope MCP 广场、阿里云百炼 MCP 广场、腾讯云和字节 MCP 市场在 2026 年的服务数和调用量未检索到。
- 信通院 ATH 协议的具体内容和发布时间、AIP 的标准状态未核实。
- 小米、OPPO 具体 Agent 产品（超级小爱、小布）的 2026 能力参数，以及荣耀 MagicOS 11 的发布日期，来源说法不一。
- A2A 在企业侧的采用数据缺失。

---

## 五、关键趋势与争论：通用 vs 垂直、出海、企业落地难点、定价、政策

### Takeaway
2026 年的五个主题：
- **企业落地**：仍处早期，IDC 测得企业业务渗透率 18%，62% 的企业把数据权限与合规列为首要障碍；竞争从功能展示转向"可复用的业务闭环"。
- **定价**：Token 价格从 2024–25 年的价格战转为 2026 年上涨（摩根士丹利称 API 输出价格涨约 80%），订阅化（Token Plan、Coding 订阅）兴起，按结果计费被 IDC 视为方向。
- **政策**：网信办等三部门 5 月发布首份智能体专项文件（可控、可审计、可追责）。
- **出海**：受 Manus 案影响，出海退出路径明显收紧。
- **通用 vs 垂直**：通用 Agent 以"Claw/桌面执行"形态普及，企业收入则集中在问数、审核、报告、月结等垂直闭环场景。

### Cited Findings

#### 企业级 Agent 落地：数据、私有化、ROI、可靠性
- IDC（2026-05，对《实施意见》的解读）：
  - 智能体在企业业务中的渗透率仅 18%。
  - 62% 的企业把数据权限与安全合规列为跨系统执行的首要障碍；58.7% 的企业把治理与合规放在平台引入目标的首位。
  - 2026、2027 年将是企业活跃智能体数量增长最快的两年，单年同比超 200%；到 2031 年达 3.5 亿个，2026–2031 CAGR 135.3%。

  — [IDC 博客](https://www.idc.com/resource-center/blog/idc%E6%B4%9E%E5%AF%9F%EF%BC%9A%E6%94%BF%E7%AD%96%E4%B8%8E%E5%B8%82%E5%9C%BA%E5%85%B1%E6%8C%AF-%E3%80%8A%E6%99%BA%E8%83%BD%E4%BD%93%E5%AE%9E%E6%96%BD%E6%84%8F%E8%A7%81%E3%80%8B/)
- 转述 IDC：2025 年中国企业活跃智能体接近 200 万，2026 年预计 500 万（与上条 CAGR 推算的量级一致）— [奥哲](https://www.authine.com/hangye/1773.html)（搜索摘要）
- IDC MarketScape（2026-09，中国 ERM 领域 AI Agent 厂商评估）：
  - 竞争正从功能展示转向可落地、可复用的业务闭环；较成熟的场景集中在问数、审核、报告和月结。
  - 私有化部署和信创适配加速渗透，但纯私有化能力尚未全面落地。
  - 商业模式从软件许可转向"席位订阅 + 算力消耗 + 项目服务"。
  - 未来两年，"低风险流程自动闭环、高风险决策人机协同"将成为主流治理模式。

  — [IDC 博客](https://www.idc.com/resource-center/blog/idc-marketscape%E6%9C%80%E6%96%B0%E8%AF%84%E4%BC%B0%EF%BC%9A%E4%BC%81%E4%B8%9A-ai-agent-%E7%9A%84%E7%AB%9E%E4%BA%89%EF%BC%8C%E6%AD%A3%E4%BB%8E%E5%8A%9F%E8%83%BD%E5%B1%95%E7%A4%BA%E8%BD%AC%E5%90%91/)
- IDC FutureScape 2026（2026-01-27）预测：
  - 到 2027 年，没有优先建设 AI 就绪数据的企业，扩展 AI 时生产力将下降 15%。
  - 到 2028 年，69% 的企业自建智能体项目会因 ROI 未达标而被放弃。
  - 到 2026 年，中国 500 强企业 40% 的岗位将与智能体深度协作。
  - 到 2030 年，最多 20% 的中国 500 强企业可能因智能体管控不力引发高关注度事件。

  — [IDC 博客](https://www.idc.com/resource-center/blog/%E8%AD%A6%E6%83%95%E7%94%9F%E4%BA%A7%E5%8A%9B%E5%80%92%E9%80%80%EF%BC%8Cidc-futurescape-2026%E6%99%BA%E8%83%BD%E4%BD%93%E5%8D%81%E5%A4%A7%E9%A2%84%E6%B5%8B%E5%8F%91%E5%B8%83/)
- 市场规模（待核实）：第三方转引 IDC 口径，企业级狭义智能体市场 2025 年约 212 亿元，2026 年约 449 亿元，2029 年约 3320 亿元；另一份报告给出 2025 年 182–232 亿元。未见 IDC 原文 — [clawpk 研究](https://clawpk.net/research/R-INDUSTRY-12-china-enterprise-agent-2026)（搜索摘要）
- 私有化部署在模型厂商收入中萎缩：智谱本地化部署收入占比从 70% 以上降到 13.5%，上半年收入 1.62 亿元（-20.5%）— [凤凰网](https://finance.ifeng.com/c/8w2xJM1uWhU)；[东方财富](https://finance.eastmoney.com/a/202609013861301675.html)（搜索摘要）
- 协同办公被视为企业 Agent 最容易落地的入口（盘和林观点）；记者实测飞书 aily 时出现内容重复推送等不稳定现象 — [每日经济新闻](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)

#### 定价与变现
- **Token 价格反转上涨**：摩根士丹利称，2026 Q2 中国大模型 API 价格比 2025 Q1 输入上涨约 48%、输出上涨约 80%；智谱期内三次涨价，API 均价 +101% — [凤凰网](https://finance.ifeng.com/c/8w2xJM1uWhU)
- MiniMax M3 先涨价一倍，约一周后改为"永久半价" — [钛媒体](https://www.tmtpost.com/8121654.html)；豆包 2.1 Pro 每百万 tokens 输入 6 元、输出 30 元 — [SegmentFault](https://segmentfault.com/a/1190000047897953)
- 订阅化：
  - 阿里云百炼 Token Plan 订阅覆盖多家模型 — [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
  - 智谱 GLM-5.3 以订阅制交付编码智能体 — [腾讯新闻](https://news.qq.com/rain/a/20260902A000NP00)
  - 支付宝 Token Pay 支持企业"批量购买、一键分发" Token 席位 — [金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)
- IDC 预测：到 2028 年，70% 的软件供应商需转向按业务结果、交易量或自动化成果计费 — [IDC FutureScape](https://www.idc.com/resource-center/blog/%E8%AD%A6%E6%83%95%E7%94%9F%E4%BA%A7%E5%8A%9B%E5%80%92%E9%80%80%EF%BC%8Cidc-futurescape-2026%E6%99%BA%E8%83%BD%E4%BD%93%E5%8D%81%E5%A4%A7%E9%A2%84%E6%B5%8B%E5%8F%91%E5%B8%83/)
- C 端变现仍弱：千问"尚未考虑商业化"（2026-03）— [解放日报](https://www.jfdaily.com/wx/detail.do?id=1052590)；MiniMax C 端付费转化率不足 1% — [钛媒体](https://www.tmtpost.com/8121654.html)

#### 政策（"人工智能+"与智能体专项）
- 背景：国发〔2025〕11 号（2025-08-26）提出，到 2027 年新一代智能终端、智能体等应用普及率超 70%，2030 年超 90% — [人民网](http://finance.people.com.cn/n1/2025/0826/c1004-40550585.html)；[CERNET](https://www.cernet.edu.cn/xxh/focus/zc/202605/t20260528_2738385.shtml)
- **2026-05-08 国家网信办、国家发展改革委、工业和信息化部联合印发《智能体规范应用与创新发展实施意见》**：
  - 这是国家层面首份智能体专项规范性文件。
  - 把智能体定义为"具备自主感知、记忆、决策、交互与执行能力的智能系统"。
  - 要求做到可控、可审计、可追责。

  — [CERNET](https://www.cernet.edu.cn/xxh/focus/zc/202605/t20260528_2738385.shtml)。IDC 解读该文件的其他内容：
  - 围绕科学研究、产业发展、提振消费、民生福祉、社会治理五大方向，打造 19 个典型场景。
  - 安全治理覆盖决策权限、行为管控、供应链安全和分类分级。
  - 推进智能体互联协议 AIP，探索注册平台、软件商店和供需信息发布平台。

  — [IDC 博客](https://www.idc.com/resource-center/blog/idc%E6%B4%9E%E5%AF%9F%EF%BC%9A%E6%94%BF%E7%AD%96%E4%B8%8E%E5%B8%82%E5%9C%BA%E5%85%B1%E6%8C%AF-%E3%80%8A%E6%99%BA%E8%83%BD%E4%BD%93%E5%AE%9E%E6%96%BD%E6%84%8F%E8%A7%81%E3%80%8B/)
- 背景（2025-12-25）：工信部等八部门《"人工智能+制造"专项行动实施意见》提出打造 1000 个高水平工业智能体、100 个高质量行业数据集。2026-04-28：工信部办公厅、国家数据局综合司部署"模数共振"行动，面向高价值场景打造专用模型和特色智能体，共建"智能体工厂" — [CERNET](https://www.cernet.edu.cn/xxh/focus/zc/202605/t20260528_2738385.shtml)
- 备案：2026-07 有 7 款端侧生成式 AI 服务完成备案（见第四部分）— [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)

#### Agent 出海
- Manus 案（见第二部分）：迁往新加坡之后仍被商务部审查，发改委限制创始人出境，CNBC 报道交易被叫停 — [财新 Global](https://www.caixinglobal.com/2026-01-08/china-to-review-metas-acquisition-of-ai-startup-manus-102401786.html)；[CNBC](https://www.cnbc.com/2026/04/27/meta-manus-china-blocks-acquisition-ai-startup.html)
- 大厂和模型公司以"国内主体 + 国际版"方式出海：
  - 扣子 3.0 称"全球上线" — [新浪财经](https://finance.sina.com.cn/wm/2026-06-03/doc-inhzzyte2869078.shtml)
  - 阿里推进 Qwen Work 国际版，未来 12 个月新增土耳其、芬兰、荷兰云地域 — [每日商报](https://hzdaily.hangzhou.com.cn/mrsb/2026/09/24/article_detail_3_20260924A116.html)
  - 腾讯云 ADP 4.0 海外版 — [ai-equal](https://ai-equal.com/tools/adp)（搜索摘要）
  - 千问计划年内上线国际版 — [解放日报](https://www.jfdaily.com/wx/detail.do?id=1052590)
- Genspark 以美国公司身份推进企业市场，在 Microsoft、Google Cloud、Gemini Enterprise 等渠道上架 — [TechIntelPro](https://techintelpro.com/news/ai/agentic-ai/gensparkai-extends-series-b-to-485m-at-26b-valuation-appoints-cro)

#### 通用 Agent vs 垂直 Agent
- 通用 Agent 的 2026 年形态是"桌面/云端执行 + 办公交付"：Kimi Work（6 月）、WorkBuddy（3 月）、QClaw（3 月）、Genspark Claw（3 月）、百度搭子（日提问量增长 20 倍）、千问"任务助理"— [36氪](https://www.36kr.com/p/3844092401666564)；[网易号选型文](https://www.163.com/dy/article/L21DS91E0556BHK5.html)；[新浪财经](https://finance.sina.com.cn/stock/t/2026-03-09/doc-inhqknrq6967657.shtml)；[TechIntelPro](https://techintelpro.com/news/ai/agentic-ai/gensparkai-extends-series-b-to-485m-at-26b-valuation-appoints-cro)；[解放日报](https://www.jfdaily.com/wx/detail.do?id=1143071)；[甲子光年](https://www.jazzyear.com/article_info.html?id=1697)
- 垂直和行业 Agent 有政策目标与成熟场景支撑："1000 个工业智能体"、"特色智能体/智能体工厂"、百度"伐谋"做生产排程、IDC 认定较成熟的问数/审核/报告/月结场景 — [CERNET](https://www.cernet.edu.cn/xxh/focus/zc/202605/t20260528_2738385.shtml)；[解放日报](https://www.jfdaily.com/wx/detail.do?id=1143071)；[IDC MarketScape](https://www.idc.com/resource-center/blog/idc-marketscape%E6%9C%80%E6%96%B0%E8%AF%84%E4%BC%B0%EF%BC%9A%E4%BC%81%E4%B8%9A-ai-agent-%E7%9A%84%E7%AB%9E%E4%BA%89%EF%BC%8C%E6%AD%A3%E4%BB%8E%E5%8A%9F%E8%83%BD%E5%B1%95%E7%A4%BA%E8%BD%AC%E5%90%91/)
- 阶跃认为现有智能体有三个问题：应用之间记忆不互通、单一模型难以完成复杂决策、独立 App 拿不到系统和其他服务的调用权，因此主张从"过程交互"转向"结果交互" — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)

### Inferences
- **"通用 vs 垂直"在中国更像"入口 vs 闭环"的分工**：通用 Agent（豆包、千问、Kimi Work、WorkBuddy）争的是用户意图入口和 Token 消耗；企业愿意付费的是垂直闭环（财务月结、审核、排产），这部分大量由私有化、信创和行业 ISV 承接。2027 年大概率继续是"通用入口 + 垂直 Skill/子 Agent"的组合架构。
- **定价从"卷低价"转向"卷价值"**：Token 涨价、订阅化、按结果计费三条线同时出现，说明需求（Agent 长任务、Coding）已经压过供给。对 Agent 工具厂商来说，成本端的不确定性在上升。
- **政策是"促进 + 规范"双轨**：既有 2027 年 70% 普及率的硬目标，又有可控、可审计、可追责和身份码标准，合规能力（审计、权限、回滚）会成为 To G/To B 招标的硬门槛。
- **出海分化**：中国大厂以国内主体输出国际版（受监管认可），独立创业公司"迁出再卖"的路径被 Manus 案堵住。

### Gaps
- 中国本土 Agent 产品的具体价格（扣子会员/企业版、钉钉悟空、飞书 aily、WorkBuddy 收费）在可得来源中均未披露。
- 沙丘智库、艾瑞、中国信通院 2026 年智能体报告未检索到（搜索额度用尽）；IDC 企业级智能体市场规模原始数字未核实。
- "人工智能+"70% 普及率的统计口径和考核办法未见官方说明。
- 生成式 AI 备案在 2026 年针对 Agent 的新要求（如是否单独备案智能体）未检索到。

---

## 六、2027 年信号与既定计划

### Takeaway
已明确的 2027 信号集中在六方面：
- **政策**：2027 年智能体普及率超 70%。
- **标准**：GB/Z 185 落地，智能体身份码和注册平台推进。
- **企业侧**：IDC 预计 2026–2027 年企业活跃智能体单年增长超 200%，2027 年 45% 的企业将管理多智能体系统。
- **终端侧**：AI 手机首次过半，HarmonyOS 7、荣耀 Robot Phone、Qwen Book 12 月首批体验，小米 AgentOS 为传闻。
- **支付和开放平台**：阿宝、微信 AI 开放平台扩大开放。
- **资本**：Kimi、阶跃冲刺港股，MiniMax 定下年底 10 亿美元 ARR 目标。

### Cited Findings
- 政策目标：到 2027 年新一代智能终端、智能体等应用普及率超 70% — [人民网](http://finance.people.com.cn/n1/2025/0826/c1004-40550585.html)
- IDC：2026、2027 年企业活跃智能体单年同比增长超 200%；到 2027 年，45% 的企业将管理跨渠道、应用和供应商的多智能体系统；50% 的 AI 驱动型企业应用部署将设立监督智能体的新岗位；建立成熟 AI/智能体卓越中心的企业，在创新、速度和服务质量上比竞争对手高 20% — [IDC 实施意见解读](https://www.idc.com/resource-center/blog/idc%E6%B4%9E%E5%AF%9F%EF%BC%9A%E6%94%BF%E7%AD%96%E4%B8%8E%E5%B8%82%E5%9C%BA%E5%85%B1%E6%8C%AF-%E3%80%8A%E6%99%BA%E8%83%BD%E4%BD%93%E5%AE%9E%E6%96%BD%E6%84%8F%E8%A7%81%E3%80%8B/)；[IDC FutureScape](https://www.idc.com/resource-center/blog/%E8%AD%A6%E6%83%95%E7%94%9F%E4%BA%A7%E5%8A%9B%E5%80%92%E9%80%80%EF%BC%8Cidc-futurescape-2026%E6%99%BA%E8%83%BD%E4%BD%93%E5%8D%81%E5%A4%A7%E9%A2%84%E6%B5%8B%E5%8F%91%E5%B8%83/)
- IDC MarketScape：未来两年"低风险流程自动闭环、高风险决策人机协同"将成为主流 — [IDC](https://www.idc.com/resource-center/blog/idc-marketscape%E6%9C%80%E6%96%B0%E8%AF%84%E4%BC%B0%EF%BC%9A%E4%BC%81%E4%B8%9A-ai-agent-%E7%9A%84%E7%AB%9E%E4%BA%89%EF%BC%8C%E6%AD%A3%E4%BB%8E%E5%8A%9F%E8%83%BD%E5%B1%95%E7%A4%BA%E8%BD%AC%E5%90%91/)
- 智能体互联国标的影响：业内预计 3–6 个月后在终端产品层面出现较真实的影响；光大证券认为从标准试点到业绩确认约需半年到一年，基础设施和中间件环节先受益 — [网易](https://c.m.163.com/news/a/L0LMEEBN0550B1DU.html)。《实施意见》要求探索智能体注册平台、软件商店和供需信息发布平台 — [IDC](https://www.idc.com/resource-center/blog/idc%E6%B4%9E%E5%AF%9F%EF%BC%9A%E6%94%BF%E7%AD%96%E4%B8%8E%E5%B8%82%E5%9C%BA%E5%85%B1%E6%8C%AF-%E3%80%8A%E6%99%BA%E8%83%BD%E4%BD%93%E5%AE%9E%E6%96%BD%E6%84%8F%E8%A7%81%E3%80%8B/)
- 阿里：
  - Qwen Book 2026 年 12 月开始首批体验 — [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
  - 吴泳铭计划训练 5–10T 参数的新模型 — [网易号长文](https://m.163.com/dy/article/L815ECR90511NEUN.html)
  - 五年内云和 AI 年收入超 1000 亿美元 — [每日经济新闻](https://www.nbd.com.cn/articles/2026-03-21/4302415.html)
  - 未来 12 个月新增海外云地域 — [每日商报](https://hzdaily.hangzhou.com.cn/mrsb/2026/09/24/article_detail_3_20260924A116.html)
- 支付宝"阿宝"将逐步向全量用户开放，并同步启动 AI 开放平台 — [金融界](https://m.jrj.com.cn/madapter/finance/2026/06/16120857482949.shtml)；微信表示其他厂商的 A2A 适配后续跟进，未给时间表 — [新浪财经](https://finance.sina.com.cn/wm/2026-06-07/doc-iniaqpeu4740245.shtml)
- 华为"天工计划"目标孵化 5000 多个 Agent、10000 多个 AI 元服务 — [爱范儿](https://www.ifanr.com/1668931)；荣耀 Robot Phone 后续上线感知、决策、执行等智能体能力，小米下一代系统传闻进化为 AgentOS — [腾讯新闻/雷科技](https://news.qq.com/rain/a/20260719A009GB00)
- IDC：2026 年中国 AI 手机预计 1.47 亿部，首次过半，系统级 Agent 的装机基础在 2027 年将继续扩大 — [蓝鲸新闻/网易](https://www.163.com/dy/article/L7C1HESD05198R91.html)
- 豆包 SAEP：没有拒绝的 App 将按风险分级逐步开放操作权限 — [投资界](https://news.pedaily.cn/202610/570372.shtml)
- 资本：
  - Kimi G 轮估值 500 亿美元，据报道最快 6 个月内赴港 — [IT之家](https://www.ithome.com/0/979/817.htm)（搜索摘要）
  - 阶跃已改制，推进港股 — [财新](https://m.caixin.com/m/2026-05-08/102442074.html)
  - MiniMax 管理层有信心年底 ARR 达 10 亿美元 — [钛媒体](https://www.tmtpost.com/8121654.html)
- IDC 的 2028 年预测为 2027 年规划提供了方向：69% 的企业自建 Agent 项目会因 ROI 被放弃，70% 的软件商转向按结果计费 — [IDC FutureScape](https://www.idc.com/resource-center/blog/%E8%AD%A6%E6%83%95%E7%94%9F%E4%BA%A7%E5%8A%9B%E5%80%92%E9%80%80%EF%BC%8Cidc-futurescape-2026%E6%99%BA%E8%83%BD%E4%BD%93%E5%8D%81%E5%A4%A7%E9%A2%84%E6%B5%8B%E5%8F%91%E5%B8%83/)

### Inferences
- **2027 年中国 Agent 工具层可能的六条主线**（基于以上信号推断）：
  1. 手机和超级 App 之间形成**授权协议化的 A2A/API 接口**（微信、支付宝、鸿蒙模式），GUI 模拟点击退居兜底。
  2. 企业采购从"平台"转向 **AgentOps/治理/审计**，身份码和注册平台成为合规前提。
  3. **Skills/Claw 生态**成为主要分发单位，大厂各自的 Skill 市场之间开始竞争。
  4. **定价**从 Token 计费走向"订阅 + 按结果"的混合模式，Token 成本上行会挤压 Agent 应用毛利。
  5. **办公入口**（钉钉、飞书、企微/WorkBuddy、千问办公）决出企业 Agent 的第一梯队。
  6. 上市公司（智谱、MiniMax、拟上市的 Kimi、阶跃）会受到 ARR 兑现和亏损的约束，Agent 叙事需要用收入证明。
- 2027 年 70% 普及率目标会拉动政务、国企和制造业的智能体项目（如工业智能体、智能体工厂），利好私有化和信创厂商（如 HiAgent、ADP 私有化），但 IDC 的 ROI 放弃率预测提示泡沫风险。

### Gaps
- 字节、腾讯、百度没有检索到明确的 2027 年 Agent 路线图；百度世界大会 2026、腾讯全球数字生态大会 2026 的内容未覆盖（搜索额度用尽）。
- 2027 年 70% 普及率目标的中期评估或统计口径没有官方数据。
- 没有找到中国本土机构（信通院、沙丘智库、艾瑞）对 2027 年智能体市场规模的预测。
