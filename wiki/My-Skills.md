---
title: My Skills
type: reference
created: 2026-04-17
updated: 2026-04-17
tags: [skills, claude-code, config]
area: 通用
---

# My Skills 总览

> 所有 Claude Code 技能清单，按来源分类。当前共 **4 个全局本地技能 + 6 个项目级技能 + 4 个已安装插件（含约 14 个可用技能）+ 若干内置技能**。

## 内置技能（Claude Code 自带）

| 技能名 | 调用方式 | 说明 |
|--------|----------|------|
| update-config | `/update-config` | 修改 settings.json（权限、环境变量、hooks） |
| keybindings-help | `/keybindings-help` | 自定义键盘快捷键 |
| simplify | `/simplify` | 审查已修改代码，优化质量与复用 |
| less-permission-prompts | `/less-permission-prompts` | 自动生成 Bash/MCP 工具白名单，减少权限弹窗 |
| loop | `/loop` | 定时循环执行任务（如每5分钟轮询） |
| claude-api | `/claude-api` | 构建/调试 Claude API 和 Anthropic SDK 应用 |
| init | `/init` | 初始化 CLAUDE.md 文件 |
| review | `/review` | Review Pull Request |
| security-review | `/security-review` | 安全审查当前分支变更 |

> 来源：Claude Code 内置，无需安装。

## 本地技能（~/.claude/skills/）

| 技能名 | 调用方式 | 说明 | 加载路径 |
|--------|----------|------|----------|
| pdf | `/pdf` | PDF 读取、合并、拆分、加水印、OCR、加密等 | `~/.claude/skills/pdf/` |
| docx | `/docx` | Word 文档创建、编辑、格式化、提取内容 | `~/.claude/skills/docx/` |
| xlsx | `/xlsx` | Excel 电子表格读写、公式、图表、数据清洗 | `~/.claude/skills/xlsx/` |
| pptx | `/pptx` | PowerPoint 演示文稿创建、编辑、提取 | `~/.claude/skills/pptx/` |

## 项目级技能（仅在对应项目目录下生效）

### Playwright 项目（~/Playwright/.claude/skills/）

| 技能名                 | 说明                                                     | 加载路径                                               |
| ------------------- | ------------------------------------------------------ | -------------------------------------------------- |
| playwright-cli      | 浏览器自动化，用 Playwright 操控 Edge 浏览器进行网页交互和测试               | `~/Playwright/.claude/skills/playwright-cli/`      |
| bestseller-analysis | 查询 Amazon Best Seller 排名，在榜单中查找 ASIN 的大类/子类排名并记录到 Wiki | `~/Playwright/.claude/skills/bestseller-analysis/` |
| keyword-analysis    | 从西柚找词提取指定 ASIN 的关键词排位数据（广告位、自然位、AC 状态），生成明细表格          | `~/Playwright/.claude/skills/keyword-analysis/`    |

> 这些 Skill 仅在 `C:/Users/yangs/Playwright/` 目录下启动 Claude Code 时才会加载。

### Obsidian 目录（~/Obsidian/.claude/skills/）

| 技能名 | 说明 | 加载路径 |
|--------|------|----------|
| json-canvas | 创建/编辑 JSON Canvas 文件（.canvas），支持节点、边、分组 | `~/Obsidian/.claude/skills/json-canvas/` |
| obsidian-cli | 通过 CLI 与 Obsidian 交互：读写笔记、搜索、管理插件 | `~/Obsidian/.claude/skills/obsidian-cli/` |

> defuddle、obsidian-markdown、obsidian-bases 已移除（与 claude-obsidian 插件重复），由插件统一提供。

> 这些 Skill 在 `C:/Users/yangs/Obsidian/` 及其子目录（如 MyVault1）下启动 Claude Code 时加载。

### MyVault1 项目（~/Obsidian/MyVault1/.claude/skills/）

