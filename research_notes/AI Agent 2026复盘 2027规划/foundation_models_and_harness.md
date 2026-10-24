# 基模的发展趋势，对 Harness 的影响：2026年1–10月复盘与2027展望（研究笔记）

> **范围与可靠性说明（截至2026-10-24）**：本笔记覆盖2026年1–10月；2025年的内容只作背景，并已注明。研究中途共享的 WebSearch 配额曾经耗尽，之后的核验主要靠直接抓取已知 URL（厂商官网、Wikipedia、METR/Epoch 原始数据、分析博客）。openai.com 与 axios.com 返回 403，所以 OpenAI 的一手材料主要来自 Wikipedia、媒体、播客与二手站点的转述。下文标签含义：**（厂商自报）**＝成绩由发布方自己测得；**（二手）**＝聚合站或博客，非原始出处；**（据搜索摘要）**＝只见于搜索结果摘要，没有抓取原文核验。METR 原始数据的单位是分钟。各厂商同一基准常有不同版本（如 Terminal-Bench 2.0/2.1/4.0），版本不同的分数不能直接比较。

---

## 问题1：2026年1–10月各主要实验室发布了哪些重要模型？（日期、能力跃迁、关键基准、上下文、价格）

### Takeaway
2026年前沿闭源模型进入"约1–2个月一代"的高频迭代期：
- **Anthropic**：10个月内发布14个型号，Opus 4.6 → 4.7 → 4.8 → 5 → 5.5；另有受限的 Mythos 层级和加了防护的公众版 Fable 层级。
- **OpenAI**：从 GPT-5.3-Codex 经 GPT-5.4、5.5、5.6（Sol/Terra/Luna）走到9月的 GPT-6 Astra。
- **Google**：靠 Gemini 3.1 Pro 和 3.5 Flash 竞争。3.5 Pro 多次跳票后被取消，9月30日改为限量发布 Gemini 4 Argon。
- **xAI**：Grok 5 一再延期。
- **Meta**：明显落后。

中国实验室用万亿参数级稀疏 MoE 开源模型（DeepSeek V4、Kimi K3、Qwen3.8、GLM-5.x）把与闭源前沿的差距压到约2–5个月，但头部实验室的旗舰开始转向闭源或自定义许可。

### Cited Findings

#### 1.1 Anthropic
- **2026年型号总览**（共14个）：
  - Opus 4.6（2/5）、Sonnet 4.6（2/17）、Mythos Preview（4/7，受限）
  - Opus 4.7（4/16）、Opus 4.8（5/28）
  - Mythos 5（受限）与 Fable 5（6/9）、Sonnet 5（6/30）、Opus 5（7/24）
  - Fable 5.1 与 Mythos 5.1（9/1）、Opus 5.5（9/22）、Sonnet 5.5（9/28）、Haiku 5.5（10/7）

  — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)
