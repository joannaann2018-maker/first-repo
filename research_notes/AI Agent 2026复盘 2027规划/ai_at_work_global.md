# AI at work（全球，不含中国）：2026年1–10月复盘与2027年方向

> 研究截止日：2026-10-23。所有事实均标注月份/年份；2025年内容仅作背景并注明"背景"。"（二手）"=来自媒体/聚合站转述、未能打开一手原文；"（搜索摘要）"=仅见于搜索结果摘要、原页面未能打开（403/503）；"（厂商自述）"=厂商自测或自报、无第三方验证。注：本轮研究中途共享 WebSearch 额度用尽，之后仅对已获得的 URL 做一手抓取核实，部分问题因此留在 Gaps。

## 1. 主要产品与2026年轨迹（发布时间、席位/用户、定价变化、变现）

### Takeaway
2026年工作场景AI的主线是"从席位制助手/聊天，走向可委派、长时运行、按用量计费的智能体（Cowork / Autopilot / Dots / Custom Agents）"。Microsoft 365 Copilot 付费席位从1月的1500万翻倍至7月的3000万+（仍仅约占4.5亿+商业席位的6–7%），并推出 $99 的 E7 与 $15 的 Agent 365；Anthropic 借 Claude Cowork/Claude Code 成为企业侧增长最快的厂商（run-rate 从2025年底约$90亿升至2026年5月$470亿+），其技术被 Microsoft 直接嵌入 Copilot Cowork；Google 称 Gemini Enterprise 售出800万+席位、近90% Fortune 100 在用；OpenAI 以常驻智能体 Dots 与插件生态主攻；Salesforce Agentforce ARR 超$15亿。几乎所有厂商都在2026年引入 credits/consumption 计费。

### Cited Findings

