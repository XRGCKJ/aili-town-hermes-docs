# 02. 专家系统

## 专家设计规则

每个专家都被建模为：

```text
Town Persona + Hermes Execution Profile
```

也就是说，一个专家同时拥有：
- 城镇中的社会身份
- Hermes 中的执行能力定义

## 专家分层

### Tier A：核心专家
这些是常驻、高价值专家。

特点：
- 始终存在于城镇模型中
- 人格一致性更强
- 可接收广播
- 可触发或参与协作
- 可维护更丰富的记忆摘要

建议初始示例：
- Torvalds：代码架构与调试
- Intel：研究与信息抽取
- Buffett：长期投资推理

### Tier B：按需专家
这些专家只在需要时激活。

特点：
- 不必常驻世界循环
- 有明确定义的人格和执行 profile
- 记忆占用较小
- 适合垂直领域专家

### Tier C：背景角色
这些是轻量叙事角色。

特点：
- 更多用于氛围和交互 framing
- 不需要完整执行循环
- 可以用轻量响应规则实现

## Persona 字段

典型 Town persona 字段包括：
- `expert_id`
- `name`
- `title`
- `tier`
- `domain_tags`
- `signature_style`
- `core_values`
- `known_for`
- `current_location`
- `relationship_tags`

## Execution Profile 字段

典型 Hermes execution profile 字段包括：
- `primary_model`
- `fallback_model`
- `allowed_tools`
- `allowed_skills`
- `knowledge_policy`
- `execution_mode`
- `security_policy`

## 示例心智模型

如果用户请求项目调试帮助：
- Town 选择 **Torvalds**，因为人格与角色匹配该任务。
- Hermes 使用 Torvalds 的执行 profile 完成实际执行。
- Town 最后用 Torvalds 的语气和世界上下文呈现结果。

这就是身份与执行分离的核心设计。