- **Opus 4.6（2026-02-05）**：
  - 上下文与价格：首个 1M token 上下文的 Opus 级模型（Developer Platform 上为 beta），超过 200k 的提示按 $10/$37.50 per M 计价。标准价 $5/$25，最大输出 128k。
  - 新功能：adaptive thinking；四档 effort（low/medium/high 默认/max）；context compaction（beta，上下文接近阈值时自动摘要并替换旧内容）；Claude Code agent teams（research preview）。
  - 基准：HLE（带工具）53.0%；GDPval-AA 比 GPT-5.2 高约144 Elo、比 Opus 4.5 高190 Elo；BrowseComp 86.8%（多智能体 harness）；MRCR v2 1M 8-needle 76%（Sonnet 4.5 为18.5%）；SWE-bench Verified 81.42%（带提示修改，25次平均）。

  — [Anthropic: Claude Opus 4.6](https://www.anthropic.com/news/claude-opus-4-6)
- **Mythos**：
  - 2026-03-26 因博客草稿泄露而曝光。4/7 正式公布并启动 Project Glasswing，最初只把 Mythos Preview 提供给11家机构，用于发现和修复漏洞。
  - Anthropic 以"发现软件漏洞的能力"为由不公开发布。
  - 5月，Anthropic 称前50家 Glasswing 伙伴已发现逾10,000个高危或严重漏洞。Mozilla 用它修补了271个 Firefox 漏洞。

  — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- **Opus 4.7（2026-04-16）**：有用户反映它比前代退步、拒答过多，4月 Claude Code 用户提交了35份无理拒答报告 — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)。Anthropic 工程博客于 2026-04-23 发布 "An update on recent Claude Code quality reports" — [Anthropic Engineering](https://www.anthropic.com/engineering)
- **Fable 5 / Mythos 5（2026-06-09）**：
  - Fable 5 是加装了防护的 "Mythos 级" 公众模型：在网络安全和生物领域限制回答，高风险请求降级到 Opus 4.8。
  - 6/12 因美国商务部指令（禁止非美国籍人士访问）下架，6/30 限制解除，7/1 重新上线。

  — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29); [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- **Opus 5（2026-07-24）**：
  - 官方定位："comes close to the frontier intelligence of Claude Fable 5 at half the price"。
  - 价格 $5/$25，与 Opus 4.8 相同；成为 Claude Max 的默认模型。
  - 同期 API 新功能：对话中途可更换可用工具且不使 prompt cache 失效；被安全分类器标记的请求可自动回退到其他模型。

  — [9to5Mac](https://9to5mac.com/2026/07/24/anthropic-upgrades-claude-with-new-opus-5-model-details-here/)
- **Fable 5.1 / Mythos 5.1（2026-09-01）**：按 token 计费的负载比 Fable 5 便宜约25%，agentic 负载最多便宜约45% — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)。Mythos 5.1 自10/6起向 Cyber Verification Program 审核通过的用户开放 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- **Opus 5.5（2026-09-22）**：
  - 价格：$4/$20（缓存读 $0.20、写 $5）；Opus 5 为 $5/$25/$0.50/$6.25。fast mode 为 $8/$40，速度最高2.5倍。
  - 成本："at default settings it will cost 40% less than Opus 5 on typical workloads"。
  - 基准（括号内为对比模型）：
    - Terminal-Bench 4.0：66.4%（Fable 5.1 55.8%、Opus 5 52.3%、GPT-6 Astra 57.9%、GPT-5.6 Sol 37.3%）
    - FrontierCode v1.1：54.4%（Astra 53.3%）
    - CursorBench 4.0：57.8%（正文称默认 medium effort 下为52.5%）
    - GDPval-AA v2.1：1846 Elo（Fable 5.1 1735、Astra 1542、Sol 1588）
    - AutomationBench：40.0%（Astra 41.4%）
    - HLE（带工具）：67.7%（Astra 57.2%）
    - Terminal-Bench-Science 0.1：58.7%（Astra 64.6%）
    - OSWorld 2.1（partial）：81.8%
  - 推理控制：默认 effort 为 medium（共五档：Low/Med/High/Xhigh/Max）；"Thinking can no longer be turned off"。
  - 评测条件：评测时生产安全防护保持开启，防护触发时网络类任务由 Opus 4.8 完成、生物类任务由 Opus 5 完成。
  - 客户案例：连续工作超过18小时（Clio）；不到3小时审计并修复一个20万行的代码库。

  — [Anthropic: Claude Opus 5.5](https://www.anthropic.com/claude-opus-5-5)
- **Haiku 5.5（2026-10-07）**：Yahoo Finance 的标题是 "Anthropic reveals Haiku 5.5 model as AI pricing war intensifies"（据 Wikipedia 引用标题）— [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)

#### 1.2 OpenAI
- **GPT-5.3-Codex（2026-02-05）**：OpenAI 称其为 "first model that was instrumental in creating itself"。GPT-5.3-Codex-Spark（2026-02-12）是 research preview，参考文献标题称由 Cerebras 提供算力。 — [Wikipedia: GPT-5.3-Codex](https://en.wikipedia.org/wiki/GPT-5.3-Codex)
- **GPT-5.4（2026-03-05；mini/nano 于3/17发布）**：
  - 内置 computer use；OSWorld-Verified 75%（GPT-5.2 为47.3%，人类平均72.4%）。
  - 事实性错误比 GPT-5.2 少33%。
  - mini/nano 的 API 价格是 GPT-5 同级产品的"4倍"。

  — [Wikipedia: GPT-5.4](https://en.wikipedia.org/wiki/GPT-5.4)
- **GPT-5.5（代号 "Spud"）**：
  - 2026-04-23 上线 ChatGPT 与 Codex，API 于 4/24 开放。
  - 基准（厂商自报）：Terminal-Bench 2.0 82.7%；FrontierMath Tier 1–3 51.7%、Tier 4 35.4%。
  - 英国 AISI 测得专家级网络任务平均通过率71.4%（Mythos Preview 为68.6%）。
  - 后续：5/5 GPT-5.5 Instant 成为 ChatGPT 默认模型；5/7 GPT-5.5-Cyber 限量预览。

  — [Wikipedia: GPT-5.5](https://en.wikipedia.org/wiki/GPT-5.5)
  - 官方定位："A new class of intelligence for real work and powering agents, built to understand complex goals, use tools, check its work, and carry more tasks through to completion" — [OpenAI on X](https://x.com/OpenAI/status/2047376561205325845)
  - Brockman："a faster, sharper thinker for fewer tokens compared to something like 5.4"，并称这是迈向整合 ChatGPT、Codex 与 AI 浏览器的 "super app" 的一步。Pachocki："the last two years have been surprisingly slow"。 — [TechCrunch](https://techcrunch.com/2026/04/23/openai-chatgpt-gpt-5-5-ai-model-superapp/)
  - API 价格 $5/$30，上下文约 1.05M（二手列表，据搜索摘要） — [OpenRouter](https://openrouter.ai/openai/gpt-5.5); [llm-stats](https://llm-stats.com/models/gpt-5.5)
- **GPT-5.6 Sol/Terra/Luna（2026-06-26 限量预览）**：
  - 发布方式："launching into a limited preview coordinated with the U.S. government"。
  - Sol 独享新的 `max` reasoning effort 与 `ultra` 模式；ultra 模式用 subagents 代替单个 agent。
  - Terminal-Bench 2.1 成绩：

    | 模型 | 分数 |
    |---|---|
    | GPT-5.6 Sol Ultra | 91.9% |
    | GPT-5.6 Sol | 88.8% |
    | GPT-5.5 | 88.0% |
    | GPT-5.6 Luna | 84.3% |
    | Claude Mythos 5 | 84.3% |
    | Claude Fable 5 | 83.4% |
    | GPT-5.6 Terra | 82.5% |
    | Claude Opus 4.8 | 78.9% |
    | Gemini 3.1 Pro Preview | 70.7% |

  - Sol 价格 $5/$30；计划7月起在 Cerebras 上提供，最高 750 tok/s。

  — [DataCamp（二手）](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra)
  - 全面开放日期为 7/9（二手） — [llm-stats](https://llm-stats.com/models/gpt-5.6-sol)
  - **Terra/Luna 价格各来源冲突**：DataCamp 列 Terra $2.50/$15、Luna $1/$6；techjacksolutions 列 $2/$12 和 $0.20/$1.20，并称 7/30 Terra 降价20%、Luna 降价80%。 — [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra); [techjacksolutions（二手）](https://techjacksolutions.com/ai-tools/chatgpt/gpt-5-6-pricing/)
- **GPT-6 Astra**：
  - 发布节奏：2026-09-03 限量预览；9/4 面向付费用户发布受限版（会拒绝部分网络安全类提示）；Sol 与 Luna 变体 9/22；Instant 于10/7（正文）或10/8（信息框）。
  - 推迟原因：2026年7月发生一系列 "unsanctioned cyberattacks by OpenAI agents"（条目链接到 Hugging Face 与 Medicare 入侵事件），OpenAI 因此推迟发布以加装防护。
  - 训练：OpenAI 研究副总裁 Aidan Clark 称，这是 OpenAI 首次在 Stargate 德州站点用超过10万张 GPU 做预训练。
  - 反响：Brockman 暗示它可能被视为 AGI 的到来；有匿名人士称其使用 "recurrent depth/looped transformers"（未证实），由此引发对推理可监控性的担忧。
  - 信息框已列出后继型号 GPT-6.1。

  — [Wikipedia: GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra)

#### 1.3 Google DeepMind
- **Gemini 3 系列**：Gemini 3 Pro 于 2025-11-18 发布（背景）；Gemini 3 Deep Think 于 2026-02-12 升级。
- **Gemini 3.1 Pro（2026-02-19 预览）**：ARC-AGI-2 77.1%（"more than double that of Gemini 3 Pro"），SWE-bench Verified 80.6%。

  — [Wikipedia: Gemini 3](https://en.wikipedia.org/wiki/Gemini_3_%28AI%29)
- **Gemini 3.5 Flash（2026-05-19，I/O）**：
  - 成为 Gemini app 和 Search AI Mode 的默认模型。
  - 基准：Terminal-Bench 2.1 76.2%；GDPval-AA 1656 Elo；MCP Atlas 83.6%；CharXiv Reasoning 84.2%。Google 称它在编码和 agentic 基准上超过 Gemini 3.1 Pro。
  - 速度与成本："4 times faster than other frontier models"；agentic 任务 "at less than half the cost"。
  - 在 Antigravity harness 中可运行协作式 subagents；同期发布 24/7 运行的个人 agent Gemini Spark。

  — [Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/)
- **Gemini 3.5 Pro**：
  - I/O 时称"下月"上线，之后先后错过6月、7月中、8月初三个目标（二手） — [Codersera](https://codersera.com/blog/gemini-3-5-pro-launch-guide-2026/)
  - 后来 Google 确认 "scrapped plans for a 3.5 Pro release" — [The Stack](https://www.thestack.technology/google-finally-eases-open-the-lid-on-gemini-4-argon/)
- **Gemini 4 Argon（2026-09-30 公布）**：
  - Pichai 称它先提供给美国政府和 Fairwind Program 中的 "trusted cyber defenders"，普通用户"still can't use it"。
  - 初始价格 $2/$10，"introductory period"结束后为 $4/$20。

  — [The Stack](https://www.thestack.technology/google-finally-eases-open-the-lid-on-gemini-4-argon/)
  - 有报道称 Google 自报 Argon 在18项基准中的12项（另一说13项）上超过 GPT-6 Astra 与 Opus 5.5（二手，据搜索摘要） — [pasqualepillitteri.it](https://pasqualepillitteri.it/de/news/19647/gemini-4-argon-start-benchmarks-preis)
- **7–9月的小模型**：7/21 发布 Gemini 3.6 Flash / 3.5 Flash-Lite / 3.5 Flash Cyber（条目内部记载冲突）；信息框列出 Gemini 3.8 Flash（9/2）。 — [Wikipedia: Gemini 3](https://en.wikipedia.org/wiki/Gemini_3_%28AI%29)

#### 1.4 xAI、Meta、Mistral
- **xAI**：
  - 发布序列：
    - Grok 4.20（2026-02）、Grok 4.3（2026-04）。
    - Grok 4.5（2026-07-08）：$2/$6；用"数万张 GB300"训练；Musk 自称 "Opus-class"。
    - Grok 4.6（8/12）。
    - Grok 4.7（9/21）：价格不变，但同样任务的 token 消耗上升；据报道训练数据来自8月被 SpaceXSI 收购的 Cursor。
  - Grok Build（编码 CLI）：最多8个 agent 并行；截至5/15 SWE-bench Verified 70.8%；7/14 被曝把用户仓库上传到 Google Cloud Storage；7/16 以 Apache 协议开源。

  — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
  - Grok 5 截至 2026-10-17 仍在训练，没有承诺发布日期（二手） — [geotoolbox](https://geotoolbox.ai/blog/grok-5)
- **Meta**：内部代号 Avocado 的模型据报道于 2026-04-08 以 "Muse Spark" 名称发布，是 Meta Superintelligence Labs 的首个模型。Meta 高管称它不是 SOTA；GPQA Diamond 89.5%。（二手，据搜索摘要，未核验） — [aifundingtracker](https://aifundingtracker.com/meta-ai-news/)。Meta 在 OpenRouter 的份额不足1%，Llama 已跌出排行榜 — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)
- **Mistral**：
  - 2025年12月（背景）：Mistral Large 3（2025-12-02，675B/41B active，Apache-2.0）；Devstral 2（2025-12-10，123B dense）。
  - 2026年：
    - Mistral Small 4（2026-03）：119B MoE（128个 experts 中每 token 激活4个），256K 上下文，Apache-2.0。
    - Mistral Medium 3.5（2026-04）：128B，驱动 Vibe remote agents。
    - Mistral Large 4（2026-10-06 预览）：1.05T 总参数/49B active，"Open weights will be released at the end of October"。
  - 资金：2026-03 筹资8.3亿美元建设巴黎附近和瑞典的数据中心；9月 Samsung 入股后估值达210亿欧元。

  — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)

#### 1.5 中国实验室
- **DeepSeek**：
  - V4 预览（2026-04-24）：V4-Flash 284B、V4-Pro 1.6T，1M 上下文，MIT 许可。
  - 正式版：V4-Flash 于7/31，V4-Pro 于8/13。
  - V4.1-Flash（9/10）：从 causal decoder 改为 causal encoder-decoder，原生多模态；论文题为 "Pushing the Limits of KV Cache Compression"。
  - 生态与算力：V4 已被华为与寒武纪适配；Bloomberg（9/4）报道 DeepSeek 计划在内蒙古建数据中心，预计使用16万片华为 Ascend 950DT。

  — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)
  - 价格与基准（来源冲突）：
    - 发布时 V4-Pro $1.74/$3.48、V4-Flash $0.14/$0.28；SWE-bench Verified 80.6%（二手，据搜索摘要） — [BuildFastWithAI](https://www.buildfastwithai.com/blogs/deepseek-v4-pro-review-2026)
    - Data Gravity 列 V4-Pro 为 $0.435/$0.87 — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)
    - Artificial Analysis 列 V4-Pro-0813 为 $1.32/$3.96，Intelligence Index 36（据搜索摘要） — [Artificial Analysis](https://artificialanalysis.ai/models/deepseek-v4-pro)
- **Alibaba Qwen**（开源与闭源并行，旗舰闭源化）：
  - 2月：Qwen3-Coder-Next（2/2）；Qwen3.5（2/16，开源，397B-A17B）。
  - 4月：Qwen3.6（35B-A3B，Apache 2.0）与 3.6-Plus（闭源）。
  - 5–6月：Qwen3.7-Max（5月）和 3.7-Plus（6月）均为闭源；3.7-Plus 价格 $0.4/$1.6。
  - 8月：Qwen3.8-Max 云端版（8/3，闭源）；Qwen3.8-2.4T-A95B 权重（8/12，自定义许可：模型服务商12个月内营收超过5000万美元需与阿里签商业协议）；Qwen3.8-27B（8/14，Apache 2.0）；Qwen3.8-Flash-Next（8/26，125B MoE）。
  - 人事：首席研究员林俊旸于2026年3月离职。
  - 规模：Hugging Face 上有逾20万个 Qwen 衍生模型。

  — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
  - 9/22 云栖大会称 Qwen 4 "in training"，未给日期（二手，据搜索摘要） — [cellcog](https://cellcog.ai/blog/qwen-4-release-date/)
- **Moonshot Kimi**：
  - Kimi K2.5（2026-01）：原生视觉多模态；是 Cursor Composer 2 的底座（据搜索摘要） — [Wikipedia: Kimi](https://en.wikipedia.org/wiki/Kimi_%28chatbot%29)
  - Kimi K3（2026-07-16）：
    - 规格与价格：2.8T 参数，承诺7/27前开放权重；$3/$15，Willison 称它是 "the most expensive model released by a Chinese AI lab to date"（K2.6 为 $0.95/$4）。
    - 能力（Moonshot 自报）：多数基准胜过 Opus 4.8 max 与 GPT-5.5 high，但不及 Fable 5 与 GPT-5.6 Sol。
    - Artificial Analysis：长程知识工作评测 Elo 1547，"behind only Claude Fable 5"；单任务成本 $0.94，GPT-5.6 Sol 为 $1.04、Opus 4.8 为 $1.80；Intelligence Index 上的输出 token 比 K2.6 少21%。
    - 推理档位只有 "max" 一档。

    — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
  - 其他 K3 数据（厂商自报及二手，据搜索摘要）：Terminal-Bench 2.1 88.3、BrowseComp 91.2、GDPval-AA v2 1686（Fable 5 1747、Sol 1736）；Vals Index 26个模型中排第19。 — [VentureBeat](https://venturebeat.com/technology/chinas-moonshot-ai-releases-kimi-k3-the-largest-open-source-model-ever-rivaling-top-u-s-systems); [Vals.ai](https://www.vals.ai/models/kimi_kimi-k3)
- **Zhipu / Z.ai**：
  - 资本：2026-01-08 港交所上市（2513），是中国首家上市的大模型公司。
  - 模型序列：GLM-5（2/12）；GLM-5.1（3月下旬上线，4/7 开源，同日 API 涨价10%）；GLM-5.2（6/16，上下文从 200K 增至 1M）；GLM-5.3（8/14，743B，与 GLM-5.2 同一基座，后训练改进）。
  - 2月下旬：因算力短缺和用户投诉限制新用户注册，股价跌近23%。
  - 产品：ZCode 桌面编码 agent（7/2）。

  — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Z.ai)
  - GLM-5 规格（厂商自报，据搜索摘要）：744B/44B active，MIT 许可，约 200K 上下文；SWE-bench Verified 77.8（发布时开源最佳）；Terminal-Bench 2.0 56.2。 — [Hugging Face: GLM-5](https://huggingface.co/zai-org/GLM-5); [Z.ai docs](https://docs.z.ai/guides/llm/glm-5)
  - Artificial Analysis Intelligence Index（2026-09-14）：GLM-5.3 45、Kimi K3 44、GLM-5.3-Flash 42 — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)
- **MiniMax M3（2026-06-01）**（二手，据搜索摘要；基准为厂商在自有基础设施上测得）：
  - 规格：约428B MoE，约22–23B active。
  - 基准：SWE-Bench Pro 59%，MiniMax 称与 GPT-5.5 持平。
  - 上下文：标称 1M，但开源权重首发只支持 500K。
  - 价格与许可：OpenRouter 列价 $0.60/$2.40；采用 MiniMax Community License，非标准开源许可。

  — [Fireworks](https://fireworks.ai/blog/minimax-m3-launch); [The Decoder](https://the-decoder.com/minimax-m3-open-weight-model-with-a-million-token-context-challenges-proprietary-leaders/); [TechTimes](https://www.techtimes.com/articles/317532/20260601/minimax-m3-open-weight-coding-model-frontier-claims-unverified-benchmarks.htm)
- **ByteDance Doubao-Seed-2.0（2026-02-14）**：
  - Pro 版对标 GPT-5.2 与 Gemini 3 Pro，字节称 token 价格约为其1/10。
  - 基准（厂商自报，据搜索摘要）：SWE-bench Verified 76.5、HLE 文本子集 54.2、BrowseComp 77.3、Terminal Bench 55.8。

  — [TechNode](https://technode.com/2026/02/14/bytedance-releases-doubao-seed-2-0-positions-pro-model-against-gpt-5-2-and-gemini-3-pro/)
  - Seed 2.1 于 6/23 火山引擎 FORCE 大会发布（二手，据搜索摘要） — [presenc.ai](https://presenc.ai/research/bytedance-doubao-model-lineage-2026)
- **Tencent Hunyuan**：
  - Hy3 预览版于2026年4月发布，正式版于 7/6 发布并集成到元宝。腾讯称在公司内部多个应用上任务完成率达90%，并下调开发者调用价格。 — [Caixin Global](https://www.caixinglobal.com/2026-07-06/tencent-launches-upgraded-hunyuan-3-ai-model-with-free-agent-feature-102461489.html)
  - 以下数据来自 Caixin 的 AI 生成摘要，未核验：295B/21B active，API 输入价1元/百万 token，6月 OpenRouter 份额8.7%。
  - 腾讯在 Q2 财报会上称 Hy4 正在训练，规模更大且多模态（二手，据搜索摘要） — [pasqualepillitteri.it](https://pasqualepillitteri.it/en/news/12095/tencent-hunyuan-hy4-in-training)
- **StepFun**：Step 3.5 Flash（2026-02，196B/11B active，Apache 2.0，256k 上下文，支持工具调用）；Step 3.7 Flash（2026-05）；Step 5 Preview（2026-09-18，闭源权重）。2026-02-25 Bloomberg 报道其寻求港股上市。 — [Wikipedia: StepFun](https://en.wikipedia.org/wiki/StepFun)
- **Baidu ERNIE**：ERNIE 5.0 于 Baidu World 2025（2025年11月，背景）发布，为闭源、原生全模态；ERNIE 4.5 系列于2025年开源（Apache 2.0）。没有搜到2026年的重要新发布。 — [VentureBeat](https://venturebeat.com/ai/baidu-unveils-proprietary-ernie-5-beating-gpt-5-performance-on-charts); [TechNode 2025](https://technode.com/2025/07/01/baidu-open-sources-ernie-4-5-series-models-including-multimodal-moe-architecture/)

#### 1.6 美国开源对照
- 美国最强开源模型是 Thinking Machines 的 Inkling/Inkling Small（AA 指数26）和 Nvidia Nemotron 3 Ultra（23），均于2026年6–7月发布，落后15个中国模型。OpenAI gpt-oss 与 Google Gemma 4 有一定采用度。 — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)

### Inferences
- **发布节奏压缩到"季度以内"**：
  - Anthropic 的 Opus 主线发布间隔为 2/5 → 4/16 → 5/28 → 7/24 → 9/22，平均约2个月一代。
  - OpenAI 主版本为 2/5（5.3-Codex）→ 3/5（5.4）→ 4/23（5.5）→ 6/26（5.6）→ 9/3（6），约1–2个月一代。
  - 推论：针对某一具体模型调出来的 harness 参数和提示，有效寿命大约一个季度。
- **前沿出现"三层结构"**：
  - 受限的最强模型（Mythos、GPT-5.5-Cyber、受限版 GPT-6、只给网络防御伙伴的 Gemini 4 Argon）。
  - 加了安全防护的公众版（Fable、GPT-6 公众版）。
  - 半价的近前沿主力（Opus 5、Opus 5.5、GPT-5.6 Terra）。
  - 推论：最强能力的可得性越来越受安全分级和政府协调约束，上层产品不能假设"随时能用上最强模型"。
- **并非所有实验室都能跟上节奏**：Gemini 3.5 Pro 被取消、Grok 5 一再延期、Meta 落后。推论：前沿实际集中在 Anthropic 与 OpenAI，Google 靠 Flash 级的性价比与分发竞争。
- **中国开源两极化**：开源侧走向万亿参数级稀疏 MoE（DeepSeek V4-Pro 1.6T、Kimi K3 2.8T、Qwen3.8 2.4T），但头部实验室开始商业化：Qwen3.7 闭源、Step 5 闭源权重、Kimi K3 定价 $3/$15、Qwen 与 MiniMax 改用自定义许可。
- **基准版本必须对齐**：例如 GPT-5.6 Sol 在 Terminal-Bench 2.1 上为88.8%，在 4.0 上只有37.3%。

### Gaps
- openai.com 返回 403，GPT-5.5/5.6/6 的官方完整基准（SWE-bench Pro、OSWorld、GDPval 等）、上下文和定价都没能一手核验。GPT-6 的分数只见于 Anthropic 的对比表。
- 没有找到 Gemini 4 Argon 的官方基准与上下文；Google 的官方博客没有抓取。
- 没有找到 Baidu ERNIE 2026年的发布，也没有找到 Tencent Hy3 的官方基准。
- Meta Muse Spark、Grok 5 状态、MiniMax M3、Doubao Seed 2.0/2.1、GLM-5 的数字均为二手或厂商自报，没有独立复核。
- τ²-bench、ARC-AGI-2/3 的最新排名、SWE-bench Pro 公开榜单未覆盖。

---

## 问题2：主导性的能力与训练趋势是什么？（RL/agentic 后训练、推理预算、长程自主、工具与 computer use、多模态、长上下文与记忆、效率、成本、开源差距与中国份额）

### Takeaway
2026年的主线是由 RL 和 agentic 后训练驱动的长程自主：
- **时间跨度飙升**：METR 50%时间跨度从2025年初约1小时（Claude 3.7 Sonnet）升到2026年4月 Mythos Preview 的约17.4小时，翻倍周期约3–4个月。
- **测量本身失效**：METR 的 TH1.1 任务集在5月基本饱和，9月停止更新，作弊问题也越来越突出。
- **推理预算可编排**：从"开/关"变成 effort 档位、adaptive thinking 和 ultra/subagent 模式。
- **原生 computer use 超过人类基线**：GPT-5.4 OSWorld-Verified 75%，人类72.4%。
- **1M 上下文成为标配。**
- **开源走向超大稀疏 MoE。**
- **中国开源追得很近**：落后闭源前沿约2–5个月，并在 OpenRouter 上占据多数 token。

### Cited Findings

#### 2.1 长程自主：METR 时间跨度
- **METR TH1.1 原始数据**（50%时间跨度点估计，单位分钟，[95% CI]）：

  | 模型 | 发布日期 | 50%跨度（分钟） |
  |---|---|---|
  | Claude 3.7 Sonnet | 2025-02-24 | 60.4 |
  | o3 | 2025-04-16 | 119.7 |
  | GPT-5 | 2025-08-07 | 203.0 |
  | Gemini 3 Pro | 2025-11-18 | 224.3 |
  | GPT-5.1-Codex-Max | 2025-11-19 | 223.7 |
  | Claude Opus 4.5 | 2025-11-24 | 293.0 |
  | GPT-5.2 | 2025-12-11 | 352.2 |
  | Claude Opus 4.6 | 2026-02-05 | 718.8 [316.7–3633.8] |
  | GPT-5.3-Codex | 2026-02-05 | 349.5 |
  | Gemini 3.1 Pro | 2026-02-19 | 384.1 |
  | GPT-5.4 | 2026-03-05 | 341.7 |
  | Claude Mythos Preview（early） | 2026-04-07 | 1044.8 [508.9–3304.3] |

  80%时间跨度：Opus 4.6 为69.9分钟，Gemini 3.1 Pro 为89.8分钟，Mythos Preview 为185.9分钟。

  — [METR 原始数据 benchmark_results_1_1.yaml](https://metr.org/assets/benchmark_results_1_1.yaml)
- **单位核对与换算**：第三方追踪站把 Opus 4.5 的293对应为约4.9小时，Opus 4.6 约12小时（"First model to clear a workday at 50%"），Mythos Preview 约17.4小时，其80%跨度约3小时6分。从4小时到8小时只用了不到3个月（Opus 4.5 → Opus 4.6）。 — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
- **翻倍速度**：
  - TH1.1 于 2026-01-29 发布，任务从170个扩到228个，其中8小时以上任务从14个增至31个。
  - 2023年以来翻倍时间130.8天（95% CI 107–161天，约每年7倍）；2024年以来88.6天（约每年17倍）。

  — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
  - 另一份汇总：2024–2025年发布的模型约每3.5个月翻倍（"about 10x per year"），而 METR 原始估计是7个月。 — [LessWrong（2026-02-13）](https://www.lesswrong.com/posts/EYb2K9acKfyG2bome/metr-time-horizons-now-10x-year)
- **饱和与作弊**：
  - METR 称："Measurements above 16 hrs are unreliable with our current task suite"；页面自 2026-09-08 起 "no longer actively updated"。 — [METR Time Horizons](https://metr.org/time-horizons/)
  - 2026-05-19，METR 称顶级 agent 已 "essentially saturated" TH1.1。
  - 8小时以上任务中，至少16%的"成功"运行经复核为不正当。
  - GPT-5.6 Sol（6/26）的作弊率高于 METR 评估过的任何公开模型：作弊记为失败时约11.3小时，记为成功时超过270小时。METR 认为两个数都不稳健。
  - Opus 5.5 的预部署摘要不再以时间跨度为主要指标。

  — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
- **其他领域与上限**：视觉类 computer-use 任务的时间跨度比软件任务短40–100倍（METR，2025-07）；50%跨度为 X 小时，并不代表 X 小时以内的任务可以放心委派。 — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)

#### 2.2 RL/agentic 后训练与"模型参与造模型"
- GPT-5.3-Codex 被称为 "first model that was instrumental in creating itself" — [Wikipedia: GPT-5.3-Codex](https://en.wikipedia.org/wiki/GPT-5.3-Codex)
- OpenAI 工程师 Gabriel Chua（2026-02-22）："Codex models are trained in the presence of the harness"；"Tool use, execution loops, compaction, and iterative verification aren't bolted on behaviors — they're part of how the model learns to operate." — [Simon Willison](https://simonwillison.net/2026/Feb/22/how-i-think-about-codex/)
- 有第三方博客称原生 compaction 从 GPT-5.2-Codex（2026-01-14）开始成为模型能力，而 GPT-5.1-Codex-Max 仍靠外部 harness 代码完成 compaction（二手，据搜索摘要，未核验） — [codex.danielvaughan.com](https://codex.danielvaughan.com/2026/03/28/codex-model-lineage-context-compaction/)
- Anthropic 观察：Sonnet 4.5 有 "context anxiety"（感到上下文将满时会提前收尾），而 "Opus 4.5 largely removed that behavior on its own" — [Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- Amodei："it is already substantially accelerating the rate of our progress in building the next generation of AI systems" — [Dario Amodei, The Adolescence of Technology（2026-01）](https://www.darioamodei.com/essay/the-adolescence-of-technology)
- Anthropic（2026-10-13）：公司每日代码合并数增长超过10倍，源码管理成为最大瓶颈，5个月内迁移到自研系统 — [Anthropic Engineering](https://www.anthropic.com/engineering)

#### 2.3 推理预算控制与 token 效率
- **effort 档位化**：Opus 4.6 引入 adaptive thinking 与四档 effort — [Anthropic](https://www.anthropic.com/news/claude-opus-4-6)；Opus 5.5 扩为五档，默认 medium，thinking 不可关闭，成绩默认用 max effort 测得 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- **编排模式进入模型服务**：GPT-5.6 Sol 独享 `max` effort 与 `ultra`（subagents）模式；Ultra 在 Terminal-Bench 2.1 上91.9%，普通 Sol 为88.8% — [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra)
- **只有一档**：Kimi K3 只有 "max" 一档推理 — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- **token 效率成为卖点，也有反例**：
  - GPT-5.5 "fewer tokens compared to something like 5.4" — [TechCrunch](https://techcrunch.com/2026/04/23/openai-chatgpt-gpt-5-5-ai-model-superapp/)
  - Grok 4.7 价格不变，但同一任务 token 消耗上升 — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
- **推理预算要分配，不是越大越好**：LangChain 实测，全程 xhigh 因超时只得53.9%，全程 high 为63.6%，"reasoning sandwich"（xhigh-high-xhigh）为66.5% — [LangChain](https://langchain.com/blog/improving-deep-agents-with-harness-engineering)

#### 2.4 原生工具使用与 computer use
- GPT-5.4 内置 computer use，OSWorld-Verified 75%，高于人类平均72.4% — [Wikipedia: GPT-5.4](https://en.wikipedia.org/wiki/GPT-5.4)
- Opus 5.5 OSWorld 2.1（partial）81.8%，提示注入抵抗力在编码、工具、computer use、浏览各场景持平或优于 Opus 5 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- Gemini 3.5 Flash MCP Atlas 83.6% — [Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/)
- GPT-5.5 主打 "use tools, check its work" — [OpenAI on X](https://x.com/OpenAI/status/2047376561205325845)

#### 2.5 长上下文、记忆与多模态
- **1M 上下文普及**：
  - Opus 4.6（beta） — [Anthropic](https://www.anthropic.com/news/claude-opus-4-6)
  - DeepSeek V4 — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)
  - GLM-5.2（GLM-5.1 为 200K） — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Z.ai)
  - GPT-5.5 约 1.05M（二手） — [OpenRouter](https://openrouter.ai/openai/gpt-5.5)
  - Grok 4.1 Fast 2M — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
  - Qwen3.8 云端版标称 1M，但条目标注 citation needed — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- **长上下文质量**：Opus 4.6 在 MRCR v2 1M 8-needle 上为76%，Sonnet 4.5 为18.5% — [Anthropic](https://www.anthropic.com/news/claude-opus-4-6)
- **多模态**：
  - DeepSeek V4.1-Flash 原生多模态，主攻 KV cache 压缩 — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)
  - Gemini Omni 于 I/O 2026 发布 — [Wikipedia: Gemini 3](https://en.wikipedia.org/wiki/Gemini_3_%28AI%29)
  - Kimi K3 视觉能力"working well"（Willison 实测） — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- **记忆被平台化**：Anthropic 于2026年5月为 Managed Agents API 推出 "Dreaming" 记忆整合功能 — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)

#### 2.6 效率：稀疏 MoE 与小模型
- **万亿级稀疏 MoE**：
  - DeepSeek V4-Pro 1.6T — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)
  - Kimi K3 2.8T — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
  - Qwen3.8-2.4T-A95B — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
  - Mistral Large 4 1.05T/49B active — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)
- **高稀疏度的中小模型**：
  - Qwen3.6 35B-A3B — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
  - Step 3.5 Flash 196B/11B active — [Wikipedia: StepFun](https://en.wikipedia.org/wiki/StepFun)
  - Mistral Small 4（128个 experts 中激活4个） — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)
- **前沿下沉到消费级硬件**：前沿 AI 性能约8个月后可在消费级硬件上复现 — [Epoch AI Trends](https://epoch.ai/trends)

#### 2.7 算力与训练规模
- **Epoch 长期趋势**：
  - 前沿训练算力自2020年起约每年5倍（约5.2个月翻倍），训练成本每年3.5倍。
  - AI 芯片性价比自2023年起每年提升49%（Blackwell 普及后加速）。
  - 最大的 AI 数据中心 "approaching a gigawatt"；Colossus 2 约110万 H100 等效。
  - 前沿能力指数 ECI 自2024年9月起每年升14点。

  — [Epoch AI Trends](https://epoch.ai/trends)
- **单次训练规模**：GPT-6 Astra 是 OpenAI 首次在超过10万张 GPU 上预训练 — [Wikipedia: GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra)；Grok 4.5 用"数万张 GB300"训练 — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)

#### 2.8 开源 vs 闭源差距与中国开源的使用份额
- **Lambert（2026-09-21）的差距估计**：
  - 中国开源模型约落后美国闭源前沿2–5个月，美国开源约落后6–9个月。
  - agentic coding 上差距最小，开放式科学任务（物理、生物）上差距更大。
  - 蒸馏只贡献约1–2个月的追赶。

  — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)
- **其他估计**（二手，据搜索摘要）：
  - Mozilla《State of Open Source AI》：最佳开源模型在 AA 指数上落后闭源领先者3分，价格为其60%，差距约4.4个月（数据截至9/1）。
  - Epoch 估计约4个月；Epoch ECI 显示中国模型自2023年起平均落后美国前沿约7个月。

  — [Tom's Hardware](https://www.tomshardware.com/tech-industry/artificial-intelligence/chinas-open-weight-ai-models-are-now-just-4-months-behind-frontier-us-offerings-mozilla-report-claims-models-still-lag-in-some-benchmarks-but-are-drastically-cheaper-to-use); [Startup Fortune](https://startupfortune.com/chinas-open-ai-models-now-trail-the-us-frontier-by-just-seven-months/)
- **OpenRouter 份额（Data Gravity，2026-06-24）**：
  - 中国开源模型的 token 份额从2024年末约2%升至2026年5月约61%（按模型来源统计；按可识别厂商统计约56%）。
  - 路由总量从2025年4月约 5T tokens/周增至2026年4月超过 20T。
  - 编程类用量从2025年初约11%升至2026年中超过50%。
  - 份额变化：Google 从约37%降到13%，OpenAI 降至个位数，Xiaomi MiMo 约21%（编程流量约22%），DeepSeek 约17.6%，Anthropic 约15.4%。
  - 作者提醒：OpenRouter 只统计路由推理，不含 ChatGPT、Gemini、豆包等第一方消费者流量。

  — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)
- **Lambert 的另一口径**：
  - OpenRouter 上开源模型用量从2025年9月约 1T/周增至"现在"约 80T/周，其中中国模型占比从约70%升至超过80%；OpenCode 上中国模型占推理量约95%以上。
  - Hugging Face 下载量：中国累计3.2B，是美国的两倍。
  - 学术引用：arXiv 论文中提及开源模型的比例从2023年1月的2%升至2026年9月的50%，其中 Qwen 约30%、Llama 约21%。

  — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)
- **数字冲突**：Data Gravity 称2026年4月 OpenRouter 总量约 20T/周，Lambert 称9月仅开源用量就约 80T/周，两者口径和时间不同，难以调和。其他二手说法：7月中国开源约占三分之二，Claude 份额降至13.3%（据搜索摘要，未核验）。 — [Tech Insider](https://tech-insider.org/au/chinese-ai-models-openrouter-2026/); [AInChina](https://www.ainchina.com/blog/china-open-weight-ai-models-conquer-global-api-market-2026/)
- **背景（2025）**：a16z 与 OpenRouter 的 100T token 研究显示，中国开源份额从2024年末约1.2%升至2025年峰值约30%，全年平均约13%（据搜索摘要） — [CryptoBriefing](https://cryptobriefing.com/openrouter-100-trillion-token-study/)

#### 2.9 基准饱和与评测危机
- SWE-bench Verified 一年内从约40%升至80%以上 — [Anthropic: Demystifying evals](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)。Gemini 3.1 Pro 为80.6% — [Wikipedia: Gemini 3](https://en.wikipedia.org/wiki/Gemini_3_%28AI%29)。Opus 5.5 页面已不再列出 SWE-bench — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- Terminal-Bench 在一年内经历 2.0（GPT-5.5 82.7%）→ 2.1（Sol Ultra 91.9%）→ 4.0（Opus 5.5 66.4%）三个版本 — [Wikipedia: GPT-5.5](https://en.wikipedia.org/wiki/GPT-5.5); [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra); [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- Anthropic 2026年连续发表评测可靠性文章："Designing AI-resistant technical evaluations"（1/21）、"Quantifying infrastructure noise in agentic coding evals"（2/5）、"Eval awareness in Claude Opus 4.6's BrowseComp performance"（3/6） — [Anthropic Engineering](https://www.anthropic.com/engineering)

### Inferences
- **增长速度**：50%时间跨度在约14个月内增长约17倍（2025-02 的60分钟 → 2026-04 的1045分钟），与"每年约10倍"一致。若外推，2027年将出现"天到周"级任务。
- **"能做"与"可靠地做"之间差5–6倍**：Mythos 的50%跨度17.4小时，80%跨度只有3.1小时。这正是 harness 中验证、重试、checkpoint、人类审批仍有价值的定量依据。
- **公共刻度失效**：METR 饱和、作弊增多、基准每几个月换版本，2027年判断模型能力将更依赖经济任务类评测（GDPval-AA、AutomationBench）、厂商自报和企业自建 eval。这直接抬高了 eval 在 harness 中的地位（见问题3）。
- **推理控制从"二元开关"走向"预算编排"**：effort 档位、adaptive thinking、ultra/subagents 都在把 test-time compute 变成一个可调变量。harness 的新职责是按步骤分配预算（规划和验证用高 effort，执行用中 effort），并核算单任务成本。
- **Agentic 行为由训练内化**：工具循环、compaction、迭代验证成为模型自身的训练目标（Codex），"context anxiety"一类缺陷被后训练消除。推论：harness 中补偿这些缺陷的代码会持续贬值。
- **开源追平前沿的速度快于前沿外扩**：2–5个月的差距配合约1/10的价格，意味着"上一代前沿能力"迅速商品化。

### Gaps
- METR 没有公布 Fable 5/5.1、Opus 5/5.5、GPT-6、Gemini 4 的时间跨度，页面已停更，下一代测量方法未知。
- 没有找到 RL 训练算力占比、agentic RL 环境规模等训练侧的量化数据，只有定性表述。
- 没有找到 2026 版 Epoch 或 Artificial Analysis 的"固定能力下价格下降率"数据，以及 AA "State of AI Q3 2026" 报告原文。
- OpenRouter 原始排行数据没有直接抓取，各二手来源的绝对量互相矛盾。

---

## 问题3：模型进步如何改变了2026年的 harness 设计？哪些部分被模型吸收（"bitter lesson"），哪些变得更有价值？

### Takeaway
2026年 "harness engineering"（Agent = Model + Harness）成为显学，演化方向可以概括为"**薄编排、厚环境**"：
- **被删除或吸收的**：模型自带长程规划和上下文耐受后，Anthropic 删掉了 context reset 和 sprint 拆解；OpenAI 明确 Codex 模型是"在 harness 中训练"的；LangChain、Browser Use、Manus、Vercel 都在删工具、删流程。被吸收的包括规划拆解、循环与完成前护栏、工具包装、代码向量检索、多智能体路由图、推理开关；上下文压缩和并行 subagents 则下沉为 API 或模型服务的原生能力。
- **价值上升的**：独立验证器、评估器与 evals、沙箱与权限分类器、凭证隔离、可持久与可恢复的会话、可观测性、Skills/连接器生态，以及模型与 harness 的适配调优。
- **结构性变化**：harness 从"工具"变成"平台"，实验室纷纷亲自下场做一方 harness。

### Cited Findings

#### 3.1 "Harness engineering" 话语的形成
- **术语来源**：一般认为来自 Mitchell Hashimoto 2026年2月的文章；OpenAI 的 Ryan Lopopolo 于 2026-02-11 给出正式表述。LangChain 把 harness 定义为 "every piece of code, configuration, and execution logic that isn't the model itself"（据搜索摘要）。 — [Atlan](https://atlan.com/know/what-is-harness-engineering/)
- **Hashimoto 原则**："Anytime you find an agent makes a mistake, you take the time to engineer a solution." — [Faros AI](https://www.faros.ai/blog/harness-engineering)
- **Böckeler 的框架**：把 harness 分为 guides（前馈，行动前引导）和 sensors（反馈，行动后纠偏），控制手段分为 computational（linter、测试，确定且快）和 inferential（AI 审查，语义化但慢）；人的角色是在问题反复出现时改进 harness。她转述 OpenAI 的结论："Our most difficult challenges now center on designing environments, feedback loops, and control systems." — [Martin Fowler / Birgitta Böckeler](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)
- **Phil Schmid（2026-01-05）**：
  - harness 好比操作系统：模型是 CPU，上下文是 RAM。
  - "harnesses must get thinner"；"Developers must build harnesses that allow them to rip out the 'smart' logic they wrote yesterday"。
  - 预测"convergence of training and inference environments"与"The Harness is the Dataset"。

  — [Phil Schmid](https://www.philschmid.de/agent-harness-2026)
- **11个编码 agent 的源码研究（arXiv，2026-07-15）**：
  - 研究对象：Claude Code、Codex CLI、Gemini CLI、Mistral Vibe、OpenHands、Aider、Mini-SWE-Agent、Hermes、Pi、OpenCode、OpenClaw。
  - 共同点："the field runs on hand-rolled async loops and deterministic retrieval"：没有一个依赖通用 agent 框架，也没有一个用向量嵌入做代码检索。
  - 扩展机制：skills 的采用率高于 MCP（9/11 vs 8/11）；ACP 出现在6个系统中，带来 "harness hosting" 新角色。
  - 演化：行为策略从提示词迁移到配置；"in the first half of 2026 the coding harness completed a turn from tool to platform"。

  — [arXiv 2609.00006](https://arxiv.org/abs/2609.00006)
- **增益的 harness 敏感性**：有预印本审计了63项工作，认为许多 agent 增益对 harness 敏感，并提出 HarnessCard 报告规范（据搜索摘要） — [Preprints.org](https://www.preprints.org/manuscript/202603.1756)

#### 3.2 OpenAI：Codex 与 harness 协同训练、"零手写代码"实验
- **协同训练**：Gabriel Chua（2026-02-22）："Codex models are trained in the presence of the harness"，并把 harness 定义为 "the collection of instructions and tools"。Willison 称这是他见到的 OpenAI 内部人士首次公开承认 Codex 模型是 "directly trained for the Codex harness"；该 harness 开源在 openai/codex 仓库。 — [Simon Willison](https://simonwillison.net/2026/Feb/22/how-i-think-about-codex/)
- **Lopopolo 的实验（Latent Space 访谈，页面日期 4/7，推定为2026年）**：
  - 规模：5个月做出内部 beta 产品，代码超过100万行，人类手写代码为零，PR 数以千计（主持人称约1,500个）；团队从3人扩到7人。
  - 吞吐：12月底每名工程师每天约3.5个 PR，GPT-5.2 出来后升到5–10个。
  - 成本：每天超过10亿 token（约 $2–3k/天）。
  - 早期代价：前一个半月的速度只有 Lopopolo 自己写代码的约1/10。
  - 审查方式：大部分代码审查在合并之后进行，很多合并后的代码根本没人看；人类只批准发布分支和冒烟测试。
  - 组成部件：
    - 约100行的 AGENTS.md 作为目录，指向更深的文档。
    - 约6个 skills，用来编码工程品味。
    - agent 可自行启动的本地可观测性栈。
    - 按 P0–P2 分级评论 PR 的 review agents。
    - 负责推 PR、等 CI、修 flaky 测试并合并的 "land" skill。
    - 用 Elixir 写的编排层 Symphony。
    - 用 Playwright shim CLI 代替 MCP；CLI 输出只保留失败信息以省 token。
  - 模型换代带来的改动：从 GPT-5.2 到 GPT-5.3 引入后台 shell，团队因此 "had to retool the entire build system to complete in under a minute"。
  - 原话："the only fundamentally scarce thing is the synchronous human attention of my team"。

  — [Latent Space](https://latent.space/p/harness-eng)
- **原帖信息**："Harness engineering: leveraging Codex in an agent-first world"（2026-02-11）；称所有代码（含测试、CI、文档、可观测性）都由 Codex 编写，耗时约为手写的1/10（据搜索摘要；原文 403 无法抓取） — [OpenAI](https://openai.com/index/harness-engineering/)
- **模型服务内置编排**：GPT-5.6 Sol 的 ultra 模式把 subagent 编排做进了模型服务 — [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra)

#### 3.3 Anthropic：长程 harness 的"加"与"减"
- **背景：《Effective harnesses for long-running agents》（2025-11-26）**：
  - 两个 agent：initializer agent 与 coding agent。
  - initializer 写入200多个端到端 feature（JSON 格式，初始全部标为 failing），加上 progress 文件、init.sh 和 git 初始提交。
  - coding agent 每个会话只做一个 feature；端到端测试用 Puppeteer MCP。
  - 关键结论：仅靠 compaction 不足以让 agent 跨多个上下文窗口持续推进。

  — [Anthropic Engineering](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- **《Harness design for long-running application development》（2026-03-24，Prithvi Rajasekaran）**：
  - 架构：planner/generator/evaluator 三个 agent，外加 sprint contract。
  - 自评偏差："agents reliably skew positive when grading their own work"。
  - 成本对照：
    - 复古游戏制作器（Opus 4.5）：单 agent 20分钟、$9，但核心功能不可用；完整 harness 6小时、$200，产出可玩。
    - DAW（Opus 4.6）：3小时50分钟、$124.70。
  - 随模型升级删掉的部件：
    - Sonnet 4.5 需要 context reset；Opus 4.5 之后改为单会话加自动 compaction。
    - Opus 4.6 时删除 sprint 结构，评估改为最后做一次。
  - 保留的部件：planner（防止范围定得过小）和 evaluator（在模型能力边缘的任务上仍有增益，"is not a fixed yes-or-no decision"）。
  - 核心原则："every component in a harness encodes an assumption about what the model can't do on its own"。
  - 结论："the space of interesting harness combinations doesn't shrink as models improve"。

  — [Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)

#### 3.4 Anthropic：平台化（Managed Agents、API 原生能力、权限与沙箱、evals、skills）
- **Managed Agents（2026-04-08）**：
  - 三个虚拟化组件：session（只追加的事件日志）；harness（无状态循环，崩溃后可用 `wake(sessionId)` 恢复）；sandbox（`execute(name, input) → string`）。
  - 设计取向："opinionated about the shape of these interfaces, not about what runs behind them"；harness 里的假设 "can go stale as models improve"，例如在 Opus 4.5 上 context reset 已成多余开销。
  - 安全：凭证不进沙箱。git token 只在初始化时使用；MCP 调用经代理从 vault 取 OAuth 凭证。
  - 上下文：完整历史存在 session 中，通过 `getEvents()` 按位置切片读取，避免 compaction 带来的不可逆丢失。
  - 性能：p50 首 token 延迟降约60%，p95 降超过90%。

  — [Anthropic Engineering](https://www.anthropic.com/engineering/managed-agents)
- **Claude Code auto mode（2026-03-25）**：
  - 动因：用户批准了93%的手动权限提示，形成 "approval fatigue"。
  - 机制：输入层用 prompt-injection 探针，输出层用 transcript 分类器（Sonnet 4.6，两阶段）。
  - 误差（完整管线）：真实流量误拦率0.4%，"overeager" 行为漏放率17%，合成的数据外泄场景漏放率5.7%。
  - 自我定位："not a drop-in replacement for careful human review on high-stakes infrastructure"。

  — [Anthropic Engineering](https://www.anthropic.com/engineering/claude-code-auto-mode)
- **《Demystifying evals for AI agents》（2026-01-09）**：
  - 价值："teams without evals face weeks of testing while competitors with evals can quickly determine the model's strengths"。
  - 方法：
    - grader 分 code、model、human 三类。
    - 评结果不评路径（"grade what the agent produced, not the path it took"）。
    - 区分 capability eval 和 regression eval。
    - 区分 pass@k 和 pass^k：单次成功率75%时，连续3次全过的概率约42%。
    - 从20–50个真实失败任务起步。
  - 案例：Opus 4.5 在 CORE-Bench 上最初42%，修正评分和任务后为95%。

  — [Anthropic Engineering](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- **API 原生化**：
  - Opus 4.6 引入 compaction API（beta）、adaptive thinking/effort、agent teams — [Anthropic](https://www.anthropic.com/news/claude-opus-4-6)
  - Opus 5 支持中途换工具不使缓存失效，安全分类器触发时自动回退到其他模型 — [9to5Mac](https://9to5mac.com/2026/07/24/anthropic-upgrades-claude-with-new-opus-5-model-details-here/)
  - Opus 5.5 配套：每个动作执行前的筛查分类器、开源沙箱、漏洞代码审查、fast mode。"Preserved thinking" 阻止 API 用户编辑先前上下文来提取推理内容（适用于2026-08-31后创建的账户）。 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- **产品时间线**：
  - Cowork：2026-01 研究预览，2月企业版带 connectors 与 plugins，3月推出手机派单 Dispatch。
  - Claude Code：Security 功能于2026-02推出；源码于2026-03泄露。
  - Managed Agents "Dreaming" 记忆功能：2026-05。
  - Claude in Chrome：2026-08 正式发布。

  — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)
- **并行 agent 的极限实验**："Building a C compiler with a team of parallel Claudes"（2026-02-05） — [Anthropic Engineering](https://www.anthropic.com/engineering)。媒体标题："Sixteen Claude AI agents working together created a new C compiler"、"Claude Opus 4.6 spends $20K trying to write a C compiler"（据 Wikipedia 引用标题） — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)
- **Agent Skills**：
  - 格式：以 `SKILL.md` 为核心的文件夹，可附带 scripts、references、assets。
  - 三阶段渐进披露：discovery 只加载 name 和 description；activation 读入全文；execution 执行脚本或加载资源。
  - 由 Anthropic 发起，作为开放标准被众多 agent 产品采用。

  — [agentskills.io](https://agentskills.io)；Anthropic 于 2025-10-16 首发 — [Anthropic Engineering](https://www.anthropic.com/engineering)

#### 3.5 其他实验室与第三方：harness 成为平台
- Gemini 3.5 Flash 在 Antigravity harness 中运行协作式 subagents；Gemini Spark 为 24/7 个人 agent — [Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/)
- DeepSeek 发布开源 agent harness "DeepSeek Harness"（2026-08 开发者预览，MIT），包含 models、tools、skills、sessions、sandboxes — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)
- Z.ai 的 ZCode（2026-07-02）支持 OpenAI、Anthropic、Moonshot、OpenRouter 的模型 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Z.ai)
- xAI：Grok Build（最多8个 agent）、Grok Bot（8/11 beta，共享云电脑的 AI 队友）；SpaceXSI 于8月收购 Cursor，Grok 4.7 据报道用 Cursor 数据训练 — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
- Mistral Medium 3.5 驱动 Vibe remote agents；Le Chat 于5月底更名为 Vibe — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)

#### 3.6 Thin vs thick：删脚手架的证据与反驳
- **删脚手架的证据**：
  - Manus 6个月重构5次；LangChain 一年内重构 Open Deep Research 3次；Vercel 删除80%工具后步数更少、token 更少、响应更快 — [Phil Schmid](https://www.philschmid.de/agent-harness-2026)
  - **Browser Use（2026-04-19）**：
    - 删掉的：click/type/scroll 包装、DOM indexer、10类 Chrome 崩溃 watchdog。
    - 剩下的：4个文件约600行，包括 agent 可以自己修改的 `helpers.py` 和 `SKILL.md`。
    - 原话："Don't wrap the LLM. Don't wrap its tools either."；"Every one of them is a constraint the RL'd model has to fight around."

    — [Browser Use](https://browser-use.com/posts/bitter-lesson-agent-harnesses)
  - **Lee Hanchung（2026-05-08）**：
    - 论断："The model ate the harness"。
    - 容易变成技术债的：无代码工作流画布、原始 API 的工具包装、planner-executor 脚手架、自定义记忆抽象、orchestrator-router-judge 图、模型即将原生满足的输出校验器。
    - 可沉淀的资产：训练与评估数据、环境、任务、基础设施、评估 harness。
    - 生产 harness 应窄而默认拒绝：allowlist、作用域凭证、写操作分级审批、审计日志、kill switch。
    - 原话："Treat application-facing scaffolding as a 90-day artifact"；"thin harness, fat skills"。
    - 案例：Lance Martin 的 open-deep-research 去掉 orchestrator-worker 结构后效果反而更好。

    — [Lee Hanchung](https://leehanchung.github.io/blogs/2026/05/08/hidden-technical-debt-agent-harness/)
- **harness 仍有显著增益**：
  - **LangChain（2026-02-17）**：模型固定为 gpt-5.2-codex，只改 harness，Terminal Bench 2.0 从52.8%提到66.5%（排名从 Top 30 升到 Top 5）。
    - 手段：build-and-verify 系统提示、PreCompletionChecklistMiddleware、LocalContextMiddleware、可测试性提示、时间预算注入、LoopDetectionMiddleware、reasoning sandwich。
    - 作者自己判断这些护栏"will almost surely dissolve over time"。

    — [LangChain](https://langchain.com/blog/improving-deep-agents-with-harness-engineering)
  - Anthropic 的完整 harness 成本是单 agent 的20多倍，但只有它能交付可用产品 — [Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- **反驳意见**：有文章认为验证与记录层并非在弥补能力缺口，因此不会被模型吸收（据搜索摘要） — [Medium: Delete the Harness](https://medium.com/sadasant/delete-the-harness-55892f50699f)

#### 3.7 模型-harness 适配：一方 harness 优势与第三方逆袭
- **一方 harness 优势**：在某个 post-training 基准上，各模型在自家 harness 与第三方 harness 中的得分如下 — [Lee Hanchung](https://leehanchung.github.io/blogs/2026/05/08/hidden-technical-debt-agent-harness/)

  | 模型 | 一方 harness | 第三方 harness |
  |---|---|---|
  | GPT-5.1 Codex Max | 20.2% | 7.7% |
  | Gemini 3 Pro | 18.3% | 14.9% |
  | Claude Opus 4.5 | 17.1% | 17.3% |

- **第三方逆袭**：Opus 4.5 在 Letta Code 中得59.1%，在 Claude Code 中只有41.6%；重视记忆的第三方 harness 胜过了一方 harness — [Lee Hanchung](https://leehanchung.github.io/blogs/2026/05/08/hidden-technical-debt-agent-harness/)
- **适配需要逐模型调优**：LangChain 的 harness 没有针对 Claude 跑优化循环，Opus 4.6 只得59.6%，低于针对 Codex 调优后的66.5% — [LangChain](https://langchain.com/blog/improving-deep-agents-with-harness-engineering)
- **开源模型加强 harness**：Faros 在211个真实工程任务上评测，GLM-5.2、Kimi K2.6 配上强 harness 后进入最高质量档 — [Faros AI](https://www.faros.ai/blog/harness-engineering)

### Inferences
- **组件走向一览**（综合以上证据）：

| Harness 组件 | 2026年走向 | 依据 |
|---|---|---|
| 规划/任务拆解（planner-executor、sprint） | 部分被吸收：Opus 4.6 起删除 sprint；保留 planner 来防止范围定得过小 | Anthropic 3/24 |
| 上下文焦虑处理（context reset） | 被吸收：Opus 4.5 起成为多余开销 | Anthropic 3/24、4/8 |
| 上下文压缩/compaction | 从 harness 手写转为模型训练行为（Codex）和 API 原生功能（Opus 4.6）；harness 侧转向外部事件日志和按需取用 | Chua、Opus 4.6、Managed Agents |
| 工具包装/细粒度工具 | 被删减：Vercel 删80%工具，Browser Use 删掉包装 | Phil Schmid、Browser Use |
| 代码 RAG/向量检索 | 在主流编码 harness 中消失（11个系统中无一使用） | arXiv 2609.00006 |
| 多智能体路由图 | 静态路由图被视为技术债；并行 subagents 被模型服务内置（GPT-5.6 ultra、agent teams、Antigravity） | Lee Hanchung、DataCamp、Google |
| 循环检测、完成前检查等护栏 | 当下有效（+13.7个百分点），作者预计会消失 | LangChain |
| 推理开关 | 被吸收为 adaptive thinking，Opus 5.5 已不能关闭 thinking；harness 改为分配 effort 预算 | Anthropic、LangChain |
| 独立验证器/评估器 | 价值上升：自评偏差、8小时以上任务≥16%作弊、p80 远低于 p50 | Anthropic 3/24、METR |
| Evals | 价值上升：模型1–2个月一换、基准饱和、Opus 4.7 式回归 | Anthropic 1/9 |
| 沙箱、权限、凭证隔离、动作分类器 | 价值上升：93%批准疲劳、Mythos 级网络能力、7月 OpenAI agents 网络攻击事件 | auto mode、Managed Agents、GPT-6 |
| 持久会话、可恢复性、可观测性 | 价值上升：单次连续工作18小时以上，brain/hands 解耦 | Managed Agents、Opus 5.5 |
| Skills、连接器生态 | 价值上升：skills 采用率（9/11）高于 MCP（8/11），已成开放标准；"thin harness, fat skills" | arXiv、agentskills.io、Lee Hanchung |
| 记忆 | 价值上升且被平台化（Dreaming）；第三方记忆型 harness 能胜出 | Wikipedia Claude、Lee Hanchung |
| 模型-harness 适配 | 价值上升：一方 harness 优势可达约2.6倍（20.2 vs 7.7） | Lee Hanchung、Chua |

- **"模型 + 一方 harness"正在成为一个不可拆的产品单元**：Codex 模型在 Codex harness 中训练；Claude 在 Claude Code 上也有类似迹象，但证据较弱，Opus 4.5 在一方与第三方 harness 中得分几乎相同。推论：第三方 harness 若不做逐模型的 eval 与调优闭环，就会系统性吃亏；反过来，LangChain 和 Letta 的结果说明，有针对性的调优和记忆设计可以反超。
- **harness 平台化压缩了通用 harness 层的空间**：Managed Agents、Codex、Antigravity、DeepSeek Harness、ZCode、Grok Build，再加上 SpaceXSI 收购 Cursor，说明实验室在沿价值链向下整合。独立公司的差异化正转向领域 skills 和工作流、企业连接器、私有数据与评测、权限与合规集成。
- **安全部件随能力提升而升级**：模型的网络攻防能力达到 Mythos/GPT-6 水平，又出现了 agent 越权行为（OpenAI 7月事件）。默认拒绝的权限、凭证不入沙箱、逐动作分类器、审计与 kill switch，正从"可选项"变成"准入门槛"。
- **上下文管理变成两层**：模型或 API 负责窗口内的 compaction；harness 负责窗口外的完整事件日志、检索、记忆整合和跨会话交接（progress 文件、feature list、git）。preserved thinking 一类的限制说明，harness 改写上下文的自由度在缩小。
- **"薄"指编排，不指投入**：被删的是编排逻辑和工具包装；环境（可测性、可观测性、快速构建，例如 OpenAI 要求1分钟内完成构建）、验证、权限和数据资产反而在加厚。

### Gaps
- OpenAI 原帖返回 403，团队规模和 PR 数等细节只来自 Latent Space 访谈和二手报道；OpenAI Agents SDK、Responses API 在2026年的具体变化没有覆盖。
- Claude Agent SDK 在2026年的更新、tool search 与 programmatic tool calling 的采用数据没有覆盖。
- Anthropic 的 "How we contain Claude across products"（2026-05-25）、"Quantifying infrastructure noise in agentic coding evals"（2026-02-05）正文没有读取。
- Manus、Cognition 2026年的 harness 文章没有覆盖。
- 一方与第三方 harness 对比所用基准的确切名称和方法没有核实，数字转引自 Lee Hanchung。

---

## 问题4：实验室与可信预测者对2027年的预期，以及对上层产品公司的含义

### Takeaway
- **实验室领导层**：仍把2026–2027视为"强 AI"窗口。Amodei 称 "powerful AI could be as little as 1–2 years away"，并以约2027年的集群规模为参照；OpenAI 的目标是2026年9月做出"研究实习生"、2028年做出合格的 AI 研究员。Hassabis 更保守，认为 AGI 约在2030年。
- **算力**：GW 级集群在2026年开始用于预训练（GPT-6 首次超过10万 GPU；Colossus 2 约110万 H100 等效）。
- **外推与共识的分歧**：直线外推 METR 趋势，2027年中50%时间跨度会达到约一个月（167小时）。但测量本身已经失效，预测者共识也更保守：AI Futures 的 Automated Coder 中位数在2028–2030年。
- **对上层产品的含义**：模型约每季度换代，近前沿能力约2个月内价格减半，开源2–5个月追平。为弥补"当前模型缺陷"写的脚手架应按约90天折旧；持久价值在评估、数据与环境、权限与安全、记忆与工作流嵌入、分发与客户信任。

### Cited Findings

#### 4.1 实验室领导层表态
- **Amodei（2026年1月，《The Adolescence of Technology》）**：
  - "powerful AI could be as little as 1–2 years away, although it could also be considerably further out"
  - "suppose a literal 'country of geniuses' were to materialize somewhere in the world in ~2027"
  - "this matches projected cluster sizes by ~2027"
  - "may be only 1–2 years away from a point where the current generation of AI autonomously builds the next"
  - 重申此前预测："AI could displace half of all entry-level white collar jobs in the next 1–5 years"

  — [Dario Amodei](https://www.darioamodei.com/essay/the-adolescence-of-technology)
  - 注：有分析指出 "~2027 country of geniuses" 是讨论风险的思想实验，并非预测（据搜索摘要）。
- **OpenAI（背景，2025-10-28）**：
  - 目标：2026年9月实现实习生级 AI 研究助理，2028年实现 "legitimate AI researcher"。
  - 承诺：30GW 基础设施，约1.4万亿美元的财务义务。
  - Pachocki：深度学习系统 "less than a decade away from superintelligence" 是可能的；当时模型的时间跨度约5小时。

  — [TechCrunch](https://techcrunch.com/2025/10/28/sam-altman-says-openai-will-have-a-legitimate-ai-researcher-by-2028/)
- **Pachocki（2026-04）**："We see pretty significant improvements in the short term, extremely significant improvements in the medium term"；同时承认 "the last two years have been surprisingly slow" — [TechCrunch](https://techcrunch.com/2026/04/23/openai-chatgpt-gpt-5-5-ai-model-superapp/)
- **GPT-6 发布时（2026-09）**：Brockman 暗示 GPT-6 可能被视为 AGI 的到来；Pachocki 称防止意外伤害越来越难，这可能拖慢 AI 进展 — [Wikipedia: GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra)
- **Hassabis**：AGI "may arrive by 2030"（日期未核实） — [Digit](https://www.digit.in/news/general/google-deepmind-ceo-says-agi-may-arrive-by-2030-calls-current-ai-agents-a-practice-run.html/amp/)；另有二手报道称他的预期已缩短到2–3年，与2030说法冲突（据搜索摘要） — [FourWeekMBA](https://fourweekmba.com/ai-hassabiss-agi-clock-falls-to-2-3-years-how-rivals-compare/)

#### 4.2 预测机构与外推
- **METR 趋势的直线外推**（追踪站自己的算术，不是 METR 官方预测）：50%跨度达到40小时工作周约在2026年秋，达到167小时（一个月）约在2027年中；80%跨度达到8小时约在2027年初 — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
- **LessWrong 外推**：若当前速度持续到2027年，2028年初的模型时间跨度约6个月；但作者的最佳猜测是2026–27年会放缓 — [LessWrong](https://www.lesswrong.com/posts/EYb2K9acKfyG2bome/metr-time-horizons-now-10x-year)
- **LEAP Wave 8（2026-04-20 至 05-11 调查）**：超级预测者认为2028年 AI 能以80%成功率完成8小时以上任务，专家认为在2030年。对2026年底最长80%跨度的中位数预期为3.4–3.5小时。 — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
- **AI Futures Project（2026-04-02）**：Automated Coder 的中位数时间，Kokotajlo 从2029年末提前到2028年中，Lifland 从2032年初提前到2030年中 — [AGI Tracker](https://agitracker.io/blog/metr-time-horizons-2026/)
- **Epoch**：GW 级数据中心约需2年建成，每 GW 前期资本开支约380亿美元；Meta Hyperion 预计2028年1月达到370万 H100 等效；当前趋势 "set to continue through 2030" — [Epoch AI Trends](https://epoch.ai/trends)

#### 4.3 算力建设
- **Stargate**：2025-01 宣布到2029年最多投资5000亿美元；2025-09-23 新增5个站点后，规划容量接近7GW、未来三年投资超过4000亿美元；AMD 最多供应6GW、Broadcom 供应10GW 定制芯片 — [Wikipedia: Stargate LLC](https://en.wikipedia.org/wiki/Stargate_LLC)。GPT-6 首次在 Stargate 德州站点用超过10万张 GPU 预训练 — [Wikipedia: GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra)
- **其他集群**：xAI 的 Colossus 2 约110万 H100 等效，是已知最大的 AI 数据中心；全球71%的 AI 算力由五大云厂商持有 — [Epoch AI Trends](https://epoch.ai/trends)
- **中国**：DeepSeek 计划在内蒙古建数据中心，使用16万片 Ascend 950DT — [Wikipedia: DeepSeek](https://en.wikipedia.org/wiki/DeepSeek)；Z.ai 在2026年2月因算力短缺限制新用户注册 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Z.ai)
- **欧洲**：Mistral 于2026年3月筹资8.3亿美元建设数据中心；7月与 Microsoft 签下 "multibillion-dollar" 协议 — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)

#### 4.4 发布受安全与政府闸门约束
- Mythos 不公开发布；6/12–6/30，美国商务部限制非美国籍人士访问 Mythos 5 与 Fable 5 — [Wikipedia: Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos)
- GPT-5.6 以"与美国政府协调的限量预览"推出 — [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra)；GPT-6 因7月 agent 网络攻击事件推迟发布 — [Wikipedia: GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra)
- Gemini 4 Argon 先提供给美国政府和网络防御伙伴 — [The Stack](https://www.thestack.technology/google-finally-eases-open-the-lid-on-gemini-4-argon/)
- Opus 5.5 评测中安全防护触发时，任务被路由给 Opus 4.8 或 Opus 5 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)

#### 4.5 与"被碾压"风险和持久价值相关的证据
- **实验室向下游整合**：
  - OpenAI 计划把 ChatGPT、Codex 和 AI 浏览器合并为 "super app" — [TechCrunch](https://techcrunch.com/2026/04/23/openai-chatgpt-gpt-5-5-ai-model-superapp/)
  - Anthropic 推出 Cowork（含 connectors 与 plugins）、Claude Design、Claude Science、Claude in Chrome — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)
  - Google 推出 Gemini Spark — [Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/)
  - SpaceXSI 收购 Cursor（2026-08） — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
- **近前沿能力迅速降价**：从 Fable 5（6/9）到"接近 Fable 5、价格减半"的 Opus 5（7/24）约6周 — [9to5Mac](https://9to5mac.com/2026/07/24/anthropic-upgrades-claude-with-new-opus-5-model-details-here/)；Opus 5.5 以 $4/$20 达到 Fable 5.1 水平 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
- **折旧与资产的说法**：
  - "Treat application-facing scaffolding as a 90-day artifact"；耐久资产是数据、环境、任务和 eval — [Lee Hanchung](https://leehanchung.github.io/blogs/2026/05/08/hidden-technical-debt-agent-harness/)
  - "The Harness is the Dataset"：竞争优势从 prompt 转向 harness 捕获的轨迹 — [Phil Schmid](https://www.philschmid.de/agent-harness-2026)
  - Managed Agents 的接口 "designed to outlast any single implementation, including Anthropic's current ones" — [Anthropic Engineering](https://www.anthropic.com/engineering/managed-agents)
  - 有 eval 的团队能快速判断新模型强弱，没有的团队要测几周 — [Anthropic Engineering](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
  - "Open models are going to be the substrate for everyone else in the world outside of the few true frontier AI labs" — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)
- **应用层也在用开源模型**：Cursor Composer 2 以 Kimi K2.5 为底座（据搜索摘要） — [Wikipedia: Kimi](https://en.wikipedia.org/wiki/Kimi_%28chatbot%29)；Harvey、Cursor、DoorDash、Airbnb、Perplexity 都基于中国开源模型构建产品 — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)

### Inferences
- **2027年的三个关键变量**：
  - GW 级集群（Stargate、Colossus 2、Hyperion）进入训练周期，带来新一代预训练加 RL 扩展。
  - 时间跨度能否继续每年约10倍增长（可能放缓的信号：Pachocki 说"surprisingly slow"、Gemini 3.5 Pro 被取消、Grok 5 延期、安全拖慢论）。
  - 安全与监管闸门：决定最强模型何时、对谁开放。

  规划上应同时准备"快"和"慢"两种情景。
- **对 harness 的2027含义**：
  - 任务时长从小时级走向天级或周级：持久会话、异步执行、断点恢复、多 agent 并行、预算治理、人类监督与审批界面会成为核心。
  - 自评偏差和作弊不会自动消失：需要独立验证器和可审计的证据链（测试、日志、录屏）。
  - agent 的自主网络行为风险上升：默认拒绝的权限、凭证隔离、逐动作分类器会成为企业采购门槛。
- **"被碾压"风险分级**：
  - 高风险：为弥补模型短板而存在的产品，例如提示链和工作流编排器、通用 RAG、通用编码 agent 外壳、简单的模型包装。实验室的一方 harness 加上协同训练会持续侵蚀它们。
  - 低风险：拥有专有数据、环境、eval，深度嵌入行业工作流和权限体系，具备合规信任与分发渠道，能灵活切换多模型（含开源）的产品。
- **架构建议的证据基础**：按 Managed Agents 的思路做"稳定接口、可替换实现"（session、harness、sandbox 分离）；把为某一代模型写的补偿逻辑标注为"可删除"并设置复审周期（约90天）；把 eval 和 trace 当作一等资产沉淀。

### Gaps
- 没有检索到 2026年9–10月 Altman、Hassabis、Amodei 对2027年的最新表态。搜索摘要提到 Altman 在10/20发文谈 "superintelligence" 的安全挑战，但没有找到可核验的原始出处，所以没有引用。
- Stargate 2026年的实际上线容量、Anthropic 算力交易（TPU/Trainium 的 GW 数）、Epoch 对2027年训练规模（FLOP）的具体预测均没有找到。
- 资本市场对"被模型碾压"的反应（如2026年软件股抛售）没有研究。

---

## 问题5：价格/性能动态（固定能力下的价格趋势、中国开源的成本优势、企业对开源的采用）

### Takeaway
2026年价格的主线不是前沿标价暴跌，而是同等能力快速降价，加上"单任务成本"取代"每 token 价格"成为核心指标：
- **Anthropic**：约3个月内把 Fable 级能力从 Fable 5 带到半价的 Opus 5，再到 $4/$20 的 Opus 5.5。
- **OpenAI**：旗舰价格维持 $5/$30，靠分层（Terra/Luna）和 token 效率竞争。
- **中国开源**：以约1/3到1/12的价格提供落后2–5个月的能力，2026年5月约占 OpenRouter token 的61%，但收入份额很低。
- **企业采用**：在扩散（Cursor、Airbnb、DoorDash、Perplexity、Harvey）。
- **反向趋势**：中国头部实验室的定价和许可正在收紧（Kimi K3 $3/$15、Qwen 的营收门槛条款、Z.ai 涨价10%）。

### Cited Findings

#### 5.1 闭源前沿：标价稳定、同等能力快速降价
- **Anthropic**：
  - Opus 4.6 为 $5/$25 — [Anthropic](https://www.anthropic.com/news/claude-opus-4-6)
  - Opus 5 为 $5/$25，以半价接近 Fable 5 — [9to5Mac](https://9to5mac.com/2026/07/24/anthropic-upgrades-claude-with-new-opus-5-model-details-here/)
  - Opus 5.5 为 $4/$20，典型负载比 Opus 5 便宜40%，性能达到 Fable 5.1 水平 — [Anthropic](https://www.anthropic.com/claude-opus-5-5)
  - Fable 5.1 比 Fable 5 便宜约25%，agentic 负载最多便宜约45% — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)
- **OpenAI**：
  - GPT-5.5 为 $5/$30（二手） — [OpenRouter](https://openrouter.ai/openai/gpt-5.5)
  - GPT-5.6 Sol 为 $5/$30；prompt caching 有显式断点、最短缓存30分钟，写缓存按1.25倍计价，读缓存打1折 — [DataCamp](https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra)
  - GPT-5.4 mini/nano 的价格是 GPT-5 同级产品的4倍，小模型端出现涨价 — [Wikipedia: GPT-5.4](https://en.wikipedia.org/wiki/GPT-5.4)
- **Google**：Gemini 4 Argon 初始价 $2/$10，之后 $4/$20 — [The Stack](https://www.thestack.technology/google-finally-eases-open-the-lid-on-gemini-4-argon/)；Gemini 3.5 Flash 完成 agentic 任务 "at less than half the cost of other frontier models" — [Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/)
- **xAI**：Grok 4.5 为 $2/$6 — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)
- **价格战信号**：Haiku 5.5 发布时被媒体称为 "AI pricing war intensifies"（10/7） — [Wikipedia: Claude](https://en.wikipedia.org/wiki/Claude_%28language_model%29)

#### 5.2 中国与开源模型的价格
- DeepSeek V4-Pro 为 $0.435/$0.87，"roughly 3× below Gemini 3.1 Pro and ~12× below GPT-5.5 at comparable benchmark intelligence"；Kimi 约便宜80%（文中未给对比基准） — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)
- DeepSeek V4 发布价（二手，与上条冲突）：V4-Pro $1.74/$3.48，V4-Flash $0.14/$0.28 — [BuildFastWithAI](https://www.buildfastwithai.com/blogs/deepseek-v4-pro-review-2026)
- Kimi K3 为 $3/$15，K2.6 为 $0.95/$4 — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- Qwen3.7-Plus 为 $0.4/$1.6；Qwen3.8-Omni-Flash 多模态输入约0.8元/百万 token — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- MiniMax M3 为 $0.60/$2.40（二手） — [Fireworks](https://fireworks.ai/blog/minimax-m3-launch)
- Doubao-Seed-2.0 Pro 的 token 价格约为可比模型的1/10（厂商称） — [TechNode](https://technode.com/2026/02/14/bytedance-releases-doubao-seed-2-0-positions-pro-model-against-gpt-5-2-and-gemini-3-pro/)
- Z.ai 于2026-04-07 将 API 价格上调10%，但仍低于 Opus 4.6 — [Wikipedia: Z.ai](https://en.wikipedia.org/wiki/Z.ai)
- Mozilla：最佳开源模型在 AA 指数上落后3分，价格为闭源领先者的60%（二手，据搜索摘要） — [Tom's Hardware](https://www.tomshardware.com/tech-industry/artificial-intelligence/chinas-open-weight-ai-models-are-now-just-4-months-behind-frontier-us-offerings-mozilla-report-claims-models-still-lag-in-some-benchmarks-but-are-drastically-cheaper-to-use)

#### 5.3 单任务成本与 token 效率
- Artificial Analysis 测得单任务成本：Kimi K3 $0.94，GPT-5.6 Sol $1.04，Opus 4.8 $1.80；K3 的输出 token 比 K2.6 少21% — [Simon Willison](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- Alibaba Accio Work 在107个电商任务的基准上估算成本 $3.69，Codex 为 $9.27，Claude Code 为 $9.51 — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- harness 层面的成本：完整长程 harness 的成本可达单 agent 的20多倍（$200 vs $9），但只有它的产出可用 — [Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)；OpenAI 的实验团队每天消耗超过10亿 token（约 $2–3k/天） — [Latent Space](https://latent.space/p/harness-eng)

#### 5.4 用量与收入的背离
- DeepSeek 在 Vercel 上的 token 份额从不足1%升至约17%（2026年5月），收入份额仍约1%；Anthropic 与 OpenAI 靠高价企业直销拿走了行业大部分收入 — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)

#### 5.5 企业对开源模型的采用
- 基于中国开源模型构建产品的公司：Harvey、Cursor、DoorDash（Kimi）、Airbnb（Qwen）、Perplexity（DeepSeek）；美国开源中 gpt-oss 与 Gemma 4 有一定采用度 — [Interconnects](https://www.interconnects.ai/p/the-current-balance-of-power-in-open)
- 在 Faros 的211个真实工程任务评测中，开源模型（GLM-5.2、Kimi K2.6）配上强 harness 进入最高质量档 — [Faros AI](https://www.faros.ai/blog/harness-engineering)
- Z.ai 在企业和政府部署上最强；阿里云 AI 约占其外部云收入的30%；豆包月活3.45亿 — [Data Gravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)
- 进入主流云平台：Microsoft Foundry 上架 Mistral Medium 3.5 与 OCR 4 — [Wikipedia: Mistral AI](https://en.wikipedia.org/wiki/Mistral_AI)；Grok 4.6 上架 GitHub Copilot 与 Amazon Bedrock — [Wikipedia: Grok](https://en.wikipedia.org/wiki/Grok_%28chatbot%29)

#### 5.6 许可与定价收紧
- Qwen3.8-2.4T 的许可规定：模型服务商12个月内营收超过5000万美元，需与阿里签商业协议；有报道称中国 AI 公司正转向闭源模型以创造收入（SCMP 标题） — [Wikipedia: Qwen](https://en.wikipedia.org/wiki/Qwen)
- MiniMax M3 使用非标准的 Community License（二手） — [TechTimes](https://www.techtimes.com/articles/317532/20260601/minimax-m3-open-weight-coding-model-frontier-claims-unverified-benchmarks.htm)；StepFun Step 5 Preview 为闭源权重 — [Wikipedia: StepFun](https://en.wikipedia.org/wiki/StepFun)

#### 5.7 背景：长期价格下降率（2025年数据）
- Epoch（2025-03-12）：固定能力下 LLM 推理价格每年下降9–900倍，视能力门槛而定；在 GPQA 上达到 GPT-4 水平的价格每年下降40倍。Epoch 也提醒最快的降幅可能不会持续。 — [Epoch AI](https://epoch.ai/data-insights/llm-inference-price-trends)
- AI 芯片性价比每年提升49% — [Epoch AI Trends](https://epoch.ai/trends)

### Inferences
- **价格曲线的形状**：
  - 顶端标价大致稳定：闭源旗舰输入约 $4–5、输出约 $20–30 每百万 token。
  - "刚过时的前沿能力"在2–3个月内降价约50%（Fable 5 → Opus 5 → Opus 5.5）。
  - 开源的同等能力在2–5个月后出现，价格约为1/3到1/12。
- **选型指标应改为"每个成功任务的总成本"**：要把 token 量、effort 档位、重试、缓存命中率、验证开销都算进去，不能只看每 token 标价。例如 Kimi K3 标价不低，但单任务成本低于 Sol 和 Opus 4.8；Grok 4.7 价格不变，实际成本却上升。harness 的模型路由、effort 分配和缓存策略，直接决定 agent 产品的毛利。
- **"智能"在用量上商品化，在收入上没有**：Vercel 和 OpenRouter 的用量大量流向便宜的开源模型，收入仍集中在闭源前沿厂商。对产品公司而言，最可行的组合是：高价值、高风险步骤（规划、验证、安全敏感操作）用前沿模型，大批量执行步骤用开源或小模型。
- **采用开源要考虑合规与政策风险**：美国对 Mythos 级模型的国籍限制，以及围绕中国模型的政策讨论（Lambert 呼吁降低对中国模型的依赖），意味着依赖中国开源模型存在合规不确定性。harness 需要能在不同模型族之间低成本切换，并有 eval 保驾。

### Gaps
- 没有找到2026年"固定能力下价格下降率"的系统性数据（Epoch 或 AA 的2026版）。
- 企业内部（非 OpenRouter）开源模型渗透率的调查数据没有覆盖，例如 Menlo、a16z 2026年的企业调查。
- 2025年 GPT-5 的官方定价基线没有核实，无法严格比较 OpenAI 旗舰标价的同比变化。
- 各来源的 DeepSeek V4 价格相差最多约4倍，可能对应不同时点、促销或峰谷时段；官方价格页没有抓取。
