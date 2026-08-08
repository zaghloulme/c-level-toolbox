---
name: Delegation Framework
version: 1.8.5
description: "Builds task delegation systems with responsibility matrices, handoff templates, accountability tracking, and escalation protocols — for executives and managers transferring ownership to functional leads and team members."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Delegation Framework

## Core Principle

DELEGATION IS NOT TASK ASSIGNMENT — IT IS OWNERSHIP TRANSFER. A TASK IS NOT DELEGATED UNTIL THE PERSON KNOWS WHAT TO DO, WHY IT MATTERS, HOW TO DO IT, WHEN IT IS DUE, AND WHAT DONE LOOKS LIKE.

## Workflow

### Phase 1: Audit Current Tasks

List everything currently handled at the leadership level, then categorize:

**The 4-Zone Framework:**

| Zone | Description | Action |
|------|-------------|--------|
| **Zone of Genius** | Only this role can do this; highest strategic value | KEEP — protect this time |
| **Zone of Competence** | Can be done here, but others can do it equally well | DELEGATE — train and hand off |
| **Zone of Frustration** | Can be done here but at the cost of time and energy | DELEGATE FIRST — this drains capacity |
| **Zone of Incompetence** | Not the right person for this task | DELEGATE or ELIMINATE |

Walk through the task list and place each item in a zone.

### Phase 2: Build the Delegation Matrix

Create a responsibility matrix for all delegatable tasks:

```
DELEGATION MATRIX
=================

Task                      | Current Owner | Frequency  | Time/Task | Priority | SOP Exists? | Delegate To
--------------------------|---------------|------------|-----------|----------|-------------|------------
[Task 1]                  | [Role]        | [Daily]    | [X min]   | High     | No          | [Role]
[Task 2]                  | [Role]        | [Weekly]   | [X min]   | Medium   | Partial     | [Role]
[Task 3]                  | [Role]        | [Monthly]  | [X hrs]   | High     | Yes         | [Role]

WEEKLY TIME RECLAIMED IF FULLY DELEGATED: [X] hours
```

### Phase 3: Create Handoff Templates

For each delegated task, create a handoff document:

**Task Handoff Template:**

```
TASK HANDOFF: [Task Name]
=========================

WHAT: [One sentence describing the task]
WHY: [Why this task matters to the business — context, not just instructions]
WHO: [Who is now responsible]
WHEN: [Frequency and deadline — e.g., "Every Monday by 12:00"]
HOW: [Step-by-step instructions OR link to SOP]
DONE LOOKS LIKE: [Specific, observable criteria for completion]
TOOLS NEEDED: [Systems, access, accounts — with access instructions]
ESCALATION: [When to escalate vs. handle independently]
REVIEW PERIOD: [How long work will be reviewed before full autonomy]

EXAMPLE OF GOOD OUTPUT: [Link or description of a completed task done well]
EXAMPLE OF BAD OUTPUT: [Common mistakes to avoid]
```

### Phase 4: Set Up Accountability and Communication

**Communication Structure:**

```
DELEGATION COMMUNICATION SYSTEM
================================

DAILY (async):
- Delegate posts a 3-line update:
  1. What I completed today
  2. What I am working on tomorrow
  3. Any blockers or questions

WEEKLY (15-minute sync):
- Review completed tasks against the matrix
- Address any quality issues
- Adjust priorities for the coming week
- Acknowledge strong work explicitly

ESCALATION RULES:
- Level 1 (handle independently): Routine decisions within documented guidelines
- Level 2 (message before acting): Client-facing issues, financial errors, scope changes
- Level 3 (stop and escalate immediately): Legal exposure, security incidents, reputational risk

FEEDBACK CADENCE:
- Week 1-2: Review every deliverable, give detailed feedback
- Week 3-4: Review 50% of deliverables, spot-check the rest
- Month 2+: Review only flagged items, trust the process
```

