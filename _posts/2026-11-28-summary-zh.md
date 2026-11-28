---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 44 条内容中筛选出 16 条重要资讯。

---

**科技新闻**
1. [SemiAnalysis 拆解 Trainium3：DGE 让小消息跑满 HBM 带宽](#item-tech-news-1) ⭐️ 8.0/10
2. [Linux NFS 服务器 nfsd 曝 9.8 分预认证漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [热门购物网站现利用 WebRTC 的信用卡盗刷脚本](#item-tech-news-3) ⭐️ 7.0/10
4. [计算机验证的证明也可能为假](#item-tech-news-4) ⭐️ 7.0/10
5. [多州总检察长起诉 SpaceX 要求阻止 Grok 生成非法性图像](#item-tech-news-5) ⭐️ 7.0/10
6. [让形式化验证进入主流语言](#item-tech-news-6) ⭐️ 7.0/10
7. [Inkling-2-Mini 微调：0.0065% 参数改动将 MITRE 拒答从 100 降至 1](#item-tech-news-7) ⭐️ 7.0/10
8. [AMD RDNA 专用 llama.cpp 补丁称性能提升约 80%](#item-tech-news-8) ⭐️ 7.0/10
9. [talkinghead：169 MB 蒸馏模型实现单张照片实时对口型](#item-tech-news-9) ⭐️ 7.0/10
10. [微软 CEO 承认应届生招聘放缓](#item-tech-news-10) ⭐️ 7.0/10
11. [美情报机构遭 AI 工具 Artex 辅助攻击](#item-tech-news-11) ⭐️ 7.0/10
12. [《我的世界》基岩版资源包漏洞影响 26.52 至 26.63，26.65 已修复](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [标普 500 进入修正区间，较 10 月高点下跌 11.6%](#item-finance-news-1) ⭐️ 7.0/10
2. [国常会提出加力发挥“国家队”稳市作用，优化中央汇金类“平准基金”功能](#item-finance-news-2) ⭐️ 7.0/10
3. [蜜雪冰城 5 亿元入股 DeepSeek 新一轮融资规模约千亿元（未获官方确认）](#item-finance-news-3) ⭐️ 7.0/10
4. [央行将个人大额存单起购门槛降至 10 万元](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [SemiAnalysis 拆解 Trainium3：DGE 让小消息跑满 HBM 带宽](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 8.0/10

SemiAnalysis 发布对 AWS Trainium3 推理性能与微架构的深度分析，并将 Trainium3 与 TPU 一同接入其开源的 InferenceX/UBenchX 基准。按其测试，Trainium3 在 PDS 加 vLLM 软件栈下，于 TCO 对 p90 交互性曲线上除 Nvidia Vera Rubin 外优于其余所有加速器，在按生成 token 成本计的对比中与 GB300 互有胜负。微基准显示，Trainium3 借助描述符生成引擎（DGE，对应 Nvidia TMA 与 AMD MI455X TDM）在小消息尺寸下即可逼近峰值 HBM 带宽利用率，作者称这在 Nvidia GPU 上无法做到。需注意这些数字来自 SemiAnalysis 自有基准，且 AWS Annapurna Labs 联合创始人 Nafea Bshara 与 Trainium 首席架构师 Ron Diamant 团队参与了架构讲解与实验验证，并非独立第三方测量。

rss · Semianalysis · 11月27日 15:54

**「背景」** Trainium 是 AWS 自研的机器学习加速器，由其旗下 Annapurna Labs 团队设计；AWS 工程师此前已在 Annapurna Labs 拆箱首颗 Trainium 3 芯片，说明该芯片已从设计走到实体硅片阶段。SemiAnalysis 的 InferenceX 是一套开源推理基准与数据集，用吞吐—延迟的帕累托前沿曲线比较各加速器在单位总拥有成本（TCO）下的性能，此前已覆盖 TPUv7、Nvidia Rubin NVL72 与 AMD 等平台，本次把 Trainium3 纳入同一套对照框架，因此其“每美元性能”结论才能与英伟达 GPU 直接并置比较。

**「影响」** 对推理成本敏感的团队而言，这意味着 Trainium3 的选型评估应聚焦目标延迟档位下的每 token 成本，而非峰值算力，同时把 vLLM/PDS 软件栈的成熟度纳入验证范围；但由于结论建立在 SemiAnalysis 自有基准与 AWS 协助验证之上，正式采购前仍需用自身智能体（agentic）负载复测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/aws-newsroom_behind-the-scenes-at-annapurna-labs-with-activity-7460753494275436545-5iUa">Unboxing Trainium 3 Chip at Annapurna Labs | AWS ... | LinkedIn</a></li>

</ul>
</details>

**标签**: `#AI hardware`, `#AWS Trainium`, `#microarchitecture`, `#inference`, `#Nvidia GPUs`

---

<a id="item-tech-news-2"></a>
### [Linux NFS 服务器 nfsd 曝 9.8 分预认证漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec 披露 Linux 内核 NFS 服务器 nfsd 的预认证堆溢出漏洞 CVE-2026-99362，CVSS 评分为 9.8；攻击者无需登录，只需发往 tcp/2049 的连接即可越界写入内核堆并获取 root shell。该漏洞自 2014 年 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点，CVE 于 2026 年 11 月 20 日公开。OpenSec 称修复已在 6.12.117、6.18.61、7.3.2 和 7.4-rc1 发布，管理员需升级内核并重启，无法立即升级者可限制 tcp/2049 访问；所给材料未附可直接核对的公告或补丁链接，独立验证仍不充分。

telegram · zaihuapd · 11月27日 12:57

**「背景」** nfsd 是 Linux 内核内的 NFS 服务器，客户端通过 TCP 2049 访问；此次问题出在 NFSv4.1/4.2 的处理路径，因此对外提供这两版 NFS 服务的主机才存在直接暴露面。该缺陷可追溯到 2014 年的 Linux 3.16，OpenSec 的公告和外部报道均将其描述为预认证堆溢出，长期支持发行版也需要确认自身内核是否已包含回填修复。

**「运维影响」** 对可通过网络访问 tcp/2049 且启用 NFSv4.1 或 4.2 的服务器，运维方应升级到 6.12.117、6.18.61、7.3.2 或 7.4-rc1 并重启，否则补丁不会生效；无法立即升级时，应限制对 tcp/2049 的访问。否则，攻击者仅凭一条 TCP 连接就可能越界写入内核堆并取得 root shell。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>
<li><a href="https://www.getpagespeed.com/server-setup/security/nfs2root-cve-2026-99362-centos-7">NFS 2ROOT ( CVE - 2026 - 99362 ) on CentOS 7: Fixed Kernel</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#NFS`, `#CVE-2026-99362`, `#remote root exploit`, `#security patching`

---

<a id="item-tech-news-3"></a>
### [热门购物网站现利用 WebRTC 的信用卡盗刷脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

一份安全报告称，热门购物网站上出现了滥用 WebRTC 的信用卡盗刷脚本，这些脚本借助 WebRTC 通道外传窃取的卡数据，以规避常见检测。受影响的是在这些网站付款的消费者，以及加载第三方 JavaScript 的电商运营方。当前材料只有这一份报告，未提供受影响站点、脚本名称或独立验证结果，因此相关说法仍应视为待核实的厂商信息。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 信用卡盗刷脚本（俗称 Magecart 类攻击）通常指攻击者把恶意 JavaScript 注入电商结账页面，在用户提交订单时窃取卡号等支付信息，并常通过第三方脚本、营销像素或同意横幅等供应链入口植入。据 RH-ISAC 收录的报告，Sansec 研究人员曾在 2026 年 3 月 24 日发现并记录了一款不通过常规网络请求、而用 WebRTC 数据通道加载恶意代码并外传数据的支付盗刷器，目的是绕过传统安全监控。本次事件中，同一手法出现在 Lascana、Samsonite、American Tourister、Revolve 和 FWRD 五家网店，植入途径包括同意横幅设置、营销像素等，且服务端仅在结账页面启用、主要针对移动设备。

**「对电商运营者的直接影响」** 对于依赖 CSP 的 \`connect-src\` 拦截数据外传的电商站点，这一手法表明该指令并不约束 \`RTCPeerConnection\`，而经 DTLS 加密的 UDP 流量对基于 HTTP 的安全监控工具不可见；运营方因此需要盘点并运行时监控分析、客服组件、A/B 测试等第三方脚本的实际行为，而不只是审计自有代码。上述机制描述来自单一厂商相关报告，尚未获得独立验证。

**「社区讨论」** 多名评论者认为，WebRTC 并未提供新的攻击能力，主要问题是它较少被监控；普通 AJAX/HTTP 请求也能完成类似外传，真正的风险来自第三方脚本和站点自身防护不足。另有评论者把问题归因于浏览器执行远程代码、支付仍使用对称密钥等更基础的设计，并有人据此为广告拦截辩护。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/credit-card-skimming-scripts-using-webrtc-found-on-popular-shopping-sites-mr8zgdbaf">Credit card skimming scripts using WebRTC found on...</a></li>
<li><a href="https://rhisac.org/threat-intelligence/webrtc-based-payment-skimmer-targeting-ecommerce-sites-via-polyshell-vulnerability/">RH-ISAC | WebRTC-Based Payment Skimmer Targeting ECommerce ...</a></li>
<li><a href="https://vibewshield.com/news/webrtc-skimmer-bypasses-csp-steal-payment-data">WebRTC Skimmer Bypasses CSP to Steal Payment ... | VibeWShield</a></li>
<li><a href="https://rfxn.com/research/webrtc-skimmer-csp-bypass">WebRTC Skimmers : How Payment Thieves Bypass... | R-fx Networks</a></li>
<li><a href="https://informatecdigital.com/en/A-skimmer-using-WebRTC-that-evades-controls-and-steals-data-in-e-commerce./">WebRTC skimmer that bypasses security controls in e - commerce</a></li>

</ul>
</details>

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-4"></a>
### [计算机验证的证明也可能为假](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

一篇题为《False computer-checked proofs》的页面主张，计算机检查过的证明也可能为假，由此引出形式验证社区对证明检查器健全性（soundness）漏洞和多重验证的讨论。由于源页面正文未提供，无法核对其具体论证和案例；评论者承认 Lean、Metamath 等系统确实出现过健全性漏洞，但强调实际接受证明通常不只依赖单一检查器。Metamath 主数据库 set.mm 和 iset.mm 要求证明通过 5 个独立实现、不同编程语言的验证器，Lean 社区也把检查器可靠性视为持续投入的问题。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 所谓“计算机检验的证明”，是指 Lean 4、Metamath 等系统用一个尽量小的可信内核逐条检查证明项；一旦内核本身存在可靠性（soundness）缺陷，错误命题的“证明”也可能通过检查。8 月 1 日发布的 Lean 内核 soundness bug \#14576 复盘记录了一个具体先例：nanoda 的同类缺陷由 Jeremy Chen 报告，并在 Lean 的缺陷被报告前一周修复，而那份构造出来的证明特意让内核从不检查的表达式恰好落在旧版 nanoda 可接受的范围内。同一复盘还说明，Lean 4 内核曾因嵌套归纳的 phantom 参数缺陷而接受了对 False 的证明。

**「影响」** 对依赖 Lean 或 Metamath 的用户和开发者来说，具体影响是接受证明时应把多个独立实现的检查器作为防线，而不是把单次检查通过当作绝对保证；Metamath 主库已用 5 个独立验证器落实这一点，而 Lean 场景下仍需关注检查器本身的健全性漏洞。

**「社区讨论」** 评论者 twotwotwo 和 dwheeler 认为该页面没有体现从一次错误验证到成功误导数学界的差距：必须同时利用多个独立检查器的漏洞，且证明在非形式审查中还不能显得可疑；dwheeler 以 Metamath 主库要求 5 个独立验证器为例。gr\_norm 认为这些检查器积累的健全性漏洞数量很少，对绝大多数软件足够，andai 则提醒证明可能只是验证了对需求的错误理解。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://leodemoura.github.io/blog/2026-8-1-postmortem-for-kernel-soundness-bug-14576/">Postmortem for Kernel Soundness Bug #14576 — Leonardo de Moura</a></li>
<li><a href="https://essamamdani.com/blog/lean-4-soundness-bug-14576-postmortem">Lean 4 Soundness Bug #14576: What Broke the Kernel</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#soundness`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-5"></a>
### [多州总检察长起诉 SpaceX 要求阻止 Grok 生成非法性图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

弗吉尼亚州总检察长杰伊·琼斯与雷菲尔德两名州总检察长对 SpaceX 提起诉讼，要求法院阻止该公司旗下的 xAI/Grok 生成儿童性虐待材料以及未经同意的私密图像。诉讼把这类内容的“创建和推广”归责于 SpaceX，但当前公开材料仅为总检察长办公室的新闻稿，尚未提供诉状全文、具体指控细节或独立核实的技术证据。案件针对的是平台和模型提供方的责任，相关指控仍须在法庭上证明。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** 这起诉讼把生成式图像滥用纳入州消费者保护法框架，而不是依据专门的 AI 新法。据 CNBC 和《纽约时报》11 月 23 日报道，俄勒冈州和弗吉尼亚州总检察长指控 SpaceX 通过 Grok Imagine 生成性化图像，违反州消费者保护法。

**「平台责任与功能限制」** 对在 X 上使用 Grok 图像生成的用户和开发者而言，弗吉尼亚州和俄勒冈州已分别提起消费者保护诉讼，指控 SpaceX 未设置足够防护便允许生成儿童性虐待材料和非自愿性化图像；这意味着该功能的内容过滤和账号风控将直接接受法庭审查，平台需要应诉，并可能据此调整相关生成能力。

**「社区讨论」** 有评论者质疑，此类内容此前已在多数平台被禁止，为何 Grok 仍能生成，并追问用户是否需要“诱导”模型才会出现这些输出；另一名评论者则追问应如何追究实际生成者本人的责任。还有评论者称，使用 Grok 需要关联并交出 X/Twitter 账号，因此不愿为试用模型冒此风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/23/oregon-virginia-spacex-grok-deepfake-lawsuits.html">SpaceX sued by 2 states over AI deepfake porn, Grok safety claims</a></li>
<li><a href="https://www.nytimes.com/2026/11/23/technology/spacex-lawsuit-ai-sexualized-images.html">SpaceX Sued By Oregon and Virginia Over A.I.-Generated...</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/spacex-faces-lawsuits-two-states-162425330.html">SpaceX Faces Lawsuits From Two States Over Grok AI Safety Failures</a></li>
<li><a href="https://www.engadget.com/2325111/two-states-sue-spacex-over-sexually-explicit-grok-deepfakes/">Two States Sue SpaceX Over Sexually Explicit Grok Deepfakes</a></li>

</ul>
</details>

**标签**: `#AI regulation`, `#AI safety`, `#Grok`, `#content moderation`, `#platform liability`

---

<a id="item-tech-news-6"></a>
### [让形式化验证进入主流语言](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

Blaine Hansen 的评论文章主张，应设计一种让形式化验证成为常规开发流程一部分的主流编程语言，而不是只服务于少数专家的专用工具；文章本身没有发布新语言、编译器或可下载实现，属于观点性提案。Hacker News 的讨论把这一主张与已有的 Dafny、Ada/SPARK、Why3、Verus、Frama-C 和 TLA+ 等工具对照，并讨论大语言模型能否降低这些工具的使用门槛。多位评论者更关注采用路径，而不是从零设计一种“主流”语言，认为主流地位来自实际采用。

hackernews · todsacerdoti · 11月27日 05:22 · [社区讨论](https://news.ycombinator.com/item?id=50663089)

**「背景：既有验证工具」** 形式化验证工具并不新鲜，但长期分散在特定语言与验证风格中：Dafny、SPARK Ada、Verus、Frama-C、TLA+ 各有各的输入语言和验证方式。据 Why3 项目文档与其 2026 年 4 月的介绍文章，Frama-C WP、SPARK Ada 的 GNATprove、EasyCrypt 与 Creusot 等工具共享 INRIA Saclay 的 Why3 证明管理后端，用户还需自行安装 Alt-Ergo、CVC4、Z3 等求解器才能完成证明义务。这意味着要在主流语言中获得类似保障，通常得先跨过工具链拼接与求解器配置的门槛。

**「对开发者的实际影响」** 对现在就想引入形式化验证的团队来说，更可行的做法是在已有工具链上借助 LLM 降低门槛：arXiv 在 2026 年 11 月给出的十步工作流，把算法形式化、契约编写、不变式经验验证与证明构建串成可复用的流程（Dafny 为例）。这也意味着实际门槛落在迁移成本与工具链成熟度上；评论者 porcoda 认为“主流”来自采用而非立项设定，新语言需要先回答 Dafny、SPARK、Verus 等为何未能普及。

**「社区讨论」** 有评论者报告用 Ada/SPARK 将现有 C 代码迁移并提升到 SPARK Silver（无运行时错误）后发现了整数溢出等边界问题，并认为 LLM 辅助使形式化方法更易用；也有评论者指出 Dafny、SPARK、Why3、Verus、Frama-C、TLA+ 已覆盖不同验证风格，质疑能否以“主流”为目标从零设计语言，认为主流性只能由采用产生。另有开发者介绍其 Zena 语言正尝试面向 Wasm GC 和 AI 生成代码的沙箱化，但这是个人项目陈述，并非已验证的行业结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://why3.org/">Why3</a></li>
<li><a href="https://sota.io/blog/why3-eu-formal-verification-framework-inria-saclay">Why3: EU-Native Proof Framework — Frama-C, SPARK Ada ...</a></li>
<li><a href="https://arxiv.org/abs/2611.16886">[2611.16886] LLM-Assisted Verification in Dafny - arXiv.org</a></li>
<li><a href="https://arxiv.org/pdf/2611.16886v1">LLM-Assisted Verification in Dafny - arXiv.org</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#programming languages`, `#Ada SPARK`, `#LLM-assisted verification`, `#software correctness`

---

<a id="item-tech-news-7"></a>
### [Inkling-2-Mini 微调：0.0065% 参数改动将 MITRE 拒答从 100 降至 1](https://i.redd.it/84pq0qkkr14i1.png) ⭐️ 7.0/10

一位 Reddit 作者发布了 Inkling-2-Mini 的网络安全微调版 GGUF（Hugging Face 仓库 sergiogmn/Inkling-2-Mini-Cyber-GGUF），目标用户是从事授权安全研究、红队工程和 CTI 工作流的本地模型使用者。作者称只训练了作用于 layers 4–23 的 self\_attn.o\_proj 的 rank-16 LoRA（alpha=32），涉及 20/704 个张量、1.72M 参数，占总参数 0.0065%，用 555 行数据在单张 A100-80GB 上约 49 分钟完成。适配器通过 NumPy 脚本拼接到 20 个 Q8\_0 attn\_output.weight（scale 1.55），其余 684 个张量和 128 个 MoE 专家逐字节复制；仓库提供 IQ4\_NL 17.63 GB、Q6\_K 24.70 GB、Q8\_0 27.82 GB 量化及 6.89 MB BF16 PEFT adapter，可在原生 llama.cpp、Ollama 和 LM Studio 中运行。作者自报 IQ4\_NL 上 CyberSecEval MITRE-120 拒答从 100 降至 1（完全回答 68.3%、完全+部分 75.8% @4K，原模型为 0%/0.8%），CTIBench CVE→CWE-100 为 66.0%，并称超过 Qwen3.8-27B；这些结果尚未独立验证，来源中的原模型 CVE→CWE 对比数值也被截断。

reddit · r/LocalLLaMA · GodGMN · 11月27日 00:16 · [社区讨论](https://www.reddit.com/r/LocalLLaMA/comments/1y6flvh/inkling2minicyber_surgical_00065_weight_edit_for/)

**「背景」** Inkling-2-Mini 是 Thinking Machines Lab 于 2026 年 11 月 20 日发布的开源权重图像-文本模型，参数量 26B，定位本地推理；Horizon 11 月 21 日日报曾报道，据社区评论其 GGUF 版本可通过 Ollama 或 llama.cpp 运行，但当时的基准对比尚未得到独立验证。与那次发布相比，当前变化是社区作者在同一基座权重上做 rank-16 LoRA 修改并发布拼接后的 GGUF，而不是官方推出新版本。

**「对本地部署的影响」** 最直接的后果是本地部署门槛与可用性发生变化：按作者自报数据，MITRE-120 拒答从 100 降至 1，且量化权重可直接在原生 llama.cpp、Ollama 和 LM Studio 中加载，无需自定义 hook；CyberSecEval 的拒答测试衡量的正是对边缘但良性请求的误拒率，因此这一变化对应的是过度拒答减少，而非模型能力提升。代价在资源与自行拼接上：IQ4\_NL 需要约 24 GB 显存，Q6\_K、Q8\_0 体积分别为 24.70 GB 和 27.82 GB，若要把 6.89 MB 的 adapter 移植到其他量化，需使用作者提供的 NumPy 拼接脚本并以 --scale 1.55 应用。上述数字均由作者自建评测与 Qwen3Guard 判分、尚无独立复现，同时拒答率大幅下降本身意味着相关安全对齐被移除，只应在授权范围内使用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>
<li><a href="https://huggingface.co/thinkingmachines/Inkling-2-Mini">thinkingmachines/Inkling-2-Mini · Hugging Face</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://meta-llama.github.io/PurpleLlama/CyberSecEval/docs/intro">Introduction | CyberSecEval 4</a></li>

</ul>
</details>

**标签**: `#local LLM`, `#LoRA fine-tuning`, `#cybersecurity`, `#GGUF`, `#llama.cpp`

---

<a id="item-tech-news-8"></a>
### [AMD RDNA 专用 llama.cpp 补丁称性能提升约 80%](https://devnull.land/amd-specific-llama-cpp) ⭐️ 7.0/10

一份面向 AMD RDNA 显卡的 llama.cpp 最小补丁（llama-cpp-rdna-boosts）在社区测试中报告，R9700 上运行 Q6\_K\_L Swift-1.5-Qwen3.8-27B 时，预填充从 700 tps 提升到 1300 tps，解码从 35 tps 提升到 55 tps；写称相对未打补丁的基础 llama.cpp 约有 80% 的提升。该补丁可应用到固定版本的 llama.cpp 构建，并保留其对多种模型的广泛兼容性。上述数据来自单一硬件的社区实测，分享者本人尚未在 R9700 上验证，也未见独立复测；报告同时称专用推理引擎仍有小幅优势。

reddit · r/LocalLLaMA · returnity · 11月27日 20:38 · [社区讨论](https://www.reddit.com/r/LocalLLaMA/comments/1y73gcc/amdspecific_llamacpp_patch_nearly_doubles/)

**「背景」** llama.cpp 是兼容性极广的开源推理引擎，几乎支持所有常见模型格式；相比之下，Strata、Splash、Basalt、Halogen、Gufo 等专用推理引擎只在特定模型和特定硬件上有性能优势。这次被分享的 llama-cpp-rdna-boosts 是一个可打在固定版本 llama.cpp 构建上的小型补丁，专门针对 AMD RDNA 显卡调优，因此其约 80% 的提升尚未进入上游代码，使用者需要自己在已锁定的构建版本上应用补丁，并自行承担兼容性与维护成本。

**「对使用者的实际影响」** 对希望保留 llama.cpp 广泛模型兼容性的 AMD RDNA 用户来说，这个补丁不是直接合并进主线的功能，而是需要按固定提交重新套用的改动：仓库说明补丁基于干净的 llama.cpp 检出点 9cffdcc80（2026-09-02 从 0eadefebd 变基），因此每次跟进上游版本都要重新变基并自行验证。约 80% 的提升来自单张 R9700、Q6\_K\_L 量化的 Qwen3.8-27B 这一组社区测试，尚未经独立复现，其他 RDNA 型号和量化格式的实际收益仍需用户自行测量后再决定是否采用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/stew675/llama-cpp-rdna-boosts">GitHub - stew 675 / llama - cpp - rdna - boosts · GitHub</a></li>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD-specific fork of llama . cpp | devnull.land</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#AMD RDNA`, `#LLM inference`, `#performance optimization`, `#local AI`

---

<a id="item-tech-news-9"></a>
### [talkinghead：169 MB 蒸馏模型实现单张照片实时对口型](https://v.redd.it/affuqdkfw64i1) ⭐️ 7.0/10

开发者发布了 talkinghead：一个 169 MB 的蒸馏模型，从蚂蚁集团 Ditto 约 2.2 GB 的检查点压缩而来，输入一张照片和 TTS 音频即可输出唇形同步的视频。它通过 Core ML 在 M4 Pro 上达到 36.5 ms/帧，在 M3 Pro 上为 38–40 ms/帧，而 25 fps 视频的实时门槛是 40 ms/帧；一台 4 GB 显存的 RTX 3050 Ti 笔记本用 TensorRT 跑到 40.3 ms/帧，略慢于实时。在 M4 Pro 上，8.5 秒音频端到端约需 7.4 秒，调用方式是 \`Avatar\(&quot;photo.jpg&quot;\).speak\(&quot;tts\_output.wav&quot;, &quot;out.mp4&quot;\)\` 这样的几行 Python。代码以 Apache-2.0 发布在 GitHub，权重在 HuggingFace，另有一个 WebGPU 浏览器演示但并非实时。作者明确列出限制：目前只按实时速度渲染文件，尚不能直播，因为帧是批处理的，会额外增加约 120 ms 延迟；口型同步质量弱于 LatentSync（按 SyncNet 评测），换来的是约 13 倍的单帧时间缩减和约 12 倍的显存缩减（数据来自早期构建，README 标注了每个数字对应的构建版本）；M1/M2 和 Linux 尚未测试。

reddit · r/LocalLLaMA · Affectionate\_Hat\_585 · 11月27日 17:25 · [社区讨论](https://www.reddit.com/r/LocalLLaMA/comments/1y6yv05/169_mb_face_for_your_local_voice_assistant_one/)

**「背景」** 用一张照片加一段 TTS 音频生成对口型说话视频，属于音频驱动的人脸合成任务：模型必须逐帧生成口型与面部动作，算力和显存开销通常都很大。作者称这个 169 MB 的模型蒸馏自蚂蚁集团的 Ditto，后者的 checkpoint 约 2.2 GB，蒸馏把体积压到足以在本地设备上运行。类似能力目前多以云端服务形式提供，例如基于 OmniHuman 1.5 的在线「照片开口说话」工具，用户需上传照片与脚本。

**「影响」** 对在本地运行 LLM 与 TTS 的用户来说，这意味着无需服务器即可让语音助手拥有一张会说话的脸，且只需一张照片和 169 MB 权重；但由于批处理带来约 120 ms 延迟，它更适合离线生成短视频而非实时对话画面。打算在 M1/M2 或 Linux 上使用的人目前没有官方验证，作者建议先运行 \`device\_report\(\)\` 查看自己设备上的每帧耗时。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fliki.ai/features/talking-photo">Free AI Talking Photo: Make Any Photo Talk Online</a></li>

</ul>
</details>

**标签**: `#local-ai`, `#lip-sync`, `#tts`, `#model-distillation`, `#coreml`

---

<a id="item-tech-news-10"></a>
### [微软 CEO 承认应届生招聘放缓](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

微软 CEO 纳德拉在《The Pragmatic Engineer》播客中承认，应届生招聘已经放缓：微软会先把现有员工调配到合适岗位，再补招新人；他还称 AI 原生公司会“先用完 AI 预算，再招下一个人类”，并认为未来每家公司都会如此。截至 6 月 30 日，微软员工数为 22.3 万，一年减少 5000 人，为 2016 年以来首次年度下滑。麻省理工学院与微软研究院的论文显示，采用 GitHub Copilot 的企业季度技术岗招聘减少 29%，初级岗位受影响最大。

telegram · zaihuapd · 11月27日 03:03

**「背景」** 今年年初，纳德拉在达沃斯还表示仍相信校园招聘；这一立场与他在播客中承认应届生招聘放缓形成对照。近期一项利用 GitHub Copilot 在 5,414 家跨国公司推广作为自然实验的 MIT 与微软研究院论文给出了相关证据：采用一年后，季度技术岗位招聘下降 29%，初级软件工程师招聘下降约 40%，而资深工程师招聘基本持平。

**「对应届生与初级岗位的影响」** 对应届毕业生而言，直接后果是入门级招聘名额收紧：纳德拉描述的顺序是先调配现有员工、再补招新人，而报道引用的 MIT 与微软研究院论文称，采用 GitHub Copilot 的企业季度技术岗招聘减少 29%，初级岗位受影响最大。计划走校园招聘的人应预期名额更少、竞争更集中在能展示 AI 协作与判断力的项目经历上；需注意该论文结论是采用情况与招聘下降之间的关联，并非因果预测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://economics.mit.edu/sites/default/files/2026-11/AILaborDemand_06Nov2026.pdf">AI-Assisted Programming and Labor Demand - economics.mit.edu</a></li>
<li><a href="https://todayforai.com/en/items/art-b0db345b-a86">MIT and Microsoft Study Finds Copilot Cuts Junior Coder ...</a></li>

</ul>
</details>

**标签**: `#AI and jobs`, `#Microsoft`, `#GitHub Copilot`, `#tech hiring`, `#labor market`

---

<a id="item-tech-news-11"></a>
### [美情报机构遭 AI 工具 Artex 辅助攻击](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

据《纽约时报》报道，美国中央情报局、国家地理空间情报局和国家情报总监办公室遭到黑客攻击，攻击过程中使用了 AI 工具 Artex；报道称此次攻击看起来并不严重，受影响的是非机密侦察数据。Artex 可整合多个开源 AI 模型来测试网络和计算机防御，由一名中国开发者于今年早些时候发布，后来被用于多起攻击，包括针对欧盟的一起，该开发者已将其从 GitHub 账号删除。报道还提到，FBI 今年早些时候曾警告网络罪犯和间谍正在广泛使用 Artex；上述说法来自媒体转述，尚缺技术细节与官方确认。

telegram · zaihuapd · 11月27日 10:42

**「背景」** 据 BleepingComputer 报道，FBI 此前警告称，名为 ARTEX 的 AI 渗透测试框架可自动执行网络攻击，并已被用于 ConnectWise 供应链攻击等事件。另据 kursiv.media 报道，该工具最初由使用中文账号名 Autumn-27 的开发者发布，在发现被广泛滥用后于 10 月将主仓库从 GitHub 删除。

**「影响」** 若报道属实，相关机构在评估风险时需把可整合多个开源模型的公开工具纳入攻击面，并重点检查非机密侦察数据的暴露情况；报道只称非机密侦察数据受到影响，未提及机密系统或数据受损。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/fbi-warns-artex-ai-hacking-tool-is-powering-global-cyberattacks/">FBI warns ARTEX AI hacking tool is powering global cyberattacks</a></li>
<li><a href="https://kz.kursiv.media/en/2026-11-27/engk-yeri-ai-hacking-tool-artex-spreads-globally-despite-creators-takedown/">FBI warns of AI hacking tool ARTEX as open-source copies proliferate</a></li>

</ul>
</details>

**标签**: `#AI cybersecurity`, `#cyberattacks`, `#US intelligence`, `#open-source AI`, `#Artex`

---

<a id="item-tech-news-12"></a>
### [《我的世界》基岩版资源包漏洞影响 26.52 至 26.63，26.65 已修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

《我的世界》基岩版被披露存在资源包漏洞：含有 content.zipe 文件的资源包可改动 Ore UI 界面框架文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版本，更早版本也可能受影响，覆盖 PC、手机和主机，Java 版不受影响。Mojang 已在 26.65 版修复；当玩家加入服务器或 Realm 并开启资源包自动下载时，可能无需手动安装就收到问题文件。

telegram · zaihuapd · 11月27日 18:04

**「背景」** 资源包可用于替换游戏材质和界面，服务器或 Realm 可让客户端自动下载资源包。此次问题在于 content.zipe 能覆盖基岩版 Ore UI 界面框架文件并执行隐藏脚本，从而绕过正常的手动安装步骤。

**「影响与应对」** 使用 26.52 至 26.63 的玩家应升级到 26.65；在仍启用自动下载的旧版本上加入不受信任的服务器或 Realm，仍可能触发删除全部存档、获取玩家 IP，以及在 Windows 上无提示打开任意 URI 或启动资源包内批处理文件等行为。AxmBro 发布的 Windows 只读检测工具可查找 content.zipe，但不能判断资源包是否恶意。

**标签**: `#Minecraft`, `#安全漏洞`, `#资源包`, `#基岩版`, `#补丁修复`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [标普 500 进入修正区间，较 10 月高点下跌 11.6%](https://www.cnbc.com/2026/11/27/the-sp-500-is-in-a-correction-bear-markets-and-recessions-dont-always-follow.html) ⭐️ 7.0/10

标普 500 指数 11 月 20 日下跌 3.7%，收于 6,910.39 点，自 2025 年 4 月以来首次进入修正区间；该指数较 10 月 6 日收盘纪录高点 7,818.93 点低 11.6%。投资者担忧 AI 支出放缓、大型科技股估值和美联储利率路径。

rss · CNBC Finance · 11月27日 13:21

**「背景」** 修正指较近期高点下跌至少 10%，跌幅达到 20%则视为熊市；CNBC 分析称，13 次标普 500 熊市中有 8 次与美国国家经济研究局（NBER）定义的经济衰退重叠，5 次没有。德意志银行策略师 Henry Allen 认为，1962 年以来每次标普 500 熊市都至少伴随衰退、经济数据恶化或美联储加息周期之一，而当前至少到目前为止尚无这些条件，这属于其个人判断。

**标签**: `#S&amp;P 500`, `#stock market correction`, `#recession risk`, `#Federal Reserve policy`, `#bear market history`

---

<a id="item-finance-news-2"></a>
### [国常会提出加力发挥“国家队”稳市作用，优化中央汇金类“平准基金”功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

国务院总理李强 11 月 27 日主持召开国务院常务会议，提出持续完善资本市场稳市机制、实施好存量政策并谋划出台增量政策，要求加力发挥“国家队”稳市作用、进一步优化中央汇金公司的类“平准基金”功能并提供充足流动性保障。会议还要求推动上市公司加大分红回购、完善保险和企业年金、社保基金等中长期资金入市支持政策，并强化全链条监管、查处财务造假和违规减持；此次通稿未给出具体资金规模、措施细则或时间表，属政策方向性部署。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 中央汇金公司被会议列为“国家队”稳市力量之一；所谓类“平准基金”，指在市场异常波动时通过逆向操作提供流动性、以稳定市场的资金安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>

</ul>
</details>

**标签**: `#China capital markets`, `#State Council policy`, `#market stabilization`, `#Central Huijin`, `#long-term capital`

---

<a id="item-finance-news-3"></a>
### [蜜雪冰城 5 亿元入股 DeepSeek 新一轮融资规模约千亿元（未获官方确认）](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

据搜狐网转述的二级报道，DeepSeek 已完成第二轮融资，募资规模约 1000 亿至 1055 亿元人民币，投后估值约 6155 亿元；新增 31 家出资人包括腾讯、宁德时代、中国移动和 vivo，蜜雪冰城股份有限公司认缴 5 亿元，这笔资金通过砺思资本管理的天津砺思星深基金投入。该报道未获 DeepSeek 或蜜雪方面官方确认。

telegram · zaihuapd · 11月27日 06:33

**「背景」** 据《The Information》报道，DeepSeek 今年 6 月已完成约 510 亿元人民币的首轮融资，此后的第二轮融资目标曾多次调整：最初设为 500 亿元，随后上调至约 1000 亿元。此次募资规模和出资人名单均来自二手报道，尚无 DeepSeek 或投资方的官方确认。

**「影响」** 若该报道属实，蜜雪冰城持有的是砺思星深基金的份额，而非 DeepSeek 直接股权，其风险敞口与这只由砺思资本管理、备案募资 26.4 亿元后扩至 75.2 亿元关账的盲池基金挂钩；相较蜜雪 2025 年 335.6 亿元营收和约 58.9 亿元归母净利，这 5 亿元认缴额占比有限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/020/251.htm">曝 DeepSeek 第二轮 融 资 1055 亿 元 ： 估 值 6155 亿 元 ， vivo ...</a></li>

</ul>
</details>

**标签**: `#DeepSeek financing`, `#AI investment`, `#Mixue Group`, `#China private markets`, `#unconfirmed report`

---

<a id="item-finance-news-4"></a>
### [央行将个人大额存单起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购大额存单的起点从 20 万元下调至不低于 10 万元，机构起点从 1000 万元降至不低于 500 万元，自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 大额存单是银行面向个人和机构发行的大额存款凭证，现行认购门槛由 2015 年《大额存单管理暂行办法》确定，个人为 20 万元、机构为 1000 万元，新办法将两项门槛同时减半；据《工人日报》报道，修订后的办法还要求大额存单各业务环节的定价符合央行计结息规则并纳入自律管理。

**「影响」** 门槛下调后，可动用资金达到 10 万元但不足 20 万元的个人将符合认购条件，500 万元至 1000 万元的机构资金也被纳入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.workercn.cn/papers/grrb/2026/06/15/4/grrb202606154.pdf">grrb0420260615C</a></li>

</ul>
</details>

**标签**: `#China banking regulation`, `#PBOC`, `#large-denomination CDs`, `#deposit rates`, `#retail savings`

---