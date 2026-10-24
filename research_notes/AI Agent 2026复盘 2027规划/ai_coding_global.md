# 2026年全球AI Coding市场回顾（AI编程助手 / 编程Agent / AI应用构建器，2026年1–10月，不含中国本土工具）

> 研究截止：2026-10-23/24。除特别标注"背景（2025）"外，以下事实均为2026年。
> 标注说明：**[二手]** = 来自聚合站/博客/二次报道，未在一手来源核实；**[未证实]** = 传闻、匿名信源或数字冲突；**[推算]** = 本笔记基于引用数据自行计算。
> 说明：WebSearch额度在调研中途一度用尽，之后主要靠WebFetch抓取已知的一手页面（官方博客、定价页、财报会、TechCrunch、Wikipedia等），结束前又补了4次搜索。部分空白见各节"Gaps"。

---

## 1. 主要玩家与2026年关键指标（收入/ARR、用户、估值、发布时间线）

### Takeaway
2026年市场格局变成"实验室直营Agent主导 + 头部应用被实验室收编 + 少数高估值独立公司"。Claude Code是事实上的品类领导者：2月run-rate已超$25亿，Stack Overflow 2026调查中Agent使用率第一（66%）。OpenAI Codex周活从年初约40万涨到6月的500万以上。Cursor在ARR约$30亿时被SpaceX（xAI）以约$600亿全股票收购。GitHub Copilot用户达5000万，6月改为按量计费。独立公司仍拿到高估值：Cognition（$480亿，ARR $9亿）、Lovable（$133亿，ARR $5亿）、Replit（$90亿）、Factory（$50亿）。

### Cited Findings

