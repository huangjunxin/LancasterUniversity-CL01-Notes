# 阅读笔记：Brezina (2025) Corpus linguistics and AI

## 书目

| 项 | 内容 |
|---|---|
| 作者 | Vaclav Brezina（Lancaster University） |
| 出处 | *International Journal of Language Studies*, Vol. 19, No. 2, April 2025, pp. 75–90 |
| 类型 | position paper（立场/论述文，不是实证研究） |
| DOI | 10.5281/zenodo.15250820（文章首页印有；zenodo 链接本机访问返回 403，**开放获取状态未核实**） |
| 课程内编号 | 文件名 `5-Brezina-192`；归属哪一周待确认（见 [NOTES.md](../NOTES.md)） |

## 一句话

AI 处理的是“形式”，理解“意义”仍要人在语境里做；语料库语言学给的是第三条路 —— **transparent evidence + functional context**，而不是把分析者工程化掉。

## 结构（印刷页码）

| 节 | 内容 | 页 |
|---|---|---|
| 1 | Introduction：AI 给出的“语料库语言学”定义与图示 | 75 |
| 2 | Understanding language: the corpus linguistics approach | 79 |
| 3 | #LancsBox X: a software tool responding to emerging technologies | 83 |
| 4 | Conclusions：数据 vs 解释（星空/星座之喻） | 88 |

## 论点链（五步）

1. **图灵 imitation game**：外部行为等价就算“会”——功能主义标准
2. **塞尔 Chinese room**：按规则搬运字符串，不等于理解意义
3. **关键区分 form vs meaning**：电脑处理编码为 0/1 的形式，人交流意义；意义来自社会互动与语境（引 Wittgenstein 的 language games）
4. **LLM 的两个问题**：不透明黑箱（结果不可复现、来源不可追溯）；训练在 AI 生成数据上还有 model collapse 风险（引 Shumailov et al., 2024）
5. **语料库的回应**：人仍是分析中心，做法“does not engineer the analyst out of the picture”；给出三条语言建模路径

## 三条语言建模路径（Figure 4，p80）

| 路径 | 做法 | 局限 |
|---|---|---|
| form matching（如 sentiment analysis） | 用词典形式去匹配真实文本 | 语言上过于简单，看不见反讽 |
| LLM / 机器学习 | 复杂模型 | 黑箱；不可复现；不可溯源 |
| **corpus linguistic approach** | 透明证据 + 功能语境 | 需要人来解释 |

第三者的分水岭就两个词：**transparent evidence** 与 **functional context**。

## 全文最好用的例子（p81–82）

一段文本里出现 4 次形容词 **good**，问它表达什么：

- **sentiment analysis**：good 频繁 → 判为正面
- **ChatGPT**：换个问法，给出两个互相矛盾的结论；取决于提问措辞
- **concordance**：看四条语境 —— “‘This is good’, said the Mad Hatter”；“I cannot say that this would be good”；“Many claim that this is good. I don't agree.”；“Good? That's a laugh!” → 其实**强烈负面、反讽**

结论：四次的“形式频率”完全一样，意义只能靠语境（concordance）才看得见。这个例子可以直接搬到第 2、3 周讲 KWIC 与话语分析。

## 与 #LancsBox X 有关的事实（p83–88）

- 免费，Windows / macOS / Linux，普通笔记本可跑
- **GraphColl**：搭配表 + 搭配图，鼠标悬停即看语境
- 内置大语料示例：**Hansard Corpus**（1802 年至今英国议会发言，约 **20 亿词**）
- 摘要提到 **web scraping** 功能
- 支持访问 **metadata**（说话人背景、性别、年龄、社会经济地位等）
- 文中预告 **easy annotations**：自定义类别与层级（如 evaluation: negative / neutral / positive）+ 颜色高亮

> 版本注意：文中引用写作 Brezina & Platt (2024)，官网当前署名 2026、版本 6.0.2。引用时以官网为准，正文里的功能描述可能对应更早版本。

## 对课程的实际用法

课程标题就是 “Corpus linguistics and **new technologies**: data, language and society”，本文基本是这条线的理论支撑。三条可操作的检查（我按论文逻辑转写，不是原文）：

1. 任何 LLM 辅助得到的结论，先问“**能不能复现同一个结果**”
2. 频率相同不等于意义相同 —— 四个 good 就是反例，**语境不是装饰**
3. 工具是否可解释，本身算方法的一部分

## 引用格式

Brezina, V. (2025). Corpus linguistics and AI: #LancsBox X in the context of emerging technologies. *International Journal of Language Studies*, 19(2), 75–90. https://doi.org/10.5281/zenodo.15250820

## 不入库

期刊版权 + 仓库 PUBLIC：PDF 不入库，本地放 `source/`（已 gitignore）；这里只留书目、结构、论点与我自己转写的内容。
