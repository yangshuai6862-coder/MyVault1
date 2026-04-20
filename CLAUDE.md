# MyVault1: 产品经理知识库

Owner: yangs | 综合产品经理 | 触控笔/应变计/Amazon运营/专利/APP合作
Updated: 2026-04-14

## 目录结构

```
vault/
├── _templates/                   # 模板(7个)
├── Clippings/                    # 网页剪藏
├── Excalidraw/                   # 绘图
├── Attachments/                  # 附件
└── wiki/
    ├── index.md                  # 主索引
    ├── log.md                    # 操作日志(只追加)
    ├── hot.md                    # 最近上下文
    ├── patent/                   # 专利文档
    ├── competitor/               # 竞品分析
    │   └── 竞品分析报告/
    ├── tech-issue/               # 技术问题
    │   ├── 应变计相关/
    │   └── APP相关/
    ├── market/                   # 市场信息
    │   └── Amazon运营操作/
    ├── diary/                    # 日记
    ├── meeting/                  # 会议纪要
    └── compilation/              # 资料汇总
```

## Frontmatter

必填:
```yaml
title: <中文标题>
type: <类型>
created: YYYY-MM-DD
updated: YYYY-MM-DD
```

| type        | 说明   | 特有字段                                  |
| ----------- | ---- | ------------------------------------- |
| patent      | 专利文档 | patent_type, patent_status, inventors |
| competitor  | 竞品分析 | product, brand                        |
| tech-issue  | 技术问题 | severity, root_cause                  |
| diary       | 日记   | -                                     |
| market      | 市场信息 | source_url                            |
| meeting     | 会议纪要 | meeting_date, participants, location  |
| compilation | 资料汇总 | -                                     |

可选: `status`, `tags`, `area`(触控笔|应变计|Amazon运营|APP|通用), `related`

## 模板

`_templates/` 下 7 个模板: patent, competitor, tech-issue, diary, market, meeting, compilation

## 规范

- 中文文件名，日期放 frontmatter
- Wikilink: `[[笔记名称]]` | 附件: `![[]]` | 外部URL: markdown链接
- 专利: 专利标题 | 竞品: 产品名称 | 日记: YYYY-MM-DD.md | 会议: YYYY-MM-DD 主题.md

## 操作

- **Ingest**: 放 `.raw/`，说 "ingest [文件名]"
- **Query**: 直接提问
- **Lint**: "lint the wiki"
- **Save**: "save this"
- **Log**: 新条目追加到 log.md 顶部
