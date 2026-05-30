# 07. User Interaction Layer

## Purpose

The system should support multiple entry points without forcing users to understand the internal architecture.

Supported entry points:
- CLI
- Feishu
- Web

## Guiding principle

Users should express goals, not routing logic.

The system should handle:
- task classification
- expert selection
- learning triggers
- result packaging

## CLI

CLI is the fastest way to test the architecture early.

Suggested commands:
- `town ask "Why does this Python project fail to start?"`
- `town ask --expert intel "Summarize this README"`
- `town experts`
- `town task list`

## Feishu

Feishu is ideal for team workflows and asynchronous usage.

Potential capabilities:
- `@town` auto-routing
- `@expert` direct requests
- task status cards
- learning notifications
- daily reports

## Web

Web is best for visibility and operations.

Potential capabilities:
- expert hall
- broadcast feed
- task board
- knowledge library
- execution trace view

## Output design

A useful user response usually has three layers:
1. direct conclusion
2. expert framing or collaboration summary
3. optional sources and details

This preserves usability while still surfacing system intelligence.
