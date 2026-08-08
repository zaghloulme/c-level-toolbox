---
name: SWOT Analysis with Strategic Action Plan
version: 3.4.5
description: "Conducts structured SWOT analyses with prioritized strengths, weaknesses, opportunities, and threats, cross-referenced into strategic action items for business planning and decision-making."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# SWOT Analysis

## Core Principle

A SWOT WITHOUT ACTION ITEMS IS JUST A LIST — EVERY ANALYSIS MUST END WITH CROSS-REFERENCED STRATEGIES AND PRIORITIZED NEXT STEPS THAT TELL THE USER EXACTLY WHAT TO DO.

## SWOT Context Types

Every analysis falls into one of these categories. Identify which one applies before gathering inputs.

| Context Type | When It Applies | Focus Areas |
|-------------|----------------|-------------|
| **Full Business** | Annual review, strategic planning, investor prep | All operations, finances, team, market position |
| **Product Launch** | Evaluating whether to build and ship a new product | Product-market fit, resources, competition, timing |
| **Market Entry** | Expanding into a new geography, segment, or channel | Local conditions, regulations, cultural fit, logistics |
| **Partnership Evaluation** | Considering a joint venture, co-marketing deal, or acquisition | Compatibility, shared resources, risk exposure, exit terms |
| **Strategic Decision** | Evaluating a major organizational decision or pivot | Relevant internal capabilities and external conditions |

## Impact Levels

| Level | Definition | Action Implication |
|-------|-----------|-------------------|
| **HIGH** | Directly affects revenue, survival, or core strategic positioning | Address within 30 days — build into immediate action plan |
| **MEDIUM** | Affects growth rate, efficiency, or competitive position | Address within 90 days — include in quarterly planning |
| **LOW** | Affects perception, minor processes, or long-term positioning | Monitor and revisit next quarter |

## Step 1: Understand

Gather these inputs before analyzing anything:

1. **Business/product name** — what the user is analyzing
2. **Industry/category** — the market they operate in
3. **Business stage** — early-stage (pre-revenue or early revenue), growth (scaling, hiring, expanding), or mature (established, optimizing, defending position)
4. **Decision context** — what specific decision or question this SWOT will inform (e.g., "Should we expand into wholesale?", "Should we acquire this company?")
5. **Known competitors** — 2-3 main competitors the user is aware of
6. **Target market** — who the user serves or wants to serve

**If the user provides a vague request like "do a SWOT for my business":**

1. Ask: "What decision or question do you want this SWOT to help you make?"
2. If they say "just a general assessment," default to Full Business context and frame the decision as: "Where should you focus your strategic energy over the next 6-12 months?"
3. Still gather items 1-3 and 5-6 above — a SWOT without business context produces generic results.

**GATE: Do not proceed to Step 2 until you have: the business description, the business stage, and the decision context.**

## Step 2: Analyze

Guide the user through each quadrant with targeted questions. Extract 4-6 items per quadrant and assign each a HIGH, MEDIUM, or LOW impact level.

**CRITICAL RULE: Internal factors (Strengths and Weaknesses) are things the business controls. External factors (Opportunities and Threats) are things happening in the market, industry, or environment that the business cannot directly control. Never mix internal and external factors within a quadrant.**

### 2A: Strengths (Internal, Positive)

Ask the user:
- What do you do better than your competitors?
- What unique resources, skills, or assets do you have?
- What do customers consistently praise or return for?
- What processes or systems give you an efficiency advantage?
- What is your strongest revenue stream or most reliable income source?

Extract 4-6 strengths with HIGH/MEDIUM/LOW impact levels.

Example output for a B2B services firm:
```
| # | Strength | Impact |
|---|----------|--------|
| 1 | Proprietary methodology with documented 40% faster delivery than industry standard | HIGH |
| 2 | Deep sector expertise in financial services — few competitors with this focus | HIGH |
| 3 | 72-hour turnaround on proposals vs. industry average of 2 weeks | MEDIUM |
| 4 | 65% of new business comes from existing client referrals | MEDIUM |
| 5 | Portfolio of 80+ documented case studies with quantified outcomes | LOW |
```

### 2B: Weaknesses (Internal, Negative)

