---
name: Financial Model Builder
version: 1.6.5
description: "Builds bottoms-up financial models with documented revenue drivers, cost assumptions, headcount plans, cash flow projections, and sensitivity analysis — for internal planning or investor-ready fundraising."
---

# Financial Model

## Deliverable requirements (hard)

Every financial model MUST contain the following components as complete tables — never as summary narrative:

1. **Revenue drivers table** — unit economics, pricing tiers, sales cycle, conversion rates. Show the formulas.
2. **Cost assumptions table** — COGS, gross margin, unit cost breakdown.
3. **Headcount plan** — hires by quarter, by function, with fully-loaded cost per hire.
4. **Operating expenses** — categorized (S&M, R&D, G&A) with monthly or quarterly figures.
5. **Cash flow projection** — 36 months minimum, opening cash, inflows, outflows, closing cash, runway.
6. **Sensitivity table** — key drivers flexed ±20%, showing runway and break-even impact.
7. **Documented assumptions** — every headline number traceable to a stated input.

Never replace any of these with a summary or "here's what the model would contain." Produce every table in full inline.

## Core Principle

A FINANCIAL MODEL IS ONLY AS GOOD AS ITS ASSUMPTIONS — EVERY NUMBER MUST TRACE BACK TO A STATED ASSUMPTION THAT CAN BE CHALLENGED, TESTED, AND UPDATED.

## Phase 1: Model Inputs

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Business model** | "How do you make money? (SaaS, product, services, marketplace)" | No default — must be provided |
| **Revenue streams** | "What are your revenue sources and pricing?" | No default — must be provided |
| **Current metrics** | "Current MRR/revenue, customers, conversion rates, churn?" | Pre-revenue if not provided |
| **Cost structure** | "Fixed costs, variable costs, planned hires?" | Will build from scratch |
| **Model timeframe** | "12, 24, or 36 months?" | 24 months |
| **Model purpose** | "Who is this for? (internal planning, seed raise, Series A)" | Internal planning |

**GATE: Do not proceed without business model and revenue stream details.**

## Phase 2: Assumptions Sheet

Every model starts with a documented assumptions sheet.

```
## Key Assumptions

### Revenue Assumptions
| Assumption | Value | Source/Rationale |
|-----------|-------|-----------------|
| Starting MRR/Revenue | $[X] | Current |
| Monthly customer growth rate | [X]% | [Based on: historical, benchmark, or target] |
| Conversion rate (trial to paid) | [X]% | [Source] |
| Average revenue per customer | $[X] | [Current pricing] |
| Monthly churn rate | [X]% | [Historical or industry benchmark] |
| Expansion revenue rate | [X]% | [Upsell/cross-sell estimate] |

### Cost Assumptions
| Assumption | Value | Source/Rationale |
|-----------|-------|-----------------|
| Customer acquisition cost (CAC) | $[X] | [Current or estimated] |
| Gross margin | [X]% | [Based on COGS breakdown] |
| Monthly fixed costs (current) | $[X] | [Actual] |
| Planned hires | [X] people by month [X] | [Hiring plan] |
| Average fully-loaded cost per hire | $[X]/month | [Market rate] |
| Marketing spend (% of revenue) | [X]% | [Target] |
```

**GATE: Present assumptions to the user for validation before building the model.**

## Phase 3: Model Build

### Revenue Model (Bottoms-Up)

```
## Revenue Model

### Monthly Cohort Model
| Month | New Customers | Churned | Active | MRR | Expansion | Total MRR |
|-------|--------------|---------|--------|-----|-----------|-----------|
| M1 | [X] | [X] | [X] | $[X] | $[X] | $[X] |
| M2 | [X] | [X] | [X] | $[X] | $[X] | $[X] |
| ... | | | | | | |
| M24 | [X] | [X] | [X] | $[X] | $[X] | $[X] |

### Annual Revenue Summary
| | Year 1 | Year 2 |
|--|--------|--------|
| ARR (ending) | $[X] | $[X] |
| Total Revenue | $[X] | $[X] |
| YoY Growth | — | [X]% |
```

### Expense Model

