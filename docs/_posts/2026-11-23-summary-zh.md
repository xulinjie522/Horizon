---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 27 条内容中筛选出 5 条重要资讯。

---

**科技新闻**
1. [OpenAI 刊文讨论困惑度与智能的关系](#item-tech-news-1) ⭐️ 7.0/10
2. [英媒指太子集团关联人士参与英伟达芯片对华走私](#item-tech-news-2) ⭐️ 7.0/10

**科技博客**
1. [不确定时，不妨有策略地“乱试”](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股大幅下挫，亚洲多个市场推出稳定市场措施](#item-finance-news-1) ⭐️ 8.0/10
2. [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 刊文讨论困惑度与智能的关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 刊发一篇概念性文章，讨论模型困惑度（perplexity）与智能之间的关系，并引发围绕交叉熵损失趋势和评测基准设计的技术讨论。现有材料未包含文章全文，因此文章的具体论证、图表和结论无法独立核实；这更像一篇分析文章，而非产品发布或能力声明。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度（perplexity）用于衡量语言模型逐 token 预测时的不确定性，OpenAI 的文章将其与交叉熵损失视为等价指标。该文作者、OpenAI 首席科学家 Jakub Pachocki 主张用这一指标比较不同模型开发者并讨论共同安全标准；Hacker News 讨论则批评文章没有解释熵、对数困惑度和困惑度之间的换算关系。

**「社区讨论」** 评论中，hazrmard 补充了困惑度的定义：它衡量模型预测下一个 token 时的惊讶程度，最佳值为 1，最差等于词表大小；jrflo 则表示，交叉熵损失在强化学习（RL）使用增多后仍呈现清晰趋势令人意外，并认为这种简单基准比日益复杂的评测更有价值。d\_burfoot 主张，对原始数据流的预测或压缩率正可刻画智能进展；reasonableklout 引用 Mustafa Suleyman 的说法称，微软已在 OpenAI 的评测集上报告 MAI-2 Base，其 log-perplexity 为 0.819。这些均为评论者说法，未获所给原文证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>
<li><a href="https://news.ycombinator.com/item?id=50601525">Perplexity and Intelligence | Hacker News</a></li>

</ul>
</details>

**标签**: `#language models`, `#perplexity`, `#model evaluation`, `#AI research`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [英媒指太子集团关联人士参与英伟达芯片对华走私](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

英国《金融时报》援引知情人士称，被美国财政部指为柬埔寨太子集团“二号人物”的胡小伟，涉嫌参与将英伟达芯片运入中国。报道援引贸易数据称，2024 年 12 月至 2025 年 12 月，Megaspeed 马来西亚子公司进口货物的申报价值约 46 亿美元，部分芯片据称流入中国黑市。太子集团否认胡小伟曾为其工作，并称有关非法网络和私人飞机走私的指控缺乏事实依据。上述内容来自对这篇报道的转述，相关指控尚未得到独立证实。

telegram · zaihuapd · 11月22日 04:34

**「背景」** 这起指控的核心对象 Megaspeed 并非首次进入监管视野：据德国之声报道，这家被视为英伟达在东南亚最大客户、近年采购了数十亿美元英伟达产品的公司，已被指控违反美国出口管制、将芯片转运至中国（tool-2-2）。《金融时报》同一调查还提到，Megaspeed 前高管 Alice Huang 处于美方相关调查的中心，有美国官员怀疑她是中国间谍，北京称这一说法是“抹黑”（tool-2-1）。作为同类执法先例，CNN 今年 11 月的报道提到，Super Micro 创始人已于 3 月被控走私价值 25 亿美元、搭载英伟达芯片的服务器，同样涉及违反美国出口法（tool-2-3）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1">Alice Huang’s links to the chip underworld</a></li>
<li><a href="https://www.dw.com/en/megaspeed-and-the-battle-to-go-high-end-nvidia-chips-into-china/a-79909129">Megaspeed : Nvidia partner at the center of the spy affair</a></li>
<li><a href="https://www.cnn.com/2026/11/16/tech/nvidia-sex-spies-serious-problems">Lies, spies and sex are just one part of the Nvidia story. | CNN Business</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#chip smuggling`, `#export controls`, `#AI hardware`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时，不妨有策略地“乱试”](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 在没有明确指引、也不知道什么做法会有用的模糊局面里，直觉往往让人谨慎等待更多信息；作者却认为，这种等待通常更慢，主动“乱试”（flail）才是更快获得理解的办法。

**「方案」** 他给出的做法是：大量尝试不同方案，密切关注来自专家同事和现实指标的反馈，并果断砍掉没有积极反馈的方案。多方案既能提高遇到有效做法的概率，也能避免对单一计划过度投入。作者把适用场景分为三类。产品上，在尚未找到产品市场契合时可在边缘试错：他在现已退役的 GitHub Models 上做的许多功能都没成，但允许 GitHub Actions token 调用 AI 推理的那项意外受欢迎，后来成为“Continuous AI”的种子。工程上，面对过于复杂、庞大或已高度优化的系统，与其通读全貌再动手，不如先做一批试探性改动，看效果再决定深入还是放弃——AI agent 可以一次生成五个重构供筛选。组织上，资深或 Staff 工程师常遇到团队互不沟通、某团队不满却说不清原因的情况，此时可自动化部分手工工作、主动接管任务或提出长期方案；多数不会有用，但至少显示在努力，而且必须对反馈敏感，否则不满可能转向自己。作者也警告：乱试做不好会损害声誉，而且从内部感受像反复失败，需要把这种不适视为要跨越的心理障碍之一。

**「启示」** 作者的核心论点是，信息不足时，快速而广泛地试错、并随时根据反馈放弃失败方案，比先求完整理解更有效；关键不在“乱”，而在反馈与止损。

**标签**: `#engineering practice`, `#experimentation`, `#uncertainty`, `#feedback loops`, `#organizational dynamics`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大幅下挫，亚洲多个市场推出稳定市场措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 8.0/10

美国 AI 科技股周五遭遇大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数重挫近 11%。中国内地、韩国和中国台湾地区随后公布稳定市场措施，包括下调融资保证金最低比例至 80%、放宽上市公司回购限制，以及限制卖空。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 融资保证金最低比例指投资者借钱买股票时必须自付的资金占比；中国内地此前为 100%，此次降至 80%，意味着投资者可撬动更多资金买入。卖空则是押注股价继续下跌的交易，此前 11 月初费城半导体指数也曾在两周抛售中累计下跌约 13%。

**「影响」** 这些措施将直接降低中国内地融资交易门槛、放宽韩国上市公司回购，并提高中国台湾地区卖空与融券的成本，影响当地短线交易者、券商和上市公司。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.caixinglobal.com/2026-11-01/cover-story-the-global-tech-selloff-tests-the-economics-behind-ai-boom-102499694.html">Cover Story: The Global Tech Sell - Off Tests the Economics Behind AI ...</a></li>
<li>China, South Korea and Taiwan are pulling out the emergency playbook ...</li>

</ul>
</details>

**标签**: `#US tech selloff`, `#semiconductor stocks`, `#Asian market stabilization`, `#short-selling restrictions`, `#margin financing`

---

<a id="item-finance-news-2"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

据彭博报道，蚂蚁集团领投中国具身智能公司 Simplexity Robotics 的 1 亿美元 pre-A 轮融资，投后估值 16 亿美元；阿里巴巴、腾讯、HongShan 和蓝驰创投跟投。公司 2025 年 7 月成立于杭州，今年 3 月曾称成立半年内累计融资 20 亿元人民币，当时投后估值已超 10 亿美元。

telegram · zaihuapd · 11月23日 02:02

**「背景」** 具身智能指把人工智能装进实体机器人、使其能感知并操作物理世界的技术方向。Simplexity Robotics 于 2025 年 7 月在杭州成立，核心团队来自理想汽车；据彭博今年 3 月披露，公司在成立半年内已完成五轮融资、累计融资 20 亿元人民币，当时投后估值已超过 10 亿美元。

**「影响」** 按彭博报道，这笔 1 亿美元将用于与宇树、优必选等更成熟的厂商争夺市场；据市场研究机构 Smart Analytics Global 的数据，中国厂商合计占全球人形机器人出货量约 97%，因此新资金加剧的竞争主要发生在中国同业之间，而非直接冲击海外厂商。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://global.chinadaily.com.cn/a/202608/11/WS6a7a8b3aa310986e2b46a1a5.html">Chinese humanoid robot makers hold 97% global shipments in H1</a></li>
<li><a href="https://smartanalyticsglobal.com/global-humanoid-robot-shipments-q3-2026-agibot-ubtech-unitree/">SAG: Global Humanoid Robot Shipments Surge 347% YoY in Q3 ...</a></li>

</ul>
</details>

**标签**: `#embodied AI`, `#humanoid robots`, `#venture funding`, `#Ant Group`, `#China tech`

---