Ask the user:
- Where do you lack resources (time, money, people, tools)?
- What do customers complain about or request that you cannot deliver?
- What do competitors do better than you?
- What processes are manual, slow, or error-prone?
- What skill gaps exist on your team?

Extract 4-6 weaknesses with impact levels.

Example output for a B2B services firm:
```
| # | Weakness | Impact |
|---|----------|--------|
| 1 | Team capacity capped at 8 active engagements — turning away 3-4 qualified leads per quarter | HIGH |
| 2 | No recurring revenue — pipeline resets quarterly with project completions | HIGH |
| 3 | Weak digital presence — website traffic minimal, no content strategy | MEDIUM |
| 4 | No standardized delivery packages — every engagement is custom, creating scope creep | MEDIUM |
| 5 | 40% of revenue comes from two anchor clients | LOW |
```

### 2C: Opportunities (External, Positive)

Ask the user:
- What market trends are working in your favor?
- What unmet needs exist in your market that nobody is serving well?
- What partnerships, collaborations, or channels could you pursue?
- What technology or tool changes could benefit you?
- What competitor weaknesses could you exploit?

Extract 4-6 opportunities with impact levels.

### 2D: Threats (External, Negative)

Ask the user:
- What competitors are growing or entering your space?
- What economic, regulatory, or market shifts concern you?
- What technology changes could disrupt your business model?
- What customer behavior shifts could reduce demand for what you offer?
- What supply chain, cost, or pricing pressures are you facing?

Extract 4-6 threats with impact levels.

**GATE: Review all four quadrants with the user before proceeding. Confirm that items are correctly categorized (internal vs. external) and that impact levels feel accurate. Adjust based on user feedback.**

## Step 3: Present

Deliver the complete analysis in this order.

### 3A: SWOT Matrix

Present the 2x2 matrix as a summary view. Bold HIGH-impact items.

```
## SWOT Matrix — [Business Name]

|  | Positive | Negative |
|--|---------|----------|
| **Internal** | **STRENGTHS** | **WEAKNESSES** |
|  | **S1: Proprietary methodology (HIGH)** | **W1: Team capacity cap (HIGH)** |
|  | **S2: Financial services expertise (HIGH)** | **W2: No recurring revenue (HIGH)** |
|  | S3: 72-hour proposal turnaround (MEDIUM) | W3: Weak digital presence (MEDIUM) |
|  | S4: Referral network (MEDIUM) | W4: No standardized packages (MEDIUM) |
|  | S5: Case study portfolio (LOW) | W5: Two-client concentration (LOW) |
| **External** | **OPPORTUNITIES** | **THREATS** |
|  | **O1: [Key opportunity] (HIGH)** | **T1: [Key threat] (HIGH)** |
|  | O2: [Opportunity] (MEDIUM) | T2: [Threat] (MEDIUM) |
```

### 3B: Cross-Reference Strategies

This is the highest-value section. Cross-reference quadrants to generate four strategy types:

**SO Strategies (Strengths + Opportunities) — Aggressive plays: use what you are good at to capture what the market is giving you.**

**WO Strategies (Weaknesses + Opportunities) — Improvement plays: fix internal gaps to capture external opportunities.**

**ST Strategies (Strengths + Threats) — Defensive plays: use what you are good at to protect against external risks.**

**WT Strategies (Weaknesses + Threats) — Survival plays: minimize internal gaps to avoid external dangers.**

### 3C: Top 3 Strategic Action Items

Distill the cross-reference strategies into the three highest-priority actions. Each must include an owner, a timeframe, and the strategy reference it maps to.

```
## Top 3 Strategic Action Items

1. **[Action title]**
   Owner: [Name]
   Timeframe: [X] days
   Maps to: [Strategy reference]
   First step: [Specific first action]

2. **[Action title]**
   Owner: [Name]
   Timeframe: [X] days
   Maps to: [Strategy reference]
   First step: [Specific first action]

3. **[Action title]**
   Owner: [Name]
   Timeframe: [X] days
   Maps to: [Strategy reference]
   First step: [Specific first action]
```

**GATE: Present the full analysis — matrix, cross-reference strategies, and action items — to the user. Ask them to review before saving.**

## Step 4: Act

After the user approves the analysis:

1. **Save as markdown file** — write the complete analysis to a file at the user's preferred path
   - Default filename: `swot-analysis-[business-name].md`
   - Include all sections: matrix, four quadrants with full descriptions, cross-reference strategies, and action items

