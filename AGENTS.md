# AGENTS.md — 本仓库的 AI 工作约定

这是兰卡斯特 CL01 课程的个人笔记仓库。本文件是 agent 的权威约定；执行与本文件冲突时，先改本文件再照做。

## 事实来源与禁止事项

- **课程事实**（周次、主题、日期、工具）只认 [CURRICULUM.md](CURRICULUM.md)。不凭记忆补写课程内容。
- 没听过/没看过的课，笔记里只能写"待听课"，**不许编造课程观点、案例或讲师立场**。
- 外部链接写进仓库前必须实测（curl 或浏览器打开），**不构造 URL**。这条是硬规则。
- 统计口径（MI、logDice、log-likelihood、keyness、effect size）以课程讲授为准；[reference/methods-cheatsheet.md](reference/methods-cheatsheet.md) 只是课前预读，冲突时改速查表并记进 learning-records。

## 语言与写作

- 讲解用中文，术语保留英文原词（首次出现写成"concordance（索引/语境共现）"这种）。
- `glossary/terms.md` 是术语译名的底座：笔记里出现的术语写法必须与它一致，新增术语先加表再引用。
- 笔记短、可操作优先于完整：一个能复现的操作步骤，胜过三段概念转述。
- 表格优先于长段落；截图用相对路径 `../assets/...` 引用。

## 目录约定

- 周笔记 `weeks/NN-slug.md`，八周文件已存在，**只填不改名**（改名会断看板与互链）。
- 新建周笔记一律从 [templates/weekly-note.md](templates/weekly-note.md) 生成。
- 工具卡 `tools/<tool>.md`：固定五节（是什么 / 能干什么 / 怎么起 / 我的操作记录 / 坑）。
- 语料卡 `corpora/<slug>.md`：从 [corpora/_语料卡片模板.md](corpora/_语料卡片模板.md) 复制。
- 讲义（幻灯片 PDF）转进 `weeks/NN-*.md` 的「笔记」与「工具实操」，按 slide 页码标注来源；原件不入库。
- 截图放 `assets/`，命名 `YYYY-MM-DD-weekNN-描述.png`。
- 进度状态**只在 README 看板**维护，别的文件不写状态。

## 数据与提交

- 语料原文、下载包、数据库文件**不入库**（版权 + 体积）；只记来源、版本、获取日期、预处理参数。
- 课程 PDF / 讲义原件也**不入库**：留一页来源记录（元数据、结构、关键要点）＋ 术语并入 `glossary/terms.md`；原件放 `source/`（已 gitignore）。
- 提交用仓库级身份 `huangjunxin <huang-junxin@qq.com>`，不要改。
- 提交信息用中文祈使句，一次提交一件事。
