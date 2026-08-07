# C Level Toolbox

Executive decision support inside Claude — 69 skills for strategy, finance, operations, legal, HR, and growth. Built for C-level leaders and senior teams in mid-to-large organizations.

Everything runs entirely within Claude. There is nothing to connect, no account to link, and no third-party tool required. You describe what you need in plain language; the toolbox produces a finished, ready-to-use document.

---

## What it does

Ask for a business deliverable and get it back complete — not a blank template. For example:

- "Build me a pitch deck for our Series A" → a full slide-by-slide deck in markdown, ready to paste into PowerPoint, Google Slides, or Keynote.
- "Forecast our cash flow for the next 12 months" → a three-scenario forecast with runway and hiring guidance.
- "Draft a mutual NDA for a vendor discussion" → a complete agreement with a legal-review disclaimer.
- "Score these three vendors for us" → a weighted comparison matrix with a recommendation.

The toolbox adapts to how you work: your preferred tone, your currency, your role, and your language. You set this once and it applies everywhere.

---

## Getting started

### 1. Install

In Claude Code, add the plugin from this folder:

```
/plugin install c-level-toolbox
```

Or point Claude Code at the folder directly:

```
claude --plugin-dir /path/to/c-level-toolbox
```

### 2. Run setup (one time)

Type:

```
/setup
```

Claude asks a few short questions — your name, role, how you like to be spoken to, your currency, and your top priorities — then remembers them for every future request. This takes about a minute. You can change any answer later with `/update-profile`.

### 3. Use any skill

Type a slash command, or just describe what you need. To see the full menu, ask Claude "what can the C Level Toolbox do?" or browse the categories below.

---

## What's inside

**Finance and Pricing** — break-even, budgets, cash flow, compensation, cost analysis, financial dashboards and models, projections, investor updates, pricing, P&L, quarterly reviews, revenue forecasts, ROI.

**HR and Team** — annual reviews, culture documents, employee surveys, exit interviews, hiring scorecards, OKRs, 1:1 templates, performance reviews.

**Operations and Systems** — annual planning, business continuity, change management, decision matrices, delegation frameworks, project trackers, QA checklists, risk assessments, vendor evaluations.

**Legal and Compliance** — compliance checklists, IP audits, letters of intent, NDAs, non-compete and partnership agreements.

**Sales and Strategy** — business plans, competitor analysis, joint ventures, market research and sizing, partnership proposals, pitch decks, product roadmaps, revenue models, SWOT.

**Growth, Branding, Analytics, and Consulting** — annual reports, churn analysis, KPI dashboards, customer lifetime value, benchmarking, brand positioning, executive resumes, expert positioning, mission statements, signature talks, TED-style outlines, consulting frameworks, diagnostics, crisis communications, LinkedIn strategy, and more.

**AI and Technology** — AI content and ethics policies, AI use-case discovery.

---

## Personalization

Your preferences live in a file called `user-config.md` in your working directory. It is created by `/setup` and read silently before every response. It is never shared and is excluded from version control by default.

To update it at any time:

```
/update-profile
```

---

## A note on legal and financial output

The legal skills (NDAs, agreements, letters of intent) generate drafts for reference and negotiation. They are not legal advice — have any agreement reviewed by a qualified attorney in the relevant jurisdiction before signing. The finance skills produce models and estimates based on the inputs you provide; review the assumptions before acting on them.

---

*Version 3.2.0 — by AxuraOps*
