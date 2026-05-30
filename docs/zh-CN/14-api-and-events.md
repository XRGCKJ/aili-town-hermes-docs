# 14. API 与事件设计

## 目标

Town × Hermes 不应只靠 prompt 拼接运行，而应逐步演进为明确的 API 与事件驱动系统。

## API 设计原则

- 输入输出结构化
- 避免 UI 与执行层直接耦合
- 支持同步请求与异步任务
- 支持事件订阅与状态回调

## 核心 API

### 1. 创建任务

```http
POST /api/tasks
```

请求体示例：

```json
{
  "input": "为什么这个 Python 项目启动失败？",
  "preferred_expert": "expert.intel",
  "channel": "cli"
}
```

### 2. 获取任务详情

```http
GET /api/tasks/{task_id}
```

### 3. 获取专家列表

```http
GET /api/experts
```

### 4. 获取广播流

```http
GET /api/broadcasts
```

### 5. 查询知识库

```http
GET /api/knowledge?query=task+state
```

## 事件模型

系统内部建议采用统一事件结构。

### 示例

```json
{
  "event_type": "task.updated",
  "entity_id": "task_001",
  "payload": {
    "old_status": "routed",
    "new_status": "executing"
  },
  "created_at": "2026-05-30T00:00:00Z"
}
```

## 常见事件类型

- `task.created`
- `task.updated`
- `task.failed`
- `broadcast.created`
- `knowledge.created`
- `memory.updated`
- `execution.completed`

## 为什么事件重要

事件机制可以支持：
- UI 自动刷新
- 任务通知
- 学习触发
- 审计追踪
- 模块解耦

## Webhook / Callback 扩展

未来可支持：
- 飞书通知回调
- Web 前端订阅
- 第三方系统接入

## 原则

先定义清晰事件，再做复杂自动化。
