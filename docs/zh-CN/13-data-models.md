# 13. 数据模型设计

## 目标

为了让 Town × Hermes 可扩展、可治理、可追踪，需要为关键对象建立统一数据模型。

核心对象包括：
- Expert
- Task
- BroadcastEvent
- MemoryEntry
- KnowledgeEntry
- ExecutionRecord

## 1. Expert

### 示例结构

```json
{
  "id": "expert.intel",
  "name": "Intel",
  "role": "Research Strategist",
  "domain_tags": ["research", "analysis", "strategy"],
  "persona_summary": "擅长结构化分析与多来源综合判断",
  "execution_profile": "deep_research",
  "visibility": "public",
  "status": "active"
}
```

### 关键字段
- `id`
- `name`
- `role`
- `domain_tags`
- `persona_summary`
- `execution_profile`
- `visibility`
- `status`

## 2. Task

### 示例结构

```json
{
  "id": "task_001",
  "title": "分析项目启动失败原因",
  "status": "executing",
  "priority": "medium",
  "created_by": "user",
  "assigned_experts": ["expert.intel"],
  "input": "为什么这个 Python 项目启动失败？",
  "context_refs": ["memory_12", "broadcast_03"],
  "created_at": "2026-05-30T00:00:00Z"
}
```

### 关键字段
- `id`
- `title`
- `status`
- `priority`
- `created_by`
- `assigned_experts`
- `input`
- `context_refs`
- `created_at`
- `updated_at`

## 3. BroadcastEvent

### 示例结构

```json
{
  "id": "broadcast_03",
  "source": "github_release",
  "topic": "framework update",
  "summary": "某框架发布重大版本",
  "relevance_score": 0.91,
  "target_experts": ["expert.builder", "expert.intel"],
  "created_at": "2026-05-30T00:00:00Z"
}
```

## 4. MemoryEntry

### 示例结构

```json
{
  "id": "memory_12",
  "scope": "expert",
  "owner_id": "expert.intel",
  "summary": "用户长期关注 AI agent 架构与系统治理",
  "tags": ["user_goal", "architecture"],
  "updated_at": "2026-05-30T00:00:00Z"
}
```

## 5. KnowledgeEntry

### 示例结构

```json
{
  "id": "knowledge_07",
  "type": "shared",
  "title": "Town 应统一管理任务状态机",
  "summary": "任务状态机应由 Town 维护，避免执行层与产品层耦合",
  "source_refs": ["task_001"],
  "quality_score": 0.88,
  "created_at": "2026-05-30T00:00:00Z"
}
```

## 6. ExecutionRecord

### 示例结构

```json
{
  "id": "exec_88",
  "task_id": "task_001",
  "executor": "Hermes",
  "model": "gpt-5-class",
  "tools_used": ["code_search", "web_search"],
  "status": "success",
  "latency_ms": 4200,
  "cost_estimate": 0.18,
  "created_at": "2026-05-30T00:00:00Z"
}
```

## 原则

数据模型应满足：
- 可序列化
- 可审计
- 可扩展
- 可回溯对象关系
