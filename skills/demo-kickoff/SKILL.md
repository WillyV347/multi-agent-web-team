---
name: demo-kickoff
description: Run the demo kickoff — thin research → design → build checklist for a fictional business, with three human gates. Use on Codex, Claude Code, or Cursor when the user asks to try the multi-agent web team.
---

# Demo Kickoff (skill)

You are running the **multi-agent web team demo** in this repo.

This skill is the **host-neutral** entry point (especially for **Codex**, which does not use Cursor/Claude slash commands). On Cursor/Claude Code, `/demo-kickoff` in `commands/demo-kickoff.md` is equivalent — keep behavior aligned.

## Input

The user provides a **fictional or hypothetical** business name and one-line context. Example:

`Harbor & Pine Coffee — neighborhood café in Portland, OR`

If the input includes real business details that look confidential, remind the user this skill is for demos with fictional scenarios and keep outputs generic.

## Hard rules

1. **Do not invent external facts.** Hours, reviews, phone numbers, social URLs, prices → `UNKNOWN — needs verification` unless the user supplied them.
2. **Pause at three gates.** Do not skip approvals.
3. **Stay in scope.** Produce short demo artifacts; do not expand into a full multi-phase delivery playbook unless the user explicitly asks.
4. **Use sample agents/skills in this repo** (`product-manager`, `ui-designer`, `frontend-engineer`, `backend-engineer`, `seo-specialist`, `accessibility-specialist`, plus `write-prd`, `component-scaffold`, `seo-audit`).

## Flow

### Phase A — Research brief

1. Act as `product-manager` (optionally lean on `write-prd` if scope is feature-sized).
2. Ask `seo-specialist` for a one-page IA + intent sketch.
3. Produce a **Gate 1 brief**: problem, audience, primary success metric, MUST features, non-goals, open questions.

**Gate 1 — stop and ask the user to approve or correct the brief.**

### Phase B — Design notes

After Gate 1 approval:

1. Act as `ui-designer`.
2. Produce **design notes**: palette commitment, type pairing, hero composition, one distinctive layout move, a11y notes for contrast/motion.
3. Keep it to roughly one page.

**Gate 2 — stop and ask the user to approve or correct the visual direction.**

### Phase C — Build checklist

After Gate 2 approval:

1. `frontend-engineer` — page/component checklist; use `component-scaffold` for any net-new reusable component.
2. `backend-engineer` — minimum form/API/data notes.
3. `accessibility-specialist` — WCAG floor checklist tied to the design notes.
4. Merge into a single **Gate 3 checklist**: ready-to-build items, risks, and items that need real credentials or infrastructure (CMS, hosting, API keys, etc.).

**Gate 3 — stop and ask the user to approve the checklist.**

### Close

Summarize what was produced. Optionally note logical next steps if the user wanted to build for real: create an implementation repo, add real brand assets, wire up hosting — without implying this demo repo becomes that build.
