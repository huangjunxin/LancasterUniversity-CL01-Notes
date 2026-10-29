# 第 1 周 · Introduction to corpus linguistics

> 官方主题（edX）：Introduction to corpus linguistics
> 状态：见 [README 看板](../README.md#进度看板) · 大纲来源 [CURRICULUM.md](../CURRICULUM.md)

## 本周材料

| 材料 | 内容 | 备注 |
|---|---|---|
| 1.3 Glossary of terms | CASS 术语表，38 条 | [来源记录](../glossary/cass-key-terms.md) |
| Lecture 1, part 1 | 转录为主：concordance 与 frequency 两个镜头、Cruden 的圣经索引 | 只有转录，没拿到幻灯片 |
| Lecture 1, part 2 | 14 页：频率、Zipf、CQL | 截图基于 #LancsBox X 5.0.3.9 |
| Lecture 1, part 3 | 6 页：semantic prosody、索引行标注、Kilgarriff | 截图基于 5.0.3.8 / 5.0.3.9 |
| Lecture 1, part 4 | 7 页：两个测试 + 最终结论 | 截图基于 5.0.3.8 |
| 材料 5：Brezina (2025) AI 论文 | 16 页立场论文 | [阅读笔记](../reference/reading-brezina-2025-ai.md)；pt3–pt4 都在引它 |

四节录像的英文转录放在本地 `source/`（已 gitignore，不入库）。

## 本周目标（自拟，听完课后按课程实际内容校正）

- 语料库和“随便一堆文本”的差别：representativeness、balance、size 各解决什么问题
- token 与 type 的区别，为什么所有频率都要换算成 per million
- 课程演示里第一眼看到的 BNC 是什么、为什么它常被当参照

## 全课线索：四条 Message

这一周不是四段独立内容，是同一个论证的四步。讲者每节都收在一条 Message 上：

| 出处 | Message 原文 | 换成一句话 |
|---|---|---|
| pt1 | Concordance and frequency reveal the words, meaning and importance | 两个镜头：语境 + 频率 |
| pt2 | We report frequency using both absolute and relative values | 报频率必须两个数一起给 |
| pt2 | Words are rare | 所以语料必须大到百万、十亿级 |
| pt2 | #LancsBox offers powerful searches: simple, smart, CQL | 查询能力分三层 |
| pt3 | Semantic prosody is part of the meaning | 意义在搭配里，不在词典里 |
| pt4 | Corpus linguistics remains essential——AI complements, not replaces | AI 是补充，不是替代 |

## 笔记

### 1. pt1：concordance 与 frequency 是两个镜头

讲者开场用了一个比喻（转录）：两者是**观察数据的两个镜头**（two lenses），都靠专门的软件来看。

- **concordance（KWIC）** 给出“用法”：一个词每次出现时连同左右语境一起排开，这是理解意义的入口
- **frequency** 给出“重要程度”：出现得多不多、值不值得当结论
- 界面上通常三者并列：absolute frequency、relative frequency，以及**跨文本 / 语域 / 体裁的分布 —— 这就是 dispersion（离散度）**（pt1 第一次出现）

历史对照：中世纪的圣经索引是手工做的 —— Cruden 的 *Concordance of the Holy Scriptures* 花了一年、每天 18 小时；今天软件几秒出结果。pt1 那个二维码指向的就是官网的[工具史时间线](../reference/corpus-linguistics-history.md)。

现场演示（转录）：BNC2014（**1 亿词**当代英式英语）里查 sit through，得到 sat through / sitting through 等所有形态；按左语境过滤 **have / had to sit through**，这一类约占全部索引行 **10%**。

### 2. pt2：频率两个数一起报（Message 1）

Leech（2011: 7）被引作这一段的支点：语料库能给的独门东西，就是 “information about frequency”。

| 类型 | 定义 | 用途 |
|---|---|---|
| absolute（raw）frequency | 直接数 hits | 原始证据量 |
| relative frequency | 每给定词数（通常 1M）出现几次 | 估计概率、**跨不同规模的语料比较** |

~~~
relative frequency = absolute frequency / number of tokens in corpus × basis for normalization
~~~

例子（pt2 p3–p4）：148 次命中 / BNC2014 全库 102M tokens = **1.45**（每百万词）。

> 我的注：分母写 102 而不是 102,000,000，因为基数选的是“百万词”。**分母单位必须和基数单位对齐** —— 差这一步就是六个数量级。

操作细节（转录）：#LancsBox 会**同时**显示 absolute 与括号里的 relative，还能直接复制粘贴进报告。

### 3. pt2：Zipf 定律 —— words are rare（Message 2）

- 按词频排序，第 2 高频约是第 1 的 1/2，第 3 约 1/3，依此类推；讲者强调 **“This is approximate numbers”**
- 100M 语料里：the ≈ **6,000,000**；of ≈ **3,000,000**（正好一半）；people / time / year 这类实词已经拖到图尾
- 推论：要观察稳定模式，语料得是**百万到十亿词**级别 —— 这是“为什么需要大语料”的正式理由
- 细节见 Brezina (2018) 第 2 章 → [章节地图](../reference/book-brezina-2018.md)

### 4. pt2：CQL 与三层检索（Message 3）

查询串拆解（`[hw="sit" pos="V.*"] through within <s/>`）：

| 片段 | 作用 |
|---|---|
| `[hw="sit" pos="V.*"]` | 词元 sit 且词性为动词 → sit / sits / sat / sitting |
| `through` | 紧邻的下一词 |
| `within <s/>` | 限制在同一句内 |

正反例（转录给了原话）：*“then having sat through over an hour of this”* 命中；*“stones upon which you can sit. Through those two spruce trees”* 被句界挡掉。

三层检索（Message 3）：

| 层 | 写法 | 例子 |
|---|---|---|
| simple | 直接打词 / 短语 | `love`、`I love going` |
| smart | 大写关键词 | `TIME`（语义相关词）、`PASSIVE`（被动结构）、`EMOTION` / `E2` |
| CQL | 方括号 + 结构约束 | 上面那条 |

语法细节与学习路线见 [CQL 速查](../reference/cql-cheatsheet.md)。

### 5. pt3：semantic prosody（Message 4）

看 sit through 的索引行，左右语境有固定倾向（转录原话）：

- 左边常见：**bravely · rather than · forced to · had to**
- 右边常见：**10 hours of · it again · the painful lecture · those meetings about nothing**

按右搭配排序（pt3 p2）：

| 左 | 节点 | 右 |
|---|---|---|
| Could you | sit through | 10 hours of Shakespeare performed |
| half a brain would happily | sit through | 100 million billion awkward, uncomfortable |
| The average worker will | sit through | 6,240 meetings during their career |
| We | sat through | a 20-minute demo |
| | sitting through | a 20-minute fashion show |
| I’d sooner | sit through | a bad play |

结论：**sit through 带明显的负面语义韵** —— 我们要么被 forced、要么 have to，会 “do anything rather than” 熬过去。这层评价**不在词典释义里，只能从搭配分布读出来**。

### 6. pt3：给索引行打标注（课堂实操）

课上演示了最新版 #LancsBox 的标注功能：

1. 定义类目，例如 **evaluation**，三个层级：negative（红）/ neutral（琥珀）/ positive（绿）
2. 不必标注全部索引行 —— 可以**随机抽 10 条**做示范
3. 点选单条或多条给值，边看更多语境边判断
4. 工具**自动统计**各类占比

意义：把“我读出来的评价”变成**可计数、可复核**的东西 —— 这正是 [材料 5](../reference/reading-brezina-2025-ai.md) 里预告的 easy annotations，课上看到实操了。

### 7. pt3：Kilgarriff 与“别把判断外包”

- 讲者先引 2025 那篇论文的立场：balanced approach —— 承认语料方法的价值，同时对新技术的可能性保持开放；但要先回答：**human analyst 在这套流程里还剩什么角色？把人 engineer out 之后还剩下什么？**
- 再引 Kilgarriff (2007) *Googleology is bad science*：他批评的不是“用网络”，而是**把分析师的主体性（agency）整体外包给单一工具**
- 讲者的改写：**ChatGPT-logy is bad science —— “if we just rely on a single tool”**

> 我的注：所有批评都指向“单一工具 + 不核查”，不是工具本身。语料库方法在这里的作用是提供可查的第二意见。

### 8. pt4：两个测试（数字与意义）

**测试一：频率**（pt4 p1–p2）—— 问 ChatGPT「people 每百万词多少？比 time 多吗？」，它给了带出处的答案，逐条核对：

| 词 | ChatGPT 的 BNC2014 | **#LancsBox 实测** |
|---|---|---|
| people | ~2,500 | **1,222.62**（125,080 次） |
| time | ~2,400 | **1,609.05**（164,614 次） |

排序碰巧对，**数字虚高一倍左右**（102M tokens，词表 858,450 个 type）。

**测试二：多词表达**（pt4 p3–p6）——“education and courage”：

| 查法 | 结果 |
|---|---|
| 问 ChatGPT | 认真解释两个词，还给现成 motto：“We need education to understand the world, and courage to change it.” |
| #LancsBox 查 BNC2014 | **Freq 0 (0)**，Texts 0/88,171，表格空白 |
| Google 精确检索 | 约 **26 条**，多为 TikTok / Instagram 励志内容，常被标点切开 |

→ 这是 **non-collocational expression**：AI 给了一个像样的“意思”，语料证明它没被使用过。对照工具：Routledge *A Frequency Dictionary of Multi-Word Expressions in British English*（Brezina & Gablasova 编）。

**最终 Message**（pt4 p7）：语料库语言学仍然必要，AI 是补充而非替代；**transparency、replicability、critical evaluation** 三条底线不变。

## 课后测验（2026-10-29 · 8/8）

第 1 周课后题全对。题目本身等于课程给出的考点清单 —— 八题对八节，权重看得很清楚。

| # | 考什么 | 正确答案要点 | 对应笔记 |
|---|---|---|---|
| 1 | concordance 是什么 | **一种显示格式**：关注的表达连同其即时语境一起呈现（不是数据库、不是词频测量） | §1 |
| 2 | 为什么要用语料库 | 计算机能帮我们发现**本来难以察觉的模式**（不是“验证直觉”，也不是“回答所有问题”） | §1–2 |
| 3 | 频率为什么重要 | 它显示一个词/表达/特征在**实际使用中**的重要程度 | §2 |
| 4 | 绝对 vs 相对频率 | 绝对频率是出现次数；相对频率**按语料规模归一化** | §2 |
| 5 | Zipf 定律 | 词频**快速衰减**（第 2 高频约为第 1 的一半，依此类推） | §3 |
| 6 | BNC2014 是什么 | **当代英式英语的大型通用语料库**（general corpus） | §1 |
| 7 | semantic prosody | 一个词在语境中的**典型正面/负面联想**，用语料库的 concordance 就能观察 | §5 |
| 8 | Kilgarriff 的警告 | **只依赖单一技术工具、没有人的控制，会损害科学严谨性** | §7 |

### 三个值得注意的地方

**1. 测验只考概念，不考操作。** 八题里没有一题考 CQL 语法、dispersion、标注功能 —— 第 1 周的考核重心是“能不能把话讲对”，动手部分靠后面的周次和工具实操去练。

**2. 两个容易踩的干扰项，方向相反：**

- 第 5 题的干扰项说“实词总比虚词更常用” —— 事实正好相反，最高频的全是 the / of 这类语法词（pt2 里 the ≈ 600 万，of ≈ 300 万）
- 第 6 题的干扰项说 BNC2014 是“大型口语语料库” —— 它是**通用**语料库；Spoken BNC2014 只是其中的口语部分（约 1100 万词），别把子库当全集

**3. 第 2 题修正了我笔记的重心。** 我用 Leech 的“information about frequency”开了头，容易让人以为语料库的价值就是数频率。但测验的正确答案是“发现本来难以察觉的模式”。两者不矛盾：**频率是手段，发现模式才是目的** —— 这也是第 2 周要进搭配与关键词的原因。

## 第 1 周通关清单

都能用自己的话说出来，就可以进第 2 周。2026-10-29 课后测验 8/8，概念层已过关；下面三条工具复现还空着：

- [ ] 能说清语料库和“一堆文本”的差别：representativeness、balance、size 各管什么
- [ ] 能说出 concordance 与 frequency 各回答什么问题（“两个镜头”）
- [ ] 能手算 relative frequency：148 次 / 102M tokens 为什么是 1.45
- [ ] 能解释 Zipf 定律一句话版本，以及它为什么让“低频词的结论”不可靠
- [ ] 能说出 `[hw="sit"]` 与 `[word="sit"]` 的差别
- [ ] 能区分 simple / smart / CQL 三层检索，各举一例
- [ ] 能举出 sit through 的三个负面搭配，并解释 semantic prosody
- [ ] 能说清给索引行打标注是为了什么（可计数、可复核）
- [ ] 能用四个 good 的例子讲清 form 与 meaning 的区别
- [ ] 能复述 people / time 测试：AI 数字 vs 语料实测差多少
- [ ] 能说出 education and courage 在三处的结果，并解释差异
- [ ] 能背出最后三个词：transparency、replicability、critical evaluation

## 工具实操

| 日期 | 工具 | 语料 | 查询 / 采样 | 参数 | 结果 | 截图 |
|---|---|---|---|---|---|---|
|  | #LancsBox X | BNC2014（whole corpus） | `[hw="sit" pos="V.*"] through within <s/>` | 期望 Freq 148 (1.45)，Texts 128/88,171 | **待复现** |  |
|  | #LancsBox X | BNC2014（whole corpus） | 词表查 time / people | 期望 1,609.05 / 1,222.62 | **待复现** |  |
|  | #LancsBox X | BNC2014（whole corpus） | 短语查 `education and courage` | 期望 Freq 0 (0) | **待复现** |  |

> 三条都复现之后，才算“自己的环境与课程口径一致”。

## 练习与测验

| 任务 / 题目 | 我的答案 | 结果 | 备忘 |
|---|---|---|---|
|  |  |  |  |

## 结论

第 1 周的内核一句话：**频率必须归一化才能比较（Zipf 又说明大多数词证据不足），而意义只能从搭配与语境里读出来** —— AI 能给看似合理的数字和解释，但两者都可能经不起语料核对。

## 疑问（待查）

- [ ] #LancsBox X 5.0.3.x（课件）与官网 6.0.2 的查询语法、标注功能是否一致？
- [ ] 讲义里 BNC2014 是 102M tokens，官方规模口径是多少（含/不含标点、按 CLAWS7 token）？
- [ ] “basis for normalization” 取 1M 是课程统一规定，还是按语料规模选？做 keyness 时换不换？
- [ ] 标注功能里“随机抽 10 条”是抽样策略还是仅演示？正式做评价标注时样本量怎么定？

## 术语新增 → [glossary/terms.md](../glossary/terms.md)

- dispersion（pt1 首次出现）、semantic prosody、multi-word expression
- absolute / relative frequency、basis for normalization、Zipf’s law、subcorpus
- CQL / CEQL、p-attribute / s-attribute、headword

## 参考

- [#LancsBox 官网的工具史时间线](../reference/corpus-linguistics-history.md)（pt1 二维码指向；1900s–1993，7 个节点）
- 课程材料 1.3：CASS 术语表（38 条）→ [来源记录](../glossary/cass-key-terms.md)
- 查询语法 → [CQL 速查](../reference/cql-cheatsheet.md)
- 材料 5：Brezina (2025) → [阅读笔记](../reference/reading-brezina-2025-ai.md)
- Brezina, V. (2018). *Statistics in Corpus Linguistics*, ch. 2（Zipf 细节）→ [章节地图](../reference/book-brezina-2018.md)
- Leech, G. (2011).（pt2 引用，未下载）
- Kilgarriff, A. (2007). Last words: Googleology is bad science. *Computational Linguistics*, 33(1), 147–151.（pt3 引用）
- Brezina, V. & Gablasova, D. *A Frequency Dictionary of Multi-Word Expressions in British English*. Routledge.（pt4 展示）
