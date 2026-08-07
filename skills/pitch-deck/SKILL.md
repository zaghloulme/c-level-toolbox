---
name: Pitch Deck Builder
version: 2.4.1
description: "Builds complete investor, client, or partnership pitch decks — slide-by-slide content with problem, solution, market, traction, team, and ask — for fundraising, client proposals, and keynote presentations. Delivers markdown inline by default; can produce a file if requested and if a suitable tool is available."
---

# Pitch Deck

## Core Principle

EVERY SLIDE MUST COMMUNICATE ONE IDEA IN UNDER 30 WORDS OF BODY TEXT — IF YOU CANNOT SAY IT IN 30 WORDS, SPLIT IT INTO TWO SLIDES.

## Phase 1: Extract Pitch Elements

Gather the six core pitch elements through conversation. Ask the user directly — do not assume or fabricate any business details.

1. **Ask for the business brief** — request a 2-3 sentence description of what the business does, or accept a file/URL the user provides
2. **Extract these six elements** from the conversation:

| Element | What to Capture | Required? |
|---------|----------------|-----------|
| **Problem** | Who suffers, what the pain is, why existing solutions fail | Yes |
| **Solution** | What the product/service does, core value proposition | Yes |
| **Market Size** | TAM/SAM/SOM or target audience size | Yes |
| **Traction** | Revenue, users, growth rate, key milestones, testimonials | If available |
| **Team** | Key people, relevant experience, advisors | If available |
| **The Ask** | Funding amount, deal terms, partnership scope, or next steps | Yes |

3. **Identify the deck type** based on context:
   - **Investor deck** — emphasize market size, traction, financials, and funding ask
   - **Client deck** — emphasize problem/solution fit, case studies, pricing, and next steps
   - **Partnership deck** — emphasize mutual benefit, audience overlap, and proposed terms

4. **Present the extraction summary** to the user before proceeding:

```
## Pitch Elements

**Deck type:** Investor pitch
**Problem:** [extracted problem statement]
**Solution:** [extracted solution]
**Market:** [TAM/SAM/SOM or audience size]
**Traction:** [key metrics or "early stage — focusing on vision"]
**Team:** [key people and relevant background]
**The Ask:** [specific amount or action requested]

Ready to build the slide outline? (yes / adjust)
```

**GATE: Do not proceed to Phase 2 until the user confirms the extraction is accurate.**

## Phase 2: Build Slide Outline

Construct a 10-12 slide outline using the standard pitch deck structure. Each slide gets a title and 1-3 bullet points summarizing the content.

1. **Map elements to slides** using this default structure:

| Slide # | Title | Content Guidance | Max Words |
|---------|-------|-----------------|-----------|
| 1 | Title Slide | Company name, one-line tagline, presenter name, date | 15 |
| 2 | The Problem | Pain point in concrete terms. Use a stat or story. | 30 |
| 3 | The Solution | What you built and why it works. Lead with the outcome. | 30 |
| 4 | How It Works | 3-step process or product screenshot description. Visual-first. | 25 |
| 5 | Market Opportunity | TAM/SAM/SOM with sources. One chart description. | 25 |
| 6 | Business Model | How you make money. Pricing tiers or revenue streams. | 25 |
| 7 | Traction | Key metrics: revenue, users, growth %. Use numbers, not words. | 20 |
| 8 | Competition | 2x2 matrix or comparison table. Show your unique position. | 25 |
| 9 | The Team | Key people, names, one-line bios. 2-4 people max. | 30 |
| 10 | Financials | Revenue projections, unit economics, or key financial metrics. | 25 |
| 11 | The Ask | Specific amount, use of funds breakdown, timeline. | 25 |
| 12 | Contact | Name, email, website, social links. Clean and simple. | 15 |

2. **Adapt for deck type:**
   - **Client deck:** Replace slides 5, 7, 10 with Case Study, Testimonials, Pricing
   - **Partnership deck:** Replace slides 7, 10, 11 with Audience Overlap, Proposed Terms, Mutual Benefits

3. **Present the outline for review** — show the slide titles and bullet points as a numbered list in chat and ask the user to approve or request edits.

4. **Apply any changes** the user requests before proceeding

**GATE: Do not proceed to Phase 3 until the user confirms the outline is correct.**

## Phase 3: Write the Slide Content