### Phase 5: Define the Autonomy Ladder

Map each task to an autonomy level and promote deliberately over time:

```
AUTONOMY LADDER
================

Level 1: "Follow the SOP exactly" (Week 1)
         - Follow the handoff document step by step
         - Ask before deviating
         - All output reviewed before use

Level 2: "Do it, then show me before it goes out" (Week 2-3)
         - Task completed independently
         - Reviewed before delivery or publication
         - Feedback on quality, not process

Level 3: "Do it and tell me what you did" (Week 4-6)
         - Task completed and delivered without pre-approval
         - Summary sent after completion
         - Spot-checks only

Level 4: "Full ownership" (Month 2+)
         - Complete autonomy within scope
         - Only exceptions escalated
         - Monthly metrics reviewed, not individual tasks

PROMOTION CRITERIA:
- Zero critical errors for 2 consecutive weeks
- Proactively identifies and solves problems
- Asks clarifying questions — but not the same question twice
```

## Example 1: Executive Delegating to Functional Leads

**Context:** Division head currently handling sales oversight, financial reporting, HR decisions, and operational reviews. Goal: focus on strategic partnerships and board reporting.

```
ZONE AUDIT:
Zone of Genius (KEEP):
- Board and investor reporting (3 hrs/week)
- Strategic partnership conversations (4 hrs/week)
- Final approval on key hires and major contracts (2 hrs/week)

Zone of Competence (DELEGATE):
- Weekly sales pipeline reviews → Sales Director
- Monthly financial reporting compilation → CFO
- Vendor contract renewals → COO

Zone of Frustration (DELEGATE FIRST):
- HR escalations and routine approvals → HR Director
- Operational exception handling → COO
- Scheduling and meeting coordination → Executive Assistant

TOTAL DELEGATABLE: ~18 hrs/week
```

## Example 2: Department Head Building a RACI

**Context:** Operations head scaling a team from 3 to 8 people. Tasks are unclear, ownership is disputed, and work keeps bouncing back.

```
RACI MATRIX
===========
(R=Responsible, A=Accountable, C=Consulted, I=Informed)

Task                      | Dept Head | Team Lead | Analyst | Specialist | Coordinator
--------------------------|-----------|-----------|---------|------------|------------
Process design            | A         | R         | C       | -          | -
Reporting and metrics     | I         | A         | R       | -          | C
Vendor management         | A         | C         | -       | R          | I
Client escalations        | A         | R         | -       | C          | I
Day-to-day scheduling     | I         | -         | -       | -          | R,A

DEPARTMENT HEAD ROLE SHIFT:
Before: Involved in all tasks
After: Accountable for outcomes, not responsible for execution
Time reclaimed: 12-15 hrs/week
Reinvested into: Cross-functional alignment and strategic planning
```

## Recovery and Fallback

- If the task list cannot be articulated, prompt: "Walk through the last week hour by hour. What was actually done?" Build the list from real activity.
- If there is resistance to delegating ("no one will do it right"), start with one low-stakes task for two weeks. Build trust through direct experience.
- If delegation breaks down (work comes back wrong), check: Was the SOP clear? Was "done" defined? If yes, it may be a fit issue. If no, fix the handoff first.
- If reverse delegation keeps happening (team brings tasks back to leadership), enforce escalation rules and ask: "What would you do if I were unreachable for a week?"

## Constraints

- **NEVER delegate Zone of Genius tasks** — those are the highest-value activities only you can do
- **ALWAYS include a handoff template** — verbal instructions are not delegation
- **ALWAYS include an autonomy ladder** — micromanagement defeats the purpose
- Every handoff must include "DONE LOOKS LIKE" criteria — without it, quality expectations are invisible
- Escalation rules are mandatory — without them, everything escalates
- Start with 3-5 tasks in the first month — do not hand off everything at once
- Minimum review period for any new delegate: two weeks of supervised output
