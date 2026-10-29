# 术语表（中英对照）

**分工**：本页是工作译名底座 —— 笔记里出现的术语，写法必须和这里一致；先加表，再引用。
官方定义来自课程材料 1.3（CASS 术语表），见 [cass-key-terms.md](cass-key-terms.md)；“官方页”列给页码，一句话释义是我的转写，不是原文。
“建议周次”是按大纲推的，听课后校正。

| English | 中文 | 一句话 | 官方页 | 建议周次 |
|---|---|---|---|---|
| absolute frequency | 绝对频率 | 某表达在语料中出现多少次，直接数 hits | — | W1 |
| annotation | 标注 | 叠加在原文上的编码信息（如语法范畴），也指加这些信息的过程 | p5 | W2 |
| balance | 平衡性 | 采样框里各子集的比例经过设计，使语料能覆盖目标语言的各类文本 | p5 | W1 |
| basis for normalization | 归一化基数 | 把绝对频率换算成相对频率时所除的单位（如每百万词） | — | W1 |
| CEQL | 简易查询语言 | CQPweb 默认的 simple query 语法，CQP 语法的简化替代 | — | W1 |
| colligation | 类联接 | 语法范畴之间的共现，或词与语法范畴之间的共现 | p5 | W2 |
| collocation | 搭配 | 词或短语之间的共现关系：一个词出现时另一个更可能出现 | p5 | W2 |
| comparability | 可比性 | 两个语料（子库）的采样框相似或相同，才可比较 | p5 | W4 |
| concordance | 索引 / 语境共现 | 检索项每次出现时连前后语境一起列出 | p5 | W1 |
| concordancer | 索引工具 | 能从文本或语料生成 concordance 的程序 | p5 | W1 |
| corpus / corpora | 语料库 | 某语言变体或体裁的代表性语言集合，以电子形式存储、供软件分析 | p6 | W1 |
| corpus construction | 语料库建设 | 设计、采文、编码、组装、存元数据、加标记、可能再加标注的全过程 | p6 | W4 |
| corpus-based | 语料库为基 | 用语料检验预设假设或例证既有理论（区别于 bottom-up 的 corpus-driven） | p6 | W1 |
| corpus-driven | 语料库驱动 | 自下而上从数据里找模式，再用模式解释规律与例外 | p6 | W1 |
| CQL | 语料库查询语言 | 用“token + 标注 + 结构”写查询的语言；#LancsBox 与 CWB/CQP 都支持，写法有差异 | — | W1 |
| diachronic | 历时的 | 采样跨时间段的文本，用来研究语言使用的变化 | p6 | W5 |
| dispersion | 离散度 | 一个词在全库各文本/子库里的分布是否均匀，光有总频掩盖“全挤在一两篇里” | — | W2 |
| encoding | 编码 | 用标记语言与标注表示文本结构的过程 | p6 | W4 |
| frequency list | 词频表 | 某类项目（词、名词、四词序列等）及其出现次数的清单 | p7 | W1 |
| headword (hw) | 词元条目 | 查询语法里由 hw 指定，sit 一次覆盖 sit / sits / sat / sitting | — | W1 |
| key word in context (KWIC) | 关键词居中 | 节点词居中、左右语境分列的显示方式；此处的 key word 指“检索词” | p7 | W1 |
| keyword | 关键词 | 在目标文本/语料中比在某参照语料中显著更频繁的词 | p7 | W2 |
| lemma | 词元 | 只靠屈折变化区分的一组词形所属的基础词（walked/walking/walks → WALK） | p7 | W2 |
| lemmatisation | 词形还原 | 一种标注：给每个 token 标出所属 lemma | p7 | W2 |
| lexis | 词汇 | 语言中的词及其他有意义单位（如习语） | p7 | W3 |
| lockword | 锁定词 | 在目标语料与参照语料中频率相近的词，是 keyword 的对照面（Brezina 2018 §3.4） | — | W3 |
| markup | 标记 | 插进语料文件、表示原文非词语特征（段落、缺图、版式）的编码 | p7 | W4 |
| markup language | 标记语言 | 把标记（及标注、元数据）写进机器可读文本的标准，今天即 XML | p8 | W4 |
| metadata | 元数据 | 关于数据的数据：作者、出版日期、标题等 | p8 | W4 |
| monitor corpus | 动态语料库 | 持续增补新文本，始终同时代表最新与较早的语言状态 | p8 | W4 |
| node | 节点词 | 正在研究其共现模式的那个词 | p8 | W2 |
| p-attribute | 位置属性 | 每个 token 上的一列标注：word、hw、pos、sem 等 | — | W1 |
| reference corpus | 参照语料库 | 不针对某变体、而以代表性采样框代表语言总体，供关键词等比较 | p8 | W2 |
| relative frequency | 相对频率 | 每给定词数（如 1M）出现多少次，可跨不同规模的语料比较 | — | W1 |
| representativeness | 代表性 | 采样使语料含全部应有的文本类型且比例正确，从而准确反映整体 | p8 | W1 |
| s-attribute | 结构属性 | 覆盖一段文本的结构标注（句 s、话轮 u、text），CQL 里写作 <s/> | — | W1 |
| sample | 样本 / 采样 | 收入语料的单篇文本或其节选；也指统计意义上从总体抽出的个案；还常说语料是“语言的一个样本” | p9 | W4 |
| sample corpus | 抽样语料库 | 在指定采样框内追求平衡与代表性的语料 | p9 | W4 |
| sampling frame | 采样框 | 规定如何从文本总体中取样、取哪些类型、哪段时间、样本数量与长度的规则 | p9 | W4 |
| significance test | 显著性检验 | 判定结果统计显著性的数学程序 | p9 | W2 |
| statistical significance | 统计显著性 | 结果纯属偶然的概率很低（通常 <5%）即称显著 | p9 | W2 |
| subcorpus | 子语料库 | 语料库中按元数据切出的一部分（如 informal speech），查询结果与它绑定 | — | W1 |
| synchronic | 共时的 | 只看某一时间点的语言状态，不涉变化 | p9 | W5 |
| tagging | 标注（打标） | annotation 的口语说法，尤指给每个词都分配分析（词性、语义标注） | p10 | W2 |
| text | 文本 | 作可数名词：任何含语言使用的产物；作不可数名词：收集到的语篇 | p10 | W3 |
| token | 词次 | 文本中某一个具体词形的每一次出现 | p10 | W1 |
| type | 词型 | 一个具体词形；写法有差就是不同类型（也用于“文本类型”） | p10 | W1 |
| type-token ratio | 型次比 | 词型总数 ÷ 词次总数，衡量词汇多样性；**不同规模的语料之间不可比** | p10 | W2 |
| XML | XML | 当前语料与网络数据传输的通用标记语言，标签用尖括号 | p10 | W4 |
| POS tagging | 词性标注 | 为每个 token 标词性 | — | W2 |
| hapax legomenon | 一次词 | 全库只出现一次的词 | — | W1 |
| collocate | 搭配词 | 与节点词共现的词 | — | W2 |
| span | 跨距 | 围绕节点词取左右各几个词 | — | W2 |
| keyness | 关键性 | 目标语料相对参照语料的频率突出程度 | — | W2 |
| mutual information (MI) | 互信息 | 共现强度指标，偏向低频稀有搭配 | — | W2 |
| log-likelihood | 对数似然 | 共现显著性统计量（G²），对高频敏感 | — | W2 |
| logDice | logDice | 搭配强度指标，对单词语频依赖小，跨语料较可比 | — | W2 |
| effect size | 效应量 | 差异的大小，与“是否显著”分开报 | — | W2 |
| register | 语域 | 由使用情境决定的语言变体 | — | W3 |
| learner corpus | 学习者语料库 | 二语学习者产出构成的语料 | — | W7 |
| Zipf's law | 齐夫定律 | 按频率排序，第 n 高频项的频次约为第 1 项的 1/n，故证据量快速衰减 | — | W1 |

“官方页”为空（—）的条目不在 CASS 术语表里，是课程通用或我自己补的计量术语。

## 待补（听到再写）

-
