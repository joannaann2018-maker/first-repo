# 2026年全球（不含中国）toB AI商业化复盘：支出与份额、实验室收入、AI-native应用、巨头变现、商业模式/GTM、问题与2027信号

> 资料时间范围：2026年1–10月（截至2026-10-24），2025年数据均标注为“背景”。标注“二手/估算/未核实”的条目请在成稿时降权使用。Sacra数字均为第三方估算，非公司披露。本次调研中途WebSearch额度耗尽，后半程仅通过直接抓取已知页面（公司官网、SEC EDGAR、已检索到的文章）补充。

## 1. 2026年企业AI支出规模、市场份额与企业/消费收入结构

### Takeaway
Gartner年内三次上调2026年全球AI支出预测至约$2.7T（+49.5%），但约56%是基础设施，真正“模型层”支出口径很小（GenAI models仅$28.3B）。企业LLM份额上，Anthropic自2025年中起领先（Menlo 2025年底：40% vs OpenAI 27% vs Google 21%），Ramp数据显示其在2026年4月首次在“付费企业渗透率”上超过OpenAI并在8月扩大到43.8% vs 39.8%，但Q3 OpenAI增速反超。OpenAI收入结构在2026年8月转为“企业为主”。

### Cited Findings

**宏观支出（Gartner）**
- 2026-01-15 Gartner预测2026年全球AI支出$2.52T（+44% YoY），并预计2027年达$3.3T — [Gartner 2026-01-15](https://www.gartner.com/en/newsroom/press-releases/2026-1-15-gartner-says-worldwide-ai-spending-will-total-2-point-5-trillion-dollars-in-2026)
- 2026-05-19上调至$2.59T（+47%） — [Gartner 2026-05-19](https://gartner.com/en/newsroom/press-releases/2026-05-19-gartner-forecasts-worldwide-ai-spending-to-grow-47-percent-in-2026)
- 2026-09-16再上调至约$2.7T（+49.5%；Techstrong报道为$2.67T）；AI基础设施$1.48T约占56%；较1月预测净增约$143B，其中约$118B来自基础设施 — [Gartner 2026-09-16](https://gartner.com/en/newsroom/press-releases/2026-09-16-gartner-forecasts-worldwide-ai-spending-to-grow-49-point-5-percent-in-2026)；[Techstrong 2026-09-21](https://techstrong.ai/features/gartner-global-ai-spending-to-hit-2-7-trillion-in-2026/)
- Gartner 9月版细分（2026）：GenAI models $28.3B（+117%，2025年$13B）；AI-optimized IaaS $42.3B（+96%），其中推理$23.3B、训练$19B，预计2027年推理占AI-optimized IaaS的59%；AI agents & assistants $29.2B；AI services $576.5B；AI software $461.6B；AI应用开发平台增速由28%上调至39%；技术供应商约占全球AI支出35%；AI services机会2030年可达$1.2T — [Techstrong 2026-09-21](https://techstrong.ai/features/gartner-global-ai-spending-to-hit-2-7-trillion-in-2026/)

**企业 vs 消费**
- （背景）Menlo Ventures：2025年企业GenAI支出$37B，同比3.2倍 — [Menlo 2025 State of GenAI in the Enterprise](https://menlovc.com/perspective/2025-the-state-of-generative-ai-in-the-enterprise/)
- Menlo（2026-09-16）：2026年全球消费级AI支出约$40B（2025年$12B）；美国55%的AI用户至少为一款AI产品付费（约9,000万人）；约20%付费者由雇主/学校付费，人均$95/月 vs 自费$55/月；付费方式：50%月度订阅、26%年付、17%纯用量计费、15%订阅+用量；14%的高付费者（$100+/月）贡献60%消费支出；样本为2026年7月5,067名美国成年人 — [Menlo 2026 State of Consumer AI](https://menlovc.com/perspective/2026-the-state-of-consumer-ai/)
- 同报告：通用助手渗透（AI用户为分母）ChatGPT 60%、Gemini 58%、Claude 20%（Claude用户中82%付费、48%使用agent）；agent产品渗透：Codex 35%、Claude Code/Cowork 32%、Perplexity 24% — [Menlo 2026-09-16](https://menlovc.com/perspective/2026-the-state-of-consumer-ai/)
- OpenAI：2026-03-31称企业客户占收入>40%（一年前约30%），预计2026年底与消费持平；2026年1月CFO Friar称公司“entered the year at 60-40”；2026-08-14 Friar向股东表示“The majority of our revenue is now enterprise”（据CNBC，较预期提前约两个季度） — [Yahoo Finance 2026-03/04](https://finance.yahoo.com/markets/stocks/articles/openai-closes-122bn-funding-round-093126735.html)；[Unite.AI（AI生成稿，引CNBC）](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)

**企业侧模型厂商份额**
- （背景）Menlo 2025年底：企业LLM API使用份额Anthropic 40%、OpenAI 27%、Google 21%（三家合计88%）；2025年中为32%/25%/20%；OpenAI在2023年为50%；编码场景Anthropic 54% vs OpenAI 21%；样本495名美国企业决策者。注意：Menlo是Anthropic投资方，口径不含消费收入与软件内嵌AI — [ValueAdd VC（二手）](https://valueaddvc.com/blog/anthropic-market-share-2026-40-percent-enterprise-llm-spend-openai)；[BigDATAwire（2025年中企业LLM API支出$8.4B）](https://www.hpcwire.com/bigdatawire/this-just-in/menlo-ventures-report-enterprise-llm-spend-reaches-8-4b-as-anthropic-overtakes-openai/)
- Ramp AI Index（基于7万+美国企业卡/账单交易，偏SMB与科技型公司）：2026年2月整体付费AI采用率47.6%，Anthropic 24.4%，Google 4.7%，xAI <2%；2026年4月（5月发布）Anthropic 34.4%首次超过OpenAI 32.3%，整体50.6% — [New Space Economy 2026-06-26（二手汇总）](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)
- Ramp 7月数据（8-12发布）：Anthropic 43.5% vs OpenAI 39.7%（经搜索摘要） — [Unite.AI](https://www.unite.ai/ja/openai-closes-on-anthropic-in-ramps-business-spending-data/)；8月数据：整体56.1%，Anthropic 43.8% vs OpenAI 39.8%；中位企业AI支出约$12/月，前1%企业约$7,200–7,450/月；部分高支出企业人均AI支出环比下降；Census Bureau口径的企业AI采用率仅22.1%；Ramp同时推出按模型/用户拆分的Token Spend Management — [Crypto Briefing 2026-09-22](https://cryptobriefing.com/ramp-ai-index-token-spend-volumes-update/)
- Ramp首席经济学家Ara Kharazian（2026-08-20）：Q3至今OpenAI在Ramp客户中的增速超过Anthropic（归因于OpenAI新模型），并称Anthropic的Fable 5因“价格+监管施加的数据保留要求”在采用和实际应用上令人失望（经搜索摘要，未全文核对） — [Crypto Briefing](https://cryptobriefing.com/openai-narrows-gap-anthropic-ramp-business/)
- RBC Capital Markets 2026 CIO调研（117名IT负责人）：90%计划2026年增加AI支出，90%正在设立专门AI预算 — [CRN India](https://www.crn.in/news/cios-signal-rising-tech-spend-and-deeper-shift-to-enterprise-ai-in-2026/)；57%称ChatGPT为最常用模型服务；多数称AI支出为新增预算而非挤占软件预算，无人预计软件总支出下降 — [New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)
- a16z Global 2000调研（100名年营收$5亿+企业高管；二手来源未注明年份）：OpenAI模型在78%受访企业投产，Anthropic 44%；平均预期LLM支出由约$7M增至约$11.6M（+65%） — [New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)；a16z最新可确认的公开版本为2025年版 — [a16z 2025](https://a16z.com/ai-enterprise-2025/)
- Bain Automation & AI Pathfinder（951家公司）：测量过节省的公司中近40%节省<10%（常见目标11–20%）；90%再次增加AI预算；仅7%在生产中运行完全自主agent — [New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)
- 云/基础设施侧需求印证：Microsoft商业RPO $678B（+84%，截至2026-06-30） — [Microsoft FY26 Q4](https://www.microsoft.com/en-us/investor/earnings/fy-2026-q4/press-release-webcast)；Oracle RPO $664B（同比增加$209B，截至2026-08-31），Q1 FY27新签>$30B AI云合同 — [Oracle 8-K 2026-09-10](https://www.sec.gov/Archives/edgar/data/1341439/000119312526387905/0001193125-26-387905.txt)

### Inferences
- “AI支出”头条数字被基础设施主导；可被软件/模型公司直接确认为收入的部分远小于$2.7T。Gartner的“GenAI models $28.3B”明显低于Anthropic一家2026年前三季度约$33B的实际收入（见第2节），说明其分类把大量实验室收入归入AI software/services等其他类别，引用时需说明口径。
- 企业侧份额：2025年Menlo的“Anthropic领先”在2026年被Ramp交易数据从另一维度印证（渗透率而非金额），驱动力是编码agent（Claude Code/Cowork）；但Q3起OpenAI凭新模型与降价回追，竞争格局并未固化。
- Ramp显示“广覆盖、浅支出”：一半以上中小企业付费，但中位数仅$12/月，支出高度集中在头部1%——toB AI收入的真实大头来自大企业API/编码与大额合同，而非长尾SaaS订阅。
- 企业收入在实验室收入中的占比上升（OpenAI：约30%→>40%→>50%），2026年toB已是前沿实验室的主战场。

### Gaps
- 未找到Menlo 2026年企业LLM市场更新（其官网列表截至2026-10仅有9月消费报告等）；未找到a16z 2026年CIO调研（a16z.com/ai-enterprise-2026/返回404）；ICONIQ、Bessemer、IDC的2026年数据未获取（搜索额度耗尽）。
- 2026年按“金额”计的企业LLM API份额（Anthropic/OpenAI/Google/开源权重）无可靠来源；Google与开源模型的2026企业份额缺失。
- Anthropic 2026年企业/消费收入拆分未见于S-1泄露报道。

## 2. 前沿模型公司（OpenAI / Anthropic）2026年收入、企业占比、客户与大单

### Takeaway
Anthropic从2025年底约$9B run-rate跃升至2026年7月底$65B；按泄露S-1与投资者日信息，2026年Q1/Q2/Q3实际收入$4.7B/$11.6B/$16.8B（前三季约$33B），Q3调整后盈利，但上半年账面净亏损$80.7B（含$72B非现金项）。OpenAI 2025年收入$13.1B，2026年7月run-rate $40B、9月底约$50B，目标年底≥$70B，8月起企业收入过半、企业客户超200万。两家都在冲刺IPO（Anthropic最早11月后，OpenAI推迟到至少2027）。

### Cited Findings

**Anthropic：收入与盈利**
- Run-rate轨迹：2025年底约$9B → 2026年2月$14B → 3月$19B → 4月$30B → 5月初$44B → 5月中$47B；Claude Code上线约9个月达约$2.5B run-rate — [SaaStr](https://www.saastr.com/by-year-end-anthropic-will-out-earn-every-public-software-company-except-microsoft/)；Series H公告确认“run-rate revenue crossed $47 billion earlier this month”（2026-05-28） — [Anthropic Series H](https://www.anthropic.com/news/series-h)
- 2026年7月底run-rate $65B（投资者更新，较一年前约$5B增长约7倍） — [CNBC 2026-08-17](https://www.cnbc.com/2026/08/17/anthropic-says-annualized-revenue-climbed-to-65-billion-in-july.html)；NYT（2026年9月，经Bloomberg转述）称年内annualized revenue将超$100B（二手预测） — [Yahoo/Bloomberg](https://uk.finance.yahoo.com/news/anthropic-annualized-revenue-top-100-220623178.html)；分析师估计年底run-rate可达$110B — [The Star（Reuters）2026-10-15](https://www.thestar.com.my/tech/tech-news/2026/10/15/anthropic039s-q3-revenue-surges-45-to-nearly-17-billion)
- 泄露S-1（Reuters 2026-09-28）：2025年收入约$4.6B（+1,088%）；2025年经营亏损$8.06B（2024年$2.98B）；净亏损$42B（含融资相关负债减记）；算力与基础设施支出$7.33B；2025年底现金及短期投资$20.28B；两家未具名客户贡献2025年近1/4收入 — [Fortune 2026-09-29](https://fortune.com/2026/09/29/anthropic-leaked-ipo-prospectus-losses-growth-ai-end-humanity/)；[CNBC/Reuters 2026-09-28](https://www.cnbc.com/2026/09/28/anthropics-ipo-prospectus-shows-sweeping-ai-vision-surging-costs-reuters.html)
- 初步S-1（WSJ 2026-10-20）：2026上半年收入$16.3B（2025上半年$1.1B）；上半年净亏损$80.7B，其中$72B为可转债/融资工具非现金调整（剔除后约$8.7B）；上半年算力/基础设施支出近$9B；两家客户约占上半年收入20%；未来十年不可撤销云算力承诺约$450B（Google Cloud $111B、AWS $110B、Microsoft $31B），含洽谈中项目最高可达$750B — [Investing.com/WSJ](https://www.investing.com/news/stock-market-news/anthropic-revenue-hits-163-billion-as-preliminary-s1-outlines-ipo-risks--wsj-4960928)
- 季度收入：Q1 $4.7B、Q2 $11.6B（FT口径$11.5B）、Q3 $16.8B（环比+45%，来源为2026-10-14投资者日两名参会者）；公司称Q3调整后盈利 — [The Star（Reuters）](https://www.thestar.com.my/tech/tech-news/2026/10/15/anthropic039s-q3-revenue-surges-45-to-nearly-17-billion)；Bloomberg报道Q3毛利率85%、调整后经营利润率>11%（经搜索摘要，未全文核对；FT来源未说明是总额还是净额收入） — [BGOV/Bloomberg](https://news.bgov.com/artificial-intelligence/anthropic-revenue-hits-16-8-billion-in-quarter-before-ipo-1)
- 收入口径：SaaStr指出Anthropic对部分云合作伙伴销售按总额（gross）确认，抬高营收 — [SaaStr](https://www.saastr.com/by-year-end-anthropic-will-out-earn-every-public-software-company-except-microsoft/)

**Anthropic：融资、算力、IPO**
- 2026-02-12融资$30B，估值$380B — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- 2026-05-28 Series H $65B，投后$965B（Altimeter、Dragoneer、Greenoaks、Sequoia领投；含超大云厂商此前承诺的$15B，其中Amazon $5B）；算力：Amazon最多5GW新容量、Google/Broadcom 5GW TPU、SpaceX Colossus 1/2 GPU；AWS仍为主要云与训练伙伴 — [Anthropic Series H](https://www.anthropic.com/news/series-h)
- IPO：目标估值>$2T，上市可能推迟到2026年11月美国中期选举之后，预计早于OpenAI — [Fortune](https://fortune.com/2026/09/29/anthropic-ipo-s-1-prospectus-income-statement/)；[The Star（Reuters）](https://www.thestar.com.my/tech/tech-news/2026/10/15/anthropic039s-q3-revenue-surges-45-to-nearly-17-billion)

**Anthropic：企业/政府/伙伴交易（2026）**
- 2026-05-04与Blackstone、Hellman & Friedman、Goldman Sachs成立企业AI服务公司（Apollo、General Atlantic、Leonard Green、GIC、Sequoia参与），面向中型企业（社区银行、中型制造商、区域医疗系统），Anthropic Applied AI工程师嵌入；CFO Krishna Rao：“Enterprise demand for Claude is significantly outpacing any single delivery model” — [Anthropic](https://anthropic.com/news/enterprise-ai-services-company)；[Blackstone](https://blackstone.com/news/press/anthropic-partners-with-blackstone-hellman-friedman-and-goldman-sachs-to-launch-enterprise-ai-services-firm)；据WSJ（经Mobile World Live）该实体价值约$1.5B，Anthropic/Blackstone/H&F各约$300M、Goldman约$150M — [Mobile World Live](https://www.mobileworldlive.com/?p=502929)；后以“Ode with Anthropic”运营，基于2026年5月收购的Fractional AI，CEO Chris Taylor（日期未确认） — [Webull/Barchart](https://www.webull.com/news/15231673947530240)
- 2026-03-12 Claude Partner Network：2026年首期投入$100M；Accenture培训3万名专业人员（设Anthropic Business Group），Cognizant向约35万员工开放Claude，Infosys设Anthropic CoE；伙伴团队扩大5倍；Claude是唯一同时在AWS、Google Cloud、Microsoft上提供的前沿模型 — [Anthropic CPN](https://www.anthropic.com/news/claude-partner-network)
- 2026-09-18与Accenture（旗下Faculty）合作嵌入式模型评估，双方预计5年内各投入至少$1B — [Anthropic](https://www.anthropic.com/news/accenture-embedded-evaluation)
- 2026-10-02 Claude Frontier Academy：投入$100M，目标2027年底前培训1万名Frontier Deployed Engineers；首批机构Accenture、Bain、Capgemini、Commonwealth Bank of Australia、Deloitte、McKinsey、Morgan Stanley、Novo Nordisk；伙伴网络中46,000家公司的人员已获17.5万+张Claude认证 — [Anthropic](https://www.anthropic.com/news/claude-frontier-academy)
- 2026-10-01 Barclays规模化部署Claude；2026-10-14开设新加坡办公室并与新加坡政府签MOU；2026-10-08向美国Genesis Mission承诺3年$150M — [Anthropic Newsroom](https://www.anthropic.com/news)
- 模型/价格：Claude Opus 5.5（2026-09-22）典型负载运行成本比Opus 5低40%；Sonnet 5.5（09-28）多数工作成本最多降30%；Haiku 5.5（10-07）；Mythos与Fable 5.1（09-15） — [Anthropic Newsroom](https://www.anthropic.com/news)

**OpenAI：收入与客户**
- 2025年收入$13.1B；2026年3月称月收入约$2B；2025年底annualized >$20B — [Yahoo Finance](https://finance.yahoo.com/markets/stocks/articles/openai-closes-122bn-funding-round-093126735.html)；[Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- 2026-02-27宣布$110B融资（估值$840B） — [Long Angle](https://www.longangle.com/alts-education/software-ai)；2026-03-31完成$122B，投后$852B（Amazon $50B，其中$35B以IPO或技术里程碑为条件；Nvidia、SoftBank各$30B；约$3B来自个人投资者）；ChatGPT 9亿+ WAU、5,000万+订阅 — [Yahoo Finance](https://finance.yahoo.com/markets/stocks/articles/openai-closes-122bn-funding-round-093126735.html)
- 2026-08-14股东会（CNBC）：run-rate $40B，7月环比+20%；同期企业客户数+32%；广告接近$1B年化；Friar称采购正从“无约束的员工AI支出”转向“cost per unit of intelligence”，新模型在agentic coding任务上效率提升54%并伴随降价；2026-08-13称企业客户>200万（一年前2倍）、WAU>10亿 — [Unite.AI（AI生成稿，引CNBC与OpenAI公告）](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- OpenAI企业使用研究（2026-08-12）：截至2026年6月，Codex占企业客户Codex+ChatGPT输出token的64%；2月以来法务、销售、招聘、市场的周活企业Codex用户分别增长108倍、41倍、41倍、26倍，工程5倍；前10%企业人均输出token是典型企业的8.3倍，差距自1月扩大3倍 — [Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- Bloomberg（2026年8月）：annualized >$40B，约为2025年底两倍；Axios（2026-09-29，匿名来源）：接近$70B年化节奏，自Q3初+70%，B2B收入同期增长>100%，Q3新增消费收入超过去年全年 — [PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/openai-annualized-revenue-nears-70-billion-amid-enterprise-growth/)
- Bloomberg（2026-10-08）：9月底annualized约$50B；预计年底≥$70B，主要由企业驱动；正以$1.4T pre-money洽谈$30B+融资（含MGX等阿联酋基金）；FT称早前$70B说法源于投资者按Anthropic对云厂商销售的计法测算；消息当日Nasdaq 100跌1.4%、芯片指数跌3.4%；IPO推迟至至少2027年 — [Yahoo/Bloomberg](https://finance.yahoo.com/technology/ai/articles/openai-expects-70-billion-annualized-014338719.html)
- 组织变动：Brad Lightcap于2026-08-11结束8年任期；CRO Denise Dresser任职8个月后于08-13卸任，前Wiz高管Dali Rajic接任 — [Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- WSJ（2026-09-28）：OpenAI因对齐测试表现不及前代而暂停GPT-6.1 Astra发布 — [PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/openai-annualized-revenue-nears-70-billion-amid-enterprise-growth/)
- OpenAI Deployment Company：聚合站称OpenAI设立控股子公司，初始投资>$4B，向企业派驻FDE构建生产级AI系统（未找到官方公告，未核实） — [BestBlogs](https://www.bestblogs.dev/en/article/f648cbd2)；The Next Web在2026年5月将其与Anthropic服务公司并列为“瞄准同类企业客户”的新实体 — [TNW 2026-05-05](https://thenextweb.com/news/servicenow-30-billion-2030-now-assist-ai-revenue)
- OpenAI在SF、NYC、Seattle、London、Munich、Dublin、Sydney招聘FDE，职责覆盖discovery→技术方案→构建→生产上线，以生产采用和可量化工作流影响考核 — [OpenAI Careers](https://openai.com/careers/forward-deployed-engineer-(fde)-sf-san-francisco/)

### Inferences
- 按季度实际收入，Anthropic Q3 2026单季$16.8B已超过Salesforce单季营收（Q2 FY27 $11.3B），前三季约$33B；SaaStr在5月给出的“2026日历年$20–26B”估计已被实际数据超越。
- 两家run-rate不可直接比较：Anthropic对云渠道按总额确认，且run-rate多用“最近一个月×12”；OpenAI的$50B与“$70B”差异即源于口径。成稿时建议同时给出“实际季度收入”和“run-rate”两套数字。
- 粗算（推论）：OpenAI 8月run-rate $40B中企业过半，意味着企业侧年化>$20B；Anthropic $65B run-rate下，即使只看企业/API，规模也已超过任何一家纯SaaS公司。
- 两家的增量主要来自编码agent（Claude Code、Codex）及其向法务/销售/招聘等非工程职能扩散；“编码agent→通用知识工作agent”是2026年toB收入最强的单一引擎。
- Anthropic客户集中度高（两家客户占约20–25%），在IPO文件中被列为风险；具体客户身份未披露（勿臆测）。

### Gaps
- Anthropic与OpenAI 2026年的企业客户总数、$100K+/$1M+大客户数量及增速未在可得来源中披露（Anthropic S-1泄露报道未涉及）。
- 2026年美国政府（GSA OneGov等）新合同、国防部相关合作、OpenAI for Countries/Stargate等主权项目的2026进展未能核实（搜索额度耗尽）。
- ChatGPT Business/Enterprise、Claude Team/Enterprise的2026年席位价格档位未获取；OpenAI Frontier企业agent平台的官方页面返回403。
- OpenAI Deployment Company仅有单一聚合站来源，规模、成立时间与股东需核实。

## 3. AI-native应用公司：ARR里程碑、增速、毛利与估值

### Takeaway
2026年AI-native应用继续“超高速爬坡”：编码/应用生成（Cursor B2B年化约$2.6B→SpaceX以$60B收购；Lovable约$600M；Replit约$525M）、客服agent（Sierra $200M、Decagon约$100M、Fin总ARR约$400M→Salesforce以约$3.6B收购）、法律（Harvey $300–400M+，估值$15.5B）、语音（ElevenLabs约$600M）、搜索（Perplexity约$750M，估）与企业搜索（Glean约$300M）。估值普遍为20–80倍ARR，并首次出现“头部AI应用被平台/巨头整体收购”的大额退出。

### Cited Findings

**编码与应用生成**
- Cursor（Anysphere）：SpaceX于2026-06-16签约以$60B全股票收购（4月曾获“$60B收购或$10B合作”选择权；SpaceX在Nasdaq上市数日后签约），预计2026年Q3完成，含$10B终止费；据公司提供给Reuters的数据，Cursor B2B年化收入约$2.6B — [Quartz](https://qz.com/spacex-buying-cursor-anysphere-60-billion-deal-061626)；[Barchart](https://www.barchart.com/story/news/2504462/spacex-to-acquire-ai-coding-startup-cursor-in-60-billion-deal-following-record-ipo)；[Techzine](https://www.techzine.eu/news/devops/142197/spacex-acquires-cursor-for-60-billion/)
- Cursor其他ARR说法（聚合站，未核实）：2026年2月$2B，5–6月约$4B；最后一轮独立私募估值为2025年11月$29.3B — [Tech Insider](https://tech-insider.org/cursor-60-billion-valuation-anysphere-ai-coding-2026/)；[ValueAdd VC](https://valueaddvc.com/company/cursor)
- 背景：xAI于2026-01-06以约$230B估值融资$20B，SpaceX于2月初收购xAI — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- Lovable：2024年11月上线后约8个月破$100M ARR；2025年12月$200M；2026年2–3月约$400M；6月约$500M；2026年8月“跟踪至8月底$600M run-rate”；过去12个月ARR翻4倍；2026-08-12完成$400M Series C，估值$13.3B（Menlo领投、EQT联合领投）；约2/3的Fortune 500有员工使用；6,000万+项目 — [VKTR](https://www.vktr.com/ai-platforms/lovable-raises-400-million-at-133-billion-valuation/)；[Menlo](https://menlovc.com/perspective/built-to-run-doubling-down-for-lovables-400m-series-c/)；联合创始人称9月已超$600M（与上述日期有出入） — [Ecosistema Startup](https://ecosistemastartup.com/lovable-cruza-us600m-arr-y-consolida-el-vibe-coding/)
- Replit（Sacra估算，2026-05-28）：2026年4月年化约$525M（2025年底$300M）；2026年3月$400M Series D、估值$9B（约19倍远期收入）；毛利率约85%；流失“低”（无数字）；2026年5月上线自助式企业高ACV套餐；已上架Azure与Google Cloud Marketplace — [Sacra](https://sacra.com/research/replit-passes-500m-year/)

**客服/CX agent**
- Sierra：2025年11月ARR $100M（成立约21个月） — [TechCrunch 2025-11-21](https://techcrunch.com/2025/11/21/bret-taylors-sierra-reaches-100m-arr-in-under-two-years/)；2026-05-04 Series E $950M，投后$15.8B（Tiger Global、GV领投） — [idlen.io](https://www.idlen.io/news/sierra-950-million-series-e-15-8-billion-valuation-bret-taylor-tiger-global-may-2026)；2026年5月ARR约$200M（两个季度翻倍，约79倍ARR估值），服务40%的Fortune 50（公司说法），按结果收费（ARR来源未明确标注） — [Crypto Briefing 2026-08-18](https://cryptobriefing.com/sierra-200m-annualized-revenue-may/)
- Decagon（Sacra估算）：2026年7月年化约$100M（2025年底$44M）；2026年1月$250M Series D、估值$4.5B（Coatue、Index），3月按同估值员工tender；定价“按对话”（更主流）或“按解决”（单价更高、仅在无人工介入解决时收费） — [Sacra](https://sacra.com/c/decagon/)
- Fin（原Intercom，2026年5月更名）：2026-06-15 Salesforce签约以约$3.6B收购，30,000+客户，AI agent平均端到端解决76%支持量 — [Salesforce IR](https://investor.salesforce.com/news/news-details/2026/Salesforce-Signs-Definitive-Agreement-to-Acquire-Fin/default.aspx)；据二手分析，收购时总ARR约$400M（约$300M传统SaaS + 约$100M Fin agent，agent增速约350%），$0.99/resolution价格未变 — [Drag（二手）](https://www.dragapp.com/blog/salesforce-buys-fin/)

**垂直与知识工作**
- Harvey：2026年完成$550M融资、估值$15.5B（官网博客确认；日期各源为2026-09-09或10-01） — [Harvey Blog](https://www.harvey.ai/blog)；此前2026年内由GIC与Sequoia领投$200M、估值$11B — [Techleap](https://finder.techleap.nl/news/note/harvey-raises-200m-at-11b-valuation-to-expand-legal-ai-agents)；ARR：Sacra估2025年底$195M→2026年5月$300M — [Sacra](https://sacra.com/c/harvey/)；另有报道称已超$400M ARR、3,000+付费机构（未核实） — [Entrepreneur Loop](https://entrepreneurloop.com/harvey-ai-valuation-15-5b/)
- Glean（Sacra估算）：2026年5月ARR约$300M（2025年底$208M，+89% YoY），2025年12月$200M（9个月翻倍）；按席位订阅，首单ACV典型$100–500K，Fortune 500大单>$5M/年；最近公开估值$7.2B（2025年6月） — [Sacra](https://sacra.com/c/glean/)
- Abridge：Sacra估2025年5月ARR约$100M、2025年Q1合同ARR $117M；2025年6月估值$5.3B；2026年4月追加$316M Series E；约$2,500/临床医生/年；Kaiser 24,600名医生、Mayo 2,000+、UPMC计划2026年覆盖12,000+临床人员 — [Sacra](https://sacra.com/c/abridge/)
- ElevenLabs（Sacra估算）：2025年底约$330M→2026年Q1末约$450M→4月破$500M→6月约$600M；自助与企业收入接近50/50；2026年2月$500M Series D（Sequoia）估值$11B；Bloomberg（2026-07-02）报道以$22B估值洽谈tender（未成交）；41% Fortune 500使用；2026年6月与英国DSIT签MoU — [Sacra](https://sacra.com/c/elevenlabs/)
- Perplexity（Sacra估算）：2026年8月年化约$750M（2025年底约$232M）；Enterprise Pro $40/席位/月；最近公开估值$20B（2025年9月） — [Sacra](https://sacra.com/c/perplexity/)
- Gamma（Sacra）：2025年10月ARR约$102M，2023年起盈利，52名员工，60万+付费订阅，2025年11月估值$2.1B（a16z领投）——2026年数据缺失 — [Sacra](https://sacra.com/c/gamma/)
- 2026年Q1各家估值快照：Harvey $11B、Sierra $10B、Decagon $4.5B、Glean $7.2B、Cursor $29.3B、Replit $9B — [Long Angle](https://www.longangle.com/alts-education/software-ai)

**基础设施/中间层**
- 2026-08-19 Stripe宣布收购OpenRouter：年化token量4.5+千万亿（quadrillion），500+模型、80+提供方、1,000万用户，三年来月均增长约33%；2026年7–8月间Ramp、Cursor等10余家公司推出自有模型路由器 — [Menlo](https://menlovc.com/perspective/stripe-to-acquire-openrouter-why-everyone-is-obsessed-with-model-routing/)
- Menlo 2026年投资Fireworks（推理运行时，07-16）与Factory（agentic软件开发，10-05） — [Menlo Perspectives](https://menlovc.com/perspective/)

### Inferences
- “$100M ARR俱乐部”入会速度继续刷新：Lovable约8个月、Sierra约21个月、Gamma以52人盈利达$100M；更显著的是“$100M→$500M”阶段的速度（Lovable约1年、ElevenLabs约1.5年、Replit约1年），说明头部AI应用已从“爆款”进入“规模化收入”阶段。
- 估值倍数（推论，按文中数字计算）：Sierra约79x、Harvey约39–52x（取$400M/$300M）、Lovable约22x、Cursor收购价约23x B2B年化（若按$4B则约15x）、Replit约19x远期——客服agent因“结果计价+替代人工预算”享有最高溢价。
- 2026年出现两条退出路径：被AI平台/超级公司收购（SpaceX/xAI–Cursor，用于获取开发者数据与分发）与被SaaS巨头收购（Salesforce–Fin），说明巨头选择“买”agent能力与结果计价客户群。
- 编码类应用面临上游模型方的直接竞争（Claude Code、Codex在Menlo消费调研中合计渗透率已超过多数独立产品），这是Cursor选择被并入拥有自研模型（Grok）的集团的背景之一（推论）。

### Gaps
- 多数ARR为Sacra等第三方估算或公司口头说法，缺乏审计口径；Sierra、Harvey、Cursor的最新ARR各源不一致。
- AI-native应用的毛利率（除Replit约85%的估算、Gamma盈利外）缺乏可靠2026数据；Cursor、Lovable、Harvey、Sierra毛利未知。
- Abridge、Gamma的2026年ARR，以及OpenEvidence等其他快速增长公司未能覆盖；SpaceX–Cursor交易是否已完成交割未确认。

## 4. 软件巨头（Incumbents）的AI变现、SaaS重定价与“SaaS已死”之争

### Takeaway
巨头AI收入已可量化但体量仍远小于实验室：Microsoft M365 Copilot付费席位>3,000万、Azure FY26首破$100B；Salesforce Agentforce ARR >$1.5B（口径扩大后）；ServiceNow AI ACV破$1B并把目标上调至$1.5B；Workday AI贡献>25%新ACV；Adobe AI-first ARR增速>150%但不披露绝对值；Oracle靠AI云把RPO推到$664B。年初“SaaSpocalypse”令SaaS指数Q1下跌约26%，此后部分反弹；财报中席位压缩尚未出现，但多家巨头启动裁员重组与CEO更替。

### Cited Findings

**Microsoft（FY26 Q4，2026-07-29发布）**
- 收入$90.0B（+18%）；Microsoft Cloud $59.3B（+27%）；Azure及其他云服务+43%，FY26 Azure收入首超$100B；Intelligent Cloud $39.3B（+32%）；M365商业云+16%（调整后，报告+14%）；Dynamics 365 +13%；商业RPO $678B（+84%）；Q4购置物业设备现金支出$35.8B，FY26 $115.9B；M365 Copilot付费席位>3,000万；Nadella：“advancing the frontier on the cost-to-outcome curve, ensuring every customer can turn tokens into business results” — [Microsoft FY26 Q4](https://www.microsoft.com/en-us/investor/earnings/fy-2026-q4/press-release-webcast)
- 电话会称Copilot净增付费席位环比翻倍以上（经搜索摘要） — [Microsoft Earnings Call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q4)；二手报道称FY26 Q3约2,000万席位（未核实） — [TradingKey](https://www.tradingkey.com/analysis/stocks/us-stocks/262063724-microsoft-msft-surged-8-after-q4-fy2026-earnings-azure-43-copilot-tradingkey)；GitHub Copilot 5,000万用户（据CNBC，经搜索摘要） — [CNBC 2026-07-29](https://www.cnbc.com/2026/07/29/microsoft-msft-q4-earnings-report-2026.html)

**Salesforce（Q2 FY27，2026-08-26发布）**
- Agentforce ARR >$1.5B（+240% YoY；自本季起口径纳入Slackbot与Headless 360，增速非同口径）；Agentforce + Data 360 ARR约$3.9B（+210%）；Q1 FY27 Agentforce ARR为$1.2B（+205%） — [Salesforce Q2 FY27](https://www.salesforce.com/news/press-releases/2026/08/26/fy27-q2-earnings/)；[Salesforce IR（Fin收购公告）](https://investor.salesforce.com/news/news-details/2026/Salesforce-Signs-Definitive-Agreement-to-Acquire-Fin/default.aspx)
- 收入$11.3B（+11%，含Informatica $456M）；cRPO $33.5B（+14%）；FY27收入指引$46.1–46.4B（上调$200M，含Contentful与Fin并购约$200M贡献）；Q2交付3.2B AWUs（agentic work units，环比+97%），累计7.0B；Agentforce One Edition与Agentforce for Apps订单环比翻倍 — [Salesforce Q2 FY27](https://www.salesforce.com/news/press-releases/2026/08/26/fy27-q2-earnings/)
- 电话会：新增2,000家付费生产客户（环比+70%）；订单三位数增长，约50%来自客户“续充credits”；仅5%知识工作者升级到溢价版（溢价60–80%）；Benioff：“We're still trapped in some ways in old per user pricing models”“Our seats were supposed to decline”但席位同比增长、流失率接近历史最低；“This is not the SaaSpocalypse… Apps are not dying”；称持有的Anthropic股份“has been like half our value”；$25B加速回购均价$176/股、至少回购14%股本；Slackbot上线5个月达100万活跃用户；Salesforce自用help agent累计500万+对话、64%自主解决；某大型数字平台客户Q2消耗4,500万AWUs（14倍增长），正就“结果计价或ILA”谈判一笔$40M合同 — [Motley Fool 电话会实录](https://www.fool.com/earnings/call-transcripts/2026/08/31/salesforce-crm-q2-2027-earnings-call-transcript/)

**ServiceNow**
- Q2 2026（2026年7月）：AI ACV破$1B（2025年底约$600M，Moveworks贡献>$100M）；订阅收入$3,877M（+24.5%）；cRPO $13.20B（+21%）；658家客户ACV>$5M（+23%）；123笔>$1M新增ACV交易（+近40%）；agentic部署9个月增长9倍；推出Otto统一AI入口、Action Fabric（Anthropic为首个设计伙伴）、Build Agent（支持Cursor/Windsurf/Claude Code/GitHub Copilot）；FY26订阅收入指引$15.76–15.78B；毛利指引反映更多使用超大云合作与AI采用加快 — [ServiceNow Q2 2026 8-K](https://www.sec.gov/Archives/edgar/data/1373715/000137371526000072/erq2fy26.htm)
- Q1 2026：Now Assist ACV约$750M；ACV>$1M的Now Assist客户同比+130%以上 — [ServiceNow Q1 2026 8-K](https://www.sec.gov/Archives/edgar/data/0001373715/000137371526000054/erq1fy26.htm)；[TNW](https://thenextweb.com/news/servicenow-30-billion-2030-now-assist-ai-revenue)
- 2026-05-04投资者日：2030年订阅收入约$30B（约19% CAGR，上行情景$32B）；近期AI ACV目标由$1B上调至$1.5B；2030年约30% ACV来自AI；AI产品毛利率与公司平均大致相当 — [TNW 2026-05-05](https://thenextweb.com/news/servicenow-30-billion-2030-now-assist-ai-revenue)
- J.P. Morgan（2026-10-20，二手转载）：大规模AI消费变现推迟到2027；当前AI ACV增长主要来自升级AI版本的提价（客户支出+10–25%），增量消费占比很小；多数客户尚未用完credit池；预计2027年约50%新增业务转向非席位模式、席位压缩“第一波”出现在2027；股价自上次财报后约+58%，目标价$150 — [KuCoin转载](https://kucoin.com/news/flash/jpmorgan-maintains-overweight-on-servicenow-ai-monetization-delayed-to-2027)；Q3财报定于2026-10-28 — [Yahoo Finance](https://finance.yahoo.com/markets/stocks/articles/servicenows-quarterly-earnings-preview-know-075920791.html)

**SAP（Q3 2026，2026年10月发布）**
- 当期云积压€24.1B（+28%）；云收入+26%；Cloud ERP Suite +29%；总收入+13%，单季首超€10B；non-IFRS经营利润+18%，首超€3B；Klein：“Our Autonomous Enterprise strategy is not just resonating, it is being adopted”，客户认为Joule Work强化了转型业务论证；新闻稿未披露Business AI具体变现指标 — [SAP Q3 2026](https://news.sap.com/2026/10/sap-announces-q3-2026-results/)

**Workday**
- 2026-02-09：联合创始人Aneel Bhusri回任CEO，Carl Eschenbach卸任；Bhusri：“AI is a bigger transformation than SaaS” — [Workday 8-K Ex.99.1](https://www.sec.gov/Archives/edgar/data/1327811/000132781126000007/wday-020626xex991.htm)
- Q2 FY27（2026-08-27）：订阅收入$2.471B（+13.9%）；12个月订阅积压$9.034B（+14.2%）；5,500+客户使用至少一个原生agent（环比+35%）；AI驱动>25%新ACV；FY27订阅收入指引$9.94–9.95B（+13%） — [Workday Q2 FY27](https://www.sec.gov/Archives/edgar/data/1327811/000132781126000042/wday-07312026x991.htm)
- 2026-09-29：重组裁员约2.5%（主要在产品与技术团队），费用$65–80M；文件未提及AI — [Workday 8-K](https://www.sec.gov/Archives/edgar/data/1327811/000132781126000048/wday-20260929.htm)

**Adobe（Q3 FY26，2026-09-10）**
- 收入$6.76B（+13%）；总Adobe ARR $27.50B；AI-first ARR同比增长>150%（未披露绝对值）；MAU超10亿；FY26收入指引$26.576–26.626B、期末ARR增长10.2%；管理层称以freemium扩大用户并深化agentic体验 — [Adobe Q3 FY26 Ex.99.1](https://www.sec.gov/Archives/edgar/data/796343/000079634326000147/adbeex991q326.htm)
- 2026-09-03宣布：Anil Chakravarthy将于2026-12-01接任CEO，Shantanu Narayen转任执行董事长 — [Adobe Newsroom](https://news.adobe.com/news/2026/09/adobe-reports-record-q3-fy2026-revenue)

**Oracle（Q1 FY27，2026-09-10）**
- 收入$19.3B（+30%）；云收入$11.6B（+62%）；OCI $7.4B（+121%）；云应用（SaaS）$4.2B（+10%）；RPO $664B（同比+$209B）；Q1新签>$30B AI云合同，自Q4末交付30万+GPU；自由现金流-$5B，通过ATM出售$20B普通股；FY27收入指引≥$90B — [Oracle 8-K](https://www.sec.gov/Archives/edgar/data/1341439/000119312526387905/0001193125-26-387905.txt)；FY26收入$67.4B，软件业务$24.5B同比下降1% — [SaaStr](https://www.saastr.com/by-year-end-anthropic-will-out-earn-every-public-software-company-except-microsoft/)

**Intuit与HubSpot**
- Intuit FY26（2026-08-25）：收入$21.4B（+14%）；Global Business Solutions $12.9B（+16%）；FY27指引仅+9–10%；战略定位“AI-driven expert platform” — [Intuit 8-K](https://www.sec.gov/Archives/edgar/data/896878/000089687826000029/0000896878-26-000029.txt)；2026-05-20宣布裁员约17%，费用$300–340M（文件未将其与AI挂钩） — [Intuit 8-K](https://www.sec.gov/Archives/edgar/data/896878/000089687826000024/0000896878-26-000024.txt)
- HubSpot Q2 2026（2026-08-05）：收入$911.7M（+20%，固定汇率+17%）；客户306,446（+14%）；每客户平均订阅收入$11,800（+4%）；CEO：“Our pricing updates make it easier for customers to get started, realize value quickly, and scale”“The AI shift unlocks a much larger opportunity” — [HubSpot 8-K](https://www.sec.gov/Archives/edgar/data/1404655/000119312526335148/0001193125-26-335148.txt)；2026-10-01董事会批准裁员约7%（约660人），费用$65–75M；CEO备忘录称“并非由AI效率驱动”，转向“交付客户结果”，未来人员增速将低于收入增速 — [HubSpot 8-K](https://www.sec.gov/Archives/edgar/data/1404655/000119312526414965/0001193125-26-414965.txt)

**SaaS股价与“SaaS已死/席位压缩”争论**
- 触发链：2026-01-12 Anthropic发布Claude Cowork，01-30发布Cowork plugins；02-03软件股单日蒸发约$285B市值、IGV进入熊市，Jefferies交易员创造“SaaSpocalypse”一词；02-23 Citrini Research颠覆情景报告后IGV见底；截至03-11一周反弹13%；03-24因新agent发布再跌4% — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- 截至2026-03-31年初至今：SEG SaaS指数-25.7%（同期标普500 -4.8%）；Atlassian -58.0%、Workday -39.7%、HubSpot -39.5%、ServiceNow -31.6%、Adobe -30.8%、SAP -30.8%、Salesforce -29.4%、Shopify -28.4% — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- 席位压缩论据：公开SaaS中位NRR由2021年117%降至2025年108%（SEG当前106%）；私有公司中位NDR由2022年106%降至2024年101%；公开SaaS中位收入增速由2021年27%降至2025年10%；Bain估AI可自动化关键职能30–50%活动 — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- 反方论据：Q4 2025标普500软件公司93%利润超预期；Deutsche Bank（3月中）称未发现任何预期2026年AI对收入有负面影响的软件公司；BofA称抛售“internally inconsistent”；WSJ报道多家Fortune 500科技高管是在内部搭小应用而非替换供应商 — [Long Angle](https://www.longangle.com/alts-education/software-ai)
- 溢出至私募信贷：软件约占BDC组合20%（约$100B）；2–4月9只基金赎回请求超上限（Blackstone BCRED 7.9%，约$3.7B）；JPMorgan 3月初下调软件抵押贷款估值 — [Long Angle](https://www.longangle.com/alts-education/software-ai)

### Inferences
- 量级对比（推论）：Salesforce Agentforce ARR $1.5B约占其FY27收入指引的3%；ServiceNow AI ACV $1B约占FY26订阅收入指引的6%；M365 Copilot 3,000万席位按$30标价上限约$10.8B年化（实际ARPU因折扣更低）——对比Anthropic单季$16.8B，巨头AI收入仍是“增量补充”而非主营替代。
- 巨头当前AI变现主要靠“提价+升级版本+捆绑”（ServiceNow AI版本+10–25%、Salesforce溢价版60–80%），真正的“按用量/按结果”收入要到2027年才规模化。
- “SaaS已死”在2026年更多体现为估值压缩与人员重组（Intuit 17%、HubSpot 7%、Workday 2.5%，三家文件均未把裁员归因于AI）以及CEO更替（Workday、Adobe），而非财报中的席位下滑；Salesforce等“基于记录系统（system of record）”的厂商以“headless/agent接口+数据平台”重新定位。
- Oracle的增长几乎全部来自AI云（OCI +121%），而其软件业务下滑1%——在“AI受益”叙事中，基础设施型巨头与应用型SaaS分化明显。

### Gaps
- Microsoft FY27 Q1、ServiceNow Q3（10-28）、Alphabet/Amazon Q3等将在2026年10月底发布，未纳入。
- Google Cloud/Gemini Enterprise 2026年企业AI指标、SAP Business AI/Joule具体收入、Adobe AI-first ARR绝对值、Intuit/HubSpot的AI agent与credits指标均未在可得文本中披露。
- 2026年4月后SaaS指数的反弹幅度：有二手来源称IGV在2026-04-13至10-12上涨约41%，但未能定位可靠出处，未核实。
- Microsoft 2026年M365提价、Copilot SKU/捆绑变化（如E5/E7、SMB版）未获取（官网页面503）。

## 5. 商业模式与GTM创新：定价、FDE/服务化、咨询/SI、云市场、ROI、采购安全、主权AI

### Takeaway
2026年toB AI定价从“纯席位”走向“席位+用量+结果”的混合菜单（Salesforce同时提供$2/对话、约$0.10/动作的Flex Credits、$5–$550/用户多档；Fin $0.99/resolution；Sierra按结果；Decagon按对话或按解决）。GTM最大变化是“交付能力”成为瓶颈：前沿实验室直接下场做服务（Anthropic与PE巨头合资服务公司、$100M培训1万名FDE、$100M伙伴网络；OpenAI据报设立Deployment Company），咨询/SI、三大云和支付/路由层成为分发渠道；企业采购关注“每单位智能成本”、零数据保留与客户自控存储。

### Cited Findings

**定价模式**
- Salesforce Agentforce现行价目：Flex Credits $500/10万credits（标准动作20 credits≈$0.10，语音≈$0.15），不结转、超额按合同价月结；对话制$2/次（面向客户的agent，不可与Flex Credits在同一org混用）；Agentforce User License $5/用户/月（需搭配Flex Credits）；Agentforce Coworker $50/用户/月；Sales/Service等add-on $125/用户/月（员工使用不计量），行业版$150；Max Edition $550起/用户/月（含每org每年275万Flex Credits）；Salesforce Foundations免费；购买方式Pre-Purchase、Pre-Commit、PayGo — [Salesforce Agentforce Pricing](https://www.salesforce.com/agentforce/pricing/)
- Salesforce管理层：以ILA、Flex Credits与超额计费变现；Benioff称客户可“按用户和agent、按消耗或按结果”购买；与$40M级客户谈“结果计价或ILA”二选一 — [Motley Fool 实录](https://www.fool.com/earnings/call-transcripts/2026/08/31/salesforce-crm-q2-2027-earnings-call-transcript/)
- 结果计价：Fin $0.99/resolution被视为市场参考价，2026年7月核实仍未变；Salesforce以约$3.6B收购Fin被解读为对“按解决计价”在企业规模上的最强验证；市场分化为“上移的计量式AI”与“小团队的含AI席位包” — [Drag（二手）](https://www.dragapp.com/blog/salesforce-buys-fin/)；Sierra按完成结果收费 — [Crypto Briefing](https://cryptobriefing.com/sierra-200m-annualized-revenue-may/)；Decagon按对话（更主流）或按解决（更高单价、升级人工不收费） — [Sacra](https://sacra.com/c/decagon/)
- 席位仍是主流之一：Glean按席位（ACV $100–500K） — [Sacra](https://sacra.com/c/glean/)；Perplexity Enterprise Pro $40/席位/月 — [Sacra](https://sacra.com/c/perplexity/)；Abridge约$2,500/临床医生/年 — [Sacra](https://sacra.com/c/abridge/)；Gamma credits+订阅（Plus $8、Pro $18、Ultra $100/月） — [Sacra](https://sacra.com/c/gamma/)
- ServiceNow：AI增长主要来自AI版本提价；credit池未用完；J.P. Morgan预计2027年约50%新增业务转向非席位 — [KuCoin转载JPM](https://kucoin.com/news/flash/jpmorgan-maintains-overweight-on-servicenow-ai-monetization-delayed-to-2027)
- “数字劳动力”计量单位：Salesforce以AWU（agent自主完成的离散任务，如解决工单、更新记录）作为核心KPI — [Motley Fool 实录](https://www.fool.com/earnings/call-transcripts/2026/08/31/salesforce-crm-q2-2027-earnings-call-transcript/)
- 实验室层面以token/用量为主：SaaStr指出Anthropic收入来自token与agent消耗而非席位，并认为席位制SaaS定价承压 — [SaaStr](https://www.saastr.com/by-year-end-anthropic-will-out-earn-every-public-software-company-except-microsoft/)

**FDE / 服务化交付**
- Anthropic + Blackstone/H&F/Goldman服务公司（2026-05-04）：小团队驻场找高价值用例→构建定制Claude系统→长期运维；大企业仍由SI主导，新公司补充中型企业交付能力 — [Anthropic](https://anthropic.com/news/enterprise-ai-services-company)
- Claude Frontier Academy（2026-10-02）：$100M，2027年底前培训1万名FDE，采用“医学式”培训（多日实训+12周驻场+终考），首批FDE徽章预计2027年初；Anthropic称“具备在真实企业落地能力的人才已成最难招的人才” — [Anthropic](https://www.anthropic.com/news/claude-frontier-academy)
- OpenAI：全球多地招聘FDE — [OpenAI Careers](https://openai.com/careers/forward-deployed-engineer-(fde)-sf-san-francisco/)；Deployment Company（>$4B，未核实） — [BestBlogs](https://www.bestblogs.dev/en/article/f648cbd2)

**咨询/SI与伙伴**
- Claude Partner Network：$100M（2026）、Accenture 3万人培训、Cognizant约35万人、Infosys CoE、伙伴团队扩5倍，并向伙伴提供Applied AI工程师支持在途项目、代码现代化starter kit — [Anthropic CPN](https://www.anthropic.com/news/claude-partner-network)；网络内已有Accenture、Deloitte、PwC等 — [Anthropic](https://anthropic.com/news/enterprise-ai-services-company)
- Accenture与Anthropic各5年至少$1B投入嵌入式评估（Faculty执行，Anthropic直接出资） — [Anthropic](https://www.anthropic.com/news/accenture-embedded-evaluation)
- ServiceNow Action Fabric以Anthropic为首个设计伙伴，开放给第三方AI通过ServiceNow工作流执行动作 — [ServiceNow Q2 2026 8-K](https://www.sec.gov/Archives/edgar/data/1373715/000137371526000072/erq2fy26.htm)

**云市场、路由与支付层**
- Claude可在AWS、Google Cloud、Microsoft三家使用；Anthropic未来十年云承诺约$450B（Google $111B、AWS $110B、Microsoft $31B） — [Anthropic CPN](https://www.anthropic.com/news/claude-partner-network)；[Investing.com/WSJ](https://www.investing.com/news/stock-market-news/anthropic-revenue-hits-163-billion-as-preliminary-s1-outlines-ipo-risks--wsj-4960928)
- Replit上架Azure（2025年7月）与Google Cloud Marketplace（2025年9月） — [Sacra](https://sacra.com/research/replit-passes-500m-year/)
- Stripe收购OpenRouter（2026-08-19）；Ramp、Cursor等推出自有路由器；OpenRouter企业版提供开通、权限与AI预算管理 — [Menlo](https://menlovc.com/perspective/stripe-to-acquire-openrouter-why-everyone-is-obsessed-with-model-routing/)

**ROI度量、采购与安全**
- OpenAI CFO（2026-08-14）：企业采购转向“cost per unit of intelligence” — [Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)；Ramp推出按提供方/模型/用户的周度Token Spend Management — [Crypto Briefing](https://cryptobriefing.com/ramp-ai-index-token-spend-volumes-update/)
- Anthropic Enterprise Frontier Safeguards（2026-09-01）：零数据保留（ZDR）+自动化滥用检测，数据存于客户自有AWS/Azure/GCP账户，客户管理密钥，旗标直达客户、Anthropic员工不审阅；不改变API价格/限额、不另收费；覆盖Claude Code、Claude Enterprise、Bedrock、Google Agent Platform、Microsoft Foundry；与100+客户共建（Goldman、Morgan Stanley、Citi、BofA、Wells Fargo、Mastercard、Visa、KPMG、Comcast、Salesforce、Snowflake、Stripe等）；自Fable 5起引入30天数据保留以支持跨会话滥用检测 — [Anthropic EFS](https://www.anthropic.com/news/enterprise-frontier-safeguards)

**主权/政府**
- Anthropic：新加坡办公室+政府MOU（2026-10-14）；美国Genesis Mission 3年$150M（10-08） — [Anthropic Newsroom](https://www.anthropic.com/news)
- ElevenLabs与英国DSIT签MoU（2026年6月） — [Sacra](https://sacra.com/c/elevenlabs/)
- OpenAI新一轮融资洽谈阿联酋MGX等主权基金 — [Yahoo/Bloomberg](https://finance.yahoo.com/technology/ai/articles/openai-expects-70-billion-annualized-014338719.html)

### Inferences
- 定价演进的实质是“谁承担不确定性”：席位制由客户承担使用不足风险，用量制由客户承担费用波动，结果制由供应商承担效果风险；2026年头部厂商普遍提供“菜单式”组合，而结果计价在客服等可清晰定义“解决”的场景率先跑通。
- “服务即软件”反向发生：模型厂商在补交付（FDE、合资服务公司、培训认证），说明企业AI的瓶颈已从“模型能力”转到“落地工程+流程改造”；收入将越来越多以“模型token+交付服务”捆绑形式出现。
- 分发渠道多元化：SI/咨询（大企业）、PE组合公司（中型企业）、云市场（采购便利+预算抵扣）、支付/费控层（Stripe、Ramp）——后者可能成为中小企业模型选择与预算的新“入口”。
- 安全/合规正在成为定价之外的竞争维度：Fable 5的数据保留要求影响了采用（Ramp），Anthropic随即推出客户自控存储的EFS。

### Gaps
- Zendesk结果计价、Microsoft Copilot Studio/agent计费、Workday Flex Credits、ServiceNow Pro Plus/assist packs等2026年具体价格未获取。
- OpenAI与咨询公司（如Accenture、PwC等）2026年新合作、OpenAI Frontier平台的伙伴与定价未核实。
- 未找到可靠的企业AI ROI统一测量框架或大样本ROI数据（除Bain样本）；“试点→生产”转化率的2026年权威数据缺失。
- 主权AI（OpenAI for Countries、Stargate各国项目、Mistral/Cohere等）的2026年进展未能覆盖。

## 6. 问题：毛利压力、试点落地、留存、价格战与收入质量

### Takeaway
2026年toB AI的核心问题不是需求，而是“收入质量与资本强度”：run-rate与实际收入、总额/净额确认、ARR口径扩大、客户集中度让数字难以横向比较；实验室账面巨亏与数千亿美元算力承诺并存；巨头的消费式AI收费普遍“credits未用完、变现推迟到2027”；模型价格持续通缩、路由器普及加剧同质化竞争；人才与交付能力成为落地瓶颈。

### Cited Findings

**收入质量/口径**
- run-rate vs 实际：Anthropic 7月run-rate $65B，而上半年实际收入$16.3B — [CNBC](https://www.cnbc.com/2026/08/17/anthropic-says-annualized-revenue-climbed-to-65-billion-in-july.html)；[Investing.com/WSJ](https://www.investing.com/news/stock-market-news/anthropic-revenue-hits-163-billion-as-preliminary-s1-outlines-ipo-risks--wsj-4960928)；SaaStr提醒run-rate为前瞻口径且Anthropic部分云渠道按总额确认 — [SaaStr](https://www.saastr.com/by-year-end-anthropic-will-out-earn-every-public-software-company-except-microsoft/)
- OpenAI“$50B vs $70B”之争源于口径（FT），消息令Nasdaq 100当日跌1.4% — [Yahoo/Bloomberg](https://finance.yahoo.com/technology/ai/articles/openai-expects-70-billion-annualized-014338719.html)；Reuters来源亦未说明Anthropic季度收入是总额还是净额、如何定义盈利 — [The Star（Reuters）](https://www.thestar.com.my/tech/tech-news/2026/10/15/anthropic039s-q3-revenue-surges-45-to-nearly-17-billion)
- Salesforce Agentforce ARR自Q2 FY27起纳入Slackbot与Headless 360，增速非同口径 — [Salesforce Q2 FY27](https://www.salesforce.com/news/press-releases/2026/08/26/fy27-q2-earnings/)
- 客户集中度：Anthropic两家客户占2025年近1/4、2026上半年约20%收入，公司预计有限客户群将在可预见未来贡献显著收入份额 — [Investing.com/WSJ](https://www.investing.com/news/stock-market-news/anthropic-revenue-hits-163-billion-as-preliminary-s1-outlines-ipo-risks--wsj-4960928)
- 应用层ARR多为估算或未注明来源（如Sierra $200M的出处未标注；Harvey ARR各源$300M–$400M+不一） — [Crypto Briefing](https://cryptobriefing.com/sierra-200m-annualized-revenue-may/)；[Sacra](https://sacra.com/c/harvey/)

**亏损与资本强度**
- Anthropic 2025年经营亏损$8.06B；2026上半年净亏损$80.7B（$72B非现金），算力支出近$9B；不可撤销云承诺约$450B，潜在最高$750B；文件称寻求的容量超过超大云厂商愿意提供的水平，因而转向第三方数据中心 — [Fortune](https://fortune.com/2026/09/29/anthropic-leaked-ipo-prospectus-losses-growth-ai-end-humanity/)；[Investing.com/WSJ](https://www.investing.com/news/stock-market-news/anthropic-revenue-hits-163-billion-as-preliminary-s1-outlines-ipo-risks--wsj-4960928)
- Oracle Q1 FY27自由现金流-$5B并通过ATM出售$20B股票；Microsoft FY26物业设备现金支出$115.9B（上年$64.6B） — [Oracle 8-K](https://www.sec.gov/Archives/edgar/data/1341439/000119312526387905/0001193125-26-387905.txt)；[Microsoft FY26 Q4](https://www.microsoft.com/en-us/investor/earnings/fy-2026-q4/press-release-webcast)

**毛利**
- Anthropic Q3毛利率85%（Bloomberg，经搜索摘要，口径未明）——与“上半年近$9B算力支出”并存，可能未计训练成本 — [BGOV/Bloomberg](https://news.bgov.com/artificial-intelligence/anthropic-revenue-hits-16-8-billion-in-quarter-before-ipo-1)
- ServiceNow：AI产品毛利率目前与公司平均相当，但算力规模化后能否维持是关键问题；FY毛利展望反映更多超大云合作 — [TNW](https://thenextweb.com/news/servicenow-30-billion-2030-now-assist-ai-revenue)；[ServiceNow Q2 2026 8-K](https://www.sec.gov/Archives/edgar/data/1373715/000137371526000072/erq2fy26.htm)
- RBC公开摘要：AI-native软件毛利率%可能更低但毛利额更高（无具体数字） — [New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)

**试点落地/ROI/消费不足**
- Bain：测量过节省的公司近40%节省<10%；仅7%运行完全自主agent — [New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)
- ServiceNow多数客户未用完credit池，消费式变现推迟到2027 — [KuCoin转载JPM](https://kucoin.com/news/flash/jpmorgan-maintains-overweight-on-servicenow-ai-monetization-delayed-to-2027)；Salesforce仅5%知识工作者升级溢价版 — [Motley Fool 实录](https://www.fool.com/earnings/call-transcripts/2026/08/31/salesforce-crm-q2-2027-earnings-call-transcript/)
- （背景）Gartner 2025-06-25预测：到2027年底超过40%的agentic AI项目将被取消 — [Drag（转引）](https://www.dragapp.com/blog/salesforce-buys-fin/)
- 人才瓶颈：Anthropic称落地人才是“AI实施中最紧迫的问题之一” — [Anthropic](https://www.anthropic.com/news/claude-frontier-academy)

**价格战/同质化**
- Opus 5.5运行成本较Opus 5低40%、Sonnet 5.5最多低30% — [Anthropic Newsroom](https://www.anthropic.com/news)；OpenAI新模型agentic coding效率+54%并降价，Brockman谈及中国开源模型竞争 — [Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- 10余家公司推出模型路由器，Menlo举例“换模型每年省$100K”的仪表盘（假设性示例） — [Menlo](https://menlovc.com/perspective/stripe-to-acquire-openrouter-why-everyone-is-obsessed-with-model-routing/)
- Ramp：部分高支出企业人均AI支出环比下降 — [Crypto Briefing](https://cryptobriefing.com/ramp-ai-index-token-spend-volumes-update/)

**模型质量/合规风险影响采用**
- Fable 5因价格与数据保留要求采用不佳（Ramp经济学家） — [Crypto Briefing](https://cryptobriefing.com/openai-narrows-gap-anthropic-ramp-business/)；OpenAI因安全问题暂停GPT-6.1 Astra发布 — [PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/openai-annualized-revenue-nears-70-billion-amid-enterprise-growth/)

**留存**
- 公开SaaS中位NRR由117%（2021）降至108%（2025），SEG当前106% — [Long Angle](https://www.longangle.com/alts-education/software-ai)；消费侧：46%付费者支出较一年前增加、12%减少 — [Menlo](https://menlovc.com/perspective/2026-the-state-of-consumer-ai/)；Replit流失被描述为“低”（无数字） — [Sacra](https://sacra.com/research/replit-passes-500m-year/)

### Inferences
- 2026年“vibe revenue”争议的主战场从小型AI应用转移到了前沿实验室本身：同一家公司可同时给出“$65B run-rate”“$16.8B季度收入”“调整后盈利”与“$80.7B半年净亏损”，口径选择会让结论截然相反；IPO后的标准化披露将是2027年的关键校准点。
- 消费式收费的“预付credits未消耗”是2026年巨头AI收入的隐性风险：订单（bookings）领先于真实使用，若2027年消耗未跟上，续约时可能出现降级或价格让步。
- 模型价格每代降30–40%，意味着实验室收入增长必须依靠用量（agent任务、编码token）指数级增长来抵消；对应用层而言，毛利改善的同时护城河更依赖工作流、数据与交付，而非模型差异。

### Gaps
- AI应用层毛利（尤其依赖第三方模型的编码/客服公司）在2026年的可靠数据缺失；推理成本对AI-native公司毛利的量化影响未获取。
- 2026年AI应用的logo/收入流失率、“试点→生产”转化率（如MIT NANDA等）2026年更新版未获取。
- Anthropic 85%毛利率的口径（是否剔除训练、是否按净额收入）待核实。

## 7. 2027年toB AI商业化信号

### Takeaway
2027年的关键变量：（1）AI实验室上市（Anthropic最早2026年11月后，OpenAI至少2027年）把收入口径与盈利能力置于公开监管之下；（2）巨头的消费式/非席位AI变现集中在2027年兑现或证伪（ServiceNow约50%新增业务转非席位）；（3）FDE/服务化交付规模化（1万名FDE目标）；（4）推理成为算力支出主体、价格持续下探；（5）AI-native头部公司被并购或上市、SaaS巨头继续并购agent能力与重组。

### Cited Findings
- Gartner预计2027年全球AI支出$3.3T；2027年推理将占AI-optimized IaaS的59% — [Gartner 2026-01-15](https://www.gartner.com/en/newsroom/press-releases/2026-1-15-gartner-says-worldwide-ai-spending-will-total-2-point-5-trillion-dollars-in-2026)；[Techstrong](https://techstrong.ai/features/gartner-global-ai-spending-to-hit-2-7-trillion-in-2026/)
- IPO：Anthropic目标估值>$2T、上市或在11月中期选举后 — [Fortune](https://fortune.com/2026/09/29/anthropic-ipo-s-1-prospectus-income-statement/)；OpenAI IPO推迟至至少2027年，正以$1.4T pre-money融资、目标年底≥$70B annualized — [Yahoo/Bloomberg](https://finance.yahoo.com/technology/ai/articles/openai-expects-70-billion-annualized-014338719.html)
- 收入外推：分析师估Anthropic 2026年底run-rate可达$110B — [The Star（Reuters）](https://www.thestar.com.my/tech/tech-news/2026/10/15/anthropic039s-q3-revenue-surges-45-to-nearly-17-billion)
- 巨头：ServiceNow预计消费式变现2027年规模化、约50%新增业务转向非席位，席位压缩“第一波”在2027 — [KuCoin转载JPM](https://kucoin.com/news/flash/jpmorgan-maintains-overweight-on-servicenow-ai-monetization-delayed-to-2027)；ServiceNow 2030年目标$30B订阅收入、约30% ACV来自AI — [TNW](https://thenextweb.com/news/servicenow-30-billion-2030-now-assist-ai-revenue)；Salesforce对Fin的收购预计在FY27 Q4（2026年11月–2027年1月）完成 — [Salesforce IR](https://investor.salesforce.com/news/news-details/2026/Salesforce-Signs-Definitive-Agreement-to-Acquire-Fin/default.aspx)
- 交付能力：Anthropic目标2027年底培训1万名FDE，首批徽章2027年初 — [Anthropic](https://www.anthropic.com/news/claude-frontier-academy)；EFS“今秋”广泛可用 — [Anthropic EFS](https://www.anthropic.com/news/enterprise-frontier-safeguards)
- 重组延续至2027：Workday员工调整预计在FY28 Q1基本完成；HubSpot现金支付至2027-06-30，人员增速将低于收入 — [Workday 8-K](https://www.sec.gov/Archives/edgar/data/1327811/000132781126000048/wday-20260929.htm)；[HubSpot 8-K](https://www.sec.gov/Archives/edgar/data/1404655/000119312526414965/0001193125-26-414965.txt)
- 低增长指引：Intuit FY27收入指引+9–10%；Adobe FY26期末ARR增长10.2% — [Intuit 8-K](https://www.sec.gov/Archives/edgar/data/896878/000089687826000029/0000896878-26-000029.txt)；[Adobe Q3 FY26](https://www.sec.gov/Archives/edgar/data/796343/000079634326000147/adbeex991q326.htm)
- 编码agent外溢：Codex在法务/销售/招聘周活用户数十至百倍增长；Codex占企业输出token 64% — [Unite.AI](https://www.unite.ai/openai-tells-investors-enterprise-revenue-has-overtaken-its-chatgpt-consumer-business/)
- 价格与路由：新一代模型降价30–40%；路由/费控层被支付公司整合（Stripe–OpenRouter） — [Anthropic Newsroom](https://www.anthropic.com/news)；[Menlo](https://menlovc.com/perspective/stripe-to-acquire-openrouter-why-everyone-is-obsessed-with-model-routing/)
- 企业预算意愿：90% CIO计划增加AI支出并设立专门预算；无人预期软件总支出下降 — [CRN India](https://www.crn.in/news/cios-signal-rising-tech-spend-and-deeper-shift-to-enterprise-ai-in-2026/)；[New Space Economy](https://newspaceeconomy.ca/2026/06/26/enterprise-ai-spending-market-analysis-2026/)

### Inferences
- 2027年toB商业化方向（推论）：
  1. **从“卖席位”到“卖完成的工作”**：结果/任务计价（resolution、AWU、agent action）将从客服扩展到IT服务、财务运营、法务等可定义产出的流程；巨头的“credits预付+超额”模式将接受真实消耗检验。
  2. **编码agent成为通用企业agent入口**：Claude Code/Codex向非工程职能渗透，可能直接侵蚀垂直SaaS与内部工具预算，同时推动“企业自建小应用”（Lovable/Replit类）。
  3. **交付即护城河**：FDE、合资服务公司、SI伙伴认证体系决定大客户获取速度；“模型+交付+治理（EFS类）”捆绑销售成为大单标准形态。
  4. **口径透明化**：IPO与公开财报将迫使行业区分run-rate、GAAP收入、总额/净额与ARR定义，估值可能从“ARR倍数”转向“毛利额/自由现金流”。
  5. **价格通缩下的用量竞赛**：单位token价格持续下降、推理占比上升，收入增长依赖agent长任务带来的用量爆发；路由与费控层（Stripe/Ramp/OpenRouter）将增强买方议价。
  6. **并购整合**：SaaS巨头继续收购AI-native agent公司（Salesforce–Fin模式），平台型公司收购开发者入口（SpaceX/xAI–Cursor模式）；同时SaaS内部持续“组织扁平化+人员增速低于收入”。
- 需警惕的反向信号：若2027年巨头AI credits消耗不及预期、Gartner所称agent项目大量取消、或实验室IPO后披露的净额收入/毛利显著低于市场认知，toB AI估值可能经历再定价。

### Gaps
- 未获取IDC、Forrester、Gartner对2027年企业GenAI软件（非基础设施）支出的分项预测。
- 未获取a16z/ICONIQ/Bessemer对2027年AI应用定价与预算结构的调研结论。
- Microsoft、ServiceNow、Alphabet、Amazon等10月底财报（含2027财年展望）尚未发布，需在成稿前补充。
