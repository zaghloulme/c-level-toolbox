---
name: Pricing Analysis and Optimization
version: 1.1.0
description: "Analyzes pricing effectiveness through competitor benchmarking, value metric alignment, and price sensitivity assessment — then models revenue impact of proposed changes before implementation."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Pricing Analysis

## Core Principle

PRICE BASED ON VALUE DELIVERED, NOT COST INCURRED — YOUR PRICE SHOULD REFLECT WHAT THE CUSTOMER GAINS, NOT WHAT IT COSTS YOU TO DELIVER.

## Phase 1: Brief

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Product/service** | "What are you pricing?" | Must be provided |
| **Current price** | "What do you charge now?" | Must be provided |
| **Pricing model** | "One-time, subscription, per-unit, tiered, usage-based?" | Must be provided |
| **Competitors** | "Who are your top 3 competitors and what do they charge?" | Will request |
| **Customer feedback** | "Have customers commented on price? (too high, fair, would pay more)" | No direct feedback |
| **Goal** | "What are you optimizing for? (revenue, volume, market share, margin)" | Revenue maximization |

**GATE: Confirm brief before proceeding.**

## Phase 2: Analyze

### Analysis Framework

1. **Competitive positioning** — where you sit relative to competitors (premium, mid-market, budget)
2. **Value metric alignment** — does your pricing scale with the value customers receive?
3. **Price sensitivity indicators** — signals from conversion rates, objections, or win/loss data
4. **Willingness to pay estimation** — Van Westendorp or comparable framework
5. **Margin analysis** — gross margin at current price and at proposed alternatives

### Competitive Benchmark Table

| Competitor | Price | Model | Key Differentiator |
|-----------|-------|-------|-------------------|
| Competitor A | $X/mo | Subscription | [Feature X] |
| Competitor B | $Y | Annual license | [Community, integrations] |
| You | $Z/mo | Subscription | [Your differentiator] |

**GATE: Present analysis findings and wait for direction before making recommendations.**

## Phase 3: Build

### Deliverables

**1. Pricing Analysis Report**
- Competitive benchmark with positioning map
- Current pricing strengths and weaknesses
- Price sensitivity assessment
- Revenue impact estimates for proposed changes

**2. Pricing Recommendations**
- 2-3 pricing options with projected outcomes
- Tier structure recommendations (if applicable)
- Bundling or packaging suggestions
- Implementation approach (grandfather existing, phase in, immediate)

**3. Price Change Impact Model**
- Scenario table: price x estimated volume = projected revenue
- Conservative, base, and optimistic scenarios
- Break-even analysis: how many customers can you lose before the increase hurts?

**4. Communication Plan**
- How to announce price changes to existing customers
- Messaging framework that leads with value, not cost
- Grandfather policy recommendations
- FAQ for customer-facing team

## Phase 4: Polish

### Testing Recommendations

- A/B test pricing page if traffic allows
- Offer the new price to new customers first, keep existing customers on current plan
- Survey customers with "Would you pay $X for this?" before committing

### Review Cadence

Reassess pricing every 6-12 months as value delivered, costs, and competitive landscape evolve.

## Example 1: B2B Platform ($1,200/year, considering increase)

**Finding:** Competitors charge $1,800-$4,800/year for comparable platforms. Current price signals "entry-level tool" and attracts price-sensitive buyers who churn faster.
**Recommendation:** Increase to $2,400/year for new customers, grandfather existing at $1,200 for 18 months. Expected: 12% volume decrease on new sales, 76% net revenue increase (88 customers × $2,400 = $211,200 vs. 100 × $1,200 = $120,000 baseline). Churn rate expected to improve as price-sensitive cohort is replaced.

## Example 2: Professional Services Retainer ($15K/month, considering tiers)

**Finding:** Single price forces small-team and enterprise clients into the same engagement structure, with enterprise clients consistently asking for more scope.
**Recommendation:** Three tiers — Core ($10K), Growth ($18K), Enterprise ($32K) — with clear scope differentiation. Expected 40% revenue increase from upsell capture within 12 months.

## Anti-Patterns

- **Cost-plus pricing** — adding a margin to your costs ignores what customers value. A solution that costs $5,000 to deliver may be worth $50,000 to the buyer.
- **Copying competitor prices** — your differentiation should justify different pricing. Copy the model, not the number.
- **Fear of raising prices** — if nobody complains about your price, it is probably too low. 15-25% of prospects should find you too expensive.
- **Too many tiers** — 3 tiers maximum. More creates decision paralysis.
- **Never testing** — set a price, test it, adjust. Pricing is iterative.

## Recovery

- **No competitor data:** Use industry benchmarks, comparable products in adjacent categories, or customer willingness-to-pay surveys.
- **Customers say price is too high:** Investigate whether it is a price problem or a value communication problem. Often the proposal or onboarding is the issue, not the price itself.
- **Pricing is genuinely complex:** Simplify first. If you cannot explain your pricing in 30 seconds, customers cannot evaluate it.
- **Existing customers push back on increase:** Lead with value, grandfather generously, and be transparent about timing.
