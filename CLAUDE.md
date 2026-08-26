# Multi-Agent Web Team — session frame

This repo is a **multi-agent web team demo**: named roles, shared skills, and human gates. Route work through the sample agents instead of bypassing them.

## Hosts

| Host | How this repo loads |
|---|---|
| **Cursor** | Plugin via [`.cursor-plugin/plugin.json`](.cursor-plugin/plugin.json); slash command `/demo-kickoff` |
| **Claude Code** | Plugin via [`.claude-plugin/`](.claude-plugin/); marketplace entry in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json); command `/demo-kickoff` (namespaced if installed as a marketplace plugin) |
| **Codex** | Plugin via [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) + skills under `skills/`; repo marketplace [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json); also auto-loads this `AGENTS.md`. Prefer the `demo-kickoff` **skill** (Codex has no slash-command surface like Cursor/Claude). |

Keep this file and `CLAUDE.md` identical.

## Ground-truth pointers

- Role briefs: [`agents/`](agents/)
- Skills: [`skills/`](skills/) (`write-prd`, `component-scaffold`, `seo-audit`, `demo-kickoff`)
- Cursor/Claude command: [`commands/demo-kickoff.md`](commands/demo-kickoff.md)
- Architecture: [`ARCHITECTURE.md`](ARCHITECTURE.md)

## Standing disciplines

- **Gates are human** — pause at Gate 1 (scope), Gate 2 (design), Gate 3 (build checklist).
- **Demo data only** — never invent real business facts; mark gaps `UNKNOWN — needs verification`.
- **Roles over vibes** — when a phase needs a specialist, open the matching file under `agents/` and follow it.
- **Skills are procedures** — call the sample skills instead of improvising a whole workflow.
- **Stay in scope** — keep outputs short and appropriate for the demo; extend the repo if you need more depth.

## Change-routing

| The ask | Route |
|---|---|
| Run the end-to-end demo | `demo-kickoff` skill **or** `/demo-kickoff` command |
| Scope / success metric / PRD | `product-manager` → `write-prd` if needed |
| Visual direction | `ui-designer` (after Gate 1) |
| Implementation checklist | `frontend-engineer` + `component-scaffold` |
| Forms / API / data | `backend-engineer` |
| SEO baseline | `seo-specialist` → `seo-audit` if a URL exists |
| Accessibility floor | `accessibility-specialist` |

## Keep-current rule

If you add an agent, skill, or command, update **both** `AGENTS.md` and `CLAUDE.md`, plus the host manifests under `.cursor-plugin/`, `.claude-plugin/`, and `.codex-plugin/`.
