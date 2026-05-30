# 17. 聊天会话纪要

## 会话日期

2026-05-30

## 本次目标

将 Town × Hermes 相关中文版架构文档、开发线路图、模块设计文档逐步整理并推送到仓库中。

## 已完成推送的文档

本次会话中已完成以下文件写入：

- `docs/zh-CN/08-task-board-and-state-machine.md`
- `docs/zh-CN/09-memory-and-summaries.md`
- `docs/zh-CN/10-safety-and-governance.md`
- `docs/zh-CN/11-development-roadmap.md`
- `docs/zh-CN/12-module-breakdown.md`
- `docs/zh-CN/13-data-models.md`
- `docs/zh-CN/14-api-and-events.md`
- `docs/zh-CN/15-mvp-implementation-plan.md`
- `docs/zh-CN/16-deployment-and-operations.md`

## 本次讨论形成的核心结论

### 1. Town 与 Hermes 的职责边界
- Town 负责路由、编排、任务协调、人格与产品表达。
- Hermes 负责统一执行，是系统唯一执行内核。

### 2. 任务系统是核心基础设施
- 任务需要统一状态机。
- 状态至少包括 `new`、`routed`、`executing`、`waiting`、`done`、`archived`、`failed`。
- 任务状态不只是 UI 信息，也决定提醒、接管、学习与升级逻辑。

### 3. 记忆应采用摘要化设计
- 不应长期无差别保存完整上下文。
- 应区分 Session Memory、Expert Summary Memory、Shared Town Memory。
- 目标是提高检索质量并保持长期连续感。

### 4. 系统需要治理层
- 多工具、多专家、多知识写入能力不能只靠 prompt 约束。
- 应建设权限控制、预算控制、审计日志、学习写入控制等机制。

### 5. 开发应分阶段推进
建议顺序：
1. 先跑通执行闭环
2. 再引入广播与专家协作
3. 再做学习沉淀
4. 最后增强多端交互、治理和运维

### 6. 需要明确模块边界
核心模块包括：
- Interaction Layer
- Town Orchestrator
- Expert Registry
- Task System
- Hermes Runtime
- Broadcast System
- Memory System
- Knowledge System
- Governance Layer
- Observability / Ops

### 7. 数据模型、API 与事件模型应尽早规范
- 关键对象包括 Expert、Task、BroadcastEvent、MemoryEntry、KnowledgeEntry、ExecutionRecord。
- 系统建议采用结构化 API 与统一事件模型，为后续 UI、审计、自动化打基础。

## 本次协作方式

- 用户以“继续”方式逐步确认推送。
- 文档采用编号化中文 Markdown 形式写入 `docs/zh-CN/`。
- 提交信息主要使用 `Add Chinese docs batch 4`、`Add Chinese docs roadmap batch`、`Add Chinese docs roadmap batch 2`、`Add Chinese docs roadmap batch 3`。

## 后续建议补充文档

建议下一步继续补充：
- 专家定义规范
- Prompt / Context 装配规范
- 广播订阅与过滤策略
- 知识入库规则
- 权限矩阵设计
- CLI / Web / Feishu 接入细节
- 测试与评估方案

## 结论

本次会话已完成 Town × Hermes 中文架构文档从 08 到 16 的主要补充，并形成一套较清晰的中文开发框架与模块化设计基础。