#### Anthropic / Claude Code
- **Claude Code收入**：上线后6个月内年化收入达$10亿；截至2026年2月run-rate超过$25亿；1月1日至2月期间周活用户（WAU）翻倍；2026年初以来企业订阅数翻了两番 — [VentureBeat, 2026-05-08](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)；2月12日的数据点来自Anthropic的Series G公告（经[Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)转引）。背景（2025）：2025年9月Claude Code run-rate约$5亿（同上，Exploding Topics引Series F公告）。
- 2026年2月以后**没有找到Anthropic官方公布的Claude Code单独收入**。网上流传的$80亿、$150亿等数字来自预测或追踪站 — [二手/未证实] [搜索汇总所引gradually.ai等](https://www.gradually.ai/en/claude-code-statistics/)。
- **使用强度**：2026年5月Code with Claude大会上，Anthropic称平均每位开发者每周使用Claude Code 20小时，公司内部多数代码已由Claude Code编写 — [VentureBeat, 2026-05-08](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。
- **GitHub提交占比**：约4%的公开GitHub commit由Claude Code撰写（METR转引SemiAnalysis，2026年2月） — [METR, 2026-02-24](https://metr.org/blog/2026-02-24-uplift-update/)。
- **Anthropic整体run-rate（编程是主要驱动）**：2024年12月$10亿 → 2025年底约$90亿 → 2026年2月$140亿 → 3月$190亿 → 4月$300亿。Amodei称Q1年化增长80倍，而公司按"每年10倍"做的规划。OpenAI认为$300亿因云伙伴收入（AWS/Google Cloud）的计法高估了约$80亿 — [VentureBeat, 2026-05-08](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。2026年5月超过$470亿 — [Verdict via Yahoo Finance, 2026-05-29](https://finance.yahoo.com/markets/stocks/articles/anthropic-raises-65bn-series-h-110356689.html)。2026年7月底$650亿（Bloomberg/CNBC匿名信源报道，公司未公布） — [二手/未证实] [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)。NYT（9月，匿名信源）称年内有望达到$1000亿run-rate — [未证实] 同上。
- **客户**：年支出超过$100万的企业客户超过1000家，比2月翻倍 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。2026年2月Claude Code收入中企业占比过半 — [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)。
- **融资/估值**：Series G于2026年2月完成，$300亿，投后$3800亿，GIC、Coatue领投 — [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)，[VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。Series H于2026年5月29日公布，$650亿（含此前超大规模云厂商承诺的$150亿，其中Amazon $50亿），投后$9650亿，Altimeter、Dragoneer、Greenoaks、Sequoia领投 — [Verdict via Yahoo Finance](https://finance.yahoo.com/markets/stocks/articles/anthropic-raises-65bn-series-h-110356689.html)。IPO方面：Bloomberg报道最早2026年10月，高盛、摩根大通、摩根士丹利参与早期讨论 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)；10月1日Bloomberg报道目标约$2万亿、最早11月中旬上市 — [二手/未证实] [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)。
- **算力合作（与"实验室-客户"关系有关）**：2026年5月从SpaceX获得Colossus 1算力（超过300MW、超过22万张Nvidia GPU）；Amazon投资最高$250亿、对应最多5GW；Google/Broadcom 5GW — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。
- **编程相关模型时间线**：Opus 4.6（2月5日，带agent teams）；Sonnet 4.6（2月17日）；Mythos Preview（4月7日，仅向Project Glasswing伙伴开放）；Opus 4.7（4月16日）；Opus 4.8（5月28日）；Fable 5 / Mythos 5（6月9日）；Sonnet 5（6月30日）；Opus 5（7月24日）；Fable 5.1 / Mythos 5.1（9月1日）；Opus 5.5（9月22日）；Sonnet 5.5（9月28日）；Haiku 5.5（10月7日） — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_(language_model))。
- **Fable 5**：Mythos级模型加安全分类器后对公众开放，定价$10/$50（每百万token输入/输出），面向"多日、异步"任务。官方案例：Stripe的5000万行Ruby代码库迁移1天完成（人工需2个月以上）；Mythos 5近乎自主地做了一周以上的基因组研究。Cursor CEO Michael Truell称其"打开了此前够不着的一类长时程问题"；Cognition称其在FrontierBench上得分最高 — [Anthropic, 2026-06-09](https://www.anthropic.com/news/claude-fable-5-mythos-5)。6月12日因美国商务部出口管制指令下线，7月1日加装新的网络安全分类器后重新上线 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)，[Anthropic](https://www.anthropic.com/news/redeploying-fable-5)。
- **Claude Code 2026年官方产品时间线（周报）** — [Claude Code What's new](https://code.claude.com/docs/en/whats-new)：
  - 3/23–27：auto mode研究预览（由分类器代替权限确认）；Desktop支持computer use；Web端支持PR auto-fix
  - 3/30–4/3：CLI支持computer use
  - 4/6–10：Ultraplan（在云端起草计划、网页上评审、远程执行）；Monitor工具；/loop
  - 4/13–17：Opus 4.7成为默认模型，新增xhigh effort；Web端上线**Routines**（按定时、GitHub事件或API触发模板化云Agent）；手机推送通知；CLI改为原生二进制
  - 4/20–24：/ultrareview研究预览（云端多个找bug的Agent组成"舰队"）；Web端改版
  - 4/27–5/1：`claude ultrareview`接入CI；Windows不再依赖Git Bash
  - 5/11–15：Agent view（`claude agents`，一个界面管理所有会话）；/goal（持续工作直到满足完成条件）
  - 5/18–22：auto mode开放给Pro；/usage按skill/subagent/plugin/MCP拆分用量；/code-review
  - 5/25–29：Opus 4.8成为默认；**dynamic workflows**（Claude写脚本编排几十到上百个subagent）
  - 6/8–12：subagent可再派生subagent（最多5层）
  - 6/15–19：Artifacts（Team/Enterprise beta）
  - 6/29–7/3：Sonnet 5成为Pro/Team Standard/Enterprise默认；subagent默认后台运行；Linux版Desktop beta
  - 7/6–10：Desktop内置浏览器
  - 7/20–24：Opus 5成为默认Opus（1M上下文）；iOS Simulator窗格；Claude Security插件（多Agent漏洞扫描）
  - 8/3–7：跨会话消息；云会话的**自托管环境**（Team/Enterprise公测）；8月14日起auto mode成为Pro/Max/Team新会话的默认权限模式
  - 8/10–14：触及用量上限后自动续跑；fork mode默认开启
  - 8/17–21：/design（Claude Design画板）；手机上可看到远程设备卡片
  - 8/31–9/4：Fable 5.1上线（1M上下文）
  - 9/7–11：`claude plugin eval`
- **其他Claude Code/Cowork里程碑**：
  - 2025/26年假期Claude Code走红，大量非程序员用它vibe coding — [Wikipedia: Claude Code（引Axios 2026-01-07、WSJ 2026-01-17、NYT 2026-01-23）](https://en.wikipedia.org/wiki/Claude_Code)
  - 2026年1月微软被报道内部采用Claude Code — [同上（引The Verge 2026-01-22）](https://en.wikipedia.org/wiki/Claude_Code)
  - Cowork于2026年1月推出，开发者称其大部分由Claude Code构建 — [同上（引Mashable 2026-01-14）](https://en.wikipedia.org/wiki/Claude_Code)
  - 2月20日推出Claude Code Security；2月24日Cowork企业版上线插件 — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_(language_model))
  - 背景（2025）：Claude Code于2025年2月发布，2025年5月GA，2025年10月20日推出Web版 — [Wikipedia: Claude Code](https://en.wikipedia.org/wiki/Claude_Code)
- **Agent SDK / 生态**：2026年5月Managed Agents API推出"Dreaming"记忆整合研究预览 — [Wikipedia: Claude Code（引VentureBeat 2026-05-07）](https://en.wikipedia.org/wiki/Claude_Code)。2026年10月22日Anthropic把Agent Skills捐给Agentic AI Foundation — [Anthropic News](https://www.anthropic.com/news)。约10月17日上线官方插件仓库和"Mods"系统 — [二手] [tech-insider](https://tech-insider.org/claude-code-plugins-official-mods-cloud-sessions-2026/)。

#### Cursor（Anysphere）→ 被SpaceX收购
- **ARR**：背景（2025）：2025年1月超$1亿，6月超$5亿，11月Series D（$23亿，投后$293亿）时超$10亿 — [Wikipedia: Cursor (company)](https://en.wikipedia.org/wiki/Cursor_(company))。2026年3月2日Bloomberg报道经常性收入3个月内翻倍至约$20亿 — [Cursor blog press列表](https://cursor.com/blog)。2026年5月21日Bloomberg报道年化销售额$30亿 — [Wikipedia: Cursor (company)](https://en.wikipedia.org/wiki/Cursor_(company))。TechCrunch春季报道称年底有望超过$60亿ARR — [TechCrunch, 2026-09-08](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)。Getlatka估算$40亿 — [二手/估算] [Getlatka](https://getlatka.com/companies/cursor.com)。
- **SpaceX收购**：
  - 2026年4月曾洽谈以约$500亿估值融资$20亿 — [TechCrunch](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)
  - 4月21日SpaceX宣布获得年内以$600亿收购Cursor的权利，或改为支付$100亿做联合工作 — [Wikipedia（引CNBC 2026-04-21）](https://en.wikipedia.org/wiki/Cursor_(company))
  - 6月16日宣布以全股票方式行权；8月14日交割，换成389,289,254股SpaceX A类股（按7日VWAP约$600亿），Cursor并入"SpaceXAI"团队 — [Wikipedia（引SEC 8-K）](https://en.wikipedia.org/wiki/Cursor_(code_editor))，[Cursor blog「Cursor is now a part of SpaceX」2026-08-14](https://cursor.com/blog)
  - 投资人称Cursor卖身的主要原因是**算力严重受限** — [TechCrunch, 2026-09-08](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)
- **自研模型**：2026年3月发布Composer 2，基座是月之暗面的开源权重模型Kimi K2.5，用户先发现了这一点公司才披露。Lee Robinson称最终模型约1/4的算力来自基座；Aman Sanger承认一开始没在博客里提Kimi基座是"失误" — [Wikipedia（引TechCrunch 2026-03-22、Business Insider）](https://en.wikipedia.org/wiki/Cursor_(company))。被收购后，Cursor博客发布了Grok 4.6（8月12日）和Grok 4.7（9月21日，"长时程编码与知识工作最强模型"） — [Cursor blog](https://cursor.com/blog)。
- **2026年产品/并购**：Firetiger加入Cursor（8月13日）；AIUC-1 Agent安全认证；Cursor Router模型路由（8月6日）；云Agent启动提速3倍；可在自管机器上运行云Agent（9月2日）；Projects（9月10日）；Rollouts与Security Review机器人（9月23日）；本地Agent远程控制（10月6日）；**Origin App Marketplace**（10月13日）；云Agent画布（10月16日） — [Cursor blog](https://cursor.com/blog)。CodeRabbit是Origin应用市场的首发伙伴，"为托管在Origin上的PR做独立校验" — [CodeRabbit blog, 2026-10-13](https://www.coderabbit.ai/blog)。背景（2025）：2025年12月19日收购代码评审公司Graphite — [Wikipedia](https://en.wikipedia.org/wiki/Cursor_(company))。

#### OpenAI Codex
- **用户增长**：2025年9月至2026年1月，Codex使用量从约为Claude Code的5%升到约40% — [Wikipedia: Codex（引WIRED 2026-03-11）](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))。WAU：3月4日160万（Fortune）；3月中旬超200万，为年初的5倍（Reuters 3月19日） — [同上](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))；6月2日超500万，其中知识工作者（非开发者）约占20% — [Constellation Research（引OpenAI报告）](https://www.constellationr.com/insights/news/openai-touts-broadening-codex-usage-5-million-weekly-active-users)；7月13日约700万，7月21日Codex加ChatGPT Work合计约1000万 — [二手/未证实，口径不明] [Startup Fortune](https://startupfortune.com/openais-codex-and-chatgpt-work-just-crossed-10-million-weekly-users-and-the-coding-wars-have-a-new-shape/)。
- **2026年发布时间线** — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))：
  - 2月2日：Codex桌面app（管理多个Agent）
  - 2月3日：Xcode 26.3集成
  - 2月4日：进入GitHub Agent HQ（公开预览）
  - 2月5日：GPT-5.3-Codex
  - 约2月12日：Codex-Spark，跑在Cerebras上，约快15倍；同期投放超级碗广告
  - 3月初：Windows版
  - 3月5日：GPT-5.4
  - 3月6日：Codex Security
  - 3月19日：宣布把ChatGPT、Atlas、Codex合并为超级app，并收购Astral（Python工具链公司）
  - 3月27日：企业插件
  - 4月：Reuters报道受Claude Code压力，OpenAI把资源转向Codex和企业工具
  - 6月22–23日：与Trail of Bits合作"Patch the Planet"
  - 7月9日：Codex app与ChatGPT桌面版合并
- **模型**：GPT-5.5于4月23日发布（Codex内400K上下文；Fast mode速度1.5倍、价格2.5倍；API $5/$30） — [VentureBeat, 2026-04-23](https://venturebeat.com/technology/openais-gpt-5-5-is-here-and-its-no-potato-narrowly-beats-anthropics-claude-mythos-preview-on-terminal-bench-2-0)。GPT-5.6 Sol/Terra/Luna于7月9日发布，Sol被称为OpenAI"最强编码模型"，Codex内可用 — [OpenAI](https://openai.com/index/gpt-5-6/)，[Artificial Analysis](https://artificialanalysis.ai/articles/gpt-5-6-has-landed)。GPT-6 Astra于9月3–4日发布（网络安全受限版）；GPT-6 Sol/Luna于9月22日；GPT-6 Instant于10月7日 — [Wikipedia: GPT-6](https://en.wikipedia.org/wiki/GPT-6)。
- **企业客户**：Cisco、Nvidia、Ramp、Rakuten、Harvey在开发团队中部署Codex — [Wikipedia（引Fortune 2026-03-04）](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))。

#### GitHub Copilot（Microsoft）
- **FY26 Q4财报会（2026-07-29）**，来源均为 [Microsoft IR](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)：
  - "GitHub Copilot now has 50 million users"；GitHub总用户2.25亿，覆盖90%以上的Fortune 500
  - "Copilot revenue accelerated over 60% quarter-over-quarter"
  - 本季度推出按量计费；Amy Hood称"6月商业模式调整后，GitHub Copilot消费强于预期"，同时Copilot用量增长拖累了分部毛利率，但季内有所改善
  - "one in three pull requests on GitHub now involves an agent"
  - 自研MAI-Code-1-Flash已有"数百万开发者"使用，代码采纳率更高，中位token用量低10%
- **付费用户**：2026年1月（FY26 Q2）付费订阅470万，同比增长75%；背景（2025）：总用户2025年7月约2000万，10月超2600万 — [二手] [搜索汇总所引getpanto](https://www.getpanto.ai/blog/github-copilot-statistics)。
- **GitHub Copilot当前定价（2026年10月访问）**：
  - Free；Pro $10（含$10基础加$5 flex额度）；Pro+ $39（$39加$31）；新增**Max $100**（$100加$100）；1 AI credit = $0.01
  - 云Agent（把任务派给Copilot生成PR）限Pro/Pro+/Max；委派给第三方Agent（Claude、Codex）为预览功能，限Pro+/Max；代码补全不消耗credit
  - 模型列表包括Fable 5/5.1、Opus 5.5、GPT-6.1系列、MAI-Code-1.1-Flash、Gemini、Grok 4.5–4.7、Kimi K3
  - 来源：[GitHub Copilot Plans](https://github.com/features/copilot/plans)
- 7月24日Copilot上线Claude Opus 5 — [GitHub Changelog](https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot/)。
- 9月16日第九巡回法院在Doe v. GitHub案中维持驳回DMCA诉求，开源许可违约诉求未决 — [Wikipedia: GitHub Copilot（引Reuters）](https://en.wikipedia.org/wiki/GitHub_Copilot)。

#### Google（Antigravity / Gemini CLI / Jules / Windsurf授权）
- 背景（2025）：2025年7月Google以$24亿授权Windsurf技术，并聘请Varun Mohan等人；2025年11月18日随Gemini 3发布Antigravity — [Wikipedia: Google Antigravity](https://en.wikipedia.org/wiki/Google_Antigravity)。
- 2026年2月19日Gemini 3.1 Pro进入Antigravity。2月Google以恶意使用拖累服务为由，封禁了接入第三方Agent OpenClaw的用户 — [同上（引VentureBeat 2026-02-23）](https://en.wikipedia.org/wiki/Google_Antigravity)。
- **I/O 2026（5月19日）**：
  - Antigravity 2.0独立桌面应用：并行多Agent、动态subagent、定时后台任务
  - Antigravity CLI（Go编写）和Antigravity SDK
  - Gemini API推出Managed Agents（基于Antigravity harness和Gemini 3.5 Flash）
  - AI Studio新增原生Android支持，可一键导出到Antigravity
  - 新增**$100/月AI Ultra**（Antigravity额度为Pro的5倍）
  - 来源：[Google Blog, 2026-05-19](https://blog.google/innovation-and-ai/technology/developers-tools/google-io-2026-developer-highlights/)；最高档Ultra从$250降到$200 — [Wikipedia（引TechCrunch）](https://en.wikipedia.org/wiki/Google_Antigravity)
- **Gemini CLI退场**：5月19日Antigravity CLI向所有人开放；6月18日起Gemini CLI和Code Assist IDE扩展对AI Pro/Ultra及免费个人用户停止服务，企业Code Assist许可不受影响。Gemini CLI此前有10万以上GitHub star、6000个合并PR、"数百万用户" — [Google Developers Blog, 2026-05-19](https://developers.googleblog.com/an-important-update-transitioning-gemini-cli-to-antigravity-cli/)。开发者批评新CLI闭源 — [The Register, 2026-05-20](https://www.theregister.com/ai-ml/2026/05/20/bye-bye-gemini-cli-google-nudges-devs-toward-antigravity/5243605)，用量上限更紧 — [The New Stack](https://thenewstack.io/google-antigravity-cli/)。
- Gemini 3.5 Pro截至10月仍未发布，Bloomberg报道原因是编码表现未达内部目标 — [二手/未证实] [AIToolsReview](https://aitoolsreview.co.uk/insights/gemini-3-5-pro)，[TheAIRankings](https://theairankings.com/google/gemini-3-5-pro/)。
- 2026年1月Linus Torvalds用Antigravity给个人项目vibe-code了一个可视化工具 — [Wikipedia: Vibe coding（引ZDNET 2026-01-12、Ars Technica 2026-01-13）](https://en.wikipedia.org/wiki/Vibe_coding)。

#### Cognition（Devin + Windsurf）
- 背景（2025）：2025年9月融资$4亿，投后$102亿 — [TechCrunch, 2026-05-27](https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/)。
- **2026年5月27日**：融资超$10亿，投前$250亿/投后$260亿，Lux、General Catalyst、8VC领投；ARR $4.92亿；Devin企业用量连续6个月环比增长50%；客户包括Mercedes-Benz、NASA、Goldman Sachs、Santander — [TechCrunch](https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/)。
- **2026年9月8日**：融资$20亿，估值$480亿，a16z领投（另有Accel、Founders Fund、General Catalyst、Avenir）；run-rate $9亿。The Information预测年底达$40–50亿；公司租用的Nvidia集群每年花费数亿美元，全年现金消耗可能达$8亿；为降本正在基于开源模型训练自有模型 — [TechCrunch](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)。
- 2026年6月Windsurf更名为Devin Desktop；2026年3月员工约200人（SF Standard） — [Wikipedia: Cognition AI](https://en.wikipedia.org/wiki/Cognition_AI)。"Cognition 89%的代码由Devin编写" — [二手/未证实] [tech-insider](https://tech-insider.org/ie/cognition-devin-26-billion-2026/)。

#### AI应用构建器（vibe coding平台）
- **Lovable**：背景（2025）：2025年11月ARR $2亿（Bloomberg）；12月Series B $3.3亿，估值$66亿 — [Wikipedia: Lovable](https://en.wikipedia.org/wiki/Lovable_(company))。2026年6月ARR $5亿；8月12日Series C $4亿，估值$133亿（Menlo、Scaleup Europe Fund领投）；平台上有6000万个项目，月访问9亿；6月签下多年期Google Cloud协议，用量提升5倍；有自研模型 — [TechCrunch, 2026-08-12](https://techcrunch.com/2026/08/12/lovable-confirms-new-13-3b-valuation-raises-another-400m/)。9月ARR $6亿 — [二手/未证实] [Okara](https://okara.ai/blog/how-lovable-grew)。
- **Replit**：2026年3月Series D $4亿，估值$90亿，Georgian领投（半年内估值涨到3倍） — [Trending Topics](https://www.trendingtopics.eu/replit-raises-400m-tripling-its-valuation-to-9-billion-in-six-months/)，[Sacra](https://sacra.com/c/replit/)。
  - 年化收入：2025年底约$3亿，2026年4月约$5.25亿 — [Sacra估算，非公司披露](https://sacra.com/c/replit/)
  - 用户：2026年3月超5000万
  - 产品：Agent 4于2026年3月上线Web，5月上线iPhone（此前与Apple的App Store审核纠纷持续4个月）
  - 定价：Core从$25降到$20，新增$100 Pro，改为effort-based计价
  - 来源：[Sacra](https://sacra.com/c/replit/)；公司此前称目标是2026年底run-rate $10亿 — [二手] [TechBuzz](https://www.techbuzz.ai/articles/replit-hits-9b-valuation-eyes-1b-arr-in-monster-round)
- **Vercel v0**：2月3日推出面向企业的新v0（git工作流、安全）；8月5日推出v0 API（无界面生成应用，在Vercel Sandbox里预览）；2026年没有披露用户数或营收 — [Vercel blog](https://vercel.com/blog)。
- **Bolt.new**：未找到2026年数据（见Gaps）。

#### 其他重要玩家（2026年动态）
- **Factory**：2026年9月15日融资$2亿，估值$50亿；推出Factory Router（称推理成本降63%，9月23日）、Automations、Analytics、Environments、OpenCompute（客户自托管的沙盒编排器）；上架Claude Marketplace（9月9日）和OpenAI B2B市场（9月29日）；与Databricks合作（10月19日）；收购Mentlio（10月9日）；Blackstone案例 — [Factory News](https://factory.com/news)。其Agent Droid（GPT-5.3-Codex）在Terminal-Bench 2.0上得77.3% — [Snorkel/TB2榜单](https://snorkel.ai/leaderboard/terminal-bench-2-0/)。
- **Augment Code**：主打"Cosmos" Software Factory；Prism模型路由（5月2日）；7月29日Cosmos默认模型换成GPT-5.6 Sol；8月14日Auggie CLI harness重构，标题称任务成本"比Claude Code低53%"；10月8日发布"Augment Code's next chapter"（内容未能读取） — [Augment blog](https://www.augmentcode.com/blog)。
- **Amp（原Sourcegraph）**：
  - 2025年12月2日拆分为独立公司
  - 2月10日Amp Free满额、放缓增长；3月30日Free去掉广告
  - 7月18日推出月度订阅，可绑定ChatGPT订阅；9月13日自带算力/订阅/key即可免费使用；10月10日可"零成本使用你的Claude订阅"
  - 多模型分工：GPT-5.4作Oracle、Opus 4.7作smart、GPT-5.5作deep、Fable 5.1作ultra、GPT-6 Astra
  - 来源：[Amp News](https://ampcode.com/news)
- **Warp**：转向"software factories"，例如Warp Factories支持Microsoft Teams和Azure DevOps（10月7日）、"Sign in to Warp with ChatGPT"（9月29日） — [Warp blog](https://www.warp.dev/blog)。
- **AWS Kiro**：
  - 2026年10月changelog：Kiro Crew 0.9.0（crewmates可配置档案、排程、看板）；CLI 2.3x版本支持V3云会话；IDE 1.4.0上线Memory；spec文档支持Markdown Review
  - 10月15日上线Kimi K3（2.4倍credit倍率）；套餐分Pro/Pro+/Pro Max/Power
  - 来源：[Kiro Changelog](https://kiro.dev/changelog/)；Opus 5.5为2.0倍credit倍率 — [Kiro](https://kiro.dev/changelog/models/claude-opus-5-5/)
- **Zed**：
  - ACP Registry上线（1月28日）；Parallel Agents（4月22日）；Zed 1.0（4月29日）；Zed for Business（5月6日）
  - **Delta**（8月12日）："面向与Agent协作编码的多人环境"；9月16日公测时自称"替换PR是我们替换GitHub的第一步"
  - 来源：[Zed blog](https://zed.dev/blog)，[Introducing Delta](https://zed.dev/blog/introducing-delta)
- **Cline**：9月2日把VS Code扩展上的1100万开发者迁到新的Cline SDK，称Agent失败率下降10倍；9月14日推出面向开源权重模型的Cline Desktop — [Cline blog](https://cline.bot/blog)。
- **CodeRabbit**：10月8日单月开源代码评审量突破100万次，并承诺向开源投入$1000万以上；10月6日发布CodeRabbit Security基准报告；10月7日推出Slack Agent；10月22日加入"SpaceX Super Intelligence Partner Network"，上架Grok Build插件市场 — [CodeRabbit blog](https://www.coderabbit.ai/blog)。
- **xAI/SpaceX**：除Cursor外，Artificial Analysis提到"Grok 4.5 in Grok Build"（xAI自有编码Agent） — [Artificial Analysis](https://artificialanalysis.ai/articles/gpt-5-6-has-landed)。

### Inferences
- [推算] Claude Code在2026年2月约占Anthropic run-rate的18%（$25亿/$140亿）。Anthropic整体从$140亿涨到$470亿以上的主要动力是编程和Agent用量（Dario称"软件工程师是最快采用新技术的人"）。所以Claude Code的真实收入很可能远高于官方最后公布的$25亿，但没有官方数字。
- [推算] Codex年初WAU约40万（3月中旬超200万、为年初5倍），6月超500万，半年增长约12倍以上。增长靠桌面app、超级碗广告，以及开放ChatGPT订阅给第三方工具（Zed/Amp/Warp）带来的分发。
- [推算] 估值与收入倍数：Cursor $600亿 / 约$30亿 ≈ 20倍；Cognition $480亿 / $9亿 ≈ 53倍（TechCrunch也指出它高于Cursor的25–30倍）；Lovable $133亿 / $5亿 ≈ 27倍；Anthropic $9650亿 / $470亿 ≈ 20倍。资本仍在押注"非赢家通吃"。
- 2026年最大的结构性事件是"实验室吞并应用层"：Cursor并入SpaceXAI，Google用Antigravity取代自家开源Gemini CLI，微软自研MAI-Code模型，OpenAI把Codex并进超级app。同时，独立公司（Cognition、Factory、Lovable、Replit）通过多模型路由、自研或微调模型、企业部署能力（自托管、合规）保住了自己的位置。

### Gaps
- Claude Code在2026年2月之后的官方收入或WAU、Claude Code在Slack里的2026年数据，均未找到。
- Cursor付费用户数、毛利率，以及被收购后的ARR，均未找到（被收购后可能不再单独披露）。
- Copilot的Max档何时推出、2026年最新付费席位数，均未找到。
- Google Jules在2026年的状态、Antigravity用户数，均未找到。
- JetBrains（Junie/AI Assistant，博客返回403）、Bolt.new、Kilo Code、Roo Code的2026年数据，未能获取。

---

## 2. 商业模式变化（订阅分层、按量计费与限额、毛利压力、自研模型、企业席位、实验室与客户的冲突）

### Takeaway
2026年定价从"包月加请求次数"全面转向"分层订阅（$8–$200，$100档成为新标配）加token/credit按量计费加周额度"。动因是推理成本让订阅模式持续亏损（第三方估算Claude订阅对Agent用量的补贴达API价的15–30倍；Replit 2025年毛利在36%到-14%之间波动）。应对方式主要有三种：自研或开源基座模型（Composer 2基于Kimi、微软MAI-Code、Lovable自研、Cognition自训）、模型路由，以及向开源权重模型迁移。另一条主线是实验室与客户的冲突：Cursor被xAI系收购，Anthropic想把第三方harness的用量单独计费、又暂停了，OpenAI则开放订阅给第三方工具来抢分发。

### Cited Findings
- **Anthropic订阅（2026年10月）**：
  - Pro $20/月（年付$17）；Max 5x起价$100（另含每月$100 API额度）；Max 20x（含每月$200 API额度，页面未显示价格）；Team Standard $20/$25；Team Premium $100/$125；Enterprise $20/席位加API费率用量
  - Claude Code包含在所有付费档；5小时滚动窗口加周限额；触顶后可开启按API价计费的usage credits；Fable在Pro上需usage credits，在Max/Team Premium上计入周额度的50%
  - API：Fable 5.1 $10/$50、Opus 5.5 $4/$20、Sonnet 5.5 $2/$10、Haiku 5.5 $0.10/$0.50（≤100K）
  - 来源：[Claude Pricing](https://claude.com/pricing)
  - Fable 5于6月22日前随订阅免费，6月23日起需usage credits — [Anthropic](https://www.anthropic.com/news/claude-fable-5-mythos-5)；7月1–19日临时包含在所有订阅中，7月20日起成为高档位标准功能 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- **Anthropic的第三方harness计费风波**：5月13日宣布、原定6月15日生效：第一方工具（聊天、官方`claude` CLI）继续用订阅额度；第三方Agent和SDK用量（ACP、`claude -p`、Agent SDK及基于它的应用）改用单独的月度credit（Pro $20 / Max 5x $100 / Max 20x $200），按API价计费。Zed转引第三方估算称，此前订阅对Agent用量的补贴约为API价的15–30倍。6月16日Anthropic通知暂缓实施，表示修订方案后会提前通知 — [Zed blog, 2026-05-14（6月16日更新）](https://zed.dev/blog/anthropic-subscription-changes)。10月10日Amp宣布可"零成本使用Claude订阅" — [Amp News](https://ampcode.com/news)。
- **GitHub Copilot转为token计费**：2026年6月1日起Copilot Chat和Agent用量从Premium Request Units改为按token计的GitHub AI Credits，补全和NES不计费；Zed提醒重度Agent用户成本会上升 — [Zed blog, 2026-06-01](https://zed.dev/blog/github-copilot-usage-based-billing)。新档位为Pro $10 / Pro+ $39 / Max $100，含基础额度加可变flex额度 — [GitHub Plans](https://github.com/features/copilot/plans)。微软称调整后消费强于预期，但用量增长压低了毛利率 — [Microsoft IR FY26Q4](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)。
- **Cursor被收购后定价改为与Grok捆绑**：
  - Plus $8（仅Grok模型，Cursor与Grok共用额度池）；Premium $30（Plus的4倍用量，含云Agent、代码托管、AI代码评审，第三方模型按API标价另计）；Super $100（15倍）；Ultra $200（50倍）；Teams $30起/人
  - 额度**每周刷新**，可加购
  - 来源：[Cursor Pricing（2026年10月访问）](https://cursor.com/pricing)
  - 背景（2025）：2025年7月Pro从500次请求改为按用量封顶，引发意外扣费风波，随后退款 — [Wikipedia](https://en.wikipedia.org/wiki/Cursor_(code_editor))
- **Google**：5月新增$100/月AI Ultra档（Antigravity额度为Pro的5倍），顶档从$250降到$200 — [Google Blog](https://blog.google/innovation-and-ai/technology/developers-tools/google-io-2026-developer-highlights/)，[Wikipedia](https://en.wikipedia.org/wiki/Google_Antigravity)；用户反映Antigravity CLI更快触及上限 — [The New Stack](https://thenewstack.io/google-antigravity-cli/)。
- **OpenAI**：ChatGPT Pro为$100–$200/月，Plus $20 — [VentureBeat, 2026-04-23](https://venturebeat.com/technology/openais-gpt-5-5-is-here-and-its-no-potato-narrowly-beats-anthropics-claude-mythos-preview-on-terminal-bench-2-0)。GPT-5.6 API：Sol $5/$30、Terra $2.5/$15、Luna $1/$6；缓存写入新收1.25倍 — [Artificial Analysis](https://artificialanalysis.ai/articles/gpt-5-6-has-landed)。ChatGPT订阅可在Zed（5月15日）、Amp（7月18日）、Warp（9月29日）中使用 — [Zed blog](https://zed.dev/blog)，[Amp](https://ampcode.com/news)，[Warp](https://www.warp.dev/blog)。
- **Replit**：Core $20、Pro $100，effort-based计价取代每个checkpoint固定$0.25（简单任务低至$0.06，复杂任务可达数美元）；2025年毛利在约36%到-14%之间波动，主因是编码Agent的LLM成本 — [Sacra](https://sacra.com/c/replit/)。
- **毛利压力与现金消耗**：Cognition依赖昂贵的OpenAI/Anthropic模型，租用的Nvidia集群每年花费数亿美元，全年现金消耗可能达$8亿，正在基于开源模型训练自有模型以接近盈亏平衡 — [TechCrunch, 2026-09-08](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)。Cursor卖身主要因为算力受限 — 同上。
- **自研/开源模型，降低对Anthropic/OpenAI的依赖**：
  - Cursor Composer 2基于Kimi K2.5（3月）— [Wikipedia](https://en.wikipedia.org/wiki/Cursor_(company))；被收购后转向Grok 4.6/4.7 — [Cursor blog](https://cursor.com/blog)
  - 微软MAI-Code-1-Flash — [Microsoft IR](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
  - Lovable自研模型 — [TechCrunch](https://techcrunch.com/2026/08/12/lovable-confirms-new-13-3b-valuation-raises-another-400m/)
  - Cognition自训模型 — [TechCrunch](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)
  - Kiro和Copilot上架Kimi K3 — [Kiro](https://kiro.dev/changelog/)，[GitHub](https://github.com/features/copilot/plans)
- **模型路由与成本优化成为标配**：Cursor Router（8月6日）— [Cursor blog](https://cursor.com/blog)；Factory Router称降本63% — [Factory](https://factory.com/news)；Augment Prism — [Augment](https://www.augmentcode.com/blog)。
- **开源权重模型的token份额（Vercel AI Gateway）**：
  - 5月数据：Anthropic占支出的65%，DeepSeek token份额升到17%
  - 6月数据：开源权重约占token量的三分之一，Anthropic占支出61%
  - 8月数据：开源权重首次过半（56%）
  - 9月数据：开源权重占token的71.5%、支出的23%；AI总支出增长13倍，单位token成本减半
  - 来源：[Vercel blog](https://vercel.com/blog)
- **实验室与客户的冲突，以及竞合**：
  - 2026年4月Reuters报道OpenAI因Claude Code的压力把资源转向Codex — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - Google 2月封禁接入OpenClaw的Antigravity用户 — [Wikipedia: Antigravity](https://en.wikipedia.org/wiki/Google_Antigravity)
  - SpaceX一边拥有Cursor，一边向Anthropic出租Colossus 1算力 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)
  - TechCrunch（5月27日）写道"去年所有迹象都指向模型厂商自己吞下这个市场"，但Cognition的融资显示独立公司仍有空间 — [TechCrunch](https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/)
  - 9月TechCrunch称AI coding"远非赢家通吃" — [TechCrunch](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)
  - Anthropic 10月12日发文《Strengthening our defenses against distillation attacks》（仅见标题） — [Anthropic News](https://www.anthropic.com/news)
  - 背景（2025）：2025年8月Anthropic撤销OpenAI的Claude Code访问权限 — [Wikipedia: Claude Code（引Wired）](https://en.wikipedia.org/wiki/Claude_Code)
- **企业侧成本管控**：38%的开发者所在组织设置了AI用量上限，28%审查支出数据，27%按工作类型用不同模型，25%限制使用人员；21%称组织AI支出在增加 — [Stack Overflow blog, 2026-10-06](https://stackoverflow.blog/2026/10/06/the-results-of-the-2026-developer-survey-are-here/)。

### Inferences
- $100/月正在成为"专业开发者"的新标准档：Claude Max 5x、Copilot Max、Cursor Super、Google AI Ultra、Replit Pro、ChatGPT Pro入门档都在这个价位。$200是重度档，$8–$20是引流档。"无限量"已经消失，取而代之的是"周额度加超额按API价"。
- 订阅补贴不可持续（第三方估算15–30倍、Replit出现负毛利、Cognition现金消耗$8亿），推动三件事：①按token计费（Copilot在6月转型）；②第三方harness单独计价（Anthropic尝试后暂缓，说明它也担心失去生态和分发）；③应用公司自研、换开源基座或路由降本。Vercel数据显示，开源权重模型的token份额从约17%升到71.5%，但支出份额只有23%：高价值任务仍集中在Anthropic/OpenAI的前沿模型上，低价值的长尾token在流向开源模型。
- 实验室与客户的冲突在2026年以"收购和捆绑"告终：Cursor从Anthropic/OpenAI的大客户变成xAI系的分发渠道（套餐变成Grok捆绑）。OpenAI则反过来开放ChatGPT订阅给第三方编辑器（Zed/Amp/Warp），借渠道对抗Claude Code。

### Gaps
- 未找到Cursor、Lovable、Claude Code产品线的2026年毛利率（The Information等付费报道无法访问）。
- 未找到Claude Max 20x的2026年确切价格，以及周限额的具体数值（定价页未列出）。
- 未找到企业席位大单的金额（例如Copilot、Claude Code的企业级合同规模）。

---

## 3. 技术与产品趋势（终端Agent、后台/云Agent、并行多Agent、代码评审Agent、spec驱动、长时程自主编码、非开发者vibe coding、App Builder留存、安全事件）

### Takeaway
2026年的产品主线是从"单个Agent加人逐步审批"转向"多Agent编排、云端或后台长时间运行、自动权限、自动评审"：auto mode、Routines、dynamic workflows、Antigravity 2.0、Cursor cloud agents、Copilot把任务委派给第三方Agent都属于这一类。评审和验证成为新瓶颈，于是出现了代码评审Agent，以及"替换GitHub或PR"的AI原生代码托管（Cursor Origin、Zed Delta）。长时程任务的单位从小时变成天甚至周（Fable 5、Mythos 5）。安全面明显扩大：供应链攻击开始专门针对Agent配置文件，例如CLAUDE.md和.cursorrules投毒，以及窃取Agent凭证。

### Cited Findings
- **终端/CLI Agent成为主战场**：Google用闭源的Antigravity CLI（Go）取代Gemini CLI，6月18日对消费者停服 — [Google Developers Blog](https://developers.googleblog.com/an-important-update-transitioning-gemini-cli-to-antigravity-cli/)；Amp于5月6日重建CLI — [Amp](https://ampcode.com/news)；Kiro CLI 2.3x支持V3云会话 — [Kiro](https://kiro.dev/changelog/)；Claude Code的`claude ultrareview`可在CI里跑 — [Claude Code](https://code.claude.com/docs/en/whats-new)。Stack Overflow 2026调查中，使用Agent的受访者里Claude Code占66%、GitHub Copilot占59% — [SO blog](https://stackoverflow.blog/2026/10/06/the-results-of-the-2026-developer-survey-are-here/)。
- **后台/云Agent与定时任务**：
  - Claude Code：Routines（4月）、云会话自托管环境（8月）、subagent默认后台（7月） — [Claude Code](https://code.claude.com/docs/en/whats-new)
  - Cursor：云Agent可跑在自管机器上（9月2日）、启动提速3倍 — [Cursor blog](https://cursor.com/blog)
  - Antigravity 2.0：定时后台任务 — [Google Blog](https://blog.google/innovation-and-ai/technology/developers-tools/google-io-2026-developer-highlights/)
  - Amp：可自行唤醒的定时Agent（7月21日） — [Amp](https://ampcode.com/news)
  - Kiro Crew：带排程的crewmates — [Kiro](https://kiro.dev/changelog/)
  - Copilot：云Agent，以及委派给Claude/Codex — [GitHub Plans](https://github.com/features/copilot/plans)
  - Factory：OpenCompute自托管沙盒编排 — [Factory](https://factory.com/news)
- **并行多Agent和大规模编排**：
  - Opus 4.6的agent teams：Nicholas Carlini用16个Agent写出能编译Linux内核的Rust版C编译器，花费近$2万（2026年2月） — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_(language_model))
  - Claude Code dynamic workflows可编排几十到上百个subagent（5月）；跨会话消息（8月） — [Claude Code](https://code.claude.com/docs/en/whats-new)
  - Codex桌面app定位为"管理多个编码Agent"（2月2日） — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - Zed Parallel Agents（4月22日） — [Zed](https://zed.dev/blog)
  - METR指出，同时跑多个Agent的开发者时间记录不可靠，这是研究难点之一 — [METR](https://metr.org/blog/2026-02-24-uplift-update/)
  - GitHub上三分之一的PR涉及Agent — [Microsoft IR](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
- **自动权限（auto mode）**：3月研究预览，用分类器代替逐条确认；8月14日起成为Pro/Max/Team新会话的默认；会拦截破坏性git命令，并在变量未解析的`rm -rf`前询问 — [Claude Code](https://code.claude.com/docs/en/whats-new)。
- **代码评审/验证Agent**：
  - Claude Code /code-review、/ultrareview（云端多个找bug的Agent）、Claude Security插件 — [Claude Code](https://code.claude.com/docs/en/whats-new)
  - Cursor Bugbot、Security Review与Rollouts机器人（9月23日） — [Cursor](https://cursor.com/blog)
  - Codex Security（3月6日，beta测试中误报下降50%以上） — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - CodeRabbit单月开源评审超100万次 — [CodeRabbit](https://www.coderabbit.ai/blog)
  - Augment Cosmos专门做"移除代码评审瓶颈"（5月6日） — [Augment](https://www.augmentcode.com/blog)
  - DORA评论文章认为，AI的ROI取决于评审和验证层能否跟上 — [InfoQ, 2026-05](https://www.infoq.com/news/2026/05/dora-roi-ai-assisted-dev-report/)
- **AI原生代码托管 / "替换GitHub"**：Cursor Premium档含"code hosting"，并推出Origin应用市场（10月13日）— [Cursor Pricing](https://cursor.com/pricing)，[CodeRabbit](https://www.coderabbit.ai/blog)；Zed Delta（8月12日私测、9月16日公测）称"替换PR是替换GitHub的第一步" — [Zed](https://zed.dev/blog)；Cursor发文《Git at any scale》（8月18日） — [Cursor blog](https://cursor.com/blog)。
- **"Software factory"叙事**：Warp Factories — [Warp](https://www.warp.dev/blog)；Augment "Cosmos Software Factory" — [Augment](https://www.augmentcode.com/blog)；Factory"在企业规模化自我改进的软件开发"（9月融资） — [Factory](https://factory.com/news)；"Loop engineering"（Augment 7月22日的文章，以及arXiv论文LoopsBench） — [Augment](https://www.augmentcode.com/blog)，[arXiv 2608.00267](https://arxiv.org/pdf/2608.00267)。
- **Spec驱动和计划先行**：Kiro的spec文档支持Markdown Review（10月15日）— [Kiro](https://kiro.dev/changelog/)；Claude Code Ultraplan（4月）和/goal完成条件（5月） — [Claude Code](https://code.claude.com/docs/en/whats-new)。
- **长时程自主编码**：Fable 5面向"多日、异步"任务，Stripe 5000万行迁移1天完成，Mythos 5做了一周以上的研究 — [Anthropic](https://www.anthropic.com/news/claude-fable-5-mythos-5)；Cursor博客发文《Improved token efficiency for longer agent runs》（9月23日），Navan的一个月迁移约一周完成 — [Cursor blog](https://cursor.com/blog)；Opus 5宣称减少并行Agent之间的冲突，Frontier-Bench v0.1得分43.3% — [二手] [InfoWorld](https://www.infoworld.com/article/4201551/anthropic-releases-more-efficient-claude-opus-5.html)，[Codersera](https://codersera.com/blog/claude-opus-5-benchmarks-explained-2026/)。
- **非开发者vibe coding**：2025/26年假期Claude Code在非程序员中走红 — [Wikipedia: Claude Code](https://en.wikipedia.org/wiki/Claude_Code)；Codex约20%的用户是非开发者（6月） — [Constellation](https://www.constellationr.com/insights/news/openai-touts-broadening-codex-usage-5-million-weekly-active-users)；Stack Overflow调查中"一人组织"的比例从4%升到10% — [SO blog](https://stackoverflow.blog/2026/10/06/the-results-of-the-2026-developer-survey-are-here/)；Dario预言2026年会出现首个一人运营的十亿美元公司 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。
- **App Builder规模**：Lovable有6000万个项目、月访问9亿，ARR $5亿（6月）— [TechCrunch](https://techcrunch.com/2026/08/12/lovable-confirms-new-13-3b-valuation-raises-another-400m/)；Replit有5000万以上用户，覆盖85%的Fortune 500 — [Sacra](https://sacra.com/c/replit/)；v0推出企业版和API — [Vercel](https://vercel.com/blog)；Google AI Studio支持一键导出到Antigravity，可从prompt生成Android应用 — [Google Blog](https://blog.google/innovation-and-ai/technology/developers-tools/google-io-2026-developer-highlights/)。
- **协议与标准**：Zed ACP Registry（1月）— [Zed](https://zed.dev/blog)；Anthropic把Agent Skills捐给Agentic AI Foundation（10月22日） — [Anthropic News](https://www.anthropic.com/news)；Vercel Agent Plugins 1.0规范（8月6日） — [Vercel](https://vercel.com/blog)；Claude Code在没有CLAUDE.md时读取AGENTS.md — [二手] [ScriptByAI](https://www.scriptbyai.com/claude-code-timeline/)。
- **2026年安全事件（Agent工具链本身）**：
  - 3月31日Claude Code CLI源码经暴露的map文件泄露 — [Wikipedia: Claude Code（引Ars Technica、CNBC）](https://en.wikipedia.org/wiki/Claude_Code)
  - 3月Codex漏洞：恶意分支名可注入命令并泄露GitHub token（已修补） — [Wikipedia: Codex（引SecurityWeek）](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - Antigravity文件搜索工具的prompt-injection漏洞，即使在最严格模式下也能任意代码执行，2月28日修复、4月披露 — [Wikipedia: Antigravity（引CyberScoop）](https://en.wikipedia.org/wiki/Google_Antigravity)
  - 2月13日用户报告Cowork在整理文件时删掉了家庭照片 — [Wikipedia: Claude（引Futurism）](https://en.wikipedia.org/wiki/Claude_(language_model))
  - 背景（2025）：Antigravity Turbo模式删光了用户整个硬盘 — [Wikipedia: Antigravity](https://en.wikipedia.org/wiki/Google_Antigravity)；Replit Agent删除生产数据库 — [Wikipedia: Replit](https://en.wikipedia.org/wiki/Replit)
  - GPT-5.6发布后数日内有删文件事故的报道 — [二手/未证实] [AIToolsReview](https://aitoolsreview.co.uk/insights/gpt-5-6)
- **针对编码Agent的供应链攻击**（大多来自安全厂商研究简报，[二手]）：
  - **TrapDoor**（2026年5月）：npm/PyPI/Crates上34个恶意包、384个版本，植入含零宽字符隐藏指令的.cursorrules和CLAUDE.md，还向browser-use、langchain、langflow提PR
  - **Bitwarden CLI被投毒**（2026年4月）：90分钟窗口内334台机器安装，窃取Claude Code、Cursor、Codex CLI、Kiro、Gemini CLI的配置
  - 朝鲜（DPRK）用Claude Opus生成"让AI Agent愿意推荐和安装"的恶意npm包（5月）
  - jscrambler包投放窃密木马，专偷Claude Desktop、Cursor、Windsurf凭证（7月）
  - "Ghostcommit"演示：Cursor和Antigravity在多个模型下泄露密钥，Claude Code全部拒绝（7月）
  - Context7 "ContextCrush" MCP规则注入（3月披露）
  - "TrustFall"：信任对话框被利用后，恶意代码以开发者全部权限执行（5月）
  - Mini Shai-Hulud（4月）：滥用Claude Code SessionStart hook实现持久化
  - 来源：[Noqta](https://www.noqta.tn/en/blog/trapdoor-supply-chain-attack-ai-coding-tools-2026)，[CSA CISO Briefing 2026-07-13](https://labs.cloudsecurityalliance.org/research/alt-ciso-briefing-2026-07-13/)，[CSA TrapDoor研究笔记](https://labs.cloudsecurityalliance.org/wp-content/uploads/2026/05/CSA_research_note_trapdoor-multi-ecosystem-supply-chain-ai-targeting_20260526-csa-styled.pdf)，[Phoenix Security](https://phoenix.security/accelerating-supply-chain-attacks-npm-pypi-vsx-ai-enabled-2026/)
- **AI用于防御，以及新的副作用**：
  - Mythos Preview（4月7日）通过Project Glasswing向超过40家机构开放；前50家伙伴发现超过1万个高危或严重漏洞，但到9月只有10%被披露、不到1%被修复；Mozilla用它修了271个Firefox漏洞 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
  - Dark Reading（8月7日）指出Codex参与的"Patch the Planet"产出的大量AI补丁有缺陷 — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - 6月12日至7月1日Mythos/Fable因美国出口管制下线 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- **AI生成代码的质量与开源生态压力**：
  - GitHub博客（2月12日）把低质量AI贡献称作"Eternal September"；cURL终止漏洞赏金，Ghostty改为邀请制贡献 — [Wikipedia: Vibe coding](https://en.wikipedia.org/wiki/Vibe_coding)
  - rsync 3.4.3（5月20日）出现增量备份故障，此前数十个commit署名"tridge and claude"（LWN 6月3日，The Register 6月4日） — 同上
  - WSJ（5月22日）报道Mario Zechner、Armin Ronacher警告"vibe slop"危机 — 同上
  - arXiv论文《Vibe Coding Kills Open Source》（1月21日） — 同上
  - 背景（2025）：CodeRabbit 2025年12月分析发现，AI参与的PR"重大问题"约为1.7倍、安全漏洞为2.74倍；Veracode 2025年10月发现生成代码的安全性没有随能力提升而改善 — 同上

### Inferences
- 2026年的竞争重心从"模型加编辑器"转向"编排层、harness和运行环境"。证据有两条：TB2榜单前列多是第三方harness（NexAU-AHE、LemonHarness）跑GPT-5.5；同一模型在不同harness上的分差很大（Snorkel 84.7%，Vals的Terminus 2只有73.2%）。harness质量和成本效率（Auggie称比Claude Code便宜53%）成了应用公司的主要护城河。
- 代码产出大幅增加后，瓶颈移到评审、验证和集成：GitHub三分之一的PR涉及Agent，CodeRabbit单月评审百万次，开源维护者开始拒收AI PR。于是出现两条路线：评审Agent，以及重新设计代码托管和协作单元（Origin、Delta）。这也是对GitHub护城河的直接挑战。
- 安全风险正从"AI写出的漏洞"扩展到"Agent本身成为攻击面"：配置文件投毒、MCP规则注入、hook持久化、凭证窃取。auto mode这类自动权限普及后，分类器和沙箱成了必需品。2027年企业采购大概率会把Agent安全认证（如Cursor的AIUC-1）和自托管列为门槛。

### Gaps
- 未找到App Builder（Lovable/Replit/Bolt/v0）2026年留存率或流失率的可靠数据。
- 未找到Claude Code在Slack里，以及Jules的2026年具体使用数据。
- 供应链攻击细节大多只有单一安全厂商来源，没有找到一手披露交叉验证。
- METR的"OpenAI/Hugging Face hacking incident"调查（8月26日）只看到标题 — [METR](https://metr.org/)。

---

## 4. 影响证据（生产力研究、AI写代码的占比、对招聘与初级开发者的影响）

### Takeaway
采用率几乎全覆盖：Stack Overflow 2026调查中66%用编码Agent，其中73%每天使用。但严格测量的生产力证据仍弱：METR 2026年2月的更新从"慢19%"变为"可能加速"，可置信区间跨零，METR自己称是"非常弱的证据"。DORA强调AI是"放大器"，且存在J曲线。大公司AI写代码的占比快速上升（Google约75%的新代码、Snap≥65%、Anthropic"多数"、GitHub三分之一PR涉及Agent）。初级岗位受压持续加深：Stanford ADP数据显示，22–25岁AI高暴露职业的就业比趋势低19%，数据截至2026年6月。

### Cited Findings
- **METR（2026-02-24）**：
  - 第二轮研究从2025年8月开始，57名开发者、143个仓库、800多个任务
  - 回归开发者耗时 -18%（即加速；CI -38%到+9%），新开发者 -4%（CI -15%到+9%）
  - 30–50%的开发者说因为不想不用AI做，所以没提交某些任务；时薪从$150降到$50，可能加重了选择偏差；同时运行多个Agent让计时失真
  - METR认为真实加速可能更大，这个估计是下限，但数据是"非常弱的证据"；计划改用固定任务实验、观察性数据等新设计
  - 背景（2025）：原研究（2025年2–6月数据）发现耗时增加19%（CI +2%到+39%）
  - 来源：[METR](https://metr.org/blog/2026-02-24-uplift-update/)
- **METR使用调查（2026-05-11，349名技术工作者）**：自报"工作价值"变化的中位数为1.4–2倍，METR提示对幅度应保持怀疑 — [METR](https://metr.org/)。有二手来源称中位"3倍速度" — [二手/与METR首页表述冲突] [搜索汇总所引ingenire等](https://ingenire.com/blog/metr-2026-developer-productivity-study)。
- **DORA**：2026年发布《The ROI of AI-assisted Software Development (2026.01)》，提出AI是"放大器"，收益取决于工程基础；有J曲线（二手解读称其计算器假设头3个月效率下降15%） — [InfoQ, 2026-05](https://www.infoq.com/news/2026/05/dora-roi-ai-assisted-dev-report/)，[DORA](https://dora.dev/insights/balancing-ai-tensions/)。截至检索时没找到2026年版《State of AI-assisted Software Development》 — [DORA research页](https://www.dora.dev/research/ai)。背景（2025）：近5000名受访者，约90%在工作中用AI，约一半"有些信任"AI输出，30%"很少或不信任" — [InfoQ 2025-09](https://www.infoq.com/news/2025/09/dora-state-of-ai-in-dev-2025)。
- **Stack Overflow 2026开发者调查（2026-10-06发布，超3万人参与，历时7周）**：
  - 使用：66%用编码助手或Agent，63%用通用聊天工具；73%每天使用；约31%每天用AI 4小时以上
  - 使用Agent的人中Claude Code 66%、GitHub Copilot 59%；Anthropic和OpenAI模型使用量大致持平，Google远远落后
  - 态度：62%至少有些正面（每日用户中71%）；48%在易于验证时才信任AI，16%对多数非关键任务信任；93%要求来源标注
  - 回避AI的原因：41.3%不回避，17.1%担心技能退化，15.2%出于道德原因，13.0%出于隐私安全
  - 访问Stack Overflow：64%在简单问题上来得更少了
  - 来源：[SO blog](https://stackoverflow.blog/2026/10/06/the-results-of-the-2026-developer-survey-are-here/)，[SO AI页](https://survey.stackoverflow.co/2026/ai)
  - Codex 29.5%、Cursor 25.5%只见于二手分析，一手页面未列出 — [二手] [daily.dev](https://daily.dev/posts/2026-stack-overflow-survey-ai-agent-trust-obdnbazse)
  - SO官方X账号的表述是"65%用编码Agent，但其中六成在某些场景回避AI" — [Stack Overflow on X](https://x.com/StackOverflow/status/2107144120305115389)
  - 背景（2025）：不信任AI准确性的比例（46%）高于信任（33%） — [搜索汇总，DORA相关报道](https://www.infoq.com/news/2025/09/dora-state-of-ai-in-dev-2025)
- **大公司AI写代码的占比**：
  - **Google**：2024年秋约25%，2025年秋约50%；2026年4月报道约四分之三的新代码由AI生成、再经工程师审查 — [Wikipedia: AI-assisted SD（引Business Insider、The Guardian 2026-07）](https://en.wikipedia.org/wiki/AI-assisted_software_development)
  - **Snap**：2026年4月称至少65%的新代码由AI生成 — 同上
  - **Anthropic**：多数代码由Claude Code编写（2026年5月） — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)
  - **Microsoft**：背景（2025）：2025年4月Nadella称部分项目20–30%的代码由AI编写 — [TechRadar](https://www.techradar.com/pro/a-shockingly-high-amount-of-microsoft-code-is-now-written-by-ai-it-admits)
  - **Meta**：背景（2025）：Zuckerberg 2025年4月预测"明年大约一半开发由AI完成" — [Digit](https://www.digit.in/news/general/mark-zuckerberg-says-ai-will-write-most-of-metas-ai-code-by-2026.html/amp/)
  - **全平台**：GitHub三分之一的PR涉及Agent（2026年7月） — [Microsoft IR](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；Claude Code约占公开GitHub commit的4% — [METR引SemiAnalysis](https://metr.org/blog/2026-02-24-uplift-update/)
  - **Cognition**：Devin编写89%的代码 — [二手/未证实] [tech-insider](https://tech-insider.org/ie/cognition-devin-26-billion-2026/)
- **对招聘与初级开发者的影响**：
  - **Stanford Digital Economy Lab "Canaries in the Coal Mine"**（2026-08-12修订，ADP薪资数据截至2026年6月）：22–25岁AI高暴露职业的就业比低暴露同龄人的趋势水平低19%；自2025年8月首次记录以来差距持续扩大；资深员工没有类似差距；作者强调这是描述性指标而非因果 — [Stanford DEL](https://digitaleconomy.stanford.edu/publications/canaries-in-the-coal-mine/)。另有二手报道称差距从一年前的13%扩大到19%，且主要来自招聘减少而非裁员 — [二手] [IEEE Spectrum](https://spectrum.ieee.org/ai-effect-entry-level-jobs)
  - Gusto 2026新毕业生招聘报告：2022年最大的入门岗位（包括Software Engineer）在新毕业生招聘中的占比都在缩小 — [Gusto](https://gusto.com/resources/gusto-insights/new-grad-hiring-report-2026)
  - LinkedIn：AI engineer连续第二年成为年轻人增长最快的职位 — [二手] [LetsDataScience](https://letsdatascience.com/news/linkedin-identifies-ai-engineer-as-fastest-growing-role-e82f85f1)
  - 对大厂新毕业生招聘降幅的估计在约25%到约65–73%之间，口径各不相同 — [二手/口径不一] [Hakia](https://hakia.com/news/entry-level-tech-hiring-crisis-2026/)，[RezScore](https://blog.rezscore.com/software-engineering-job-market-2026/)
  - Stack Overflow：AI和裁员改变了开发者与雇主之间的力量对比；"一人组织"比例从4%升到10%；只有18%每天去办公室 — [SO blog](https://stackoverflow.blog/2026/10/06/the-results-of-the-2026-developer-survey-are-here/)
  - Anthropic于10月2日宣布投入$1亿，在2027年底前培训1万名工程师，以弥补企业AI人才缺口 — [Anthropic News](https://www.anthropic.com/news)
  - NYT 2026年专题"Coding After Coders"（Clive Thompson）描述硅谷程序员已经很少亲手写代码 — [Wikipedia: AI-assisted SD](https://en.wikipedia.org/wiki/AI-assisted_software_development)

### Inferences
- "体感生产力"和"测量生产力"之间的落差仍是2026年的核心矛盾，但方向变了：2025年METR测出的是变慢，2026年的数据指向加速，只是因为开发者"拒绝不用AI"而难以测量。这本身就是强采用信号。机构层面（DORA）的结论是：个人吞吐上升不等于团队交付改善，评审和验证是新瓶颈。
- 大公司AI代码占比已从2025年的20–30%升到2026年的50–75%（Google、Snap），实验室内部接近全部。下一步的度量口径很可能从"AI写了多少行"转向"多少PR由Agent端到端完成"（GitHub的三分之一口径）。
- 初级岗位的压力是结构性的，并在加深（Stanford差距在一年内扩大）。但市场同时出现AI engineer岗位增长和培训投入（Anthropic的1万人计划），意味着入门门槛从"会写代码"变成"会指挥和验证Agent"。

### Gaps
- 未找到2026年版DORA《State of AI-assisted Software Development》（可能尚未发布或尚未被索引）。
- 未找到Microsoft、Meta、Salesforce、Amazon在2026年公开表述的AI代码占比。
- 没有找到2026年严格的新RCT（METR的新设计尚未产出结果）；Google内部RCT等其他研究也未找到2026年数据。
- 新毕业生招聘降幅的数字口径混乱，缺少BLS、Indeed等一手数据交叉验证。

---

## 5. 基准测试（SWE-bench Verified/Pro、Terminal-Bench在2026年的演进与榜首）

### Takeaway
2026年两大"旧标尺"相继饱和退役。OpenAI在2月宣布不再报告SWE-bench Verified（污染、59.4%的困难题有缺陷）；Vals.ai把SWE-bench Verified（Opus 5 97%领先）和Terminal-Bench 2.0都标为"已饱和、归档"。行业转向SWE-bench Pro（Mythos Preview 77.8%，后来Opus 5/Fable 5约79–80%，为厂商自报或二手数据）、Terminal-Bench 2.1/3.0（3.0上榜首只有约43%），以及自建评测（CursorBench、FrontierBench、DeepSWE、Coding Agent Index）。开源权重模型（DeepSeek V4、GLM 5.3、Kimi K3）在饱和基准上已逼近闭源前沿。

### Cited Findings
- **SWE-bench Verified退役**：OpenAI于2026年2月（多数来源为2月23日）宣布停止报告SWE-bench Verified、推荐SWE-bench Pro，并建议其他厂商也这样做。理由：
  - 训练数据污染：GPT-5.2、Claude Opus 4.5、Gemini 3 Flash能凭记忆复现部分原始修复
  - 审计138道最难题，59.4%在测试设计或问题描述上有实质缺陷
  - 近6个月SOTA只从74.9%升到80.9%
  - 来源：[OpenAI](https://openai.com/index/why-we-no-longer-evaluate-swe-bench-verified/)（403无法直读，内容经搜索摘要和二手转述），[OpenAI Devs on X](https://x.com/OpenAIDevs/status/2026002219909427270)，[Pebblous](https://blog.pebblous.ai/blog/swe-bench-verified-retired/en/)
  - 另有一篇文章把同一事件写成7月8日，日期以OpenAI原帖为准
- **SWE-bench Verified最终榜单（Vals.ai，mini-SWE-agent harness，最后更新2026-09-01，已因饱和归档）**：Claude Opus 5 97.0%、DeepSeek V4 Pro 96.4%、GPT-5.6 Sol 96.2%、Grok 4.6 95.6%、GPT-5.6 Terra 95.4%、GLM 5.3 95.4%、Claude Fable 5 95.0%、Kimi K3 93.4%、GPT-5.6 Luna 93.0%、GLM 5.3 Flash 92.0% — [Vals.ai](https://www.vals.ai/benchmarks/swebench)。背景（2025）：2025年11月Opus 4.5为80.9% — [OpenAI（经二手转述）](https://blog.pebblous.ai/blog/swe-bench-verified-retired/en/)。
- **SWE-bench Pro（Public）**：
  - 2026年4月（厂商自报）：Mythos Preview 77.8%、Opus 4.7 64.3%、GPT-5.5 58.6%、Gemini 3.1 Pro 54.2% — [VentureBeat, 2026-04-23](https://venturebeat.com/technology/openais-gpt-5-5-is-here-and-its-no-potato-narrowly-beats-anthropics-claude-mythos-preview-on-terminal-bench-2-0)
  - 2026年7月（二手）：Opus 5 79.2%（Opus 4.8为69.2%）；Fable 5 80.0–80.3%（各来源不一） — [二手] [MorphLLM](https://www.morphllm.com/claude-benchmarks)，[Codersera](https://codersera.com/blog/claude-opus-5-benchmarks-explained-2026/)
  - GPT-5.6 Sol 64.6%、Terra 63.4%、Luna 62.7% — [二手] [ExplainX](https://www.explainx.ai/blog/gpt-5-6-release-date-features-benchmarks-2026)
  - Scale标准化评测的分数明显低于厂商自报（例如GPT-5.2 Codex在公开集上41.0%） — [二手] [搜索摘要](https://www.morphllm.com/swe-bench-pro)
  - 2026年9月出现论文《SWE-Bench Pro Verified》（仅见标题），说明Pro也开始需要"Verified化" — [arXiv 2609.08149](https://arxiv.org/pdf/2609.08149)
- **Terminal-Bench 2.0**（2025-11-07上线）：
  - GPT-5.5 82.7%、Mythos Preview 82.0%、Opus 4.7 69.4%、Gemini 3.1 Pro 68.5%（2026年4月，厂商自报） — [VentureBeat](https://venturebeat.com/technology/openais-gpt-5-5-is-here-and-its-no-potato-narrowly-beats-anthropics-claude-mythos-preview-on-terminal-bench-2-0)
  - 官方榜单（Snorkel镜像，约10月初）：NexAU-AHE + GPT-5.5 84.7%；LemonHarness 84.5%；Capy + GPT-5.5 83.1%；Codex CLI + GPT-5.5 82.2%；WOZCODE + Opus 4.7 80.2%；TongAgents + Gemini 3.1 Pro 80.2%；Factory Droid + GPT-5.3-Codex 77.3%。共142个条目 — [Snorkel](https://snorkel.ai/leaderboard/terminal-bench-2-0/)
  - 统一harness（Vals.ai，Terminus 2，最后更新2026-06-04，已因饱和归档）：GPT-5.5 73.2%、Opus 4.8 70.04%、Opus 4.7 68.54%、Gemini 3.5 Flash 67.42%、GPT-5.3 Codex 64.05%、Meta Muse Spark 59.55%、Qwen 3.7 Max 59.18% — [Vals.ai](https://www.vals.ai/benchmarks/terminal-bench-2)
- **Terminal-Bench 2.1 / 3.0**：
  - 2.1：OpenAI称GPT-5.6 Sol在2.1和DeepSWE上达SOTA — [OpenAI](https://openai.com/index/gpt-5-6/)；二手称Sol 88.8%（Sol Ultra 91.9%）— [二手] [ExplainX](https://www.explainx.ai/blog/gpt-5-6-release-date-features-benchmarks-2026)；另有二手称Opus 5为89.1%、比Sol只低0.4分（两说冲突），且8月时Opus 5不在2.1的verified榜上 — [二手/冲突] [MorphLLM](https://www.morphllm.com/claude-benchmarks)
  - 3.0（Snorkel）：Opus 5 42.7%、GPT-5.6 Sol 34.6%、Fable 5 34.1% — [Snorkel](https://snorkel.ai/leaderboard/terminal-bench-2-0/)
- **综合编码Agent指数（Artificial Analysis，2026-07-09）**：GPT-5.6 Sol（在Codex中）得80，比Fable 5高2.8分；Terra 77、Luna 75（指数由DeepSWE、Terminal-Bench v2、SWE-Atlas-QnA组成）。Sol在Codex中的单任务成本比Fable 5（max）低约40%，比Opus 4.8（max，在Claude Code中）低约10% — [Artificial Analysis](https://artificialanalysis.ai/articles/gpt-5-6-has-landed)。
- **厂商和应用自建评测**：Fable 5号称在CursorBench、Cognition FrontierBench/FrontierCode、ViBench（vibe coding）上SOTA — [Anthropic](https://www.anthropic.com/news/claude-fable-5-mythos-5)；Opus 5在CursorBench 3.2上以约一半成本接近Fable 5 — [二手] [InfoWorld](https://www.infoworld.com/article/4201551/anthropic-releases-more-efficient-claude-opus-5.html)。
- **METR Time Horizon 1.1**于2026年1月29日发布（任务集更大、方法不变），本次未取得各模型的具体时长；原始研究的翻倍周期约7个月 — [METR](https://metr.org/)。

### Inferences
- 一年里分数从约81%（2025年11月）涨到97%（2026年9月），SWE-bench Verified已失去区分度。Terminal-Bench 2.0在统一harness下也到了70%以上，前列被harness工程拉开（84.7%对73.2%）。2027年的"可信标尺"更可能是：SWE-bench Pro及其Verified子集、TB 3.0/4.0（头部只有约43%，空间大）、长时程任务（METR time horizon、FrontierBench），以及"单位任务成本"类指标（AA指数）。
- 2026年的两极：Anthropic在SWE-bench Pro和TB3.0这类"真实仓库与长任务"上领先；OpenAI在Terminal-Bench 2.x、Coding Agent Index和成本效率上领先。开源权重模型在饱和基准上与前沿差1–4个百分点，这会持续压低应用层的模型采购价。
- 厂商自报分数与独立统一harness分数常差10个百分点以上（如GPT-5.5在TB2上82.7%对73.2%），引用时必须注明harness和来源。

### Gaps
- 无法直接读取Scale SWE-bench Pro官方榜单（morphllm返回429，一手页面未访问到），Opus 5、Fable 5、GPT-6的Pro分数均只有二手数据。
- 未取得GPT-6 Sol/Astra、Opus 5.5、Fable 5.1的权威编码基准数值。
- 未取得METR Time Horizon 1.1中2026年模型的具体时长（图表无法解析）。

---

## 6. 2027年预期与路线图

### Takeaway
2027年的关键变量包括：Anthropic和OpenAI的IPO与收入兑现（Anthropic被报道年内冲$1000亿run-rate）、头部独立公司按指引冲$40–60亿ARR、编码Agent从"开发者工具"扩展到"知识工作超级app"、长时程自主（多日到数周）和多Agent的"软件工厂"成为主流叙事、AI原生代码托管挑战GitHub、Agent安全和出口管制成为准入门槛、开源权重模型进一步压低单位成本。要注意的是，多数2027年的定量预期来自匿名信源或投资人预测，确定性较低。

### Cited Findings
- **收入与估值预期**：
  - Cursor年底有望超过$60亿ARR（TechCrunch春季报道） — [TechCrunch](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)
  - Cognition年底$40–50亿（The Information预测） — 同上
  - Replit目标2026年底$10亿run-rate — [二手] [TechBuzz](https://www.techbuzz.ai/articles/replit-hits-9b-valuation-eyes-1b-arr-in-monster-round)
  - Anthropic年内有望达$1000亿run-rate — [未证实，NYT匿名信源] [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)
- **IPO**：Anthropic据报最早2026年10月IPO，三大投行参与早期讨论 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)；10月1日Bloomberg报道目标估值约$2万亿、最早11月中旬上市 — [未证实/二手] [Exploding Topics](https://explodingtopics.com/blog/anthropic-revenue)。OpenAI和Anthropic都在为公开市场做准备，有报道称Anthropic已秘密递交IPO申请 — [Constellation](https://www.constellationr.com/insights/news/openai-touts-broadening-codex-usage-5-million-weekly-active-users)。
- **产品形态向"超级app"收敛**：
  - OpenAI计划把ChatGPT、Atlas浏览器、Codex合并成一个桌面app（3月19日），7月9日Codex app已并入ChatGPT桌面版 — [Wikipedia: Codex](https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent))
  - Nadella称Copilot的"Code"体验会并入统一的消费级加商业级"super app"，GitHub Copilot采用harness与模型分离的架构 — [Microsoft IR](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)
  - Google把终端、IDE、SDK、托管Agent统一到Antigravity平台 — [Google Developers Blog](https://developers.googleblog.com/an-important-update-transitioning-gemini-cli-to-antigravity-cli/)
  - Codex的知识工作者用户占比在上升 — [Constellation](https://www.constellationr.com/insights/news/openai-touts-broadening-codex-usage-5-million-weekly-active-users)
- **模型路线**：
  - Anthropic的5.5代已全部发布（Opus 9月22日、Sonnet 9月28日、Haiku 10月7日）；Fable/Mythos作为顶层，Mythos受限开放 — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_(language_model))
  - OpenAI的GPT-6家族在9–10月陆续发布，Brockman称它"可能最终被视为AGI的到来" — [Wikipedia: GPT-6](https://en.wikipedia.org/wiki/GPT-6)
  - Google Gemini 3.5 Pro因编码表现推迟 — [二手/未证实] [AIToolsReview](https://aitoolsreview.co.uk/insights/gemini-3-5-pro)
  - Antigravity将于2026年11月2日移除Claude 4.6模型 — [Wikipedia: Antigravity](https://en.wikipedia.org/wiki/Google_Antigravity)
- **人才与经济**：Anthropic承诺2027年底前培训1万名工程师；9月9日发布《Scenarios for our economic future》，对到2030年的增长、就业和工资做情景建模（未读取到具体数字） — [Anthropic News](https://www.anthropic.com/news)。Dario预言2026年会出现首个一人运营的十亿美元公司 — [VentureBeat](https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth)。
- **监管与安全门槛**：Mythos、Fable级模型曾被美国出口管制下线（6月12日至7月1日），之后以"网络安全分类器"和可信访问计划的形式恢复 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)；Anthropic在10月扩大Cyber Verification Program并发布"Cyber Mission" — [Anthropic News](https://www.anthropic.com/news)；METR在10月提出四项失控风险提案，其中包括评估"AI自动化对内部能力增长的加速程度" — [METR](https://metr.org/)。
- **评测与研究**：METR计划改用固定任务实验和观察性数据，重新测量开发者提效 — [METR](https://metr.org/blog/2026-02-24-uplift-update/)；Vals.ai已因饱和归档SWE-bench Verified和TB2，转向TB 2.1/4.0等新版 — [Vals TB2](https://www.vals.ai/benchmarks/terminal-bench-2)。

### Inferences
- 2027年格局预判（推断）：
  - ①"三大实验室加xAI系Cursor加微软Copilot"控制大部分开发者席位和token，独立公司（Cognition、Factory、Augment、Replit、Lovable）转向企业交付（自托管、合规、forward-deployed engineer）和垂直场景；资本市场继续支持非赢家通吃（Cognition一年内估值从$102亿到$480亿）。
  - ②定价进一步走向"订阅加按量"：$100档成为主流专业档，企业端按token和成果计价的比例上升。开源权重模型在长尾任务上的份额继续扩大（Vercel 9月已占token的71.5%）。
  - ③产品单位从"会话"变为"工厂或流水线"：多Agent编排、定时和事件触发、自托管云环境、跨会话协作，任务时长以天计。评审、验证和集成会成为主要产品战场，并冲击PR/GitHub范式（Origin、Delta）。
  - ④Agent安全（配置投毒、MCP注入、凭证窃取）和前沿模型的网络安全访问管控，会成为企业采购和跨国可用性的硬门槛。
- 风险提示（推断）：①多家公司的2026年底收入指引（Cursor $60亿以上、Cognition $40–50亿、Anthropic $1000亿）都来自报道或投资人预测，2027年复盘时需核对实际值；②算力约束（Cursor卖身的主因、Anthropic的"基础设施吃紧"）仍可能限制增长和服务质量；③初级工程师管道萎缩的长期代价，可能在2027–2028年以"资深人才断层"的形式显现。

### Gaps
- 没有找到各公司官方公布的2027年具体产品路线图或收入目标（多数公司不公开）。
- 《Scenarios for our economic future》等前瞻报告的具体数字未读取到。
- Anthropic、OpenAI IPO的最终时间和估值未确认（截至10月23日仍是报道）。
