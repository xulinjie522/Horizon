---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 10 items, 3 important content pieces were selected

---

**Technology News**
1. [Anthropic&\#x27;s data-center power projected at 87% gas, 11% coal in 2028](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI Post Links Perplexity to Model Intelligence, Sparking Debate](#item-tech-news-2) ⭐️ 7.0/10

**Technology Blog**
1. [When in Doubt, Flail: Experimenting Under Uncertainty](#item-tech-blog-1) ⭐️ 6.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Anthropic&\#x27;s data-center power projected at 87% gas, 11% coal in 2028](https://betterdatacenterproject.com/2026/11/16/how-ai-is-powered-a-breakdown-of-byop-and-grid-power/) ⭐️ 7.0/10

A Better Data Center Project analysis discussed on Hacker News projects that 87% of Anthropic&\#x27;s data-center power will come from natural gas and 11% from coal in 2028. The figures are a forecast for the company&\#x27;s future power sourcing, not measured operating data or a confirmed Anthropic commitment. The surrounding discussion focuses on AI infrastructure&\#x27;s energy use, local pollution and regulation.

hackernews · happosai · Nov 22, 08:57 · [Discussion](https://news.ycombinator.com/item?id=50597612)

**「Why leased capacity sets Anthropic&\#x27;s fuel mix」** Anthropic does not build most of its own data centers; it leases capacity, including an arrangement for xAI&\#x27;s Colossus 1 cluster in the Memphis, Tennessee–Southaven, Mississippi area, where on-site gas turbines have drawn complaints about local air pollution. Because that compute is contracted rather than owned, the fuel mix of the facilities Anthropic rents — not its own procurement — is what drives its projected 2028 power profile.

**「Impact」** Under the projected 2028 mix, 87% of Anthropic’s data-center power would come from gas and 11% from coal, so communities hosting those sites and the grids serving them would absorb most of the emissions and demand growth from Anthropic’s compute expansion. Buyers and regulators evaluating that compute footprint should treat it as fossil-dominated through 2028, not as a renewable-backed load.

**「Community discussion」** Commenters criticized Anthropic over its leasing of Colossus 1 and what they described as local pollution in Memphis, with one arguing the company has made no US renewable commitments; others said regulation is needed because environmental and social costs are otherwise externalized. A separate thread debated the scale of data-center energy use and the role of shale-gas byproducts and flaring.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Colossus_%28data_center%29">Colossus ( data center ) - Wikipedia</a></li>
<li><a href="https://www.thebureauinvestigates.com/stories/2026-08-14/misaligned-colossus-musks-data-empire-anthropic">How Musk’s toxic data empire is powering Anthropic ’s… | TBIJ</a></li>
<li><a href="https://nextomoro.com/compute-rent/">Compute rent: what the Anthropic -xAI Colossus deal... | nextomoro</a></li>
<li><a href="https://betterdatacenterproject.com/2026/11/16/how-ai-is-powered-a-breakdown-of-byop-and-grid-power/">How AI is powered : a breakdown of BYOP and grid power</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#data centers`, `#energy`, `#environmental impact`, `#Anthropic`

---

<a id="item-tech-news-2"></a>
### [OpenAI Post Links Perplexity to Model Intelligence, Sparking Debate](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI has published a post discussing perplexity—the degree of surprise a language model shows when predicting the next token—as a measure connected to model intelligence. The supplied material does not include the post&\#x27;s text, so its specific evidence, benchmarks, or quantitative claims cannot be verified here. The piece nonetheless prompted detailed technical discussion about cross-entropy loss, evaluation benchmarks, and prediction-based views of intelligence.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** Perplexity is a standard language-modeling metric that gauges how surprised a model is when predicting each next token; lower is better, with a perfect predictor scoring 1 and a random predictor approaching the vocabulary size. OpenAI&\#x27;s post connects this training-time measure to broader model intelligence, which is why the argument invites scrutiny of how prediction quality relates to capability.

**「Community Discussion」** Commenters debated the post&\#x27;s framing: hazrmard noted that perplexity was not defined in the article and explained it as next-token surprise bounded by vocabulary size, while jrflo called the apparent cross-entropy trend surprising given increasing use of RL and welcomed a simpler benchmark. tensor questioned claims that abilities &quot;emerge&quot; at particular perplexities, arguing that task-specialized smaller models may have high perplexity on other tasks, and d\_burfoot endorsed the view that prediction or compression rate on raw data captures progress toward intelligence.

**Tags**: `#perplexity`, `#language-models`, `#model-evaluation`, `#machine-learning`, `#OpenAI`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [When in Doubt, Flail: Experimenting Under Uncertainty](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** When an engineer faces a situation with no clear guidance and no obvious path forward, the instinct is to wait until the situation is better understood. Sean Goedecke argues the opposite: in ambiguous situations, the faster route to understanding is usually to act.

**「Solution」** His heuristic is to &quot;flail&quot;: try many different things, watch feedback extremely carefully, and ruthlessly drop whatever isn&\#x27;t drawing positive response. Volume matters for three reasons. It gives direct contact with reality, like a caveman pressing every button on an iPhone; most plans will be bad, so you need many attempts for one to work; and holding ten plans keeps you from over-investing in any single one. Goedecke applies this to three settings. Product flailing suits features without product-market fit — at GitHub Models, an integration letting AI inference run from a GitHub Actions token was unexpectedly sticky and seeded &quot;Continuous AI.&quot; Engineering flailing beats studying a huge, tangled system end to end; instead make speculative changes and keep only what looks like an improvement, a task he notes AI agents now help with. Organizational flailing suits senior and staff engineers facing non-technical problems: automate manual work, volunteer for tasks, propose long-term plans. The author concedes the risk: flailing badly damages reputations in tech companies, and feedback discipline matters most in the organizational case, where dropping a failing plan builds trust while pressing on directs others&\#x27; frustration at you.

**「Takeaway」** Goedecke&\#x27;s point is that the uncomfortable sense of flailing is a psychological barrier rather than a warning sign: so long as you stay sensitive to feedback and abandon plans that fail, broad experimentation is often the quickest way to become useful in unclear situations.

**Tags**: `#engineering judgment`, `#experimentation`, `#feedback loops`, `#organizational dynamics`, `#product development`

---