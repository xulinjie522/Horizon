---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 44 items, 16 important content pieces were selected

---

**Technology News**
1. [SemiAnalysis: Trainium3 beats GB300 on inference cost per token, trails Vera Rubin](#item-tech-news-1) ⭐️ 8.0/10
2. [Linux NFS server flaw CVE-2026-99362 allows pre-auth root access](#item-tech-news-2) ⭐️ 8.0/10
3. [Card-skimming scripts use WebRTC to evade detection on shopping sites](#item-tech-news-3) ⭐️ 7.0/10
4. [Debate over false computer-checked proofs and verifier soundness](#item-tech-news-4) ⭐️ 7.0/10
5. [State attorneys general sue SpaceX over Grok&\#x27;s alleged sexual image generation](#item-tech-news-5) ⭐️ 7.0/10
6. [Essay argues for a formally verifiable mainstream programming language](#item-tech-news-6) ⭐️ 7.0/10
7. [Inkling-2-Mini-Cyber GGUF adds 0.0065% LoRA for security work](#item-tech-news-7) ⭐️ 7.0/10
8. [AMD RDNA llama.cpp patch reports large prefill, decode gains](#item-tech-news-8) ⭐️ 7.0/10
9. [169 MB talkinghead model gives local voice assistants a lip-synced face](#item-tech-news-9) ⭐️ 7.0/10
10. [Microsoft CEO says new-grad hiring slowed as AI budgets come first](#item-tech-news-10) ⭐️ 7.0/10
11. [Hackers reportedly used AI tool Artex against CIA and other US intelligence agencies](#item-tech-news-11) ⭐️ 7.0/10
12. [Minecraft Bedrock resource-pack flaw affects 26.52–26.63; 26.65 fixes it](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [S&amp;P 500 enters correction, 11.6% below October record](#item-finance-news-1) ⭐️ 7.0/10
2. [China State Council Pledges Stronger Market-Stabilization Role for Central Huijin](#item-finance-news-2) ⭐️ 7.0/10
3. [Report: DeepSeek raises RMB 100–105.5 billion; Mixue invests RMB 500 million](#item-finance-news-3) ⭐️ 7.0/10
4. [PBOC lowers minimum purchase thresholds for large-denomination CDs](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [SemiAnalysis: Trainium3 beats GB300 on inference cost per token, trails Vera Rubin](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 8.0/10

SemiAnalysis published a Trainium3 deep dive reporting that AWS&\#x27;s accelerator, run in a &quot;PDS&quot; configuration with vLLM, achieves better performance per TCO than every other accelerator it tested except Nvidia&\#x27;s Vera Rubin across the throughput-versus-p90-interactivity frontier, and trades blows with or beats Nvidia GB300 on cost to generate tokens. The numbers come from the publication&\#x27;s InferenceX suite, which now lists Trainium3 alongside TPUv7, Nvidia Rubin NVL72, AMD hardware and OpenAI&\#x27;s Jalapeño, plus AgentX, which replays recorded coding-agent sessions against a Trainium3 server for an end-to-end agentic workload. SemiAnalysis credits microarchitecture as well as AWS&\#x27;s supply chain: its Trainium Descriptor Generation Engines, the counterpart to Nvidia TMA and AMD MI455X TDM, reach peak HBM bandwidth utilization at small message sizes, which the authors say is not possible on Nvidia GPUs. AWS Annapurna Labs staff, including co-founder Nafea Bshara and Trainium chief architect Ron Diamant, helped validate the experiments, so these are vendor-collaborated benchmarks rather than independent measurements.

rss · Semianalysis · Nov 27, 15:54

**「How Trainium differs from GPU lineage」** Trainium is AWS&\#x27;s in-house machine-learning accelerator, designed by its Annapurna Labs chip team and now in its third generation. Nvidia&\#x27;s datacenter GPUs descend from graphics processors, with each generation bolting on dedicated AI hardware — Volta&\#x27;s Tensor Cores, Hopper&\#x27;s TMA for tile movement between HBM and SRAM, and Blackwell&\#x27;s Tensor Memory for accumulation — while SemiAnalysis describes Trainium as designed from the ground up around tiles as a first-class primitive rather than a sea of threads with tensor engines added on. The tradeoff the piece notes is software: this tile-first design was historically a major programming burden that the authors argue is no longer the case.

**「Impact」** The reported cost advantage is tied to a specific software path — Trainium3 PDS plus vLLM — and the piece notes that software complexity, long a weakness of the tile-first design, is now described as no longer a major obstacle; teams comparing accelerators should therefore match serving stacks before drawing conclusions from perf-per-TCO curves. The cycle-level microbenchmarks behind the claims \(SBUF-to-PSUM latency and bandwidth, rack-scale bandwidth, attention head\_dim effects on roofline percentage\) are published through the open-source UBenchX and InferenceX repositories, giving capacity planners reproducible data rather than only headline ratios.

<details><summary>References</summary>
<ul>
<li><a href="https://ca.finance.yahoo.com/news/aws-annapurna-labs-global-ai-100500331.html">AWS Annapurna Labs Global AI, Compute, Data, and Quantum...</a></li>

</ul>
</details>

**Tags**: `#AI hardware`, `#AWS Trainium`, `#microarchitecture`, `#inference`, `#Nvidia GPUs`

---

<a id="item-tech-news-2"></a>
### [Linux NFS server flaw CVE-2026-99362 allows pre-auth root access](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec has disclosed CVE-2026-99362, a CVSS 9.8 pre-authentication heap overflow in the Linux kernel&\#x27;s NFS server \(nfsd\) that lets an unauthenticated attacker write out of bounds via a single connection to tcp/2049 and potentially obtain a root shell. The flaw dates to Linux 3.16 \(2014\) and affects hosts with NFSv4.1 or 4.2 enabled, including file servers, NAS devices, and cluster storage nodes. Fixes are available in kernel 6.12.117, 6.18.61, 7.3.2, and 7.4-rc1; operators must upgrade and reboot, or restrict tcp/2049 at the firewall if they cannot patch immediately. The CVE was made public on November 20, 2026, though the Telegram relay does not include a direct advisory or patch reference for independent verification.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** NFS servers expose filesystems to clients through the kernel&\#x27;s nfsd, and this flaw sits in the NFSv4.1/4.2 handling reachable over TCP port 2049 before any login. OpenSec&\#x27;s write-up and subsequent coverage describe it as a 12-year-old defect present since Linux 3.16, which is why remediation requires upgrading the kernel and rebooting rather than only restarting a userspace service.

**「Operational impact」** Any host that serves NFSv4.1 or 4.2 — the default on modern kernels — with tcp/2049 reachable is exposed; per OpenSec&\#x27;s write-up, a single TCP connection lets an unauthenticated attacker write 61 bytes past a kernel heap object in nfsd while handling NFSv4 SEQUENCE replies, which can be chained into a root shell. Operators must upgrade to a fixed kernel and reboot, since the flaw lives in the running kernel; where a reboot is not immediately possible, the only interim mitigation given is blocking tcp/2049 at the firewall, which also cuts off legitimate NFS clients.

<details><summary>References</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://dbu.gs/vulnerability/PT-2026-151543">CVE - 2026 - 99362 — Vulnerability in Linux Kernel | dbugs</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#CVE-2026-99362`, `#remote root exploit`, `#security patching`

---

<a id="item-tech-news-3"></a>
### [Card-skimming scripts use WebRTC to evade detection on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A security report describes card-skimming scripts on popular shopping sites that use WebRTC to evade detection while collecting and exfiltrating payment-card data. The supplied material does not identify the affected merchants or scripts and provides no independent corroboration, so the campaign’s scope and prevalence remain unverified. The report attributes the technique to evasion of monitoring; it does not quantify how widely it is deployed.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Earlier WebRTC skimmer」** WebRTC data channels were already documented as a skimmer channel earlier in 2026: an RH-ISAC threat-intelligence writeup reports that on 24 March 2026 Sansec researchers identified a payment skimmer using WebRTC data channels instead of conventional web requests to load malicious code and exfiltrate stolen payment data, bypassing traditional security controls. The technique&\#x27;s advantage is that it avoids the HTTP request paths most monitoring and Content-Security-Policy rules watch; the current campaign applies the same approach to checkout pages on major retail sites.

**「CSP won&\#x27;t close the gap」** For e-commerce operators, the practical consequence is that a Content-Security-Policy \`connect-src\` directive does not govern WebRTC peer connections, so a CSP that successfully restricts fetch and XHR exfiltration can still leave \`RTCPeerConnection\` channels open; WebRTC traffic is DTLS-encrypted UDP and therefore not visible to HTTP-layer security tooling. That shifts the burden to runtime inventory and monitoring of third-party scripts — analytics, chat widgets, and A/B testing tools being common injection vectors — rather than to static policy alone, according to the cited analyses.

**「Community discussion」** Commenters argued that WebRTC is mainly an evasion choice rather than a new exfiltration mechanism, with one saying ordinary HTTP requests could accomplish the same theft and another speculating that a site’s connect-src CSP may simply have omitted WebRTC. The thread traced the underlying exposure to third-party JavaScript, arguing that any shop embedding outside scripts remains vulnerable regardless of the transport used.

<details><summary>References</summary>
<ul>
<li><a href="https://rhisac.org/threat-intelligence/webrtc-based-payment-skimmer-targeting-ecommerce-sites-via-polyshell-vulnerability/">RH-ISAC | WebRTC-Based Payment Skimmer Targeting ECommerce ...</a></li>
<li><a href="https://vibewshield.com/news/webrtc-skimmer-bypasses-csp-steal-payment-data">WebRTC Skimmer Bypasses CSP to Steal Payment ... | VibeWShield</a></li>
<li><a href="https://rfxn.com/research/webrtc-skimmer-csp-bypass">WebRTC Skimmers : How Payment Thieves Bypass... | R-fx Networks</a></li>

</ul>
</details>

**Tags**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-4"></a>
### [Debate over false computer-checked proofs and verifier soundness](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

A linked page argues that computer-checked proofs can be false, and a Hacker News thread debates the practical risk. Commenters acknowledge soundness bugs have been found in proof checkers, including Lean and the original C Metamath verifier, but note that Metamath&\#x27;s set.mm and iset.mm databases require proofs to pass five independently created verifiers in five programming languages. One commenter cites a DeepMind researcher&\#x27;s proof that passed Lean and a then-week-old version of nanoda by exploiting a different bug in each, while arguing that misleading mathematicians would also require the input to survive informal review.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Proof checkers are supposed to reject invalid proofs, so a soundness bug—a defect that lets the checker accept a proof of False—undermines the assurance conveyed by a &quot;computer-checked&quot; label. In August 2026, Lean 4&\#x27;s kernel accepted a proof of False through a nested-inductive phantom-parameter bug, issue \#14576; a postmortem described how it was found and fixed. Leonardo de Moura&\#x27;s postmortem also notes that the related nanoda bug was reported by Jeremy Chen and fixed a week before the Lean bug was reported.

**「Impact」** For formal-verification users, the thread&\#x27;s concrete takeaway is that acceptance by one checker is not a guarantee; high-stakes results should be cross-checked with independently implemented verifiers, as Metamath&\#x27;s database rules already require. Commenters also argue the practical risk is low for most software because an exploited soundness bug must still hide a further problem in the verified program.

**「Community discussion」** dwheeler argues the page is misleading for systems that require multiple provers, pointing to Metamath&\#x27;s five independent verifiers, while gr\_norm says all known soundness bugs in long-standing checkers are rare enough to fit in a tweet and are good enough for most software. twotwotwo adds that one bad verification is far from misleading mathematicians, since multiple checkers and informal review must also fail.

<details><summary>References</summary>
<ul>
<li><a href="https://leodemoura.github.io/blog/2026-8-1-postmortem-for-kernel-soundness-bug-14576/">Postmortem for Kernel Soundness Bug #14576 — Leonardo de Moura</a></li>
<li><a href="https://essamamdani.com/blog/lean-4-soundness-bug-14576-postmortem">Lean 4 Soundness Bug #14576: What Broke the Kernel</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-5"></a>
### [State attorneys general sue SpaceX over Grok&\#x27;s alleged sexual image generation](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

Virginia Attorney General Jay Jones and a second state attorney general, Rayfield, filed suit against SpaceX — which the announcement describes as parent company of X, xAI and Grok — alleging that the Grok platform generated child sexual abuse material and non-consensual intimate images and promoted their creation. The supplied material contains no complaint text or underlying evidence, so the specific legal claims, the remedy sought and the total number of participating states remain unconfirmed. The action is a set of allegations, not an adjudicated finding, and it targets the corporate parent rather than xAI or Grok alone.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Background」** Grok Imagine is the image-generation tool named in the Oregon and Virginia complaints, which accuse SpaceX of violating state consumer protection laws, according to CNBC and NYT coverage. The complaints also argue that non-consensual sexualized images harm people beyond those depicted, while X Safety has said CSAM and non-consensual explicit images of real people are not allowed on X or Grok.

**「Where the lawsuits bite」** The suits are brought under state consumer protection law rather than content rules, so if the allegations are proven they could expose SpaceX to civil penalties and injunctions requiring changes to Grok&\#x27;s image-generation safeguards in Virginia and Oregon. They also test whether the parent company, SpaceX Super Intelligence, rather than xAI itself, carries liability for how the chatbot handles sexual imagery. The underlying claims remain allegations; the complaint and supporting evidence were not included in the supplied material.

**「Community discussion」** Commenters questioned how Grok could produce such material if it were already widely blocked, asking whether the model was unusually permissive or whether users had to deliberately trick it, and one argued the users generating the images should also face consequences. Another commenter said the requirement to link a Twitter account to use Grok would deter them from trying the model at all; these are reader speculation and personal reactions, not evidence about the allegations.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/23/oregon-virginia-spacex-grok-deepfake-lawsuits.html">SpaceX sued by 2 states over AI deepfake porn, Grok safety claims</a></li>
<li><a href="https://www.nytimes.com/2026/11/23/technology/spacex-lawsuit-ai-sexualized-images.html">SpaceX Sued By Oregon and Virginia Over A.I.-Generated...</a></li>
<li><a href="https://www.engadget.com/2325111/two-states-sue-spacex-over-sexually-explicit-grok-deepfakes/">Two States Sue SpaceX Over Sexually Explicit Grok Deepfakes</a></li>
<li><a href="https://www.theguardian.com/technology/2026/sep/03/elon-musk-ai-grok-child-porn-lawsuit">Child sexual abuse survivor alleges Elon Musk’s AI ... | The Guardian</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/spacex-faces-lawsuits-two-states-162425330.html">SpaceX Faces Lawsuits From Two States Over Grok AI Safety Failures</a></li>
<li><a href="https://www.engadget.com/2325111/two-states-sue-spacex-over-sexually-explicit-grok-deepfakes/">Two States Sue SpaceX Over Sexually Explicit Grok Deepfakes</a></li>

</ul>
</details>

**Tags**: `#AI regulation`, `#AI safety`, `#Grok`, `#content moderation`, `#platform liability`

---

<a id="item-tech-news-6"></a>
### [Essay argues for a formally verifiable mainstream programming language](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

Blaine Hansen&\#x27;s opinion essay argues that formal verification needs a mainstream programming language designed for it, rather than remaining confined to specialized tools and research languages. The post does not announce a new language, compiler, or release; it makes a design argument, and the Hacker News thread debates how it relates to Ada SPARK, Dafny, Verus, Why3, Frama-C, and TLA+. Commenters also discuss whether LLMs are making these tools more accessible and whether a verification-first language can achieve mainstream adoption.

hackernews · todsacerdoti · Nov 27, 05:22 · [Discussion](https://news.ycombinator.com/item?id=50663089)

**「Background」** Formal verification tools have existed for years, but largely as specialized ecosystems rather than features of mainstream languages. Why3, for example, is an INRIA proof-management layer used by Frama-C WP, GNATprove for SPARK Ada, EasyCrypt, and Creusot, and it relies on external provers such as Alt-Ergo, CVC4, and Z3. The essay’s proposal is therefore about making that kind of verification usable in a mainstream language, not inventing formal verification from scratch.

**「Practical path」** Teams that need verification today are more likely to get results by adopting an existing toolchain than by waiting for a new mainstream language: one commenter reported translating C repositories into SPARK, proving SPARK Silver \(absence of runtime errors\), and surfacing integer overflows at boundary values. A November 2026 paper presents a ten-step LLM-assisted Dafny workflow covering specification, invariant validation, and proof construction, indicating where tooling is trying to reduce the expertise barrier.

**「Community discussion」** A commenter with direct experience reports using Ada SPARK to translate C repositories and lift them to SPARK Silver, the absence-of-runtime-errors level, uncovering integer overflows for maintainers. Others argue that Dafny, SPARK, Why3, Verus, Frama-C, and TLA+ already address parts of the problem, and question whether “mainstream” can be a design goal rather than an outcome of adoption.

<details><summary>References</summary>
<ul>
<li><a href="https://why3.org/">Why3</a></li>
<li><a href="https://sota.io/blog/why3-eu-formal-verification-framework-inria-saclay">Why3: EU-Native Proof Framework — Frama-C, SPARK Ada ...</a></li>
<li><a href="https://arxiv.org/abs/2611.16886">[2611.16886] LLM-Assisted Verification in Dafny - arXiv.org</a></li>
<li><a href="https://arxiv.org/pdf/2611.16886v1">LLM-Assisted Verification in Dafny - arXiv.org</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#programming languages`, `#Ada SPARK`, `#LLM-assisted verification`, `#software correctness`

---

<a id="item-tech-news-7"></a>
### [Inkling-2-Mini-Cyber GGUF adds 0.0065% LoRA for security work](https://i.redd.it/84pq0qkkr14i1.png) ⭐️ 7.0/10

A Reddit author published Inkling-2-Mini-Cyber-GGUF, a modified build of thinkingmachines/Inkling-2-Mini for authorized cybersecurity research and CTI workflows. The edit is a rank-16 LoRA \(alpha=32\) trained on 20 attention-output tensors in layers 4–23—1.72M parameters, or 0.0065%—then spliced into the Q8\_0 GGUF weights with a NumPy script at scale 1.55 while all 128 MoE experts and 684 other tensors were copied unchanged. The release includes IQ4\_NL \(17.63 GB\), Q6\_K \(24.70 GB\) and Q8\_0 \(27.82 GB\) quants, a vision projector, and a 6.89 MB BF16 adapter, and the author says it runs in stock llama.cpp, Ollama and LM Studio. In the author’s self-reported IQ4\_NL benchmarks, MITRE-120 refusals fell from 100 to 1 \(68.3% full, 75.8% full+partial at 4K, versus 0%/0.8% stock\), and CTIBench CVE→CWE-100 scored 66.0%, which the post says beats Qwen3.8-27B.

reddit · r/LocalLLaMA · GodGMN · Nov 27, 00:16 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y6flvh/inkling2minicyber_surgical_00065_weight_edit_for/)

**「Background」** Inkling 2 Mini, the model this adapter patches, is Thinking Machines Lab&\#x27;s open-weight image-text-to-text model with 26B parameters, published in November 2026 on Hugging Face with a full model card. Horizon&\#x27;s November 21 digest reported that the release uses a looped transformer architecture sized for local inference and that a GGUF build from Unsloth already runs through Ollama or llama.cpp. That existing GGUF path is the relevant prior step: the author&\#x27;s LoRA is not merged into full-precision weights and re-converted, but spliced directly into already-quantized Q8\_0 attention-output tensors.

**「Practical effect for offline security workflows」** Teams wanting a local model for authorized security work can now get the altered refusal behavior from a 17.63 GB IQ4\_NL GGUF that runs in stock llama.cpp, Ollama, or LM Studio on a 24 GB GPU, with the 6.89 MB adapter and NumPy script letting them re-splice other quants. Because CyberSecEval&\#x27;s relevant test measures false refusals on borderline-but-benign prompts, the 100→1 figure is a false-refusal metric rather than a safety score, and since it is self-reported against a 120-prompt set the author describes as eval-disjoint from the SFT mix, teams should re-run their own harness before depending on it.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>
<li><a href="https://huggingface.co/thinkingmachines/Inkling-2-Mini">thinkingmachines/Inkling-2-Mini · Hugging Face</a></li>
<li><a href="https://meta-llama.github.io/PurpleLlama/CyberSecEval/docs/intro">Introduction | CyberSecEval 4</a></li>

</ul>
</details>

**Tags**: `#local LLM`, `#LoRA fine-tuning`, `#cybersecurity`, `#GGUF`, `#llama.cpp`

---

<a id="item-tech-news-8"></a>
### [AMD RDNA llama.cpp patch reports large prefill, decode gains](https://devnull.land/amd-specific-llama-cpp) ⭐️ 7.0/10

A community write-up documents a minimal llama.cpp patch, stew675/llama-cpp-rdna-boosts, intended to boost inference on AMD RDNA GPUs while retaining llama.cpp&\#x27;s broad model compatibility. On an R9700 running Q6\_K\_L Swift-1.5-Qwen3.8-27B, the write-up reports prefill rising from 700 to 1,300 tokens/s and decode from 35 to 55 tokens/s, which the Reddit post describes as roughly an 80% increase over unpatched llama.cpp. The results come from one card and have not been independently verified by the poster, who does not have an R9700 to test; the write-up also says purpose-built inference engines retain a slight edge.

reddit · r/LocalLLaMA · returnity · Nov 27, 20:38 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y73gcc/amdspecific_llamacpp_patch_nearly_doubles/)

**「Background」** llama.cpp is a general-purpose LLM inference engine valued for running a wide range of models across hardware, while purpose-built engines often trade that compatibility for model- or hardware-specific speed. The patch is distributed as a minimal diff against a pinned llama.cpp build and targets AMD RDNA GPUs specifically.

**「Deployment constraint」** AMD RDNA users who want the reported speedup must apply an out-of-tree patch to a clean llama.cpp checkout pinned at commit 9cffdcc80, which was re-based on 2026-09-02 from 0eadefebd, rather than getting the change by pulling upstream. That keeps llama.cpp&\#x27;s broad model compatibility but requires re-applying the patch as the project advances.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/stew675/llama-cpp-rdna-boosts">GitHub - stew 675 / llama - cpp - rdna - boosts · GitHub</a></li>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD-specific fork of llama . cpp | devnull.land</a></li>

</ul>
</details>

**Tags**: `#llama.cpp`, `#AMD RDNA`, `#LLM inference`, `#performance optimization`, `#local AI`

---

<a id="item-tech-news-9"></a>
### [169 MB talkinghead model gives local voice assistants a lip-synced face](https://v.redd.it/affuqdkfw64i1) ⭐️ 7.0/10

A builder released talkinghead, a 169 MB distilled model that turns one photo plus TTS audio into a lip-synced video for users running LLM and TTS pipelines locally without a server. The model, distilled from Ditto&\#x27;s roughly 2.2 GB checkpoints, is offered through a two-line Apache-2.0 Python API: \`Avatar\(&quot;photo.jpg&quot;\).speak\(&quot;tts\_output.wav&quot;, &quot;out.mp4&quot;\)\`. The builder reports 36.5 ms per frame on an M4 Pro and 38–40 ms on an M3 Pro via Core ML, where real time for 25 fps is 40 ms, and 40.3 ms on a 4 GB RTX 3050 Ti laptop via TensorRT. The stated limits are weaker lip sync than LatentSync—traded for about 13x less time per frame and 12x less GPU memory on an earlier build—and batching that adds up to roughly 120 ms of latency, so it renders files at real-time speed but is not yet a live stream; M1/M2 and Linux are untested.

reddit · r/LocalLLaMA · Affectionate\_Hat\_585 · Nov 27, 17:25 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y6yv05/169_mb_face_for_your_local_voice_assistant_one/)

**「What it&\#x27;s built on」** talkinghead is a distilled version of Ditto, an Ant Group talking-head model whose checkpoints run about 2.2 GB, so the release compresses an existing avatar generator into a 169 MB Core ML/TensorRT package rather than introducing a new architecture. Comparable lip-sync tools are typically hosted web services where you upload a face image and an audio track and download a rendered MP4, the workflow a fully local pipeline is meant to replace. The builder also positions the model against LatentSync on SyncNet lip-sync accuracy, trading some sync quality for substantially lower per-frame time and memory.

**「Impact」** Developers adding a face to a local LLM/TTS stack get a small, serverless deployment option, but must account for weaker lip sync and roughly 120 ms of batching latency; those on M1/M2 or Linux should run \`device\_report\(\)\` before relying on it because the builder has not tested those setups.

<details><summary>References</summary>
<ul>
<li><a href="https://fliki.ai/features/talking-photo">Free AI Talking Photo: Make Any Photo Talk Online</a></li>
<li><a href="https://magichour.ai/products/lip-sync">Free AI Lip Sync Video Generator Online (No Sign Up) | Magic Hour</a></li>

</ul>
</details>

**Tags**: `#local-ai`, `#lip-sync`, `#tts`, `#model-distillation`, `#coreml`

---

<a id="item-tech-news-10"></a>
### [Microsoft CEO says new-grad hiring slowed as AI budgets come first](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

Microsoft CEO Satya Nadella said on The Pragmatic Engineer podcast that new-grad hiring has slowed, describing a sequence in which companies redeploy existing staff, AI-native firms exhaust their AI budgets before adding the next human hire, and every company will eventually do the same. Microsoft&\#x27;s headcount fell to 223,000 as of June 30, down 5,000 over the year and the first annual decline since 2016, according to the report. The item also cites an MIT–Microsoft Research paper that found a 29% reduction in quarterly tech hiring at firms adopting GitHub Copilot, with junior roles most affected. Nadella had said at Davos earlier in the year that he still believed in campus recruiting; his podcast remarks acknowledge a shift but do not amount to a formal policy change or prove that AI spending caused Microsoft&\#x27;s headcount decline.

telegram · zaihuapd · Nov 27, 03:03

**「Background」** Earlier in the year, Nadella said at Davos that he still believed in campus recruiting, so his podcast remarks mark a shift in that position. The hiring context also includes a November 23 MIT and Microsoft Research paper that used GitHub Copilot adoption across 5,414 multinational firms as a natural experiment; it estimated a 29% quarterly fall in technical hiring a year after adoption, with junior software engineer hiring down about 40% while senior hiring stayed flat.

**「Tighter entry-level pipeline」** For entry-level candidates the concrete consequence is a narrower pipeline: Microsoft says it moves existing employees into open roles before backfilling externally, and the cited MIT/Microsoft Research study found the steepest hiring declines at junior levels, with 29% fewer quarterly tech hires at firms adopting GitHub Copilot. New graduates should expect to compete against internal redeployments rather than net-new openings, and to be assessed on how they work with AI tools; the 29% figure is a correlation measured across adopting firms, not a headcount reduction proven to be caused by Copilot.

<details><summary>References</summary>
<ul>
<li><a href="https://economics.mit.edu/sites/default/files/2026-11/AILaborDemand_06Nov2026.pdf">AI-Assisted Programming and Labor Demand - economics.mit.edu</a></li>
<li><a href="https://todayforai.com/en/items/art-b0db345b-a86">MIT and Microsoft Study Finds Copilot Cuts Junior Coder ...</a></li>
<li><a href="https://fourweekmba.com/ai-copilot-cut-junior-coder-hiring-about-40-study-finds/">Copilot Cut Junior Coder Hiring About 40%, Study Finds</a></li>

</ul>
</details>

**Tags**: `#AI and jobs`, `#Microsoft`, `#GitHub Copilot`, `#tech hiring`, `#labor market`

---

<a id="item-tech-news-11"></a>
### [Hackers reportedly used AI tool Artex against CIA and other US intelligence agencies](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

Hackers reportedly used an AI tool called Artex to target the CIA, the National Geospatial-Intelligence Agency, and the Office of the Director of National Intelligence, according to a New York Times report cited in the item. The reported impact was limited to non-classified reconnaissance data and did not appear severe. Artex, released earlier this year by a Chinese developer, combines multiple open-source AI models to test networks and computer defenses; it was later used in multiple attacks, including one against the EU, and the developer deleted it from GitHub after the FBI warned that criminals and spies were widely using it.

telegram · zaihuapd · Nov 27, 10:42

**「What ARTEX is and how it spread」** ARTEX is an AI-powered penetration-testing framework that chains multiple open-source AI models to probe network and host defenses. The FBI had already warned that criminals and spies were using it at scale, including in a ConnectWise supply-chain breach that compromised Microsoft 365 customer environments. Its original developer, posting in Chinese under the handle Autumn-27, removed the primary GitHub repository in October after the tool spread, according to Kursiv.

**「Impact」** The developer’s deletion of Artex from GitHub came after it had already been used in multiple attacks, including one against the EU, so the removal does not by itself show that the tool is out of circulation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/fbi-warns-artex-ai-hacking-tool-is-powering-global-cyberattacks/">FBI warns ARTEX AI hacking tool is powering global cyberattacks</a></li>
<li><a href="https://kz.kursiv.media/en/2026-11-27/engk-yeri-ai-hacking-tool-artex-spreads-globally-despite-creators-takedown/">FBI warns of AI hacking tool ARTEX as open-source copies proliferate</a></li>

</ul>
</details>

**Tags**: `#AI cybersecurity`, `#cyberattacks`, `#US intelligence`, `#open-source AI`, `#Artex`

---

<a id="item-tech-news-12"></a>
### [Minecraft Bedrock resource-pack flaw affects 26.52–26.63; 26.65 fixes it](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

Minecraft Bedrock versions 26.52 through 26.63 are affected by a resource-pack vulnerability in which packs containing a content.zipe file can modify Ore UI files and run hidden scripts. Developer 8Crafter disclosed the issue on Reddit on November 15, saying earlier versions may also be affected and that it covers PC, mobile, and console while Java Edition is unaffected. When players join a server or Realm with automatic resource-pack downloads enabled, they may receive a problem pack without manually installing it; 8Crafter listed deleting all saves, obtaining the player&\#x27;s IP, and, on Windows under certain conditions, opening arbitrary URIs or launching a batch file to download malware as possible exploits. Mojang has fixed the issue in version 26.65, and AxmBro released a read-only Windows detection tool that finds content.zipe but cannot determine whether a pack is malicious.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** Resource packs are content bundles that Bedrock can download automatically when a player joins a server or Realm, so a malicious pack can reach players without a manual install. According to the report, the packs can alter files in Ore UI, the game&\#x27;s interface framework, and run hidden scripts.

**「Impact」** Players joining servers or Realms with automatic resource-pack downloads enabled should update to 26.65, since the reported delivery path requires no manual installation. AxmBro&\#x27;s Windows tool can flag a content.zipe file but cannot tell users whether the pack is malicious.

**Tags**: `#Minecraft`, `#安全漏洞`, `#资源包`, `#基岩版`, `#补丁修复`

---

## Financial News

<a id="item-finance-news-1"></a>
### [S&amp;P 500 enters correction, 11.6% below October record](https://www.cnbc.com/2026/11/27/the-sp-500-is-in-a-correction-bear-markets-and-recessions-dont-always-follow.html) ⭐️ 7.0/10

The S&amp;P 500 fell into a correction on Nov. 20, closing at 6,910.39, or 11.6% below its Oct. 6 record of 7,818.93, after a 3.7% drop that day. Deutsche Bank strategist Henry Allen said the selloff differs from past bear markets because it has not coincided with a recession, worsening economic data, or a hawkish central-bank shift.

rss · CNBC Finance · Nov 27, 13:21

**「Background」** A correction is a decline of at least 10% from a recent high and a bear market is 20% or more, and CNBC reported that 8 of 13 S&amp;P 500 bear markets overlapped with NBER-defined recessions while 5 did not.

**Tags**: `#S&amp;P 500`, `#stock market correction`, `#recession risk`, `#Federal Reserve policy`, `#bear market history`

---

<a id="item-finance-news-2"></a>
### [China State Council Pledges Stronger Market-Stabilization Role for Central Huijin](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

China&\#x27;s State Council said on Nov. 27 that it will step up the &quot;national team&\#x27;s&quot; market-stabilization role and further optimize Central Huijin&\#x27;s quasi-&quot;stabilization fund&quot; function, while urging listed companies to increase dividends and buybacks. The meeting readout, chaired by Premier Li Qiang, set policy direction but did not specify new funding, measures, or a timeline.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** China&\#x27;s State Council is the country&\#x27;s cabinet, and the &quot;national team&quot; refers to state-backed investors that buy shares during market selloffs; Central Huijin, a state-owned holder of stakes in major financial institutions, has been used as a quasi stabilization fund to support prices.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>

</ul>
</details>

**Tags**: `#China capital markets`, `#State Council policy`, `#market stabilization`, `#Central Huijin`, `#long-term capital`

---

<a id="item-finance-news-3"></a>
### [Report: DeepSeek raises RMB 100–105.5 billion; Mixue invests RMB 500 million](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

A secondary Sohu report says DeepSeek completed a second funding round of roughly RMB 100–105.5 billion at about RMB 615.5 billion post-money valuation. Mixue Group subscribed RMB 500 million through a fund among 31 new investors, which the report says also include Tencent, CATL, China Mobile, and vivo; the round has not been officially confirmed.

telegram · zaihuapd · Nov 27, 06:33

**「Background」** DeepSeek&\#x27;s earlier first round, completed in June, raised about RMB 51 billion, and the company had initially set the second round&\#x27;s target at RMB 50 billion before raising it to roughly RMB 100 billion, according to The Information as cited by IT之家.

**「Impact」** Mixue’s RMB 500 million commitment, routed through a venture fund, gives the beverage company indirect exposure to DeepSeek and ties a slice of its balance sheet to a private AI asset rather than its main business.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ithome.com/1/020/251.htm">曝 DeepSeek 第二轮 融 资 1055 亿 元 ： 估 值 6155 亿 元 ， vivo ...</a></li>

</ul>
</details>

**Tags**: `#DeepSeek financing`, `#AI investment`, `#Mixue Group`, `#China private markets`, `#unconfirmed report`

---

<a id="item-finance-news-4"></a>
### [PBOC lowers minimum purchase thresholds for large-denomination CDs](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

The People&\#x27;s Bank of China on Nov. 27 published new rules for large-denomination certificates of deposit that lower the individual minimum purchase to 100,000 yuan from 200,000 yuan and the institutional minimum to 5 million yuan from 10 million yuan, effective March 21, 2027. The central bank also issued same-day rules on RMB deposit and loan rates requiring financial institutions to set rates independently and barring improper tactics such as attracting deposits with high interest.

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The new measures replace the PBOC&\#x27;s 2015 interim rules, which had set the 200,000-yuan individual and 10-million-yuan institutional thresholds that are now being halved; the revision also brings pricing across all stages of certificate-of-deposit business under the central bank&\#x27;s self-discipline regime.

**「Impact」** The lower individual threshold brings savers with 100,000 to 200,000 yuan into the product&\#x27;s eligible range, while the accompanying rate rules constrain how banks may compete for deposits.

<details><summary>References</summary>
<ul>
<li><a href="https://www.workercn.cn/papers/grrb/2026/06/15/4/grrb202606154.pdf">grrb0420260615C</a></li>

</ul>
</details>

**Tags**: `#China banking regulation`, `#PBOC`, `#large-denomination CDs`, `#deposit rates`, `#retail savings`

---