Write the full deck as structured slide content using the approved outline. Apply the rules from the Slide-by-Slide Content Guide for each slide.

Format each slide as:

```
---
**Slide [N]: [Title]**

[Body content — bullet points, one idea per line, max 30 words total]

_Speaker note: [one sentence on what to say or emphasize verbally]_
```

Write all slides in sequence without pausing. After the final slide, ask:

"Want me to save this as a file? I'll write it to `pitch-deck-[company-name].md` unless you specify a path."

If saving: save the complete deckto the specified path.

**GATE: Present all slides before asking for refinements.**

## Phase 4: Refine the Deck

After the user reviews the slides, apply feedback directly to the markdown.

1. Accept specific change requests ("slide 7 needs the actual MRR number", "the ask slide should list use of funds")
2. Rewrite only the affected slides
3. Show the revised slides inline — do not reprint the entire deck for one change
4. If the user requests a full rewrite of a slide, replace it completely and mark it with `[revised]` in the title line for easy scanning

If 3 rounds of revision do not resolve the issue, ask: "What outcome are you trying to achieve on this slide?" — diagnose intent before iterating further.

## Phase 5: Deliver the Final Deck

1. Write the final approved deck to a file : `pitch-deck-[company-name]-final.md`
2. Confirm the file path to the user
3. Provide paste instructions:

```
**To use this deck:**
- **Google Slides / PowerPoint / Keynote:** Create one slide per section. Copy the body content for each slide. Delete speaker notes before presenting or keep them in the notes panel.
- **Paste into a design tool:** The markdown structure maps directly to slide titles and bullets. One `---` separator = one new slide.
- **Send as a document:** The file reads cleanly as a standalone briefing document before the deck is designed.
```

## Slide-by-Slide Content Guide

Every slide follows the same rule: one idea, visual-first, minimal text.

| Slide | Key Rule | Example |
|-------|----------|---------|
| **1. Title** | Company name large, tagline in one line, presenter + date small at bottom | "WorkflowOS — Operations intelligence for scaling teams" |
| **2. Problem** | Lead with pain. One stat or one-sentence story. Frame as audience's problem. | "The average operations team spends 60% of their week on reporting instead of decisions" |
| **3. Solution** | One sentence + three benefit bullets (not features) | "WorkflowOS surfaces the right data at the right moment for every decision" |
| **4. How It Works** | Three numbered steps, 5-8 words each. Visual-first. | "1. Connect your systems. 2. Set your metrics. 3. Decisions surface automatically." |
| **5. Market** | TAM/SAM/SOM stacked largest to smallest. Cite sources. One visual. | "TAM: $12B. SAM: $3.2B. SOM: $180M." |
| **6. Business Model** | Model in one line. 2-3 pricing tiers. One unit economic metric. | "SaaS: $2,500/mo growth, $6,000/mo enterprise, $15,000/mo custom" |
| **7. Traction** | Numbers only, large font. If pre-revenue: pilots, LOIs, waitlist. | "$85K MRR / 34 enterprise clients / 18% MoM growth" |
| **8. Competition** | 2x2 quadrant, you in top-right. 3-5 named competitors. No bashing. | Axes: "Ease of Implementation" vs "Real-Time Intelligence" |
| **9. Team** | 2-4 people max. Photo, name, title, one credential each. | "Sarah Chen, CEO — Ex-McKinsey, 10 years in enterprise software" |
| **10. Financials** | 3-year projections or run rate. Simple bar chart. Key assumptions small. | "Path to $8M ARR in 24 months" |
| **11. The Ask** | Exact amount. Use-of-funds breakdown (3-4 categories as %). Timeline. | "$4M Series A. 45% product, 35% GTM, 15% team, 5% ops" |
| **12. Contact** | Name, email, website, social. One closing line. No clutter. | "Let's build the operating system for your organization." |

## Example 1: B2B SaaS Investor Pitch

**User says:** "I need an investor pitch deck for my SaaS startup. We built an AI-powered operations platform for mid-market companies called WorkflowOS. We have 34 enterprise clients, $85K MRR, growing 18% month-over-month. Raising a $4M Series A."

