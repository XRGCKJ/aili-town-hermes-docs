# 01. Architecture

## Core principle

The central architectural rule is simple:

> **Town decides context, identity, orchestration, and user experience. Hermes executes.**

This prevents duplication of runtime responsibilities and keeps the implementation aligned with the final corrected design.

## Layered architecture

```text
User Interfaces
├─ CLI
├─ Feishu
└─ Web

Town Layer
├─ Personas
├─ World state
├─ Broadcasts
├─ Social relationships
├─ Task orchestration
├─ Learning triggers
└─ Narrative output

Hermes Execution Layer
├─ Agent runtime
├─ Tool usage
├─ Skills
├─ Model policy
├─ Safety / approval hooks
├─ Learning execution
└─ External integrations

External Capability Layer
├─ LLMs
├─ APIs
├─ GitHub
├─ Web pages
├─ Documents
└─ Storage systems
```

## Responsibility split

### Town layer responsibilities
- define expert identity
- maintain current location, role, and narrative position
- route tasks to appropriate experts
- decide when collaboration is needed
- generate real-world broadcast events
- choose when learning should be triggered
- maintain user-facing memory digests and experience framing

### Hermes layer responsibilities
- execute the task for a selected expert
- use tools and skills
- apply model strategy from the execution profile
- perform learning runs against external sources
- return structured execution results
- respect safety, tool, and platform policies

## State separation

### Town state
Town state includes:
- persona data
- task board
- locations
- narrative entries
- social graph
- broadcast history
- user-facing memory digest

### Hermes state
Hermes state includes:
- execution profile
- allowed tools
- allowed skills
- current execution context
- tool results
- artifacts
- execution logs

## Why this separation matters

Without separation, the system tends to drift into one of two failure modes:

1. **Town re-implements an agent runtime**, making Hermes redundant.
2. **Hermes carries too much product experience logic**, making the persona system weak.

The final system avoids both by keeping Town and Hermes cleanly separated.
