# 02. Expert System

## Expert design rule

Every expert is modeled as:

```text
Town Persona + Hermes Execution Profile
```

This means the expert has both:
- a social identity inside the town
- an execution capability definition inside Hermes

## Expert tiers

### Tier A: Core experts
These are persistent, high-value experts.

Characteristics:
- always available in the town model
- have stronger persona consistency
- can react to broadcasts
- can trigger or receive collaboration
- can maintain richer memory summaries

Suggested initial examples:
- Torvalds: code architecture and debugging
- Intel: research and extraction
- Buffett: long-term investment reasoning

### Tier B: On-demand experts
These are activated only when needed.

Characteristics:
- not always active in the world loop
- have defined persona and execution profile
- limited memory footprint
- good for domain specialists

### Tier C: Background roles
These are light narrative roles.

Characteristics:
- mostly for atmosphere and interaction framing
- no need for full execution loop
- can be implemented with lightweight response rules

## Persona fields

Typical Town persona fields include:
- `expert_id`
- `name`
- `title`
- `tier`
- `domain_tags`
- `signature_style`
- `core_values`
- `known_for`
- `current_location`
- `relationship_tags`

## Execution profile fields

Typical Hermes execution profile fields include:
- `primary_model`
- `fallback_model`
- `allowed_tools`
- `allowed_skills`
- `knowledge_policy`
- `execution_mode`
- `security_policy`

## Example mental model

If a user asks for project debugging help:
- Town selects **Torvalds** because the persona and role match the request.
- Hermes executes using Torvalds' execution profile.
- Town later presents the result in Torvalds' voice and world context.

This is the core identity/execution split.
