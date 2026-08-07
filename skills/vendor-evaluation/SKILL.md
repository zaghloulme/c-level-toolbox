---
name: Vendor Evaluation
description: "Creates structured vendor and supplier comparison matrices with weighted scoring, total cost of ownership analysis, and recommendation summaries — for procurement decisions involving multiple candidates across software, services, or physical suppliers."
allowed-tools: Read Write Glob
---

# Vendor Evaluation

## Core Principle

A VENDOR EVALUATION IS ONLY VALUABLE WHEN IT PRODUCES A CLEAR RECOMMENDATION WITH VISIBLE MATH — NEVER PRESENT A COMPARISON WITHOUT WEIGHTED SCORES AND A TOTAL COST OF OWNERSHIP CALCULATION.

---

## Evaluation Types

Every evaluation falls into one of these categories, which determines the default criteria:

| Type | Examples | Default Criteria Focus |
|------|----------|----------------------|
| **Software/SaaS** | CRMs, ERP systems, project management, collaboration tools | Features, pricing tiers, integrations, ease of use, scalability |
| **Agency/Service Provider** | Marketing agencies, consulting firms, legal or accounting firms | Portfolio quality, communication, pricing model, turnaround, specialization |
| **Contractor/Freelancer** | Specialists, developers, designers, consultants | Relevant experience, rate, availability, communication, portfolio |
| **Physical Vendor/Supplier** | Manufacturers, distributors, logistics providers, equipment vendors | Unit cost, quality, lead time, minimum order, reliability |

---

## Step 1: Understand

Gather these inputs before building any comparison. Ask all questions at once to minimize back-and-forth.

1. **What are you buying?** — software, service, contractor, or physical product/supply
2. **What problem does this solve?** — the specific need driving the purchase
3. **Budget range** — total or per-period budget, even approximate
4. **Must-have requirements** — dealbreakers that eliminate a vendor immediately
5. **Nice-to-have features** — important but not dealbreakers
6. **Candidates** — the 2-5 vendors or tools being considered, by name
7. **Current solution** — what is in use now, if anything, and why it is not working
8. **Team size** — how many people will use this tool or work with this vendor
9. **Decision timeline** — when the decision needs to be made

**If the user provides items 1, 6, and at least one must-have requirement, proceed with reasonable defaults for the rest.** Ask only about missing critical details.

**Brief template to present if the user gives a vague request:**

```
I will build a structured vendor evaluation for you. Quick answers needed:

1. What are you buying? (software, service provider, contractor, supplier)
2. What problem are you solving?
3. Budget range? (even approximate helps)
4. Dealbreaker requirements? (things a vendor MUST have or they are out)
5. Which vendors are you comparing? (2-5 names)
6. What do you use now, and why is it not working?
7. How many people will use this?
```

**GATE: Do not proceed to Step 2 until you have: the evaluation type, at least 2 named candidates, and at least 1 must-have requirement. If the user cannot name candidates, suggest 3-4 well-known options in the category and ask them to confirm.**

---

## Step 2: Evaluate

Build three analysis components. Complete all three before presenting anything to the user.

### 2A: Weighted Scoring Matrix

Select 5-7 criteria from the table below based on the evaluation type and user priorities. **Do not use more than 7 criteria — analysis paralysis makes the evaluation unusable.**

**Criteria Reference:**

| Criterion | Applies To | What to Score |
|-----------|-----------|---------------|
| **Core Features** | All types | Does it solve the stated problem? Coverage of must-haves and nice-to-haves |
| **Pricing/Cost** | All types | Affordability relative to budget and value delivered |
| **Ease of Use** | Software, Services | Setup time, learning curve, day-to-day usability |
| **Support Quality** | Software, Services | Response time, channels available, documentation quality |
| **Scalability** | Software, Suppliers | Can it grow with the business? Pricing at 2x and 5x current usage |
| **Integration** | Software | Connects with existing tools and systems |
| **Reputation/Track Record** | All types | Reviews, references, years in business, client stability |

**Weighting rules:**
- Assign each criterion a weight from 1 (low priority) to 5 (critical priority)
- Must-have requirements always get weight 5
- The user's stated top priority gets weight 5
- Remaining criteria distribute across 2-4 based on relevance
- **NEVER weight all criteria equally — that defeats the purpose of weighting**

**Scoring rules:**
- Score each vendor 1-5 on each criterion
- 1 = poor/missing, 2 = below average, 3 = adequate, 4 = good, 5 = excellent
- Calculate weighted score per criterion: score x weight
- Sum weighted scores for each vendor to get the total

**Matrix format:**