#### Microsoft 365 Copilot / Copilot Chat / Agent 365 / E7
- **席位轨迹**：FY26 Q2 财报会（2026-01-28）披露 M365 Copilot 付费席位 1500万；同季 M365 商业付费席位超4.5亿，No Jitter 自算付费渗透率约3.3%；Copilot Chat 仅称"企业聊天用户是付费席位的数倍"、未给数字 — [No Jitter, 2026-02-03](https://www.nojitter.com/ai-automation/microsoft-365-copilot-hits-15-million-paid-seats)
- 2026-03-09 微软官方博客：付费 Copilot 席位同比增长160%+，日活使用增长10倍，部署超过35,000席的客户同比增至3倍；90% 的 Fortune 500 使用 Copilot，80% 的 Fortune 500 已在使用微软智能体；Agent 365 Registry 预览两个月即登记"数千万"智能体；微软内部可见50万+个智能体 — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)
- FY26 Q3（2026-04-29）：付费席位超2000万；拥有5万席以上的客户同比增至4倍；微软AI业务年化收入超$370亿（+123%）；2026日历年资本开支预计约$1900亿 — [CIO Dive, 2026-04-30](https://www.ciodive.com/news/microsoft-earnings-Q3-2026/819009/)
- FY26 Q4（2026-07-29）：付费席位**超3000万**，净新增席位环比翻倍以上；5万席以上客户同比增长7倍+；将 Copilot 部署给大多数信息工作者的企业客户环比增近75%；人均对话数同比近翻倍；"平均周活跃度与 Outlook、Teams 相当"；三个季度内用户满意度翻倍、本季延迟下降25%；Purview 已审计500亿+次 Copilot 交互（+~360%）；M365 商业付费席位同比+6% — [Microsoft FY26 Q4 Earnings Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- **大单**（同一电话会）：NHS England 为50.5万临床人员与员工部署；KPMG 扩展至27.6万+员工；HSBC 承诺20万席；10家公司各购6万席以上（AstraZeneca、Boeing、Infosys、Koch、P&G、Stellantis、TCS、UPMC、Wells Fargo、Wipro）；EY 将 E7 部署至40万员工 — [Microsoft FY26 Q4 Earnings Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- **路线与商业模式**（同一电话会）：Nadella 称 Copilot 正"from chat to Cowork to Autopilots"演进；Cowork 于上月GA、7月起叠加按用量计费，"数千家客户已付费"；Autopilots 定义为"具备完整企业合规的自主长时运行智能体"；Copilot 各体验（含 Code）将合并为横跨消费与商业的"super app"；Agent 365 上线约两个月注册近4000万个智能体；E7 仅部分季度在售即"数百家企业购买数百万席"；微软正转向"per-seat-plus-consumption"；Copilot 使用增加导致该分部毛利率略降；GitHub Copilot 用户5000万并引入用量计费；Dynamics 365 暴露65万+ MCP actions，客服 credit 消耗环比4倍 — [Microsoft FY26 Q4 Earnings Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- **E7 / Agent 365 发布**：2026-03-09 发布 Microsoft 365 E7 "Frontier Suite"（E5 + M365 Copilot + Agent 365 + Entra Suite，由 Work IQ 驱动），2026-05-01 GA，$99/用户/月（含/不含 Teams 两版）；Agent 365 同日GA，$15/用户/月，定位"AI智能体的控制平面"；同时发布 Copilot "Wave 3"（Word/Excel/PowerPoint/Outlook 内的 agentic 体验）；Copilot 同时使用 OpenAI 与 Anthropic 模型，Claude 经 Frontier 计划进入主线 Copilot Chat — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)
- **许可与涨价**：E7 各组件单买约$117（E5 $60 + Copilot $30 + Agent 365 $15 + Entra Suite $12），E7约省15%，CSP 推广折扣至2026-12-31（15%折后约$84）；Copilot CSP 折扣15–40%；M365 E3 自2026-07-01由$36涨至$39、E5由$57涨至$60；Copilot Studio/Foundry 的智能体构建与运行另按 Azure 用量计费，不含在 E7 内 — [SAMexpert, 2026-05](https://samexpert.com/microsoft-product-terms-may-2026/)
- **SMB**：Copilot Business（≤300用户）$21/用户/月（年付），企业版$30；Copilot Chat 对合格 M365 订户免费 — [No Jitter, 2026-02](https://www.nojitter.com/ai-automation/microsoft-365-copilot-hits-15-million-paid-seats)；2026-05-28 推出 "Microsoft 365 Business Standard/Premium with Copilot" 捆绑 SKU（正文称7月1日推出、页首称"已GA"，二者矛盾；页面未列价）— [Microsoft 365 Blog, 2026-05-28](https://www.microsoft.com/en-us/microsoft-365/blog/2026/05/28/introducing-microsoft-365-business-with-copilot-the-new-standard-for-small-business/)
- **Copilot Cowork**：2026-03-09 以 research preview 发布，"把 Claude Cowork 背后的技术带入 M365 Copilot" — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)；2026-06-16 全球GA：需 M365 Copilot USL；按 Copilot Credits 用量计费（PayGo $0.01/credit，P3 预付折扣），按轻/中/重任务给出成本估算器；GA时运行 Anthropic Opus 4.8 与 Sonnet 4.6（Frontier 客户可用 GPT 5.5），将推出更便宜的微调模型 "Cowork 1"；"超过半数 Fortune 500 在用"、"Frontier 计划史上增长最快的功能"；默认关闭，可在租户/组/用户层设预算；微软内部测试（125次运行）称其每提示成本比"Claude Cowork + M365 connector"低30–40%（厂商自述）— [Microsoft 365 Blog, 2026-06-16](https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/16/copilot-cowork-is-now-generally-available/)
- **Autopilot（常驻智能体）**：2026-06-02 发布 Microsoft Scout——首个 "Autopilot"，后台常驻、无需每次提示即行动，每个智能体拥有独立 Entra 身份，基于开源 OpenClaw 技术，经 Frontier 以实验性方式发布；后更名为 Autopilot — [Microsoft 365 Blog, 2026-06-02](https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/02/introducing-microsoft-scout-your-always-on-personal-agent/)
- **"新 Copilot"（2026-09-25）**：Home（Chat 与 Cowork 合一、将自动路由到 Chat/Cowork/Code）、Code（自然语言构建小应用，与 GitHub Copilot 同技术、沙箱运行）、Autopilot（9月底私测，有自己的身份/记忆/电脑/工作区，可在 Teams/Outlook 中被@）；另有 Office in Copilot、Copilot Managed Runtime、plugin registry、FinOps for AI；定价双轨：USL 固定费覆盖日常 Chat 与 Office 内 AI（内含按准确度/速度/成本路由模型的 "Auto"），UBB 用量计费覆盖 Cowork、Code、Autopilot 与"Astra、Fable"等前沿模型；Ignite 定于2026-11-17至20 — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)
- 其他2026发布：Copilot Studio 计算机操作智能体与新 workflows（05-26）、M365 Copilot 新设计（05-28）、Work IQ APIs（06-02）、"Copilot in Excel: Built for the era of Frontier Finance"（06-25）、Microsoft 365 G7 政府版（09-15）、在 Copilot Cowork 与 Copilot Studio 中构建应用（09-10）— [Microsoft 365 Blog 索引](https://www.microsoft.com/en-us/microsoft-365/blog/)
- 市场反应（搜索摘要，Reuters 经 Yahoo 转载）：自1月中旬 Anthropic 发布 Claude Cowork 至3月，微软股价跌超14%，Reuters 将此与 Copilot Cowork 发布时机相联系 — [Yahoo Finance/Reuters, 2026-03](https://finance.yahoo.com/news/microsoft-taps-anthropic-copilot-cowork-130144093.html)
- 术语：2026年微软官方用语为 "Frontier Transformation / Frontier program / Frontier Suite / Frontier Professionals"；"Frontier Firm"（2025 WTI 概念）未出现在 2026-03-09 博客与 FY26 Q4 电话会中；电话会提到新设工程组织 "Microsoft Frontier Co."（6,000名嵌入式专家）— [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)；[FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)

#### Google Workspace with Gemini / Gemini Enterprise
- Google Cloud Next 2026（拉斯维加斯，约2026-04-23结束）：Vertex AI 品牌退役，改名 **Gemini Enterprise Agent Platform**（构建、部署、治理智能体的统一平台）；Gemini Enterprise 2026Q1 付费MAU环比+40%、部署于2,800+企业、售出800万+席位（newsletter 转述，未在 Alphabet 文件中找到该席位数）— [Business Analytics Substack, 2026-04-24](https://businessanalytics.substack.com/p/google-launches-gemini-enterprise)
- Alphabet Q2 2026（2026-07-22）：Pichai 称"近90%的 Fortune 100 在使用 Gemini Enterprise"；Google Cloud 收入$248亿（同比+82%），经营利润$88亿（上年$28亿）；Gemini App MAU 9.5亿；Gemini 模型每分钟处理220亿 API tokens — [Alphabet 8-K Q2 2026](https://www.sec.gov/Archives/edgar/data/0001652044/000165204426000066/googexhibit991q22026.htm)
- 版本：Business（1–500用户）、Standard、Plus、Pay-as-you-go、Frontline（≥150个 Standard/Plus 用户，只能用管理员下发的智能体）；功能含 Deep Research、权限感知企业搜索与 grounding、Agent Marketplace、NotebookLM 企业版、无代码自定义智能体（预览）等；官方文档未列价格 — [Google Cloud Docs](https://docs.cloud.google.com/gemini/enterprise/docs/editions)
- 价格（二手且互相矛盾）：一份指南称 Business $21、Standard $30、Plus $50（年付），另一来源仅确认"起价$30/席/月" — [coworker.ai](https://coworker.ai/blog/gemini-enterprise-pricing)；[vdf.ai](https://vdf.ai/blog/gemini-enterprise-pricing-vs-private-ai/)
- Workspace 侧2026重点：Workspace Studio（用 Gemini 构建智能体）、Sheets canvas 迷你应用、"Workspace Drops"（约2026-09，AI 图像生成/编辑与跨应用 AI 帮助）、高管"先建的5个智能体"等内容 — [Google Workspace Blog](https://workspace.google.com/blog)
- Claude Cowork 可通过 Gemini Enterprise Agent Platform 部署（Google 平台承载第三方工作智能体）— [Claude Cowork 产品页](https://claude.com/product/cowork)

#### OpenAI：ChatGPT Enterprise / Business / Edu
- 2026-02-27 OpenAI 公告（"Scaling AI for everyone"）：ChatGPT 周活9亿、消费订阅5000万+、"900万+付费商业用户"（DIW 标题称 users、正文称 businesses，口径不一）；Codex 周用户160万（年初以来增至3倍+）；同文宣布$1100亿新投资（投前估值$7300亿）— [Digital Information World, 2026-02-28](https://www.digitalinformationworld.com/2026/02/openai-reports-900m-weekly-chatgpt.html)
- OpenAI 称企业业务已占其收入40%+，并有望在2026年底与消费业务持平（搜索摘要；页面403）— [OpenAI: The next phase of enterprise AI](https://openai.com/index/next-phase-of-enterprise-ai/)
- **DevDay 2026（2026-09-29）**：头条为常驻智能体 **Dots**——GPT-6 Astra 驱动，每个 dot 有独立云端电脑和浏览器、7×24 追踪目标；可在 ChatGPT（桌面/移动/网页）、Slack、Microsoft Teams 中对话并跨渠道保留上下文；通过插件连接4,000+应用；空闲时用只读工具"主动研究"；Custom Rules 设定允许/需审批/禁止的动作；Pro 200 与 Business Premium 先推，Enterprise/Edu/Healthcare 工作区需管理员开启。同场发布 ChatGPT Space（团队与 dots 共享上下文的工作区）、Pages（人与 dots 共同编辑的文档）、GPT-6.1 Sol（称以 Astra 约20%的 token 价格接近其能力）、Codex 云端运行；$200 Pro 档从20×Plus用量降为10× — [BGR, 2026-09](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- 开发者侧：Agents API 增加 computer use 与 Codex 的多智能体能力；插件可依据拟议的 "MCP Events" 规范在连接应用发生事件时触发自动化；GPT-6.1 Sol 可在 API、"ChatGPT Work" 与 Codex 中使用 — [InfoQ, 2026-10-02](https://www.infoq.com/news/2026/10/openai-devday-2026/)
- 价格（第三方引用 OpenAI 定价页）：ChatGPT Business Standard 席$20/月（年付；月付$25），Premium 席$100（月付$125），至少2席；Enterprise 无公开价（第三方称约$45–75/用户/月、约150席起，非官方）— [coworker.ai](https://coworker.ai/blog/chatgpt-enterprise-pricing)

#### Anthropic：Claude Enterprise / Team（Claude Cowork、Claude Code、Chrome/Office 集成）
- **收入**：run-rate 2025年底约$90亿 → 2026-02-12 $140亿（Series G）→ 04-06 超$300亿 → 5月初超$470亿（Simon Willison 汇总 Anthropic 历次公告）— [Simon Willison, 2026-05-29](https://simonwillison.net/2026/May/29/anthropic/)
- 2026-05-28 Series H：融资$650亿，投后估值$9650亿；Claude Code 与 Cowork 被列为关键产品；Claude 成为首个同时在 AWS、Google Cloud、Microsoft Azure 提供的前沿模型 — [Anthropic, 2026-05-28](https://www.anthropic.com/news/series-h)
- 二手：据 Bloomberg/Reuters，7月底 run-rate 超$650亿；年付超$100万的客户4月超1,000家（2月500+）— [codeconductor.ai（二手）](https://codeconductor.ai/blog/claude-code-anthropic-profitability/)；Claude Code run-rate 2月超$25亿、年初以来企业订阅翻两番 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)；Forbes 估计约85%收入来自企业与开发者 — [Forbes, 2026-05-21](https://www.forbes.com/sites/paulocarvao/2026/05/21/anthropic-openai-enterprise-ai-profitability/)
- **Cowork 时间线**：2026-01-12 面向 Max 首发，01-16 Pro，01-23 Team/Enterprise（二手）— [BuildFastWithAI](https://www.buildfastwithai.com/blogs/what-is-claude-cowork)；02-24 管理员私有插件市场，04-09 企业部署控制（访问、预算、用量追踪），08-26 内置浏览器（官方产品页）— [Claude Cowork 产品页](https://claude.com/product/cowork)；07-07 web 与移动端 beta（二手）— [Tech-Insider](https://tech-insider.org/au/claude-cowork-web-mobile-launch-2026/)；产品页现称 "Cowork is now just Claude"（与 Chat 合并，先推 Pro/Max）— [Claude Cowork 产品页](https://claude.com/product/cowork)
- **Cowork 形态/定价/渠道**：面向非编码知识工作，"给目标→跨文件与工具执行→交回成果"；支持定时任务、移动端发起后云端持续运行、computer use 研究预览（优先 connector→浏览器→屏幕）；Pro $17/月（年付）或$20、Max 5× $100、Max 20× $200、Team $20/席/月（2–150人）、Enterprise 询价；企业可经 Amazon Bedrock、Gemini Enterprise Agent Platform、Microsoft Foundry 部署，含 RBAC、预算、Analytics API、OpenTelemetry 至 SIEM；插件打包 skills/connectors/sub-agents（如 Legal、Finance）；扩展含 Claude in Chrome、Claude for Google Workspace、Claude for Microsoft 365 — [Claude Cowork 产品页](https://claude.com/product/cowork)
- **2026年9–10月企业动态**：Claude Opus 5.5（09-22）、Sonnet 5.5（09-28）、Haiku 5.5（10-07）；Enterprise Frontier Safeguards（零数据保留+滥用检测，09-01）；与 Accenture 合作嵌入式评估、5年至少投入$10亿（09-18）；Barclays 扩大 Claude 部署（10-01）；$1亿 "Claude Frontier Academy" 培训1万名工程师（Accenture、Bain、CBA、Deloitte、McKinsey、Morgan Stanley、Novo Nordisk 参与，10-02）；将 Agent Skills 标准捐赠给 Agentic AI Foundation，已有70+智能体平台集成（10-22）— [Anthropic News](https://www.anthropic.com/news)
- Claude Duet research preview（10-21）、Claude Platform 全量上架 Google Cloud（10-22）、HCLTech 成为 Global Premier 合作伙伴（10-21）、Code Review GA（10-15）、Claude Managed Agents 用例 — [Claude Blog](https://claude.com/blog)

#### Salesforce：Slack AI / Slackbot / Agentforce in Slack
- 2026-01-13 新 Slackbot GA（Business+ 与 Enterprise+，1–2月分阶段推送）：个人工作智能体，基于对话/文件/频道上下文并遵循权限，可检索、起草、排程、结合 Salesforce 客户数据做会前简报；定位 Agentforce 360 在 Slack 的"对话前门"，编排 Agentforce 与第三方智能体为"即将推出"；新闻稿未说明是否另行收费 — [Salesforce 新闻稿, 2026-01-13](https://www.salesforce.com/news/press-releases/2026/01/13/slackbot-announcement/)
- Q2 FY27（2026-08-26）：Agentforce ARR 超$15亿（+240%；自本季起计入 Slackbot 与 Headless 360，口径变化）；Agentforce + Data 360 ARR 近$39亿（+210%）；Agentforce 与 Slack 累计 Agentic Work Units 70亿、Q2 单季32亿（环比+97%）；Slack 录得被收购以来最快的季度 NNAOV 增长，Slackbot 用户环比+150%；Agentforce Apps 订阅收入按固定汇率仅+8%；FY27 收入指引上调至$461–464亿（+11–12%，含待完成的 Contentful 与 Fin 收购）— [Salesforce 8-K, 2026-08-26](https://www.sec.gov/Archives/edgar/data/0001108524/000110852426000187/crm-q2fy27xexhibit991.htm)

#### Atlassian Rovo
- FY26 Q2（截至2025-12-31，2026年初发布）：CEO 称 Rovo MAU 超500万 — [Atlassian 8-K](https://www.sec.gov/Archives/edgar/data/1650372/000165037226000008/ex991q2fy26.htm)（背景：2025-10 的 Q1 FY26 时"AI能力 MAU"为350万（搜索摘要）— [BusinessWire, 2025-10-30](https://www.businesswire.com/news/home/20251030385606/en/Atlassian-Announces-First-Quarter-Fiscal-Year-2026-Results)）
- FY26 Q4（2026-08-06 发布）：收入$17.7亿（+28%），Cloud $12.1亿（+31%）；Rovo 被80%+ Fortune 500 使用（但 Fortune 500 仅占其收入约10%）；Rovo 辅助动作环比+50%；MCP server 与 Teamwork Graph CLI 合计 MAU 超100万（单季翻倍以上）；Teamwork Graph 200B+对象，称基于其的智能体答案准确度最高+44%、token 少48%（厂商自述）；使用 Rovo 的客户 ARR 增速为未采用者的2倍以上；Teamwork Collection 含约10倍 Rovo credits，并在测试用量超额与 "Flex" 承诺消费模式；未再披露 Rovo MAU — [Futurum, 2026-08-11](https://futurumgroup.com/insights/atlassian-q4-fy-2026-can-rovo-turn-ai-usage-into-durable-growth/)

#### Zoom AI Companion
- Q1 FY27（2026-05-21 电话会）：AI Companion 付费MAU同比+184%（主要来自 AI Companion 3.0 早期采用）；My Notes 上线约4个月 MAU 超150万（不含试用）；Raymond James 扩展至约1万席 Custom AI Companion；前十大 CX 交易中9笔含付费 AI；3月推出 Zoom AI Services（含 Scribe API）；收入$12.4亿（+5.5%），FY27 收入指引上调至$50.8–50.9亿；未披露 AI Companion 绝对用户数 — [Motley Fool 电话会纪要](https://www.fool.com/earnings/call-transcripts/2026/05/21/zoom-zm-q1-2027-earnings-call-transcript/)

#### Notion AI
- 2026-02 推出 Custom Agents（处理FAQ、状态汇总、工作流自动化），至2026-05-13 用户已构建100万+个；05-13 推出 Notion Developer Platform（Workers 沙箱代码、数据库同步、External Agent API、CLI），首批支持 Claude Code、Cursor、Codex、Decagon 等第三方智能体在 Notion 内被分派任务；CEO Ivan Zhao："Any data, any tool, any agent" — [TechCrunch, 2026-05-13](https://techcrunch.com/2026/05/13/notion-just-turned-its-workspace-into-a-hub-for-ai-agents/)
- Sacra 估算 ARR 2026-07 约$8.65亿（+82%，非公司披露）；公司披露2025年底50%+ ARR 来自启用 AI 的客户；Business/Enterprise 版 Custom Agents 需 credits（$10/1,000 credits/月，二手）— [Sacra](https://sacra.com/research/notion-at-865m-year-growing-82-yoy/)

#### Glean（企业搜索/知识图谱）
- ARR：2025-12 达$2亿 — [Glean 新闻稿](https://www.glean.com/press/glean-surpasses-200m-in-arr-for-enterprise-ai-doubling-revenue-in-nine-months)；2026-05 达$3亿（约15个月前为$1亿；TechCrunch 指出消费制部分更接近 run-rate）；估值仍为2025-06 Series F 的$72亿；卖点转为"大幅降低企业AI账单"（context graph 让 AI 少消耗 token）；计价为纯消费制或"活跃用户月费+模型用量"混合；文中称许多公司"正在烧穿 AI 预算"；竞争者包括 Google、Microsoft、OpenAI、Anthropic、Salesforce、Atlassian — [TechCrunch, 2026-05-28](https://techcrunch.com/2026/05/28/gleans-top-line-crosses-300m-as-ai-budget-cutting-becomes-its-major-selling-point/)

#### Box AI
- Q4 FY26 电话会（2026-03-03）：FY26 收入$11.8亿（+8%）；最高档 Enterprise Advanced 上线一年即占收入10%，较 Enterprise Plus 平均提价30–40%；Box Extract GA；Box Automate 计划 FY27 上半年推出（人+智能体工作流）；将 Box 定位为 Claude Cowork、Copilot、IBM watsonx、ChatGPT 及自建智能体的"文件系统"，按用户席位或 API/AI units 消费变现；称未来企业内智能体数量将"增加百倍" — [Box Q4 FY26 讲稿](https://s21.q4cdn.com/328470014/files/doc_earnings/2026/q4/transcript/Box-Q4-FY26-earnings-prepared-remarks.pdf)

#### Harvey（法律垂直，代表"垂直知识工作智能体"）
- 官方博客置顶：Harvey 以$155亿估值融资$5.5亿（页面未显示日期）；2026-08至10密集发布：首个开放权重后训练模型 Tenet（08-20）、合同审阅智能体（09-10）、Harvey Agent 用于法律检索（09-22）、在 Word 中直接运行自定义智能体（09-23）、与 LexisNexis 共建 Motion to Dismiss 工作流（10-07）、Legal Work Orchestration（10-15）、Harvey Graph（10-19）、支持自定义 MCP 的 Connector Library（10-21）；新设东京、波士顿办公室 — [Harvey Blog](https://www.harvey.ai/blog)

### Inferences
- 微软3000万付费席位对应4.5亿+商业席位（年中同比+6%），推算渗透率约6–7%；1–7月新增约1500万席且大单（>5万席客户同比7倍）集中，说明"全员部署"的拐点出现在2026年中，但长尾渗透仍低。
- 定价范式在2026年高度一致地转向"席位+用量"：Microsoft（USL+UBB、Copilot Credits）、Salesforce（AWU、Agentforce ARR）、Atlassian（credits+Flex）、Notion（credits）、Glean（消费制）、Box（AI units）、GitHub（UBB）、OpenAI（Dots 任务计入用量）。这打开了收入上限，也把推理成本和毛利压力（微软已提示）直接带入应用层。
- Anthropic 从"模型供应商"变为"工作应用层竞争者 + Microsoft 的上游供应商"：Copilot Cowork 基于 Claude Cowork 技术，微软同时宣传其比 Claude Cowork 便宜30–40%——典型的竞合关系，2027年模型多元化与"谁拥有工作界面"将是核心博弈。
- Google 叙事以"平台+分发"为主（Agent Platform、Cloud +82%），但未在财报中直接披露 Gemini Enterprise 席位；OpenAI 企业侧有产品势能（Dots、插件、Pages、Space）但缺可核实的2026企业席位数据。
- 生产力套件厂商（Atlassian、Notion、Box、Slack、Zoom）的共同策略是把自己变成"智能体的上下文层/记录系统"（Teamwork Graph、Notion Developer Platform、Box 文件系统、Slackbot 前门），以对冲"AI 原生工具绕开 SaaS 席位"的风险。

### Gaps
- OpenAI 2026年企业/商业席位官方数（二手汇总中"700万+工作席位、企业席位同比9倍"疑为2025-11背景数据，"400万–700万+"企业席位估计口径混乱）；ChatGPT Business 新订阅200席上限（据称2026-08-24起）仅见第三方定价指南；"ChatGPT Work"具体为何产品未能核实；openai.com 抓取均为403。
- Anthropic 企业客户总数/企业席位数，以及 Claude in Excel / Claude in PowerPoint 的2026年上线日期与用量：未找到一手数据（Claude Cowork 产品页未提及 Excel/PowerPoint）。
- Gemini Enterprise 800万+席位与官方价目：未在 Google 一手材料核实。
- Perplexity Enterprise 2026年数据：未检索到（搜索额度用尽）。
- Zoom Q2 FY27（"AI 功能授权 MAU +125%"）仅见二手；Slack AI/Slackbot 单独收费与否未说明。
- 截至2026-10-23尚未发生/未覆盖：Microsoft Ignite 2026（11-17至20）、Microsoft FY27 Q1 与 Alphabet Q3 2026 财报。

## 2. 2026年发布的采用与影响数据（含生产力证据、pilot-to-production 鸿沟、workslop、shadow AI）

### Takeaway
2026年数据的共识是"广泛使用、浅层落地、价值集中"：大企业高管调查中约九成"在用AI"（McKinsey/Stanford 88%），但美国全口径企业采用率仅约20%（Census BTOS）；员工自报省时显著（BCG：42%的一线常规用户每周省约一天），但 McKinsey 的"高绩效者"仍为6%、称AI贡献EBIT的仍为37%（均与上年持平）；Wharton 80%称ROI为正、仅28%为"强正向"。更严格的准实验证据仍偏弱或为零效应；workslop 与 shadow AI 是主要副作用。

### Cited Findings

#### 宏观采用率（Census BTOS 等）
- Census BTOS：2025-12至2026-05 美国企业AI使用率在17–20%间，2026-05-03为19.8%；未来6个月预期20–23%；250+员工企业37%、100–249人32%、≤4人企业低于20%；信息业39.7%、金融保险33.9%、零售约14% — [U.S. Census Bureau, 2026-05](https://www.census.gov/library/stories/2026/05/ai-use-businesses.html)
- 口径断点：2025-11-17 起 BTOS 题目由"用于生产商品或服务"改为"任何业务职能"，头条比例由约10%跳到约20%，前后不可比；2026-04 AI 补充调查：约96%使用AI的企业称过去6个月总人数不变（其余增减各半），约10%称AI已承担原由员工完成的任务；医疗约20%（自2023年约增至3倍）、制造约12% — [Minneapolis Fed, 2026-05-29](https://www.minneapolisfed.org/article/2026/ai-adoption-in-business-grows-steadily-but-unevenly)
- Census 工作论文（基于2025-11至2026-01 AI 补充调查）：18%的企业在某业务职能使用AI，按就业加权为32%（搜索摘要）— [Census CES-WP-26-25](https://www2.census.gov/library/working-papers/2026/adrm/ces/CES-WP-26-25.pdf)
- 冲突：Census 报道称250+员工企业为37%（BTOS，2026-05），Minneapolis Fed 引 2026-04 AI 补充调查为30%（不同问卷）— [Census](https://www.census.gov/library/stories/2026/05/ai-use-businesses.html)；[Minneapolis Fed](https://www.minneapolisfed.org/article/2026/ai-adoption-in-business-grows-steadily-but-unevenly)

#### 企业高管调查
- **McKinsey State of AI 2026**（2026-08发布；2026-05-04至06-08调研；1,719人/97国，36%来自营收>$10亿企业）：近九成在至少一个职能常规用AI；44%称AI在全企业规模化（上年38%）；三个及以上职能使用由51%升至56%；大企业"规模化智能体"由27%升至40%，小企业持平于22%；约两成在规模化编码智能体（大企业31%）；37%称AI贡献EBIT（基本持平），"高绩效者"（≥5% EBIT归因AI）仍为6%；80%称个人生产力提升；32%因可用 agentic coding 自建而放弃购买至少一款软件/功能（专业服务38%、金融36%）；1/5称 token 等运行成本已限制使用；60%预计明年AI投资增加；28%已把10%以上科技预算投向AI — [BIP Capital 解读 McKinsey](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；[McKinsey 报告页](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)（搜索摘要确认发布日期与样本）
- **Deloitte State of AI in the Enterprise 2026**（2026-01；2025-08至09调研3,235名高管/24国）：仅23%中度使用 agentic AI，74%预计两年内中度至全面整合；仅21%有成熟的自主智能体治理；66%获得生产力/效率提升，仅20%称AI带来收入增长；84%未围绕AI重新设计岗位；称AI有"变革性影响"由12%升至25%（二手）— [Libertify（二手）](https://www.libertify.com/interactive-library/state-of-ai-enterprise-2026-deloitte-survey/)；[Deloitte](https://www.deloitte.com/global/en/issues/ai/state-of-ai-in-enterprise.html)
- **Wharton–GBK "The Adaptive Advantage"**（2026-10-13；1,416名美国企业领导与员工）：经理及以上日用AI 62%（约+16点）、周用91%；"兴奋"-8点、"谨慎"+7、"怀疑"+8；80%领导称ROI为正、28%为强正向；以增长指标衡量的部门强ROI 35% vs 仅效率指标13%（"节省工时"仍是40%部门的主指标）；67%用智能体完成任务/流程，但仅17%允许智能体无需逐步审批即行动、28%称AI完全嵌入核心流程；仅7%满足"证明价值、改造流程、组织对齐"全部三项；设 Chief AI Officer 的强ROI 58% vs 由现有高管兼管24%；单一批准平台 vs 仍在试验：50% vs 9%强ROI — [GBK Collective, 2026-10-13](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)（背景：2025版74%称ROI为正 — [mi-3, 2025-10](https://www.mi-3.com.au/29-10-2025/hype-hard-numbers-generative-ai-finally-faces-roi-test-and-bankers-tech-and-telco)）
- **Stanford AI Index 2026**（2026-04，日期据二手报道）：组织AI采用率88%；智能体在大多数业务职能部署仍为个位数；OSWorld 真实电脑任务成功率约66%（人类基线72.35%）；生成式AI年为美国消费者创造约$1720亿价值；73%专家 vs 23%公众认为AI会改善人们的工作方式 — [Stanford HAI](https://hai.stanford.edu/ai-index/2026-ai-index-report)；报告汇总的生产力研究：客服约14–15%、软件开发26%、营销产出73%（营销数字各转述不一）— [UNU C3, 2026-07](https://c3.unu.edu/blog/2026-stanford-ai-index-report-takeaways)

#### 员工侧调查
- **Microsoft Work Trend Index 2026**（2026-05-05；Edelman DXI 调查20,000名在工作中使用AI的知识工作者/10国，2026-02-18起；另分析一周内约10.5万条 M365 Copilot 对话）：49%的 Copilot 对话支持认知工作、19%与人协作、15%找信息、17%产出工作；66%称有更多时间做高价值工作，58%在产出一年前做不到的工作（"Frontier Professionals"为80%，占受访者16%）；仅19%处于"Frontier Zone"、50%为"Emergent"；组织因素解释67%的自报AI影响、个人因素32%（相关非因果）；仅26%称领导层在AI上一致；65%担心落后，45%认为专注现有目标更安全，仅13%称重塑工作即使失败也会被奖励；M365 活跃智能体同比15倍（2025-03至2026-03；大企业18倍）；经理示范使用AI→AI价值+17点、对 agentic AI 信任+30点 — [Microsoft WorkLab, 2026-05-05](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)
- **BCG AI at Work 2026**（2026-06-03；近1.2万人、十余个市场；二手称11,749人/14国）：一线员工常规（每天或每周数次）使用率74%（+23点）；42%的一线常规用户每周省约8小时（营销60%、IT 53%、HR 50%省时最多）；66%未获"省下时间怎么用"的指导、过半未投入战略性工作；42%的组织在端到端重塑流程或创造新模式（上年22%）；30%称组织已把智能体纳入工作流（上年13%），50%做过智能体试点；72%称技能要求变了，仅36%获足够培训；41%称认知负担加重（领导48%）；印度、中东、澳大利亚领先，法国、意大利、美国落后 — [BCG, 2026-06-03](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)；[BCG 幻灯片](https://web-assets.bcg.com/eb/92/4b39b729403fb6fcae4ff974b234/ai-at-work-slideshow-jun-2026-1.pdf)
- **Anthropic Economic Index "Cadences"**（2026-06-26；Chat/Cowork 数据2026-04-10至06-10；约9,700名受访者联结样本，计算机/数学与管理岗过度代表）：93%的对话产出成果物（解释17%、文档报告15%、指导11%），工作类对话最常产出文档报告（20%）；高薪职业每轮产出多1.34倍；Claude Code 在31类产出中26类的AI自主度高于 Chat/Cowork（平均高0.37/5分，2/3来自用户委派更多）；自报收益：速度86%、范围82%、质量69%、成本27%；68%称学得更多、57%称技能更值钱（无法排除技能侵蚀）— [Anthropic, 2026-06-26](https://www.anthropic.com/research/economic-index-june-2026-report)
- Anthropic Economic Index 2026-01（"Economic primitives"）：Claude.ai 上增强型使用重新领先（约52% vs 自动化45%），API 使用以自动化为主、反映企业把 Claude 用于后台流程自动化（搜索摘要，未打开原文）— [Anthropic, 2026-01](https://www.anthropic.com/research/anthropic-economic-index-january-2026-report)
- Gallup（二手汇总）：2026Q2 有47%的美国员工称其组织已整合AI（Q1为41%）；2026-05 仅25%称组织沟通了清晰的AI整合计划 — [Tech-Insider（二手）](https://tech-insider.org/shadow-ai-45-percent-workers-ricoh-deloitte-2026/)

#### 生产力证据（RCT / 准实验 / 行政数据）
- METR：2025-07 RCT（16名资深开源开发者、246个真实任务）发现用AI反而慢19%，而开发者事后仍自认快了约20%（背景）— [METR, 2025-07-10](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/)；2026-02-24 更新（2025-08起，57名开发者、143个仓库、800+任务）：回访开发者 −18%（CI −38%~+9%）、新开发者 −4%（CI −15%~+9%），方向转为提速但统计不显著；30–50%开发者拒绝在无AI条件下做部分任务，选择效应严重，METR 宣布改变实验设计并认为真实提速被低估 — [METR, 2026-02-24](https://metr.org/blog/2026-02-24-uplift-update/)
- Humlum & Vestergaard（NBER w33777，2026-03修订，丹麦调查+行政数据）：AI聊天机器人对员工与工作场所层面的收入和记录工时为"精确的零效应"，可排除 ChatGPT 发布两年后超过2%的影响；企业主要通过任务重组吸收AI（新增内容生成、AI监督、AI集成等任务）— [NBER w33777](https://www.nber.org/papers/w33777)
- a16z 对100位 CIO 的调查（No Jitter 2026-02 转述）：M365 Copilot 在"既有厂商AI应用"中采用领先；生产力是衡量 LLM ROI 的首要指标，ROI 低于预期，31%估计回报在盈亏平衡至1.5倍之间 — [No Jitter, 2026-02](https://www.nojitter.com/ai-automation/microsoft-365-copilot-hits-15-million-paid-seats)
- 厂商遥测：M365 Copilot 人均对话数同比近翻倍、周活跃度与 Outlook/Teams 相当（厂商自述）— [Microsoft FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Slackbot 客户证言"每天至少省90分钟""每天约省30分钟"（厂商挑选的证言）— [Salesforce, 2026-01-13](https://www.salesforce.com/news/press-releases/2026/01/13/slackbot-announcement/)

#### Pilot-to-production 鸿沟（"GenAI divide"）
- 背景（2025-08）：MIT NANDA《The GenAI Divide: State of AI in Business 2025》称约95%的企业生成式AI试点没有可测量的P&L回报（基于访谈/调查与300个公开部署，作者自称"方向性"结论，方法论有争议）— [Fortune, 2025-08-18](https://fortune.com/2025/08/18/mit-report-95-percent-generative-ai-pilots-at-companies-failing-cfo/)；未找到 MIT NANDA 2026年后续报告（搜索结果均指向2025原报告）
- 2026年的"鸿沟"证据：McKinsey 高绩效者6%与EBIT贡献37%双双持平 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；Wharton 仅7%满足全部成功标志、28%称AI完全嵌入核心流程 — [GBK](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)；Deloitte 84%未重新设计岗位、仅20%见收入增长 — [Libertify](https://www.libertify.com/interactive-library/state-of-ai-enterprise-2026-deloitte-survey/)；Stanford AI Index 称生产力收益集中于少数领先群体 — [aibusinessweekly, 2026-04-19](https://aibusinessweekly.net/p/stanford-ai-index-2026-enterprise-adoption-productivity)；Gartner（2025-06）预测到2027年底超40%的 agentic AI 项目将因成本上升、价值不明和风控薄弱被取消 — [BigDATAwire](https://www.hpcwire.com/bigdatawire/this-just-in/gartner-predicts-over-40-of-agentic-ai-projects-will-be-canceled-by-end-of-2027/)

#### Workslop（低质量AI产出）
- Stanford 相关预印本（2026-02；962名美国全职桌面工作者）：约53%承认向同事发送过AI "workslop"，38%收到过，接收方每月约耗3.4小时处理（搜索摘要；OSF 页面抓取为空）— [PsyArXiv/OSF](https://osf.io/preprints/psyarxiv/5f78h_v1)
- Zety（简历服务商，2026-01至02，1,000名美国员工，商业调查）：66%每周花至多6小时修正AI生成的错误 — [PR Newswire](https://www.prnewswire.com/news-releases/ai-workslop-is-costing-workers-hours-each-week-new-report-finds-302684523.html)；55%收到过来自经理/上级的 workslop — [Allwork.Space, 2026-03](https://allwork.space/2026/03/55-of-employees-receive-ai-workslop-from-managers-or-supervisors/)
- 概念背景：2025-09 HBR（Stanford Social Media Lab 与 BetterUp Labs 作者）提出"workslop" — [HBR, 2025-09-22](https://hbr.org/2025/09/ai-generated-workslop-is-destroying-productivity)
- 相关信号：BCG 称近半数或更多受访者因频繁审阅/纠正AI输出与"管理AI"而增加工作量，60%称"够好"的标准变高 — [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)；WTI：86%把AI输出当作起点而非最终答案，50%认为"AI输出的质量控制"是最重要的人类技能 — [WorkLab](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)

#### Shadow AI / BYO-AI
- Ricoh：45%员工每月至少一次使用未批准AI工具，53%称AI工具造成摩擦或额外工作；Deloitte 2026：员工AI可及性一年+50%，但有权限者不到60%在日常流程中使用 — [Tech-Insider（二手汇总）](https://tech-insider.org/shadow-ai-45-percent-workers-ricoh-deloitte-2026/)
- 其余 shadow AI 数字（Gartner、Netskope、Verizon DBIR、PagerDuty）见 Gaps（未能核实原始来源）

### Inferences
- "采用率"高度依赖口径：大企业高管调查的"88–90%"与 Census 全口径"约20%"相差4倍以上（前者偏大企业、"至少一个职能在用"；后者覆盖全部规模企业）。规划材料应同时引用两类数字并说明口径。
- 2026年最稳健的结论是"个体生产力自报普遍提升（McKinsey 80%、WTI 66%、Anthropic 86%），但组织级财务影响停滞（EBIT 37%、高绩效者6%不变）"。WTI（组织因素占67%）、BCG（战略清晰度比工具更重要）、Wharton（CAIO、单一平台、增长指标）都指向瓶颈在组织、流程与度量，而非工具可得性。
- "智能体"的实际形态多为人在环流程自动化：大企业40%"规模化智能体"、Wharton 67%"使用智能体"，与 Wharton 仅17%允许自主行动、Stanford"个位数部署"并存。
- Workslop 与认知负担（BCG 41%）说明AI把成本从"生产"转移到"审阅/校验"，提升了对质量标准、评审流程与"质量控制"技能的需求——这也是厂商在2026年强调评估、审计与 Code Review 类功能的背景。
- 丹麦零效应与 METR 的不显著结果提示：截至2026年，知识工作AI收益尚难在工资/工时等硬指标中观测，宏观生产力证据可能滞后于企业叙事。

### Gaps
- MIT NANDA 2026 后续报告：未找到。
- OpenAI 2026年企业使用报告（如"State of Enterprise AI"更新）与 GDPval 类工作评测的2026数据：openai.com 403，未核实。
- 2026年新发表的大样本知识工作 RCT/实地实验（NBER 等）：搜索额度用尽前未找到；仅有 METR 与丹麦研究的更新。
- Shadow AI 线索（仅见搜索摘要、未能定位一手出处，引用前需核实）：Gartner 2026Q1 约1.2万名员工/40国调查称88%有雇主AI工具的员工仍用个人AI工作；Netskope 2026 称个人AI应用使用率47%（上年78%）；Verizon 2026 DBIR 称67%AI用户在公司设备上用个人账户访问；PagerDuty 2026（1,250人）称66%用过自认为不被允许的AI工具、88%向公共AI工具分享过工作数据。
- McKinsey PDF（503）未能直接打开；"下一年预期39%"的方向（减员或增员）未能确认；Deloitte、Gallup 一手报告未打开。

## 3. 2026年劳动力影响（招聘、AI归因裁员及其可信度、入门级岗位、新角色与组织重构）

### Takeaway
2026年"AI"成为美国企业自报的头号裁员理由（1–9月120,136人，约占21%），但约85%集中在7月前、月度占比从7月33%降到9月9%，且全年裁员总量同比下降39%；更严谨的研究未见大范围替代，冲击集中在入门级/年轻员工的"少招"（Stanford Canaries：22–25岁在高暴露职业的相对就业差距扩大至19%）。组织层面，"人+智能体"主要体现为智能体身份/治理基础设施与管理者角色变化，而非成熟的新岗位体系。

### Cited Findings

#### AI归因裁员（Challenger, Gray & Christmas，美国）
- 9月报告（2026-10-01）：9月裁员43,281人；1–9月573,195人（同比−39%）；9月归因AI 3,961人（约9%）；年初至今AI 120,136人（约21%），仍为年度第一大原因；科技业年内165,925人（占29%）；年内招聘计划210,612人（+3%）— [Challenger, 2026-10-01](https://www.challengergray.com/blog/job-cuts-fall-in-september-hiring-plans-up-3-over-2025-on-weak-early-seasonal-hiring/)
- 8月报告（2026-09-03）：AI 归因3,462人，为2025-12（142人）以来最低，结束自3月起连续5个月AI为当月首要原因；年内AI 116,175人（约22%）；年内总裁员529,914人为2022年以来同期最低；Andy Challenger 称招聘计划增加但岗位"似乎没有被快速填补" — [Challenger 8月报告 PDF](https://www.challengergray.com/wp-content/uploads/2026/09/Challenger-Report-August-2026.pdf)
- 7月报告（2026-08-06）：当月AI 10,970人（33%）；年内112,713人（约24%）；自2023年追踪以来累计184,538人；Andy Challenger："AI正在改变劳动力市场，但并未拆解它"；"随着监管成形，企业在公告中会更谨慎" — [Challenger, 2026-08-06](https://www.challengergray.com/blog/challenger-report-layoffs-fall-hiring-picks-up-ai-leads-for-fifth-straight-month/)
- 4月：总裁员88,387人，AI 21,490人（26%），连续第二个月居首；Andy Challenger："无论个别岗位是否被AI取代，这些岗位的钱正在被（挪给AI）"；其他理由包括关税、伊朗战争、关停与降本 — [CBS News, 2026-05](https://www.cbsnews.com/news/ai-layoffs-job-cuts-challenger-report-april-2026/)；5月AI归因38,579人，为2023年开始追踪以来单月最高（二手，转引 Fox Business）— [Tech Jacks Solutions](https://techjacksolutions.com/ai-brief/ai-is-now-the-top-self-reported-layoff-driver-in-the-us-chal/)
- 归因可信度：Challenger 将明确"Artificial Intelligence"与"Technological Update (possibly AI)"分列，数据为雇主公告中的自述理由而非经核实的因果 — [Challenger 8月报告 PDF](https://www.challengergray.com/wp-content/uploads/2026/09/Challenger-Report-August-2026.pdf)；CBS 报道提到有怀疑者质疑AI是否为唯一原因（未具名）— [CBS News](https://www.cbsnews.com/news/ai-layoffs-job-cuts-challenger-report-april-2026/)

#### 入门级 / 年轻员工
- Stanford Digital Economy Lab（Brynjolfsson、Chandar、Chen，"Canaries in the Coal Mine?" 2026-08-12 修订版，ADP 工资数据）：22–25岁在高AI暴露职业的就业比按低暴露同龄人趋势应有水平低约19%（截至2026-06；2025-07数据版本为15%）；2022-11至2026-06 最暴露两个五分位就业下降约11%，最不暴露三个五分位增长约10%；调整主要通过"少招年轻人"而非离职；工资尚无明显调整；以AI"自动化"为主的职业下降、以"增强"为主的职业持平或上升，资深/隐性知识型岗位未见类似差距；剔除科技公司、控制利率与远程办公后依然成立；作者强调为描述性模式、非因果，控制教育后差距缩小 — [Stanford DEL, 2026-08-12](https://digitaleconomy.stanford.edu/news/canariesaug26/)；按月更新 — [Canaries Dashboard](https://digitaleconomy.stanford.edu/project/indicators/canaries-dashboard/)
- Stanford AI Index 2026（二手转述）：22–25岁软件开发者就业自2024年起下降近20%；1/3雇主预计未来一年因AI减员（集中在服务运营、供应链、软件工程）— [UNU C3](https://c3.unu.edu/blog/2026-stanford-ai-index-report-takeaways)
- Wharton–GBK（2026-10）：37%领导称已有AI相关裁员，33%放缓/冻结招聘；82%称AI帮助新员工更快产出；24%预计未来2–5年减少入门级招聘、14%预计减少高管岗位；强ROI组织并不比其他组织更可能裁员或冻结招聘 — [GBK Collective](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)
- Anthropic EI 调查（2026-06）：10%受访者认为明年可能失业，其中约38%归因于AI；受访者对他人更悲观——超1/3认为初级同事失业概率>60% — [Anthropic](https://www.anthropic.com/research/economic-index-june-2026-report)

#### 企业 / 总体就业
- McKinsey 2026：上年32%预计AI导致人数下降，今年实际仅14%报告下降；约2/3称AI对总就业几乎无影响 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)
- BTOS：约96%使用AI的企业近6个月总人数不变 — [Minneapolis Fed](https://www.minneapolisfed.org/article/2026/ai-adoption-in-business-grows-steadily-but-unevenly)
- 丹麦：对收入、工时为精确零效应 — [NBER w33777](https://www.nber.org/papers/w33777)
- WTI 引 LinkedIn 2026 劳动力市场报告：过去两年雇主创造了至少130万个AI相关岗位机会 — [Microsoft WorkLab](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)

#### 新角色与组织重构（agent 管理、"人+智能体"团队）
- 新任务出现：企业以任务重组吸收AI，新增内容生成、AI监督、AI集成类任务 — [NBER w33777](https://www.nber.org/papers/w33777)
- 智能体被设计为"同事"：Microsoft Autopilot 有自己的身份、记忆、电脑与工作区，可在 Teams/Outlook/文档中被@，受权限与审计约束 — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)；Scout/Autopilot 每个智能体使用独立 Entra 身份、敏感操作需人工签核 — [Microsoft 365 Blog, 2026-06-02](https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/02/introducing-microsoft-scout-your-always-on-personal-agent/)；OpenAI Dots 可在 Slack/Teams 中与团队协作，ChatGPT Space 让队友与 dots 共享上下文 — [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- 治理缺口：BCG 称一半受访者所在公司缺乏"管理人+AI团队"的清晰治理 — [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)；Deloitte 仅21%有成熟的自主智能体治理 — [Libertify](https://www.libertify.com/interactive-library/state-of-ai-enterprise-2026-deloitte-survey/)
- 管理者角色：经理示范使用AI→AI价值+17点、批判性思考+22点、对 agentic AI 信任+30点；营造心理安全→AI就绪度最高+20点、成为高频 agentic 用户的可能性1.4倍；Frontier Professionals 更常"先判断该由AI还是人来做"（53% vs 33%）— [Microsoft WorkLab](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)
- 领导结构：设 Chief AI Officer 的组织强ROI 58% vs 24%（兼管）vs 8%（无此角色）— [GBK Collective](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)
- 组织/人才投入：微软新设工程组织 "Microsoft Frontier Co."（6,000名嵌入式专家）— [Microsoft FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Anthropic 投$1亿培训1万名工程师以应对"企业AI人才缺口"（2026-10-02）— [Anthropic News](https://www.anthropic.com/news)
- 技能与心理成本：72%称技能要求改变、仅36%获足够培训 — [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)；47%的中层与个人贡献者报告至少一项AI负面影响（高管31%），20%的中层经理称AI损害其批判性思维（C-level 9%）— [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；担心技能退化：VP+ 48%、入门/中层46%、经理/总监32% — [GBK Collective](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)

### Inferences
- 由 Challenger 数字推算：截至6月AI归因约101,743人（=112,713−10,970），占1–9月AI累计的约85%——"AI裁员潮"主要是上半年现象；叠加 Andy Challenger 关于监管与公告谨慎的表态，2026下半年企业可能更少把裁员直接归因于AI。AI归因更像"预算从人力挪向AI"的叙事（"钱被AI拿走"），不宜当作因果替代量。
- 最稳健的结构性信号是入门级招聘收缩（Canaries 19%差距、AI Index 年轻开发者−20%、Wharton 24%预期减少入门招聘），而存量员工整体就业稳定（BTOS 96%不变、McKinsey 2/3无变化、丹麦零效应）。这意味着"学徒式"知识传承受冲击，也意味着"让新人更快上手"（Wharton 82%）是有需求的产品方向。
- "人+智能体团队"在2026年主要落在基础设施层（智能体身份、Agent 365 登记/治理、预算/FinOps、Custom Rules），"agent manager"作为正式岗位的规模证据有限；管理者能力（示范、设标准、给试错空间）被数据反复证明是关键变量。

### Gaps
- 2026年具体公司的AI相关裁员案例及事后核查（例如大型科技/金融公司公告）：本轮未获得一手来源。
- 对"AI-washing"（以AI为名的常规裁员）的系统性学术/智库评估（如 Yale Budget Lab 2026更新、Oxford Economics、NY Fed）：Yale 页面未能读取，其余未检索到。
- 美国以外（欧洲、英国、印度、日本）2026年劳动力影响数据：未找到。
- "AI operations / agent manager"等新岗位的招聘规模数据：未找到。

## 4. 产品趋势：从聊天助手到多步骤智能体；哪些场景ROI清晰、哪些令人失望

### Takeaway
2026年产品形态的四个跃迁：（1）从"问答式聊天"到"可委派、云端长时运行、返回成品"的智能体（Claude Cowork→Copilot Cowork→Autopilot / OpenAI Dots / Notion Custom Agents / Slackbot）；（2）"上下文层"（Work IQ、Teamwork Graph、Glean context graph、Box 内容层、Harvey Graph）成为差异化核心；（3）智能体获得身份、预算与治理（Agent 365、FinOps for AI、spend limits、Custom Rules）；（4）计价从席位转向"席位+用量"。ROI 最清晰的是编码、客服、文档抽取/处理与部分垂直流程（法律、金融分析、临床文书）；通用型助手的组织级财务回报仍不清晰，成本与质量（workslop）是主要失望点。

### Cited Findings

#### 从 Chat 到 Cowork 再到 Autopilot（常驻/后台智能体）
- 微软官方路线"from chat to Cowork to Autopilots"，Autopilots = 自主、长时运行、具备企业合规 — [Microsoft FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Copilot Cowork "你定义工作，Cowork 端到端执行并返回完成结果"，笔记本关机后任务仍在云端运行 — [Microsoft 365 Blog, 2026-06-16](https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/16/copilot-cowork-is-now-generally-available/)；Autopilot "持续、主动、个人化，你不在时也在工作" — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)
- Claude Cowork：给目标→跨文件与工具→交回成果，支持每日/每周/每月无人值守的定时任务 — [Claude Cowork 产品页](https://claude.com/product/cowork)
- OpenAI Dots：7×24、拥有独立云电脑与浏览器、空闲时只读"主动研究"（例：测试者的 dot 发现未发出的发票、准备好并在用户批准后发送）— [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- 生态侧：Notion 用户构建100万+ Custom Agents，并把 Claude Code/Cursor/Codex 作为可被分派任务的"同事" — [TechCrunch, 2026-05-13](https://techcrunch.com/2026/05/13/notion-just-turned-its-workspace-into-a-hub-for-ai-agents/)；Slackbot 作为个人智能体与 Agentforce 前门 — [Salesforce](https://www.salesforce.com/news/press-releases/2026/01/13/slackbot-announcement/)；M365 活跃智能体同比15倍 — [WorkLab](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)

#### 企业搜索 / 知识图谱 / "上下文层"
- Work IQ 为 Copilot 的"智能层"（2025-11首发，Copilot Chat 免费用户无法使用），Nadella："任何使用微软的公司，其最重要的底层数据库是 M365 之下的数据" — [No Jitter](https://www.nojitter.com/ai-automation/microsoft-365-copilot-hits-15-million-paid-seats)；2026-06 发布 Work IQ APIs — [Microsoft 365 Blog](https://www.microsoft.com/en-us/microsoft-365/blog/)
- Atlassian Teamwork Graph 200B+对象，称智能体答案准确度最高+44%、token −48%（厂商自述）— [Futurum](https://futurumgroup.com/insights/atlassian-q4-fy-2026-can-rovo-turn-ai-usage-into-durable-growth/)；Glean 以"context graph 减少 token、降低AI账单"销售 — [TechCrunch](https://techcrunch.com/2026/05/28/gleans-top-line-crosses-300m-as-ai-budget-cutting-becomes-its-major-selling-point/)；Box："文件是智能体的原生工作单元" — [Box 讲稿](https://s21.q4cdn.com/328470014/files/doc_earnings/2026/q4/transcript/Box-Q4-FY26-earnings-prepared-remarks.pdf)；Harvey Graph 提升智能体准确度 — [Harvey Blog](https://www.harvey.ai/blog)
- Gartner 2027 趋势将"AI context platforms"列为第4项 — [Network World, 2026-10](https://www.networkworld.com/article/4238030/gartners-top-tech-trends-for-2027-expand-and-constrain-ai-capabilities.html)

#### "AI coworker / 数字员工"与智能体治理
- Agent 365 = 智能体控制平面（观测、治理、管理、安全），GA $15/用户/月 — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)；注册近4000万个智能体；Purview 审计500亿+交互 — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- FinOps for AI（Agent 365 成本管理、策略控制、credit 申请流程）— [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)；Cowork 默认关闭、可设租户/组/用户预算 — [Microsoft 365 Blog, 2026-06-16](https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/16/copilot-cowork-is-now-generally-available/)；Claude Cowork 企业版 RBAC、预算、OpenTelemetry — [Claude Cowork](https://claude.com/product/cowork)；Anthropic Enterprise Frontier Safeguards（2026-09-01）— [Anthropic News](https://www.anthropic.com/news)
- Gartner：AI agent identity 列为2027趋势，预测到2028年25%的企业安全事件将可追溯到AI智能体滥用 — [Network World](https://www.networkworld.com/article/4238030/gartners-top-tech-trends-for-2027-expand-and-constrain-ai-capabilities.html)

#### 文档 / 表格 / 幻灯片生成
- Wave 3 把 agentic 体验带入 Word/Excel/PowerPoint/Outlook — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)；"Office in Copilot" — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)；Copilot in Excel for "Frontier Finance"（含季度结账分析等 skills，2026-06-25）— [Microsoft 365 Blog](https://www.microsoft.com/en-us/microsoft-365/blog/)
- OpenAI Pages（人与 dots 共同编辑的文档）— [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)；Claude for Microsoft 365 / Google Workspace 扩展 — [Claude Cowork](https://claude.com/product/cowork)；Harvey 在 Word 中运行自定义智能体 — [Harvey Blog](https://www.harvey.ai/blog)；Sheets canvas 迷你应用 — [Google Workspace Blog](https://workspace.google.com/blog)
- 需求侧：Anthropic EI 中工作类对话最常产出"文档和报告"（20%）— [Anthropic](https://www.anthropic.com/research/economic-index-june-2026-report)；Copilot 对话中"产出工作"占17% — [WorkLab](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)

#### 浏览器 / 电脑操作智能体
- Claude Cowork 内置浏览器（2026-08-26）与 computer use 研究预览（优先 connector→浏览器→屏幕，逐应用授权）— [Claude Cowork](https://claude.com/product/cowork)；Copilot Studio computer-using agents（2026-05-26）— [Microsoft 365 Blog](https://www.microsoft.com/en-us/microsoft-365/blog/)；OpenAI Agents API computer use — [InfoQ](https://www.infoq.com/news/2026/10/openai-devday-2026/)；每个 dot 有独立云端浏览器 — [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- 能力边界：OSWorld 约66%成功率 vs 人类72.35%，结构化基准上约1/3尝试失败 — [Stanford HAI](https://hai.stanford.edu/ai-index/2026-ai-index-report)

#### 垂直知识工作智能体
- 法律：Harvey $155亿估值、Harvey Agent、Legal Work Orchestration、与 LexisNexis 共建工作流 — [Harvey Blog](https://www.harvey.ai/blog)
- 金融：Barclays 扩大 Claude 部署（2026-10-01）— [Anthropic News](https://www.anthropic.com/news)；Copilot in Excel for Frontier Finance — [Microsoft 365 Blog](https://www.microsoft.com/en-us/microsoft-365/blog/)；Wells Fargo、HSBC 大规模 Copilot 采购 — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- 医疗：NHS England 为50.5万临床与员工部署 Copilot；UPMC 6万席+ — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Anthropic Life Sciences Verification Program（2026-09-17）— [Anthropic News](https://www.anthropic.com/news)；OpenAI Dots 对 Healthcare 工作区经管理员开启 — [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- 咨询/专业服务：KPMG 27.6万+、EY 40万（E7）— [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Accenture、Bain、Deloitte、McKinsey 参与 Claude Frontier Academy — [Anthropic News](https://www.anthropic.com/news)；McKinsey：专业服务38%因自建放弃购买软件 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)

#### 开放标准与互操作
- MCP 成为默认接口：Atlassian MCP server+CLI 100万+ MAU — [Futurum](https://futurumgroup.com/insights/atlassian-q4-fy-2026-can-rovo-turn-ai-usage-into-durable-growth/)；Dynamics 65万+ MCP actions — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；OpenAI 拟议 MCP Events — [InfoQ](https://www.infoq.com/news/2026/10/openai-devday-2026/)；Harvey 自定义 MCP — [Harvey Blog](https://www.harvey.ai/blog)；Anthropic 把 Agent Skills 捐给 Agentic AI Foundation，70+平台集成 — [Anthropic News](https://www.anthropic.com/news)
- 模型多元化/路由：Copilot 同时用 OpenAI 与 Anthropic — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)；USL 内"Auto"按准确度/速度/成本路由 — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)

#### ROI 清晰的场景
- 编码：GitHub Copilot 5000万用户、6月改价后消费超预期 — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；约两成企业规模化编码智能体（大企业31%），32%因 agentic coding 自建而放弃购买软件 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；Claude Code run-rate 2月超$25亿 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)；软件开发生产力约26% — [UNU C3](https://c3.unu.edu/blog/2026-stanford-ai-index-report-takeaways)
- 客服：Dynamics 365 客服 credit 消耗环比4倍 — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；客服生产力约14–15% — [UNU C3](https://c3.unu.edu/blog/2026-stanford-ai-index-report-takeaways)；Agentforce ARR 超$15亿 — [Salesforce 8-K](https://www.sec.gov/Archives/edgar/data/0001108524/000110852426000187/crm-q2fy27xexhibit991.htm)
- 文档抽取/内容流程：Box Enterprise Advanced 提价30–40%、一年占收入10%（保险保单、合同风险等抽取场景）— [Box 讲稿](https://s21.q4cdn.com/328470014/files/doc_earnings/2026/q4/transcript/Box-Q4-FY26-earnings-prepared-remarks.pdf)
- 会议纪要：Zoom My Notes 4个月150万+ MAU、付费 AI Companion MAU +184% — [Motley Fool](https://www.fool.com/earnings/call-transcripts/2026/05/21/zoom-zm-q1-2027-earnings-call-transcript/)
- 职能：省时最多为营销（60%）、IT（53%）、HR（50%），支持职能采用领先，销售与运营落后 — [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)
- 以增长指标衡量的部门强ROI比例是只看效率者的近3倍（35% vs 13%）— [GBK](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)

#### 令人失望 / 尚未证实的场景
- 组织级财务回报停滞：EBIT 37%、高绩效者6% — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；仅20%见收入增长 — [Libertify](https://www.libertify.com/interactive-library/state-of-ai-enterprise-2026-deloitte-survey/)；仅28%强ROI — [GBK](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)；CIO 称 ROI 低于预期 — [No Jitter](https://www.nojitter.com/ai-automation/microsoft-365-copilot-hits-15-million-paid-seats)
- 成本：1/5企业称 token 等成本限制使用，高绩效者在编码智能体上遇成本约束的可能性是他人3倍 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)；"许多公司正在烧穿AI预算" — [TechCrunch](https://techcrunch.com/2026/05/28/gleans-top-line-crosses-300m-as-ai-budget-cutting-becomes-its-major-selling-point/)；Copilot 使用增加压低微软分部毛利率 — [FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- 质量与负担：workslop（见第2节）、41%认知负担加重 — [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)
- 自主性受限：仅17%允许智能体自主行动 — [GBK](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)；大多数职能智能体部署仍为个位数 — [Stanford HAI](https://hai.stanford.edu/ai-index/2026-ai-index-report)
- 席位型 SaaS 的 AI 增量有限：Salesforce Agentforce Apps 订阅收入按固定汇率仅+8% — [Salesforce 8-K](https://www.sec.gov/Archives/edgar/data/0001108524/000110852426000187/crm-q2fy27xexhibit991.htm)；Box FY26 收入+8% — [Box 讲稿](https://s21.q4cdn.com/328470014/files/doc_earnings/2026/q4/transcript/Box-Q4-FY26-earnings-prepared-remarks.pdf)

### Inferences
- 2026年"AI coworker"从口号落地为三件具体的东西：①可委派并在云端长时运行的任务执行器（Cowork 类）；②常驻、主动、拥有身份的个人/团队智能体（Autopilot/Dots）；③面向 IT 的智能体登记、身份、预算与审计（Agent 365/FinOps）。2027年竞争焦点将从"模型能力"转向"谁掌握工作上下文（图谱/文件/对话）+谁掌握智能体治理"。
- ROI 清晰的场景有共同特征：产出可验证（代码、工单、抽取字段、会议纪要）、流程边界清楚、有天然计量单位（credit、AWU、AI unit）。通用"写作/总结"类助手的价值更难量化且易产生 workslop。
- 用量计价使"AI预算超支"成为新痛点，催生"降 token"卖点（Glean、Atlassian 自称 token −48%、微软称 Copilot Cowork 比 Claude Cowork 便宜30–40%）与 FinOps for AI 品类——2027年成本治理与模型路由会成为企业采购的核心评估项。
- McKinsey 的"32%因可自建而放弃购买软件"与 Gartner "disposable applications"趋势相互印证：agentic coding 正在侵蚀部分轻量 SaaS 的购买需求，是工作场景 SaaS 厂商的结构性风险。

### Gaps
- 浏览器智能体（如 ChatGPT Atlas、Perplexity Comet、Claude in Chrome）在企业工作场景的2026年采用数据：未找到。
- 法律以外垂直智能体（金融研究如 Hebbia、临床文书如 Abridge/Nuance DAX）的2026年营收/客户数据：未检索到（搜索额度用尽）。
- Harvey 2026年 ARR/客户数及其$155亿估值轮次的具体日期：官方博客未显示。
- 企业对 Copilot Cowork vs Claude Cowork 的实际采购对比数据：仅有微软自测成本数据。

## 5. 厂商与分析师对2027年 AI at work 的预期

### Takeaway
2027年的共识方向是"从采用到治理与变现"：Gartner 2027战略趋势把"AI上下文平台、AI智能体身份、编码智能体 harness"列为核心，并维持"2027年底前40%+ agentic 项目被取消"的警示；Forrester 预计 AI 将占2027年企业技术支出的20%，同时"AI 的空白支票即将到期"、需证明回报；厂商则押注常驻/自主智能体（Autopilots、Dots）+"席位+用量"定价，企业调查显示投资与智能体整合预期仍上行，而入门级招聘预计继续收缩。

### Cited Findings

#### 分析师
- Gartner 2027 十大战略技术趋势（2026-10-20，IT Symposium）：分"利用非文本AI前沿（1–3年）/治理自主智能体平台（3–5年）/构建持久敏捷（5年+）"三阶段；主要预测：到2027年，重视 AI-ready 数据语义的组织可将 agentic AI 准确度提升最高80%、成本降低最高60%（AI context platforms）；到2026年底自主编码智能体将生成20%的公共代码提交（AI coding agent harness）；到2028年25%的企业安全事件可追溯到AI智能体滥用（AI agent identity）；到2030年70%+的企业语音交互将被自主处理（2026年<10%）；到2030年领先组织80%的新应用将是"可丢弃应用"；到2030年LQM在25%的战略预测/运营建模任务中替代LLM — [Network World, 2026-10](https://www.networkworld.com/article/4238030/gartners-top-tech-trends-for-2027-expand-and-constrain-ai-capabilities.html)；Gartner 称2027年的议题"从采用转向治理"（搜索摘要）— [Gartner 新闻稿, 2026-10-20](https://www.gartner.com/en/newsroom/press-releases/2026-10-20-gartner-identifies-the-top-strategic-technology-trends-for-2027)
- Gartner 既有预测（仍被2026年引用）：到2027年底超40%的 agentic AI 项目将被取消（2025-06提出）— [BigDATAwire](https://www.hpcwire.com/bigdatawire/this-just-in/gartner-predicts-over-40-of-agentic-ai-projects-will-be-canceled-by-end-of-2027/)；"到2027年，GenAI 与AI智能体将对主流生产力工具构成约30年来首次真正挑战，引发约$580亿的市场洗牌"（2025-10 预测，各转述为30或35年；搜索摘要，原文403）— [Gartner 新闻稿, 2025-10-21](https://www.gartner.com/en/newsroom/press-releases/2025-10-21-gartner-unveils-top-predictions-for-it-organizations-and-users-in-2026-and-beyond)；到2028年至少15%的日常工作决策将由 agentic AI 自主做出（搜索摘要，经 qz.com 2026-10 转述）— [Quartz](https://qz.com/ai-agents-workplace-gartner)
- Forrester Predictions 2027（预测页摘要）：AI 将占2027年企业技术支出的20%；"AI 的空白支票即将到期"，CMO 等需证明价值足以覆盖上升的成本与风险；agentic buying 将参与75%的B2B采购；"随着信任侵蚀，AI厂商、企业领导、员工与客户都将要求更大控制权"；AI 故障、全球宕机将考验安全与风险负责人 — [Forrester Predictions](https://www.forrester.com/predictions/)
- IDC（微软引用）：到2028年将有13亿个智能体在运行 — [Microsoft Blog, 2026-03-09](https://blogs.microsoft.com/blog/2026/03/09/introducing-the-first-frontier-suite-built-on-intelligence-trust/)

#### 调查中的前瞻预期
- McKinsey 2026：60%预计明年AI投资增加 — [BIP Capital](https://www.bipcapital.com/insights/the-six-percent-reading-mckinseys-state-of-ai-in-2026-as-an-investor)
- Deloitte 2026：74%预计两年内（约至2027–28）中度至全面整合 agentic AI，重点在客服、供应链、研发 — [Libertify](https://www.libertify.com/interactive-library/state-of-ai-enterprise-2026-deloitte-survey/)
- BCG 2026：61%认为三年内智能体可完成其至少一半工作（领导与经理预期变化最大）— [BCG](https://www.bcg.com/publications/2026/ai-at-work-why-strategy-matters-more-than-tools)
- Wharton–GBK 2026：未来12–24个月首要AI目标为生产力/降本（52%）vs 业务增长（22%）；24%预计2–5年内减少入门级招聘 — [GBK Collective](https://www.gbkcollective.com/thoughtleadership/wharton-gbk-ai-study-2026-press-release)
- Anthropic EI 2026-06：超1/3预计12个月内AI可处理其大部分或几乎全部工作任务；近6成为明年选择了更高的暴露区间 — [Anthropic](https://www.anthropic.com/research/economic-index-june-2026-report)

#### 厂商指引与路线图
- Microsoft：转向"per-seat-plus-consumption"；Amy Hood 预计 M365 商业云增长在 FY27（2026-07至2027-06）内逐季加速；Copilot 合并为横跨消费/商业的"super app"；Autopilots 为下一阶段 — [Microsoft FY26 Q4 Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Autopilot 私测、Home/Code 经 Frontier 推出、Code 面向 M365 Premium/Pro 预览，Ignite 2026-11-17至20 — [Microsoft Blog, 2026-09-25](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/)
- Salesforce：FY27（至2027-01）收入指引$461–464亿；Slackbot 将编排 Agentforce 与第三方智能体 — [Salesforce 8-K](https://www.sec.gov/Archives/edgar/data/0001108524/000110852426000187/crm-q2fy27xexhibit991.htm)；[Salesforce 新闻稿](https://www.salesforce.com/news/press-releases/2026/01/13/slackbot-announcement/)
- Atlassian：FY27 指引 Cloud 约+25.5%、总收入约+13%，测试消费制超额与"Flex" — [Futurum](https://futurumgroup.com/insights/atlassian-q4-fy-2026-can-rovo-turn-ai-usage-into-durable-growth/)
- Zoom：FY27 收入指引$50.8–50.9亿 — [Motley Fool](https://www.fool.com/earnings/call-transcripts/2026/05/21/zoom-zm-q1-2027-earnings-call-transcript/)
- OpenAI：企业收入有望在2026年底与消费持平（搜索摘要）— [OpenAI](https://openai.com/index/next-phase-of-enterprise-ai/)；Dots 向 Enterprise/Edu/Healthcare 推出、ChatGPT Space、插件4,000+应用 — [BGR](https://www.bgr.com/2272332/openai-devday-2026-announcements/)
- Anthropic：Series H 资金用于扩展算力并"把 Claude 带到更多工作发生的地方" — [Anthropic Series H](https://www.anthropic.com/news/series-h)；与 Accenture 5年$10亿+嵌入式评估、$1亿 Frontier Academy — [Anthropic News](https://www.anthropic.com/news)
- Box：FY27 推出下一代长时运行智能体功能与 Box Automate，"企业内智能体将增加百倍" — [Box 讲稿](https://s21.q4cdn.com/328470014/files/doc_earnings/2026/q4/transcript/Box-Q4-FY26-earnings-prepared-remarks.pdf)
- Notion："Any data, any tool, any agent" — [TechCrunch](https://techcrunch.com/2026/05/13/notion-just-turned-its-workspace-into-a-hub-for-ai-agents/)

### Inferences
- 2027年 AI at work 的关键词（综合上述）：①常驻/自主智能体规模化（Autopilot、Dots）与"人在环→人在监督"的过渡；②治理（智能体身份、审计、评估、FinOps）成为采购门槛；③上下文层（图谱/语义/文件系统）成为差异化与"降 token"抓手；④"席位+用量"定价全面铺开，企业需要 AI 成本预算与 chargeback 机制；⑤ROI 度量从"节省工时"转向"增长与流程重构"指标；⑥入门级岗位与培训体系重构。
- 风险情景：Gartner 的40%项目取消、Forrester 的"空白支票到期"，与 McKinsey 1/5企业受成本约束、EBIT 影响停滞相互印证——2027年可能出现"智能体项目出清 + 预算向少数可证明ROI场景（编码、客服、文档处理、垂直流程）集中"的分化。
- 微软3000万席位、Google 800万+席位、Anthropic/OpenAI 企业收入高速增长说明需求端仍在扩张；但从30M/450M 渗透率看，2027年最大的增量空间仍在"从少数高价值用户走向全员"，这取决于用量定价下的单位经济性能否改善（微软的"Cowork 1"低成本模型、Auto 路由即为此）。

### Gaps
- Microsoft Ignite 2026（11-17至20）、Microsoft FY27 Q1/Alphabet Q3 2026 财报的2027指引：截至2026-10-23尚未发生或未覆盖。
- Forrester 2027 完整预测（付费墙）、IDC FutureScape 2027、Gartner 2027 Top Strategic Predictions（通常与趋势同期发布）的具体条目：未能获取。
- OpenAI、Google 对2027年企业AI的量化目标：未找到一手表述。
- 欧洲（EU AI Act 2026-08 起高风险义务等）监管对工作场景AI部署节奏的影响：本轮未研究。
