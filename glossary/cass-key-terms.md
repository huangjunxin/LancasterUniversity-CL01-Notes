# 课程材料 1.3：CASS 术语表（Corpus: Some key terms）

edX 课程第 1 周材料 1.3 提供的官方术语表。下面是来历、结构与要点，**完整英文定义见课程原件**（未入库，理由见末节）。

## 来源与元数据

| 项 | 内容 |
|---|---|
| 课程内文件名 | `asset-v1_lancasteruniversity+CL01+3T2025+type@asset+block@1.3_Glossary_of_terms.pdf` |
| 文档标题 | CASS Gloss [final] |
| 系列 | CASS: Briefings（ESRC Centre for Corpus Approaches to Social Science，兰卡斯特大学） |
| 版本 | Published 2013（2018 revision） |
| 制作 | Series editing & design: Mark McGlashan；CASS 中心主任: Tony McEnery |
| 规格 | 12 页，A5（420 × 595 pt），有文本层，非扫描件 |
| 文件大小 | 18.6 MB（体积来自版式图形） |

## 页面结构

| 页 | 内容 |
|---|---|
| 1–2 | 封面与版权页 |
| 3 | 引言：语料方法借计算机处理大体量语言数据 |
| 4 | What is Corpus Linguistics? —— 语料库语言学作为一套方法 |
| 5–10 | **术语表正文，38 条，字母序 A–X** |
| 11 | 推广页：指向 CASS 在 FutureLearn 的语料库课程 |
| 12 | CASS: Briefings 系列说明 |

## 术语清单（38 条，页码见 [terms.md](terms.md)）

annotation · balance · colligation · collocation · comparability · concordance · concordancer · corpus · corpus construction · corpus-based · corpus-driven · diachronic · encoding · frequency list · KWIC · keyword · lemma · lemmatisation · lexis · markup · markup language · metadata · monitor corpus · node · reference corpus · representativeness · sample · sample corpus · sampling frame · significance test · statistical significance · synchronic · tagging · text · token · type · type-token ratio · XML

条目已全部并入 [terms.md](terms.md)，带“官方页”列；一句话释义是我的转写。

## 几处值得记住的区分（原文要点）

- **KWIC 里的 key word ≠ keyword**：“Here, ‘key word’ means ‘search term’ and is distinguished from keyword.”（p7）—— 一个词居中显示，跟它“是不是关键词”无关。
- **balance 与 representativeness 互为条件**：balance 条目指向 sample，representativeness 条目指向 balance（p5、p8）；两个概念单独讲都不完整。
- **sample 有三义**：单篇文本/节选、统计上的样本、以及“语料是语言的一个样本”（p9）。
- **corpus-based vs corpus-driven**：前者用语料检验预设假设或例证理论，后者自下而上找模式（p6）。
- **type-token ratio 不可跨语料比较**：“This statistic is not comparable between corpora of different sizes.”（p10）—— 与 [methods-cheatsheet](../reference/methods-cheatsheet.md) 第 4 节“没归一化”是同一个坑。
- **keyword 的门槛**：要比参照语料显著更频繁（p7），所以参照语料一换，关键词表就换。

## 原文瑕疵（照录不改）

- p8 “The texts that makeup a corpus” 应为 “make up”。
- p11 “We provide you need to start…” 句中有漏词，原文如此。

## 版本线索

p11 指向的是 CASS 在 **FutureLearn** 的语料库课程（`futurelearn.com/courses/corpus-linguistics`），不是本 edX 课。说明这份 briefing 是旧 MOOC 时代的材料，edX 版 CL01 直接沿用；术语本身没变，讲法可能变 —— 以课程视频为准。

## 为什么原件不入库

18.6 MB + CASS 版权，仓库目前是 **PUBLIC**。做法：

- 原件留在课程后台 / 本地 `source/`（已 gitignore）
- 仓库里只存本页的来源记录 + [terms.md](terms.md) 的条目
- 如需把英文定义全文照录，先把仓库转为 private，再告诉我
