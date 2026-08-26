# Multi-Agent Web Team (Portfolio Showcase)

A **demonstration** of a role-based multi-agent web team for Cursor and Claude Code: strategy, design, engineering, and growth agents that collaborate through shared skills and a simple kickoff command.

> **Portfolio note.** This repo is an intentionally thin public showcase of the *architecture* — not a full production system. The deeper engagement playbooks, accumulated lessons, industry research cache, and studio-specific tooling used on client work remain private.

**Author:** [Will Vowell](https://github.com/WillyV347) · [breathingCode](https://www.breathingcode.com)

---

## Why this exists

Shipping a client site with AI usually fails in one of three ways:

1. One generalist agent does everything and produces generic output.
2. “Specialists” exist as labels but share no workflow, so handoffs are prose soup.
3. There are no human gates — design and launch happen without a decision.

This showcase shows the pattern that fixes that: **named roles**, **specialist skills**, **one ignition command**, and **explicit gates** between research → design → build → launch.

```
  Research  --Gate 1-->  Design  --Gate 2-->  Build  --Gate 3-->  Launch
     |                     |                    |
  product-manager       ui-designer      frontend-engineer
  seo-specialist                           backend-engineer
                                         accessibility-specialist
```

---

## What’s in this repo

| Path | Contents |
|---|---|
| [`agents/`](agents/) | 6 sample role agents (abridged) |
| [`skills/`](skills/) | 3 sample skills (`write-prd`, `component-scaffold`, `seo-audit`) |
| [`commands/demo-kickoff.md`](commands/demo-kickoff.md) | One-command demo flow for a **fictional** business |
| [`ARCHITECTURE.md`](ARCHITECTURE.md) | How roles, skills, and gates fit together |

**Not included (on purpose):** full orchestration playbooks, design-direction interrogation systems, engagement memory formats, lesson libraries, industry profile caches, or studio branding pipelines.

---

## Try the demo

### Cursor

1. Clone this repo (or add it as a local plugin path).
2. Open the folder in Cursor.
3. Run **`/demo-kickoff`** with a fictional business, e.g.  
   `/demo-kickoff Harbor & Pine Coffee — neighborhood café in Portland, OR`
4. Walk the three gates; agents will draft sample artifacts (brief, design notes, build checklist) — not a production site.

### Claude Code

Point a session at this folder (or vendor `agents/`, `skills/`, and `commands/` into a project’s `.claude/` tree) and invoke the demo kickoff the same way.

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

In a full team, these expand across strategy, design, engineering, content, and growth. This showcase keeps six so the pattern is readable in one sitting.

---

## Design principles (public)

1. **Roles over vibes** — each agent has a job description, not a personality prompt.
2. **Skills are reusable procedures** — agents call skills; skills don’t bury the whole business in one mega-prompt.
3. **Gates are human** — AI drafts; a person approves scope, design, and launch.
4. **Demo data only** — never invent real business facts; mark unknowns explicitly.
5. **Portfolio ≠ product** — what’s public teaches the shape of the system; production depth stays private.

---

## LinkedIn / portfolio blurb (copy-paste)

> Built a multi-agent web team for Cursor and Claude Code: role agents (PM, design, engineering, SEO, a11y) coordinated through shared skills and gated phases (research → design → build → launch). This public repo is a thin architecture showcase; production engagement tooling stays private.

---

## License

MIT — see [LICENSE](LICENSE). You’re free to learn from and adapt the *pattern*. Please don’t present this demo as a drop-in agency operating system; it isn’t one.