**Phase 1 extraction presented to user:**
```
**Deck type:** Investor pitch
**Problem:** Operations teams spend 60%+ of their time on reporting and coordination instead of decisions
**Solution:** WorkflowOS — AI that surfaces the right operational intelligence at the right moment
**Market:** $12B operations software market, $3.2B mid-market segment
**Traction:** 34 enterprise clients, $85K MRR, 18% MoM growth, 94% retention
**Team:** 2 co-founders — former McKinsey consultant and enterprise software CTO
**The Ask:** $4M Series A — 45% product, 35% GTM, 15% team, 5% ops
```

**Phase 2 outline presented for review:**
1. WorkflowOS — Operations intelligence for scaling teams
2. The Problem — Operations teams are drowning in coordination work
3. The Solution — AI that turns data into decisions automatically
4. How It Works — Connect, configure, decide in 3 steps
5. Market Opportunity — $12B TAM, $3.2B SAM, $180M SOM
6. Business Model — SaaS: $2,500/mo growth through $15,000/mo custom
7. Traction — 34 clients, $85K MRR, 18% MoM growth
8. Competition — Faster than legacy BI, smarter than spreadsheets, simpler than enterprise platforms
9. The Team — McKinsey + enterprise software DNA
10. Financials — Path to $8M ARR in 24 months
11. The Ask — $4M to accelerate into mid-market
12. Get in Touch — founders@workflowos.io

**Phase 3-5:** 12 slides written. Saved to `pitch-deck-workflowos.md`. Ready to paste into Google Slides or PowerPoint.

## Example 2: Consultant Client Pitch

**User says:** "I'm a brand strategy consultant and I need a pitch deck for a potential client — a D2C skincare company that wants to rebrand. I want to show them my process and pricing."

**Phase 1 extraction presented to user:**
```
**Deck type:** Client pitch
**Problem:** D2C skincare brands struggle to differentiate — generic branding leads to low recall and high acquisition costs
**Solution:** Full-service brand strategy — positioning, visual identity, messaging, launch playbook
**Traction:** 12 brand projects completed, 3 in skincare, average 35% improvement in brand recall
**Team:** Solo consultant — 8 years at Pentagram + Collins, 3 years independent
**The Ask:** $25,000 engagement over 8 weeks (audit, strategy, delivery)
```

**Phase 2 outline (adapted for client deck):**
1. Brand Strategy for [Client Name] — by [Consultant Name]
2. The Challenge — Standing out in a crowded market
3. My Approach — Positioning-first brand strategy
4. How We Work Together — Audit, Strategy, Delivery (8 weeks)
5. Case Study — GlowLab: 42% increase in brand recall
6. Case Study — BeautyStack: 28% lower acquisition cost after rebrand
7. Testimonials — What clients say
8. The Deliverables — What you get at the end of 8 weeks
9. About Me — 8 years at Pentagram + Collins, 3 years independent
10. Investment — $25,000 for the full engagement
11. Next Steps — Sign by Friday, kick off Monday
12. Contact — email, portfolio, LinkedIn

**Phase 3-5:** 12 slides written. Saved to `pitch-deck-brand-strategy.md`. Ready to paste into Google Slides or PowerPoint.

## Anti-Patterns

- **DO NOT** put more than 30 words of body text on any slide — pitch decks are visual, not documents
- **DO NOT** exceed 12 slides — attention drops sharply after slide 10; every slide beyond 12 must justify its existence
- **DO NOT** skip the Ask slide — the entire deck builds to this moment; leaving it out wastes the audience's time
- **DO NOT** use generic stock imagery descriptions — every visual element should reinforce the specific business story
- **DO NOT** cram financial projections into a wall of numbers — pick 3-4 key metrics and make them large
- **DO NOT** list features instead of benefits on the Solution slide — investors and clients buy outcomes, not feature lists
- **DO NOT** include more than 4 team members — highlight founders and key hires only
- **DO NOT** present multiple pricing options on the Ask slide for investor decks — state one clear number and the use of funds

## Recovery

**Slide content is too generic:** Ask for one concrete detail per vague slide — a real stat, a named competitor, an actual price. Generic inputs produce generic slides.

**User wants to skip the outline review:** Do not skip it. The outline gate exists to prevent writing 12 slides against a misunderstood brief. Show the outline and ask for a single yes/no.

**Brief is too vague:** Ask three questions: (1) Who is your target customer? (2) What do they pay you for? (3) What should the audience do after this deck? Do not proceed until Problem, Solution, and Ask are clear.
