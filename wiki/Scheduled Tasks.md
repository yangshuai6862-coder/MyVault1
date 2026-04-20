---
title: Scheduled Tasks
type: reference
created: 2026-04-17
updated: 2026-04-17
tags: [scheduled-tasks, cron, reference]
---

# Scheduled Tasks

本文档记录所有 Claude Code 定时任务（活跃 + 历史）。

> [!info] 规则
> 每次新增/删除/修改定时任务时，必须同步更新本文件。

---

## 活跃任务

---

### 1. 关键词排名每日更新

| 属性 | 详情 |
|------|------|
| **任务ID** | `80c44369` |
| **Cron 表达式** | `3 12 * * *` |
| **执行频率** | 每天中午 12:03（本地时间） |
| **创建时间** | 2026-04-17 |
| **类型** | 循环任务（recurring，durable） |
| **预计过期** | 创建后 7 天自动过期 |

#### 任务描述

执行每日关键词排名更新任务，从西柚找词提取指定 ASIN 的关键词排位数据（广告位、自然位、AC 状态），生成每小时明细表格并保存到 Wiki。

#### 输出

- 更新 `wiki/market/metapen/B09ZTXVNVD Keywords position.md`

---

### 2. Amazon Best Seller 排名更新

| 属性 | 详情 |
|------|------|
| **任务ID** | `4e157edf` |
| **Cron 表达式** | `17 */2 * * *` |
| **执行频率** | 每 2 小时（00:17, 02:17, 04:17, ...） |
| **创建时间** | 2026-04-17 |
| **类型** | 循环任务（recurring，durable） |
| **预计过期** | 创建后 7 天自动过期（约 2026-04-24） |

#### 任务描述

定时查询 Amazon Best Seller 排名，使用 playwright-cli 打开 Edge 浏览器抓取排名数据：

- **追踪产品**：Apple Pencil Pro, Apple Pencil (USB-C), Metapen A8, JAMJAKE, Hastraith
- **大类**：Cell Phones & Accessories（Top 100）
- **子类**：Stylus Pens（Top 80）

更新完成后自动 `git commit & push` 同步到 GitHub。

#### 输出

- 更新 `wiki/market/metapen/Bestseller.md`（追加新行，不覆盖历史）
- 推送到 GitHub 远程仓库 `yangshuai6862-coder/MyVault1`

---

### 3. AI 每日技术情报

| 属性 | 详情 |
|------|------|
| **任务ID** | `d0074b9d` |
| **Cron 表达式** | `3 9 * * *` |
| **执行频率** | 每天早上 9:03（本地时间） |
| **创建时间** | 2026-04-17 |
| **类型** | 循环任务（recurring，durable） |
| **预计过期** | 创建后 7 天自动过期（约 2026-04-24） |

#### 任务描述

自动执行 AI 技术情报搜集，涵盖以下范围：

- **国际大厂与前沿模型**：OpenAI、Google、Meta、NVIDIA、Mistral、Anthropic 等官方动态
- **开源生态与论文**：GitHub 开源项目更新、arXiv 预印本、顶会论文
- **中国 AI 动态**：Qwen、DeepSeek、智谱、百度、字节等大模型发布
- **垂直领域与工具链**：AI Agent、机器人、安全对齐、多模态、硬件芯片

更新完成后自动 `git commit & push` 同步到 GitHub。

#### 输出

- 生成日报文件：`wiki/ai-updates/YYYY-MM-DD AI日报.md`
- 更新 `wiki/log.md` 日志
- 更新 `wiki/ai-updates/_index.md` 索引
- 推送到 GitHub 远程仓库 `yangshuai6862-coder/MyVault1`

---

## 历史任务（已过期）

---

### AI 每日技术情报（旧）

| 属性 | 详情 |
|------|------|
| **任务ID** | `7c294ad6` |
| **Cron 表达式** | `3 9 * * *` |
| **执行频率** | 每天早上 9:03（本地时间） |
| **开始时间** | 2026-04-14 |
| **最近执行** | 2026-04-17 10:13:06 |
| **状态** | 已过期 |
| **替代任务** | `d0074b9d`（已重新创建） |
