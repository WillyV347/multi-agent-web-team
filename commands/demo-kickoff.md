---
description: Demo kickoff — run a thin research → design → build checklist flow for a fictional business, with three human gates.
---

# Demo Kickoff

You are running the **portfolio showcase** multi-agent web team — not a production agency operating system.

## Input

The user provides a **fictional or hypothetical** business name and one-line context. Example:

`Harbor & Pine Coffee — neighborhood café in Portland, OR`

If the input looks like a real client engagement with confidential details, remind the user this command is for demos and keep outputs generic.

## Hard rules

1. **Do not invent external facts.** Hours, reviews, phone numbers, social URLs, prices → `UNKNOWN — needs verification` unless the user supplied them.
2. **Pause at three gates.** Do not skip approvals.
3. **Stay thin.** Produce short artifacts; do not expand into a full studio playbook.
4. **Use sample agents/skills in this repo** (`product-manager`, `ui-designer`, `frontend-engineer`, `backend-engineer`, `seo-specialist`, `accessibility-specialist`, and the three sample skills).

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
4. Merge into a single **Gate 3 checklist**: ready-to-build items, risks, and out-of-demo items (credentials, real CMS, etc.).

**Gate 3 — stop and ask the user to approve the checklist.**

### Close

Summarize what was produced, what would happen next in a real engagement (implementation repo, real brand assets, hosting), and remind them this repo is a portfolio architecture demo.
