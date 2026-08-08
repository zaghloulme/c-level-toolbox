---
name: Company Culture Document
version: 1.8.5
description: "Writes company culture documents with values, behavioral definitions, rituals, and operating norms for team alignment and hiring."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Culture Document

## Core Principle

CULTURE IS NOT WHAT YOU SAY — IT IS WHAT YOU DO REPEATEDLY. A CULTURE DOCUMENT IS ONLY VALUABLE IF IT DESCRIBES REAL BEHAVIORS, NOT ASPIRATIONAL PLATITUDES.

## Phase 1: Discovery

Uncover the real culture before documenting it.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Organization size** | "How old is the organization and how many people?" | No default — must be provided |
| **Current values** | "Do you have stated values? If yes, what are they?" | No formal values |
| **What you reward** | "What behavior gets praised or rewarded here?" | No default |
| **What frustrates you** | "What behavior drives you crazy in team members or partners?" | No default |
| **Heroes** | "Describe someone who exemplifies what your organization stands for." | No default |
| **Decision filter** | "When you make a hard call, what principle guides you?" | No default |

### Culture Audit Questions

```
## Culture Reality Check

Answer honestly — not what you aspire to, but what is true today:

1. What behavior gets someone promoted or re-hired here?
2. What behavior gets someone fired or not renewed?
3. When there is a conflict between speed and quality, which wins?
4. When there is a conflict between the customer and the team member, which wins?
5. What would a new hire observe about how we work in their first week?
```

**GATE: Complete the discovery before writing the culture document.**

## Phase 2: Define Values

Articulate 3-5 core values with behavioral definitions.

### Value Definition Template

For each value, define three layers:

```
## Our Values

### Value 1: [Name — e.g., "Own It"]

**What it means:** [One sentence definition]

**What it looks like:**
- [Specific observable behavior — e.g., "You flag problems early instead of hoping they go away"]
- [Specific behavior — e.g., "You say 'I will handle that' and follow through without being reminded"]
- [Specific behavior]

**What it does NOT look like:**
- [Anti-behavior — e.g., "Blaming external factors when something goes wrong"]
- [Anti-behavior — e.g., "Waiting to be told what to do"]

**How we assess it:**
- In hiring: [Question or scenario that tests this value]
- In reviews: [Observable evidence of this value]
```

### Value Quality Check

Every value must pass these tests:
- **Is it real?** Can you point to 3 examples of this value in action?
- **Is it specific?** Would someone from another organization say "that is unique to you"?
- **Is it actionable?** Can a new hire understand what to do differently because of this value?
- **Is it honest?** Would your team agree this is true, not aspirational?

### Values to Avoid

These are not values — they are generic expectations:
- "Integrity" (everyone claims this)
- "Innovation" (meaningless without specifics)
- "Excellence" (too vague to act on)
- "Teamwork" (expected everywhere)

Instead, describe the specific version: "We ship fast and fix forward" is more useful than "Innovation."

**GATE: Present values for review before building the full document.**

## Phase 3: Write the Document

### Culture Document Template

```
# [Organization Name] Culture

**Last updated:** [Date]

---

## Who We Are

[2-3 paragraph narrative: What this organization stands for, who we serve, and how
we approach our work. Write in first person plural. Be specific and honest.]

## Our Values

### 1. [Value Name]
[Full definition with behaviors and anti-behaviors — from Phase 2]

### 2. [Value Name]
[Full definition]

### 3. [Value Name]
[Full definition]

## How Culture Shows Up Daily

### How We Communicate
[Specific norms — e.g., "We default to async. We write things down. We assume
good intent in written messages."]

### How We Make Decisions
[Decision framework — e.g., "We move fast with 80% certainty. We do not wait
for perfect information."]

### How We Give Feedback
[Feedback norms — e.g., "Directly and promptly. We do not save feedback for
quarterly reviews."]

### How We Handle Mistakes
[Error culture — e.g., "We own mistakes publicly, learn from them, and move on.
We do not punish honest errors."]

## Our Rituals

| Ritual | Frequency | Purpose |
|--------|-----------|---------|
| [e.g., Monday priorities share] | Weekly | Alignment and accountability |
| [e.g., Friday wins thread] | Weekly | Celebration and momentum |
| [e.g., Quarterly retrospective] | Quarterly | Continuous improvement |

## Who Thrives Here

This is a great place for people who:
- [Trait — e.g., "Want ownership, not hand-holding"]
- [Trait — e.g., "Communicate proactively, especially bad news"]
- [Trait]

This is NOT a great place for people who:
- [Anti-trait — e.g., "Need constant direction and approval"]
- [Anti-trait — e.g., "Avoid difficult conversations"]
- [Anti-trait]
```

**GATE: Present the full document for review.**

## Phase 4: Activate

Make the culture document a living part of the organization.

### Integration Points

- **Hiring:** Share the culture doc with candidates. Use it in interview questions.
- **Onboarding:** Review on Day 1. Discuss what each value means in practice.
- **Performance reviews:** Evaluate team members against values, not just output.
- **Decision-making:** Reference values when facing tough choices.
- **Recognition:** Call out when someone embodies a value.

### Culture Maintenance

- Review the document biannually — does it still reflect reality?
- Update when the team grows or the organization evolves
- Ask new hires after 30 days: "Does the culture doc match your experience?"
- If the answer is no, fix the culture or fix the document

## Anti-Patterns

- **Aspirational fiction** — writing the culture you wish you had instead of the one you actually have. Be honest first, then evolve.
- **Wall poster values** — "Integrity, Excellence, Innovation" on a poster with no behavioral definition changes nothing.
- **Too many values** — more than 5 values means none are prioritized. Focus.
- **Leadership does not follow them** — culture is set by what leaders do, not what they write. If leadership violates the values, the document is fiction.
- **One-time exercise** — culture evolves. A document written 3 years ago for a 5-person team does not apply to a 50-person organization.

## Recovery

- **Cannot identify values:** Use the audit questions. "What gets someone fired?" and "What gets someone praised?" reveal real values, even if unstated.
- **Team disagrees on values:** That is the conversation the culture doc exists to have. Run the discussion, find common ground, and document the agreements.
- **Current culture is unhealthy:** Acknowledge it honestly. Document what is, then define what you want and create a plan to bridge the gap.
- **Document feels corporate or stuffy:** Rewrite in the organization's natural voice. The document should sound like the business actually talks, not like an HR department.
