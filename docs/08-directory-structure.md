# 08. Directory Structure

## Goal

The repository and implementation structure should reflect the separation between:
- Town orchestration
- Hermes execution
- knowledge assets
- real-world broadcast ingestion
- user interfaces

## Suggested structure

```text
app/
├─ main.py
├─ cli.py
└─ settings.py

town/
├─ orchestrator/
│  ├─ intent_router.py
│  ├─ town_orchestrator.py
│  └─ task_board.py
├─ experts/
│  ├─ personas.py
│  ├─ registry.py
│  └─ memory_digest.py
├─ models/
│  ├─ task.py
│  ├─ result.py
│  └─ events.py
└─ narrative/
   └─ formatter.py

hermes_core/
├─ execution/
│  ├─ executor.py
│  ├─ task_envelope.py
│  ├─ result_model.py
│  ├─ result_adapter.py
│  └─ profile_loader.py
└─ profiles/
   ├─ torvalds.yaml
   ├─ intel.yaml
   └─ buffett.yaml

knowledge/
├─ baseline/
├─ personal_kb/
├─ shared_kb/
├─ ingestion/
└─ updater/

reality/
├─ sources/
├─ filters/
└─ broadcaster.py

tests/
```

## Why this structure works

- `town/` contains orchestration and identity logic
- `hermes_core/` contains execution logic and profiles
- `knowledge/` contains expert knowledge assets and pipelines
- `reality/` contains external data ingestion and broadcast logic
- `app/` contains entry points

This makes responsibilities obvious even as the codebase grows.
