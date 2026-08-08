---
name: Market Research and Opportunity Analysis
version: 1.2.3
description: "Conducts market sizing, trend analysis, audience segmentation, and opportunity assessment for business ideas, new markets, and strategic decisions."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Market Research

## Core Principle

MARKET RESEARCH ANSWERS ONE QUESTION: IS THERE A PROFITABLE GAP BETWEEN WHAT PEOPLE WANT AND WHAT IS CURRENTLY AVAILABLE?

## Workflow

### Step 1: Define the Research Scope

Ask:
1. What product, service, or business idea are you researching?
2. Who do you think your ideal customer is?
3. What specific question are you trying to answer? (Is there demand? How big is the market? Who are the competitors? What should we charge?)
4. What geography? (Regional, national, global)

**Minimum needed: question 1.**

### Step 2: Market Sizing (TAM/SAM/SOM)

Calculate three layers:

- **TAM (Total Addressable Market):** Everyone who could theoretically buy this
- **SAM (Serviceable Addressable Market):** The segment you can realistically reach with your business model
- **SOM (Serviceable Obtainable Market):** What you can realistically capture in year 1-2

**Sizing Methods:**
1. **Top-down:** Start with industry data, narrow by segment and geography
2. **Bottom-up:** Start with unit economics (price × potential customers)
3. **Comparable:** Use a similar product's market as a proxy

Always use at least two methods and cross-reference.

### Step 3: Audience Segmentation

Define 2-3 target segments:

| Segment | Profile | Pain Points | Willingness to Pay | Where They Are |
|---------|---------|-------------|-------------------|----------------|
| Primary | | | | |
| Secondary | | | | |
| Tertiary | | | | |

### Step 4: Competitive Landscape

Map competitors on two axes: price and specialization.

| Competitor | Price Point | Target Customer | Strengths | Weaknesses | Market Position |
|-----------|------------|----------------|-----------|------------|----------------|
| | | | | | |

Identify the **gap** — the underserved intersection of audience and price point.

### Step 5: Trend Analysis

Identify 3-5 relevant trends:
- Industry growth trajectory
- Customer behavior shifts
- Technology enablers
- Regulatory changes
- Cultural or demographic trends

### Step 6: Opportunity Assessment

| Factor | Score (1-5) | Notes |
|--------|------------|-------|
| Market Size | | |
| Growth Trajectory | | |
| Competition Intensity | | |
| Barrier to Entry | | |
| Your Differentiation | | |
| **Overall Opportunity** | **X/5** | |

## Examples

### Example 1: Specialized B2B Software Service

**Market Sizing:**

- **TAM:** US small business bookkeeping market = $55B annually. 33.2M small businesses, ~60% outsource some bookkeeping function.
- **SAM:** E-commerce businesses specifically = ~2.5M active sellers in the $50K-$2M revenue range. At $300-500/month for specialized services = $9-15B.
- **SOM (Year 1):** Targeting the $100K-$500K revenue range = ~400,000 businesses. At 0.1% capture rate = 400 clients × $400/mo = $1.92M ARR.

**Audience Segments:**

| Segment | Profile | Pain Point | WTP |
|---------|---------|-----------|-----|
| Mid-size operator ($100-300K) | Small team, handling multiple platforms | Inventory tracking, multi-channel reconciliation | $200-350/mo |
| Growing brand ($300K-1M) | 5-10 person team | Platform complexity makes P&L confusing | $400-600/mo |
| Category specialist ($200K+) | Deep expertise, complex fee structure | Needs category-specific reporting | $300-500/mo |

**Gap identified:** No service combines category-specific expertise with structured human support at a mid-market price. This is the opportunity.

**Opportunity Score: 4.2/5** — Large market, growing segment, fragmented competition, clear differentiation possible.

### Example 2: Specialized Delivery Service

**Quick Assessment:**

- **TAM:** US meal delivery market = $26.4B (2024), growing 12.5% CAGR
- **SAM:** Specialized meal prep for professionals = ~$4.8B
- **SOM (Year 1):** Single metro area, 500 subscribers × $150/week × 50 weeks = $3.75M

**Key Trends:**
1. Remote and hybrid work is permanent for 30%+ of knowledge workers
2. Health-conscious eating up 23% post-pandemic
3. Performance-optimized food growing as a category
4. Food subscriptions have the highest retention rates among subscription categories

**Competition Intensity: HIGH** — Multiple national operators plus 50+ local competitors in most metros. Differentiation must be specific.

**Recommendation:** Viable only with a hyper-specific niche (e.g., corporate B2B delivery, or a specific dietary segment with underserved demand). General meal prep is saturated.

## Recovery & Fallbacks

- **No industry data available:** Use bottom-up sizing from comparable businesses, proxy indicators (community sizes, search volume, adjacent markets).
- **Idea too niche to size:** That is often a good sign. Size the adjacent market and estimate the niche as a percentage.
- **Market looks saturated:** Saturated markets still have gaps. Look for underserved segments, pricing tiers, or geographic pockets. If truly no gap exists, say so.
- **Need exact numbers:** All market sizing is estimation. Present ranges, not false precision. Label sources and assumptions clearly.

## Constraints

- **ALWAYS state data sources and assumptions** — never present estimates as facts
- **NEVER guarantee market outcomes** — research reduces risk, it does not eliminate it
- Present TAM/SAM/SOM as ranges when exact data is unavailable
- Distinguish between addressable market and actual demand
- Include at least one contrarian data point or risk factor — do not just confirm what the user wants to hear
