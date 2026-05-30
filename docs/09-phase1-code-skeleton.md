# 09. Phase 1 Code Skeleton

## Goal of Phase 1

The first phase should prove one thing:

> Town can route a task to an expert backed by Hermes and receive a structured result.

## Minimum scope

Recommended minimum:
- 1 to 3 experts
- CLI entry point
- Town orchestrator
- Hermes task envelope and result model
- mock or real Hermes executor
- example execution profiles
- baseline knowledge templates

## Minimum project tree

```text
app/
town/
hermes_core/
knowledge/
tests/
```

## Practical module list

### app
- `settings.py`
- `cli.py`
- `main.py`

### town
- `intent_router.py`
- `town_orchestrator.py`
- `task_board.py`
- `registry.py`
- `memory_digest.py`

### hermes_core
- `task_envelope.py`
- `result_model.py`
- `profile_loader.py`
- `executor.py`
- `result_adapter.py`

## Example execution path

```text
CLI input
→ Town task creation
→ task type detection
→ expert routing
→ Hermes task envelope
→ Hermes executor
→ structured result
→ adapted town response
```

## Recommended strategy

Start with a mock Hermes executor to validate the flow quickly.

Then replace it with real Hermes integration once:
- profile loading works
- routing works
- result adaptation works
- CLI and API paths are stable

## Success criteria

Phase 1 is successful when:
- a user can ask a question
- Town chooses an expert
- Hermes executes with the selected profile
- a structured result is returned to the user
