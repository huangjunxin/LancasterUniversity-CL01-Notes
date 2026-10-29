# corpora/ — 语料清单

原则：**语料原文不入库**（版权 + 体积）。这里只记“用哪个、从哪来、怎么处理过”。

## 清单

| 语料 | 在哪 | 大致用途 | 卡片 |
|---|---|---|---|
| BNC 1994（XML edition） | CQPweb | 通用参照语料，几乎所有比较的基准 | 待建 |
| Spoken BNC2014 | CQPweb / BNCLab | 口语、社会变量、与 1994 对比 | 待建 |
| British English 2006 / 2021、American English 2006、B-Brown 1930s、Brown Family (extended) | CQPweb | 跨变体、跨时间对比 | 待建 |
| 50% sample of ukWaC | CQPweb | 大规模网络语料，观察高频模式 | 待建 |
| 自建语料 | 本地 | 第 4 周作业 / 结课项目 | 见 [第 4 周](../weeks/04-build-your-own-corpus.md) |

“待建”= 还没填卡片；用之前从 [_语料卡片模板.md](_语料卡片模板.md) 复制一份，文件名用小写英文 slug。

## 记录纪律

- 规模（token 数）、版本、获取日期必须记，否则频率无法换算 per million
- 预处理（清洗、去重、大小写、编码）写进卡片，不要写“已清洗”了事
- 授权状态写清楚：能不能再分发，决定它能否进这个仓库
