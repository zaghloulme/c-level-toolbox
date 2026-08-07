---
name: Risk Assessment
version: 1.7.5
description: "Conducts business risk assessments with likelihood and impact scoring, mitigation strategies, early warning indicators, and monitoring plans — for leadership teams managing operational, financial, market, and compliance exposure."
---

# Risk Assessment

## Core Principle

RISK MANAGEMENT IS NOT ABOUT ELIMINATING RISK — IT IS ABOUT KNOWING WHICH RISKS ARE WORTH TAKING AND HAVING A PLAN FOR THE ONES THAT COULD THREATEN THE BUSINESS.

## Phase 1: Identify

Surface all relevant risks before scoring them.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Business context** | "Describe the organization and what prompted this assessment." | No default — must be provided |
| **Assessment trigger** | "Why now? (new initiative, annual review, specific concern, board requirement)" | Annual review |
| **Revenue model** | "How does the organization generate revenue? (services, products, subscriptions, contracts)" | No default |
| **Dependencies** | "What does the business depend on most? (key clients, platforms, suppliers, regulators)" | No default |
| **Known risks** | "What risks are already on the radar?" | No default |

### Risk Categories

Walk through each category to ensure comprehensive coverage:

- **Financial:** Cash flow, revenue concentration, currency exposure, debt covenants
- **Operational:** Key person dependency, system failures, process breakdowns, supply chain
- **Market:** Competition, demand shifts, economic conditions, pricing pressure
- **Legal/Compliance:** Contracts, regulatory requirements, IP, liability exposure
- **Reputational:** Brand damage, client disputes, media exposure, public perception
- **Technology:** Platform dependency, data loss, cybersecurity, system outages

```
## Risk Register

| # | Risk | Category | Description |
|---|------|----------|-------------|
| R1 | [Risk name] | [Category] | [What could happen and how] |
| R2 | [Risk name] | [Category] | [What could happen and how] |
```

**GATE: Confirm the risk register is complete before scoring.**

## Phase 2: Score

Assess each risk using likelihood and impact scoring.

### Scoring Matrix

Rate each risk 1-5 on both dimensions:

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 1 | Rare (less than 5% chance) | Negligible (minor inconvenience) |
| 2 | Unlikely (5-20%) | Minor (temporary disruption) |
| 3 | Possible (20-50%) | Moderate (significant effort to recover) |
| 4 | Likely (50-80%) | Major (serious financial or operational damage) |
| 5 | Almost certain (80%+) | Catastrophic (business survival threatened) |

```
## Risk Scoring

| # | Risk | Likelihood | Impact | Risk Score | Priority |
|---|------|-----------|--------|-----------|----------|
| R1 | [Name] | [1-5] | [1-5] | [L x I] | [Critical/High/Medium/Low] |

**Priority thresholds:**
- Critical: 15-25 — Immediate action required
- High: 10-14 — Mitigation plan needed within 30 days
- Medium: 5-9 — Monitor and prepare contingency
- Low: 1-4 — Accept and review quarterly
```

### Risk Heat Map

Present a visual summary:

```
         Impact →
         1    2    3    4    5
    5  | M  | H  | C  | C  | C  |
L   4  | L  | M  | H  | C  | C  |
i   3  | L  | M  | M  | H  | C  |
k   2  | L  | L  | M  | M  | H  |
e   1  | L  | L  | L  | L  | M  |
```

**GATE: Review scored risks before building mitigation plans.**

## Phase 3: Mitigate

Create action plans for high and critical risks.

### Mitigation Strategy Template

For each critical and high-priority risk:

```
## Mitigation Plan: [Risk Name]

**Risk score:** [X] (Likelihood [X] x Impact [X])
**Risk owner:** [Name and role]

**Prevention (reduce likelihood):**
- [Action to prevent the risk from occurring]
- [Action]

**Preparation (reduce impact):**
- [Action to minimize damage if it occurs]
- [Action]

**Response (if it happens):**
1. [Immediate action]
2. [Short-term recovery step]
3. [Long-term recovery step]

**Early warning indicators:**
- [Sign that this risk is becoming more likely]
- [Metric to monitor]

**Review frequency:** [Monthly / Quarterly]
```

### Common Organizational Mitigations

| Risk | Common Mitigation |
|------|-------------------|
| Revenue concentration (1-2 large clients) | Diversify: no single client should exceed 30% of revenue |
| Key person dependency | Document processes, cross-train backups, build bench capacity |
| Platform or vendor dependency | Maintain alternative channels, export data regularly, dual-source where possible |
| Cash flow exposure | Maintain 3-month operating reserve, enforce payment terms, monitor DSO |

## Phase 4: Monitor

Set up ongoing risk monitoring.

### Risk Dashboard

```
## Risk Dashboard — [Quarter/Year]

| Risk | Score | Status | Last Reviewed | Next Review | Owner |
|------|-------|--------|--------------|-------------|-------|
| [Name] | [X] | Stable / Increasing / Decreasing | [Date] | [Date] | [Name] |
```

### Review Cadence

- **Monthly:** Review critical and high risks — any changes in likelihood or impact?
- **Quarterly:** Full risk register review — add new risks, retire resolved ones, re-score existing ones
- **After any incident:** Update the affected risk's score and mitigation plan immediately

### Risk Appetite Statement

Define the organization's risk tolerance:

```
**Risk appetite:**
- We ACCEPT risks scored 1-4 (Low) without active mitigation
- We MITIGATE risks scored 5-14 (Medium-High) with documented plans
- We AVOID or TRANSFER risks scored 15-25 (Critical) — these threaten business continuity
```

## Anti-Patterns

- **Ignoring low-probability, high-impact risks** — "It will never happen" is not a strategy. Critical risks need plans even when unlikely.
- **Risk register as a one-time exercise** — risks change as the business changes. A static register gives a false sense of security.
- **No risk owner** — unowned risks are unmanaged risks. Every risk needs one accountable person.
- **Mitigation without monitoring** — a plan that is not tracked cannot be verified as working.
- **Scoring too many risks** — do not register 50 risks. Focus on the top 10-15 that have real operational significance.

## Recovery

- **Cannot identify risks:** Walk through each category with specific prompts: "What happens if the largest client exits tomorrow?" "What if the primary system goes down for a week?"
- **Everything scores as critical:** Recalibrate — compare each risk against "business cannot operate tomorrow." Only genuine existential threats are 5/5.
- **Leadership wants to dismiss risks:** Focus on the single risk that concerns them most. One solid mitigation plan builds the practice.
- **Risk has already materialized:** Switch to incident response. Document what happened, stabilize, then update the assessment with lessons learned.
- **Team is overwhelmed:** Start with the top 3 risks only. A plan for 3 risks is better than no plan for 20.
