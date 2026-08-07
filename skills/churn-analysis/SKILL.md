---
name: Churn Analysis and Retention Planning
description: "Analyzes customer or subscriber churn with cohort breakdowns, exit reason mapping, segment risk scoring, and a structured retention action plan — for organizations managing recurring revenue or subscription-based relationships."
allowed-tools: Read Write Glob
---

# Churn Analysis & Retention Planning

## Core Principle

CHURN IS A SYMPTOM, NOT THE DISEASE. EVERY CHURNED CUSTOMER HAD A MOMENT WHERE THE VALUE THEY RECEIVED DROPPED BELOW THE PRICE THEY PAID. FIND THAT MOMENT.

## Phase 1: Define the Churn Landscape

### Required Inputs

Ask the following:

1. What is the business model? (subscription, membership, retainer, repeat purchase)
2. What is the current churn rate? (monthly or annual)
3. How do customers cancel? (self-serve, email, account manager, they just stop paying)
4. Is there exit survey data or documented cancellation reasons?
5. What is the average customer lifetime and LTV?

**Minimum needed: questions 1 and 2. If churn rate is unknown, calculate it: customers lost this period ÷ customers at start of period.**

## Phase 2: Identify Churn Patterns

Analyze by segment:

| Segment | Typical Pattern | Root Cause |
|---------|----------------|------------|
| Early churn (0-30 days) | Never activated or engaged | Poor onboarding, unmet expectations |
| Mid-term churn (1-6 months) | Used it, then stopped | No ongoing value, found alternative |
| Long-term churn (6+ months) | Loyal then left suddenly | Price increase, bad experience, change in strategy |
| Seasonal churn | Predictable drop-offs | Budget cycles, seasonal relevance |
| Involuntary churn | Payment failures | Expired cards, insufficient funds |

## Phase 3: Build Warning Signals

| Warning Signal | Risk Level | Timeframe | Action |
|---------------|-----------|-----------|--------|
| No login or activity in 14 days | Medium | Trigger at day 14 | Re-engagement outreach |
| Support ticket unresolved 48+ hrs | High | Immediate | Escalate and follow up |
| Downgraded plan | High | Within 7 days | Account manager outreach |
| Usage dropped 50%+ from baseline | High | Weekly trigger | Value reminder + check-in call |
| Payment failed | Critical | Same day | Dunning sequence (3 contacts over 7 days) |
| Viewed cancellation page | Critical | Real-time | Retention offer or account manager contact |

## Phase 4: Build Retention Interventions

For each churn segment, build a targeted intervention:

**Early Churn Prevention:**
- Improve onboarding (guided setup, quick wins in first 48 hours)
- "Did you know?" communications highlighting unused features
- Assign onboarding owner or check-in call at day 7

**Mid-Term Retention:**
- Monthly value recaps ("Here is what your team accomplished this month")
- Feature announcements tied to the customer's use case
- Business reviews for key accounts

**Long-Term Loyalty:**
- Annual relationship reviews with senior stakeholders
- Early access to new capabilities or roadmap previews
- Proactive commercial discussions before renewal

**Involuntary Churn Recovery:**
- Pre-dunning: notify before billing date if card on file is expired
- Dunning sequence: 3 contacts over 7 days with direct update link
- Grace period: maintain access for 7 days after failed payment

## Phase 5: Deliver Churn Reduction Plan

Provide a prioritized action plan with expected impact per intervention, owner, and timeline.

## Example 1: B2B SaaS Platform (Annual Contracts, Mid-Market)

**Current State:** 18% annual churn (industry benchmark: 10-12%)

| Churn Segment | % of Total Churn | Primary Reason |
|--------------|-----------------|----------------|
| Early (0-90 days) | 40% | Slow implementation, low adoption at user level |
| Mid-term (3-9 months) | 35% | Champion left organization, no relationship depth |
| Late-term (9-12 months) | 15% | Budget consolidation at renewal |
| Involuntary | 10% | Administrative / billing issues |

**Priority Interventions:**

> **#1 — Deepen Implementation Support (target: reduce early churn by 50%)**
> - Assign a Customer Success Manager for all contracts above $30K ARR
> - Require a kickoff session with end-user team within 14 days of contract signing
> - Track adoption by user, not just by account — flag accounts below 40% seat activation at day 45
> - Expected impact: Reduce early churn from 40% to 20% of total, dropping overall churn to ~13%
>
> **#2 — Build Multi-Stakeholder Relationships**
> - Map at least 2 named contacts per account within 60 days
> - Conduct quarterly business reviews for all contracts above $20K ARR
> - Log relationship depth as a health score input
> - Expected impact: Reduce champion-departure churn by 30%

## Example 2: Professional Services Retainer Model

**Current State:** 22% annual churn across retained clients

**Top cancellation reasons (from exit interviews):**

| Reason | % | Intervention |
|--------|---|-------------|
| "We brought it in-house" | 30% | Position ongoing advisory alongside execution — reframe the retainer |
| "Not enough senior attention" | 25% | Require monthly senior partner touchpoint for retainers above EGP 50K/month |
| "Scope creep eroded value" | 20% | Formal scope review at 6 months for all retainers |
| "Budget cut" | 15% | Introduce tiered retainer structures — reduce scope, not relationship |
| Other | 10% | Exit interview, personal outreach |

## Anti-Patterns

- **Discounting as the primary retention strategy** — it trains customers to threaten cancellation for discounts. Fix the value gap, not the price.
- **Treating all churn the same** — early churn, mid-term churn, and involuntary churn have different root causes and different fixes. Segment before acting.
- **No baseline measurement** — without a churn rate tracked over time, no intervention can be evaluated. Start tracking now if not already.
- **Collecting exit data without acting on it** — if three customers cite the same issue and nothing changes, the data is noise.

## Recovery

- **No churn data exists:** Start tracking today — date, customer name, reason, last activity. Even 60 days of data reveals patterns.
- **Churn rate looks acceptable but revenue is declining:** Check for downgrades. Customers moving to smaller contracts is revenue churn even without customer churn.
- **No automated systems available:** Start with manual interventions. A personal call from a senior account owner to an at-risk customer costs nothing and has the highest save rate.
- **Churn is seasonal and predictable:** Front-load revenue with annual contracts, prepay structures, or multi-year pricing rather than fighting the cycle.
