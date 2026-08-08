---
name: Service Productization Framework
version: 1.6.0
description: "Converts custom services into fixed-scope, fixed-price offerings with standardized deliverables, pricing tiers, delivery processes, and sales page copy for scalable, repeatable revenue."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Service Productization

## Fallback for thin input

**If the user has not supplied a specific service to productize, do NOT ask a wall of questions.** Produce a realistic representative productization using a plausible service for a mid-sized B2B software company (~250 people, ~$40M revenue) — e.g. an "implementation onboarding" service — with full tier structure, fixed scope, fixed price, and delivery process. Clearly label the assumed service at the top, and after delivering the framework, offer to redo it against the user's real service.

## Core Principle

A PRODUCTIZED SERVICE HAS A CLEAR SCOPE, A FIXED PRICE, AND A REPEATABLE PROCESS — THE CLIENT KNOWS EXACTLY WHAT THEY GET, AND YOU KNOW EXACTLY WHAT YOU DELIVER.

## Phase 1: Service Analysis

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Current service** | "What service do you offer that you want to productize?" | No default — must be provided |
| **Most common request** | "What do 80% of your clients ask for?" | No default — must be provided |
| **Typical timeline** | "How long does this service usually take to deliver?" | 1-2 weeks |
| **Current pricing** | "What do you typically charge for this?" | Varies per engagement |
| **Pain point** | "What frustrates you most about delivering this service today?" | Custom scoping and quoting for every client |

**GATE: Confirm the service and common request pattern before productizing.**

## Phase 2: Package Design

### Identifying the Core Offer

Strip the service down to the repeatable, high-value deliverable:

1. **List everything you do** for a typical client in this service area
2. **Identify the 80/20** — what 20% of activities deliver 80% of the value?
3. **Remove customization** — what can be standardized without hurting outcomes?
4. **Define the boundary** — what is included and what requires a separate engagement?

### Package Structure

Create 1-3 tiers:

```
## [Service Name] Packages

### Starter — $[price]
**Best for:** [Who this is for]
**Includes:**
- [Deliverable 1]
- [Deliverable 2]
- [X] rounds of revisions
**Timeline:** [X] business days
**Not included:** [Key exclusion]

### Professional — $[price] ← Most Popular
**Best for:** [Who this is for]
**Includes:**
- Everything in Starter, plus:
- [Additional deliverable]
- [Additional deliverable]
- [X] rounds of revisions
**Timeline:** [X] business days

### Premium — $[price]
**Best for:** [Who this is for]
**Includes:**
- Everything in Professional, plus:
- [High-value add-on]
- [Priority support or faster timeline]
- [Strategy session or ongoing support]
**Timeline:** [X] business days
```

### Pricing Strategy

- Price based on value delivered, not hours spent
- The middle tier should be the target — price it to be the obvious choice
- Bottom tier covers costs and serves as an entry point
- Top tier exists for premium buyers and makes the middle tier look reasonable

## Phase 3: Delivery Process

### Standard Operating Procedure

```
## Delivery SOP — [Service Name]

### Step 1: Client Onboarding
- Client purchases package or completes intake form
- Automated welcome email with timeline and next steps
- Collect all required materials (questionnaire, assets, access)

### Step 2: Production
- Day 1-2: [Initial work]
- Day 3-5: [Core deliverable creation]
- Day 5-7: [Quality check and internal review]

### Step 3: Delivery
- Send first draft to client with review instructions
- Client provides feedback within [X] business days
- Implement revisions (round 1 of [X] included)

### Step 4: Finalization
- Deliver final files in specified formats
- Send follow-up email with usage tips or next steps
- Request testimonial or case study (7 days post-delivery)
```

### Intake Questionnaire

Create a standardized intake form that replaces custom discovery calls:

- What is your organization and who is your target audience?
- What is the primary goal for this [deliverable]?
- Share any examples or references you prefer
- What brand guidelines or assets should we use?
- Any deadlines or constraints?

## Phase 4: Sales Page & Positioning

### Service Page Copy Structure

```
## [Service Name] — [Outcome-Focused Tagline]

### The Problem
[2-3 sentences about what the client struggles with]

### The Solution
[1-2 sentences about your productized service]

### What You Get
[Package breakdown — Starter / Professional / Premium]

### How It Works
1. [Step 1 — buy or book]
2. [Step 2 — provide info]
3. [Step 3 — receive deliverable]

### Results
[2-3 client results or testimonials]

### FAQ
[3-5 common questions]

### [CTA Button: "Get Started" / "Choose Your Package"]
```

### Positioning vs. Custom Services

| Custom Service | Productized Service |
|---------------|-------------------|
| "Let's hop on a call to discuss" | "Here's what you get — buy now" |
| Proposal required | Fixed price, instant purchase |
| Variable timeline | Guaranteed delivery date |
| Scope negotiation | Clear boundaries |
| Unlimited revisions | Defined revision rounds |

## Anti-Patterns

- **Productizing too much at once** — start with one service, perfect the process, then expand. Do not launch 5 packages simultaneously.
- **Including everything** — productization requires saying no. Custom strategy, unlimited revisions, and ongoing support cannot all be in the base package.
- **Pricing too low** — fixed pricing should be more profitable than hourly work because your efficiency improves over time.
- **No intake process** — without a standardized questionnaire, you end up on custom discovery calls, defeating the purpose.
- **Rigid packages with no upsell path** — always offer a way for clients to add on or upgrade.

## Recovery

- **Service is too complex to productize:** Productize one piece of it — the most common, repeatable deliverable. Keep the rest as custom work.
- **Clients want customization:** Offer the productized package as the base with clearly priced add-ons for custom elements.
- **Not enough volume to justify standardization:** Build the process and templates anyway. When volume comes, you will be ready.
- **Delivery quality varies:** Tighten the SOP, create templates and checklists, and build in a quality review step before delivery.
- **Clients choosing only the cheapest tier:** Adjust the tier structure — make the middle tier significantly more valuable than the bottom.