2. **Provide action plan summary:**

```
SWOT analysis complete and saved to swot-analysis-[business-name].md

Summary:
- [X] strengths, [X] weaknesses, [X] opportunities, [X] threats identified
- [X] HIGH-impact items requiring attention within 30 days
- 4 cross-reference strategy categories generated (SO, WO, ST, WT)
- 3 prioritized action items with owners and timeframes

Top priority: [Action item 1 — one sentence]

Suggested review cadence: Revisit this SWOT quarterly.
```

3. **Suggest follow-up actions:**
   - If HIGH-impact weaknesses were identified, suggest creating an action plan to address them
   - If HIGH-impact opportunities exist, suggest a deeper market analysis or go-to-market plan
   - If entering a new market, suggest a competitor analysis as the natural next step

## Example 1: B2B Services Firm Evaluating a New Service Line

**Context:** Professional services firm at $8M revenue considering launching a managed services offering.

**Decision:** Should we launch a managed services line and move toward recurring revenue?

**Key SWOT findings:**
- Strengths: Deep client relationships + proven implementation methodology align with managed services demand
- Weakness: No recurring revenue infrastructure or customer success capability
- Opportunity: 40% of existing clients have expressed interest in ongoing support; recurring SaaS models in adjacent spaces are valued at 5-8x revenue vs. 1.5x for project businesses
- Threat: Requires 6-month investment before first MRR; competitor already offering a managed version

**Strategic recommendation:** SWOT supports launching managed services, but sequenced: build CS capability first (90 days), pilot with 3 existing clients (Q2), then open commercially (Q3). High-impact strengths align with high-impact opportunity. The threat is real but the opportunity window is wider than the threat timeline.

## Example 2: Company Evaluating Geographic Expansion

**Context:** Consumer brand doing $4M/year domestically, evaluating UK/EU market entry.

**Key SWOT findings:**
- Strengths: 42% repeat purchase rate, "clean science" brand positioning
- Weaknesses: No international logistics, formulations not EU-compliant, team stretched thin
- Opportunities: UK clean beauty growing 12% annually, EU compliance creates long-term moat
- Threats: EU compliance costs $30K-80K for reformulation, established local competitors

**Strategic recommendation:** Phased approach — commission EU compliance assessment first (30 days), then Amazon UK pilot with top 3 products to test demand before committing to full logistics infrastructure.

## Anti-Patterns

- **DO NOT** list more than 8 items per quadrant — cognitive overload makes the analysis unusable. Default to 4-6 items.
- **DO NOT** mix internal and external factors — strengths and weaknesses are things you control; opportunities and threats are things the market controls.
- **DO NOT** deliver a SWOT without cross-reference strategies and action items — a four-quadrant list without SO/WO/ST/WT strategies is incomplete.
- **DO NOT** list vague items — "good marketing" is not a strength. "35% email open rate on a 28K subscriber list, 2x industry average" is a strength.
- **DO NOT** rate everything as HIGH impact — if every item is critical, none of them are. Use the full range.
- **DO NOT** fabricate market data or statistics — if you do not know the market growth rate, say so.
- **DO NOT** present the analysis without user review — always show the full SWOT and strategies before saving.

## Recovery

### User Cannot Identify Strengths
1. Ask: "What do your best customers say when they refer someone to you?"
2. Ask: "If you disappeared tomorrow, what would your customers struggle to replace?"
3. Ask: "What part of your business runs most smoothly?"
4. If they still struggle, start with weaknesses and competitors — strengths often emerge as the inverse.

### User Lists Only Surface-Level Items
1. Push for specifics: "When you say 'good product,' what metric proves that?"
2. Apply the "so what" test: if you cannot explain why an item matters competitively, it is not specific enough.

### Analysis Feels Too Generic
1. Ask for numbers: revenue, margins, customer counts, conversion rates, churn rates
2. Ask for customer quotes — real language reveals real strengths
3. Replace any item that could apply to any business in the industry with one specific to this situation

### File Save Fails
1. Check if the target directory exists — use `Glob` to verify the path
2. If the directory does not exist, create it before writing
3. As a last resort, present the full analysis in the conversation so the user can copy it manually
