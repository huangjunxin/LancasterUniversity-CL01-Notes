# 第 1 周 · Introduction to corpus linguistics

> 官方主题（edX）：Introduction to corpus linguistics
> 状态：见 [README 看板](../README.md#进度看板) · 大纲来源 [CURRICULUM.md](../CURRICULUM.md)

## 本周材料

| 材料 | 内容 | 备注 |
|---|---|---|
| 1.3 Glossary of terms | CASS 术语表，38 条 | 来源记录见 [glossary/cass-key-terms.md](../glossary/cass-key-terms.md) |
| Lecture 1, part 2 | 14 页讲义：频率、Zipf 定律、结构化检索 | PPT 导出；元数据标题写的是 “CORPUS DESIGN”，内容是频率；截图基于 #LancsBox X **5.0.3.9** |
| 材料 5：Brezina (2025) AI 论文 | 16 页立场论文：form vs meaning、三条语言建模路径 | [阅读笔记](../reference/reading-brezina-2025-ai.md) |

> 已知缺口：Lecture 1 应该还有 **part 1**（文件名是 pt2），以及 1.1 / 1.2 / 1.4 一类编号材料。拿到再补进上表。

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

## 第 1 周通关清单

这周材料堆得比较久，用下面几条判断能不能进第 2 周（都能用自己的话说出来就算过）：

- [ ] 能说清语料库和“一堆文本”的差别：representativeness、balance、size 各管什么
- [ ] 能手算 relative frequency：148 次 / 102M tokens 为什么是 1.45
- [ ] 能解释 Zipf 定律一句话版本，以及它为什么让“低频词的结论”不可靠
- [ ] 能说出 `[hw="sit"]` 与 `[word="sit"]` 的差别
- [ ] 能在 #LancsBox 里跑通讲义那条查询，命中数对上 148 (1.45)；对不上时知道先查 token 口径
- [ ] 能用四个 good 的例子讲清 form 与 meaning 的区别
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
- Leech, G. (2011). *Frequency structures*.（讲义 p1 引用，未下载）
- Brezina, V. (2018). *Statistics in Corpus Linguistics*, ch. 2（讲义 p6 引用）→ [章节地图与按周路线](../reference/book-brezina-2018.md)
