---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 44 items, 15 important content pieces were selected

---

**Technology News**
1. [1Password Discloses Backend Code-Push Security Incident](#item-tech-news-1) ⭐️ 8.0/10
2. [Scott Aaronson on AI-assisted math advances and proof-checking debate](#item-tech-news-2) ⭐️ 8.0/10
3. [Lean audit of Clojure core reports unreported bugs, commenters dispute some](#item-tech-news-3) ⭐️ 7.0/10
4. [Much shorter Lean version of Anthropic GRH verification appears on GitHub](#item-tech-news-4) ⭐️ 7.0/10
5. [Google publishes Cogentic research papers on factoring and discrete logs](#item-tech-news-5) ⭐️ 7.0/10
6. [LoomFormer adds per-token routing between attention heads](#item-tech-news-6) ⭐️ 7.0/10
7. [Report: NVIDIA posts open weights for Nemotron-Labs-Image-30B-A3B](#item-tech-news-7) ⭐️ 7.0/10
8. [LoopRes adds loop-aware attention residuals for pretrained LLM fine-tuning](#item-tech-news-8) ⭐️ 7.0/10
9. [Tencent open-sources Hy4 flash GGUF weights, runs on 64 GB Mac mini](#item-tech-news-9) ⭐️ 7.0/10
10. [Minecraft Java RCE via crafted server resource-pack fonts; no official patch yet](#item-tech-news-10) ⭐️ 7.0/10
11. [Samsung, SK Hynix reportedly to license YMTC&\#x27;s Xtacking NAND stacking tech](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [Commerce Department reportedly warned Intel of &\#x27;consequences&\#x27; before 10% stake deal](#item-finance-news-1) ⭐️ 9.0/10
2. [U.S. Plans New Section 301 Tariffs on 14 Trading Partners](#item-finance-news-2) ⭐️ 8.0/10
3. [Jensen Huang Returns to Nvidia as U.S.-China AI Talent Race Widens](#item-finance-news-3) ⭐️ 7.0/10
4. [SpaceX to Forgo $738 Million in Federal Broadband Subsidies, Offer Free Starlink Hardware Instead](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [1Password Discloses Backend Code-Push Security Incident](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password published an update on a November 2026 security incident after malicious code was reportedly pushed to its backend services. The supplied material identifies the deployment path as the concern but provides no root cause, timeline, or independent confirmation of scope, and it does not explain whether branch protections were missing or bypassed. The notice reportedly states that a small number of affected users were specifically notified, but the available text does not establish vault compromise or quantify impact.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** The incident fits a SaaS compromise path in which an attacker who takes over an employee’s code-hosting account can push malicious changes into production. 1Password’s update says its investigation began on November 19, 2026, after indications that an attacker had accessed an employee’s corporate GitHub account and used it to reach source code and push malicious code to backend services; reporting on the breach said customer names and email addresses were accessed but vault contents were not compromised.

**「User exposure」** For customers whose names and email addresses were accessed, the practical exposure is targeted phishing or spam rather than vault compromise. Verify unexpected 1Password messages through the official app or site instead of following links.

**「Community Discussion」** Commenters focused on SaaS backend compromise: tptacek called an employee laptop compromise leading to code pushed to GitHub and then deployed the standard breach pattern, while ctidd criticized the disclosure for not saying whether push-to-main was disabled or branch protections were bypassed. ChrisHardie, a longtime local-vault user, said the incident reinforced his concern about online vaults, and fn-mote asked for an explicit statement that encrypted vaults were not downloaded.

<details><summary>References</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1 Password ’s backend ...</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>

</ul>
</details>

**Tags**: `#security incident`, `#password managers`, `#supply chain security`, `#SaaS security`, `#code deployment`

---

<a id="item-tech-news-2"></a>
### [Scott Aaronson on AI-assisted math advances and proof-checking debate](https://scottaaronson.blog/?p=10379) ⭐️ 8.0/10

For mathematicians and theoretical computer scientists, Scott Aaronson&\#x27;s Nov. 25 blog post describes a rapid, AI-linked wave of progress on hard mathematics and theoretical computer science problems, and it points to a paper titled “The matrix multiplication exponent is nine fourths.” The supplied material does not identify the specific problems solved, the AI systems or methods involved, or whether the results have been independently verified. The post&\#x27;s hyperbolic title and the surrounding discussion make clear that the claims are still being assessed, not that a settled set of results has been established.

hackernews · Kotlopou · Nov 25, 19:11 · [Discussion](https://news.ycombinator.com/item?id=50646108)

**「Background」** Matrix multiplication&\#x27;s exponent ω describes how the number of arithmetic operations needed to multiply square matrices grows with their dimensions. A linked OpenAI math preprint titled “The matrix multiplication exponent is nine fourths” says its Lean development proves the square exponent 9/4 for division-free circuits computing formal polynomial identities over every field, and its scope document also states the formalized dual and rectangular exponents.

**「Verification burden」** If the preprint&\#x27;s matching lower bound survives checking, the matrix multiplication exponent would be pinned at 9/4, leaving no room for a faster asymptotic algorithm and shifting researchers&\#x27; attention to verifying the Lean formalization and the reduction to the distinct-elements lower bound. Until that verification is complete, the result should be treated as a claim rather than a settled bound.

**「Community discussion」** Commenters debate whether Lean, MathLib, and large amounts of compute could have produced similar progress without LLMs, with utopiah asking whether the timing reflects subsidized compute. onetimeusename argues that discrepancies between Lean and informal proofs should not be brushed aside, while pixl97 hopes any such advances remain confined to verifiable tasks.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md">math /preprints/The- matrix - multiplication - exponent -is...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://kingy.ai/blog/openai-matrix-multiplication-exponent-nine-fourths/">OpenAI Claims Matrix Multiplication Exponent Is Exactly 9/4</a></li>
<li><a href="https://xenospectrum.com/en/matrix-multiplication-nine-fourths-lower-bound/">OpenAI Preprint Claims the Matrix Multiplication Exponent Is ...</a></li>

</ul>
</details>

**Tags**: `#AI for mathematics`, `#Lean theorem proving`, `#proof verification`, `#matrix multiplication`, `#Hacker News discussion`

---

<a id="item-tech-news-3"></a>
### [Lean audit of Clojure core reports unreported bugs, commenters dispute some](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

A blog post reports that using the Lean proof assistant to audit Clojure&\#x27;s core library surfaced bugs that had not previously been reported to the project. The findings have drawn scrutiny in discussion: commenter rvprasad argues at least two entries reflect incorrect usage rather than library defects, citing a call that passes a Long to \`.indexOf\` on a byte array and \`\(get &quot;abc&quot; 1.9\)\`, where \`get\` coerces the key to an integer for string lookups. The post&\#x27;s full list and methodology are not available in the supplied material, so how many of the reported issues are genuine, confirmed defects remains unresolved.

hackernews · encyclopedism · Nov 25, 14:56 · [Discussion](https://news.ycombinator.com/item?id=50642939)

**「Background」** Lean is a dependently typed proof assistant used to formalize mathematical proofs and verify program properties, while Clojure is a dynamically typed Lisp whose core library provides widely reused collection and sequence operations. Applying Lean to an existing standard library involves modeling those operations and their edge cases as formal specifications, then checking whether the implementation satisfies them—an approach more commonly associated with purpose-built verified software.

**「Triage before patching」** For Clojure developers, the practical consequence is triage rather than immediate patching: commenters argued that at least two flagged items are questionable, with \`\(.indexOf \(seq \(byte-array \[1 2 3\]\)\) 2\)\` passing a Long where a byte is required, and \`\(get &quot;abc&quot; 1.9\)\` attributed to \`get\`&\#x27;s coercion of keys in string lookup rather than a core defect. Teams running Clojure in production—including Nubank, which absorbed Cognitect in 2020 and describes mission-critical Clojure at scale—should verify each reported case before altering code or filing upstream.

**「Community discussion」** The most substantive pushback came from rvprasad, who contends that some flagged cases would have been caught by simple type checking and that such false positives reduce the usefulness of the exercise. Another commenter, yababa\_y, linked a comparable audit of Common Lisp implementations \(SBCL, Clozure and ACL2\), while networked asked whether Lean is now displacing Rocq \(formerly Coq\) for this kind of verification work and whether language models write Lean more effectively.

<details><summary>References</summary>
<ul>
<li><a href="https://cognitect.com/">Cognitect, a Nu Holdings, Ltd. Company</a></li>

</ul>
</details>

**Tags**: `#Clojure`, `#Lean`, `#formal verification`, `#programming languages`, `#bug finding`

---

<a id="item-tech-news-4"></a>
### [Much shorter Lean version of Anthropic GRH verification appears on GitHub](https://github.com/lsernau/grh-lean) ⭐️ 7.0/10

The GitHub repository lsernau/grh-lean is being circulated as a much shorter Lean formalization of the GRH verification associated with Anthropic, according to the item and Hacker News discussion. Commenters report a reduction from roughly 17 million lines to about 76,000 lines \(99.56%\); another describes a more readable roughly 300k-line proof with documentation and a clear split between known and new mathematics. The available evidence is a repository plus community commentary rather than a peer-reviewed result, so the reported compression and its significance remain unverified.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Background」** Levent Alpöge&\#x27;s November claim, made with Claude, was that the Generalized Riemann Hypothesis had been proved and formalized in Lean; Horizon&\#x27;s November 21 digest reported the accompanying archive at roughly 15 million lines and 1.3GB, with no independent verification of correctness. Other reporting cites 17,374,215 lines across 175,187 files for the original formalization, so the new item is best understood as a much shorter version of that same GRH artifact, with its value depending on whether the reduced proof remains equivalent and machine-checkable.

**「Impact」** The reported reduction gives Lean users and formal-verification reviewers a much smaller codebase to inspect, but commenters still question whether a human can realistically read and verify the code, so the size reduction alone does not settle auditability.

**「Community discussion」** Commenters welcomed the clearer structure and documentation, with one saying the known-math/new-math split should help digestion, while another asked how realistically a human could read and verify the Lean code. A separate commenter framed the result as a contrast between incremental manual proof reduction and Anthropic applying compute and better internal models.

<details><summary>References</summary>
<ul>
<li><a href="https://alpo.ge/remark.pdf">2026-11-21 — Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis</a></li>
<li><a href="https://meridian48.com/news/ai-assisted-lean-proof-for-riemann-hypothesis-spans-17-4-million-lines-7c3f57">AI-assisted Lean proof for Riemann Hypothesis spans 17.4 ...</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#AI-assisted mathematics`, `#proof minimization`, `#open source`

---

<a id="item-tech-news-5"></a>
### [Google publishes Cogentic research papers on factoring and discrete logs](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google has added a set of “Cogentic” research papers to its google-research GitHub repository, covering integer factorization, discrete logarithms, and related number-theory topics. The item provides no paper details, peer-review status, or independent confirmation of cryptographic impact, so the results should be treated as unverified research claims rather than demonstrated breaks.

hackernews · rgwohlbold · Nov 25, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50642086)

**「Background」** Integer factorization and discrete logarithms are number-theory problems whose assumed difficulty underpins several cryptographic schemes. A discrete logarithm modulo a prime asks how many times a base must be multiplied by itself to reach a given residue; for example, powers of 2 modulo 5 repeat every four steps, so the discrete logarithm is taken modulo 4.

**「Community discussion」** One detailed HN commenter argued that the integer-factorization result builds on the general number field sieve, which already has better asymptotic complexity but depends on unproven heuristics; in that commenter’s account, the Cogentic work replaces those parts at a significant complexity cost without proving the conjectures. Other commenters linked unverified rumors of broader results, which the supplied evidence does not substantiate.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Discrete_logarithm">Discrete logarithm - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#number theory`, `#Google Research`

---

<a id="item-tech-news-6"></a>
### [LoomFormer adds per-token routing between attention heads](https://www.reddit.com/gallery/1y50x62) ⭐️ 7.0/10

A Reddit self-post describes LoomFormer, a Transformer variant in which each token carries a small matrix beside the residual stream so that attention heads can choose per token which earlier heads they read from. Read and write addresses are computed from the residual stream at every token, and this vertical head-to-head attention is interleaved with standard token attention. The author reports that a 2.8B-parameter model trained on 300B Pile tokens is level with Pythia-12B on a 10-task average: 59.9 vs 59.9 zero-shot and 61.6 vs 60.8 five-shot. The reported costs are 2–4% more FLOPs and 8–16% slower wall-clock than a plain Transformer even with fused kernels; the largest model trained is 2.8B, and the results have no independent validation.

reddit · r/MachineLearning · Alternative\_Cellist1 · Nov 25, 07:05 · [Discussion](https://www.reddit.com/r/MachineLearning/comments/1y50x62/letting_each_attention_head_choose_which_earlier/)

**「Background」** LoomFormer is measured against two existing baselines. Pythia is a public model suite trained on 300B Pile tokens, which supplies the same-token-budget, same-parameter comparison the post reports. mHC \(Manifold-Constrained Hyper-Connections\) is an earlier architecture that also reworks information flow around the residual stream; the mHC paper benchmarks it against plain and hyper-connection baselines, and Goedel-mHC-1B is released as the first open 1B+ pretrained model built on it with a matched standard-transformer baseline.

**「Impact」** For architecture researchers, the reported trade-off is a large parameter-efficiency gain accompanied by a wall-clock penalty driven by memory traffic on the routing matrix and many small projections. The 2.8B-parameter ceiling and preliminary Reddit presentation mean the approach is not yet a drop-in replacement for standard attention at larger scales.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2512.24880">mHC: Manifold-Constrained Hyper-Connections - arXiv.org</a></li>
<li><a href="https://www.goedelmachines.com/blog/releasing-goedel-mhc-1b">Releasing goedel-mHC-1B · Gödel Machines</a></li>

</ul>
</details>

**Tags**: `#transformer architectures`, `#attention routing`, `#dynamic computation`, `#language models`, `#ML research`

---

<a id="item-tech-news-7"></a>
### [Report: NVIDIA posts open weights for Nemotron-Labs-Image-30B-A3B](https://www.reddit.com/gallery/1y4yrts) ⭐️ 7.0/10

A Reddit post reports that NVIDIA released open weights on Hugging Face for Nemotron-Labs-Image-30B-A3B, the raster-image component of its Nemotron-Labs-VisualCreation &quot;Pixel as Code&quot; agentic framework. The model is described as a 30B-total/3B-active mixture-of-experts system using a Nemotron-H hybrid Mamba-2 plus attention architecture, initialized from Nemotron 3 Nano and trained with progressive mid-training and GRPO. The post also claims its output outperforms GPT Image 2 and Nano Banana Pro on key benchmarks, but supplies no independent verification or official NVIDIA confirmation.

reddit · r/LocalLLaMA · ResearchCrafty1804 · Nov 25, 05:00 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y4yrts/nvidia_just_quietly_dropped_open_weights_for/)

**「Background」** Nemotron is NVIDIA&\#x27;s family of open-weight models, and this image generator was initialized from Nemotron 3 Nano, a small hybrid Mamba-2/attention model, rather than trained from scratch. The 30B-total/3B-active mixture-of-experts layout follows the same sparse-activation pattern NVIDIA uses elsewhere in the line, such as its open Nemotron 3.5 Lightning 30B MoE with 3B active parameters. According to the Hugging Face model card, the initial release covers the image generator and its bundled visual tokenizer, not the full Nemotron-Labs-VisualCreation framework.

**「Impact」** For developers assessing open-weight image generators, the checkpoint offers a concrete 30B/3B MoE model to download and test, but the benchmark claims should be validated before adoption because the supplied evidence is a Reddit post without independent results.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/nvidia/Nemotron-Labs-Image-30B-A3B">nvidia / Nemotron - Labs - Image - 30 B - A 3 B · Hugging Face</a></li>
<li><a href="https://wccftech.com/nvidia-quietly-releases-open-weights-for-nemotron-labs-image-30b-a3b/">NVIDIA Releases Open Weights For...</a></li>
<li><a href="https://developer.nvidia.com/topics/ai/nemotron">Nemotron AI Models | NVIDIA Developer</a></li>

</ul>
</details>

**Tags**: `#open-weights`, `#image-generation`, `#multimodal`, `#NVIDIA`, `#MoE`

---

<a id="item-tech-news-8"></a>
### [LoopRes adds loop-aware attention residuals for pretrained LLM fine-tuning](https://i.redd.it/kv552tyzbq3i1.png) ⭐️ 7.0/10

A Reddit post proposes LoopRes, a fine-tuning method that lets each looped layer attend to outputs from earlier loops through trainable loop-aware keys and restricts attention to a residual window covering the latest W loops. The abstract reports gains across 6 pretrained LLMs from 3 model families and 9 benchmarks: at 2x compute, Qwen3-1.7B-Base improves by 29.1% over SFT, more than double the state-of-the-art baseline&\#x27;s gain, with gains holding up to 30B. It also claims steeper scaling than SFT from 1.7B to 8B and less compute on long outputs. The post is a truncated abstract on Reddit, not a peer-reviewed paper, so the results are not independently verified.

reddit · r/LocalLLaMA · Powerful\_Evening5495 · Nov 25, 09:44 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y53dpq/unlocking_the_power_of_loops_in_pretrained_llms/)

**「Looped transformers and the fine-tuning gap」** Looped transformers reuse a shared block of layers across several passes, buying extra computation without extra parameters. Horizon&\#x27;s November 21 and November 24 digests covered two releases built on this idea—Inkling 2 Mini, an open-weight model sized for local inference, and Zhipu&\#x27;s coding-focused GLM-5.4—but the approach has generally required training from scratch, and cheaply fine-tuning an existing pretrained LLM into a loop has so far produced only marginal gains over standard supervised fine-tuning.

**「Impact」** For developers fine-tuning pretrained LLMs, LoopRes is not a drop-in recipe: it requires modifying attention to add per-loop trainable keys and choosing the residual-window size W, so compatibility and the reported gains depend on reimplementing the method.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>
<li><a href="https://z.ai/blog/glm-5.4">2026-11-24 — Zhipu releases GLM-5.4 coding model with loop-transformer architecture</a></li>

</ul>
</details>

**Tags**: `#looped transformers`, `#LLM fine-tuning`, `#attention residuals`, `#test-time scaling`, `#model efficiency`

---

<a id="item-tech-news-9"></a>
### [Tencent open-sources Hy4 flash GGUF weights, runs on 64 GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

Tencent has open-sourced GGUF quantized weights for Hy4 flash, a 224B-parameter model, through its AngelSlim compression toolkit. The original weights are about 410.27 GiB; the smallest IQ2-AH version is 125.73 GiB, roughly 30% of the original, and Tencent says it can run on a 64 GB Mac mini using the Strata offload framework. The release reports 89 tokens per second at 10K context on a 48 GB VRAM device and 47 tokens per second at 32K context on a 128 GB M5 Max with the Q3\_K version, which scored within 0.4 points of the original model on benchmarks including DeepSWE v1.1.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** Hy4 flash is a 224B-parameter model that Tencent compressed through AngelSlim, its model-compression toolkit, and published as GGUF files for local inference. GGUF quantization stores weights at lower precision to reduce file size, with some benchmark degradation. Even the smallest Hy4 flash quantization is larger than a 64 GB Mac mini’s unified memory, so the Mac mini result relies on Strata offload letting the runtime use weights that do not all reside in RAM.

**「Offload cost: 64 GB works, but decode is slow」** The practical consequence is that 64 GB unified-memory Macs can host the smallest IQ2-AH build only through Strata offload, and at throughput well below Tencent&\#x27;s GPU figures: the released GGUF model card reports 17.3 tok/s decode and 125–127 tok/s prefill at 8K context with MTP k=2 on an M4 Pro Mac mini with 64 GB, versus 89 tok/s generation on a 48 GB VRAM device in Tencent&\#x27;s own figures. Users should therefore treat the &quot;runs on a 64 GB Mac mini&quot; claim as a capacity statement rather than a speed one, and benchmark with their own context length and prompt mix, since the card notes its results use different test conditions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ithome.com/1/032/131.htm">让大模型跑在个人设备上，腾讯混元开源 Hy 4 flash GGUF ...</a></li>
<li><a href="https://huggingface.co/AngelSlim/Hy4-flash-GGUF">AngelSlim/ Hy 4 - flash -GGUF · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#open-source models`, `#model quantization`, `#GGUF`, `#local inference`, `#Tencent Hunyuan`

---

<a id="item-tech-news-10"></a>
### [Minecraft Java RCE via crafted server resource-pack fonts; no official patch yet](https://github.com/bikini/minecraft2shell) ⭐️ 7.0/10

Minecraft Java Edition versions 1.20.5 through 1.21.10 and snapshots 26.1 through 26.4 are affected by a remote-code-execution flaw publicly disclosed on November 22 as minecraft2shell: a crafted TrueType font delivered in a server resource pack triggers a native out-of-bounds write in FreeType 2.14.3 and earlier and can execute arbitrary code in the 26.3 Windows client. Versions 1.20.4 and earlier and Bedrock Edition are reported unaffected. Mojang has no patch and still ships lwjgl-freetype 3.4.3, while a community fix, m2sfix 1.0.0 released November 24, disables font hinting through a Java agent or mod. The account comes from the public disclosure and a brief Telegram report; no official advisory or independent verification is cited.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** Minecraft Java renders TrueType fonts through the bundled FreeType library, reached via lwjgl-freetype. The disclosed proof of concept targets the Mojang-signed Minecraft Java 26.3 Windows client with FreeType 2.14.3 x64, so the flaw sits in that native font-rendering path rather than in Java code.

**「Impact」** Until an official patch exists, the disclosure advises players not to add resource packs and to set multiplayer server resource-pack permissions to &quot;Disabled,&quot; or to install m2sfix; because the malicious font arrives through a server-supplied resource pack, users on affected 1.20.5+ clients can be exposed by servers they join, not only by packs they choose themselves.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>

</ul>
</details>

**Tags**: `#Minecraft`, `#RCE`, `#vulnerability`, `#FreeType`, `#security`

---

<a id="item-tech-news-11"></a>
### [Samsung, SK Hynix reportedly to license YMTC&\#x27;s Xtacking NAND stacking tech](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

Samsung Electronics and SK Hynix have reportedly agreed, through a cross-licensing arrangement, to adopt parts of Yangtze Memory Technologies&\#x27; Xtacking technology in their 3D NAND flash production. All three companies declined to comment, so the scope, terms, and timing of any agreement remain unconfirmed. Xtacking manufactures the memory cells and the CMOS control circuitry on two separate wafers and joins them with a bonding step, allowing each part to be produced and optimized independently. An Omdia senior analyst cited in the report said this lets a manufacturer build the memory array itself while assigning the logic circuitry to a foundry, giving access to more advanced process nodes than conventional NAND manufacturing would allow.

telegram · zaihuapd · Nov 25, 14:33

**「背景：Xtacking 如何工作」** Xtacking 是长江存储自 2018 年起展示的 3D NAND 设计：它将存储单元晶圆与外围逻辑电路分开制造，再通过晶圆对晶圆的混合键合堆叠在一起，使两部分能够独立优化。其第四代方案延续了这一思路；这种分工也使厂商可以把逻辑电路交由晶圆代工厂生产，从而采用更先进的制程。

**「Impact」** Memory makers and their foundry partners would gain a production-planning option: NAND arrays could be built in-house while the CMOS logic is assigned to a foundry, allowing the logic side to use a more advanced process. Because Samsung, SK hynix, and YMTC declined to comment and no licensing terms, scope, or timeline were disclosed, customers and partners cannot yet treat the reported cross-license as a committed supply-chain change.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/samsung-and-sk-hynix-tap-ymtcs-xtacking-tech-in-cross-license">Samsung and SK Hynix cross-license YMTC&#x27;s Xtacking 3D NAND</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking ...</a></li>

</ul>
</details>

**Tags**: `#semiconductor manufacturing`, `#3D NAND`, `#Xtacking`, `#memory industry`, `#cross-licensing`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Commerce Department reportedly warned Intel of &\#x27;consequences&\#x27; before 10% stake deal](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

According to WIRED and court documents, a U.S. Commerce Department lawyer told Intel&\#x27;s chief financial officer in an August 2025 call not to &quot;mistake this for a negotiation,&quot; saying the board could refuse but warning of unpredictable consequences — days before the board handed over the shares. President Trump then announced the U.S. government &quot;fully owns and controls&quot; 10% of Intel, which it did not pay for and which is now worth about $11 billion, per the report.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** The disclosure concerns a deal the Trump administration announced in August 2025, when Commerce Secretary Howard Lutnick said the federal government would take a 10% stake in Intel and Intel confirmed an agreement with the administration.

**「Impact」** For Intel, the stake makes the U.S. government a part-owner of a company whose factory, export and investment decisions are central to U.S. chip policy — an equity holding that the New York Times notes has otherwise been rare and largely confined to crisis rescues such as the 2008 bailouts of General Motors, Chrysler and AIG.

<details><summary>References</summary>
<ul>
<li><a href="https://www.intel.com/content/www/us/en/newsroom/news/corporate/intel-and-trump-administration-reach-historic-agreement.html">Intel and Trump Administration Reach Historic Agreement to ...</a></li>
<li><a href="https://apnews.com/article/trump-intel-us-equity-stake-b538526b6698f7ebd31e99effd727693">Trump says US to get stake in Intel | AP News</a></li>
<li><a href="https://www.bbc.com/news/articles/cvg3zpdl3xdo">US government announces 10% stake in chipmaker Intel - BBC</a></li>
<li><a href="https://www.nytimes.com/2025/11/25/us/politics/trump-intel-steel-minerals-china.html">Trump Administration Is Taking Billions in Stakes in Firms Like Intel ...</a></li>

</ul>
</details>

**Tags**: `#英特尔`, `#美国商务部`, `#政府持股`, `#半导体政策`, `#工业政策`

---

<a id="item-finance-news-2"></a>
### [U.S. Plans New Section 301 Tariffs on 14 Trading Partners](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

The U.S. government plans to impose country-specific tariffs on 14 trading partners, including China, the EU, Japan and India, under Section 301 of the 1974 Trade Act, CNBC reported. Chinese goods would face an additional 20% on top of existing 25% duties, a rate that could rise to 40% if China does not comply with the October 2025 trade truce reached in Busan, the report said.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** Section 301 is a U.S. trade law that allows tariffs after a finding of unfair foreign trade practices.

**「Impact」** U.S. importers of affected manufactured goods, especially from China, would face higher import costs because the new China duty stacks on the existing 25%.

**Tags**: `#美国贸易政策`, `#Section 301`, `#关税`, `#中美贸易`, `#全球供应链`

---

<a id="item-finance-news-3"></a>
### [Jensen Huang Returns to Nvidia as U.S.-China AI Talent Race Widens](https://www.cnbc.com/2026/11/25/jensen-huang-nvidia-ai-talent-race.html) ⭐️ 7.0/10

Jensen Huang returned as Nvidia&\#x27;s CEO on Nov. 23, about 11 days after resigning, and the episode is being framed as evidence that the U.S.-China AI rivalry extends beyond chips to engineering talent. China surpassed the U.S. in share of global AI talent within three years, according to Carnegie Endowment research cited by CNBC.

rss · CNBC Finance · Nov 25, 14:29

**「Background」** Huang resigned on Nov. 12 after reports of an affair with a woman U.S. intelligence reportedly believed had links to Chinese intelligence, and Nvidia&\#x27;s board reinstated him on Nov. 23 after President Donald Trump personally intervened with the board.

**「Impact」** Nvidia investors saw the chipmaker’s market value jump by more than $950 billion in a single day after Huang’s reinstatement, according to trading data, a gain that returned it to second place globally by market capitalization.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/technology/nvidia-reinstates-jensen-huang-ceo-2026-11-23/">Huang returns as Nvidia CEO after Trump intervention in ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/trump-nvidia-jensen-huang.html">Jensen Huang: Trump sealed deal for Nvidia CEO return - CNBC</a></li>
<li><a href="https://sputnikglobe.com/20261124/nvidia-market-cap-adds-almost-1trln-after-huangs-return---trading-data-1125138619.html">Nvidia Market Cap Adds Almost $1Trln After Huang &#x27;s Return - Trading...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#US-China relations`, `#AI talent`, `#semiconductors`, `#executive leadership`

---

<a id="item-finance-news-4"></a>
### [SpaceX to Forgo $738 Million in Federal Broadband Subsidies, Offer Free Starlink Hardware Instead](https://x.com/SawyerMerritt/status/2125314062997467640) ⭐️ 7.0/10

SpaceX has agreed to give up $738 million in US federal broadband subsidies under the NTIA&\#x27;s BEAD program and instead supply free Starlink terminals to eligible households, with federal funding set at $0. Per the reported terms, SpaceX must guarantee minimum speeds of 100 Mbps download and 20 Mbps upload, offer low-cost monthly plans, and commit to 10 years of service, while being exempted from most financial audit and procurement reporting; the arrangement has not been confirmed by NTIA documentation and was relayed via a social media post.

telegram · zaihuapd · Nov 25, 02:17

**「Background」** BEAD is a federal broadband expansion program run by the National Telecommunications and Information Administration \(NTIA\), and Starlink is SpaceX&\#x27;s satellite-internet unit. NTIA&\#x27;s Arielle Roth confirmed that SpaceX would decline roughly $738 million in BEAD subsidies while still serving Starlink locations, according to Teslarati.

**「Who is affected」** Eligible rural households covered by the agreement would get Starlink hardware at no upfront cost but would still pay a discounted monthly subscription for service meeting the 100 Mbps download / 20 Mbps upload standard for 10 years, shifting the equipment cost onto SpaceX instead of the federal subsidy.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Starlink">Starlink - Wikipedia</a></li>
<li><a href="https://www.teslarati.com/spacex-starlink-rejects-fed-subsidy/">SpaceX rejects $ 738 M fed subsidy , betting on Starlink alone</a></li>

</ul>
</details>

**Tags**: `#telecom policy`, `#BEAD program`, `#SpaceX`, `#Starlink`, `#federal subsidies`

---