---
name: ROI Calculator
version: 1.4.0
description: "Builds ROI analyses for business investment decisions — tools, hires, campaigns, infrastructure — with cost breakdown, benefit quantification, payback period, and a clear go/no-go recommendation."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# ROI Calculator

## Core Principle

ROI IS A DECISION TOOL — THE GOAL IS NOT PRECISION BUT CLARITY ON WHETHER AN INVESTMENT IS WORTH MAKING AND HOW LONG UNTIL IT PAYS FOR ITSELF.

## Phase 1: Investment Context

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Investment description** | "What are you considering investing in? (system, hire, campaign, infrastructure)" | No default — must be provided |
| **Total cost** | "What is the total cost? (upfront + ongoing monthly/annual)" | No default — must be provided |
| **Time horizon** | "Over what period should we measure ROI? (6 months, 1 year, 2 years)" | 12 months |
| **Expected benefits** | "What do you expect to gain? (revenue, time saved, cost reduction, risk reduction)" | No default — must be provided |
| **Current baseline** | "What is the current state without this investment?" | No default — describe current process/cost |

**GATE: Do not proceed without the investment cost and expected benefits.**

## Phase 2: Cost Analysis

```
## Investment Cost Breakdown

### Upfront Costs
| Item | Cost | Notes |
|------|------|-------|
| [Purchase/setup fee] | $[X] | One-time |
| [Implementation/training] | $[X] | One-time |
| [Migration/switching costs] | $[X] | One-time |
| **Total Upfront** | **$[X]** | |

### Ongoing Costs (Monthly)
| Item | Monthly Cost | Annual Cost |
|------|-------------|-------------|
| [Subscription/license] | $[X] | $[X] |
| [Maintenance/support] | $[X] | $[X] |
| [Additional labor] | $[X] | $[X] |
| **Total Monthly** | **$[X]** | **$[X]** |

### Total Cost of Ownership ([X]-Month Horizon)
| | Amount |
|--|--------|
| Upfront costs | $[X] |
| + Ongoing costs ([X] months) | $[X] |
| **= Total investment** | **$[X]** |
```

## Phase 3: Benefit Quantification

```
## Benefit Analysis

### Revenue Benefits
| Benefit | Monthly Value | Annual Value | Confidence |
|---------|-------------|-------------|------------|
| [New revenue enabled] | $[X] | $[X] | High/Med/Low |
| [Revenue increase from efficiency] | $[X] | $[X] | High/Med/Low |

### Cost Savings
| Benefit | Monthly Savings | Annual Savings | Confidence |
|---------|----------------|----------------|------------|
| [Tool/service replaced] | $[X] | $[X] | High |
| [Reduced labor costs] | $[X] | $[X] | Med |

### Time Savings
| Task | Hours Saved/Month | Value (hrs x rate) | Annual Value |
|------|------------------|-------------------|-------------|
| [Task 1] | [X] hrs | $[X] | $[X] |
| [Task 2] | [X] hrs | $[X] | $[X] |

### Total Benefits
| Category | Monthly | Annual |
|----------|---------|--------|
| Revenue benefits | $[X] | $[X] |
| Cost savings | $[X] | $[X] |
| Time savings value | $[X] | $[X] |
| **Total benefits** | **$[X]** | **$[X]** |
```

## Phase 4: ROI Calculation and Decision

```
## ROI Summary

### Core Metrics
| Metric | Value |
|--------|-------|
| Total investment ([X] months) | $[X] |
| Total benefits ([X] months) | $[X] |
| Net return | $[X] |
| **ROI percentage** | **[X]%** |
| Payback period | [X] months |
| Monthly net benefit (after payback) | $[X] |

### ROI Formula
ROI = (Total Benefits - Total Investment) / Total Investment x 100

### Payback Timeline
| Month | Cumulative Cost | Cumulative Benefit | Net Position |
|-------|----------------|-------------------|-------------|
| Month 1 | $[X] | $[X] | -$[X] |
| Month 3 | $[X] | $[X] | -$[X] |
| Month 6 | $[X] | $[X] | +/-$[X] |
| Month 12 | $[X] | $[X] | +$[X] |

### Decision Framework
| ROI Range | Recommendation |
|-----------|---------------|
| Over 200% | Strong yes — invest immediately |
| 100-200% | Yes — solid return, proceed |
| 50-100% | Likely yes — if strategic alignment exists |
| 0-50% | Requires scrutiny — consider alternatives |
| Negative | No — unless strategic value justifies it |

### Recommendation
[Clear recommendation based on the numbers with key caveats]
```

## Example: ERP System Upgrade

**Investment:** $180,000 implementation cost, $4,500/month licensing. 12-month horizon total: $234,000.

**Benefits:** Replaces 3 legacy systems ($8,200/month, $98,400/year). Eliminates manual reconciliation (6 staff each saving 5 hours/month at $65/hour = $23,400/year). Faster close cycle enables earlier cash collection estimated at $35,000/year in reduced DSO.

**ROI:** ($156,800 - $234,000) / $234,000 = -33% at 12 months. Payback period: 22 months. 24-month ROI: +8.9%.

**Recommendation:** Negative 12-month ROI but positive at 22 months. If the ERP is expected to run for 5+ years, the full-term ROI is +74% (using the same formula: total benefits $784K minus total investment $450K over 5 years, divided by $450K). Proceed, but negotiate payment terms to defer the implementation fee to month 3 to smooth cash impact.

## Anti-Patterns

- **Only counting hard dollar returns** — time savings, risk reduction, and improved capacity are real benefits. Quantify them.
- **Ignoring switching costs** — migration, training, and productivity loss during transition are real costs.
- **Overconfident benefit projections** — use conservative estimates. If ROI works on conservative numbers, it works in practice.
- **Comparing against doing nothing** — sometimes the alternative is not "do nothing" but "do something different." Compare against the best alternative.
- **No defined time horizon** — an investment that takes 5 years to pay back on a tool you may replace in 3 years is a bad deal.

## Recovery

- **Benefits are hard to quantify:** Assign a conservative dollar value to intangible benefits. "Better compliance posture" = reduced fine risk = $X. "Faster reporting" = leadership time savings = $X.
- **Multiple options to compare:** Build a side-by-side table with ROI for each option and recommend the highest ROI with acceptable risk and implementation complexity.
- **ROI is negative but investment feels necessary:** Identify the minimum benefit needed to break even and assess whether that is realistic. Some investments are strategic even with negative short-term ROI — state that explicitly.
- **No baseline data:** Estimate the current cost of the problem being solved. Validate with the people doing the work before presenting to decision-makers.
