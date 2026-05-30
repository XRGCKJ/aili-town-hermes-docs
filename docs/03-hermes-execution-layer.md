# 03. Hermes Execution Layer

## Purpose

Hermes is the execution kernel of the system.

It is responsible for:
- turning task envelopes into real execution
- applying expert-specific execution profiles
- deciding which tools, skills, and models to use
- returning structured results to Town

## Key rule

Town should not replace Hermes with a custom runtime.

Town can prepare context and persona framing, but Hermes must remain responsible for actual execution logic.

## Main responsibilities

Hermes handles:
- task execution
- tool calls
- skill invocation
- model strategy
- fallback handling
- safety policy enforcement
- external integrations
- learning execution

## Standard input

A minimal task envelope can look like this:

```python
class HermesTaskEnvelope(BaseModel):
    expert_id: str
    execution_profile: str
    task_type: str
    task_goal: str
    memory_digest: str
    context_refs: list[str] = []
    location_context: str = ""
    relationship_context: str = ""
```

## Standard output

A minimal structured result can look like this:

```python
class HermesExecutionResult(BaseModel):
    success: bool
    expert_id: str
    result_type: str
    summary: str
    content: str
    citations: list[str] = []
    artifacts: list[str] = []
    knowledge_updates: list[str] = []
    memory_writes: list[str] = []
    skill_updates: dict[str, float] = {}
    metadata: dict = {}
```

## Execution profile example

```yaml
name: torvalds
primary_model: qwen3-coder-next
fallback_model: qwen3.6-plus
allowed_tools:
  - repo_reader
  - file_search
  - code_runner
allowed_skills:
  - code_review
  - debug_trace
  - patch_explanation
knowledge_policy: baseline_plus_repo_plus_docs
execution_mode: direct
security_policy: code_safe_mode
```

## Execution modes

### Direct
One expert directly handles the task.

### Delegated
The selected expert triggers internal sub-actions, tools, or delegated execution.

### Collaborative
Town coordinates multiple experts, each backed by Hermes execution.

For Phase 1, **Direct** mode is enough.

## Why model policy belongs here

Model choice is part of execution behavior, not part of town narrative.

That means:
- Town chooses the expert
- Hermes profile chooses the model strategy

This keeps architecture clean and extensible.
