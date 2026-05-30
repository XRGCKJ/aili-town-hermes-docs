# 04. Town Orchestration Layer

## Purpose

The Town layer is the experience and orchestration layer built above Hermes.

It is responsible for:
- persona framing
- expert routing
- world state
- public broadcasts
- narrative packaging
- user-facing memory summaries

## Core functions

### 1. Intent parsing
Interpret a user request and classify its broad task type.

Examples:
- code debugging
- documentation research
- investment reasoning
- general explanation

### 2. Expert routing
Choose the most appropriate expert based on:
- task type
- requested expert
- persona fit
- current world context

### 3. Context assembly
Prepare a Hermes task envelope that includes:
- expert identity
- memory digest
- location context
- relationship context
- context refs

### 4. Result adaptation
Take Hermes results and translate them into:
- user-friendly output
- narrative-style responses
- memory updates
- future task context

## Example orchestration flow

```text
User request
→ Town intent parser
→ expert selection
→ memory digest assembly
→ Hermes task envelope
→ Hermes execution
→ Town result adaptation
→ response to user
```

## Town should not do these things

Town should not:
- own a full tool-use runtime
- centrally micromanage every model selection
- replace Hermes safety logic
- duplicate execution-layer code paths

## Phase 1 minimal Town modules

A practical starting set:
- `intent_router.py`
- `town_orchestrator.py`
- `task_board.py`
- `registry.py`
- `memory_digest.py`

This is enough to get the first expert flows working.
