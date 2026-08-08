---
name: Performance Review System
version: 2.2.7
description: "Builds performance review templates with self-assessment, manager feedback, competency ratings, goal tracking, and development planning — for quarterly, biannual, or annual employee review cycles."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Performance Review

## Core Principle

A PERFORMANCE REVIEW IS NOT A REPORT CARD — IT IS A STRUCTURED CONVERSATION THAT ALIGNS EXPECTATIONS, RECOGNIZES PROGRESS, AND SETS DIRECTION FOR GROWTH.

## Phase 1: Review Design

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Team size** | "How many people will you be reviewing?" | No default — must be provided |
| **Review frequency** | "How often? (quarterly, biannual, annual)" | Biannual |
| **Roles** | "What roles are being reviewed?" | No default |
| **Current process** | "Do you have an existing review process?" | None |
| **Key success metrics** | "How do you measure success for these roles?" | No default |
| **Rating system** | "Preference: numbered scale, descriptive labels, or no ratings?" | Descriptive labels |

### Rating Scale

```
## Performance Rating Scale

| Rating | Label | Definition |
|--------|-------|-----------|
| 5 | Exceptional | Consistently exceeds expectations. Top performance for the role. |
| 4 | Exceeds Expectations | Regularly goes beyond what is asked. Strong contributor. |
| 3 | Meets Expectations | Delivers reliably. Solid, dependable performance. |
| 2 | Needs Improvement | Falls short in specific areas. Defined support and improvement plan required. |
| 1 | Unsatisfactory | Significantly below standards. Immediate action required. |
```

**GATE: Confirm review design before building templates.**

## Phase 2: Build Templates

### Self-Assessment Template

```
## Self-Assessment: [Name]

**Review period:** [Date range]
**Role:** [Title]

### Accomplishments
List your top 3-5 accomplishments this period. Include specific outcomes and numbers.

1.
2.
3.

### Goals Review
For each goal set last period:

| Goal | Target | Result | Self-Rating |
|------|--------|--------|-------------|
| [Goal 1] | [Target] | [Actual result] | [1-5] |
| [Goal 2] | [Target] | [Actual result] | [1-5] |

### Challenges
What obstacles did you face? What would you do differently?

### Development
What skills did you build this period? What do you want to develop next?

### Feedback for Management
What support, resources, or changes would help you be more effective?
```

### Manager Review Template

```
## Performance Review: [Name]

**Review period:** [Date range]
**Reviewer:** [Manager name]
**Role:** [Title]
**Date:** [Date]

---

### Performance Summary

**Overall rating:** [1-5 with label]

### Core Competencies

| Competency | Rating | Evidence |
|-----------|--------|----------|
| Quality of work | [1-5] | [Specific examples] |
| Reliability and deadlines | [1-5] | [Specific examples] |
| Communication | [1-5] | [Specific examples] |
| Initiative and ownership | [1-5] | [Specific examples] |
| [Role-specific competency] | [1-5] | [Specific examples] |

### Goal Achievement

| Goal | Target | Result | Rating | Comments |
|------|--------|--------|--------|----------|
| [Goal 1] | [Target] | [Actual] | [1-5] | [Context] |

### Strengths
What this person does well — specific examples only.

1.
2.
3.

### Areas for Growth
Where this person should focus development — specific and constructive.

1.
2.

### Next Period Goals

| Goal | Success Metric | Target Date |
|------|---------------|-------------|
| [Goal 1] | [Measurable outcome] | [Date] |
| [Goal 2] | [Measurable outcome] | [Date] |
| [Goal 3] | [Measurable outcome] | [Date] |

### Development Plan

| Skill to Develop | Action | Support Needed | Timeline |
|-----------------|--------|---------------|----------|
| [Skill] | [Training, stretch project, mentoring] | [What manager will provide] | [When] |

---

### Signatures

**Employee:** _______________ Date: ___
**Manager:** _______________ Date: ___
```

**GATE: Present templates for review and customization.**

## Phase 3: Conversation Guide

### Review Meeting Structure (45-60 minutes)

```
1. Opening (5 min) — Set a constructive tone. State the purpose.
2. Self-assessment discussion (10 min) — Let the employee share their view first.
3. Manager feedback (15 min) — Share ratings, strengths, and growth areas with examples.
4. Goal review (10 min) — Discuss progress on previous goals.
5. Goal setting (10 min) — Set goals for next period collaboratively.
6. Development planning (5 min) — Agree on specific development actions.
7. Close (5 min) — Summarize key points and confirm next steps.
```

### Underperformance Conversation Framework

For ratings of 1-2:

1. State the specific behavior or result — not character or personality
2. Explain the impact on the team or organization
3. Listen to their perspective
4. Collaboratively define what needs to change, with specifics
5. Set a clear improvement timeline with check-ins
6. Confirm the consequences if improvement does not happen by the deadline

## Phase 4: Follow Through

```
## Post-Review Checklist

- [ ] Finalize review document and file in HR records
- [ ] Send copy to the employee
- [ ] Schedule mid-period check-in
- [ ] Initiate any agreed development actions (training enrollment, project assignment)
- [ ] Update compensation if tied to review cycle
```

### Review Calendar

```
| Step | Timing |
|------|--------|
| Distribute self-assessment forms | Week 1 |
| Self-assessments due | Week 2 |
| Manager reviews completed | Week 3 |
| Review meetings held | Week 3-4 |
| Goals and development plans finalized | Week 4 |
| Mid-period check-ins | 6 weeks before next review |
```

## Anti-Patterns

- **Surprise feedback** — nothing in a formal review should be news. Give feedback throughout the period, not only in the review.
- **Recency bias** — rating based on the last two weeks instead of the full review period. Keep a running notes doc.
- **Vague feedback** — "You need to communicate better" is not feedback. "The client escalation in October was the third time a scope change was not flagged until delivery" is.
- **Rating everyone 3** — giving everyone "Meets Expectations" avoids difficult conversations but helps no one. Differentiate honestly.
- **No follow-through** — a review without goal tracking and a mid-period check-in is a wasted hour.

## Recovery

- **Never conducted a formal review before:** Start with three questions — what went well, what could improve, what are the goals for next period. Add structure in subsequent cycles.
- **Employee disagrees with the rating:** Listen fully. Ask for specific examples supporting their view. Adjust if warranted; explain your reasoning if not. Document the disagreement.
- **Reviewing contractors rather than employees:** Adapt to a project-based model — review after each major project or quarterly, focused on deliverable quality, communication, and scope management.
- **No metrics to evaluate against:** Set metrics immediately for the next review period. For this review, use qualitative assessment with specific behavioral examples.