```
| Criterion | Weight | Vendor A | Vendor B | Vendor C |
|-----------|--------|----------|----------|----------|
| Core Features | 5 | 4 (20) | 5 (25) | 4 (20) |
| Pricing | 4 | 4 (16) | 2 (8) | 5 (20) |
| Ease of Use | 4 | 5 (20) | 3 (12) | 4 (16) |
| Support | 3 | 4 (12) | 3 (9) | 3 (9) |
| Scalability | 3 | 3 (9) | 5 (15) | 4 (12) |
| Integration | 4 | 4 (16) | 5 (20) | 3 (12) |
| Reputation | 2 | 4 (8) | 5 (10) | 3 (6) |
| **TOTAL** | **25** | **101** | **99** | **95** |
```

### 2B: Cost Analysis

Build a cost comparison that goes beyond the sticker price. Calculate for both 1-year and 3-year horizons.

**Cost components to capture:**

| Component | Description |
|-----------|-------------|
| **Base cost** | Monthly or annual subscription / project fee / unit cost |
| **Per-user cost** | Additional cost per seat or team member |
| **Onboarding cost** | Setup fees, migration, training |
| **Add-on costs** | Features that cost extra beyond the base |
| **Migration cost** | Cost to switch from the current solution |
| **Scaling cost** | What the price becomes at 2x current usage |

**Cost table format:**

```
| Cost Component | Vendor A | Vendor B | Vendor C |
|----------------|----------|----------|----------|
| Base (monthly) | [amount] | [amount] | [amount] |
| Per-user add-on | [amount] | [amount] | [amount] |
| Onboarding | [amount] | [amount] | [amount] |
| Add-ons needed | [amount] | [amount] | [amount] |
| Migration estimate | [amount] | [amount] | [amount] |
| **Year 1 total** | **[amount]** | **[amount]** | **[amount]** |
| **Year 3 total** | **[amount]** | **[amount]** | **[amount]** |
| At 2x scale (monthly) | [amount] | [amount] | [amount] |
```

**If exact pricing is unavailable** (common for agencies and enterprise vendors): use the user's budget range or known quotes. Mark estimates clearly with "(est.)" and note which figures are confirmed versus projected.

### 2C: Pros/Cons and Risk Assessment

For each vendor, produce:

**Pros/Cons** — 3-4 bullets each, specific to the user's situation (not generic marketing copy):

```
## Vendor A

**Pros:**
- [Specific strength relevant to this evaluation]
- [Specific strength]
- [Specific strength]

**Cons:**
- [Specific weakness relevant to this evaluation]
- [Specific weakness]
- [Specific weakness]
```

**Risk Assessment** per vendor:

| Risk Factor | What to Evaluate |
|-------------|-----------------|
| **Vendor stability** | How long have they been in business? Funded or profitable? Any instability signals? |
| **Lock-in concern** | How hard is it to leave? Can data be exported? Are there proprietary formats? |
| **Migration difficulty** | LOW (export/import in hours), MEDIUM (requires manual re-setup), HIGH (significant rebuild required) |

---

## Step 3: Present

Deliver the evaluation in this exact order. Present everything before saving anything.

### Presentation Order

**1. Evaluation Summary** — one paragraph stating the candidates, the evaluation type, and the user's top priorities.

**2. Weighted Scoring Matrix** — full table with scores, weighted scores in parentheses, and totals.

**3. Cost Comparison Table** — all cost components, Year 1 total, Year 3 total, and at-scale pricing.

**4. Vendor Profiles** — pros/cons and risk assessment for each vendor.

**5. Recommendation:**

```
## Recommendation

### Top Pick: [Vendor]
**Weighted Score: [X/Y] | Year 1 Cost: [Amount]**

[2-3 sentences explaining why this vendor wins on the criteria that matter most.
Cite specific scores and what they mean for the user's actual situation.]

### Runner-Up: [Vendor]
**Weighted Score: [X/Y] | Year 1 Cost: [Amount]**

[2-3 sentences explaining where this vendor is strong and when to prefer it
over the top pick — the conditions under which it becomes the right choice.]

### Not Recommended for This Use Case: [Vendor]
**Weighted Score: [X/Y] | Year 1 Cost: [Amount]**

[1-2 sentences explaining why this vendor did not make the cut, and whether
there are other use cases where it would be appropriate.]
```

**6. Suggested Next Steps:**

```
## Suggested Next Steps

1. [Specific pilot or trial action for the top pick]
2. [Validation step — what to test during the pilot]
3. [Decision deadline and fallback]
4. [When to re-evaluate]
```

**GATE: Present the full evaluation and ask the user to review before saving. Offer to adjust any scores, weights, or the recommendation.**

---

## Step 4: Act

Save the evaluation based on the user's preference.

### Save the Evaluation

