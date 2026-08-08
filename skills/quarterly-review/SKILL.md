---
name: Quarterly Business Review
version: 1.4.0
description: "Creates quarterly business review documents with metric analysis, goal tracking against OKRs, wins and challenge debrief, and a prioritized plan for the next quarter."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Quarterly Review

## Core Principle

A QUARTERLY REVIEW IS NOT A REPORT CARD — IT IS A STRATEGIC RECALIBRATION. THE GOAL IS TO DECIDE WHAT TO DO NEXT, NOT JUST DOCUMENT WHAT HAPPENED.

## Phase 1: Gather Data

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Quarter** | "Which quarter are you reviewing? (Q1, Q2, Q3, Q4 + year)" | Previous quarter |
| **Goals set for this quarter** | "What were your goals or OKRs for this quarter?" | No default — must be provided |
| **Key metrics** | "What are your core business metrics? (revenue, customers, growth, utilization)" | Revenue, customers, profit |
| **Revenue this quarter** | "What was total revenue this quarter?" | No default — must be provided |
| **Biggest wins** | "What were the top 3 wins this quarter?" | No default — must be provided |
| **Biggest challenges** | "What were the top 3 challenges or shortfalls?" | No default — must be provided |

**GATE: Do not proceed without quarterly goals and actual results.**

## Phase 2: Performance Review

```
## Quarterly Business Review: [Q# Year]

### Goal Scorecard
| Goal | Target | Actual | Status | Notes |
|------|--------|--------|--------|-------|
| [Goal 1] | [Target] | [Actual] | Hit / Missed / Partial | [Context] |
| [Goal 2] | [Target] | [Actual] | Hit / Missed / Partial | |
| [Goal 3] | [Target] | [Actual] | Hit / Missed / Partial | |

**Goals hit:** [X] of [X] ([X]%)

### Financial Summary
| Metric | This Quarter | Last Quarter | QoQ Change | YTD |
|--------|-------------|-------------|-----------|-----|
| Revenue | $[X] | $[X] | +/-[X]% | $[X] |
| Expenses | $[X] | $[X] | +/-[X]% | $[X] |
| Net profit | $[X] | $[X] | +/-[X]% | $[X] |
| Profit margin | [X]% | [X]% | +/-[X]pp | [X]% |
| Customers/clients | [X] | [X] | +/-[X]% | |
| [Key metric] | [X] | [X] | +/-[X]% | |

### Monthly Breakdown
| | Month 1 | Month 2 | Month 3 | Quarter Total |
|--|---------|---------|---------|--------------|
| Revenue | $[X] | $[X] | $[X] | $[X] |
| Expenses | $[X] | $[X] | $[X] | $[X] |
| Net profit | $[X] | $[X] | $[X] | $[X] |
```

## Phase 3: Analysis

### What Worked

```
## Wins and Insights

### Top 3 Wins
1. **[Win]** — [What happened, quantified impact, why it worked]
2. **[Win]** — [Description and impact]
3. **[Win]** — [Description and impact]

### Key Insights
- [Insight about customers, market, or operations learned this quarter]
- [Insight]
```

### What Did Not Work

```
## Challenges and Lessons

### Top 3 Challenges
1. **[Challenge]** — [What happened, impact, root cause]
2. **[Challenge]** — [Description and root cause]
3. **[Challenge]** — [Description and root cause]

### Lessons Learned
- [Lesson — what changes next quarter?]
- [Lesson]
```

### Strategic Questions

```
## Strategic Assessment

1. Are we focused on the right priorities?
2. What should we START doing next quarter?
3. What should we STOP doing next quarter?
4. What should we CONTINUE doing next quarter?
5. Is our current strategy still the right one given what we learned?
```

## Phase 4: Next Quarter Plan

```
## [Next Quarter] Priorities

### Top 3 Goals
| Goal | Target | Metric | Owner | Deadline |
|------|--------|--------|-------|----------|
| [Goal 1] | [Specific target] | [How measured] | [Who] | [Date] |
| [Goal 2] | [Specific target] | [How measured] | [Who] | [Date] |
| [Goal 3] | [Specific target] | [How measured] | [Who] | [Date] |

### Key Initiatives
1. **[Initiative]** — [What, why, expected impact]
2. **[Initiative]** — [What, why, expected impact]
3. **[Initiative]** — [What, why, expected impact]

### Resource Allocation Changes
- [Any budget shifts, new hires, tool changes, or process improvements]

### Risks to Monitor
- [Risk 1] — Mitigation: [Plan]
- [Risk 2] — Mitigation: [Plan]
```

## Example: Regional Operations Division Q4 Review

**Goals:** 1) Hit $1.8M quarterly revenue (Actual: $1.74M — 97%), 2) Reduce delivery cycle time by 15% (Actual: 11% — partial), 3) Expand to two new enterprise accounts (Done — 2 signed, 1 in final negotiation).

**Key win:** Both new enterprise accounts closed with 12-month contracts at $85K and $110K annually — ahead of the $75K average target.

**Key challenge:** Delivery cycle improvement stalled at 11% because the process change required a system configuration that IT has not completed. Plan for Q1: escalate to CIO with a timeline, and identify a manual workaround if the system change slips past week 6.

**Q1 priorities:** Hit $1.95M revenue, complete system configuration to achieve the remaining 4% cycle time improvement, onboard both new enterprise accounts with a formal 30-day success plan.

## Anti-Patterns

- **Skipping the review when things are bad** — the worst quarters need the most analysis, not avoidance.
- **All numbers, no narrative** — metrics without interpretation are just data. Explain what drove the numbers.
- **Setting the same goals after missing them** — if a goal was missed, analyze why. Either adjust the goal, change the approach, or remove it.
- **Too many goals** — 3-5 goals per quarter maximum. More dilutes focus and makes accountability murky.
- **No owners on next quarter's goals** — every goal needs a person responsible for it, not a committee.

## Recovery

- **No goals were set last quarter:** Use this review to establish a baseline. Set 3 goals for next quarter and commit to reviewing them.
- **Difficult quarter (most goals missed):** Focus on root causes, not symptoms. One bad quarter is a data point. Two in a row is a pattern that needs a strategic change.
- **No financial tracking in place:** Reconstruct from ERP or bank statements. Set up proper tracking before next quarter starts.
- **Distributed team with no shared view:** Run the review asynchronously — collect input from each function head and synthesize into the QBR document before the live discussion.
