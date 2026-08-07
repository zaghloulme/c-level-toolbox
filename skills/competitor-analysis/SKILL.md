---
name: Competitor Analysis
description: "Conducts structured competitor analysis with comparison matrices, positioning maps, gap identification, threat assessment, and strategic recommendations — for executives mapping competitive landscapes, preparing go-to-market strategies, or making positioning decisions."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
---

# Competitor Analysis

## Core Principle

COMPETITIVE ANALYSIS IS ONLY VALUABLE WHEN IT DRIVES A DECISION — NEVER DELIVER A MATRIX WITHOUT STRATEGIC RECOMMENDATIONS THAT TELL THE USER WHAT TO DO NEXT.

---

## Competitive Positioning Categories

Every competitor (and the user's own business) falls into one of these positioning archetypes:

| Category | Definition | Typical Signals |
|----------|-----------|-----------------|
| **Price Leader** | Wins on affordability, targets cost-conscious buyers | Lowest tier pricing, free plans, "affordable" messaging |
| **Quality Leader** | Wins on premium experience, depth, or polish | Higher pricing, fewer features but better execution, strong brand |
| **Niche Specialist** | Wins by owning a narrow segment deeply | Messaging targets one specific audience, limited feature set tuned to that audience |
| **Full-Service** | Wins on breadth, all-in-one positioning | Large feature sets, multiple products, "everything you need" messaging |
| **Disruptor** | Wins by changing the rules — new model, new channel, new pricing | Unconventional pricing, challenger brand tone, fundamentally different delivery model |

---

## Threat Assessment Levels

| Level | Definition | Action Required |
|-------|-----------|-----------------|
| **HIGH** | Competitor directly targets the same customer, same price tier, with a strong or growing product | Requires active differentiation strategy — must communicate why you are different |
| **MEDIUM** | Competitor overlaps on audience or features but differs on positioning, pricing, or market segment | Monitor quarterly — differentiate on the overlap points |
| **LOW** | Competitor exists in the same industry but targets a different customer, price tier, or use case | Awareness only — no immediate action needed |

---

## Step 1: Understand

Gather these inputs before analyzing anything:

1. **Business/product** — what is sold, what problem it solves, who it serves
2. **Industry/category** — the market being competed in
3. **Known competitors** — names of 3-7 competitors
4. **Key differentiators** — what the organization believes makes it different (even if unvalidated)
5. **Target customer** — who the ideal buyer is (segment, role, pain points)
6. **Pricing tier** — where the business sits on the price spectrum (budget, mid-market, premium)

**If competitors are not known**, guide identification with these methods:

| Method | How It Works | Best For |
|--------|-------------|----------|
| **Direct search** | Search for the product category + "alternatives" or "vs" | Software, digital products |
| **Customer question** | Ask: "Where would your customer go if you did not exist?" | Service businesses |
| **Adjacent category** | Look at businesses solving the same pain differently | New-category products |
| **Market scan** | Search industry directories or sector reports | B2B and institutional markets |

Suggest 3-5 competitors based on the business description if none can be named. Present the suggestions and let the user confirm, remove, or add.

**GATE: Do not proceed to Step 2 until you have: the business description, at least 3 confirmed competitors, and the target customer. If target customer is not provided, infer a reasonable default and confirm it.**

---

## Step 2: Analyze

Build four analysis components. Complete all four before presenting anything.

### 2A: Comparison Matrix

Build a feature-by-feature comparison across all competitors and the user's business.

**Default columns (adapt based on industry):**

For product/SaaS businesses:
| Dimension | What to Capture |
|-----------|----------------|
| Core offering | Primary product or service in one sentence |
| Target audience | Who they sell to |
| Pricing | Plans, tiers, starting price |
| Key features | Top 3-5 features or capabilities |
| Strengths | What they do well (2-3 bullets) |
| Weaknesses | Where they fall short (2-3 bullets) |
| Positioning | Which archetype |
| Unique advantage | The one thing they do that nobody else does |

For service businesses:
| Dimension | What to Capture |
|-----------|----------------|
| Core service | Primary offering in one sentence |
| Target client | Who they serve |
| Pricing model | Hourly, package, retainer, project-based |
| Price range | Approximate range or starting price |
| Specialization | Niche or area of focus |
| Strengths | What they do well (2-3 bullets) |
| Weaknesses | Where they fall short (2-3 bullets) |
| Positioning | Which archetype |
| Unique advantage | The one thing they do that nobody else does |

### 2B: SWOT Summary Per Competitor

For each competitor, produce a condensed SWOT (2 bullets per quadrant maximum):

```
## [Competitor Name] — SWOT

| Strengths | Weaknesses |
|-----------|------------|
| - [Specific strength] | - [Specific weakness] |
| - [Specific strength] | - [Specific weakness] |

| Opportunities | Threats |
|---------------|---------|
| - [Opportunity they have] | - [Threat they face] |
| - [Opportunity they have] | - [Threat they face] |
```

### 2C: Gap Analysis

Identify 3-5 gaps — things competitors collectively miss that the organization could own.

For each gap:
- **What is missing** — the unmet need or underserved approach
- **Which competitors miss it** — name them
- **Why it matters** — connect it to target customer pain
- **Difficulty to exploit** — LOW (messaging change), MEDIUM (new offer or feature build), HIGH (fundamental pivot)

### 2D: Threat Assessment

Rate each competitor as HIGH, MEDIUM, or LOW threat. For each:
- **Rating** — HIGH / MEDIUM / LOW
- **Rationale** — one sentence explaining the rating
- **Recommended response** — what to do about this competitor specifically

---

## Step 3: Present

Deliver the analysis in a structured format. Present everything before saving anything.

### Presentation Order

**1. Comparison Matrix** — full table with all competitors and the user's business side by side

**2. Positioning Summary** — one paragraph placing each competitor into a positioning category and explaining where the user fits or should fit

**3. Threat Assessment Table:**

```
| Competitor | Positioning | Threat Level | Key Concern |
|-----------|-------------|-------------|-------------|
| [Competitor A] | [Archetype] | HIGH | [Specific concern] |
| [Competitor B] | [Archetype] | MEDIUM | [Specific concern] |
| [Competitor C] | [Archetype] | LOW | [Specific concern] |
```

**4. Top 3 Opportunities** (gaps to exploit):

```
## Opportunities

1. **[Gap name]** — [What is missing and which competitors miss it].
   [Connect to target customer pain.]
   Difficulty: [LOW / MEDIUM / HIGH] ([what it requires])

2. **[Gap name]** — [Description]
   Difficulty: [Level] ([what it requires])

3. **[Gap name]** — [Description]
   Difficulty: [Level] ([what it requires])
```

**5. Top 3 Threats** (competitive risks):

```
## Threats

1. **[Threat]** — [Why this specific competitor or trend poses a risk and what the impact would be]

2. **[Threat]** — [Description]

3. **[Threat]** — [Description]
```

**6. Strategic Recommendations** (3-5 actionable items):

```
## Strategic Recommendations

1. **[Action]** — [Specific, concrete action connected to a gap or threat. Name the competitor(s) it addresses.]

2. **[Action]** — [Description]

3. **[Action]** — [Description]
```

**GATE: Present the full analysis and ask the user to review before saving. Offer to adjust any ratings, add/remove competitors, or modify recommendations.**

---

## Step 4: Act

Save the analysis based on the user's preference.

### Option A: Save to Notion Database

1. **Search for existing context** — call `notion-search` to check if the user has a strategy, competitors, or market research page. If found, confirm placement.

2. **Create the database** — call `notion-create-database` with these properties:

   | Property | Type | Purpose |
   |----------|------|---------|
   | **Competitor** | Title | Company or product name |
   | **Category** | Select | Price Leader, Quality Leader, Niche Specialist, Full-Service, Disruptor |
   | **Threat Level** | Select | HIGH, MEDIUM, LOW |
   | **Target Audience** | Rich text | Who they sell to |
   | **Pricing** | Rich text | Plans, tiers, price range |
   | **Key Strengths** | Rich text | Top 2-3 strengths |
   | **Key Weaknesses** | Rich text | Top 2-3 weaknesses |
   | **Unique Advantage** | Rich text | Their one differentiator |
   | **Our Response** | Rich text | What the organization should do about this competitor |
   | **Last Reviewed** | Date | Date of this analysis |
   | **Notes** | Rich text | Additional context, links, observations |

   Database title: `Competitor Analysis — [Industry/Category]`

3. **Populate entries** — call `notion-create-pages` to add each competitor as a row with all fields filled from the analysis.

4. **Add the user's own business as a row** — mark it clearly so it is distinguishable. This lets the user see themselves in context.

5. **Confirm:**

```
Notion database created: "Competitor Analysis — [Category]"

  [N] entries: [Competitor names + user's business]
  Properties: Category, Threat Level, Audience, Pricing, Strengths, Weaknesses, Unique Advantage, Our Response, Last Reviewed
  All entries dated to today

  Suggested cadence: Review and update this database quarterly.
```

### Option B: Save as Markdown File

If the user prefers a local file or does not have Notion connected:

1. Write the full analysis to a markdown file at the user's preferred path
2. Default filename: `competitor-analysis-[category].md`
3. Include all sections: matrix, SWOTs, gaps, threats, recommendations

### Suggest Review Cadence

Regardless of save format, close with:

```
Competitive landscapes shift. Review this analysis quarterly:
- Update pricing and feature changes
- Re-assess threat levels based on competitor moves
- Check if identified gaps have been filled
- Refresh recommendations based on the organization's own progress
```

---

## Recovery and Troubleshooting

### Fewer Than 3 Competitors Known

1. Ask: "Where would your ideal customer go if your business did not exist?"
2. Search for the product category + "alternatives" or "competitors" to suggest options
3. Check adjacent categories — businesses solving the same pain with a different model count
4. If the user can only identify 1-2, proceed with those and note the analysis is incomplete

### No Pricing Data Available

1. Check competitor websites for public pricing pages
2. If pricing is not public: mark as "Contact for quote" and note the likely tier based on positioning and target market
3. Use comparative language: "Premium tier — positioned above this price point" or "Budget tier — significantly below"
4. **Do not fabricate pricing.** If it cannot be determined, focus the analysis on non-price dimensions

### Competitor Is Much Larger

1. Acknowledge the scale difference explicitly: "This organization serves a much broader market. The comparison focuses on the segment where you both compete."
2. Reframe the comparison around the overlap segment only
3. Adjust threat level to reflect actual overlap, not total market size
4. Focus recommendations on segments where scale is a disadvantage for the large competitor (speed, personalization, niche depth)

### Organization Does Not Yet Exist (Pre-Launch)

1. Proceed with the analysis normally — competitive analysis is most valuable before launch
2. Label the user's column clearly: "[Name] (Planned)" to distinguish plans from reality
3. Add a "Launch Positioning" recommendation: which positioning archetype and differentiation angle to lead with at launch
4. Emphasize gaps and opportunities over threats — pre-launch, the organization can build specifically to fill identified gaps

### Notion Save Fails

1. Call `notion-search` to verify workspace access
2. **Fallback:** Save the full analysis as a markdown file. All data can be transferred to Notion later.

### Analysis Feels Too Generic

1. Ask for more context: "Can you share specific features, pricing pages, or customer feedback about these competitors?"
2. Narrow comparison dimensions — focus on the 3-4 dimensions that matter most
3. Add a "Customer Perception" row — what do reviews and market feedback say about each competitor?
4. Replace generic strengths/weaknesses with specific evidence: instead of "good support," use "4.8-star rating with reviews citing fast response times"

---

## Anti-Patterns

- **DO NOT** present a comparison matrix without strategic recommendations — a matrix alone is a spreadsheet, not an analysis
- **DO NOT** rate every competitor as HIGH threat — if everything is critical, nothing is. Use the full range
- **DO NOT** recommend "be better at everything" — each recommendation must target a specific gap with a specific action
- **DO NOT** fabricate pricing, feature details, or market data — if information is unavailable, say so
- **DO NOT** skip the user's own business in the comparison — they must see themselves in the matrix to understand their position
- **DO NOT** save to Notion before the user reviews and approves the analysis — always present first, save second
- **DO NOT** compare on more than 10 dimensions — default to 8, go deeper only if the user asks
