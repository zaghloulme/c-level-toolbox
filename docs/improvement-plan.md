# C Level Toolbox — Improvement Plan

Every skill was tested headlessly against its own stated purpose. This plan lists every issue found and the concrete change that fixes it. Grouped by root cause because skills in the same bucket share the same fix pattern — apply once, verify across all skills in the bucket.

See `scorecard.md` for full test results.

## Priority key

- **P0** — skill fails its claim entirely; user gets nothing useful
- **P1** — skill produces partial/wrong output; user needs to know what's missing
- **P2** — cosmetic or documentation-only

---

## P0 — asks questions instead of producing (3 skills)

**Affected skills:**
- `project-tracker` (score 1) — Outputs only intake questions; delivers zero markdown, tasks, statuses, owners, dates, or priorities.
- `ted-talk-outline` (score 1) — Produces no outline, no narrative arc, no engagement points, no timing markers. Asks clarifying questions instead of delivering.
- `service-productization` (score 3) — No productized service artifact delivered. Output is a clarifying prompt, not the deliverable. Awaits inputs instead of producing the framework.

**Root cause**

Skill instructions front-load an intake gate. When the user hasn't supplied specifics, Claude returns a clarifying prompt instead of a demonstrative artifact. Peer skills (roi-calculator, financial-dashboard, pitch-deck) already succeed here — they produce a realistic example with defaults when inputs are thin.

**Fix**

In each SKILL.md, add a **Fallback for thin input** clause immediately before the intake questions:

> **If the user has not supplied specific inputs, do NOT ask a wall of questions. Produce a realistic representative deliverable using reasonable defaults for a mid-sized B2B software company (~250 people, ~$40M revenue), clearly label the assumed values, and offer at the end to swap in the user's real data.**

This turns the skill from a gate into a working demo the user can immediately adapt.

**Verification**

Re-run headless test; score should move from 1 → 4+.

---

## P0 — writes to file, content never surfaces (4 skills)

**Affected skills:**
- `pitch-deck` (score 2) — Output is a .pptx binary file path, not structured markdown slide-by-slide content. Purpose requires pasteable markdown, not a generated file.
- `product-roadmap` (score 2) — No roadmap content shown—only a filename and advisory notes. No ICE scores, milestones, release timelines, or status tracking visible.
- `signature-talk` (score 2) — No actual script, slide deck, audience guide, or delivery notes delivered — only a table of contents and a claim that a file was saved.
- `performance-review` (score 2) — Output is a meta-description of documents, not the actual templates. No self-assessment, manager review, or conversation guide content exists.

**Root cause**

Skill tells Claude to `Write` the deliverable to a file (e.g. `pitch-deck.md`, `roadmap.md`). The user sees the tool-call summary line — 'Saved to X' — but not the content. Same failure mode in headless mode and in normal chat when the user is expecting to *see* the deck.

**Fix**

In each SKILL.md, change the output instruction from:

> Write the deliverable to `<file>.md`

to:

> **Produce the full deliverable inline in the chat first — every slide/section/row visible to the user. After the content is shown, offer to save it to `<file>.md` if the user wants a file copy.**

The content is the value; the file is optional.

**Verification**

Re-run headless test; the deliverable must appear in the `result` field, not just a filename.

---

## P1 — incomplete: core sections missing (5 skills)

**Affected skills:**
- `budget-planner` (score 2) — No monthly breakdowns, no variance tracking template, no adjustment triggers tied to revenue/expense thresholds. Single-period summary only.
- `financial-model` (score 2) — No actual model built: no revenue drivers, cost assumptions, headcount plan, cash flow projections, or sensitivity tables — only a summary narrative with placeholder numbers.
- `financial-projection` (score 2) — No P&L table, no month-by-month breakdown, no expense categories, no break-even analysis shown. Summary metrics only; no actual projection deliverable.
- `mission-statement` (score 3) — No stakeholder input process, no alignment exercises, no facilitation guide connecting purpose to daily decisions beyond a basic decision filter table.

**Root cause**

Skill lets Claude return a summary/narrative instead of the structural artifact promised in the description. No hard requirement that the specific tables/sections must appear.

**Fix**

In each SKILL.md, append a **Mandatory deliverable checklist** section that lists — as hard requirements — every table, section, or process step named in the skill's own description. Add:

> Never replace any of these sections with a summary or narrative note. Every checklist item must appear in full in the output.

For `budget-planner`: monthly breakdown grid (all 12 columns), variance columns, threshold-based adjustment triggers.  
For `financial-model`: revenue drivers table, cost assumptions, headcount plan, cash-flow projection, sensitivity table.  
For `financial-projection`: 12-month P&L table, expense categories, break-even analysis.  
For `mission-statement`: stakeholder input process, alignment exercise, decision-filter guide.

