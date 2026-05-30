# 03. Hermes 执行层

## 角色定位

Hermes 是系统的底层执行引擎。

它不是一个“专家人格系统”，而是一个：
- 可调度模型
- 可调度工具
- 可调度技能
- 可接入外部数据
- 可执行学习流程
- 可返回结构化结果

的执行 runtime。

## Hermes 的输入

Town 向 Hermes 提交的不是“聊天消息”本身，而应该是结构化任务。

典型输入可以包括：
- task_id
- expert_id
- execution_profile
- user_goal
- task_type
- context_bundle
- constraints
- expected_output_schema

## Hermes 的输出

Hermes 返回的应是结构化执行结果，例如：

```json
{
  "status": "success",
  "summary": "Root cause identified",
  "artifacts": [],
  "sources": [],
  "confidence": 0.82,
  "next_actions": []
}
```

这样 Town 才能继续对结果做人格化包装与多端呈现。

## Execution Profile

每个专家应映射到一个 Hermes execution profile。

这个 profile 可以决定：
- 模型优先级
- 工具权限
- 技能白名单
- token / 预算限制
- 是否允许联网
- 是否允许写入知识库

## 为什么必须保留 Hermes 中心性

如果把这些执行逻辑挪到 Town：
- 系统边界会混乱
- 专家 persona 会和工具策略耦合
- 后续很难扩展更多专家
- 很难形成统一安全控制

所以应该坚持：

> **Hermes 是唯一执行内核，Town 只是组织者。**
