# 15. MVP 实施计划

## 目标

MVP 的目标不是一次性做完所有设想，而是尽快验证 Town × Hermes 的核心闭环是否成立。

这个闭环是：

用户输入 → Town 路由 → Hermes 执行 → 结果返回 → 任务可追踪

## MVP 范围

第一阶段建议只包含以下能力：

- CLI 输入
- 基础 Expert Registry
- Town 路由决策
- Hermes 执行封装
- Task 状态管理
- 基本输出格式化
- 简单日志记录

## 不纳入 MVP 的部分

以下能力建议延后：

- 飞书接入
- Web UI
- 自动知识入库
- 复杂广播系统
- 多模型复杂调度
- 精细化治理面板

## 推荐开发顺序

### Step 1：定义核心数据结构
先定义：
- Expert
- Task
- ExecutionResult
- TaskStatus

### Step 2：实现 Expert Registry
支持：
- 注册专家
- 查询专家
- 根据标签筛选专家

### Step 3：实现 Town Router
支持：
- 根据输入判定任务类型
- 选择默认专家
- 组装执行上下文

### Step 4：实现 Hermes Runtime Wrapper
支持：
- 接收结构化任务
- 调用模型或工具
- 返回结构化结果

### Step 5：实现 Task Manager
支持：
- 创建任务
- 更新状态
- 查询任务
- 记录失败

### Step 6：接通 CLI
示例命令：
- `town ask "总结这个仓库"`
- `town ask --expert intel "分析这个错误"`
- `town task list`

### Step 7：加入最小日志与观测
至少记录：
- 任务开始时间
- 执行结果
- 失败原因
- 耗时

## MVP 验收标准

一个合格 MVP 至少应做到：
- 能稳定接收输入并完成响应
- 能按专家配置路由
- 能看到任务状态变化
- 能记录最基本执行信息

## 实施建议

MVP 期间最重要的是“先让链路跑通”，而不是提前优化复杂能力。
