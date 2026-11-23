---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 27 items, 5 important content pieces were selected

---

**Technology News**
1. [OpenAI examines perplexity as an intelligence measure, prompting benchmark debate](#item-tech-news-1) ⭐️ 7.0/10
2. [FT Report Alleges Prince Group Figure Helped Smuggle Nvidia Chips to China](#item-tech-news-2) ⭐️ 7.0/10

**Technology Blog**
1. [When in Doubt, Flail About](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [US Tech Selloff Prompts Asian Market Stabilization Measures](#item-finance-news-1) ⭐️ 8.0/10
2. [Ant Group Leads $100 Million Round in China&\#x27;s Simplexity Robotics at $1.6 Billion Valuation](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI examines perplexity as an intelligence measure, prompting benchmark debate](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI published a conceptual article examining the relationship between language-model perplexity and intelligence, framed around cross-entropy loss trends and evaluation benchmarks. The supplied item includes no full article, methodology, or data, so its specific claims and any model comparisons cannot be verified from the available source. This is analysis, not a model release or an independently measured result.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Context」** The piece is by Jakub Pachocki, OpenAI&\#x27;s chief scientist, who argues for establishing perplexity — equivalently, cross-entropy loss — as a metric for comparing model developers and informing shared safety standards. Perplexity quantifies how surprised a model is when predicting the next token, making lower values indicate better prediction; a random predictor&\#x27;s perplexity approaches the vocabulary size. Hacker News discussion criticized the post for arguing from cross-entropy without explaining the relationship among entropy, log-perplexity, and perplexity itself.

**「Impact」** For model evaluators, the practical consequence is that a held-out perplexity score can be a simpler comparison than task-specific benchmarks, but it is only comparable when the evaluation set and vocabulary are held constant, since the worst-case perplexity equals vocabulary size.

**「Community discussion」** Commenters debated whether perplexity is a meaningful capability signal: one supplied a plain-language definition—next-token surprise bounded between 1 and vocabulary size—while another argued the correspondence is expected because prediction and compression capture world-model quality. Another commenter called the cross-entropy trend surprisingly clear and welcomed a simpler benchmark, and one claimed Microsoft had joined a shared held-out evaluation effort; those are thread opinions and claims, not findings established by the source.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>
<li><a href="https://news.ycombinator.com/item?id=50601525">Perplexity and Intelligence | Hacker News</a></li>

</ul>
</details>

**Tags**: `#language models`, `#perplexity`, `#model evaluation`, `#AI research`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [FT Report Alleges Prince Group Figure Helped Smuggle Nvidia Chips to China](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

The Financial Times, in a report relayed by a Telegram channel, alleged that Hu Xiaowei—identified by the U.S. Treasury Department as the &quot;number two&quot; figure at Cambodia&\#x27;s Prince Group—helped smuggle Nvidia chips into China. The report also alleged that the group had a network of shell companies and underground financing channels and used private jets to move goods. Citing trade data, it said a Malaysian subsidiary of Megaspeed declared about $4.6 billion in imports from December 2024 to December 2025, with some chips reportedly reaching China&\#x27;s black market. Prince Group denied that Hu worked for it and said the allegations about an illegal network and private-jet smuggling lacked factual basis; the claims have not been independently verified in the supplied material.

telegram · zaihuapd · Nov 22, 04:34

**「Background」** Megaspeed, the buyer named in the report, is Nvidia&\#x27;s largest client in south-east Asia and has already been accused of breaching US export controls to divert Nvidia chips into China, according to DW. The Financial Times has separately reported that former Megaspeed executive Alice Huang sits at the centre of US investigations into the underground chip trade. The broader scrutiny has produced criminal charges: in March a founder of Super Micro Computer was charged with smuggling $2.5 billion worth of servers containing Nvidia chips to China, CNN Business reported.

**「Impact」** Export-control investigators and Nvidia supply-chain partners now have a named intermediary—Megaspeed&\#x27;s Malaysian subsidiary—and a $4.6 billion declaration figure to examine; the supplied material reports no charge or court finding against Megaspeed or Prince Group.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1">Alice Huang’s links to the chip underworld</a></li>
<li><a href="https://www.dw.com/en/megaspeed-and-the-battle-to-go-high-end-nvidia-chips-into-china/a-79909129">Megaspeed : Nvidia partner at the center of the spy affair</a></li>
<li><a href="https://www.cnn.com/2026/11/16/tech/nvidia-sex-spies-serious-problems">Lies, spies and sex are just one part of the Nvidia story. | CNN Business</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#chip smuggling`, `#export controls`, `#AI hardware`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [When in Doubt, Flail About](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** Sean Goedecke argues that when guidance is unclear or the path forward is unknown, the cautious instinct to wait for understanding is usually worse than deliberate experimentation.

**「Solution」** His heuristic, which he calls “flailing,” rests on trying many different things, paying close attention to feedback from experts and reality, and ruthlessly dropping approaches that do not get positive results. Trying many options provides direct contact with reality, acknowledges that most plans will fail, and prevents overinvestment in any single plan. He applies this to product work, where GitHub Models features mostly failed but inference from a GitHub Actions token proved sticky and seeded “Continuous AI”; to complex engineering systems, where speculative changes should be kept only if they appear to improve things; and to organizational problems, where trying automation, volunteering, or long-term plans can show effort, though feedback is especially critical. He warns that bad flailing can damage a reputation, and that from the inside the approach often feels like repeated failure rather than sensible experimentation.

**「Takeaway」** Under genuine uncertainty, rapid, low-commitment experimentation with tight feedback is often more effective than exhaustive upfront understanding—provided failing approaches are dropped quickly. The uncomfortable feeling of flailing is not necessarily evidence that the approach is wrong.

**Tags**: `#engineering practice`, `#experimentation`, `#uncertainty`, `#feedback loops`, `#organizational dynamics`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US Tech Selloff Prompts Asian Market Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 8.0/10

US AI and semiconductor stocks sold off on Friday, with the Nasdaq down 5.28% and the Philadelphia Semiconductor Index down nearly 11%. Mainland China, South Korea, and Taiwan announced stabilization measures, including China&\#x27;s cut of the minimum margin-financing ratio to 80% and Taiwan&\#x27;s ban on short-selling below the previous close from Nov. 23.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** The emergency measures follow a global retreat from AI and chip shares that began earlier in November, when the Philadelphia Semiconductor Index fell roughly 13% over two weeks. China&\#x27;s margin-financing requirement had been 100%, so cutting it to 80% frees roughly ¥400bn in potential buying power, according to a summary of the measures.

**「Impact」** The measures directly affect leveraged buyers and short sellers in these markets by changing collateral requirements or restricting bearish trades.

<details><summary>References</summary>
<ul>
<li><a href="https://www.caixinglobal.com/2026-11-01/cover-story-the-global-tech-selloff-tests-the-economics-behind-ai-boom-102499694.html">Cover Story: The Global Tech Sell - Off Tests the Economics Behind AI ...</a></li>
<li>China, South Korea and Taiwan are pulling out the emergency playbook ...</li>

</ul>
</details>

**Tags**: `#US tech selloff`, `#semiconductor stocks`, `#Asian market stabilization`, `#short-selling restrictions`, `#margin financing`

---

<a id="item-finance-news-2"></a>
### [Ant Group Leads $100 Million Round in China&\#x27;s Simplexity Robotics at $1.6 Billion Valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

Ant Group led a $100 million pre-A funding round in Chinese embodied-intelligence startup Simplexity Robotics, valuing the company at $1.6 billion after the investment, according to Bloomberg. Existing investors Alibaba, Tencent, HongShan and BlueRun Ventures also participated, chairman and co-founder Wang Kai confirmed to Bloomberg.

telegram · zaihuapd · Nov 23, 02:02

**「Background」** Founded in Hangzhou in July 2025, Simplexity had already disclosed five funding rounds totaling 2 billion yuan by March 2026, when its post-money valuation exceeded $1 billion, Bloomberg reported.

**「Who is affected」** The funding gives Simplexity capital to fight for share against more established Chinese makers such as Unitree and UBTech, in a market where Chinese vendors already accounted for roughly 97% of global humanoid-robot shipments in the third quarter of 2026, according to Smart Analytics Global.

<details><summary>References</summary>
<ul>
<li><a href="https://smartanalyticsglobal.com/global-humanoid-robot-shipments-q3-2026-agibot-ubtech-unitree/">SAG: Global Humanoid Robot Shipments Surge 347% YoY in Q3 ...</a></li>

</ul>
</details>

**Tags**: `#embodied AI`, `#humanoid robots`, `#venture funding`, `#Ant Group`, `#China tech`

---