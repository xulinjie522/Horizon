---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 10 条内容中筛选出 3 条重要资讯。

---

**科技新闻**
1. [Anthropic 2028 年数据中心供电预测：87%天然气、11%煤电](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI 探讨困惑度与模型智能的关系](#item-tech-news-2) ⭐️ 7.0/10

**科技博客**
1. [迷茫时，不妨四处试探](#item-tech-blog-1) ⭐️ 6.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Anthropic 2028 年数据中心供电预测：87%天然气、11%煤电](https://betterdatacenterproject.com/2026/11/16/how-ai-is-powered-a-breakdown-of-byop-and-grid-power/) ⭐️ 7.0/10

一篇关于 AI 数据中心供电的分析文章预测，Anthropic 在 2028 年的数据中心电力结构中，87%来自天然气、11%来自煤电；标题未说明其余 2%的来源，也未说明是否包含可再生能源。该比例是讨论中的项目预测，并非 Anthropic 公布的正式采购或排放数据，现有材料没有给出计算口径、设施范围或地域分布。关键限制在于，无法据此判断这是单一站点、整体算力还是特定租赁设施的组合，也不能把它当作已签约的供电安排。

hackernews · happosai · 11月22日 08:57 · [社区讨论](https://news.ycombinator.com/item?id=50597612)

**「背景」** Anthropic 很少自建数据中心，算力主要靠租用第三方设施：按已公开的报道，它通过协议使用 xAI 位于孟菲斯的 Colossus 1 集群，而该站点依靠现场燃气轮机发电，这也是当地空气污染争议的焦点（The Bureau of Investigative Journalism 等报道）。这种模式对应报道中所说的“自带电力”（BYOP，bring your own power）：运营方不单靠公共电网，而是为园区单独配建发电设施，因此电力结构由业主的燃料选择决定，而不是由所在区域电网的可再生能源占比决定，这构成了 2028 年气电 87%、煤电 11% 这一预测的前提。

**「影响」** 由于该分析把 Anthropic 各数据中心与为其供电的具体电厂逐一对应并公开数据集，采购方和开发者可以按站点核对自身 AI 工作负载的电力来源，而不必只依赖企业层面的可再生能源总量表述。另一项实际约束是：数据中心自建电厂时，天然气几乎是唯一可快速上量的选择，而核电建设周期以年计，因此 2028 年前新增的本地化供电大体锁定为化石燃料，承担相应空气污染排放的是电厂所在社区，而不是作出采购决策的机构。

**「社区讨论」** 评论者从环境外部性角度提出批评，有人认为 Anthropic 在租赁孟菲斯 Colossus 1 设施、以及在美国缺乏可再生能源承诺方面是“坏行为者”，并主张通过监管让社区承担的污染成本被计入。另有评论强调 AI 数据中心能耗规模远超公众直觉，并提到美国页岩油伴生天然气常被燃烧或放空；这些是评论者观点和举例，不等同于对上述 2028 年电力结构的独立核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Colossus_%28data_center%29">Colossus ( data center ) - Wikipedia</a></li>
<li><a href="https://www.thebureauinvestigates.com/stories/2026-08-14/misaligned-colossus-musks-data-empire-anthropic">How Musk’s toxic data empire is powering Anthropic ’s… | TBIJ</a></li>
<li><a href="https://nextomoro.com/compute-rent/">Compute rent: what the Anthropic -xAI Colossus deal... | nextomoro</a></li>
<li><a href="https://betterdatacenterproject.com/2026/11/16/how-ai-is-powered-a-breakdown-of-byop-and-grid-power/">How AI is powered : a breakdown of BYOP and grid power</a></li>
<li><a href="https://news.ycombinator.com/item?id=50597612">87 % of the Anthropic power will come from gas and 11 % from coal in...</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#data centers`, `#energy`, `#environmental impact`, `#Anthropic`

---

<a id="item-tech-news-2"></a>
### [OpenAI 探讨困惑度与模型智能的关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 发布文章《Perplexity and Intelligence》，讨论困惑度（perplexity）与语言模型智能之间的关系。现有材料没有提供文章中的具体指标、实验数据或新基准结果，因此只能确认这是一次观点与方法讨论，而不是已经公布的评测结论。Hacker News 上的讨论围绕交叉熵损失、基准设计和“预测即压缩”的解释展开：有人认同二者之间存在清晰对应，也有人质疑仅凭困惑度阈值判断能力是否“涌现”。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景：困惑度衡量的是什么」** 困惑度（perplexity）衡量语言模型在给定前文时预测下一个 token 的“惊讶程度”：按评论者 hazrmard 给出的定义，对一段 token 序列而言，最坏情形下困惑度等于词表大小，最好情形下为 1。它由交叉熵损失换算而来，长期是语言模型预训练的核心指标之一。评论者 jrflo 提到，随着强化学习训练的比重上升，业界曾普遍认为交叉熵损失已不再是衡量模型能力的关键，因此困惑度与模型表现之间的清晰关联在他看来颇为意外。

**「影响」** 如果开发者把困惑度当作衡量模型通用能力的跨模型指标，评论中提出的反例就应纳入使用条件：专门针对数学训练的小模型，可能在其他任务上的总体困惑度更高；因此跨任务比较需要同时说明训练数据分布，否则容易把专用能力误读为通用智能。

**「社区讨论」** 有评论者补充了困惑度的定义：最差情况等于词表大小，完美预测时为 1，并指出原文没有给出定义；另一位评论者则从“预测即压缩”的角度认为，困惑度与智能的对应几乎不可避免。怀疑意见集中在能力“涌现”的阈值上：数学专用小模型可能在其他任务上困惑度更高，因此仅凭固定困惑度并不能证明某项能力出现。

**标签**: `#perplexity`, `#language-models`, `#model-evaluation`, `#machine-learning`, `#OpenAI`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [迷茫时，不妨四处试探](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 作者指出，在缺乏明确指引、不知道什么办法有效的模糊处境里，直觉上应先谨慎等待更多理解，但更有效的做法往往是“flail”（四处试探）；他也承认这是危险建议，试探得不好会损害技术公司里的声誉。

**「方案」** 在他看来，好的试探包含三个相连的要点：大量尝试不同方案、极仔细地读取反馈，并果断放弃没有得到积极反馈的方案。多试让人像原始人乱按 iPhone 一样直接接触现实，也因为多数计划本就糟糕而提高碰到可行解的概率；手上方案越多，越不会因过度投入而舍不得放弃。产品层面，他在 GitHub Models 做过不少不奏效的功能，但“用 GitHub Actions token 运行 AI 推理”意外有粘性，后来成了 Continuous AI 的种子；工程层面，面对过于复杂或庞大的系统，他主张先做一批推测性改动再看效果，而不是先通读全局。组织层面，则可用自动化、主动接手、提出长期方案等方式试探，但此时最需要敏感于反馈，否则帮助对象的不满会转向你；作者也说明，这个过程从内部感觉像反复失败，然而只要及时止损，外部往往看到的是一个主动实验的工程师。

**「启示」** 文章的核心论点是：在无法预先获得清晰度的情境中，快速、广泛地试探并依据反馈迅速收敛，比等待确定答案更能产生理解和价值。它真正的门槛不是勇气，而是能否承受“像在失败”的感受，并持续准确读取和回应反馈。

**标签**: `#engineering judgment`, `#experimentation`, `#feedback loops`, `#organizational dynamics`, `#product development`

---