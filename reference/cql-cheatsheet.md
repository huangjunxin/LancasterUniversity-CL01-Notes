# CQL 速查：从课程那条查询出发

课程第 1 周那条查询 `[hw="sit" pos="V.*"] through within <s/>` 引出两个常问的问题，先给结论。

## 0. CQL 和 BNC2014 是配套的吗？

不是一对一配套，是两层关系。

**第一层：语法。** CQL（Corpus Query Language）是查“token + 标注 + 结构”的通用语言，不绑定任何语料。#LancsBox X 手册第 8 节原话：支持 CQL 搜索（simple / wildcard / smart / CQL 四种层次）。

**第二层：标注。** 能写哪些属性，取决于语料带了什么标注。手册原文：

> The levels of annotation and syntax depend on the tagging of the corpus, but for XML corpora it is common to have i) word, ii) headword/lemma (hw), iii) part-of-speech (POS), and iv) a user-defined tag.

BNC2014 在 #LancsBox 里带的是：词形 `word`、词元 `hw`、CLAWS7 词性 `pos`、USAS 语义 `sem`，外加 XML 结构（`<s>` 句、`<u>` 话轮、`<text genre="...">`）。所以讲义那条能跑。

官方 cheat sheet 也写明了前提：

> These examples assume CLAWS7 POS-tags and USAS semantic tags.
> These are examples for the BNC2014. Other corpora use different XML elements and attributes.

**所以：语法可以迁移，属性名和 XML 元素名不能盲抄。** 换一个没有词性标注的自建语料，`pos="V.*"` 直接失效；换成 BNClab 或 CQPweb 里的语料，元素名也可能不同。

## 0.5 为什么换个工具写法就不一样

同叫 CQL，实现不同：

| 环境 | 模式 | 属性连接 | 例子 |
|---|---|---|---|
| #LancsBox X | CQL | 方括号内**空格分隔** | `[word="goes" hw="go" pos="V.*" sem="M1"]` |
| CQPweb | Simple query（CEQL） | 另一套简写（`_pattern` / `{pattern}` 等） | 见 CEQL 手册 |
| CQPweb | CQP syntax（CWB 体系） | **& 连接** | `[pos="JJ" & lemma="dry"]` |

三者概念相通，**字符串不能直接互贴**。课程演示用的是 #LancsBox 的写法。

## 1. 构件表（#LancsBox X 6.x）

| 想干什么 | 写法 | 例子 |
|---|---|---|
| 纯词 / 短语 | 直接写 | `cup of tea`、`adam's apple` |
| 单属性约束 | `[属性="正则"]` | `[word="[aeiou].*"]`（元音开头）、`[hw="like"]`（词元 like） |
| 同一 token 多属性 | 空格分隔 | `[word="professional" pos="J.*"]` |
| 排除 | `!=` | `[word="jump.*" word!=".*ing"]` |
| 大小写敏感 | `==` / `!==` | `[word=="LaTeX"]`、`[word="the" word!=="THE"]` |
| 任意一个 token | `[]` | `[word="green|blue"][]` |
| 精确重复 n 次 | `{n}` | `very{2} good` |
| 重复 m–n 次 | `{m,n}` | `really []{1,3} day`、`([](plus []){2,10})` |
| 出现 0 或 1 次 | `?` | `[pos="VB.*"] []{0,3} [pos="V.N"]?` |
| 分组后量化 | `(...)` | `([pos="N.*"] [word="and"]){2}` |
| 词 + 结构混写 | 直接混 | `very{2} ADJECTIVE{1,2} [hw="year"]` |
| 智能查询 | 大写词 | `NOUN`、`SPLIT_INFINITIVE`、`EMOTION` |
| 标点 | `/punc="..."` | `/punc="\\.|\\?"/` |
| 结构元素 | `<元素/>` | `<s/>`（整句）、`<u/>`（话轮）、`<text genre="newspaper"/>` |
| 带属性约束的结构 | `<元素 属性="值"/>` | `<u n="1" nationality="British|American"/>` |
| 范围组合 | `{within}` / `{containing}` | `[pos="D.*"] green NOUN within <text genre="newspaper"/>` |
| 反向范围 | `{!within}` / `{!containing}` | `thanks {!within} no thanks` |
| 优先级 | 最左优先，括号改 | `<s/> {containing} yes {within} <abstract/>` |

