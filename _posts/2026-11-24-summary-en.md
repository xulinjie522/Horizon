---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 50 items, 11 important content pieces were selected

---

**Technology News**
1. [Ladybird browser engine reaches alpha with macOS and Linux builds](#item-tech-news-1) ⭐️ 8.0/10
2. [Zhipu releases GLM-5.4 coding model with loop-transformer architecture](#item-tech-news-2) ⭐️ 8.0/10
3. [Nvidia Board Reinstates Jensen Huang as CEO After U.S. Government Input](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic Repository Claims VP ≠ VNP Proof Over Every Field](#item-tech-news-4) ⭐️ 8.0/10
5. [Unofficial Arm documentation site to shut down after Arm request](#item-tech-news-5) ⭐️ 7.0/10
6. [Google Reportedly Built &\#x27;Mirror Dimension&\#x27; to Test Chrome AI Agent](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows Server 2028 to drop WoW64 by default, can be added back](#item-tech-news-7) ⭐️ 7.0/10
8. [Codex2api report alleges backdoored releases v3.1.10–v3.1.12](#item-tech-news-8) ⭐️ 7.0/10
9. [Meta AI chief warns superintelligence is near, control at risk](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [AI Selloff Clouds DeepSeek and Moonshot Listing Plans](#item-finance-news-1) ⭐️ 8.0/10
2. [Shanghai Metro Announces First Fare Adjustment in 21 Years](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird browser engine reaches alpha with macOS and Linux builds](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird, an independent open-source browser engine built largely from scratch, has released its first alpha, with installable builds for macOS and Linux that no longer require users to compile it themselves. The engine implements HTML parsing, CSS, layout, JavaScript, and WebAssembly in-house while relying on external components including HarfBuzz, Skia, ffmpeg, and SQLite. The project says the alpha will still fail on some sites and crash sometimes; hands-on testing reported broad compatibility, including WebAssembly ffmpeg and Pyodide, but Datasette Lite failed because navigator.serviceWorker.startMessages was missing. Ladybird runs tabs in separate processes, and its October newsletter reported 2,184,722 web-platform-tests subtests passed, above Safari and just below Firefox.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird originated in SerenityOS and implements most browser components itself — HTML parsing, CSS, layout, JavaScript and WebAssembly — while relying on external pieces such as HarfBuzz for text shaping, Skia for 2D graphics, ffmpeg for video and SQLite for storage. In February 2026 the project began porting parts of its LibJS engine from C++ to Rust with help from AI coding agents, and its October 2026 newsletter reported a new JavaScript JIT, a Cranelift-based WebAssembly engine, and about 75,650 additional passing subtests in the roughly 2.25-million-subtest web-platform-tests suite, which put its score above Safari&\#x27;s in that month&\#x27;s runs.

**「Impact」** Users can now test an independent engine without building it, but should expect crashes and site failures; service-worker-heavy apps such as Datasette Lite already fail on a missing navigator.serviceWorker.startMessages API. The browser includes in-product reporting for broken sites and lets users review crash reports before deciding whether to send them, giving developers a direct channel to flag compatibility gaps.

**「Community discussion」** Commenters reported that sites they considered difficult, including YouTube, Google Maps, and a Proxmox/NoVNC interface, rendered or worked in the alpha, though some noted lag and slightly jerky scrolling. One commenter asked what precautions are appropriate for alpha use, particularly around logins, payments, and downloads.

**Tags**: `#Ladybird`, `#browser engines`, `#open source`, `#alpha release`, `#web standards`

---

<a id="item-tech-news-2"></a>
### [Zhipu releases GLM-5.4 coding model with loop-transformer architecture](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Zhipu has released GLM-5.4, a coding-focused model that the company describes as built on its first loop-transformer architecture and aimed at &quot;generalized coding.&quot; The &quot;first&quot; and generalized-coding claims are vendor assertions that are not independently verified in the supplied material. Access appears limited: one Hacker News commenter reported that GLM-5.4 was not available through OpenRouter or the regular Z.ai API plan and required Z.ai&\#x27;s Coding Plan, whose API keys expose the new model.

hackernews · r/LocalLLaMA · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Background」** Looped transformers run a shared block of layers for several iterations instead of computing each layer exactly once; because token generation is bottlenecked by moving layer weights from memory to the compute chip, reusing a resident block can buy reasoning depth without adding parameters. Horizon&\#x27;s 21 November digest covered an earlier open-weight instance of the idea, Thinking Machines&\#x27; Inkling 2 Mini, where the team said looping improves reasoning but adds no stored factual knowledge, so factuality still tracks parameter count. Z.ai&\#x27;s release material describes GLM-5.4 as its first flagship loop transformer, with 28 of its 78 layers run twice and a company claim of parity with 2T–3T parameter models; Z.ai has released its GLM models under the MIT license since July 2025.

**「Access path is gated at launch」** Developers routing through OpenRouter or Z.ai&\#x27;s standard API plan cannot reach GLM-5.4 at launch: as of November 23, 2026, OpenRouter&\#x27;s public catalog listed GLM-5.3 with no 5.4 entry, and access instead requires the Z.ai Coding Plan, whose API keys behave like standard keys but carry 1.5× the weekly credits of GLM-5.3. Teams that hard-code a single provider endpoint should plan for a fallback or a separate key pool for GLM-5.4 traffic.

**「Community discussion」** Commenters praised Zhipu for disclosing technical details, with one explaining that loop transformers reuse layers to reduce the memory-bandwidth bottleneck of moving weights onto the chip for each token. Others reported practical drawbacks: one complained that Chinese models&\#x27; lengthy &quot;marathon thinking&quot; makes even simple tasks slow, and another found GLM-5.4&\#x27;s sample outputs similar to GLM-5.3&\#x27;s.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Z.ai">Z. ai - Wikipedia</a></li>
<li><a href="https://anyrouter.dev/model/z-ai/glm-5.4">GLM - 5 . 4 · Zhipu AI · pricing &amp; API · AnyRouter</a></li>
<li><a href="https://www.youtube.com/watch?v=HVey00YZ5Xk">GLM - 5 . 4 Is Here: The First Loop Transformer , and What... - YouTube</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>
<li><a href="https://aihubmix.com/blog/glm-5-4-api-access-should-you-wait-for-openrouter">GLM-5.4 API Access: Should You Wait for OpenRouter?</a></li>
<li><a href="https://explainx.ai/blog/glm-5-4-coding-plan-vision-50-percent-quota-boost-november-2026">GLM-5.4 Coding Plan: +50% Quota, Vision (Nov 2026 ...</a></li>

</ul>
</details>

**Tags**: `#GLM-5.4`, `#Looped Transformers`, `#LLM architecture`, `#coding models`, `#Zhipu AI`

---

<a id="item-tech-news-3"></a>
### [Nvidia Board Reinstates Jensen Huang as CEO After U.S. Government Input](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 8.0/10

Nvidia&\#x27;s board reinstated Jensen Huang as CEO, CNBC reported on Nov. 23, in a decision reportedly shaped by input from senior U.S. government officials. According to a board statement quoted in the Hacker News discussion, the board concluded that Huang&\#x27;s reinstatement poses no national security risk. The supplied material does not include the full article or Nvidia&\#x27;s announcement, so the circumstances of his departure, the board&\#x27;s earlier decision, and any export-policy conditions remain unclear.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Background」** Jensen Huang resigned as Nvidia&\#x27;s CEO on Nov. 13, 2026, and the board&\#x27;s decision to reinstate him as president, CEO and board member took effect immediately less than two weeks later, according to the company announcement. The reversal followed a turbulent stretch for Nvidia: Horizon&\#x27;s Nov. 21 digest reported that the company was reportedly facing an SEC accounting investigation and that its stock had extended a steep selloff, while noting the allegation was unconfirmed and gave no specifics on the practices under review.

**「Discussion」** Commenters zeroed in on the board&\#x27;s statement that it had received input from senior U.S. government officials; one called that the “most operative part,” while another argued the involvement did not by itself show evidence of wrongdoing. Others criticized what they saw as inconsistency with U.S. pressure on ASML and Japanese chip firms over China sanctions, and questioned why the board reversed course so quickly.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/markets/article/nvidia-stock-extends-25-trillion-rout-as-sec-probe-reportedly-investigates-its-accounting-194945274.html">2026-11-21 — Nvidia reportedly faces SEC accounting investigation as stock falls</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html">Jensen Huang reinstated as Nvidia CEO. Stock skyrockets 31%</a></li>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director">NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI hardware`, `#semiconductor policy`, `#corporate governance`, `#US export controls`

---

<a id="item-tech-news-4"></a>
### [Anthropic Repository Claims VP ≠ VNP Proof Over Every Field](https://github.com/anthropics/formal-math/tree/main/vp-vnp) ⭐️ 8.0/10

Anthropic&\#x27;s formal-math repository now hosts a paper claiming a proof that VP ≠ VNP over every field, a result aimed at algebraic-complexity and formal-verification researchers and drawing heavy Hacker News attention. The item does not include peer review or detailed independent validation, so the separation remains a claim rather than an established result. The paper also says it has not analyzed how the result relates to relativization and algebrization, an important limitation for a complexity-theory proof.

hackernews · mikeryan52 · Nov 23, 22:09 · [Discussion](https://news.ycombinator.com/item?id=50620102)

**「Background」** VP and VNP are algebraic complexity classes for polynomials, defined using arithmetic circuits that compute expressions through addition and multiplication. Leslie Valiant introduced the classes in 1979 and asked whether they differ, the algebraic counterpart of P versus NP; the question remains open.

**「Verification gap limits reuse」** Anyone citing this result should first check the Lean formalization and address the paper&\#x27;s own admission that it has not analyzed relativization or algebrization; until then it is a claimed, not established, separation. Because VP ≠ VNP is treated as a prerequisite for proving nonuniform P ≠ NP, that unresolved gap also blocks downstream complexity claims that depend on the separation.

**「Community Discussion」** Commenters largely treated the post as part of an Anthropic push toward P vs NP rather than debating the proof&\#x27;s technical merits; one noted the paper&\#x27;s statement that it has not analyzed relativization or algebrization, and another shared a tool for navigating the Lean source. Those remarks are reactions and pointers, not independent validation.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Arithmetic_circuit_complexity">Arithmetic circuit complexity - Wikipedia</a></li>
<li><a href="https://www.kipuhub.com/en/article/algebraic-complexity-vp-vnp/">Algebraic Complexity: VP vs VNP – The Determinant vs the ...</a></li>
<li><a href="https://arxiv.org/pdf/2406.06217">Completeness classes in algebraic complexity theory</a></li>

</ul>
</details>

**Tags**: `#algebraic complexity`, `#Lean`, `#formal verification`, `#AI for math`, `#VP vs VNP`

---

<a id="item-tech-news-5"></a>
### [Unofficial Arm documentation site to shut down after Arm request](https://arm.jonpalmisc.com/) ⭐️ 7.0/10

The unofficial Arm documentation site arm.jonpalmisc.com will be discontinued on 4 December 2026. Its operator, jonpalmisc, said Arm requested removal on the grounds that hosting the documentation uses Arm trademarks and IP, which he called hard to work around while keeping the site useful. He said he is considering offers to host mirrors, seek legal advice, and release the site&\#x27;s source code without Arm IP for personal use; no successor has been announced.

hackernews · tech234a · Nov 23, 19:17 · [Discussion](https://news.ycombinator.com/item?id=50617499)

**「Context: how Arm&\#x27;s docs are mirrored」** Arm publishes its architecture reference manuals — the instruction-set documentation defining AArch64 behaviour — through its own developer site, and the site being shut down is an unofficial mirror that reformats those manuals into cross-linked HTML with per-instruction anchors such as \`abs\`. Commenters noted that similar converted pages exist elsewhere, citing a Stanford-hosted AArch64 reference, and one commenter said Arm&\#x27;s machine-readable architecture specification releases \(versions 2025-06 through 2026-09\) carry a BSD-style licence while the broader documentation set does not — a distinction that bears on why a mirror is contested.

**「Impact」** Developers who used the unofficial site as a browsable reference will lose that access when it closes. Because the operator has not committed to a mirror or replacement, users may need to rely on Arm&\#x27;s official documentation or on third-party copies whose availability and licensing are not established.

**「Community Discussion」** Commenters questioned whether documenting publicly sold hardware is fair use and how Arm&\#x27;s request is enforceable, with one pointing to a similarly formatted copy hosted at Stanford and another noting that some Arm machine-readable specification releases carry a BSD-style license. One commenter argued that legal decisions like this should be reviewed by someone who understands the engineering and business impact, an opinion rather than a confirmed fact about Arm&\#x27;s reasoning.

**Tags**: `#Arm`, `#open documentation`, `#trademark/IP`, `#hardware`, `#developer access`

---

<a id="item-tech-news-6"></a>
### [Google Reportedly Built &\#x27;Mirror Dimension&\#x27; to Test Chrome AI Agent](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

According to a brief Landian report, Google reportedly built an isolated simulated internet called Mirror Dimension to test a Chrome AI agent as it opens websites, searches, logs in, adds items to carts, and completes tasks. The environment reportedly contains thousands of mock websites, with each engineer testing in a separate isolated setup and more than 1,000 test cases run daily. The reported focus includes defenses against prompt injection and other attacks from malicious webpages; the supplied material provides no primary-source confirmation from Google.

telegram · zaihuapd · Nov 23, 01:30

**「Why a sandboxed web is needed for browser agents」** Browser-use agents are AI models that act inside a real browser—opening pages, searching, logging in, adding items to a cart and completing tasks—which means every page they visit also becomes part of their input. That makes hidden text on a malicious page a prompt-injection vector, since the agent can read it as instructions and be redirected. Google detailed the Mirror Dimension setup publicly for the first time in a company blog post, with Wired reporting that the Chrome team entirely controls the isolated web ecosystem used for these tests.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents : Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘ Mirror Dimension ’ Internet to Test Its Chrome ...</a></li>

</ul>
</details>

**Tags**: `#Chrome AI agent`, `#browser agents`, `#AI security`, `#prompt injection`, `#testing infrastructure`

---

<a id="item-tech-news-7"></a>
### [Windows Server 2028 to drop WoW64 by default, can be added back](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft said at Ignite 2026 that Windows Server 2028 will ship without the WoW64 compatibility subsystem by default, so 32-bit applications will not run out of the box. The server release is planned for fall 2027 alongside Windows 11 27H2, and administrators who need legacy support can restore WoW64 as a Feature on Demand, typically via PowerShell or DISM on Server Core. Microsoft says the change is intended to reduce attack surface and block 32-bit malware, while Windows 11 still includes WoW64 and has no announced removal plan.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 is the compatibility subsystem that has long allowed 64-bit Windows to run 32-bit applications, and Windows Server has included it by default. At Ignite 2026, Microsoft presented Windows Server 2028 as making WoW64 optional, ending that default 32-bit compatibility.

**「Impact」** Administrators planning Windows Server 2028 upgrades should inventory 32-bit applications and include the WoW64 Feature on Demand in their images, especially for Server Core, where it must be added with PowerShell or DISM; otherwise those applications will not launch by default.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/microsoft-is-removing-32-bit-app-support-by-default-in-windows-server-2028-but-windows-11-remains-unaffected/">Microsoft Is Removing 32-Bit App Support By Default In Windows ...</a></li>

</ul>
</details>

**Tags**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#legacy software`, `#Microsoft`

---

<a id="item-tech-news-8"></a>
### [Codex2api report alleges backdoored releases v3.1.10–v3.1.12](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

A Telegram post relaying an incident write-up alleges that the Codex2api author&\#x27;s GitHub account was compromised and that the attacker bypassed the main branch by pushing tags, causing releases v3.1.10 through v3.1.12 to ship a backdoor. According to the report, v3.1.11 removed authentication—effectively allowing unauthenticated remote command execution—and a workflow exfiltrated 16 GitHub Actions secrets from at least 21 repositories on the same account. The post advises anyone who installed or updated to 3.1.10–3.1.12 to stop using the tool, roll back to 3.1.9, and rotate GitHub tokens, SSH keys, database credentials, and DeepSeek and other related secrets. These claims have not been independently verified here.

telegram · zaihuapd · Nov 23, 11:21

**「Why tag-triggered releases matter」** GitHub branch protection covers branches, not tags, while release workflows are often configured to build and publish when a tag is pushed. An attacker with account access can therefore publish a release build without merging to main, and any Actions secrets available to that workflow become reachable. The episode follows reports in November 2026 of a wider campaign in which hijacked GitHub accounts were used to steal Actions secrets at scale.

**「Impact」** For affected users, the practical consequence is that any GitHub token, SSH key, database credential, or DeepSeek key reachable from the repository should be treated as exposed until rotated, and systems running an affected release should be taken offline rather than left in service. Operators should verify the deployed version against the reported range and follow the rollback to 3.1.9 before restoring service.

<details><summary>References</summary>
<ul>
<li><a href="https://www.endorlabs.com/learn/github-actions-supply-chain-attack-targeting-ci-secrets-at-scale">Hijacked GitHub Accounts Push “wfx” CI Secret Stealer to ...</a></li>
<li><a href="https://cybersecuritynews.com/github-accounts/">Hackers Hijack 4,837 GitHub Accounts to Target 61,764 ...</a></li>

</ul>
</details>

**Tags**: `#supply-chain-security`, `#github-actions`, `#security-incident`, `#secrets-management`, `#open-source-security`

---

<a id="item-tech-news-9"></a>
### [Meta AI chief warns superintelligence is near, control at risk](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Meta Chief AI Officer and Superintelligence Labs head Alexandr Wang argued in a long X post that superintelligence is no longer a future-only issue and that human control is at risk. He cited a Riemann hypothesis proof produced by mathematician Levent Alpöge with Anthropic&\#x27;s Claude and machine-checked by the Lean and Mathlib community on Saturday, saying AI&\#x27;s remaining gap to top humans is concrete knowledge, engineering integration, and experimentation. Wang called for urgent investment in safety, alignment, and protection research. The proof has no human-readable exposition yet and has not been independently vetted.

telegram · zaihuapd · Nov 23, 12:49

**「Background」** The proof Wang cites concerns the Riemann hypothesis, a 167-year-old open problem; Anthropic mathematician Levent Alpöge said he worked with the company&\#x27;s Claude model for six weeks to produce it, according to The Guardian. A technical blog reports that the result was verified in Lean, a formal proof assistant that checks a derivation against a machine-readable library but does not by itself provide a human-readable exposition—which the source says is still missing.

**「Impact」** Because the Riemann hypothesis claim rests on a machine-checked Lean/Mathlib proof without a human-readable exposition or independent review, mathematicians and AI researchers cannot yet treat it as an established result; those checks would be needed before it could reliably inform assessments of AI capabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#superintelligence`, `#AI alignment`, `#Lean/Mathlib`, `#Riemann hypothesis`

---

## Financial News

<a id="item-finance-news-1"></a>
### [AI Selloff Clouds DeepSeek and Moonshot Listing Plans](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

Bloomberg reported that a global AI selloff following Anthropic’s $119.5 billion record IPO is clouding planned or considered listings by Chinese AI companies including DeepSeek and Moonshot, after Chinese tech stocks lost $1.7 trillion since late June.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** Anthropic’s record IPO, described by CNBC as the largest in U.S. history, failed to revive the AI trade as a global selloff hit AI-linked stocks.

**「Impact」** The weaker backdrop is already visible among Chinese AI firms: Zhipu is down more than 85% from its June high, and MiniMax fell below its IPO price this month.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>
<li><a href="https://www.theguardian.com/business/2026/nov/20/global-stock-markets-slump-anthropic-ipo-ai-sell-off">Global stock markets slump as Anthropic IPO fails to stem AI ...</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China tech stocks`, `#IPO plans`, `#Anthropic IPO`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [Shanghai Metro Announces First Fare Adjustment in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai Metro announced its first fare adjustment in 21 years, setting a 3-yuan starting fare for trips of 0–4 km and introducing multi-ride tickets and discounts; the changes take effect Dec. 1.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** The fare had been unchanged for 21 years, and Shanghai held a public hearing in September 2026 on two proposed mechanisms—including possible dynamic fare adjustments and multi-ride tickets—before announcing the new fares.

**「Impact」** The change directly affects Shanghai commuters’ monthly travel costs, with the discount measures designed to cushion the effect on frequent riders.

<details><summary>References</summary>
<ul>
<li><a href="https://hot.online.sh.cn/content/2026-09/09/content_10485162.htm">时隔 21 ...</a></li>

</ul>
</details>

**Tags**: `#上海地铁`, `#公共交通票价`, `#民生政策`, `#通勤成本`

---