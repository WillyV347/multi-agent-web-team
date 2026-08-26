# Multi-Agent Web Team — session frame

This repo is a **portfolio showcase** of a role-based multi-agent web team — not a production agency operating system. Changes in a demo should go through the sample roles and gates, not around them.

## Hosts

| Host | How this repo loads |
|---|---|
| **Cursor** | Plugin via [`.cursor-plugin/plugin.json`](.cursor-plugin/plugin.json); slash command `/demo-kickoff` |
| **Claude Code** | Plugin via [`.claude-plugin/`](.claude-plugin/); marketplace entry in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json); command `/demo-kickoff` (namespaced if installed as a marketplace plugin) |
| **Codex** | Plugin via [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) + skills under `skills/`; repo marketplace [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json); also auto-loads this `AGENTS.md`. Prefer the `demo-kickoff` **skill** (Codex has no slash-command surface like Cursor/Claude). |

Keep this file and `CLAUDE.md` identical.

## Ground-truth pointers (demo)

- Role briefs: [`agents/`](agents/)
- Skills: [`skills/`](skills/) (`write-prd`, `component-scaffold`, `seo-audit`, `demo-kickoff`)
- Cursor/Claude command: [`commands/demo-kickoff.md`](commands/demo-kickoff.md)
- Architecture: [`ARCHITECTURE.md`](ARCHITECTURE.md)

## Standing disciplines

- **Gates are human** — pause at Gate 1 (scope), Gate 2 (design), Gate 3 (build checklist).
- **Demo data only** — never invent real business facts; mark gaps `UNKNOWN — needs verification`.
- **Roles over vibes** — when a phase needs a specialist, open the matching file under `agents/` and follow it.
- **Skills are procedures** — call the sample skills instead of improvising a whole playbook.
- **Stay thin** — this is a showcase; do not expand into a full studio operating system.

## Change-routing (demo)

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

If you add an agent, skill, or command to this showcase, update **both** `AGENTS.md` and `CLAUDE.md`, plus the host manifests under `.cursor-plugin/`, `.claude-plugin/`, and `.codex-plugin/`.
