# #LancsBox X

官网：https://lancsbox.lancs.ac.uk/ （2026-10-29 核实可访问）

## 是什么

兰卡斯特大学（ESRC CASS）开发的语料库分析软件，第一作者 Vaclav Brezina，即本课主讲之一。官网当前版本 **6.0.2**，免费，提供主流操作系统的安装包。

引用格式（官网给出）：
> Brezina, V. & Platt, W. (2026). `#LancsBox X` [software]. Lancaster University. http://lancsbox.lancs.ac.uk.

## 能干什么

官网的功能演示分成六块，课程里都会用到：

| 功能 | 作用 |
|---|---|
| KWIC | 检索词居中的语境行，最基础的查法 |
| GraphColl | 搭配网络可视化 |
| Words | 词频、关键词一类统计 |
| Text | 单篇文本层面的观察 |
| Advanced queries | 复杂查询；实际就是 CQL，语法见 [CQL 速查](../reference/cql-cheatsheet.md) |
| Wizard | 向导式流程，新手跟着点 |
| 内置语料 | 如 Hansard Corpus（1802 至今英国议会发言，约 20 亿词） |
| 多窗口联动 | KWIC / Text / GraphColl / Words 可并存，高亮多个窗口可一次查询全部 |
| web scraping | 抓取网络文本进语料（见 Brezina 2025 摘要） |
| 标注 concordance 行 | 给索引行打类目（如 evaluation: negative / neutral / positive），可抽样、自动统计占比（pt3 演示） |

配套还有：英文 / 中文 / 日文手册、英文速查表（cheat sheet）、练习（exercises）。**中文手册存在**，卡住先翻它。

## 怎么起

安装三步（录像 1.14）：

1. 打开 https://lancsbox.lancs.ac.uk/ ，点 **Download now for free** —— 会自动选对操作系统的版本（也可在下方按系统单独下载）
2. 跑安装包，按向导走完
3. 启动。部分系统会弹安全警告，属正常；官网说明 #LancsBox X 可安全运行，按提示给权限即可

装好之后**自带一个示例语料库**，可以直接开练。

### 上手要点

- **多窗口**：默认只有 KWIC，可以再加 Text、GraphColl、Words 窗口，拖拽、最大化、删除都行
- **多窗口同时搜**：按住 ctrl 点选多个窗口，被高亮的全部生效，输入一次就同时查
- **默认大小写不敏感**：打 `new` 也能命中 `New`；要严格匹配用 `==`
- **通配符**：`new*` 命中 new、newspaper 等
- **smart search**：全大写输入，`PASSIVE`、`ADJ NOUN` 之类，见手册第 13 节的定义（p45）
- **CQL**：方括号开头，如 `[word="new"]`、`[word="new" pos="J.*"]`，详见 [CQL 速查](../reference/cql-cheatsheet.md)

### 加语料的三条路（手册第 2 节，p6–9）

| 方式 | 做什么 |
|---|---|
| **Corpus hub** | 从内置商店下载公用语料（如 BNC2014） |
| **My data** | 指向本地文件，起名、选语言、决定要不要语法/语义标注 |
| **Web** | 网页抓取：起名、选语言、填初始 URL、设定抓取网站数与深度（跟随外链几层），点 Create corpus |

手册还有导出语料（2.4）与 draft corpora（2.5）两节。

### 手册版本

本地/官网的 `Manual_EN.pdf` 对应 **#LancsBox X 5.0.0**（Brezina & Platt 2024，50 页），官网当前版本是 **6.0.2** —— 界面细节可能有出入，按 6.x 实际操作。

手册目录速查：1 下载运行 · 2 加语料 · 3 KWIC · 4 GraphColl · 5 Words（含 keywords / key n-grams） · 6 Text · 7 Wizard（含 R 代码） · **8 Searching（CQL 在 8.5，p32–36）** · 9–12 标签集附录（spaCy POS / dependency、CLAWS C7、USAS） · 13 smart search 定义 · 14 术语表。

## 常用查询串

先记三条起步的，其余见 [reference/cql-cheatsheet.md](../reference/cql-cheatsheet.md)。

| 查询 | 在查什么 |
|---|---|
| `[hw="sit" pos="V.*"] through within <s/>` | 词元 sit 的动词形式 + 紧接 through，限同句 |
| `[word="[aeiou].*"]` | 元音开头的词形（引号里是正则） |
| `very{2} good` | very very good |

## 我的操作记录

| 日期 | 语料 | 我要做什么 | 操作路径 | 参数 | 结果 |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## 坑

| 现象 | 原因 | 解法 |
|---|---|---|
| 界面和课件截图对不上 | 课程讲义基于 #LancsBox X 5.0.3.9，官网当前 6.0.2 | 按 6.x 操作；查询语法先拿小样试跑，别整套照搬 |

## 参考

- 官网手册（中/英/日）与 cheat sheet
- Brezina et al. (2015)、Brezina et al. (2021) —— 官网 Research Papers 区可下载
- 官网 [History of corpus linguistics](https://lancsbox.lancs.ac.uk/history/) —— 已照录进 [reference/corpus-linguistics-history.md](../reference/corpus-linguistics-history.md)
