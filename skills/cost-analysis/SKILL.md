---
name: Cost Structure and Margin Analysis
version: 1.3.5
description: "Calculates the true cost to produce and deliver a product or service — direct costs, overhead allocation, and per-unit margins — then identifies where cost reductions will actually move the needle."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Cost Analysis

## Core Principle

YOU CANNOT OPTIMIZE WHAT YOU HAVE NOT MEASURED — EVERY COST MUST BE IDENTIFIED, CATEGORIZED, AND ASSIGNED TO A UNIT BEFORE MARGIN IMPROVEMENTS ARE POSSIBLE.

## Phase 1: Cost Inventory

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Product/service** | "What product or service are we analyzing costs for?" | No default — must be provided |
| **Selling price** | "What do you sell it for?" | No default — must be provided |
| **Monthly units sold** | "How many units do you sell per month?" | No default — must be provided |
| **Known direct costs** | "What costs go directly into making/delivering this? (materials, labor, tools)" | No default — list all |
| **Overhead costs** | "What are your monthly fixed business costs? (rent, software, insurance, salaries)" | Will estimate if unknown |

**GATE: Do not proceed without the product, selling price, and at least some cost data.**

## Phase 2: Cost Breakdown

### Direct Costs (COGS)

```
## Direct Cost Analysis: [Product/Service]

| Cost Component | Cost Per Unit | % of Price | Notes |
|---------------|--------------|-----------|-------|
| [Raw materials / supplies] | $[X] | [X]% | |
| [Direct labor (hours x rate)] | $[X] | [X]% | |
| [Platform/transaction fees] | $[X] | [X]% | |
| [Packaging / delivery] | $[X] | [X]% | |
| [Third-party services] | $[X] | [X]% | |
| **Total Direct Cost** | **$[X]** | **[X]%** | |
```

### Indirect Costs (Overhead Allocation)

```
## Overhead Allocation

| Overhead Category | Monthly Cost | Per Unit (÷ monthly units) |
|------------------|-------------|--------------------------|
| [Software/tools] | $[X] | $[X] |
| [Workspace/rent] | $[X] | $[X] |
| [Insurance] | $[X] | $[X] |
| [Marketing (allocated)] | $[X] | $[X] |
| [Admin/bookkeeping] | $[X] | $[X] |
| **Total Overhead/Unit** | | **$[X]** |
```

### Margin Calculations

```
## Margin Analysis

| Metric | Amount | Percentage |
|--------|--------|-----------|
| Selling price | $[X] | 100% |
| Direct costs (COGS) | $[X] | [X]% |
| **Gross profit** | **$[X]** | **[X]%** |
| Overhead per unit | $[X] | [X]% |
| **Net profit per unit** | **$[X]** | **[X]%** |

### At Current Volume ([X] units/month)
| Metric | Monthly | Annual |
|--------|---------|--------|
| Revenue | $[X] | $[X] |
| Total COGS | $[X] | $[X] |
| Gross profit | $[X] | $[X] |
| Total overhead | $[X] | $[X] |
| **Net profit** | **$[X]** | **$[X]** |
```

## Phase 3: Optimization

### Cost Reduction Opportunities

```
## Cost Optimization Recommendations

| Opportunity | Current Cost | Potential Cost | Savings/Unit | Effort |
|------------|-------------|---------------|-------------|--------|
| [Bulk purchasing] | $[X] | $[X] | $[X] | Low |
| [Supplier negotiation] | $[X] | $[X] | $[X] | Medium |
| [Process automation] | $[X] | $[X] | $[X] | High |
| [Material substitution] | $[X] | $[X] | $[X] | Medium |
```

### Volume Sensitivity

Show how costs change at different volumes:

```
## Volume Impact on Unit Economics

| Volume | Direct Cost/Unit | Overhead/Unit | Total Cost/Unit | Margin |
|--------|-----------------|---------------|----------------|--------|
| [Current] | $[X] | $[X] | $[X] | [X]% |
| [2x current] | $[X] | $[X] | $[X] | [X]% |
| [5x current] | $[X] | $[X] | $[X] | [X]% |
```

## Phase 4: Deliverable

```
## Summary

**Product:** [Name]
**True cost per unit:** $[X] (including overhead allocation)
**Current margin:** [X]%
**Target margin:** [X]%
**Top 3 cost reduction actions:**
1. [Action] — saves $[X]/unit
2. [Action] — saves $[X]/unit
3. [Action] — saves $[X]/unit
```

## Example: Enterprise Software Implementation Package

**Price:** $45,000. **Direct costs:** $12,400/engagement (project lead time $8,000, third-party tools $1,200, implementation support $2,400, data migration $800). **Overhead/engagement:** $4,500 (based on $90,000/month overhead at 20 engagements/month). **Total cost:** $16,900. **Margin:** 62%.

**Insight:** At 62% gross margin, the biggest lever is utilization — adding 5 more engagements/month cuts overhead per engagement from $4,500 to $3,600 ($90,000 ÷ 25), improving margin to 64% with no cost cuts.

## Anti-Patterns

- **Ignoring time costs** — team time has a dollar value. If a project requires 40 hours of senior staff at $150/hour fully loaded, that is $6,000 in cost.
- **Forgetting transaction and platform fees** — these are real costs. Include them.
- **Amortizing incorrectly** — one-time costs (product development, equipment) should be spread over expected lifetime units, not charged to the first sale.
- **Overhead allocation without volume context** — overhead per unit changes dramatically with volume. Always show the volume assumption.
- **Optimizing costs that do not move the needle** — a $0.10/unit savings matters at 100K units. At 100 units, focus on margin and pricing instead.

## Recovery

- **User does not know all their costs:** Walk through each delivery step and identify costs at each stage. Hidden costs usually live in time, fees, and tools.
- **Negative margins:** Flag immediately. Show which costs must be reduced or what price increase is needed to reach positive margin.
- **Service business (hard to quantify per unit):** Define the "unit" as one client engagement, one project, or one month of service. Calculate costs against that unit.
- **Multiple products sharing overhead:** Allocate overhead proportionally by revenue or by units — state the method and be consistent.
