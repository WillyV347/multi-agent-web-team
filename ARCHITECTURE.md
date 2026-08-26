# Architecture

This document explains the **shape** of the system.

## Layers

1. **Agents** (`agents/*.md`) — role prompts. Who decides, who implements, who reviews.
2. **Skills** (`skills/*/SKILL.md`) — reusable procedures an agent runs (e.g. draft a PRD, run demo kickoff).
3. **Commands** (`commands/*.md`) — Cursor / Claude Code slash entry points that orchestrate agents across phases.
4. **Host memory** — identical `AGENTS.md` (Cursor/Codex) and `CLAUDE.md` (Claude Code) so a fresh session starts in the team frame.
5. **Gates** — human checkpoints. The demo pauses for approval; it does not auto-ship.

## Host packaging

| Host | Manifest / discovery |
|---|---|
| Cursor | `.cursor-plugin/plugin.json` → root `agents/`, `skills/`, `commands/` |
| Claude Code | `.claude-plugin/plugin.json` + `marketplace.json` → same root layout |
| Codex | `.codex-plugin/plugin.json` (`skills: ./skills/`); repo marketplace `.agents/plugins/marketplace.json`; repo-local skills via `.agents/skills/*` (keep in sync with `skills/*`) |

## Demo flow (`demo-kickoff`)

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

Entry points: **`/demo-kickoff`** (Cursor/Claude) or the **`demo-kickoff` skill** (Codex and any host).

## Extending the demo

- Add another agent under `agents/` with a clear ownership boundary.
- Add a skill under `skills/<name>/SKILL.md` and, for Codex repo discovery, copy it into `.agents/skills/<name>` (keep in sync with `skills/`).
- Keep commands thin: they should route and gate, not encode every specialist procedure.
- After structural changes, update **both** `AGENTS.md` and `CLAUDE.md` and bump versions in all three host manifests.

Possible additions if you grow the system: deeper orchestration docs, persistent project memory files, cross-project lesson libraries, or industry research profiles — none of those are required for the demo as shipped.
