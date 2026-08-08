# C-Level Toolbox

71 Claude skills for the recurring work of running a company — strategy, finance, sales, product, HR, operations, legal, communications, and decision frameworks.

Every skill produces a complete deliverable, not a blank template. Zero external tools, zero accounts to connect, zero API keys.

**Browse all 71 skills →** open [`skills.html`](./skills.html) in your browser.

---

## Install

### Claude Code (CLI) — recommended

```
/plugin marketplace add zaghloulme/c-level-toolbox
/plugin install c-level-toolbox@c-level-toolbox-marketplace
```

That's it. Both commands run inside a Claude Code session. The first line registers this repo as a marketplace; the second installs the toolbox as a plugin.

Then start any session with:

```
/setup
```

Claude asks a few short questions (name, role, currency, tone, priorities) and writes a `user-config.md` that every skill personalizes to. Change anything later with `/update-profile`.

### Claude.ai (web) and Claude Desktop

Anthropic supports one-skill-at-a-time upload:

1. Grab the ZIP for the skill you want from the [Releases page](https://github.com/zaghloulme/c-level-toolbox/releases)
2. In Claude, open **Settings → Capabilities → Skills → Upload**
3. Select the ZIP; toggle the skill on

Repeat per skill. There is no whole-toolbox upload on web/Desktop today.

---

## What's inside

| Category | Count | Examples |
|---|:---:|---|
| Setup | 2 | `setup`, `update-profile` |
| Strategy & Planning | 7 | `annual-planning`, `business-plan`, `swot-analysis`, `okr-builder` |
| Finance & Metrics | 15 | `financial-model`, `roi-calculator`, `pricing-strategy`, `kpi-dashboard` |
| Sales & Marketing | 8 | `pitch-deck`, `competitor-analysis`, `market-sizing`, `churn-analysis` |
| Product & Roadmap | 3 | `product-roadmap`, `ai-use-case-finder`, `service-productization` |
| People & HR | 8 | `performance-review`, `compensation-plan`, `hiring-scorecard`, `employee-survey` |
| Operations & Projects | 9 | `project-tracker`, `risk-assessment`, `vendor-evaluation`, `annual-review` |
| Legal & Compliance | 9 | `nda-template`, `compliance-checklist`, `ip-audit`, `partnership-agreement` |
| Communication & Content | 6 | `signature-talk`, `ted-talk-outline`, `investor-update`, `crisis-comms` |
| Decision Frameworks | 4 | `decision-matrix`, `consulting-framework`, `benchmarking-report` |

**Full catalogue:** [`skills.html`](./skills.html) — searchable, categorized, one card per skill.

---

## How it works

Once installed, describe what you need in plain English. Claude picks the matching skill by its description and produces the full deliverable.

Examples:

- "Build me a Series A pitch deck." → 12-slide deck in markdown, problem through ask
- "Forecast cash flow for the next 12 months, three scenarios." → conservative/base/optimistic, month-by-month, break-even
- "Draft a mutual NDA for a vendor conversation." → complete agreement with legal-review disclaimer
- "Score these three vendors." → weighted comparison matrix + recommendation

Every skill reads your `user-config.md` first, so tone, currency, and priorities match how you actually work.

---

## Quality

Every skill in this toolbox has been headless-tested against its own stated purpose and graded by an LLM judge on a 1–5 rubric. Current baseline: **60+ skills at score 5**, all remaining skills at 3 or above. Full scorecard in [`docs/scorecard.md`](./docs/scorecard.md); improvement patterns in [`docs/improvement-plan.md`](./docs/improvement-plan.md).

---

## Legal and finance disclaimer

Legal skills (NDAs, agreements, letters of intent) produce drafts for reference and negotiation, not legal advice. Have any agreement reviewed by a qualified attorney in the relevant jurisdiction before signing.

Finance skills produce models and estimates from the inputs you provide. Review the assumptions before acting on them.

---

MIT License. Version 3.2.0.