1. Write the full evaluation to a markdown file using the Write tool
2. Default filename: `vendor-evaluation-[category].md` — ask for a preferred path if the user specifies one
3. Include all sections: scoring matrix, cost analysis, vendor profiles, recommendation, next steps

Confirm the file path after saving.

### Decision Summary for Stakeholders

If the user needs to share the decision with a leadership team or board:

```
## Decision Summary: [Category]

**Decision:** [Action + chosen vendor]
**Evaluated:** [All candidates] | **Date:** [Today]
**Why [Winner]:** [3-4 bullet points citing scores and costs]
**Key tradeoff:** [One sentence on what was given up]
**Next step:** [Pilot details with date]
```

### Suggest Trial/Pilot Approach

Regardless of save format, close with a structured pilot: test the top pick's core workflows against the user's must-have requirements, migrate a limited data subset or run a limited engagement, and set a decision deadline with the runner-up as an explicit fallback.

---

## Anti-Patterns

- **DO NOT recommend a vendor without showing the scoring math.** A recommendation without visible criteria and scores is just an opinion.
- **DO NOT weight all criteria equally.** Equal weights eliminate the purpose of a weighted evaluation. Push the user to prioritize.
- **DO NOT ignore total cost of ownership.** The cheapest base price is not always the cheapest solution. Onboarding, migration, and scaling costs change the picture.
- **DO NOT present more than 7 evaluation criteria.** Beyond 7, the matrix becomes noise.
- **DO NOT fabricate pricing, feature availability, or review scores.** Mark uncertain data with "(est.)" or "(unverified)."
- **DO NOT skip the runner-up recommendation.** The top pick might fail during the pilot. The user needs a ready fallback.
- **DO NOT present the recommendation before the scoring matrix and cost analysis.** Data before conclusion.
- **DO NOT evaluate vendors the user did not ask about.** If a strong candidate is missing, mention it as a note after the evaluation.
- **DO NOT save to file before the user reviews and approves the evaluation.** Present first, save second.

---

## Recovery and Troubleshooting

### User Names Only 1 Candidate

1. Ask: "A vendor evaluation works best with at least 2 options to compare. Who else is under consideration, or would you like suggestions in this category?"
2. Suggest 2-3 well-known options based on the evaluation type and budget range
3. If the user truly wants to evaluate just 1 vendor: reframe as a vendor audit. Score the single vendor against the criteria and provide a go/no-go recommendation with a threshold score.

### Pricing Information Is Unavailable

1. Check the vendor's public pricing page for published rates
2. If pricing is behind "Contact Sales": mark cost as "Quote required" and score the pricing criterion at 3 (neutral)
3. If the user has received quotes, use those exact figures
4. **Do not fabricate pricing.** A cost analysis with honest gaps is more useful than one with invented numbers.

### Must-Have Requirement Eliminates a Candidate

1. Score the eliminated vendor normally on all other criteria but assign 0 on the must-have criterion
2. Mark clearly in the matrix: "[Vendor]: 0 (MISSING: [requirement])"
3. Include the vendor in the final presentation with a note explaining disqualification
4. If all candidates except one are eliminated: inform the user and ask if they want to relax any must-haves or add more candidates

### Scores Are Too Close to Call

If two vendors are within 5 points of each other on the weighted total:
1. Flag the tie explicitly: "[Vendor A] and [Vendor B] are within the margin of uncertainty."
2. Break the tie with cost analysis: lower total cost of ownership wins the tiebreak
3. If cost is also similar: break on the highest-weight criterion
4. If still tied: recommend both for a head-to-head pilot

### User Disagrees with the Recommendation

1. Do not defend the recommendation. Ask: "Which vendor do you prefer, and what criteria am I underweighting?"
2. Adjust the weights based on feedback and recalculate
3. If the user overrides the data: note it in the recommendation with the stated reason

---

## Pre-Delivery Checklist

Before delivering the final evaluation, verify:

- [ ] Weighted scoring matrix has 5-7 criteria with non-equal weights
- [ ] Every score has a weighted value shown in parentheses
- [ ] Cost analysis includes Year 1 total, Year 3 total, and at-scale pricing
- [ ] Hidden costs (onboarding, migration, add-ons) are accounted for
- [ ] Each vendor has a pros/cons section with specific, non-generic bullets
- [ ] Risk assessment covers vendor stability, lock-in, and migration difficulty
- [ ] Recommendation names a top pick AND a runner-up with reasoning
- [ ] Recommendation cites specific scores and costs, not just opinions
- [ ] Trial/pilot approach is suggested for the top pick
- [ ] No fabricated pricing or feature claims — uncertain data is marked
- [ ] Decision summary is ready if the user needs to share with stakeholders
- [ ] No placeholder text like [TBD] remains in the final output
