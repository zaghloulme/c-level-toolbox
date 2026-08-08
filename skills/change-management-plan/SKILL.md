---
name: Change Management Plan
version: 1.6.5
description: "Creates change management plans with stakeholder analysis, communication strategy, phased rollout timelines, and success metrics — for organizations rolling out process, tool, or structural transitions."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Change Management Plan

## Core Principle

PEOPLE DO NOT RESIST CHANGE — THEY RESIST BEING CHANGED WITHOUT INPUT, CONTEXT, OR PREPARATION. A CHANGE MANAGEMENT PLAN ADDRESSES ALL THREE.

## Phase 1: Define the Change

Clarify what is changing and why before planning the rollout.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Change description** | "What is changing? Be specific." | No default |
| **Reason for change** | "Why is this change happening now?" | No default |
| **Scope** | "Who is affected? (specific teams, departments, clients, vendors)" | No default — must be provided |
| **Timeline** | "When does this need to be fully implemented?" | 30 days |
| **Risk of not changing** | "What happens if this change does not happen?" | No default |
| **Previous attempts** | "Has this been tried before? What happened?" | First attempt |

### Change Impact Assessment

```
## Change Impact Assessment

**Change:** [Description]
**Type:** [Process / Tool / Structure / Policy / Pricing]
**Urgency:** [Immediate / Planned / Strategic]

| Impact Area | Current State | Future State | Impact Level |
|-------------|-------------|-------------|-------------|
| Daily workflow | [How it works now] | [How it will work] | High/Medium/Low |
| Tools/systems | [Current tools] | [New tools] | High/Medium/Low |
| Team roles | [Current structure] | [New structure] | High/Medium/Low |
| Client experience | [Current experience] | [New experience] | High/Medium/Low |
```

**GATE: Confirm the change definition before stakeholder analysis.**

## Phase 2: Stakeholder Plan

Identify who is affected and how to bring them along.

### Stakeholder Map

```
## Stakeholder Analysis

| Stakeholder | Impact Level | Current Attitude | Desired Attitude | Key Concern | Action |
|-------------|-------------|-----------------|-----------------|-------------|--------|
| [Name/Group] | High/Med/Low | Supportive/Neutral/Resistant | Supportive | [Concern] | [Approach] |
```

### Communication Plan

```
## Change Communication Plan

| Audience | Message | Channel | Timing | Owner |
|----------|---------|---------|--------|-------|
| Leadership team | Full context + rationale + timeline | Meeting | Week 1 | [Name] |
| Affected teams | What changes, why, and what support is available | Town hall + email | Week 1-2 | [Name] |
| Clients (if affected) | What changes for them + any impact on their service | Email | Week 2 | [Name] |
| Vendors (if affected) | Operational adjustments needed | Email | Week 2 | [Name] |
```

### Message Framework

For each audience, structure the message as:

1. **What is changing** (clear, specific, no jargon)
2. **Why it is changing** (the business reason + benefit to them)
3. **How it affects them** (specific changes to their experience or responsibilities)
4. **What support is available** (training, resources, escalation contacts)
5. **Timeline** (when it starts, key dates, when it is complete)

**GATE: Present stakeholder plan for review.**

## Phase 3: Transition Timeline

Build the phased rollout plan.

### Transition Phases

```
## Change Rollout Timeline

### Phase 1: Prepare (Week 1-2)
- [ ] Announce the change to all stakeholders with full context
- [ ] Distribute FAQ document
- [ ] Set up new tools/processes in parallel (do not retire old ones yet)
- [ ] Identify change champions across affected teams
- [ ] Schedule training sessions

### Phase 2: Pilot (Week 2-3)
- [ ] Selected team or department tests the new process/tool
- [ ] Collect feedback and fix issues
- [ ] Document common questions and solutions
- [ ] Update training materials based on pilot feedback

### Phase 3: Rollout (Week 3-4)
- [ ] Full transition to the new process/tool
- [ ] Old process remains available as fallback with a clear sunset date
- [ ] Daily check-ins during first week of full rollout
- [ ] Dedicated support channel for questions

### Phase 4: Stabilize (Week 4+)
- [ ] Retire old process/tool on sunset date
- [ ] Address remaining issues
- [ ] Document the new process as the organizational standard
- [ ] Acknowledge the team's effort formally
```

### FAQ Template

```
## Change FAQ: [Change Name]

**Q: Why are we making this change?**
A: [Answer]

**Q: When does this take effect?**
A: [Answer]

**Q: What do I need to do differently?**
A: [Answer]

**Q: What if I encounter problems with the new [tool/process]?**
A: [Answer]

**Q: Can we revert to the old process?**
A: [Answer]
```

## Phase 4: Sustain

Ensure the change sticks and delivers the intended results.

### Success Metrics

Define 2-3 metrics that confirm the change is working:

```
## Change Success Metrics

| Metric | Before Change | Target (30 days) | Target (90 days) |
|--------|-------------|-----------------|-----------------|
| [Metric] | [Baseline] | [Target] | [Target] |
```

### Post-Change Review

At 30 and 90 days:
1. Are people using the new process or tool consistently?
2. Have the expected benefits materialized?
3. What unexpected issues have surfaced?
4. What additional support is needed?

## Anti-Patterns

- **Announcing without context** — "Starting Monday, we use [new tool]" generates immediate resistance. Lead with the reason.
- **Big bang rollout** — switching everything overnight maximizes disruption. Phase the transition.
- **Ignoring resistance** — resistance is feedback. Understand it, address it, do not dismiss it.
- **No training** — expecting people to figure it out guarantees frustration and unofficial workarounds.
- **Too many changes at once** — stacking multiple major changes in one quarter causes adoption failure across all of them.

## Recovery

- **Team is actively resisting:** Move to one-on-one conversations rather than group announcements. Understand individual concerns before re-communicating.
- **Change was rolled out too fast:** Pause, acknowledge the disruption honestly, and reintroduce with a proper timeline and support structure.
- **Change is not delivering expected results:** Separate adoption failure (people not using it) from a strategy failure (the change itself was the wrong call). Diagnose before correcting.
- **Stakeholders were not consulted before rollout:** It is not too late. Run a structured feedback session, incorporate what is actionable, and adjust the plan visibly.
