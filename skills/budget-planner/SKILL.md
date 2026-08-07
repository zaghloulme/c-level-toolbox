---
name: Business Budget Planner
version: 1.4.5
description: "Creates monthly and annual business budgets with category breakdowns, variance tracking templates, and adjustment triggers tied to revenue and expense thresholds."
---

# Budget Planner

## Core Principle

A BUDGET IS A DECISION-MAKING TOOL, NOT A SPREADSHEET — EVERY LINE ITEM MUST TIE TO A BUSINESS PRIORITY AND HAVE A CLEAR OWNER.

## Phase 1: Business Snapshot

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Monthly revenue** | "What is your current or expected monthly revenue?" | No default — must be provided |
| **Business type** | "What type of business? (service, product, SaaS, manufacturing)" | Service-based |
| **Team size** | "How many people? (headcount, contractors)" | No default — must be provided |
| **Top 3 expense categories** | "What are your biggest costs?" | No default — must be provided |
| **Budget period** | "Monthly or annual budget?" | Monthly |
| **Growth goals** | "Any planned investments or growth spending?" | None specified |

**GATE: Do not proceed without monthly revenue and business type.**

## Phase 2: Budget Framework

### Category Structure

Build the budget using these standard categories, adjusted for business type:

```
## Budget: [Business Name] — [Month/Year or Annual]

### Revenue
| Source | Budgeted | Notes |
|--------|----------|-------|
| [Primary revenue] | $[X] | |
| [Secondary revenue] | $[X] | |
| **Total Revenue** | **$[X]** | |

### Fixed Costs (Do not change month-to-month)
| Category | Budgeted | % of Revenue | Notes |
|----------|----------|-------------|-------|
| Rent/workspace | $[X] | [X]% | |
| Software/subscriptions | $[X] | [X]% | |
| Insurance | $[X] | [X]% | |
| Salaries | $[X] | [X]% | |
| **Total Fixed** | **$[X]** | **[X]%** | |

### Variable Costs (Scale with revenue)
| Category | Budgeted | % of Revenue | Notes |
|----------|----------|-------------|-------|
| Marketing/advertising | $[X] | [X]% | |
| Contractors | $[X] | [X]% | |
| COGS/fulfillment | $[X] | [X]% | |
| Transaction fees | $[X] | [X]% | |
| **Total Variable** | **$[X]** | **[X]%** | |

### Growth Investments (Discretionary)
| Category | Budgeted | % of Revenue | Notes |
|----------|----------|-------------|-------|
| New tools/equipment | $[X] | [X]% | |
| Training | $[X] | [X]% | |
| Hiring | $[X] | [X]% | |
| **Total Growth** | **$[X]** | **[X]%** | |

### Summary
| | Amount | % of Revenue |
|--|--------|-------------|
| Total Revenue | $[X] | 100% |
| Total Expenses | $[X] | [X]% |
| **Net Profit** | **$[X]** | **[X]%** |
```

### Benchmark Allocations (Service and Professional Organizations)

| Category | Healthy Range |
|----------|--------------|
| Fixed costs | 15-30% of revenue (note: personnel-heavy service businesses — consulting, agencies, professional services — commonly run 40-60% when salaries are the primary cost; benchmark accordingly) |
| Marketing | 5-15% of revenue |
| Contractors and variable labor | 10-25% of revenue |
| Profit reserve | 10-20% of revenue |

## Phase 3: Variance Tracking

### Monthly Tracking Template

```
## Variance Report: [Month]

| Category | Budgeted | Actual | Variance | % Variance |
|----------|----------|--------|----------|------------|
| [Category] | $[X] | $[X] | +/-$[X] | +/-[X]% |

### Variance Flags
Over budget by >15%: [List categories]
Over budget by 5-15%: [List categories]
On or under budget: [List categories]
```

### Adjustment Triggers

Define when to take action:

```
## Adjustment Triggers

| Trigger | Action |
|---------|--------|
| Revenue drops >10% from plan | Cut discretionary spending, pause growth investments |
| Any category exceeds budget by >20% | Review and reallocate or cut before next month |
| Revenue exceeds plan by >15% | Allocate surplus: 50% profit reserve, 30% growth, 20% distribution |
| Cash reserve drops below 2 months expenses | Freeze all non-essential spending |
| Marketing spend exceeds 15% without corresponding revenue increase | Audit campaign ROI, pause underperformers |
```

## Phase 4: Deliverable

Present the complete budget document and provide quarterly review reminders.

```
budget/
└── budget-[YYYY].md (or budget-[YYYY-MM].md for monthly)
```

Include: Revenue targets, categorized expenses, percentage benchmarks, variance tracking template, and adjustment triggers.

## Example: Professional Services Firm ($180K/month Revenue)

| Category | Amount | % |
|----------|--------|---|
| Revenue | $180,000 | 100% |
| Salaries | $72,000 | 40% |
| Office/facilities | $18,000 | 10% |
| Software/tools | $5,400 | 3% |
| Marketing | $18,000 | 10% |
| Contractors | $18,000 | 10% |
| Professional development | $3,600 | 2% |
| Profit reserve | $27,000 | 15% |
| Buffer | $18,000 | 10% |

## Anti-Patterns

- **Budgeting based on aspirations instead of data** — use actual revenue from the past 3-6 months, not best-case projections
- **No contingency buffer** — always budget 5-10% for unexpected expenses
- **Set and forget** — a budget reviewed quarterly is a suggestion. Review monthly, adjust as needed.
- **Cutting marketing first** — marketing drives revenue. Cut low-ROI marketing, not all marketing.

## Recovery

- **Irregular revenue:** Budget based on the average of the last 6 months. Create a "minimum viable budget" for low months and a "growth budget" for high months.
- **No historical data (new business unit):** Build a conservative budget based on expected revenue, then update monthly with real data for the first 6 months.
- **Expenses exceed revenue:** Flag immediately. Identify which costs can be cut or deferred, and what revenue increase is needed to break even.
- **Multiple revenue streams:** Break revenue into separate lines but keep expenses consolidated unless they directly tie to one stream.
