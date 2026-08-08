---
name: Business Plan
version: 1.2.4
description: "Writes complete business plans with executive summary, market analysis, revenue model, financial projections, and operational strategy — for new ventures, funding applications, market entries, or strategic planning cycles."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Business Plan

## Deliverable requirements (hard)

Every complete business plan MUST contain the following sections in full — never as summaries or placeholders:

1. Executive Summary
2. Company Description
3. Market Analysis (industry, target market, competitive landscape)
4. Product or Service
5. Marketing and Sales Plan
6. Operations Plan
7. Management Team and Organization
8. Financial Projections (3-year P&L, cash flow, break-even)
9. Funding Request (if applicable)
10. Appendices

**Phased delivery to avoid truncation.** Business plans are long. Deliver Pass 1 (sections 1-7) in full inline, then STOP and ask "Continue with financial projections, funding request, and appendices?" before Pass 2. Never end mid-section. Never substitute a table of contents for the actual content.

## Core Principle

EVERY BUSINESS PLAN MUST ANSWER THREE QUESTIONS: WHAT PROBLEM DO YOU SOLVE? WHO PAYS YOU? HOW DO YOU MAKE MONEY?

## Workflow

### Phase 1: Discovery Interview

Ask the user these questions (skip any already answered):

1. What does this business do in one sentence?
2. Who is the customer? (segment, industry, geography, size)
3. What problem does this solve, and how do customers currently handle it without you?
4. How does the business make money? (revenue streams, pricing model)
5. Who are the top 3 competitors?
6. What is the differentiated position or advantage?
7. What stage is the business at? (concept, pre-revenue, revenue-generating, scaling)
8. What is the purpose of this plan? (internal strategy, investor pitch, loan application, board presentation)

**DO NOT proceed to Phase 2 until you have answers to at least questions 1-4.**

### Phase 2: Market Analysis

1. Define the Total Addressable Market (TAM), Serviceable Addressable Market (SAM), and Serviceable Obtainable Market (SOM)
2. Identify 3-5 market trends supporting the opportunity
3. Build a competitive landscape table with positioning
4. Identify the gap the business fills and why now

### Phase 3: Draft the Plan

Write these sections in order:

1. **Executive Summary** (1 page max) — Problem, solution, market size, revenue model, funding ask if applicable
2. **Company Description** — Mission, vision, legal structure, founding context
3. **Market Analysis** — TAM/SAM/SOM, trends, competitive landscape
4. **Products & Services** — What is sold, pricing, key differentiators, roadmap
5. **Marketing & Sales Strategy** — Customer acquisition channels, sales process, partnerships
6. **Operations Plan** — Team structure, key processes, technology, milestones
7. **Revenue Model & Financial Projections** — Revenue streams, cost structure, 12-month P&L projection, break-even analysis
8. **Funding Requirements** (if applicable) — Amount needed, use of funds, projected return

### Phase 4: Financial Projections

Build a 12-month projection table:

| Month | Revenue | COGS | Gross Profit | Operating Expenses | Net Profit |
|-------|---------|------|-------------|-------------------|------------|
| 1     | [X]     | [X]  | [X]         | [X]               | [X]        |

- Use conservative estimates (70% of optimistic projections)
- Include assumptions beneath every projection
- Calculate break-even month
- Show both a base case and a downside scenario

### Phase 5: Review and Polish

1. Verify the executive summary can stand alone as a one-page pitch
2. Check that all financial numbers are internally consistent
3. Confirm the competitive analysis is honest — acknowledge competitor strengths before differentiating
4. Confirm the plan matches its purpose (investor plans need ROI focus; internal plans need operational detail)

## Example 1: B2B Software Company Entering a New Market

**Discovery answers:**
- Business: Workforce analytics platform for mid-size manufacturers
- Customer: Operations directors at manufacturing companies with 200-2,000 employees
- Problem: Manufacturers track equipment performance closely but have no visibility into workforce productivity patterns; decisions are made on gut feel
- Revenue: Annual SaaS license at EGP 120,000/year for up to 200 users

**Executive Summary output:**

> [Company] provides workforce analytics for mid-size manufacturers — giving operations directors the same data-driven visibility into their teams that they already have for their equipment.
>
> Egyptian manufacturers operating at 200-2,000 employees manage significant labor costs with almost no structured data on productivity patterns, shift efficiency, or workforce utilization. The result: staffing decisions based on manager intuition, reactive scheduling, and difficulty justifying headcount to ownership.
>
> The addressable market in Egypt includes approximately 4,200 manufacturers in this employee range. At an annual contract value of EGP 120,000, a 2% market penetration represents EGP 10.1M in annual recurring revenue. The business reaches break-even at 18 contracts.

**12-Month Projection (excerpt):**

| Month | Contracts | ARR (EGP) | Monthly Revenue | Expenses | Net |
|-------|-----------|-----------|----------------|----------|-----|
| 1-3   | 2         | 240,000   | 20,000         | 85,000   | -65,000 |
| 6     | 7         | 840,000   | 70,000         | 110,000  | -40,000 |
| 9     | 14        | 1,680,000 | 140,000        | 130,000  | +10,000 |
| 12    | 22        | 2,640,000 | 220,000        | 160,000  | +60,000 |

## Example 2: Regional Expansion Plan for an Existing Business

**Discovery answers:**
- Business: Professional training and certification provider, currently operating in Cairo
- Customer: HR directors at corporates seeking accredited training for 50-500 employees
- Problem: Most corporate training in Egypt is generic and not tied to measurable outcomes; organizations cannot demonstrate ROI to their boards
- Revenue: Per-seat training fees (EGP 4,500 per participant), annual L&D contracts

**Executive Summary output:**

> [Company] delivers outcome-linked professional training and certification to Egyptian corporates — with each program designed to produce verifiable competency improvements that HR directors can report to leadership.
>
> The Egyptian corporate training market generates an estimated EGP 2.8B annually, with demand concentrated in financial services, manufacturing, and government-adjacent sectors. The addressable segment — corporates with 50-500 employees seeking accredited programs — numbers approximately 1,800 organizations in Greater Cairo alone.
>
> Revenue model: per-seat fees at EGP 4,500/participant across open enrollment and in-house programs, plus annual L&D retainer agreements covering 3-4 customized programs per year at EGP 280,000-420,000 per contract. Expansion into Alexandria in Q3 and Port Said in Q4 adds an estimated EGP 3.2M in addressable revenue.

## Recovery and Fallbacks

- **User cannot answer discovery questions:** Start with questions 1 and 4 only. Build the plan iteratively, marking sections as "[NEEDS INPUT]" and returning to complete them.
- **No financial data available:** Use industry benchmarks. State all assumptions explicitly: "Based on an industry average conversion rate of X% and an average contract value of [amount]..."
- **Plan exceeds 10 pages:** The plan is covering too much. Split into a 2-page executive summary and a detailed appendix.
- **User needs investor-ready formatting:** Add a cover page, table of contents, and financial model appendix. Keep the core plan under 15 pages.

## Constraints

- **NEVER present financial projections without stating assumptions**
- **NEVER dismiss competitors** — acknowledge their strengths, then differentiate
- Always use conservative revenue estimates
- Include both base case and downside scenarios for financial projections
- Mark any section where data is estimated versus verified
