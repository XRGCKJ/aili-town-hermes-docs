# 00. Overview

## Purpose

This repository documents the finalized architecture for **Aili Town × Hermes**, a system that combines:

- a **persona-driven, text-based expert town** as the orchestration and experience layer
- **Hermes Agent** as the execution kernel

The goal is to help a team move from concept to implementation without confusing responsibilities between the Town layer and the Hermes layer.

## What this system is

Aili Town × Hermes is:
- a multi-expert system
- a town-style orchestration layer with personas, narrative, and world state
- a Hermes-backed execution architecture for tasks, tools, learning, and integrations
- a foundation for CLI, Feishu, and Web experiences

## What this system is not

It is not:
- a pure roleplay world with no real execution ability
- a Town-owned replacement for Hermes runtime
- a single-agent chatbot with cosmetic personas only
- a fully implemented product inside this repo

## Final architectural stance

The final corrected architecture is:

- **Town sits above Hermes**
- **Hermes remains the execution kernel**
- **Experts are represented as Town Persona + Hermes Execution Profile**
- **Broadcast events are grounded in real-world data**
- **Learning is triggered by Town and executed by Hermes**

## High-level execution loop

```text
User Request
→ Interface Adapter (CLI / Feishu / Web)
→ Town Intent Parsing
→ Town Routing / Orchestration
→ Expert Selection
→ Hermes Task Envelope
→ Hermes Execution
→ Result Adaptation
→ Town Narrative / Memory / UX Output
```

## Reading guidance

If you are new to the project, read in this order:
1. Overview
2. Architecture
3. Expert System
4. Hermes Execution Layer
5. Town Orchestration Layer
6. Real-World Broadcasts
7. Knowledge Learning Loop
8. User Interaction Layer
9. Directory Structure
10. Phase 1 Code Skeleton
11. Next Steps