```
## Expense Model

### Monthly Expense Breakdown
| Category | M1 | M6 | M12 | M18 | M24 |
|----------|----|----|----|-----|-----|
| COGS | $[X] | $[X] | $[X] | $[X] | $[X] |
| Personnel | $[X] | $[X] | $[X] | $[X] | $[X] |
| Marketing | $[X] | $[X] | $[X] | $[X] | $[X] |
| G&A | $[X] | $[X] | $[X] | $[X] | $[X] |
| **Total Opex** | **$[X]** | **$[X]** | **$[X]** | **$[X]** | **$[X]** |

### Headcount Plan
| Role | Start Month | Monthly Cost | Purpose |
|------|------------|-------------|---------|
| [Role] | M[X] | $[X] | [Why needed] |
```

### Cash Flow and Runway

```
## Cash Flow

| | M1 | M6 | M12 | M18 | M24 |
|--|----|----|-----|-----|-----|
| Revenue | $[X] | $[X] | $[X] | $[X] | $[X] |
| Expenses | $[X] | $[X] | $[X] | $[X] | $[X] |
| Net Cash Flow | $[X] | $[X] | $[X] | $[X] | $[X] |
| Cash Balance | $[X] | $[X] | $[X] | $[X] | $[X] |
| Runway (months) | [X] | [X] | [X] | [X] | [X] |

**Break-even month:** M[X]
**Cash needed to reach break-even:** $[X]
```

## Phase 4: Sensitivity Analysis

### Key Variable Sensitivity

```
## Sensitivity Analysis

### Impact of Growth Rate Changes on M24 ARR
| Growth Rate | M24 ARR | M24 Runway |
|------------|---------|-----------|
| [Base - 3%] | $[X] | [X] months |
| [Base rate] | $[X] | [X] months |
| [Base + 3%] | $[X] | [X] months |

### Impact of Churn Rate on M24 ARR
| Churn Rate | M24 ARR | LTV |
|-----------|---------|-----|
| [Base - 1%] | $[X] | $[X] |
| [Base rate] | $[X] | $[X] |
| [Base + 1%] | $[X] | $[X] |

### Unit Economics Summary
| Metric | Value |
|--------|-------|
| CAC | $[X] |
| LTV | $[X] |
| LTV:CAC | [X]:1 |
| Payback period | [X] months |
| Gross margin | [X]% |
```

## Example: B2B SaaS — Series A Stage

**Inputs:** $280K MRR, $1,200/mo ARPU, 6% monthly customer growth, 1.8% monthly churn, $3,200 CAC, $190K/mo fixed costs.

**M12 projection:** $459K MRR, 382 active customers, $340K monthly expenses, $119K net cash flow/month.
**M24 projection:** $752K MRR, 626 active customers, $620K monthly expenses (added 8 hires), $132K net monthly cash flow.

**Sensitivity:** If churn increases to 3%, M24 ARR drops 28%. If growth rate drops to 4%, M24 ARR drops 34%. Growth rate is the most sensitive variable — worth defending over cost cuts.

## Anti-Patterns

- **Top-down models** — "we will capture 1% of a $10B market" is not a financial model. Build bottoms-up from unit economics.
- **Static assumptions** — costs and growth rates change over time. Model step changes in hiring, pricing, and growth.
- **No assumptions documentation** — every number must have a rationale. Undocumented assumptions cannot be validated.
- **Ignoring churn** — for subscription businesses, churn is the most important variable. A 1% difference in monthly churn dramatically changes 24-month outcomes.
- **Perfect hockey sticks** — real growth is lumpy. Include realistic ramp-up periods for new channels and hires.

## Recovery

- **Pre-revenue:** Model from first customer acquisition. State assumptions clearly and weight the sensitivity analysis heavily — stakeholders know the numbers are uncertain.
- **No historical data for assumptions:** Use industry benchmarks and clearly label them. Update the model monthly as real data replaces assumptions.
- **Model too complex:** Simplify to revenue, expenses, and cash flow. Add complexity as the user gets comfortable.
- **Numbers do not work:** Show which assumptions need to change for the model to work — higher ARPU, lower churn, faster growth, or lower costs. Let the user decide which lever to pull.
