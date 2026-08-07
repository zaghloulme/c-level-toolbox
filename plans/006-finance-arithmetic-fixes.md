# Plan 006: Fix finance arithmetic errors across six skills

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: For each file, open it and confirm the excerpt
> in "Current state" matches before making any edit. These are example/formula
> sections — confirm the exact numbers and text at the cited location.

## Status

- **Priority**: P2
- **Effort**: S
- **Risk**: LOW
- **Depends on**: none
- **Category**: bug
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

Six Finance & Pricing skills contain arithmetic errors in their worked examples or formulas. Executives using these skills to make capital allocation, pricing, and forecasting decisions will reproduce these errors. The fixes are all surgical — single numbers or formula cells — and require no structural changes to any skill. All fixes are confirmed by direct calculation against the stated inputs.

## Current state and fixes

### Fix 1 — roi-calculator: example ROI figures are wrong

**File:** `skills/roi-calculator/SKILL.md`

Current line (find by text):
```
**ROI:** ($156,800 - $234,000) / $234,000 = -33% at 12 months. Payback period: 22 months. 24-month ROI: +41%.
```

The 24-month ROI figure is wrong. Verification:
- Total benefits at 24 months: $156,800/yr × 2 = $313,600
- Total investment at 24 months: $180,000 + ($4,500 × 24) = $288,000
- Correct ROI: ($313,600 − $288,000) / $288,000 = **+8.9%**

The stated +41% cannot be derived from any consistent interpretation of the inputs and the skill's own formula.

Current line (find by text):
```
**Recommendation:** Negative 12-month ROI but positive at 22 months. If the ERP is expected to run for 5+ years, the full-term ROI is 185%. Proceed, but negotiate payment terms to defer the implementation fee to month 3 to smooth cash impact.
```

The 5-year ROI of 185% uses a mixed denominator (net benefits minus upfront only, not total investment) that contradicts the stated formula. Correct 5-year ROI using the formula as written:
- Total benefits at 5 years: $156,800 × 5 = $784,000
- Total investment at 5 years: $180,000 + ($4,500 × 60) = $450,000
- Correct ROI: ($784,000 − $450,000) / $450,000 = **+74%**

### Fix 2 — financial-model: M12/M24 projection numbers don't match inputs

**File:** `skills/financial-model/SKILL.md`

Current lines (find by text):
```
**M12 projection:** $520K MRR, 435 active customers, $340K monthly expenses, $180K net cash flow/month.
**M24 projection:** $940K MRR, 785 active customers, $620K monthly expenses (added 8 hires), $320K net monthly cash flow.
```

The stated inputs (280K MRR, $1,200 ARPU, 6% growth, 1.8% churn, 233 starting customers) produce approximately 382 customers / $459K MRR at M12 and 626 customers / $752K MRR at M24 under the formula as written. The M12/M24 figures are 14–25% higher than the inputs support with no expansion revenue rate stated.

### Fix 3 — cash-flow-forecast: conservative scenario narrative contradicts the table

**File:** `skills/cash-flow-forecast/SKILL.md`

Current line (find by text):
```
**Conservative Scenario** (revenue drops 15% in month 3):
```

The table that follows shows ending cash dropping by ~$29K/month from M4 onward (from $487K → $458K → $429K → $400K), which requires ~34% revenue decline plus elevated expenses — not a 15% drop. The mismatch is between the narrative label and what the numbers actually model.

### Fix 4 — cash-flow-forecast: runway formula breaks for profitable businesses

**File:** `skills/cash-flow-forecast/SKILL.md`

Current line (find by text):
```
- **Cash Runway:** Starting cash / (monthly expenses - monthly revenue) = months until $0
```

When revenue > expenses, the denominator is negative → the formula returns a negative number with no explanation. Need a conditional guard.

### Fix 5 — cost-analysis: overhead per unit is off by one

**File:** `skills/cost-analysis/SKILL.md`

Current line (find by text):
```
**Insight:** At 62% gross margin, the biggest lever is utilization — adding 5 more engagements/month cuts overhead per engagement from $4,500 to $3,750, improving margin to 65% with no cost cuts.
```

Verification: $90,000 / 25 engagements = **$3,600** (not $3,750; $3,750 corresponds to 24 engagements). The margin at $3,600 overhead is 64% (not 65%).

### Fix 6 — pricing-analysis: revenue impact overstated

**File:** `skills/pricing-analysis/SKILL.md`

Current line (find by text):
```
**Recommendation:** Increase to $2,400/year for new customers, grandfather existing at $1,200 for 18 months. Expected: 12% volume decrease on new sales, 85% net revenue increase. Churn rate expected to improve as price-sensitive cohort is replaced.
```

Verification: 88 customers (−12% from 100) × $2,400 = $211,200. Baseline: 100 × $1,200 = $120,000. Revenue increase: ($211,200 − $120,000) / $120,000 = **76%** (not 85%).