| 技能名 | 说明 | 加载路径 |
|--------|------|----------|
| amazon-research | Amazon 品类调研：分析市场前景、竞争格局、利润空间，生成 10 阶段系统性调研报告 | `~/Obsidian/MyVault1/.claude/skills/amazon-research/` |

> 仅在 `C:/Users/yangs/Obsidian/MyVault1/` 目录下启动 Claude Code 时加载。

## 已安装插件（enabledPlugins）

### 1. claude-hud

> 来源：[jarrodwatts/claude-hud](https://github.com/jarrodwatts/claude-hud)
> 缓存路径：`~/.claude/plugins/cache/claude-hud/claude-hud/0.0.12/`

| 技能名 | 调用方式 | 说明 |
|--------|----------|------|
| setup | `/claude-hud:setup` | 配置状态栏 |
| configure | `/claude-hud:configure` | 调整状态栏布局、语言、预设等显示选项 |

### 2. claude-obsidian

> 来源：[AgriciDaniel/claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian)
> 缓存路径：`~/.claude/plugins/cache/claude-obsidian-marketplace/claude-obsidian/1.4.3/`

| 技能名 | 调用方式 | 说明 |
|--------|----------|------|
| wiki | `/claude-obsidian:wiki` | Wiki vault 初始化、脚手架、跨项目引用 |
| save | `/claude-obsidian:save` | 将对话/洞见保存为结构化 wiki 笔记 |
| autoresearch | `/claude-obsidian:autoresearch` | 自主研究循环：搜索→综合→归档到 wiki |
| canvas | `/claude-obsidian:canvas` | Obsidian 可视化画布（图片、文本、PDF、wiki 页面） |
| wiki-ingest | `/claude-obsidian:wiki-ingest` | 将来源（文件/URL）批量摄入 wiki vault |
| wiki-lint | `/claude-obsidian:wiki-lint` | Wiki 健康检查：孤立页、死链接、缺失交叉引用 |
| wiki-query | `/claude-obsidian:wiki-query` | 基于 wiki vault 回答问题，带引用 |
| defuddle | `/claude-obsidian:defuddle` | 清理网页内容（去广告/导航），生成干净 Markdown |
| obsidian-markdown | `/claude-obsidian:obsidian-markdown` | 正确编写 Obsidian 风格 Markdown |
| obsidian-bases | `/claude-obsidian:obsidian-bases` | 创建/编辑 Obsidian Bases 数据库视图 |

### 3. skill-creator

> 来源：[anthropics/claude-plugins-official](https://github.com/anthropics/claude-code-plugins) — `skill-creator` 插件
> 缓存路径：`~/.claude/plugins/cache/claude-plugins-official/skill-creator/unknown/`

| 技能名 | 调用方式 | 说明 |
|--------|----------|------|
| skill-creator | `/skill-creator:skill-creator` | 创建、修改、优化、评测 Skills |

### 4. web-access

> 来源：[eze-is/web-access](https://github.com/eze-is/web-access)
> 缓存路径：`~/.claude/plugins/cache/web-access/web-access/2.4.2/`

| 技能名 | 调用方式 | 说明 |
|--------|----------|------|
| web-access | 通过 MCP 工具调用 | 联网操作：搜索、网页抓取、浏览器自动化、社交媒体内容抓取 |

## 已注册但未启用的 Marketplace

| Marketplace | 来源 | 包含技能数 |
|-------------|------|-----------|
| anthropic-agent-skills | [anthropics/skills](https://github.com/anthropics/skills) | ~17 个（algorithmic-art, brand-guidelines, frontend-design, mcp-builder 等） |
| obsidian-skills | [kepano/obsidian-skills](https://github.com/kepano/obsidian-skills) | 5 个（defuddle, json-canvas, obsidian-bases, obsidian-cli, obsidian-markdown） |

---

*最后更新：2026-04-17 — 新建技能清单后每次创建新 Skill 时更新此文档。*
