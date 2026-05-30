# Aili Town × Hermes Docs

Documentation repository for **Aili Town × Hermes**, a text-based expert-town system where:

- **Aili Town** is the upper orchestration and experience layer.
- **Hermes Agent** is the core execution kernel.
- Experts are modeled as **Town Persona + Hermes Execution Profile**.

This repository stores architecture documents, implementation notes, example profiles, and Phase 1 code skeleton guidance.

## System summary

```text
User Interfaces
├─ CLI
├─ Feishu
└─ Web

Town Layer
├─ Expert personas
├─ World / places / broadcasts / narrative
├─ Task orchestration
├─ Learning triggers
└─ User-facing experience

Hermes Execution Layer
├─ Agent runtime
├─ Tools / Skills / Hooks / Policies
├─ Model strategy
├─ Task execution
└─ Learning execution

External capabilities
├─ Models
├─ APIs / Web / GitHub / Docs
└─ Storage / Platforms
```

## Responsibility split

### Town is responsible for
- expert identity and persona
- locations, scenes, and narrative framing
- real-world broadcast generation
- task routing and orchestration
- long-term relationship and memory summaries
- user experience across CLI / Feishu / Web

### Hermes is responsible for
- actual execution of expert tasks
- tool use and skill execution
- model policy and fallback policy
- learning execution against external sources
- execution-time integrations and safety policies

## Suggested reading order

1. [docs/00-overview.md](docs/00-overview.md)
2. [docs/01-architecture.md](docs/01-architecture.md)
3. [docs/02-expert-system.md](docs/02-expert-system.md)
4. [docs/03-hermes-execution-layer.md](docs/03-hermes-execution-layer.md)
5. [docs/04-town-orchestration-layer.md](docs/04-town-orchestration-layer.md)
6. [docs/05-real-world-broadcasts.md](docs/05-real-world-broadcasts.md)
7. [docs/06-knowledge-learning-loop.md](docs/06-knowledge-learning-loop.md)
8. [docs/07-user-interaction-layer.md](docs/07-user-interaction-layer.md)
9. [docs/08-directory-structure.md](docs/08-directory-structure.md)
10. [docs/09-phase1-code-skeleton.md](docs/09-phase1-code-skeleton.md)
11. [docs/10-next-steps.md](docs/10-next-steps.md)

## Repository scope

This repository is intentionally focused on:
- architecture and implementation documentation
- example execution profiles
- baseline knowledge templates
- Phase 1 project skeleton guidance

It does **not** claim that a full implementation already exists.
