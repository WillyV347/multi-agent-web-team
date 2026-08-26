# Architecture (Showcase)

This document explains the **shape** of the system. It is deliberately high-level.

## Layers

1. **Agents** (`agents/*.md`) — role prompts. Who decides, who implements, who reviews.
2. **Skills** (`skills/*/SKILL.md`) — reusable procedures an agent runs (e.g. draft a PRD).
3. **Commands** (`commands/*.md`) — user-facing entry points that orchestrate agents across phases.
4. **Gates** — human checkpoints. The demo pauses for approval; it does not auto-ship.

## Demo flow (`/demo-kickoff`)

```
Input: fictional business name + one-line context
        │
        ▼
 Phase A — Research brief     (product-manager + seo-specialist)
        │
        ▼  Gate 1: approve scope / success metric
        │
 Phase B — Design notes       (ui-designer)
        │
        ▼  Gate 2: approve visual direction
        │
 Phase C — Build checklist    (frontend + backend + a11y)
        │
        ▼  Gate 3: approve “ready to build” checklist
        │
 Done — summary artifact in the chat / a markdown file the user asked for
```

## What production systems add (not in this repo)

A production engagement system typically adds: deeper orchestration, design interrogation before mockups, persistent engagement memory, cross-project lessons, industry research caches, and studio-specific deliverable formats. Those stay private so client work and operational IP are not published as a cloneable toolkit.

## Extending the demo

- Add another agent under `agents/` with a clear ownership boundary.
- Add a skill under `skills/<name>/SKILL.md` and reference it from the agent.
- Keep commands thin: they should route and gate, not encode every specialist procedure.
