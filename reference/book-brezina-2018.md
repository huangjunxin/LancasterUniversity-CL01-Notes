# 教材：Brezina (2018) Statistics in Corpus Linguistics

课程第 1 周讲义 p6 直接引 “Brezina 2018: chapter 2”；[方法速查](methods-cheatsheet.md)里的公式也以它为准。本页只做**书目 + 目录地图 + 按周路线**，用来查章节，不替代读原文。

## 书目

| 项 | 内容 |
|---|---|
| 作者 | Vaclav Brezina（本课主讲） |
| 书名 | *Statistics in Corpus Linguistics: A Practical Guide* |
| 出版 | Cambridge University Press, 2018 |
| DOI | https://doi.org/10.1017/9781316410899 （2026-10-29 核实可解析） |
| 篇幅 | 316 页（PDF 页）；正文 8 章 + Final Remarks |
| 结构惯例 | 每章：本节要点 → 概念 → 应用 → Exercises → **Things to Remember** → Advanced Reading |

页码换算：**印刷页码 = PDF 页码 − 20**（Contents 在 PDF p7，正文第 1 页 = PDF p21）。

## 目录地图（印刷页码）

| 章 | 主题 | 主要小节 |
|---|---|---|
| 1 | Introduction: Statistics Meets Corpus Linguistics (1) | 1.2 什么是统计 · 1.3 基本统计术语 (5) · 1.4 建库与研究设计 (15) · 1.5 探索数据与可视化 (22) · 1.6 应用：小说家比学者更爱用形容词吗 (30) · 1.7 Exercises (32) |
| 2 | Vocabulary: Frequency, Dispersion and Diversity (38) | 2.2 Tokens, Types, Lemmas and Lexemes (38) · 2.3 词频表里的词 (42) · **2.4 The Whelk Problem: Dispersion（离散度）** (46) · 2.5 Average Reduced Frequency (53) · 2.6 TTR / STTR / MATTR (57) · 2.7 应用：英国人天天聊天气吗 (59) |
| 3 | Semantics and Discourse (66) | **3.2 Collocations and Association Measures** (66) · 3.3 搭配图与搭配网络 (75) · **3.4 Keywords and Lockwords** (79) · 3.5 人工编码的评分者一致性 (87) · 3.6 应用：英国报纸读者怎么看移民 (92) |
| 4 | Lexico-grammar (102) | 4.2 分析词汇语法特征 (103) · 4.3 交叉表、百分比与卡方 (108) · 4.4 Logistic Regression (117) · 4.5 应用：that 还是 which (130) |
| 5 | Register Variation (139) | 5.2 变量间关系与相关 (139) · 5.3 层次聚类 (151) · 5.4 多维分析 MD (160) · 5.5 应用：新西兰英语的语域 (170) |
| 6 | Sociolinguistics and Stylistics (183) | 6.2 个体风格与社会变异 (183) · **6.3 组间比较：t 检验、ANOVA、Mann–Whitney U、Kruskal–Wallis** (186) · 6.4 对应分析 (199) · 6.5 混合效应模型 (207) · 6.6 应用：白宫里的这个人是谁 (211) |
| 7 | Change over Time (219) | 7.2 时间作为变量 (219) · 7.3 百分比变化与 Bootstrap 检验 (229) · 7.4 相邻聚类 (235) · 7.5 峰值、低谷与 UFA (241) · 7.6 应用：17 世纪的颜色 (247) |
| 8 | Bringing Everything Together (257) | **8.2 统计思维的十个原则** (257) · 8.3 Meta-analysis (267) · **8.4 Effect Sizes（效应量实用指南）** (275) · 8.5 Exercises (280) |

其他：Figures (x)、Tables (xiv)、About This Book (xvii)、Final Remarks (283)、References (285)、Index (294)。

## 按周查阅路线（我按主题推的，不是课程指定阅读）

| 周 | 建议先读 | 理由 |
|---|---|---|
| 1 Introduction | ch1 §1.3–1.5；ch2 §2.2–2.3 | 讲义的 absolute / relative frequency 与 Zipf，落点在 §2.3 词频表 |
| 2 Key methods | **ch3 §3.2**（关联度量）；**3.4**（keywords / lockwords）；ch2 §2.4、2.6 | 搭配与关键词的正式口径；TTR 为什么不可跨语料比 |
| 3 Discourse analysis | ch3 §3.4 + §3.6 案例；ch5 §5.4 | 从关键词走到话语与语域 |
| 4 Build your own corpus | ch1 §1.4 | 研究设计决定采样框，不是反过来 |
| 5 Sociolinguistics | ch6 §6.2–6.3；ch7 §7.3；ch2 §2.4 | 组间比较、历时变化、离散度 |
| 6 Language testing | ch8 §8.4（效应量） | 本书无专章；测试场景至少要报效应量 |
| 7 Language learning | ch4、ch8 §8.2 | 本书无专章；用统计模型与十原则兜底 |
| 8 Swearing case study | ch1 §1.5；ch6；ch8 | 个案分析 + 差异化解读 |
| 收尾 | ch8 全章 | 十个原则 + 效应量，等于全书总结 |

## 怎么用这本书

1. **不要通读**。它是手册型教材，按周查章，读 "Things to Remember" 先建立骨架
2. 每章末尾有 Exercises，作为自测；有答案的话可以当练习
3. 教材口径与课程视频冲突时，**以课程为准**（AGENTS 规则），但把差异记进 [learning-records/](../learning-records/)
4. 公式只抄结论不够：§3.2 讲的是“不同关联度量偏向什么”，这决定了你该报 MI、logDice 还是 G²

## 授权与不入库

PDF 元数据自述：`Downloaded from https://www.cambridge.org/core. Access paid by the UCSB Libraries, on 18 Sep 2018`，每页带版权水印 —— 这是**图书馆授权下载**的副本，不是可转发的个人购买件。

- CUP 版权；本仓库为 PUBLIC
- 因此：PDF 不入库，本地放 `source/`（已 gitignore）
- 仓库里只保留书目、目录结构与页码索引

## 引用格式

Brezina, V. (2018). *Statistics in Corpus Linguistics: A Practical Guide*. Cambridge: Cambridge University Press. https://doi.org/10.1017/9781316410899
