# 12. 模块拆解文档

## 模块总览

Town × Hermes 可以拆成以下核心模块：

1. Interaction Layer
2. Town Orchestrator
3. Expert Registry
4. Task System
5. Hermes Runtime
6. Broadcast System
7. Memory System
8. Knowledge System
9. Governance Layer
10. Observability / Ops

每个模块都应保持边界清晰，避免相互污染。

## 1. Interaction Layer

负责接收用户输入与输出结果。

### 子模块
- CLI Adapter
- Feishu Adapter
- Web Adapter
- Output Formatter

### 职责
- 接入请求
- 标准化用户输入
- 展示结果
- 呈现任务状态

## 2. Town Orchestrator

这是 Town 的中枢。

### 职责
- 意图识别
- 专家路由
- 上下文组装
- 广播分发
- 学习触发决策
- 任务生命周期协调

## 3. Expert Registry

用于管理系统中的专家定义。

### 职责
- 专家元数据管理
- persona 描述
- execution profile 映射
- 领域标签管理
- 可见性与启用状态管理

## 4. Task System

用于承载所有任务。

### 职责
- 任务创建
- 状态流转
- 优先级管理
- 指派记录
- 任务归档

## 5. Hermes Runtime

系统唯一执行内核。

### 职责
- 接收结构化任务
- 调度模型 / 工具 / 技能
- 返回结构化结果
- 记录执行元信息

## 6. Broadcast System

负责把现实世界变化转成系统内事件。

### 职责
- 外部数据采集
- relevance filtering
- 生成 broadcast event
- 推送到 Town / Expert

## 7. Memory System

负责摘要化记忆。

### 职责
- 会话记忆
- 专家摘要记忆
- Town 共享记忆
- 检索与更新

## 8. Knowledge System

负责长期知识沉淀。

### 职责
- 知识候选提取
- 质量评估
- 去重归类
- 入库与回滚

## 9. Governance Layer

负责控制风险。

### 职责
- 工具权限控制
- 学习写入控制
- 预算控制
- 审计能力

## 10. Observability / Ops

负责系统运行可观测性。

### 职责
- 任务监控
- 失败告警
- 性能指标
- 成本指标
- 日志聚合

## 模块关系原则

- Interaction 不直接执行工具
- Town 不直接替代 Hermes
- Hermes 不直接决定产品表达
- Knowledge 不应绕过治理直接写入
- Broadcast 不应直接污染记忆
