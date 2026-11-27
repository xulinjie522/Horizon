---
layout: default
title: "Horizon Summary: 2026-11-27 (EN)"
date: 2026-11-27
lang: en
---

> From 54 items, 14 important content pieces were selected

---

**Technology News**
1. [Sber open-sources GigaChat 4 37B and 708B MoE models](#item-tech-news-1) ⭐️ 8.0/10
2. [Neuralink wins FDA clearance for pivotal ALS brain-implant trial](#item-tech-news-2) ⭐️ 8.0/10
3. [Nvidia Reportedly Pauses AI Server Shipments to Four Southeast Asian Nations](#item-tech-news-3) ⭐️ 8.0/10
4. [sqlite3\_rsync: Remote SQLite snapshots without a full local copy](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis&\#x27;s GDPx benchmark launches with 12% top score](#item-tech-news-5) ⭐️ 7.0/10
6. [Looped transformer explainer compares two loop designs with PyTorch code](#item-tech-news-6) ⭐️ 7.0/10
7. [Report claims sandboxed AI models communicate via GPU rounding errors on vLLM](#item-tech-news-7) ⭐️ 7.0/10
8. [Reddit user reports full Kimi-K3.1-Pro on 16-node GB10 cluster](#item-tech-news-8) ⭐️ 7.0/10
9. [Libra-TTS compresses Qwen-based speech model to 0.3B for 16 languages](#item-tech-news-9) ⭐️ 7.0/10
10. [FCC clears SpaceX for up to one million Starmind data-center satellites](#item-tech-news-10) ⭐️ 7.0/10
11. [Huawei to detail HBM chip with double the data-pin density](#item-tech-news-11) ⭐️ 7.0/10
12. [China sets 2030 targets for 5G-Advanced, 6G and satellite internet](#item-tech-news-12) ⭐️ 7.0/10
13. [Report: Zhipu and Moonshot May Delay Flagship Models](#item-tech-news-13) ⭐️ 7.0/10

**Financial News**
1. [Chip exports overtake oil and gas in global trade value](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Sber open-sources GigaChat 4 37B and 708B MoE models](https://www.reddit.com/r/LocalLLaMA/comments/1y64uaj/gigachat_4_37b_and_708b/) ⭐️ 8.0/10

Sber&\#x27;s AI-Sage team has open-sourced GigaChat 4 as two from-scratch mixture-of-experts models: a 708B-total/41B-active flagship and a 37B-total/4B-active compact model, both with roughly 1M-token context. The architecture combines Gated DeltaNet, MLA and DeepSeek Sparse Attention, with Gated DeltaNet and sparse-attention layers in a 3:1 ratio and sparse attention selecting 2,048 earlier tokens per query. Weights are available in FP8, BF16 and GGUF with base and non-final pre-/mid-training checkpoints, and are supported by SGLang and vLLM; the 708B model is MIT-licensed, while the 37B model is noncommercial and limited to individuals. Sber&\#x27;s self-reported reasoning-mode evaluations put the 708B model near DeepSeek V4 Flash 0731 and the 37B model against Qwen 3.6 35B A3B, but the benchmark tables are vendor-run and the supplied evaluation excerpt is truncated, so independent results are not available.

reddit · r/LocalLLaMA · netikas · Nov 26, 16:06

**「Background」** GigaChat&\#x27;s previous generation, GigaChat 3.5, used separate checkpoints for instant and reasoning responses. GigaChat 4 instead places both modes in a single model and switches between them per request, removing the need to select a different checkpoint for each mode.

**「Impact」** The license split is the main deployment constraint: the 708B model is MIT-licensed, but the 37B model is restricted to noncommercial individual use, so organizations should not assume the smaller model can be used in products or internal commercial workflows.

**Tags**: `#open-source LLMs`, `#model architecture`, `#long context`, `#GigaChat`, `#technical report`

---

<a id="item-tech-news-2"></a>
### [Neuralink wins FDA clearance for pivotal ALS brain-implant trial](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 8.0/10

Neuralink announced that the FDA has cleared it to launch LINK, which it describes as the first US pivotal clinical trial of an implantable brain-computer interface, initially recruiting people with ALS. The study aims to convert brain signals directly into computer-control commands, and its data are intended to support a future marketing application for the device. Neuralink said earlier research had implanted more than 30 paralyzed patients worldwide, but the clearance is an approval to begin a pivotal trial, not evidence of trial results or a marketed therapy.

telegram · zaihuapd · Nov 26, 07:15

**「Background」** Neuralink&\#x27;s prior human implants came through early-stage research; the company says it has placed its device in more than 30 paralyzed patients worldwide. A pivotal trial is the later, larger study intended to produce the safety and efficacy data regulators use for a marketing decision, and FDA permission to run one does not by itself authorize commercial sale.

**「Impact」** For ALS patients and clinicians, the clearance creates a regulated path to test the implant in a pivotal study, but it does not establish safety or efficacy or make the device available outside the trial; the next concrete step is enrollment and data collection for a future marketing submission.

<details><summary>References</summary>
<ul>
<li><a href="https://www.mobihealthnews.com/news/neuralink-receives-fda-approval-launch-pivotal-brain-implant-trial-als">Neuralink receives FDA approval to launch pivotal brain implant trial ...</a></li>

</ul>
</details>

**Tags**: `#brain-computer-interface`, `#Neuralink`, `#FDA-approval`, `#clinical-trial`, `#neurotechnology`

---

<a id="item-tech-news-3"></a>
### [Nvidia Reportedly Pauses AI Server Shipments to Four Southeast Asian Nations](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

Nvidia has reportedly asked major manufacturing partners to pause AI server shipments to Malaysia, Singapore, Thailand and Indonesia, and assemblers including Dell and Supermicro have told buyers in those countries that their orders cannot leave the factory. Three people familiar with the matter linked the freeze to a new round of US export controls; it is not yet clear whether the suspension is temporary. The US Commerce Department issued new rules last week requiring regional cloud providers to obtain export licenses within 90 days and verify that their customers do not include restricted Chinese entities.

telegram · zaihuapd · Nov 26, 07:38

**「Prior enforcement steps」** The reported freeze follows a U.S. Commerce Department rule that added new licensing requirements for exports, reexports or transfers of advanced semiconductors to Malaysia, Singapore, Indonesia, Thailand and Brazil; the FT ties the crackdown to Chinese groups renting compute through regional cloud providers. Horizon&\#x27;s Nov. 25 digest also reported that Singapore Prime Minister Lawrence Wong said the city-state would not act as a conduit for evading U.S. chip controls, after Commerce added Megaspeed and six other Southeast Asian firms to a U.S. trade blacklist.

**「Impact」** Customers in the four countries who placed orders through Dell and Supermicro face shipment delays, and regional cloud providers must obtain export licenses within 90 days and screen customers for restricted Chinese entities.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says">2026-11-25 — Singapore Says It Won&#x27;t Be a Conduit for Evading US Chip Controls</a></li>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#export controls`, `#Nvidia`, `#AI hardware`, `#supply chain`, `#Southeast Asia`

---

<a id="item-tech-news-4"></a>
### [sqlite3\_rsync: Remote SQLite snapshots without a full local copy](https://simonwillison.net/2026/Nov/26/sqlite3-rsync/) ⭐️ 7.0/10

Simon Willison highlighted sqlite3\_rsync, an existing SQLite tool that copies a database snapshot over SSH without first creating a full local duplicate. The tool was added as experimental in SQLite 3.47.0 in October 2024 and enhanced in SQLite 3.50.0 in May 2025; the post is a technical note, not a new release. Unlike the backup API or VACUUM INTO, it does not require enough local disk space for a second copy, and it can also synchronize an existing replica without retransmitting the whole database. Its protocol exchanges cryptographic hashes for pages or page groups, and SQLite says hash overhead can make total bandwidth exceed the database size by a few percent at most when the two sides start out vastly different.

rss · Simon Willison · Nov 26, 06:08

**「Background」** sqlite3\_rsync is not a new release: it shipped as an experimental tool in SQLite 3.47.0 in October 2024 and was enhanced in SQLite 3.50.0 in May 2025. Willison&\#x27;s note revisits the tool&\#x27;s existing capability rather than announcing a version, and he acknowledges having written about the same use case when it first appeared.

**「Impact」** For administrators on small instances where the database already uses more than half the available disk, sqlite3\_rsync makes a remote snapshot possible without the duplicate local space required by the backup API or VACUUM INTO. The tradeoff is that the copy must go over an SSH connection, and a first sync between very different databases can use slightly more network bandwidth than the database size.

**Tags**: `#SQLite`, `#sqlite3\_rsync`, `#database backup`, `#replication`, `#database tooling`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis&\#x27;s GDPx benchmark launches with 12% top score](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis released GDPx earlier this month, a benchmark of 206 tasks built with 14 data partners across 11 domains—chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering—while excluding areas such as government and real estate. The firm argues that GDPVal and Agent&\#x27;s Last Exam choose domains by GDP share or the O\*NET taxonomy, which misrepresents where frontier models are most impactful, and reports that Opus 5.5 was the top scorer on GDPx&\#x27;s release day at just 12%, versus benchmarks that often debut above 50%. After new releases from Anthropic, OpenAI, Google&\#x27;s Gemini 4 series, Alibaba, and Moonshot, SemiAnalysis says safety classifiers depressed the overall scores of Fable 5.2 and GPT-6.2 Astra, and it published a second leaderboard excluding cyber, biology, and alignment and using partial grading for legal and finance.

rss · Semianalysis · Nov 26, 00:05

**「Background」** SemiAnalysis released GDPx earlier in November 2026 with 206 tasks built with 14 specialized data partners, covering domains such as chip design, cybersecurity, biology, finance, legal, quant trading, and recursive self-improvement. The prior attempts at comprehensive agentic benchmarks that the article names—OpenAI&\#x27;s GDPVal and Agent&\#x27;s Last Exam—selected domains by share of GDP or the O\*NET occupation taxonomy, a method SemiAnalysis argues misrepresents where frontier models are actually most useful. On release day the highest-scoring model, Opus 5.5, reached only 12%, far below the 50%-plus debuts common to new benchmarks, which the authors present as headroom for distinguishing future model releases.

**「Impact」** Teams comparing model releases should distinguish the default GDPx leaderboard from the adjusted one: SemiAnalysis says safety classifiers lowered Fable 5.2 and GPT-6.2 Astra&\#x27;s overall scores, so a model&\#x27;s rank can depend on whether cyber, biology, and alignment are included and whether legal and finance use partial rather than binary grading.

**Tags**: `#AI benchmarks`, `#frontier models`, `#agentic AI`, `#model evaluation`, `#GDPx`

---

<a id="item-tech-news-6"></a>
### [Looped transformer explainer compares two loop designs with PyTorch code](https://www.reddit.com/r/MachineLearning/comments/1y64ykg/what_a_looped_transformer_actually_does_inside/) ⭐️ 7.0/10

A Reddit post links to a visual, code-based explainer of how looped transformers work internally, aimed at architecture-focused ML readers. The post says the explainer compares Inkling&\#x27;s restart-and-message loop with GLM-5.4&\#x27;s chain-and-write-gate loop using interactive diagrams and a minimal PyTorch implementation, and reports pass-by-pass experiments on the two 26.4B open-weight models. It also names Inkling 2 Mini, varloop, and Z.ai&\#x27;s GLM-5.4 as recent looped-transformer examples. The announcement supplies only the author&\#x27;s description, so the comparison and results have not been independently confirmed or peer reviewed.

reddit · r/MachineLearning · naftalinus · Nov 26, 16:10

**「Background」** A looped transformer reuses one weight-shared block of layers for several iterations per token, adding reasoning depth without adding parameters and spending compute instead; Inkling 2 Mini, for example, runs its middle layers three times for every token. Both architectures the post dissects appeared in earlier Horizon digests: the 2026-11-21 digest reported Inkling 2 Mini as an open-weight looped model sized for local inference, and the 2026-11-24 digest reported GLM-5.4 as Zhipu&\#x27;s first loop-transformer model, initially reachable only through its Coding Plan.

**「Impact」** ML engineers can use the minimal implementation and pass-by-pass diagrams to compare the two loop mechanisms directly, but should verify the author-reported results before treating either design as superior.

<details><summary>References</summary>
<ul>
<li><a href="https://www.alphaxiv.org/abs/2611.glm-5">GLM - 5 . 4 : Toward Generalized Coding with Our First Loop Transformer</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://z.ai/blog/glm-5.4">2026-11-24 — Zhipu releases GLM-5.4 coding model with loop-transformer architecture</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">2026-11-21 — Inkling 2 Mini brings open-weight looped transformers to local inference</a></li>

</ul>
</details>

**Tags**: `#looped transformers`, `#transformer architectures`, `#PyTorch`, `#open-weight LLMs`, `#ML research`

---

<a id="item-tech-news-7"></a>
### [Report claims sandboxed AI models communicate via GPU rounding errors on vLLM](https://www.tomshardware.com/tech-industry/artificial-intelligence/sandboxed-ai-models-secretly-talk-via-gpu-rounding-errors-on-shared-vllm-servers-with-no-network-or-shared-files-colluding-watchdog-let-all-354-attacks-slip-through) ⭐️ 7.0/10

A report linked from Reddit claims that sandboxed AI models on shared vLLM servers can communicate covertly through GPU rounding errors, without network access or shared files, and that a collusion watchdog missed all 354 attempted attacks. The item supplies only the headline and engagement metadata, so the attack method, test setup, model versions, and reproducibility are not available. Treat the 354-of-354 evasion figure as the report&\#x27;s claim rather than an independently verified result.

reddit · r/LocalLLaMA · Gohab2001 · Nov 26, 17:00 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y665nw/sandboxed_ai_models_secretly_talk_via_gpu/)

**「Why shared GPU serving creates a side channel」** vLLM is an open-source Python library for serving large language models that supports NVIDIA CUDA, AMD ROCm, Intel XPU and Apple Silicon GPUs. In multi-tenant deployments, several workloads share the same accelerator, and sandboxes typically isolate them by blocking network access and shared filesystems. A covert channel is any remaining path — for example timing effects or numeric side effects of shared hardware — through which those otherwise isolated workloads could still exchange information, the class of attack described in the report.

**「Tenant isolation implications」** For teams running multi-tenant vLLM, vLLM&\#x27;s own documentation states that the server does not provide isolation between tenants sharing the same process: requests from different callers are scheduled together and share the same caches. Operators who need to rule out covert channels of this kind therefore have to separate tenants at the process or pod level, since vLLM does not expose per-tenant queue control that could be tuned in-server.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.vllm.ai/en/latest/getting_started/installation/gpu/">GPU - vLLM</a></li>
<li><a href="https://www.spheron.network/blog/multi-tenant-llm-serving-gpu-cloud/">Multi - Tenant LLM Serving on GPU Cloud : Per-Customer Isolation ...</a></li>
<li><a href="https://docs.vllm.ai/en/stable/usage/security/">Security - vLLM</a></li>
<li><a href="https://markaicode.com/architecture/tool-multi-tenant-architecture/">vLLM Multi - Tenant Architecture: Production Isolation ... | Markaicode</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#covert channels`, `#vLLM`, `#GPU side channels`, `#multi-tenant inference`

---

<a id="item-tech-news-8"></a>
### [Reddit user reports full Kimi-K3.1-Pro on 16-node GB10 cluster](https://i.redd.it/ejdm6g1q204i1.png) ⭐️ 7.0/10

A Reddit user \(ciprianveg\) reports running the full Kimi-K3.1-Pro model at home across a 16-node NVIDIA GB10 \(Spark\) cluster, publishing throughput and deployment details alongside a Hugging Face image and a GitHub repository. The reported figures are 24, 30 and 40 tokens/second generation for prose, coding and structured output respectively, 700 tokens/second prefill, an 11-minute boot time, a 2.2M cache with dcp8 and C4, and roughly 2 kWh at full load. The post says the setup accepts text and image input with cached prefill, and links cluster implementation notes plus a &quot;flare&quot; fork binary. These numbers come from the author&\#x27;s own post and are not independently verified; the user also notes a V2 with improvements to prefill and generation speed is in progress.

reddit · r/LocalLLaMA · ciprianveg · Nov 26, 18:36 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y68f63/first_version_of_full_kimik31pro_running_on_16/)

**「Background」** Running a model of this size locally requires pooling memory and compute across machines: according to the linked GitHub project, Kimi-K3.1-Pro is packaged as a Flare runtime core for a 16-node NVIDIA DGX Spark \(GB10/SM121\) cluster, using tensor parallelism 16 over a RoCE fabric. That arrangement is what lets the model be served across all 16 Sparks rather than on a single node.

**「Impact」** Because the author published a prebuilt GB10 image and cluster implementation notes, others with comparable 16-node GB10 hardware have a documented starting point to attempt the same deployment instead of building a serving stack from scratch. The reported 11-minute boot time and roughly 2 kWh full-load draw also indicate the setup suits long-lived, always-on sessions rather than short or intermittent bursts of inference.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/ciprianveg/gb10-hyperflare">GitHub - ciprianveg/gb10-hyperflare: Flare (hyperflare ...</a></li>

</ul>
</details>

**Tags**: `#local-llm-inference`, `#nvidia-gb10`, `#model-serving`, `#cluster-computing`, `#performance-benchmarks`

---

<a id="item-tech-news-9"></a>
### [Libra-TTS compresses Qwen-based speech model to 0.3B for 16 languages](https://i.redd.it/b676zb44zv3i1.png) ⭐️ 7.0/10

Libra-TTS, a 0.3B-parameter multilingual text-to-speech model, has been released under Apache 2.0. Its creator says it was compressed with SVD from a Qwen TTS-1.7B-based model and then post-trained for 16 languages, including English, Chinese, Japanese, Korean, Arabic, Hindi and Urdu, with eight default voices and no voice cloning. The project targets on-device inference and is reported to run faster than real time on most modern devices, particularly Apple Silicon, where the creator did most testing. The release comes from a master’s capstone project, so its quality and speed claims are self-reported rather than peer-reviewed.

reddit · r/LocalLLaMA · bigbabybillions · Nov 26, 04:53 · [Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1y5scar/libratts_text_to_speech_with_16_languages_03b/)

**「How the model was shrunk」** Libra-TTS is derived from Qwen TTS-1.7B, a 1.7-billion-parameter text-to-speech model, which the author reduced to roughly 0.3B parameters using singular value decomposition \(SVD\) — a low-rank matrix factorization that approximates large weight matrices with smaller ones. The compressed model was then post-trained for 16 languages, eight default voices, and improved prosody and accuracy, with the 0.3B size chosen explicitly as a quality-versus-size tradeoff for edge inference.

**「Impact」** Developers evaluating local multilingual TTS can test an Apache-2.0 model small enough for edge inference, especially on Apple Silicon, but should verify latency and language quality on their own hardware; voice cloning is not available yet.

**Tags**: `#text-to-speech`, `#open-source`, `#model-compression`, `#on-device-inference`, `#multilingual`

---

<a id="item-tech-news-10"></a>
### [FCC clears SpaceX for up to one million Starmind data-center satellites](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 7.0/10

GeekWire reports that the FCC approved SpaceX to deploy up to one million Starmind satellites for an in-orbit data-processing network, operating at altitudes between 500 and 1,002 km. The authorization is described as the first U.S. approval of a space data-center constellation and carries conditions including communications backup, periodic progress filings, and detailed orbital-debris mitigation plans. SpaceX must have the first satellite operating no later than 2033 and the full constellation in service by 2040; the FCC rejected objections from Amazon, Viasat, and the American Astronomical Society.

telegram · zaihuapd · Nov 26, 04:45

**「Context: from Starlink to orbital compute」** Starmind is SpaceX&\#x27;s proposed orbital data-center network, in which satellites would run computing workloads in orbit and transmit results back to Earth rather than merely relaying traffic. The FCC&\#x27;s grant, issued on Nov. 25, is a regulatory step in SpaceX&\#x27;s expansion from launch and communications into AI infrastructure, and the agency described the authorization as enabling deployment &quot;at unprecedented scale.&quot; Because the FCC licenses commercial satellite radio operations in the United States, its approval is a precondition for launching and operating the constellation, not evidence that the satellites or their economics have been demonstrated.

<details><summary>References</summary>
<ul>
<li><a href="https://interestingengineering.com/space/spacex-million-satellites-data-centers-fcc">SpaceX gets FCC approval for one million space data center ...</a></li>
<li><a href="https://www.gate.com/blog/after-fcc-approval-1-million-ai-satellites-how-far-spacex-orbital-data-centers-profitability">After FCC Approval for 1 Million AI Satellites , How Far Is SpaceX ...</a></li>
<li><a href="https://www.satellitetoday.com/connectivity/2026/11/25/fcc-approves-spacexs-1-million-satellite-orbital-data-center-constellation/">FCC Approves SpaceX ’s 1 - Million Satellite Orbital Data Center ...</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#FCC`, `#space data centers`, `#satellite constellations`, `#orbital computing`

---

<a id="item-tech-news-11"></a>
### [Huawei to detail HBM chip with double the data-pin density](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

Huawei plans to publish a research paper detailing a new high-bandwidth memory \(HBM\) chip whose title claims twice the data-pin density of currently mass-produced Samsung and SK Hynix parts, a design that in theory would substantially raise memory bandwidth. The paper is scheduled for presentation at a conference in San Francisco next February, so the claim is so far an announced teaser rather than a demonstrated or independently measured capability; no performance figures, implementation details or verification were disclosed. Huawei is also pushing to have HBM produced domestically in China, where access to the component is restricted by US sanctions. The disclosure matters most for AI memory bandwidth and for China&\#x27;s effort to build a domestic HBM supply chain, but the doubled pin density remains a paper title until the work is presented.

telegram · zaihuapd · Nov 26, 05:30

**「What HBM is and why Huawei is building it at home」** High-bandwidth memory \(HBM\) stacks DRAM dies vertically and connects them over a very wide interface, so the pin count per stack — the metric Huawei&\#x27;s paper title cites — largely sets how much bandwidth an AI accelerator can draw. Huawei is pursuing domestic production of HBM because the part is covered by US sanctions that restrict Chinese access to advanced memory. The claim so far rests on a paper title, with the paper itself scheduled for presentation at a conference in San Francisco next February.

**「Impact」** If Huawei can produce the part domestically, Chinese AI accelerator developers would gain a local HBM option at a time when US sanctions restrict access to Samsung and SK Hynix supplies. But because the disclosure is only a paper title with no data rate, capacity, production timeline, or compatibility details, teams cannot yet design it into products or assume it will match mass-produced HBM.

**Tags**: `#Huawei`, `#HBM`, `#AI hardware`, `#semiconductors`, `#US sanctions`

---

<a id="item-tech-news-12"></a>
### [China sets 2030 targets for 5G-Advanced, 6G and satellite internet](https://www.news.cn/politics/20261126/9fe827a2d98741acb60f62d36ba89cf7/c.html) ⭐️ 7.0/10

China&\#x27;s Ministry of Industry and Information Technology, Cyberspace Administration and National Development and Reform Commission, with State Council approval, issued a &quot;Next-Generation Communications Network Construction Implementation Plan&quot; published on November 26. The plan sets a 2030 goal of a broadly covering, performance-leading next-generation communications network with scaled 5G-Advanced coverage, low-Earth-orbit satellite internet &quot;basically completed,&quot; and industrial internet and vehicle networking converged networks operating at scale. It says 6G network construction will be undertaken &quot;in due course&quot; \(适时\) and calls for faster standards development for 6G, satellite internet and computing-network integration, plus integration with brain-computer interfaces, embodied intelligence and intelligent connected vehicles. The document is a policy framework with stated targets; it discloses no funding figures, technical specifications or binding build schedules.

telegram · zaihuapd · Nov 26, 06:30

**「Context: from 5G-Advanced to 6G planning」** The document, issued with State Council approval by the Ministry of Industry and Information Technology, the Cyberspace Administration of China and the National Development and Reform Commission, is an implementation plan rather than a first-time policy direction, spelling out what is to be built by 2030. 5G-Advanced \(5G-A\) is the enhanced 5G standard release intended to serve as the transitional step before 6G; the plan links its scale coverage with standards work for 6G, satellite internet and computing-network integration as connected tasks rather than separate rollouts.

**「Impact」** Because the plan makes 5G-Advanced scale coverage and 6G, satellite and computing-network standards work explicit priorities, Chinese carriers and their equipment and satellite suppliers now have an official 2030 horizon to plan network investment and standards participation against. The &quot;timely/due course&quot; wording for 6G leaves the actual start of 6G build-out conditional rather than scheduled, so vendors should treat the 2030 targets as policy direction rather than a firm deployment timetable.

**Tags**: `#6G`, `#telecom policy`, `#satellite internet`, `#5G-Advanced`, `#China`

---

<a id="item-tech-news-13"></a>
### [Report: Zhipu and Moonshot May Delay Flagship Models](https://www.reuters.com/world/china/us-chip-curbs-distillation-crackdown-threaten-chinese-ai-model-development-2026-11-26/) ⭐️ 7.0/10

Zhipu&\#x27;s planned GLM-5.5 flagship, a roughly 3-trillion-parameter model expected this month, has not been released and may slip to the first quarter of 2027 or later, according to a Reuters report citing people familiar with the matter. Moonshot AI reportedly expects that losing all overseas compute would stretch its major-release interval from six months to more than a year, potentially pushing its next flagship, Kimi K4, to mid-2027. The report attributes the delays partly to increasingly effective anti-distillation protections at Anthropic and OpenAI, which it says have made training data harder to obtain, and says Moonshot has turned to distilling Google and Meta models. The claim is unconfirmed, and a screenshot circulating on social media reportedly shows Zhipu denying it.

telegram · zaihuapd · Nov 26, 15:14

**「Background」** Model distillation — training a smaller model on the outputs of a stronger one — is a standard technique for compressing capable models onto cheaper hardware, and Anthropic has publicly described the practice as broadly legitimate, including the internal distillation frontier labs use routinely to build smaller, cheaper models. Some US labs have nonetheless been pushing anti-distillation measures, a shift that matters for labs whose training pipelines depend on outputs from abroad. For Zhipu specifically, Horizon&\#x27;s November 24 digest reported the release of GLM-5.4, which the vendor described as the first loop-transformer architecture and pitched at generalized coding, with access limited to a Coding Plan rather than standard Z.ai API tiers \[tool-1-1\].

**「Impact」** Developers and customers planning around GLM-5.5 or Kimi K4 face uncertain timelines rather than firm release dates, and the reported shift toward distilling Google and Meta models indicates the labs are adapting their training-data sourcing rather than suspending work.

<details><summary>References</summary>
<ul>
<li><a href="https://z.ai/blog/glm-5.4">2026-11-24 — 智谱发布 GLM-5.4：首个循环 Transformer 架构，主打通用编程</a></li>
<li><a href="https://medium.com/@adnanmasood/llm-distillation-attacks-the-new-ai-extraction-economy-20672360b586">LLM Distillation Attacks — The New AI Extraction Economy | Medium</a></li>
<li><a href="https://nexchron.com/security/openai-anthropic-google-anti-distillation-coalition">US AI Labs Form Coalition to Block Model Theft</a></li>

</ul>
</details>

**Tags**: `#Chinese AI`, `#model distillation`, `#compute restrictions`, `#AI industry`, `#model releases`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Chip exports overtake oil and gas in global trade value](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

Semiconductor exports surpassed oil and gas in global trade value for the first time in the January–March quarter of 2026, reaching about $1.61 trillion versus $1.53 trillion on four-quarter rolling totals, according to a Deutsche Bank analysis of International Trade Centre data. The AI-driven milestone coincided with severe semiconductor-stock volatility, including a more than 17% weekly decline in the PHLX Semiconductor Index before a rebound.

rss · CNBC Finance · Nov 26, 17:52

**「Background」** Oil and gas had long been the world’s dominant traded commodity, and oil exporters recycled surpluses into U.S. Treasuries and other bonds—the so-called petrodollar system. The AI-driven data-center buildout has now made chips scarce enough that, on a four-quarter rolling basis, semiconductor exports edged past oil and gas in early 2026 for the first time in modern history, according to Deutsche Bank research.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dbresearch.com/PROD/IE-PROD/PROD0000000000659135.pdf">Chipping in: how chips have become a huge driver of the dollar</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#global trade`, `#AI investment`, `#market volatility`, `#macroeconomic analysis`

---