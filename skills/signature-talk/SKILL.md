---
name: Signature Keynote Talk Builder
version: 1.4.0
description: "Develops signature keynote talks with modular sections, audience customization guides, and delivery notes for conferences, summits, and executive speaking engagements."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Signature Talk

## Fallback for thin input

**If the user has not supplied their idea, do NOT ask a wall of questions.** Produce a realistic representative 30-minute signature keynote using a plausible topic for a mid-sized B2B software company CEO (~250 people, ~$40M revenue) — e.g. "how mid-market SaaS wins the enterprise AI wave without losing its soul" — with all five modular sections, an audience customization guide (investor / client / conference / internal), speaker notes card, slide outline, and quality checklist. Deliver every section in full inline. Clearly label the assumed topic at the top, and after delivering the talk, offer to swap in the user's real topic.

## Delivery guard

**Never truncate. Never substitute a table-of-contents for actual content.** If the full deliverable would exceed a single message, deliver Pass 1 (Modules 1-2, plus the audience customization guide) in full, then ask "Continue with Modules 3-5, speaker notes, and quality checklist?" before Pass 2. Both passes must be complete prose in-chat, not summaries.

## Core Principle

A SIGNATURE TALK DELIVERS ONE POWERFUL IDEA THROUGH A REPEATABLE STRUCTURE THAT WORKS WHETHER YOU HAVE 15 MINUTES OR 60.

## Phase 1: Brief

Gather the inputs that define the talk. No brief, no outline.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Core message** | "What is the ONE idea you want every audience member to remember?" | No default — must be provided |
| **Target audience** | "Who is in the room? Industry, role, seniority level." | Senior leaders and executives |
| **Talk length** | "How long is your typical slot? 15, 30, 45, or 60 minutes?" | 30 minutes |
| **Desired outcome** | "What should the audience DO after your talk? Reach out, apply the framework, change behavior?" | Apply the framework and follow up |
| **Personal story** | "What personal experience or case study anchors your credibility on this topic?" | No default — must be provided |
| **Speaking context** | "Where do you give this talk? Industry conferences, internal events, webinars?" | Industry conferences |

**GATE: Confirm the brief before building the outline.**

## Phase 2: Outline

Build the talk structure using the Signature Talk Framework:

### Framework (5 Modules)

1. **The Hook (10% of time)** — Open with a story, surprising stat, or provocative question that earns attention
2. **The Problem (20%)** — Name the pain the audience feels. Make them nod. Use specific language they use themselves
3. **The Framework (40%)** — Deliver your core methodology in 3-5 steps. This IS the signature content
4. **The Proof (20%)** — Case studies, results, before/after examples that demonstrate the framework works
5. **The Bridge (10%)** — Connect the talk to the desired action. Not a hard sell — a natural next step

### Outline Format

```
**Talk Title:** [Working title]
**Core Message:** [One sentence]
**Length:** [Time]

**Module 1: The Hook** (~[X] min)
- Opening story/stat/question
- Transition to problem

**Module 2: The Problem** (~[X] min)
- Pain point 1
- Pain point 2
- "What if" pivot to solution

**Module 3: The Framework** (~[X] min)
- Step 1: [Name] — [key point]
- Step 2: [Name] — [key point]
- Step 3: [Name] — [key point]

**Module 4: The Proof** (~[X] min)
- Case study / results
- Audience-relevant example

**Module 5: The Bridge** (~[X] min)
- Recap core message
- CTA and next step
```

**GATE: Present the outline and wait for approval before writing the full script.**

## Phase 3: Write

Draft the full talk script with these rules:

- **Conversational tone** — write for the ear, not the eye. Short sentences. Contractions welcome.
- **Stage directions** — include delivery notes in brackets: [PAUSE], [SLIDE: before/after image], [ASK AUDIENCE]
- **Transitions** — every module ends with a clear bridge sentence into the next
- **Time stamps** — note approximate timing at each module break
- **Audience interaction** — include at least one moment per module where the speaker engages the audience (question, show of hands, reflection prompt)

### Modular Adaptation Guide

After the full script, provide a guide for adjusting the talk length:

| Slot | What to Cut | What to Keep |
|------|------------|--------------|
| 15 min | Cut Module 4 (Proof), shorten Problem to 1 pain point | Hook, Framework (abbreviated), Bridge |
| 30 min | Full structure as written | All modules |
| 45 min | Expand Framework with deeper examples, add Q&A | All modules + audience Q&A |
| 60 min | Add workshop element after Framework | All modules + interactive exercise |

## Phase 4: Polish

### 1. Speaker Notes Card

Create a condensed reference card with:
- Opening line (memorized)
- 3-5 framework step names
- Key transition phrases
- Closing line and CTA (memorized)

### 2. Slide Outline

Suggest a slide structure (not full slides):
- Recommended slide count for the talk length
- Key slides: title, problem stat, framework overview, each step, case study result, CTA
- Design direction: minimal text, one idea per slide, high-contrast visuals

### 3. Talk Quality Checklist

```
## Signature Talk Checklist

- [ ] Opens with a hook that earns attention in the first 30 seconds
- [ ] Core message is stated explicitly at least twice
- [ ] Framework has 3-5 named steps (memorable and repeatable)
- [ ] At least one concrete case study with specific results
- [ ] Audience interaction in every module
- [ ] CTA is clear, single, and non-pushy
- [ ] Talk can be shortened to 15 min by cutting modules (modular design)
- [ ] No jargon the target audience would not immediately understand
- [ ] Closing line is rehearsal-ready (scripted word for word)
```

## Example

**Brief:**
- Core message: "Most transformation programs fail not because of the strategy but because of the transition architecture"
- Audience: CHROs and COOs at a leadership conference
- Length: 30 minutes
- CTA: Download the transition architecture framework

**Hook excerpt:**
"In 2019, a 12,000-person organization spent $40M on a transformation program. Two years later, 70% of the changes had been reversed. The strategy was sound. The consultants were excellent. What failed was everything that happened between the plan and the people. [PAUSE] Today I'm going to show you what that gap looks like — and how to close it."

## Anti-Patterns

- **No clear framework** — talks without a named, repeatable methodology are forgettable. Give it steps. Give it a name.
- **Selling from the stage** — the Bridge module is an invitation, not a pitch. Audiences shut down at hard sells.
- **Reading slides** — the script is for the speaker's mouth. Slides support visually. Never duplicate.
- **Too many ideas** — one core message. If you cannot say it in one sentence, narrow it.
- **Skipping the personal story** — frameworks without personal stakes feel academic. The story is what makes it yours.

## Recovery

- **No personal story:** Use a well-documented case study from your experience. Note this weakens the "signature" quality — personal stakes matter.
- **Framework feels generic:** Ask what the speaker does differently than everyone else in their field. Build the framework around that specific differentiator.
- **Talk rejected twice:** Ask which module feels wrong. Isolate whether the issue is the hook, the framework depth, or the CTA.
- **Multiple CTAs requested:** Push back. One CTA converts. Offer to create a landing page that houses multiple options instead.
