---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 44 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [1Password 披露 2026 年 11 月后端代码安全事件](#item-tech-news-1) ⭐️ 8.0/10
2. [Aaronson 谈 AI 数学进展与 Lean 验证争议](#item-tech-news-2) ⭐️ 8.0/10
3. [用 Lean 审查 Clojure 核心库并报告未公开缺陷](#item-tech-news-3) ⭐️ 7.0/10
4. [GRH Lean 证明压缩至约 7.6 万行](#item-tech-news-4) ⭐️ 7.0/10
5. [Google 发布 Cogentic 整数分解与离散对数论文](#item-tech-news-5) ⭐️ 7.0/10
6. [LoomFormer：按 token 路由早期注意力头](#item-tech-news-6) ⭐️ 7.0/10
7. [NVIDIA 开放 Nemotron-Labs-Image-30B-A3B 权重](#item-tech-news-7) ⭐️ 7.0/10
8. [LoopRes：用循环残差提升预训练 LLM 微调](#item-tech-news-8) ⭐️ 7.0/10
9. [腾讯开源 Hy4 flash 量化权重，最小版可在 64GB Mac mini 运行](#item-tech-news-9) ⭐️ 7.0/10
10. [Minecraft Java 版资源包字体 RCE 漏洞](#item-tech-news-10) ⭐️ 7.0/10
11. [三星、SK 海力士据悉采用长江存储 Xtacking 技术](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝施压英特尔交出 10%股权 政府未付对价获得股份](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对 14 个贸易伙伴加征第 301 条国别关税](#item-finance-news-2) ⭐️ 8.0/10
3. [黄仁勋回归英伟达，美中 AI 竞争聚焦人才](#item-finance-news-3) ⭐️ 7.0/10
4. [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为免费提供星链终端](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 披露 2026 年 11 月后端代码安全事件](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 就 2026 年 11 月安全事件发布博客更新，事件涉及据称被推送到后端服务的恶意代码。现有材料没有说明攻击者如何获得代码推送或部署权限，也未交代是否缺少 main 分支保护规则或这些规则被绕过。对使用其托管服务的用户而言，关键未决问题是后端代码是否可能接触账户数据；评论者还指出，公告未明确说明加密保险库未被下载。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「事件背景」** 1Password 的公告称，公司于 2026 年 11 月 19 日开始调查一起事件：攻击者访问了一名员工的公司 GitHub 账号，并利用该账号读取源代码、向后端服务推送恶意代码。MacRumors 的报道则称，此次事件中有部分客户的姓名和电子邮件地址被访问，但客户保险库内容未遭泄露。

**「影响与应对」** 1Password 表示客户保险库未被攻破、内容仍安全，但部分客户的姓名和电子邮件地址被访问，这些用户需警惕利用上述信息定制的钓鱼邮件。对公司和安全团队而言，公告未说明是否存在分支保护规则被绕过的问题，因此其他依赖员工 GitHub 权限向生产后端部署代码的 SaaS 团队目前无法据此评估自身同类风险。

**「社区讨论」** 评论区集中质疑后端代码部署链路：ctidd 追问 1Password 是否禁止直接推送 main、是否缺少分支保护规则或规则被绕过，并认为公告没有充分回应。tptacek 认为员工终端被攻陷后经代码仓库进入生产是 SaaS 公司的标准攻击路径；ChrisHardie 担心这类生产环境代码推送会动摇对在线保险库的信任，fn-mote 则希望公告明确写出“加密保险库未被下载”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1 Password ’s backend ...</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>

</ul>
</details>

**标签**: `#security incident`, `#password managers`, `#supply chain security`, `#SaaS security`, `#code deployment`

---

<a id="item-tech-news-2"></a>
### [Aaronson 谈 AI 数学进展与 Lean 验证争议](https://scottaaronson.blog/?p=10379) ⭐️ 8.0/10

Scott Aaronson 在一篇被广泛讨论的博文中把“过去一周”描述为类似 AI 奇点开端，称 AI 相关工具正在快速推进多个数学与理论计算机科学开放问题；帖子还链接了一份题为《矩阵乘法指数是 9/4》的材料。围绕这些结果的争论集中在 Lean/MathLib 形式化、形式证明与非形式证明的差异，以及未使用证明片段是否影响结论。给定的博客摘录和讨论没有给出具体模型、完整问题清单或独立复核，因此这些应视为博文与社区讨论中的主张，而非已确认的测量结果。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景」** 矩阵乘法指数 ω 描述两个 n×n 矩阵相乘所需算术运算数随 n 增长的速度；OpenAI 的 math 仓库在 11 月 24 日发布的预印本称，其 Lean 开发在无除法电路、形式多项式恒等式这一限定模型下证明了 9/4 的指数，范围文件还列出对偶和矩形指数。Lean 是可机器检查形式证明的证明助手，MathLib 是其数学库，因此这类工作的可信度取决于形式化范围是否覆盖非形式论证，以及独立检查能否复现。

**「对算法研究与证明核查的影响」** 如果该预印本的下界成立，矩阵乘法的指数就被确定为 9/4，与已知上界吻合，算法研究者也就不必再寻找渐近更快的矩阵乘法算法，而应转向常数因子、实际实现等方向。不过相关报道指出，Lean 形式化目前只覆盖这套论证的一部分，因此在把 9/4 当作已定结论之前，同行需要逐项核对 Lean 证明与论文非形式论证是否一致。

**「社区讨论」** 评论者 utopiah 质疑，若只有 Lean、MathLib 和算力而没有 LLM/GenAI，这些进展是否仍会发生；onetimeusename 则反驳把 Lean 与非形式证明之间的差异轻描淡写为琐碎问题的态度，认为计算机生成证明的核验问题长期存在、不应被忽略。pixl97 担心这类能力若从可验证任务外溢到更开放的领域，会带来更大的不确定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md">math /preprints/The- matrix - multiplication - exponent -is...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://kingy.ai/blog/openai-matrix-multiplication-exponent-nine-fourths/">OpenAI Claims Matrix Multiplication Exponent Is Exactly 9/4</a></li>
<li><a href="https://xenospectrum.com/en/matrix-multiplication-nine-fourths-lower-bound/">OpenAI Preprint Claims the Matrix Multiplication Exponent Is ...</a></li>

</ul>
</details>

**标签**: `#AI for mathematics`, `#Lean theorem proving`, `#proof verification`, `#matrix multiplication`, `#Hacker News discussion`

---

<a id="item-tech-news-3"></a>
### [用 Lean 审查 Clojure 核心库并报告未公开缺陷](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

一篇博客文章发布了用 Lean 审查 Clojure 核心库的结果，声称发现此前未被报告的缺陷；这一结论目前来自作者的审计，尚不等同于独立复现或上游维护者确认。对 Clojure 用户和库维护者而言，是否构成实际问题取决于具体案例能否被认定为核心库缺陷并进入修复或测试。

hackernews · encyclopedism · 11月25日 14:56 · [社区讨论](https://news.ycombinator.com/item?id=50642939)

**「背景」** Clojure 的核心库（clojure.core）提供 \`seq\`、\`get\` 等基础函数，其中不少函数的行为依赖 Java 宿主类型，例如字节数组和字符串，因此参数类型与隐式转换会直接影响结果。Lean 是依赖类型的交互式定理证明器，主要用于形式化数学和程序验证；用它审计动态语言库，通常是把函数的预期行为写成 Lean 命题，再通过证明或反例来检查实现是否符合这些规格。

**「对开发者的实际影响」** 对打算依据这份审计清单修改代码的 Clojure 开发者来说，第一步应是分诊而非直接修复：社区讨论已指出，清单中至少两项分别是调用方把 Long 传给 byte-array 的 .indexOf，以及 get 对字符串键做整数强制转换这一既有语义，属于用法或类型问题而非库缺陷，若照单全收地改动反而会引入噪声。考虑到 Clojure 在 Nubank 等机构承载大规模关键业务系统，核心函数的边界语义确实值得逐条核对，但现有证据只能说明存在值得复查的边角行为，尚不足以证明存在可触发的生产故障。

**「社区讨论」** 评论者对清单中的至少两个案例提出质疑：\`\(.indexOf \(seq \(byte-array \[1 2 3\]\)\) 2\)\` 被指为把 Long 传给按字节处理的 \`indexOf\`，\`\(get &quot;abc&quot; 1.9\)\` 则被解释为 \`get\` 在字符串场景下把键强制转换为整数，因此更像类型使用或边界行为问题，而非核心库缺陷。另有评论者称在 SBCL、Clozure 和 ACL2 中做过类似审计并发现数十个问题，同时有人询问这类工作为何转向 Lean、语言模型是否比 Rocq 更擅长写 Lean。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cognitect.com/">Cognitect, a Nu Holdings, Ltd. Company</a></li>

</ul>
</details>

**标签**: `#Clojure`, `#Lean`, `#formal verification`, `#programming languages`, `#bug finding`

---

<a id="item-tech-news-4"></a>
### [GRH Lean 证明压缩至约 7.6 万行](https://github.com/lsernau/grh-lean) ⭐️ 7.0/10

一个与广义黎曼猜想（GRH）相关的 Lean 形式化项目发布了大幅缩短的版本，社区评论称代码量从约 1700 万行降至约 7.6 万行，降幅约 99.56%。评论还指出，缩短版区分“已知数学”和“新数学”，并配有较多人读文档，便于理解。这些数字和效果目前主要来自 GitHub 仓库与 Hacker News 讨论，尚非同行评审或独立复现的结果；社区也把这次压缩与 Anthropic 的算力和模型辅助联系起来，但这属于评论判断。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** Horizon 11 月 21 日的摘要曾报道，Levent Alpöge 声称与 Claude 合作发现了广义黎曼猜想（GRH）的证明，并称相关论证已在 Lean 中无额外假设地形式化；该摘要同时指出，这仍是未经独立验证的声明，评论中提到的证明归档约 1500 万行。另有报道给出的原始形式化为 17,374,215 行 Lean 代码、175,187 个文件。此次条目讨论的较短版本，正是在这一超大形式化基线上出现的压缩版本。

**「影响」** 对 Lean 用户和形式化验证研究者来说，若缩短版能通过编译并保持与原证明等价，最直接的好处可能是人工审查和后续维护成本显著下降；在采用前仍应核对压缩是否保留了完整证明链，而不能只依据行数降幅判断正确性。

**「社区讨论」** 有评论称赞缩短版用“已知数学/新数学”的分区和文档提升了可读性，也有人追问这类 Lean 代码究竟有多少人能真正读懂并人工验证。另有评论把大幅压缩归因于 Anthropic 投入算力和更强的内部模型，这属于对原因的判断，而非已证实结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://alpo.ge/remark.pdf">2026-11-21 — Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis</a></li>
<li><a href="https://meridian48.com/news/ai-assisted-lean-proof-for-riemann-hypothesis-spans-17-4-million-lines-7c3f57">AI-assisted Lean proof for Riemann Hypothesis spans 17.4 ...</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#AI-assisted mathematics`, `#proof minimization`, `#open source`

---

<a id="item-tech-news-5"></a>
### [Google 发布 Cogentic 整数分解与离散对数论文](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research 的 GitHub 仓库发布了名为 Cogentic 的论文集合，主题涵盖整数分解、离散对数及相关数论问题。现有材料只提供了论文集合的标题和仓库入口，没有论文细节、同行评审结果或经独立验证的密码学影响，因此尚不能据此判断 RSA 等依赖整数分解或离散对数的系统是否受影响。

hackernews · rgwohlbold · 11月25日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50642086)

**「背景」** 整数分解和离散对数是公钥密码学中的两类基础难题：前者支撑 RSA 等方案的安全假设，后者是在模运算中由底数和结果反求指数。社区讨论还提到，正因整数分解的可靠性长期受到质疑，业界才发展出不依赖 RSA 的替代方案，因此相关算法论文会首先被放在现有密码部署的背景下审视。

**「社区讨论」** 评论者 gukoff 认为，该整数分解结果建立在通用数域筛法（GNFS）之上，用更高的复杂度代价替换了 GNFS 中依赖未证明启发式的部分，但并未证明这些猜想。另一名评论者 fidotron 转述所谓“可信人士”的传闻，称这只是更大成果的开端；该说法在给定材料中没有得到证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Discrete_logarithm">Discrete logarithm - Wikipedia</a></li>
<li><a href="https://news.ycombinator.com/item?id=50642086">Google releases Cogentic papers on integer factorization , discrete ...</a></li>

</ul>
</details>

**标签**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#number theory`, `#Google Research`

---

<a id="item-tech-news-6"></a>
### [LoomFormer：按 token 路由早期注意力头](https://www.reddit.com/gallery/1y50x62) ⭐️ 7.0/10

LoomFormer 让每个注意力头不再只按固定权重读取早期头，而是由当前 token 的残差流计算读写地址，并在残差流旁维护 2n 个与单头同宽的槽位；这种“纵向”头间注意力（warp）与常规 token 注意力（weft）交错。作者称，在相同参数预算和相同的 300B Pile token 上训练的 2.8B 模型，在 10 项任务平均分上与 Pythia-12B 持平：零样本 59.9 对 59.9，五样本 61.6 对 60.8，并显著优于 mHC。帖子还称 Pythia-2.8B 第 17–32 层只有 23% 的头关注非 sink token，而该模型为 74%。代价是 FLOPs 增加 2–4%，即使使用融合内核，实际运行时间仍比普通 Transformer 慢 8–16%，且目前最大只训练到 2.8B；这是一则 Reddit 自述，结果被截断，尚无独立验证。

reddit · r/MachineLearning · Alternative\_Cellist1 · 11月25日 07:05 · [社区讨论](https://www.reddit.com/r/MachineLearning/comments/1y50x62/letting_each_attention_head_choose_which_earlier/)

**「背景」** 原帖把 mHC 列为对照方法之一。mHC（manifold-constrained hyper-connections）属于在残差流上学习多条通路、而非只保留单一残差连接的一类做法，其公开对比表已在多个下游基准上比较 Baseline、HC 与 mHC（tool-2-1）。Gödel Machines 此前发布了首个采用 mHC 的 10 亿参数级开源预训练模型 goedel-mHC-1B，权重以 Apache 2.0 提供，并同时给出在相同条件下训练的标准 Transformer 基线，使 mHC 具备可查的对照结果（tool-2-2）。至于 Pythia，原帖将其作为使用相同 300B Pile token 与相同参数预算的基线模型。

**「影响」** 对想复现或采用该结构的团队，主要工程负担是为每个 token 维护槽位矩阵，并处理大量小投影带来的内存流量；作者给出的 8–16% 实际运行时间减速意味着质量收益必须足以抵消这一开销。当前公开证据只有作者自述的 2.8B 规模对比，尚未覆盖更大模型或独立复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2512.24880">mHC: Manifold-Constrained Hyper-Connections - arXiv.org</a></li>
<li><a href="https://www.goedelmachines.com/blog/releasing-goedel-mhc-1b">Releasing goedel-mHC-1B · Gödel Machines</a></li>

</ul>
</details>

**标签**: `#transformer architectures`, `#attention routing`, `#dynamic computation`, `#language models`, `#ML research`

---

<a id="item-tech-news-7"></a>
### [NVIDIA 开放 Nemotron-Labs-Image-30B-A3B 权重](https://www.reddit.com/gallery/1y4yrts) ⭐️ 7.0/10

据 Reddit 帖子，NVIDIA 已在 Hugging Face 放出 Nemotron-Labs-Image-30B-A3B 的开放权重；这是一个总参数 30B、激活参数 3B 的 MoE 自回归图像生成器，属于 Nemotron-Labs-VisualCreation（“Pixel as Code”）框架。该框架被描述为用于创建栅格图像以及网页、演示文稿、文档、图表和科学图等可编辑视觉产物的智能体框架；模型采用 Nemotron-H 的 Mamba-2 与注意力混合结构，从 Nemotron 3 Nano 初始化，并经过渐进式中训练和 GRPO。帖子还称，该模型在关键基准上超过 GPT Image 2 和 Nano Banana Pro，但没有提供官方确认或具体基准数据。

reddit · r/LocalLLaMA · ResearchCrafty1804 · 11月25日 05:00 · [社区讨论](https://www.reddit.com/r/LocalLLaMA/comments/1y4yrts/nvidia_just_quietly_dropped_open_weights_for/)

**「背景」** 混合专家（MoE）模型标注的“30B 总参数/3B 激活参数”意味着模型总容量约 300 亿参数，但处理每个 token 时只激活约 30 亿参数，从而把推理开销压到更接近小模型的水平。Nemotron 系列已有采用这一规格的开放模型，Hugging Face 页面则说明此次初始发布包含图像生成器及其配套视觉分词器。

**「影响」** 对开发者而言，开放权重意味着可以在自有环境中部署这一 30B MoE 图像生成器，并针对特定视觉任务进行微调，而不必只依赖闭源 API。但帖中未给出许可证、显存需求或推理延迟信息，实际采用前需核实这些条件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/nvidia/Nemotron-Labs-Image-30B-A3B">nvidia / Nemotron - Labs - Image - 30 B - A 3 B · Hugging Face</a></li>
<li><a href="https://developer.nvidia.com/topics/ai/nemotron">Nemotron AI Models | NVIDIA Developer</a></li>

</ul>
</details>

**标签**: `#open-weights`, `#image-generation`, `#multimodal`, `#NVIDIA`, `#MoE`

---

<a id="item-tech-news-8"></a>
### [LoopRes：用循环残差提升预训练 LLM 微调](https://i.redd.it/kv552tyzbq3i1.png) ⭐️ 7.0/10

一种名为 LoopRes 的微调方法被提出，目标是把预训练 LLM 的循环层从仅有边际提升变为稳定增益。它基于 Attention Residuals，让每个循环层直接关注此前循环的输出，并用可训练的 loop-aware key 区分这些迭代；同时把每层的残差窗口限制在最近 W 个循环，迫使模型逐环增量构建。帖子摘要称，在 3 个模型家族、6 个预训练 LLM 和 9 个基准上，2 倍计算下 Qwen3-1.7B-Base 比 SFT 提升 29.1%，超过此前最佳基线增益的两倍，并在最大 30B 模型及三个家族上保持；从 1.7B 到 8B，LoopRes 随计算增长比 SFT 更陡、上限更高，长输出所需计算更少。上述均为帖子中的作者声明，摘要被截断，且来源为 Reddit，尚无同行评审或独立复现信息。

reddit · r/LocalLLaMA · Powerful\_Evening5495 · 11月25日 09:44 · [社区讨论](https://www.reddit.com/r/LocalLLaMA/comments/1y53dpq/unlocking_the_power_of_loops_in_pretrained_llms/)

**「背景」** 循环 Transformer 通过反复执行同一组共享层，在不增加参数的情况下增加计算量，但此前这类架构通常需要从零训练，且在 LLM 上仅带来有限提升。把已有预训练模型微调成循环结构的成本更低，但相对常规 SFT 的收益同样边际；LoopRes 所基于的 Attention Residuals 则提供了让层直接读取早期循环输出的思路。

**「影响」** 对希望以较低成本把现有预训练模型改造成循环计算的团队，LoopRes 提供了一条在微调阶段而非从头训练时获取循环收益的候选路径；实际采用前需关注残差窗口 W、loop-aware key 的实现细节，并等待完整论文、基准配置和独立复现。

**标签**: `#looped transformers`, `#LLM fine-tuning`, `#attention residuals`, `#test-time scaling`, `#model efficiency`

---

<a id="item-tech-news-9"></a>
### [腾讯开源 Hy4 flash 量化权重，最小版可在 64GB Mac mini 运行](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过 AngelSlim 开源了 224B 参数 Hy4 flash 的 GGUF 量化权重：原权重约 410.27GiB，最小的 IQ2-AH 版本为 125.73GiB，约为原版的 30%。借助 Strata offload 框架，该最小版本可在 64GB Mac mini 上运行。腾讯方面公布的数据显示，48GB 显存设备在 10K 上下文下每秒生成 89 个 token，M5 Max 128GB 跑 Q3\_K 版本、32K 上下文时每秒生成 47 个 token；在 DeepSWE v1.1 等评测中，Q3\_K 与原模型得分差距不超过 0.4 分。上述吞吐和评测数据尚缺独立复测。

telegram · zaihuapd · 11月25日 09:29

**「背景」** Hy4 flash 的总参数量为 224B，属于需要大幅压缩才能部署到个人设备的模型规模；GGUF 是一种把量化后的权重打包、供本地推理使用的格式。腾讯通过 AngelSlim 工具箱完成这次量化，而 Strata offload 这类卸载框架会把设备内存容纳不下的部分权重放到外部存储，并在需要时调回，从而降低运行时的内存占用。

**「实际运行速度」** 对打算在 64 GB Mac mini 上本地运行的用户，关键限制是速度，而不只是能否加载：Hugging Face 模型卡给出的 M4 Pro 64 GB、IQ2 量化、8K 上下文实测为预填充 125–127 token/s、解码 17.3 token/s，低于来源中 48 GB 显存设备的 89 token/s 和 M5 Max 的 47 token/s，但测试条件不同。部署前应按这一量级评估交互体验，并为 125.73 GiB 的权重预留足够磁盘空间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/032/131.htm">让大模型跑在个人设备上，腾讯混元开源 Hy 4 flash GGUF ...</a></li>
<li><a href="https://huggingface.co/AngelSlim/Hy4-flash-GGUF">AngelSlim/ Hy 4 - flash -GGUF · Hugging Face</a></li>

</ul>
</details>

**标签**: `#open-source models`, `#model quantization`, `#GGUF`, `#local inference`, `#Tencent Hunyuan`

---

<a id="item-tech-news-10"></a>
### [Minecraft Java 版资源包字体 RCE 漏洞](https://github.com/bikini/minecraft2shell) ⭐️ 7.0/10

11 月 22 日公开的 minecraft2shell 显示，服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Java 版 26.3 Windows 客户端执行任意代码。受影响版本为 1.20.5 至 1.21.10 及 26.1 至 26.4 快照，1.20.4 及更早版本和基岩版不受影响。Mojang 仍使用 lwjgl-freetype 3.4.3，暂无官方补丁；社区于 11 月 24 日发布 m2sfix 1.0.0，通过 Java agent 或 mod 关闭 hinting。

telegram · zaihuapd · 11月25日 12:46

**「背景」** Minecraft Java 版客户端通过 LWJGL 的 lwjgl-freetype 绑定调用 FreeType 来解析并渲染资源包中的 TrueType 字体；当服务器下发资源包时，客户端就会把不受信任的字体数据交给字体解析器处理。该 PoC 的验证环境是 Mojang 签名的 Java 26.3 Windows 客户端，其捆绑的 FreeType 为 2.14.3 x64，攻击面因此位于客户端自带的原生字体组件。

**「影响与应对」** 在官方补丁发布前，受影响 Java 版玩家应避免加入会下发不可信资源包的服务器，并将多人游戏服务器资源包权限设为“禁用”，或安装 m2sfix 1.0.0；服务器运营者也应暂停向客户端推送未经验证的资源包。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>

</ul>
</details>

**标签**: `#Minecraft`, `#RCE`, `#vulnerability`, `#FreeType`, `#security`

---

<a id="item-tech-news-11"></a>
### [三星、SK 海力士据悉采用长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容。三星、SK 海力士和长江存储均拒绝置评，因此协议范围、量产时间和适用产品尚未得到确认。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上，再通过键合工艺合二为一，使两部分可以独立生产和优化；Omdia 高级分析师称，这种分工允许厂商自行生产存储阵列，把逻辑电路交给晶圆代工厂，从而用上更先进的制程。

telegram · zaihuapd · 11月25日 14:33

**「背景：Xtacking 是什么」** Xtacking 是长江存储于 2018 年首次展示的 3D NAND 架构：存储单元晶圆与外围逻辑（CMOS）电路晶圆分开制造，再通过晶圆对晶圆的混合键合（hybrid bonding）堆叠为一体，两部分因此可以各自独立生产与优化。据 TechPowerUp 报道，在第四代 Xtacking 中这一分离式设计仍然保留；长江存储则表示，自 2018 年以来已在全球提交逾 1.2 万件专利、在美国提交逾 4000 件申请。

**「影响」** 若该交叉许可最终实施，三星和 SK 海力士可在 3D NAND 中分开制造存储阵列与 CMOS 逻辑电路，并将逻辑部分交由晶圆代工厂生产，从而采用更先进的制程；这会改变它们与代工厂的协作方式。但三家公司均拒绝置评，协议覆盖范围、许可费用和量产时间尚未披露，因此当前只能视为未确认的计划。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/samsung-and-sk-hynix-tap-ymtcs-xtacking-tech-in-cross-license">Samsung and SK Hynix cross-license YMTC&#x27;s Xtacking 3D NAND</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking ...</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking ... | TechPowerUp</a></li>

</ul>
</details>

**标签**: `#semiconductor manufacturing`, `#3D NAND`, `#Xtacking`, `#memory industry`, `#cross-licensing`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝施压英特尔交出 10%股权 政府未付对价获得股份](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据 WIRED 和法庭文件报道，2025 年 8 月美国商务部律师在与英特尔首席财务官的通话中表示这并非一场谈判，若董事会拒绝将面临无法预测的后果，几天后英特尔董事会交出了美方要求的股份。特朗普随后宣布美国政府“完全拥有并控制英特尔 10%的股份”，且未为此支付对价，这批股份现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 2025 年 8 月，英特尔宣布与特朗普政府达成协议，随后特朗普于 8 月 22 日表示美国政府已取得英特尔 10%股份，商务部长卢特尼克也确认联邦政府将持有这 10%股份。

**「影响」** 对英特尔及其股东而言，美国政府凭这 10%股份获得对公司的控制权，公司治理结构由此改变。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.intel.com/content/www/us/en/newsroom/news/corporate/intel-and-trump-administration-reach-historic-agreement.html">Intel and Trump Administration Reach Historic Agreement to ...</a></li>
<li><a href="https://apnews.com/article/trump-intel-us-equity-stake-b538526b6698f7ebd31e99effd727693">Trump says US to get stake in Intel | AP News</a></li>
<li><a href="https://www.bbc.com/news/articles/cvg3zpdl3xdo">US government announces 10% stake in chipmaker Intel - BBC</a></li>

</ul>
</details>

**标签**: `#英特尔`, `#美国商务部`, `#政府持股`, `#半导体政策`, `#工业政策`

---

<a id="item-finance-news-2"></a>
### [美国拟对 14 个贸易伙伴加征第 301 条国别关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

据 CNBC 报道，美国拟依据 1974 年《贸易法》第 301 条，对包括中国、欧盟、日本、印度在内的 14 个贸易伙伴加征按国别设定税率的新关税。对华方案是在 2018 年已加征的 25%关税基础上再加 20%；若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，对华新关税可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 第 301 条允许美国对认定存在不公平贸易行为的国家加征关税；本轮针对的是靠补贴形成制造业产能过剩、并以低价冲击美国生产商的商品，报道未说明生效时间，也未见官方确认。

**「影响」** 若实施，相关制造业出口商与美国进口商将面对更高关税成本，幅度因国别而异。

**标签**: `#美国贸易政策`, `#Section 301`, `#关税`, `#中美贸易`, `#全球供应链`

---

<a id="item-finance-news-3"></a>
### [黄仁勋回归英伟达，美中 AI 竞争聚焦人才](https://www.cnbc.com/2026/11/25/jensen-huang-nvidia-ai-talent-race.html) ⭐️ 7.0/10

据 CNBC 报道，黄仁勋在 11 月 12 日辞去英伟达 CEO 后于 11 月 23 日回归；特朗普称自己介入促成了这一回归，并称黄仁勋若离开可能转投中国，但表示从未有迹象显示中方招募过他。卡内基基金会的研究显示，中国在全球 AI 人才中的占比已在三年内超过美国。

rss · CNBC Finance · 11月25日 14:29

**「背景」** 黄仁勋于 11 月 12 日因被报道与一名据称被美国情报部门认为与中国情报有关联的女性有婚外情而辞任，11 月 23 日在特朗普直接介入后复职。

**「受影响群体」** 对中美两地的人工智能工程师来说，直接后果是薪酬被抬高：文中引述的招聘人士称，跳槽通常可带来 25%至 30%的加薪，一家中国 AI 初创公司给一名身在加拿大的 Meta 工程师开出了 140 万元人民币（约合 21 万美元）加股票期权的待遇。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/technology/nvidia-reinstates-jensen-huang-ceo-2026-11-23/">Huang returns as Nvidia CEO after Trump intervention in ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/trump-nvidia-jensen-huang.html">Jensen Huang: Trump sealed deal for Nvidia CEO return - CNBC</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#US-China relations`, `#AI talent`, `#semiconductors`, `#executive leadership`

---

<a id="item-finance-news-4"></a>
### [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为免费提供星链终端](https://x.com/SawyerMerritt/status/2125314062997467640) ⭐️ 7.0/10

SpaceX 已同意放弃 7.38 亿美元美国联邦宽带补贴，改为向符合条件的美国家庭免费提供星链终端设备。据转述，这属于美国国家电信与信息管理局（NTIA）BEAD 计划下的「零支出协议」，即联邦拨付金额为 0 美元；SpaceX 须保证至少 100 Mbps 下载、20 Mbps 上传，提供低价月费套餐，并承诺服务 10 年，以换取大部分财务审计和行政报告义务的豁免。该消息由 Telegram 频道转述一条推文，未提供 NTIA 文件或独立确认。

telegram · zaihuapd · 11月25日 02:17

**「背景」** BEAD 是美国国家电信与信息管理局（NTIA）管理的联邦宽带建设补贴计划，星链则是 SpaceX 旗下的卫星宽带服务。

**「影响」** 对符合条件的美国农村家庭来说，最直接的变化是终端设备免费，但每月仍需支付套餐费，能否省钱取决于月费与原有宽带账单的对比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Starlink">Starlink - Wikipedia</a></li>
<li><a href="https://www.teslarati.com/spacex-starlink-rejects-fed-subsidy/">SpaceX rejects $ 738 M fed subsidy , betting on Starlink alone</a></li>

</ul>
</details>

**标签**: `#telecom policy`, `#BEAD program`, `#SpaceX`, `#Starlink`, `#federal subsidies`

---