两条容易忽略的规则（官方 cheat sheet）：

- `Y {containing} X` 等价于 `X {within} Y`，只要求 Y 包含 X 的全部 token
- 运算符**最左边**的先结合，除非加括号

## 2. 学习路线（7 步，每步一条自测查询）

不要从头背语法。按“改一个条件、看命中数怎么变”来学，每步都留记录。

| 步 | 自测查询 | 学到什么 |
|---|---|---|
| 1 | `[hw="like"]` vs `[word="like"]` | hw 是词元（likes/liked 也算），word 是具体词形。命中数差异就是词形还原的作用 |
| 2 | `[word="[aeiou].*"]` | 引号里是正则，不是通配符 |
| 3 | `[word="professional" pos="J.*"]` vs 只用 word | 同一 token 的多层标注约束 |
| 4 | `[hw="sit" pos="V.*"] through` vs 加 `within <s/>` | 邻接 ≠ 相邻；句界会切掉跨句匹配 |
| 5 | `very{2} good`、`[pos="VB.*"] []{0,3} [pos="V.N"]?` | 量化与跨度 |
| 6 | `<u/>`、`<text genre="fiction"/>` | 结构也是可查的对象 |
| 7 | 同一条查询拿到 CQPweb 里换 CQP syntax 写 | `&` 与空格的区别；CEQL 与 CQL 的区别 |

## 3. 练习材料（官方，均已实测可下载）

| 材料 | 用途 |
|---|---|
| [Cheatsheet 6.0.0 (EN)](https://lancsbox.lancs.ac.uk/data/materials/Cheatsheet_6.0.0_en.pdf) | 一页纸语法全表，贴在旁边用 |
| [Manual (EN)](https://lancsbox.lancs.ac.uk/data/materials/Manual_EN.pdf) | 第 8 节第 5 点（印刷 p34–36）是 CQL 正式说明 |
| [Ex_KWIC](https://lancsbox.lancs.ac.uk/data/materials/Ex_KWIC.pdf) · [Ex_Words](https://lancsbox.lancs.ac.uk/data/materials/Ex_Words.pdf) · [Ex_Text](https://lancsbox.lancs.ac.uk/data/materials/Ex_Text.pdf) · [Ex_GraphColl](https://lancsbox.lancs.ac.uk/data/materials/Ex_GraphColl.pdf) | 官方分级练习，配 answers 版 |
| [Ex_Building_corpus](https://lancsbox.lancs.ac.uk/data/materials/Ex_Building_corpus.pdf) · [Ex_DDL](https://lancsbox.lancs.ac.uk/data/materials/Ex_DDL.pdf) | 建库与 DDL 场景，第 4、7 周用得上 |
| [CQPweb CEQL 手册](https://cqpweb.lancs.ac.uk/doc/CQPweb-CEQL-manual.html) | 换到 CQPweb 时的 simple query 语法 |

## 4. 记录纪律

每条查询记四样，记在 [tools/lancsbox-x.md](../tools/lancsbox-x.md) 的「我的操作记录」里：

1. 查询串（原样，含引号）
2. 语料 + 子库（BNC2014 / whole corpus 还是 informal speech）
3. 命中数（absolute + relative）
4. 一句解读：这个结果说明什么

**改一个条件就记一行。** 第 2 步起，学习效果全部来自对照，不来自背。

## 5. 参考

- #LancsBox X Manual (EN)，第 8 节 Searching（CQL 部分在印刷 p34–36）
- #LancsBox X Query cheat sheet 6.0.0
- CQPweb CEQL manual
- 本仓库 [Brezina 2018 章节地图](book-brezina-2018.md)：ch2 §2.3 讲词频表，ch3 §3.2 讲搭配度量