### Fix 7 — financial-dashboard: LTV formula omits gross margin (two files)

**File 1:** `skills/financial-dashboard/SKILL.md`

Current line (find by text):
```
| Customer Lifetime Value (LTV) | Avg Revenue per Customer x Avg Retention (months) | SaaS, memberships |
```

**File 2:** `skills/kpi-dashboard/SKILL.md` — handled in plan 001. Skip this fix here; it will be done as part of that plan.

### Fix 8 — financial-dashboard: revenue per client is unreconcilable

**File:** `skills/financial-dashboard/SKILL.md`

Current text in the ASCII dashboard (find by text):
```
║  Revenue per Client: $73,529                           ║
```

Verification: $1,240,000 revenue / 20 clients = $62,000; the companion investor-update skill uses 17 clients → $72,941. No integer client count produces $73,529. Use 17 clients and $72,941 to match the companion skill.

### Fix 9 — budget-planner: benchmark contradicts worked example

**File:** `skills/budget-planner/SKILL.md`

Current benchmark line (find by text):
```
| Fixed costs | 15-30% of revenue |
```

The worked example directly below shows a professional services firm with 53% fixed costs — nearly double the 30% upper bound — with no note that this category typically exceeds the benchmark. The benchmark range is too narrow for professional services.

### Fix 10 — financial-projection: scenario bands are asymmetric

**File:** `skills/financial-projection/SKILL.md`

Current lines (find by text):
```
- Conservative: [X-2]% monthly growth
- Optimistic: [X+3]% monthly growth
```

Conservative is base−2pp, optimistic is base+3pp. No rationale is given for the asymmetry. This structurally biases every board model produced by this skill upward.

## Scope

**In scope** (the only files to modify):
- `skills/roi-calculator/SKILL.md`
- `skills/financial-model/SKILL.md`
- `skills/cash-flow-forecast/SKILL.md`
- `skills/cost-analysis/SKILL.md`
- `skills/pricing-analysis/SKILL.md`
- `skills/financial-dashboard/SKILL.md`
- `skills/budget-planner/SKILL.md`
- `skills/financial-projection/SKILL.md`

**Out of scope** (do NOT touch):
- Any formula templates with `[X]` placeholders — those are fill-in-the-blank patterns, not errors
- Any skill not listed above
- `skills/kpi-dashboard/SKILL.md` — LTV formula handled in plan 001

## Steps

### Step 1: Fix roi-calculator — correct 24-month and 5-year ROI

Open `skills/roi-calculator/SKILL.md`.

**Change 1** — find:
```
24-month ROI: +41%.
```
Replace with:
```
24-month ROI: +8.9%.
```

**Change 2** — find:
```
the full-term ROI is 185%.
```
Replace with:
```
the full-term ROI is +74% (using the same formula: total benefits $784K minus total investment $450K over 5 years, divided by $450K).
```

**Verify**: `grep -n "41%\|185%" "skills/roi-calculator/SKILL.md"` → no matches.

### Step 2: Fix financial-model — correct M12/M24 projections

Open `skills/financial-model/SKILL.md`.

Find:
```
**M12 projection:** $520K MRR, 435 active customers, $340K monthly expenses, $180K net cash flow/month.
**M24 projection:** $940K MRR, 785 active customers, $620K monthly expenses (added 8 hires), $320K net monthly cash flow.
```

Replace with:
```
**M12 projection:** $459K MRR, 382 active customers, $340K monthly expenses, $119K net cash flow/month.
**M24 projection:** $752K MRR, 626 active customers, $620K monthly expenses (added 8 hires), $132K net monthly cash flow.
```

**Verify**: `grep -n "520K\|435 active\|940K\|785 active" "skills/financial-model/SKILL.md"` → no matches.

### Step 3: Fix cash-flow-forecast — align conservative scenario narrative with table

Open `skills/cash-flow-forecast/SKILL.md`.

Find:
```
**Conservative Scenario** (revenue drops 15% in month 3):
```

Replace with:
```
**Conservative Scenario** (revenue at 80% of base, expenses at 110% of base from month 3):
```

**Verify**: `grep -n "drops 15%" "skills/cash-flow-forecast/SKILL.md"` → no matches.

### Step 4: Fix cash-flow-forecast — add guard to runway formula

Open `skills/cash-flow-forecast/SKILL.md`.

Find:
```
- **Cash Runway:** Starting cash / (monthly expenses - monthly revenue) = months until $0
```

Replace with:
```
- **Cash Runway:** Starting cash / (monthly expenses - monthly revenue) = months until $0. If revenue ≥ expenses (cash-flow positive), output "N/A — cash-flow positive; runway is not the binding constraint" instead of calculating.
```

