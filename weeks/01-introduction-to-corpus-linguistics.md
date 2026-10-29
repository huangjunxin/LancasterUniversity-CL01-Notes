# 第 1 周 · Introduction to corpus linguistics

> 官方主题（edX）：Introduction to corpus linguistics
> 状态：见 [README 看板](../README.md#进度看板) · 大纲来源 [CURRICULUM.md](../CURRICULUM.md)

## 本周材料

| 材料 | 内容 | 备注 |
|---|---|---|
| 1.3 Glossary of terms | CASS 术语表，38 条 | 来源记录见 [glossary/cass-key-terms.md](../glossary/cass-key-terms.md) |
| Lecture 1, part 2 | 14 页讲义：频率、Zipf 定律、结构化检索 | PPT 导出；元数据标题写的是 “CORPUS DESIGN”，内容是频率；截图基于 #LancsBox X **5.0.3.9** |
| Lecture 1, part 3 | 6 页：semantic prosody（sit through 的负面语境）+ 为什么不能拿搜索引擎/ChatGPT 当语料 | 截图基于 #LancsBox X 5.0.3.9 |
| Lecture 1, part 4 | 7 页：两个测试（频率 / 多词表达）+ 最终结论；附英文转录 | 截图基于 #LancsBox X **5.0.3.8** |
| 材料 5：Brezina (2025) AI 论文 | 16 页立场论文：form vs meaning、三条语言建模路径 | [阅读笔记](../reference/reading-brezina-2025-ai.md)；part 3 的 p4–p6 就是这篇

> 已知缺口：Lecture 1 应该还有 **part 1**，以及 1.1 / 1.2 / 1.4 一类编号材料。拿到再补进上表。

## 本周目标（自拟，听完课后按课程实际内容校正）

- 语料库和“随便一堆文本”的差别：representativeness、balance、size 各解决什么问题
- token 与 type 的区别，为什么所有频率都要换算成 per million
- 课程演示里第一眼看到的 BNC 是什么、为什么它常被当参照

## 笔记

### 1. 频率是语料库的独门优势

Leech（2011: 7，讲义 p1 引）：

> If asked what is the one benefit that corpora can provide and that cannot be provided by other means, I would reply ‘information about frequency’.

两种频率（p2）：

| 类型 | 定义 | 用途 |
|---|---|---|
| absolute frequency | 某个语言表达在语料中出现多少次，直接数 hits | 原始证据量 |
| relative frequency | 每给定词数（如 1M）出现多少次 | 估计出现概率；**跨不同规模的语料比较** |

计算公式（p3）：

```
relative frequency = absolute frequency / number of tokens in corpus × basis for normalization
```

讲义例子：148 次命中 / BNC2014 全库 102M tokens = **1.45**（每百万词）。

> 我的注：这里分母写 102 而不是 102,000,000，是因为归一化基数选的是“百万词”。**分母单位必须和基数单位对齐**，这是换算最容易错的一步，也是第 2 周做跨语料比较的前置条件。

图里那次查询（p3–p4，BNC2014 · 2.0 CLAWS7 · whole corpus）：`[hw="sit" pos="V.*"] through within <s/>`，Freq 148 (1.45)，Texts 128/88,171。

**Message 1（p5）：报频率时，绝对值与相对值一起报。** 只给 1.45 读者不知道证据有多少，只给 148 无法和别人比较。

### 2. Zipf 定律：词是稀有的

- 按词频排序，第 2 高频词的频次约为第 1 的 1/2，第 3 约为 1/3，依此类推（p6，Brezina 2018 第 2 章）
- 直接后果：**语料能提供的“关于某个词”的证据量衰减极快**
- 可视化（p7）：横轴 rank、纵轴 absolute frequency 的散点 —— the 6,041,234 / of 3,042,376 / and 2,616,708 / was 881,473 / people 121,591，横轴一直铺到 60 多万名

**Message 2（p8）：Words are rare.** 所以后面所有统计量（搭配、关键词）都要在“大多数词没几次”这个前提下谈，不能拿单个低频词的频率差当结论。

### 3. 结构化检索：#LancsBox 的查询语法

讲义用同一个查询串讲了四页（p9–p13）：

```
[hw="sit" pos="V.*"] through within <s/>
```

| 片段 | 作用 |
|---|---|
| `[hw="sit" pos="V.*"]` | 词元（headword）是 sit、词性是动词 → 命中 sit / sits / sat / sitting |
| `through` | 紧邻的下一词 |
| `within <s/>` | 把匹配限制在同一句内 |

对比例子（p12）：

- ✓ Then, having **sat through** over an hour of this → 命中
- ✗ stones upon which you can **sit. Through** those two spruce trees → 被句界挡住

p13：同一条查询换 subcorpus（BNC2014 → informal speech，11M），表格清空 —— 查询结果是绑定语料/子库的，换了库要重跑。

**Message 3（p14）：#LancsBox offers powerful searches.** 也就是说，检索能力的关键不是“能不能搜词”，而是能不能把“词元 + 词性 + 邻接 + 句界”这些条件一起说清楚。

### 4. 课程立场的另一半：AI 处理形式，意义在语境里

Brezina（2025，材料 5）把整门课的问题意识说清楚了 —— 课程标题里的 “new technologies” 不是噱头：

- 电脑处理的是**形式**（0/1 编码的词形），人交流的是**意义**；意义来自社会互动与语境
- LLM 是不可复现的黑箱：同一个问题换个问法，结论可以相反，也追不到答案的来源
- 因此语料库方法的价值在 **transparent evidence + functional context**：证据可查、语境可见、分析者留在图里

最能说明问题的是四个 **good** 的例子（论文 pp.81–82）：sentiment analysis 判正面，ChatGPT 给出互相矛盾的答案，concordance 一看是反讽。**形式频率完全相同，意义只在语境里。**

→ 细节见 [阅读笔记](../reference/reading-brezina-2025-ai.md)。

### 5. semantic prosody：搭配会带评价色彩

**Message 4（pt3 p3）：Semantic prosody is part of the meaning.**

讲义用同一个查询 `[hw="sit" pos="V.*"] through within <s/>` 的 148 条结果（p1），把语境词圈出来：

> bravely · rather than · forced to · had to · 10 hours of · the painful lecture · it again · those meetings about nothing

按右搭配排序（p2）更清楚：

| 左 | 节点 | 右 |
|---|---|---|
| forget your toothbrush: Could you | sit through | 10 hours of Shakespeare performed |
| half a brain would happily | sit through | 100 million billion awkward, uncomfortable |
| The average worker will | sit through | 6,240 meetings during their career |
| of player expression. Evan: We | sat through | a 20-minute demo, and |
| | sitting through | a 20-minute fashion show |
| help myself. I'd sooner | sit through | a bad play in a |

结论：**sit through 不只是“sit + through”，而是“熬过（不快的事）”**。这层评价色彩不在词典释义里，只能从搭配分布读出来 —— 这正是“意义在语境里”的可操作版本。

它也把 pt2 和 pt3 接成一条线：频率（pt2）→ KWIC 把 148 条语境摊开 → 从搭配看出评价（pt3）→ 意义。

### 6. 为什么不能“Google 一下”或“问 ChatGPT”

- pt3 p5：中文屋漫画（一台电脑在箱子里，只留 IN / OUT）—— 形式进出，没有意义
- pt3 p6：Kilgarriff (2007) 的 *Last words: Googleology is bad science*，讲义把标题改成 **“ChatGPTology is Bad Science”**

Kilgarriff 那段话批评的是：把搜索引擎命中数当成语言频率来用 —— 门槛低，但没有语料库边界、没有归一化、数字不稳定。换成 ChatGPT 同理：回答不可复现、来源不可追溯（见 [材料 5 的阅读笔记](../reference/reading-brezina-2025-ai.md)）。

> 我的理解：这不是“别用 AI”，而是“别把 AI 的输出当数据”。数据要有边界和口径，解释要能追溯到语境 —— 这两件事恰好就是语料库方法在做的事。

### 7. 两个测试：AI 的数字和定义都靠不住

**测试一：频率（pt4 p1–p2）**

问 ChatGPT：“people 每百万词出现多少次？比 time 多吗？” 它给了带语料出处的答案，然后被逐条核对：

| 词 | ChatGPT 说的 BNC1994 | BNC2014 | COCA | **#LancsBox 实测 BNC2014** |
|---|---|---|---|---|
| people | ~2,100 | ~2,500 | ~2,200 | **1,222.62**（125,080 次） |
| time | ~2,200 | ~2,400 | ~2,000 | **1,609.05**（164,614 次） |

排序碰巧是对的（time > people），但**数字全部虚高**：people 高约一倍，time 高约 50%。实测环境：BNC2014 whole corpus，102M tokens，词表 858,450 个 type。

**测试二：多词表达是否存在（pt4 p3–p6）**

“education and courage” 是不是英语里的固定搭配？

| 查法 | 结果 |
|---|---|
| 问 ChatGPT | 认真解释 education、courage，还给出一句现成 motto：“We need education to understand the world, and courage to change it.” |
| #LancsBox 查 BNC2014 | **Freq 0 (0)**，Texts 0/88,171，表格空白 |
| Google 精确检索 | 约 **26 条**，多是 TikTok / Instagram / YouTube 的励志内容，常常被标点切开 |

→ 这是一个 **non-collocational expression**：AI 能给你一个像样的“意思”，语料告诉你它根本没被使用。

对照资源（p6）：Routledge 的 *A Frequency Dictionary of Multi-Word Expressions in British English*，作者正是 **Brezina 与 Gablasova** —— 课程两位讲师出的工具书，专查这类“到底有没有这个说法”。

### 8. 讲者的结论

pt4 p7（转录同）：

> Corpus linguistics remains essential—AI and LLMs are valuable tools that complement, not replace, corpus analysis. Transparency, replicability, and critical evaluation remain crucial.

换成三个可执行的检查：

1. **transparency**：这个数字来自哪个语料、多大、怎么切词？说得出才算证据
2. **replicability**：换个人、换个时间，能不能得到同一个结果？
3. **critical evaluation**：是不是把一个“看着像”的表达当成了真实用法？

> 我的注：这两个测试合起来正好闭环 —— 测试一说明 AI 会给**假数字**，测试二说明 AI 会给**假意义**。前者用语料查，后者用搭配分布查，两者都不是“问一句”能解决的。

## 第 1 周通关清单

这周材料堆得比较久，用下面几条判断能不能进第 2 周（都能用自己的话说出来就算过）：

- [ ] 能说清语料库和“一堆文本”的差别：representativeness、balance、size 各管什么
- [ ] 能手算 relative frequency：148 次 / 102M tokens 为什么是 1.45
- [ ] 能解释 Zipf 定律一句话版本，以及它为什么让“低频词的结论”不可靠
- [ ] 能说出 `[hw="sit"]` 与 `[word="sit"]` 的差别
- [ ] 能在 #LancsBox 里跑通讲义那条查询，命中数对上 148 (1.45)；对不上时知道先查 token 口径
- [ ] 能用四个 good 的例子讲清 form 与 meaning 的区别
- [ ] 能举出 sit through 的三个负面搭配，并解释“semantic prosody 是意义的一部分”
- [ ] 能说明 Kilgarriff 为什么说“拿搜索命中数当频率”是坏科学
- [ ] 能复述 people / time 测试：ChatGPT 的数字和 BNC2014 实测差多少
- [ ] 能说出 education and courage 在 ChatGPT / BNC2014 / Google 三处的结果，并解释差异
- [ ] 能背出最后一句的三个词：transparency、replicability、critical evaluation
- [ ] CASS 术语表里 W1 相关条目（corpus / concordance / KWIC / token / type / balance / representativeness）能不看表解释

## 工具实操

| 日期 | 工具 | 语料 | 查询 / 采样 | 参数 | 结果 | 截图 |
|---|---|---|---|---|---|---|
|  | #LancsBox X | BNC2014（whole corpus） | `[hw="sit" pos="V.*"] through within <s/>` | 期望 Freq 148 (1.45)，Texts 128/88,171 | **待复现** |  |

> 复现目的：验证自己环境的 BNC2014 token 数（讲义显示 102M）与课件一致；不一致就不是“照抄答案”，而是先对口径。

## 练习与测验

| 任务 / 题目 | 我的答案 | 结果 | 备忘 |
|---|---|---|---|
|  |  |  |  |

## 结论

第 1 周的内核一句话：**频率必须归一化后才能比较，而 Zipf 定律决定了大多数词根本拿不到足够证据** —— 后面所有方法都在跟这两件事打交道。

## 疑问（待查）

- [ ] #LancsBox X 5.0.3.9（课件）与官网 6.0.2 的查询语法是否完全兼容？升级后哪些写法变了？
- [ ] 讲义里 BNC2014 是 102M tokens，BNC2014 的官方规模口径是多少（含/不含标点、是否按 CLAWS7 token）？
- [ ] “basis for normalization” 取 1M 是课程统一规定还是按语料规模选？做 keyness 时是否换基数？

## 术语新增 → [glossary/terms.md](../glossary/terms.md)

- absolute frequency / relative frequency / basis for normalization
- Zipf's law
- headword（查询语法里的 hw）
- subcorpus

## 参考

- [#LancsBox 官网的语料库语言学工具史时间线](../reference/corpus-linguistics-history.md)（1900s–1993，7 个节点）
- 课程材料 1.3：CASS 术语表（38 条，2013 / 2018 rev）→ [来源记录](../glossary/cass-key-terms.md)、[条目](../glossary/terms.md)
- Lecture 1 part 2（14 页，课程后台，未入库）
- 查询语法怎么学 → [reference/cql-cheatsheet.md](../reference/cql-cheatsheet.md)（含官方手册 / cheat sheet / 练习）
- 材料 5：Brezina (2025) → [阅读笔记](../reference/reading-brezina-2025-ai.md)
- Kilgarriff, A. (2007). Last words: Googleology is bad science. *Computational Linguistics*, 33(1), 147–151.（讲义 pt3 p6 引用，未下载）
- Brezina, V. & Gablasova, D. *A Frequency Dictionary of Multi-Word Expressions in British English*. Routledge.（pt4 p6 展示，未下载）
- Lecture 1 part 4 的英文转录（课程后台，未入库）
- Leech, G. (2011). *Frequency structures*.（讲义 p1 引用，未下载）
- Brezina, V. (2018). *Statistics in Corpus Linguistics*, ch. 2（讲义 p6 引用）→ [章节地图与按周路线](../reference/book-brezina-2018.md)
