---
name: Joint Venture Proposal
version: 1.6.0
description: "Writes joint venture proposals with value exchange analysis, revenue sharing structure, responsibility matrices, and exit terms — for organizations proposing partnerships where two parties co-invest resources to create shared value."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Joint Venture Proposal

## Core Principle

A JOINT VENTURE PROPOSAL MUST ANSWER ONE QUESTION CONVINCINGLY: WHY IS THIS PARTNERSHIP MORE VALUABLE THAN EITHER PARTY ACTING ALONE — IF YOU CANNOT QUANTIFY THE MULTIPLIER, THE DEAL IS NOT READY.

## Phase 1: Brief

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Partner name** | "Who is this proposal being pitched to?" | No default — must be provided |
| **JV concept** | "What will the two organizations create or deliver together?" | No default — must be provided |
| **Your contribution** | "What does your organization bring? (distribution, IP, capital, capabilities)" | No default — must be provided |
| **Their contribution** | "What does the partner bring?" | No default — must be provided |
| **Revenue model** | "How will revenue be generated and split?" | 50/50 revenue share |
| **Duration** | "Is this a one-time project or an ongoing partnership?" | One-time project with renewal option |

**GATE: Confirm the brief before drafting the proposal.**

## Phase 2: Structure

### Proposal Architecture

```
1. Executive Summary — the opportunity in 3-4 sentences
2. The Opportunity — market need and why now
3. Partnership Value — what each party brings, why together > alone
4. Deliverables — what will be created or delivered
5. Revenue Model — how money flows, revenue split, expense handling
6. Responsibilities — who does what, with deadlines
7. Timeline — key milestones and dates
8. Terms — duration, exclusivity, IP, exit
9. Next Steps — how to move forward
```

### Value Exchange Matrix

```
| | [Your Organization] | [Partner Organization] |
|---|---------------------|------------------------|
| **Distribution/Reach** | [Channels, segments] | [Channels, segments] |
| **Expertise** | [Specific capabilities] | [Specific capabilities] |
| **Assets** | [Products, IP, systems] | [Products, IP, systems] |
| **Capital** | [Investment if any] | [Investment if any] |
| **Combined value** | [Why 1+1>2] |
```

**GATE: Present the structure and value exchange for approval.**

## Phase 3: Write

### Writing Rules

- Lead with the partner's benefit, not yours
- Quantify everything possible (market size, projected revenue, capacity contributed)
- Be specific about responsibilities — vague roles create disputes later
- Include an exit clause — good partnerships plan for all outcomes
- Keep the tone direct and professional, not promotional

### Proposal Sections

**Executive Summary (150-200 words)**
- What the JV is, who benefits, projected outcome
- Written so a senior executive understands the deal in 60 seconds

**The Opportunity**
- Market data or trend supporting the concept
- Gap that this JV fills
- Timing — why this should happen now

**Partnership Value**
- Your organization's contribution with specifics
- The partner's contribution with specifics
- The multiplier effect — what the combined effort produces that neither could alone

**Revenue Model**
```
Revenue source: [Product/service/contract/event]
Projected revenue: [Amount] based on [assumptions]
Split: [X%] to [Your Organization] / [Y%] to [Partner]
Payment schedule: [When and how payments are made]
Expense handling: [Who covers what costs, caps, and reimbursement process]
```

**Responsibilities Matrix**
```
| Task | Owner | Deadline |
|------|-------|----------|
| [Task 1] | [Your org / Partner] | [Date] |
| [Task 2] | [Your org / Partner] | [Date] |
```

**Terms**
- Duration and renewal conditions
- Exclusivity scope (if any)
- IP ownership for co-created assets
- Confidentiality expectations
- Exit clause with notice period
- Dispute resolution process

## Phase 4: Polish

### 1. Partner Personalization

Review the proposal for:
- References to the partner's specific business context, market position, or stated objectives
- Alignment with their known strategic priorities
- Language and formality that matches their organization's communication style
- No generic or template-feeling sections

### 2. Risk Mitigation

Address potential objections proactively:
```
## Addressed Risks
- **Time commitment:** Estimated [X hours/week] for [Y weeks/months]
- **Financial exposure:** Costs capped at [amount] per party before mutual approval required
- **Brand risk:** Approval process for all co-branded materials
- **Exit risk:** Either party can exit with [X days] written notice
```

### 3. Proposal Checklist

```
- [ ] Executive summary is under 200 words
- [ ] Partner's benefit is addressed before yours
- [ ] Revenue projections include stated assumptions
- [ ] Every responsibility has an owner and deadline
- [ ] Exit clause is fair to both parties
- [ ] IP ownership is explicitly defined
- [ ] Next steps include a specific date or action
```

## Example 1: Technology Distribution Partnership

```
Concept: Co-market and distribute a combined offering to new client segments
Your organization brings: Established product IP, technical integration capability, 200-client install base
Partner brings: Regional sales network across 6 cities, government and institutional relationships, brand trust in target segment
Revenue: License fees on new clients acquired through the partnership, 40% to each party, 20% to shared marketing fund
Projected: 35 new contracts in Year 1 at EGP 180,000 average = EGP 6.3M gross
```

## Example 2: Corporate Event Co-Hosting

```
Concept: Annual industry conference combining both organizations' networks and credibility
Your organization brings: Content programming, speaker relationships, digital audience of 12,000
Partner brings: Venue relationships, local sponsorship connections, operational logistics, physical audience of 8,000
Revenue: Ticket sales + corporate sponsorships, split 50/50 after direct costs
Projected: 450 attendees at EGP 3,500 = EGP 1.575M gross; EGP 650,000 in sponsorships
```

## Anti-Patterns

- **Leading with your needs** — the proposal must show why this benefits the partner. They are making the decision.
- **Vague revenue projections** — "we could make a lot of money" is not a business case. Show the math with conservative assumptions.
- **No exit clause** — partnerships without exit terms create disputes. Define the off-ramp before the deal is signed.
- **Unequal effort, equal split** — if one party contributes 80% of the work, a 50/50 split creates friction. Match the split to the contribution.
- **Undefined IP ownership** — who owns the co-created assets, client relationships, and brand elements after the JV ends? Define it now.
- **Proposing without a relationship** — JV proposals work best when a working relationship already exists. Cold proposals to organizations with no prior contact rarely close.

## Recovery

- **Limited knowledge of the partner's priorities:** Recommend a scoping conversation before submitting the proposal. A 30-minute call to understand their current objectives sharpens the value proposition significantly.
- **Revenue projections are speculative:** Use conservative estimates (50% of optimistic scenario). Show three scenarios: conservative, base, optimistic.
- **Partner has significantly more to offer:** Adjust the split to reflect contribution value. A 60/40 or 70/30 split in the partner's favor may be the right structure and signals awareness of the imbalance.
- **User is uncertain about terms:** Default to a short-term pilot (90 days) with a renewal option. Lower commitment reduces hesitation on both sides.
