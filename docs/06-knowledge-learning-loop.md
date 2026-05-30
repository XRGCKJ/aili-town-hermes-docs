# 06. Knowledge Learning Loop

## Purpose

The system must support learning that updates expert knowledge over time.

The key design rule is:

> **Town decides when learning should happen. Hermes performs the learning execution.**

## Knowledge layers

The system should distinguish between:

### Baseline knowledge
What an expert already knows by default.

### Personal KB
Longer-lived expert-specific knowledge.

### Shared KB
Knowledge useful across multiple experts.

### Working context
Short-lived task-specific context.

### Insight memory
Reflections, lessons, and reusable patterns.

## Learning triggers

Learning can be triggered by:
- a new user task
- a real-world broadcast
- scheduled refresh runs
- a failed task that requires follow-up learning

## Learning pipeline

```text
Trigger detected by Town
→ expert selection
→ Hermes learning execution
→ fetch / extract / compare / summarize
→ write KB updates
→ update skill indicators
→ write memory summary
→ expose result back to Town
```

## Example workflow

A user asks for help integrating a new open-source library:
- Town routes to Torvalds
- existing baseline knowledge is not enough
- Town triggers learning support via Hermes
- Hermes reads docs / release notes / examples
- a summary is written to personal or shared KB
- Torvalds can now answer with enriched context

## Design guidelines

- keep baseline knowledge lightweight but useful
- treat external sources as inputs to structured learning
- prefer knowledge updates over endlessly growing raw history
- separate user-facing narrative memory from execution artifacts