**Verify**: `grep -n "cash-flow positive\|N/A" "skills/cash-flow-forecast/SKILL.md"` → contains the new guard text.

### Step 5: Fix cost-analysis — correct overhead per unit

Open `skills/cost-analysis/SKILL.md`.

Find:
```
adding 5 more engagements/month cuts overhead per engagement from $4,500 to $3,750, improving margin to 65% with no cost cuts.
```

Replace with:
```
adding 5 more engagements/month cuts overhead per engagement from $4,500 to $3,600 ($90,000 ÷ 25), improving margin to 64% with no cost cuts.
```

**Verify**: `grep -n "3,750\|65% with no cost" "skills/cost-analysis/SKILL.md"` → no matches.

### Step 6: Fix pricing-analysis — correct revenue impact percentage

Open `skills/pricing-analysis/SKILL.md`.

Find:
```
Expected: 12% volume decrease on new sales, 85% net revenue increase.
```

Replace with:
```
Expected: 12% volume decrease on new sales, 76% net revenue increase (88 customers × $2,400 = $211,200 vs. 100 × $1,200 = $120,000 baseline).
```

**Verify**: `grep -n "85% net revenue" "skills/pricing-analysis/SKILL.md"` → no matches.

### Step 7: Fix financial-dashboard — LTV formula and revenue per client

Open `skills/financial-dashboard/SKILL.md`.

**Change 1** — find:
```
| Customer Lifetime Value (LTV) | Avg Revenue per Customer x Avg Retention (months) | SaaS, memberships |
```
Replace with:
```
| Customer Lifetime Value (LTV) | Avg Revenue per Customer x Avg Retention (months) x Gross Margin % | SaaS, memberships |
```

**Change 2** — find:
```
║  Revenue per Client: $73,529                           ║
```
Replace with:
```
║  Revenue per Client: $72,941                           ║
```

**Verify**:
- `grep -n "73,529" "skills/financial-dashboard/SKILL.md"` → no matches
- `grep -n "Gross Margin" "skills/financial-dashboard/SKILL.md"` → contains the LTV line

### Step 8: Fix budget-planner — add note to benchmark for professional services

Open `skills/budget-planner/SKILL.md`.

Find:
```
| Fixed costs | 15-30% of revenue |
```

Replace with:
```
| Fixed costs | 15-30% of revenue (note: personnel-heavy service businesses — consulting, agencies, professional services — commonly run 40-60% when salaries are the primary cost; benchmark accordingly) |
```

**Verify**: `grep -n "15-30%" "skills/budget-planner/SKILL.md"` → contains the updated line with the parenthetical note.

### Step 9: Fix financial-projection — make scenario bands symmetric

Open `skills/financial-projection/SKILL.md`.

Find:
```
- Conservative: [X-2]% monthly growth
- Optimistic: [X+3]% monthly growth
```

Replace with:
```
- Conservative: [X-2]% monthly growth
- Optimistic: [X+2]% monthly growth
```

**Verify**: `grep -n "X+3" "skills/financial-projection/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "41%\|185%" "skills/roi-calculator/SKILL.md"` → no matches
- [ ] `grep -n "520K\|435 active\|940K\|785 active" "skills/financial-model/SKILL.md"` → no matches
- [ ] `grep -n "drops 15%" "skills/cash-flow-forecast/SKILL.md"` → no matches
- [ ] `grep -n "cash-flow positive" "skills/cash-flow-forecast/SKILL.md"` → match found
- [ ] `grep -n "3,750" "skills/cost-analysis/SKILL.md"` → no matches
- [ ] `grep -n "85% net revenue" "skills/pricing-analysis/SKILL.md"` → no matches
- [ ] `grep -n "73,529" "skills/financial-dashboard/SKILL.md"` → no matches
- [ ] `grep -n "Gross Margin" "skills/financial-dashboard/SKILL.md"` → match found
- [ ] `grep -n "X+3" "skills/financial-projection/SKILL.md"` → no matches
- [ ] No formula templates (lines containing `[X]`) were modified in any file
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- A cited excerpt doesn't match the live file (numbers have already been changed or file structure differs)
- A fix requires changing a `[X]` placeholder template line rather than a concrete example number
- You cannot locate the text to replace (search with a shorter substring from the excerpt)

## Maintenance notes

- Fix 2 (financial-model M12/M24) assumes no expansion revenue. If the skill is later updated to include an explicit expansion revenue rate input, these projection figures should be recalculated to match that rate
- Fix 7 (LTV formula in financial-dashboard) aligns with the CLV skill's formula — future updates to the CLV skill's gross margin treatment should be mirrored here
- Fix 4 (runway guard) uses "N/A" as the output for cash-positive businesses; the financial-dashboard skill uses "Cash runway calculation assumes zero revenue as worst-case" as a note — that difference is intentional, as the two skills serve different contexts
