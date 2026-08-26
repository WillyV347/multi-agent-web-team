# Multi-Agent Web Team (Portfolio Showcase)

A **demonstration** of a role-based multi-agent web team for **Cursor**, **Claude Code**, and **Codex**: strategy, design, engineering, and growth agents that collaborate through shared skills and a gated kickoff.

> **Portfolio note.** This repo is an intentionally thin public showcase of the *architecture* — not a full production system. The deeper engagement playbooks, accumulated lessons, industry research cache, and studio-specific tooling used on client work remain private.

**Author:** [Will Vowell](https://github.com/WillyV347)

---

## Why this exists

Shipping a client site with AI usually fails in one of three ways:

1. One generalist agent does everything and produces generic output.
2. “Specialists” exist as labels but share no workflow, so handoffs are prose soup.
3. There are no human gates — design and launch happen without a decision.

This showcase shows the pattern that fixes that: **named roles**, **specialist skills**, **one ignition entry point**, and **explicit gates** between research → design → build → launch.

```
  Research  --Gate 1-->  Design  --Gate 2-->  Build  --Gate 3-->  Launch
     |                     |                    |
  product-manager       ui-designer      frontend-engineer
  seo-specialist                           backend-engineer
                                         accessibility-specialist
```

---

## Compatible hosts

| Host | Manifest | How to run the demo |
|---|---|---|
| **Cursor** | [`.cursor-plugin/plugin.json`](.cursor-plugin/plugin.json) | `/demo-kickoff …` |
| **Claude Code** | [`.claude-plugin/`](.claude-plugin/) | `/demo-kickoff …` (or namespaced if installed from the marketplace) |
| **Codex** | [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) + [`.agents/`](.agents/) | Invoke the **`demo-kickoff` skill** (slash commands are Cursor/Claude) |

Shared layout: root `agents/`, `skills/`, and `commands/` (Cursor + Claude). Codex loads skills from the plugin (`skills/`) and also from [`.agents/skills/`](.agents/skills/) when you open this repo directly. Session frame: identical [`AGENTS.md`](AGENTS.md) (Cursor/Codex) and [`CLAUDE.md`](CLAUDE.md) (Claude Code).

---

## What’s in this repo

| Path | Contents |
|---|---|
| [`agents/`](agents/) | 6 sample role agents (abridged) |
| [`skills/`](skills/) | `write-prd`, `component-scaffold`, `seo-audit`, `demo-kickoff` |
| [`commands/demo-kickoff.md`](commands/demo-kickoff.md) | Slash-command entry (Cursor / Claude Code) |
| [`ARCHITECTURE.md`](ARCHITECTURE.md) | How roles, skills, and gates fit together |
| [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json) | Codex repo marketplace pointing at this plugin |

**Not included (on purpose):** full orchestration playbooks, design-direction interrogation systems, engagement memory formats used in production, lesson libraries, industry profile caches, or studio branding pipelines.

---

## Install & try

### Cursor

1. Add this repo as a Cursor plugin (marketplace or local path). Manifest: [`.cursor-plugin/plugin.json`](.cursor-plugin/plugin.json).
2. Open a chat and run:  
   `/demo-kickoff Harbor & Pine Coffee — neighborhood café in Portland, OR`
3. Walk the three gates.

### Claude Code

**Option A — marketplace (recommended for reuse across repos)**

Commit this to a consuming repo’s `.claude/settings.json` (this showcase repo is **public**, so Claude Code web can fetch it):

```json
{
  "extraKnownMarketplaces": {
    "multi-agent-web-team": {
      "source": {
        "source": "github",
        "repo": "WillyV347/multi-agent-web-team"
      }
    }
  },
  "enabledPlugins": {
    "multi-agent-web-team@multi-agent-web-team": true
  }
}
```

Then run `/multi-agent-web-team:demo-kickoff …` (or the short name your install exposes).

**Option B — open this repo**

Clone and open this folder in Claude Code. `CLAUDE.md` loads the session frame; use `/demo-kickoff` or ask to run the demo kickoff skill.

**Vendoring fallback:** copy `skills/<name>/` → `.claude/skills/<name>/`, `commands/*.md` → `.claude/commands/`, `agents/*.md` → `.claude/agents/`.

### Codex

**Option A — install as a plugin from this repo’s marketplace**

1. Clone this repo (or add it as a marketplace source).
2. Codex reads [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json) (and the legacy-compatible [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json)).
3. Install **Multi-Agent Web Team** from the Plugins UI / plugin browser.
4. Ask: `Run the demo-kickoff skill for Harbor & Pine Coffee — neighborhood café in Portland, OR`  
   (or `@` the plugin / skill if your Codex build supports it).

**Option B — open this repo without installing**

`AGENTS.md` loads automatically. Skills are also discoverable under [`.agents/skills/`](.agents/skills/) (mirrors of `skills/` for Codex discovery). Ask Codex to run `demo-kickoff`.

---

## Sample agents

| Agent | Owns |
|---|---|
| `product-manager` | Scope, PRD, success metrics |
| `ui-designer` | Visual direction and mockup notes |
| `frontend-engineer` | UI implementation checklist |
| `backend-engineer` | APIs, forms, data boundaries |
| `seo-specialist` | On-page + technical SEO baseline |
| `accessibility-specialist` | WCAG floor and keyboard/screen-reader checks |

---

## Design principles (public)

1. **Roles over vibes** — each agent has a job description, not a personality prompt.
2. **Skills are reusable procedures** — agents call skills; skills don’t bury the whole business in one mega-prompt.
3. **Gates are human** — AI drafts; a person approves scope, design, and launch.
4. **Demo data only** — never invent real business facts; mark unknowns explicitly.
5. **Portfolio ≠ product** — what’s public teaches the shape of the system; production depth stays private.
6. **One repo, three hosts** — Cursor, Claude Code, and Codex share agents/skills; each host has its own thin manifest.

---

## License

MIT — see [LICENSE](LICENSE). You’re free to learn from and adapt the *pattern*. Please don’t present this demo as a drop-in agency operating system; it isn’t one.
