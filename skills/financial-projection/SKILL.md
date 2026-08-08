---
name: 12-Month Financial Projection
version: 1.4.5
description: "Builds 12-month financial projections with three revenue scenarios, expense forecasting by category, break-even analysis, and a month-by-month P&L summary — for planning, investor presentations, or loan applications."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Financial Projection

## Deliverable requirements (hard)

Every 12-month projection MUST contain the following as complete tables — never as summary metrics only:

1. **Month-by-month P&L table** — all 12 months as columns; rows for revenue, COGS, gross profit, operating expenses (categorized), EBITDA, net income.
2. **Three revenue scenarios** — conservative, base, optimistic — each with its own P&L or at minimum a revenue-line row per scenario.
3. **Expense forecasting by category** — S&M, R&D, G&A, Facilities, Other — with month-over-month figures, not annual totals only.
4. **Break-even analysis** — the specific month revenue covers total costs under the base scenario.
5. **Assumptions log** — every headline figure traceable to an input.

Never substitute a narrative summary for the tables. Produce every table in full inline.

## Core Principle

PROJECTIONS ARE NOT PREDICTIONS — THEY ARE STRUCTURED ASSUMPTIONS THAT HELP YOU MAKE DECISIONS TODAY BASED ON WHERE THE NUMBERS COULD GO.

## Phase 1: Baseline Data

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Current monthly revenue** | "What is your current monthly revenue?" | No default — must be provided |
| **Revenue model** | "How do you make money? (subscriptions, one-time sales, retainers, project-based)" | No default — must be provided |
| **Current monthly expenses** | "What are your total monthly expenses?" | No default — must be provided |
| **Growth rate assumption** | "What monthly growth rate do you expect? (or historical growth if available)" | 3-5% month-over-month |
| **Planned investments** | "Any major expenses planned? (hires, equipment, marketing spend)" | None |
| **Projection purpose** | "What is this for? (internal planning, investors, loan, strategic)" | Internal planning |

**GATE: Do not proceed without current revenue, expenses, and revenue model.**

## Phase 2: Revenue Projection

### Three Scenarios

Build projections for conservative, base, and optimistic scenarios:

```
## Revenue Projection: 12-Month Outlook

### Assumptions
- Base monthly growth rate: [X]%
- Conservative: [X-2]% monthly growth
- Optimistic: [X+2]% monthly growth
- Starting monthly revenue: $[X]

### Monthly Revenue by Scenario

| Month | Conservative | Base | Optimistic |
|-------|-------------|------|------------|
| Month 1 | $[X] | $[X] | $[X] |
| Month 2 | $[X] | $[X] | $[X] |
| ... | | | |
| Month 12 | $[X] | $[X] | $[X] |
| **Annual Total** | **$[X]** | **$[X]** | **$[X]** |
```

### Revenue Drivers

Break revenue into its component drivers:

```
### Revenue Driver Breakdown (Base Case)

| Driver | Month 1 | Month 6 | Month 12 |
|--------|---------|---------|----------|
| [Product/service 1] units | [X] | [X] | [X] |
| [Product/service 1] revenue | $[X] | $[X] | $[X] |
| [Product/service 2] units | [X] | [X] | [X] |
| [Product/service 2] revenue | $[X] | $[X] | $[X] |
| **Total** | **$[X]** | **$[X]** | **$[X]** |
```

## Phase 3: Expense Forecast

### Expense Categories

```
## Expense Projection

### Fixed Expenses (Monthly)
| Category | Current | Month 6 | Month 12 | Notes |
|----------|---------|---------|----------|-------|
| [Rent/workspace] | $[X] | $[X] | $[X] | |
| [Software] | $[X] | $[X] | $[X] | |
| [Salaries] | $[X] | $[X] | $[X] | |

### Variable Expenses (Scale with Revenue)
| Category | % of Revenue | Month 1 | Month 6 | Month 12 |
|----------|-------------|---------|---------|----------|
| [COGS] | [X]% | $[X] | $[X] | $[X] |
| [Marketing] | [X]% | $[X] | $[X] | $[X] |
| [Contractors] | [X]% | $[X] | $[X] | $[X] |

### Planned Step-Up Costs
| Investment | Month | Monthly Cost | Purpose |
|-----------|-------|-------------|---------|
| [New hire] | Month [X] | $[X] | [Rationale] |
| [Tool upgrade] | Month [X] | $[X] | [Rationale] |
```

## Phase 4: Profit and Loss Summary

### Monthly P&L

```
## Projected Profit & Loss (Base Case)

| | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 | M9 | M10 | M11 | M12 |
|--|----|----|----|----|----|----|----|----|----|----|-----|-----|
| Revenue | | | | | | | | | | | | |
| COGS | | | | | | | | | | | | |
| Gross Profit | | | | | | | | | | | | |
| Operating Expenses | | | | | | | | | | | | |
| **Net Profit** | | | | | | | | | | | | |
| Cumulative P&L | | | | | | | | | | | | |

### Break-Even Point
- Break-even month: Month [X] (base case)
- Monthly revenue needed to break even: $[X]
```

### Key Metrics Over Time

```
### Financial Health Metrics

| Metric | Month 1 | Month 6 | Month 12 |
|--------|---------|---------|----------|
| Gross margin | [X]% | [X]% | [X]% |
| Net margin | [X]% | [X]% | [X]% |
| Monthly burn rate | $[X] | $[X] | $[X] |
| Cash runway (months) | [X] | [X] | [X] |
```

## Example: New Service Line Launch

**Inputs:** Existing business at $850K/month revenue, adding a new consulting practice. New practice starts at $80K/month, expected 8% monthly growth for 6 months then stabilizing. New hire in month 2 at $12,000/month fully loaded. Additional fixed costs $8,000/month.

**Result (Base Case):** New practice reaches $118K/month by month 6. Total business revenue at month 12: $1.08M. Contribution from new practice turns positive at month 3 after hire and setup costs.

## Anti-Patterns

- **Hockey stick projections without justification** — 50%+ monthly growth needs a specific driver, not optimism
- **Ignoring step-up costs** — revenue growth triggers new expenses (more support, infrastructure, team). Model these.
- **Single scenario only** — always model at least conservative and base. Stakeholders need to see the range.
- **Projecting revenue without unit economics** — "we will make $1M" is not a projection. Show the units, prices, and conversion rates that produce $1M.
- **Forgetting taxes** — include estimated tax liability in the expense forecast

## Recovery

- **Pre-revenue business unit:** Start with zero revenue and model from first sale. Focus on expense runway — how many months until the money runs out?
- **Highly variable revenue:** Use the lowest 3 months as the conservative base. Model seasonality if applicable.
- **No growth rate data:** Use industry benchmarks or model flat revenue as conservative, 3% as base, 8% as optimistic.
- **Projections for investors:** Add a "key assumptions" section listing every assumption and its source. Investors stress-test assumptions, not the numbers themselves.
