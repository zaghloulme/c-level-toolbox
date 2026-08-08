---
name: One-on-One Meeting Template
version: 1.5.0
description: "Designs recurring 1:1 meeting templates with check-in questions, priorities alignment, career development discussion, and action item tracking — for consistent, trust-building manager-report conversations."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# One-on-One Template

## Core Principle

THE 1:1 IS THE TEAM MEMBER'S MEETING, NOT YOURS — IT EXISTS TO SURFACE WHAT YOU WOULD NOT HEAR OTHERWISE, BUILD TRUST, AND REMOVE OBSTACLES FROM THEIR PATH.

## Phase 1: Meeting Design

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Team member role** | "What role is this 1:1 for?" | No default |
| **Relationship stage** | "How long have you worked together?" | New relationship |
| **Frequency** | "How often will you meet? (weekly, biweekly)" | Weekly |
| **Duration** | "How long is each meeting?" | 30 minutes |
| **Format** | "Video, phone, or in-person?" | Video |
| **Current pain** | "What is not working in your current 1:1s, if any?" | No structure in place |

**GATE: Confirm meeting parameters before building the template.**

## Phase 2: Build Template

### Standard 1:1 Template (30 minutes)

```
## 1:1 Meeting: [Manager] + [Team Member]

**Date:** [Date]
**Duration:** 30 minutes

---

### Their Updates (10 min)
Let the team member lead. Ask open questions. Listen more than you talk.

- How are you doing this week?
- What is going well?
- What is challenging right now?
- Is there anything blocking your work?

### Priorities Alignment (10 min)
Confirm what matters most and clear obstacles.

- What are your top priorities this week?
- Are they the right priorities? (Validate or redirect)
- What do you need from me to move them forward?
- Any decisions you need me to make?

### Growth and Development (5 min)
Rotate through these topics — pick 1-2 per meeting, not all.

- What did you learn this week?
- Is there a project or opportunity you want to take on?
- How are you feeling about your career trajectory here?
- What skill do you want to develop next?

### Action Items (5 min)
Both parties leave with clear commitments.

| Action | Owner | Due |
|--------|-------|-----|
| | | |
| | | |

### Notes for Next Meeting
[Carry-forward items, topics to revisit]
```

### Question Library

Rotate to keep 1:1s from becoming stale:

**Engagement and Satisfaction:**
- What is energizing you right now?
- What is draining you?
- On a scale of 1-10, how engaged are you at work? What would move that one point higher?

**Feedback:**
- What is one thing I could do differently as your manager?
- Is there anything you are not getting feedback on but wish you were?
- What feedback do you have for the team or the organization?

**Strategy and Alignment:**
- Do you feel clear on your priorities? Where is it murky?
- Are you spending time on the right things?
- What would you stop doing if you could?

**Relationship and Trust:**
- Is there anything you have been meaning to bring up but have not?
- Do you have enough autonomy in your role?
- How can I better support you?

**GATE: Present template for review and customization.**

## Phase 3: Running the Meeting

### Before the Meeting

- Both parties add topics to a shared document 24 hours before
- Review notes from the last 1:1 and follow up on previous action items first
- Come prepared to listen and unblock, not to brief

### During the Meeting

- Start with their agenda, not yours
- Target ratio: them talking 70%, you talking 30%
- Take notes on commitments and follow-ups in real time
- If they say "everything is fine" — ask specifically: "How did the [project] go this week?"
- Address difficult topics in the first half, not the last 2 minutes

### After the Meeting

- Summarize action items in the shared document within 1 hour
- Follow through on your commitments before the next 1:1
- If a sensitive topic came up, check in via message within 48 hours

### Shared Running Document

```
## 1:1 Running Document: [Manager] + [Team Member]

### [Date]
Their updates:
Priorities:
Growth topic:
Action items:

### [Previous Date]
...
```

## Phase 4: Cadence Adjustments

| Relationship Stage | Frequency | Duration |
|-------------------|-----------|---------|
| New team member (first 90 days) | Weekly | 45 min |
| Established (90+ days) | Weekly or biweekly | 30 min |
| Senior/autonomous | Biweekly | 25 min |
| During change or uncertainty | Weekly (regardless of seniority) | 30 min |

### Quarterly Relationship Check

Every 3 months, ask:
1. "Are our 1:1s useful? What would make them better?"
2. "Is the cadence right for where you are?"
3. "Is there a topic we keep avoiding that we should address directly?"

## Anti-Patterns

- **Status update meetings** — if the entire 1:1 is project updates, it is not a 1:1. Status updates belong in standups or async tools.
- **Manager talks the whole time** — this is their meeting. Your role is to ask, listen, and unblock.
- **Canceling regularly** — canceling 1:1s signals that their development is not a priority.
- **Only holding 1:1s when something is wrong** — consistency is what makes 1:1s useful. Irregular 1:1s create the impression they only happen when there is a problem.
- **Same questions every week** — rotate from the question library. Predictability kills honesty.

## Recovery

- **Team member says nothing is wrong (but something clearly is):** Build trust over time. Ask specific questions about specific work rather than open-ended ones. "How did the [specific situation] land with the client?" yields more than "How are things?"
- **1:1s feel like a waste of time:** Ask the team member what they would find useful and redesign the template together. A template imposed without input often fails.
- **Too many direct reports for weekly 1:1s:** Biweekly is the minimum. If even that is not feasible, the span of control is too large and the structure needs to change.
- **Difficult feedback must be delivered:** Do not save it for the 1:1. Address it closer to the event. But if it comes up during a 1:1, address it in the first half, not the last two minutes.
