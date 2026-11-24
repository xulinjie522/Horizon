---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 50 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [Ladybird 独立浏览器引擎发布首个 alpha](#item-tech-news-1) ⭐️ 8.0/10
2. [智谱发布 GLM-5.4：首个循环 Transformer 架构，主打通用编程](#item-tech-news-2) ⭐️ 8.0/10
3. [英伟达董事会恢复黄仁勋 CEO 职位，称已听取美国政府高层意见](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic 仓库宣称 Lean 证明 VP≠VNP 对所有域成立](#item-tech-news-4) ⭐️ 8.0/10
5. [应 Arm 要求，非官方 Arm 文档站将于 12 月 4 日停站](#item-tech-news-5) ⭐️ 7.0/10
6. [谷歌搭建 Mirror Dimension 模拟网测试 Chrome AI 代理](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](#item-tech-news-7) ⭐️ 7.0/10
8. [Codex2api 疑遭供应链投毒，恶意版本窃取密钥](#item-tech-news-8) ⭐️ 7.0/10
9. [Meta AI 负责人称超级智能临近，黎曼猜想证明待复核](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [据报 Anthropic IPO 后 AI 股遭抛售，DeepSeek 等中国 AI 公司上市计划蒙上阴影](#item-finance-news-1) ⭐️ 8.0/10
2. [上海地铁公布 21 年来首次票价调整](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 独立浏览器引擎发布首个 alpha](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird 这个独立开源浏览器引擎发布了首个 alpha 版本，macOS 和 Linux 用户现在可以直接下载安装，无需自行编译。它自行实现 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 等核心部件，仅复用 HarfBuzz、Skia、ffmpeg 和 SQLite 等外部组件，并按标签页分进程隔离；项目称 10 月新增 75,650 个 web-platform-tests 子测试通过，超过 Safari。项目方明确这是 alpha：部分网站无法使用，浏览器有时会崩溃，并鼓励用户从浏览器内报告问题站点和选择是否发送崩溃报告。据原文作者测试，ffmpeg 编译的 WebAssembly 视频工具和 Pyodide REPL 可运行，但依赖 service worker/web worker 组合的 Datasette Lite 因缺少 navigator.serviceWorker.startMessages 而报错。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 源自 Andreas Kling 发起的 SerenityOS 项目，长期坚持自行实现 HTML 解析、CSS 引擎、布局和 JavaScript 等核心部件，而不是基于 Chromium 或 Gecko 分叉。项目在 2026 年 2 月发布《Ladybird adopts Rust, with help from AI》，用 Claude Code 和 Codex 在两周内把 LibJS 的部分组件从 C++ 迁移为约 2.5 万行 Rust；随后 10 月的月度通讯记录了将样式与布局移入独立线程、启用新的 JavaScript JIT、替换 WebAssembly 引擎，以及在约 225 万项 web-platform-tests 子测试中单月新增 75,650 项通过的成绩。

**「影响」** 对开发者和早期用户而言，现在可以直接在 macOS/Linux 上安装并测试，无需自行编译；但项目方明确这是 alpha，部分网站不工作且会崩溃，因此更适合兼容性验证和提交缺陷，而不是依赖它完成关键任务。

**「社区讨论」** 有评论者称，新闻站点、Proxmox/NoVNC 甚至 YouTube 和 Google Maps 都能正常打开，NoVNC 在 Ladybird 中甚至比 Firefox 更流畅，但也有人指出页面滚动略有卡顿。另一位评论者认为，改用 SQLite、Skia 等成熟组件显著提升了可用性，不过也怀念 SerenityOS 时期自研大量组件的黑客精神。

**标签**: `#Ladybird`, `#browser engines`, `#open source`, `#alpha release`, `#web standards`

---

<a id="item-tech-news-2"></a>
### [智谱发布 GLM-5.4：首个循环 Transformer 架构，主打通用编程](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

智谱发布 GLM-5.4，这是一款主打「通用编程」（generalized coding）的模型，官方称其首次采用循环 Transformer（loop transformer）架构；其中「首次」和「通用编程」两项说法均来自厂商，尚未获得独立验证。社区成员把循环 Transformer 解释为让同一组权重在推理时重复计算，以缓解每生成一个 token 都要把整层权重从 HBM 搬入芯片所带来的内存带宽瓶颈。可用性方面，Simon Willison 报告称该模型无法通过 OpenRouter 或常规 Z.ai API 套餐调用，需要改用 Coding Plan；其 API key 与普通 key 用法相同，但可访问新模型。

hackernews · r/LocalLLaMA · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 循环 Transformer（Looped Transformer）的核心做法是让同一组共享层在推理时重复执行多次，以额外计算换取更深的推理步数，而不是按层数线性增加参数。GLM-5.4 采用这一思路：Z.ai 称其 78 层中有 28 层执行两遍，并声称可达到 2T–3T 参数模型的推理水平。Horizon 11 月 21 日的日报曾报道另一款采用循环架构的开源权重模型 Inkling 2 Mini，并提到团队称循环可提升推理、但不会增加存储的事实知识，事实性仍取决于参数规模。

**「接入渠道尚未打通」** 希望接入 GLM-5.4 的开发者目前需要绕道：截至 2026 年 11 月 23 日 08:47 UTC，OpenRouter 的公开目录仍只列出 GLM-5.3，没有 GLM-5.4 条目，因此已经接入 OpenRouter 的应用需改走其他渠道或单独转发该模型的请求。GLM-5.4 被纳入 Z.ai 的 Coding Plan，每周额度为 GLM-5.3 的 1.5 倍并支持视觉输入，使用标准 API 套餐的团队需评估是否改订该套餐。

**「社区讨论」** 有评论者赞赏智谱公开了较多技术细节，认为这与西方公司的封闭做法形成反差，并称循环 Transformer 是 SOTA 模型的明显演进方向。另一些用户则抱怨这类中国模型存在「马拉松式思考」：即便面对概念上很简单的任务也会反复自我怀疑，完成时间远高于前沿模型；Simon Willison 用同一提示生成的对比图显示，GLM-5.4 与 GLM-5.3 的输出看起来颇为相似。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://anyrouter.dev/model/z-ai/glm-5.4">GLM - 5 . 4 · Zhipu AI · pricing &amp; API · AnyRouter</a></li>
<li><a href="https://www.youtube.com/watch?v=HVey00YZ5Xk">GLM - 5 . 4 Is Here: The First Loop Transformer , and What... - YouTube</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>
<li><a href="https://aihubmix.com/blog/glm-5-4-api-access-should-you-wait-for-openrouter">GLM-5.4 API Access: Should You Wait for OpenRouter?</a></li>
<li><a href="https://explainx.ai/blog/glm-5-4-coding-plan-vision-50-percent-quota-boost-november-2026">GLM-5.4 Coding Plan: +50% Quota, Vision (Nov 2026 ...</a></li>

</ul>
</details>

**标签**: `#GLM-5.4`, `#Looped Transformers`, `#LLM architecture`, `#coding models`, `#Zhipu AI`

---

<a id="item-tech-news-3"></a>
### [英伟达董事会恢复黄仁勋 CEO 职位，称已听取美国政府高层意见](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 8.0/10

英伟达董事会恢复了黄仁勋（Jensen Huang）的 CEO 职位。公司在声明中表示，董事会在作出决定过程中听取了美国政府高层的意见，并据此确信黄的复职不构成国家安全风险。所提供的材料主要是公司公告链接和新闻标题，因此他被免职的原因、此次反转的具体时间以及复职附带的条件，均无法从现有内容中得到确认。有评论者称，这一决定距董事会迫使他离职不到两周，并提到司法部表示不予起诉；这些说法来自评论，而非已核实的事实。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「背景」** 据 CNBC 报道，黄仁勋于 11 月 13 日辞去 Nvidia CEO 一职，距董事会 11 月 23 日宣布其复职不到两周。Nvidia 的官方新闻稿称，此次复职立即生效，黄仁勋重新担任总裁、CEO，并恢复董事席位。

**「影响」** 董事会在公告中把复职与“美国政府高层意见”和“不构成国家安全风险”的判断直接挂钩，这意味着 CEO 人选的确立过程明确引入了政府审查因素，而不只是常规的公司治理程序。对英伟达的客户、合作伙伴和投资者而言，这种安排使公司最高管理层与 AI 芯片出口政策辩论的走向更加紧密地绑定在一起，相关决策的可预期性也随之降低。

**「社区讨论」** 多位评论者把声明中“董事会听取了美国政府高层意见”一句视为整份声明的关键，认为它说明政府介入了此次人事决定。也有人提出相反看法，认为目前流出的信息并未显示存在实质证据，并指出董事会在不到两周内从迫使黄仁勋离职转为一致同意其复职，沟通方式造成了不必要的动荡；还有评论者批评美国在要求 ASML 和日本芯片企业遵守对华限制的同时，却对英伟达另作处理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html">Jensen Huang reinstated as Nvidia CEO. Stock skyrockets 31%</a></li>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director">NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI hardware`, `#semiconductor policy`, `#corporate governance`, `#US export controls`

---

<a id="item-tech-news-4"></a>
### [Anthropic 仓库宣称 Lean 证明 VP≠VNP 对所有域成立](https://github.com/anthropics/formal-math/tree/main/vp-vnp) ⭐️ 8.0/10

Anthropic 的 formal-math 仓库提供了 \`vp-vnp\` 论文和 Lean 工程，论文宣称证明了 VP≠VNP 对所有域成立。若该主张成立，将给出代数复杂度中 VP 与 VNP 的分离；但目前它只是仓库中的主张，所给材料没有同行评审或独立验证，论文也明确表示尚未分析该结果与相对化、代数化障碍的关系。对研究者和形式化数学社区而言，眼下可检查的是论文和 Lean 工程本身，而不是一个已确立的定理。

hackernews · mikeryan52 · 11月23日 22:09 · [社区讨论](https://news.ycombinator.com/item?id=50620102)

**「背景」** 算术电路以变量和常数为基础，通过加法和乘法计算多项式，是代数复杂度理论的标准模型。1979 年 Leslie Valiant 据此定义了 VP（可用多项式规模算术电路计算的多项式类）和 VNP（可类似验证的多项式类），并问二者是否不同；这一问题至今仍未解决，常被视为 P 与 NP 问题的代数对应物。

**「核验前的影响」** 对代数复杂性研究者而言，若该 Lean 证明通过独立核验，将否定通常设定下永久式具有多项式规模代数电路这一可能，并使依赖 VP=VNP 的论证失去前提；在此之前，应把仓库中的结论视为未经同行评审的声明，先核验形式化定理的假设与完整性。

**「社区讨论」** 评论中一条实质性意见引用论文称，作者尚未分析该结果与相对化、代数化障碍的关系；另一条则推荐用 \`slim\` 工具在无需本地构建 Lean 的情况下浏览源码。其余讨论多是对 AI 攻克数学难题和实验室竞争的感叹，未形成技术共识。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Arithmetic_circuit_complexity">Arithmetic circuit complexity - Wikipedia</a></li>
<li><a href="https://www.kipuhub.com/en/article/algebraic-complexity-vp-vnp/">Algebraic Complexity: VP vs VNP – The Determinant vs the ...</a></li>
<li><a href="https://www.proofatlas.ai/collaboration/vp-versus-vnp-permanent-vs-determinant/">VP versus VNP — Permanent versus Determinant | ProofAtlas</a></li>
<li><a href="https://www.cs.columbia.edu/~toni/Talks/Icalp2021.pdf">ALGEBRAIC</a></li>

</ul>
</details>

**标签**: `#algebraic complexity`, `#Lean`, `#formal verification`, `#AI for math`, `#VP vs VNP`

---

<a id="item-tech-news-5"></a>
### [应 Arm 要求，非官方 Arm 文档站将于 12 月 4 日停站](https://arm.jonpalmisc.com/) ⭐️ 7.0/10

非官方 Arm 文档站 arm.jonpalmisc.com 宣布将于 2026 年 12 月 4 日停止服务。站点维护者 jonpalmisc 称，Arm 以商标和知识产权为由要求移除该站，理由是站点托管其文档时使用了这些内容；他表示，在不影响站点可用性的前提下很难规避这一要求。维护者还表示，将评估外界提出的镜像托管、寻求法律意见以及发布不含 Arm IP 的源码等方案，但这些方案目前均未落实。

hackernews · tech234a · 11月23日 19:17 · [社区讨论](https://news.ycombinator.com/item?id=50617499)

**「背景」** 这类非官方站点把 Arm 的指令集参考文档转成可按指令名直接检索的网页，方便开发者查阅单个指令的语义，而不必翻查 Arm 官方发布的手册。据评论者所述，Arm 本身会发布机器可读的 ISA 规范（MRAS），其开源包采用 BSD 风格许可，但只覆盖 ISA 参考部分，不含 EL 等其他架构文档；另有评论者将该站与斯坦福托管的 arm64 参考页面对比。争议的核心因此是：Arm 文档中的哪些内容可以被第三方重新发布。

**「影响」** 对该站用户而言，最直接的影响是失去一个查阅 Arm 文档的第三方入口，需在 12 月 4 日前另找资料。维护者虽提到可能接受镜像或发布不含 Arm IP 的源码，但尚未承诺可用的替代站点。

**「社区讨论」** 评论区的核心争论是 Arm 是否有权阻止第三方整理其公开架构文档：有人质疑整理公开销售的硬件文档为何受限，也有人认为这应属于合理使用。ethin 还称，他持有的多个版本 Arm MRAS（2025-06、2025-09、2026-03、2026-09）似乎采用 BSD 风格许可证，因此质疑该移除要求的依据；这些是评论者观点，不代表已获法律确认。

**标签**: `#Arm`, `#open documentation`, `#trademark/IP`, `#hardware`, `#developer access`

---

<a id="item-tech-news-6"></a>
### [谷歌搭建 Mirror Dimension 模拟网测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

据蓝点网报道，谷歌为 Chrome 的 AI 代理搭建了一个名为 Mirror Dimension 的模拟互联网，用于在隔离环境中测试其打开网站、搜索浏览、登录、加购和完成任务等操作。报道称该环境包含数千个模拟网站，每名工程师单独隔离测试，每天运行超过 1000 个测试案例，重点防御恶意网页的提示词注入等攻击。上述细节来自二级报道，尚无谷歌或独立来源确认。

telegram · zaihuapd · 11月23日 01:30

**「背景：浏览器代理与提示词注入」** 浏览器 AI 代理不再只回答问题，而是代替用户点击、输入、登录和完成购买，因此网页内容与代理指令之间的边界成为安全关键。若页面中隐藏的文本被模型当成指令执行，就会形成提示词注入；谷歌的安全博客称，其在 Mirror Dimension 中用隐蔽载荷和隐藏的注入攻击检验代理防御。

**「影响」** 如果该设施按报道运行，Chrome AI 代理在登录、加购等敏感操作上的验证将依赖隔离模拟站点和每天 1000 多个测试用例；对浏览器代理开发者而言，这意味着提示词注入防护需要可重复的离线回归测试，而不只是真实网站抽测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents : Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘ Mirror Dimension ’ Internet to Test Its Chrome ...</a></li>

</ul>
</details>

**标签**: `#Chrome AI agent`, `#browser agents`, `#AI security`, `#prompt injection`, `#testing infrastructure`

---

<a id="item-tech-news-7"></a>
### [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上表示，Windows Server 2028 将默认不再包含 WoW64 兼容子系统，因此该服务器系统在默认配置下无法运行 32 位应用。该版本计划于 2027 年秋季与 Windows 11 27H2 一同发布。需要运行 32 位软件的管理员可以通过按需功能（FoD）把 WoW64 装回，在 Server Core 上通常使用 PowerShell 或 DISM 添加。微软给出的理由是缩小攻击面、阻止 32 位恶意软件；Windows 11 目前仍保留 WoW64，微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景：WoW64 兼容层」** WoW64（Windows 32-bit on Windows 64-bit）是 64 位 Windows 上运行 32 位应用的兼容层，长期随系统默认提供，使大量旧版管理工具和业务软件无需额外配置即可在 64 位服务器上启动。此次调整把该组件改为按需功能（FoD），因此在 Server Core 等精简安装中，管理员需要通过 PowerShell 或 DISM 显式添加它，之后才能继续运行 32 位应用。

**「影响」** 依赖 32 位遗留软件的企业需要在部署前确认这些程序是否仍在使用，并把安装 WoW64 按需功能纳入系统镜像或部署脚本，否则新装的 Windows Server 2028 会直接无法启动这些应用。目前这一恢复方式来自微软的说明，尚未有独立测试验证其在 Server Core 等各版本上的具体行为。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/microsoft-is-removing-32-bit-app-support-by-default-in-windows-server-2028-but-windows-11-remains-unaffected/">Microsoft Is Removing 32-Bit App Support By Default In Windows ...</a></li>

</ul>
</details>

**标签**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#legacy software`, `#Microsoft`

---

<a id="item-tech-news-8"></a>
### [Codex2api 疑遭供应链投毒，恶意版本窃取密钥](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

Telegram 报告称，Codex2api 作者的 GitHub 账号被入侵，攻击者绕过 main 分支推送 tag，使 v3.1.10–v3.1.12 的 Release 构建包含后门。报告称 v3.1.11 移除了鉴权，等同于未授权远程命令执行；相关 workflow 还外传了同一账号下至少 21 个仓库的 16 个 GitHub Actions secrets。报告建议已安装或更新到这些版本的用户立即停用并回退到 3.1.9，同时轮换 GitHub token、SSH key、数据库及 DeepSeek 等相关凭据。上述说法来自单一 Telegram 汇总帖，尚未独立核实。

telegram · zaihuapd · 11月23日 11:21

**「背景」** Codex2api 这类项目依靠 GitHub Actions 的 Release 工作流发布二进制，而该工作流通常由推送 tag 触发；因此，攻击者只要拿到账号权限并推送 tag，就能绕过 main 分支的代码审查，让官方发布渠道直接产出带后门的版本。同类风险在 2026 年 11 月已有规模化记录：Endor Labs 与 Cybersecurity News 分别报道了针对 CI secrets 的 GitHub Actions 供应链攻击，称约 4,837 个 GitHub 账号被劫持、波及 61,764 个仓库，攻击目标为 GitHub Actions secrets 与云凭证；目前没有证据表明本次事件与该轮攻击属同一行动。

**「影响与处置」** 对使用 Codex2api 的部署而言，若曾运行 3.1.10–3.1.12，应将相关 Actions secrets 和运行环境凭据视为可能已泄露；仅回退版本不足以消除风险，还需轮换凭据并检查仓库与部署环境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.endorlabs.com/learn/github-actions-supply-chain-attack-targeting-ci-secrets-at-scale">Hijacked GitHub Accounts Push “wfx” CI Secret Stealer to ...</a></li>
<li><a href="https://cybersecuritynews.com/github-accounts/">Hackers Hijack 4,837 GitHub Accounts to Target 61,764 ...</a></li>

</ul>
</details>

**标签**: `#supply-chain-security`, `#github-actions`, `#security-incident`, `#secrets-management`, `#open-source-security`

---

<a id="item-tech-news-9"></a>
### [Meta AI 负责人称超级智能临近，黎曼猜想证明待复核](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Meta 首席 AI 官、超级智能实验室负责人 Alexandr Wang 在 X 发长文称，超级智能已不再是“未来某天”的议题，并警告人类可能难以控制可无限自我改进或比自己聪明 1000 倍的系统。他以数学家 Levent Alpöge 借助 Anthropic 的 Claude 完成、周六经 Lean 与 Mathlib 社区机器校验的黎曼猜想证明为例，认为 AI 与顶尖人类的差距只剩具体知识、工程整合与实验三块，并呼吁紧急投入安全、对齐与防护研究。该证明目前尚无人类可读版本，也未获独立复核，因此上述能力判断仍属 Wang 的表述，并非已确认的结果。

telegram · zaihuapd · 11月23日 12:49

**「背景」** 已有 167 年历史的黎曼猜想是数学界最著名的未解问题之一。Lean 是定理证明器，Mathlib 是其形式化数学库；在 Lean 中通过机器校验，意味着证明的步骤能按形式逻辑规则被检查，但这不同于同行评审，也不等于已经存在可供人类阅读的完整论证。

**「复核门槛」** 对数学界和 AI 安全评估者而言，首要问题是取得可读的证明阐述并完成独立复核；在仅有 Lean/Mathlib 机器校验、且无人类可读版本的情况下，外部研究者无法直接判断证明的正确性与意义，也不能据此确认超级智能已经到来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>
<li><a href="https://news.cgtn.com/news/2026-11-22/New-era-for-math-AI-helps-prove-the-167-year-old-Riemann-hypothesis-1ShAhHwzc1a/p.html">New era for math? AI helps prove the 167-year-old Riemann hypothesis</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#superintelligence`, `#AI alignment`, `#Lean/Mathlib`, `#Riemann hypothesis`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [据报 Anthropic IPO 后 AI 股遭抛售，DeepSeek 等中国 AI 公司上市计划蒙上阴影](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

据彭博报道，Anthropic 创纪录的 1195 亿美元 IPO 后全球 AI 股遭抛售，中国科技股自 6 月底以来累计蒸发 1.7 万亿美元。这给 DeepSeek、月之暗面和阶跃星辰筹备或考虑的上市计划蒙上阴影。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 的 1195 亿美元 IPO 是美国史上最大规模 IPO，但上市后并未提振 AI 板块，全球 AI 相关股票反而延续抛售。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>
<li><a href="https://www.theguardian.com/business/2026/nov/20/global-stock-markets-slump-anthropic-ipo-ai-sell-off">Global stock markets slump as Anthropic IPO fails to stem AI ...</a></li>

</ul>
</details>

**标签**: `#AI selloff`, `#China tech stocks`, `#IPO plans`, `#Anthropic IPO`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [上海地铁公布 21 年来首次票价调整](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

上海地铁公布 21 年来首次票价调整方案：新起乘价为 3 元，覆盖 0 至 4 公里，之后按 4、4、4、7、7、10、10 公里加 1 元，50 公里以上每 15 公里加 1 元，并将于 12 月 1 日起实施。同步推出四档计次票及同一支付渠道当月累计满 90 元享 9 折等优惠。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海地铁上一次票价调整距今已有 21 年。此次调价方案此前在 2026 年 9 月举行的优化地铁票价机制听证会上讨论，当时申通地铁集团同时提出计次票和满额优惠等配套方案，表示将与新票价机制同步公布实施。

**「影响」** 上海高频通勤者是直接受影响群体，单次出行支出将按新分段规则计算；官方称计次票和满额折扣旨在减少调价对这部分人群的影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hot.online.sh.cn/content/2026-09/09/content_10485162.htm">时隔 21 ...</a></li>

</ul>
</details>

**标签**: `#上海地铁`, `#公共交通票价`, `#民生政策`, `#通勤成本`

---