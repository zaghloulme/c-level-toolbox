---
name: Revenue Forecast
version: 1.4.5
description: "Projects revenue with conservative, base, and optimistic scenarios using historical data, growth drivers, and planned changes — by stream, channel, or segment — for budgeting, planning, or board reporting."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Revenue Forecast

## Core Principle

A REVENUE FORECAST IS A RANGE, NOT A NUMBER — PRESENT THREE SCENARIOS AND IDENTIFY WHICH ASSUMPTIONS SEPARATE THEM.

## Phase 1: Historical Data

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Monthly revenue (last 6-12 months)** | "Share your monthly revenue for the last 6-12 months." | No default — must be provided |
| **Revenue streams** | "How do you generate revenue? (products, services, subscriptions, one-time)" | No default — must be provided |
| **Seasonality** | "Are there seasonal patterns in your revenue?" | No known seasonality |
| **Growth drivers** | "What is driving growth? (new clients, new products, geographic expansion, pricing)" | Organic growth |
| **Planned changes** | "Any upcoming changes? (new product launch, price increase, new channel, headcount)" | None planned |
| **Forecast period** | "How far out? (3, 6, or 12 months)" | 12 months |

**GATE: Do not proceed without at least 3 months of historical revenue data.**

## Phase 2: Trend Analysis

### Historical Performance

```
## Revenue Analysis

### Monthly Revenue History
| Month | Revenue | MoM Change | YoY Change |
|-------|---------|-----------|-----------|
| [Month] | $[X] | +/-[X]% | +/-[X]% |
| ... | | | |

### Key Metrics
| Metric | Value |
|--------|-------|
| Average monthly revenue (last 6 months) | $[X] |
| Average monthly growth rate | [X]% |
| Revenue trend | Growing / Flat / Declining |
| Highest month | $[X] ([Month]) |
| Lowest month | $[X] ([Month]) |
| Revenue volatility (std deviation) | $[X] |
```

### Revenue by Stream

```
### Revenue Breakdown by Stream
| Stream | Monthly Avg | % of Total | Growth Rate | Trend |
|--------|-----------|-----------|-------------|-------|
| [Stream 1] | $[X] | [X]% | [X]% | ↑↓→ |
| [Stream 2] | $[X] | [X]% | [X]% | ↑↓→ |
```

## Phase 3: Forecast Model

### Three Scenarios

```
## Revenue Forecast: [Period]

### Assumptions

| Factor | Conservative | Base | Optimistic |
|--------|-------------|------|------------|
| Monthly growth rate | [X]% | [X]% | [X]% |
| New stream revenue | $0 | $[X] | $[X] |
| Seasonal adjustment | Yes | Yes | Yes |
| Price change impact | None | None | +[X]% |
| Churn/loss factor | [X]% | [X]% | [X]% |

### Monthly Forecast

| Month | Conservative | Base | Optimistic |
|-------|-------------|------|------------|
| M1 | $[X] | $[X] | $[X] |
| M2 | $[X] | $[X] | $[X] |
| ... | | | |
| M12 | $[X] | $[X] | $[X] |
| **Total** | **$[X]** | **$[X]** | **$[X]** |

### Forecast by Revenue Stream (Base Case)

| Month | [Stream 1] | [Stream 2] | [Stream 3] | Total |
|-------|-----------|-----------|-----------|-------|
| M1 | $[X] | $[X] | $[X] | $[X] |
| ... | | | | |
```

### Key Drivers and Risks

```
### What Separates the Scenarios

**Conservative → Base:** [Key assumption difference, e.g., "Assumes new
enterprise sales rep is productive from M3, generating 2 new accounts/month"]

**Base → Optimistic:** [Key assumption difference, e.g., "Assumes strategic
partnership launches in Q2 adding $80K/month in co-sell revenue"]

### Downside Risks
1. [Risk] — Impact: -$[X]/month — Likelihood: [High/Med/Low]
2. [Risk] — Impact: -$[X]/month — Likelihood: [High/Med/Low]

### Upside Opportunities
1. [Opportunity] — Impact: +$[X]/month — Likelihood: [High/Med/Low]
```

## Phase 4: Deliverable

```
## Forecast Summary

**Forecast period:** [X] months
**Conservative annual revenue:** $[X]
**Base case annual revenue:** $[X]
**Optimistic annual revenue:** $[X]

**Planning recommendation:** Budget against the conservative scenario.
Target the base case. Celebrate if you hit optimistic.
```

## Example: B2B Services Division ($1.5M/month Average)

**History:** 8 months of data, $1.3M-$1.7M range, average $1.5M, 3.5% monthly growth driven by account expansion and 2 new enterprise clients per quarter.

**Planned changes:** New sales hire starting month 2 (ramp to full productivity by month 5), price increase of 8% on new contracts starting month 4.

**Forecast (12 months):** Conservative $1.55M avg (1.5% growth, slow hire ramp, no price lift), Base $1.82M avg (3.5% + hire + partial price lift), Optimistic $2.1M avg (hire outperforms + full price lift + one large account expansion).

**Key driver:** The new sales hire is the primary scenario separator between conservative and base. Conservative assumes 4-month ramp; base assumes 3-month ramp.

## Anti-Patterns

- **Straight-line projections** — revenue rarely grows in a straight line. Account for seasonality, ramp-up periods, and plateaus.
- **Single-number forecasts** — always provide a range. A single number is either a lie or a guess.
- **Ignoring churn and cancellations** — for recurring revenue, model churn. Gross new revenue minus churn equals net revenue growth.
- **Forecasting without identifying drivers** — "revenue will grow 10%" is not a forecast. "4 new enterprise clients at $120K/year from the expanded sales team" is a forecast.
- **Over-optimism bias** — most leadership teams forecast 2-3x what actually happens. Use historical growth rates as the base, not aspirational targets.

## Recovery

- **Less than 3 months of data:** Use industry benchmarks and clearly label the forecast as preliminary. Update monthly as data accumulates.
- **Highly variable revenue:** Focus on trailing averages rather than month-to-month growth rates. Widen the gap between conservative and optimistic scenarios.
- **New revenue stream with no data:** Model it separately with a conservative ramp. Do not include it in the base case until you have 2-3 months of actual results.
- **Revenue declining:** Acknowledge the trend. Model scenarios for stabilization and recovery. Identify which specific actions change the trajectory and who owns them.
