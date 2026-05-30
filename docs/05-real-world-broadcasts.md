# 05. Real-World Broadcasts

## Purpose

Broadcasts make the town responsive to the outside world.

A broadcast is a structured town event generated from real-world data such as:
- GitHub releases
- market movements
- research publications
- news items
- weather or time-related context

## Why broadcasts matter

Without broadcasts, the town becomes a static routing shell.

With broadcasts, the town can:
- react to real changes
- trigger expert learning
- create shared context
- generate ambient intelligence for users

## Broadcast pipeline

```text
External source
→ fetch
→ filter
→ score importance
→ summarize
→ create town broadcast event
→ deliver to relevant experts
→ trigger optional learning or follow-up actions
```

## Broadcast event example

```python
class TownBroadcastEvent(BaseModel):
    event_id: str
    source_type: str
    title: str
    content: str
    source_ref: str
    reliability: float
    importance_score: float
    tags: list[str]
    created_at: str
```

## Design rules

1. Do not dump raw external data directly into the town.
2. Every broadcast should have source attribution.
3. Broadcasts should be filtered for relevance and importance.
4. Not every expert needs to respond to every broadcast.
5. High-importance broadcasts can trigger learning.

## Example use case

A major GitHub library release is detected:
- a broadcast is generated
- Torvalds receives it because it is code-related
- Intel may receive it for summary extraction
- Town may schedule a learning action