**Verification**

Re-run headless test; each mandated section must be textually present in the output.

---

## P1 — long deliverable truncates mid-section (1 skill)

**Affected skills:**
- `business-plan` (score 2) — Output cuts off mid-section ('## REV') — financial projections section entirely missing, rendering it incomplete for funding applications.

**Root cause**

Full business plans are legitimately long. The output was cut off mid-'REV[enue Projections]' — hit a token/output ceiling.

**Fix**

In `business-plan/SKILL.md`, restructure delivery:

> **Deliver the plan in two passes.** Pass 1: produce the executive summary, market analysis, product/service, marketing plan, operations plan, and management team in full (roughly the first half). Then STOP and ask: 'Continue with financial projections, funding request, and appendices?' before proceeding. This guarantees the reader sees complete sections rather than a truncated single output.

Alternatively: default to a condensed but structurally complete version and offer 'expand section X' as a follow-up.

**Verification**

Output ends at a clean section boundary with a 'Continue?' prompt, not mid-word.

---

## P1 — description-artifact mismatch (2 skills)

**Affected skills:**
- `ai-content-policy` (score 2) — Output is a finished blog post, not a policy. Missing: disclosure requirements, quality standards, review workflows — the entire policy framework.
- `annual-review` (score 2) — Output is fabricated content for a fictional company, not a review compiled from real user data. Skill was never actually invoked.

**Root cause**

The description is ambiguous enough that Claude produces subject-matter content (a blog post for ai-content-policy; fictional review content for annual-review) instead of the *meta-artifact* (a policy governing AI content; a review of actual user-supplied performance data).

**Fix**

In each SKILL.md, add — immediately after the front-matter — a **What this skill does and does not produce** paragraph:

For `ai-content-policy`:
> This skill produces a **policy document** governing how the organization uses AI to create content — disclosure rules, quality gates, review workflows. It does NOT produce AI-generated content itself.

For `annual-review`:
> This skill produces an **annual review compiled from actual performance data the user provides**. If no data is provided, ask for or generate clearly-labelled sample data first — never fabricate a fictional company's review.

**Verification**

Re-run; the output is a policy/framework document, not a work product in the covered domain.

---

## P2 — description overpromises for conversational skills (2 skills)

**Affected skills:**
- `setup` (score 1) — Output is a deck generator result, not an onboarding config writer. No preferences collected, no user-config.md written.
- `update-profile` (score 1) — Output updates no preference in user-config.md. It generates a sales deck — entirely unrelated to the skill's purpose.

**Root cause**

Not defects. These are interactive utilities that collect user preferences — they legitimately don't produce a stand-alone artifact and correctly asked the user for input. But their descriptions ('Update any preference...', 'First-run onboarding...') could be sharper about the conversational nature so users know what to expect.

**Fix**

Minor description tightening only. Add the word **interactive** to make the mode explicit:

For `setup`: `First-run interactive onboarding. Collects your preferences through a short conversation and writes user-config.md to personalize every skill in the toolbox.`

For `update-profile`: `Interactive update of any preference in user-config.md — tone, currency, tools, priorities, or anything else stored during setup.`

No behavioural change needed. This just prevents the tester (and users) from expecting an artifact.

**Verification**

Documentation-only change; excluded from artifact-producing test suite in future runs.

---

## Skills scoring 4 (small gaps)

These deliver but with minor room to improve. No fix required for ship-readiness; captured here for backlog.

- `ai-use-case-finder` — Roadmap row cut off mid-cell; scoring formula inconsistency (3×3×4=36 not 48 for competitive intel).
- `business-continuity-plan` — Output truncated mid-sentence (Part 4 cut off); communication templates CS-1 through CS-4 referenced but never delivered.
- `competitor-analysis` — Output truncates mid-sentence in Opportunity #2; otherwise comprehensive with matrix, SWOT, gaps, threats, and recommendations.
- `diagnostic-assessment` — No explicit scoring rubric, benchmarking comparisons, or 25-question detail visible — referenced but not included.
- `intellectual-property-audit` — OSS audit action item truncated mid-sentence. No budget summary or total remediation cost estimate provided.
- `risk-assessment` — Heat map ASCII formatting is broken/misaligned; R4 mitigation is cut off mid-sentence; R3, R7, R9, R10 lack full mitigation plans.

## Skills scoring 5 (49)

These match their stated purpose in the real-world test. No action needed. See `scorecard.md` for the full list.
---

## Post-publication changes (2026-08-08)

Removed from the toolbox: `nda-template`, `ai-ethics-policy`, `ai-content-policy`. The P1 fix for `ai-content-policy` is retained here for reference only — the skill no longer ships.
