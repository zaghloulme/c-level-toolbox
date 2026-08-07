---
name: Quality Assurance Checklist
version: 1.5.0
description: "Creates QA checklists for products, services, or content with pass/fail criteria, review workflows, defect tracking, and continuous improvement cycles — for standardizing quality control across teams and delivery processes."
---

# Quality Assurance Checklist

## Core Principle

QUALITY IS NOT INSPECTED IN AT THE END — IT IS BUILT IN AT EVERY STAGE. A QA CHECKLIST IS THE LAST SAFETY NET, NOT THE FIRST LINE OF DEFENSE.

## Phase 1: Scope

Define what is being quality-checked and the standards it must meet.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Deliverable type** | "What are you QA-checking? (product, service delivery, content, digital product, client work)" | No default — must be provided |
| **Quality standards** | "What does 'ready to deliver' look like? Any specific standards or client requirements?" | Professional quality, error-free |
| **Common defects** | "What goes wrong most often? What complaints have been received?" | No default — critical input |
| **Who reviews** | "Who performs the QA check? (creator, team member, department lead)" | Self-review |
| **Frequency** | "How often is this deliverable produced?" | No default |

**GATE: Confirm scope and standards before building the checklist.**

## Phase 2: Build Checklist

Create a comprehensive QA checklist with pass/fail criteria.

### Checklist Structure

Every QA checklist has three layers:

```
## QA Checklist: [Deliverable Name]

**Version:** 1.0
**Last updated:** [Date]
**Reviewer:** [Name/Role]

### Critical Items (Must pass — blocks delivery)
- [ ] [Check item] — **Pass criteria:** [Specific, measurable standard]
- [ ] [Check item] — **Pass criteria:** [Specific, measurable standard]

### Important Items (Should pass — flag if failed)
- [ ] [Check item] — **Pass criteria:** [Standard]
- [ ] [Check item] — **Pass criteria:** [Standard]

### Nice-to-Have Items (Improve if time permits)
- [ ] [Check item] — **Pass criteria:** [Standard]

### Sign-Off
- [ ] All critical items pass
- [ ] Important items reviewed (failures documented)
- **Approved by:** _______________
- **Date:** _______________
```

### Category-Specific Checklists

**Content QA:**
- Spelling and grammar (zero errors)
- Brand voice and style consistency
- All links functional
- Images properly sized and alt-tagged
- CTA present and working
- Mobile formatting checked

**Service Delivery QA:**
- Deliverable matches scope or SOW
- All promised components included
- Client-specific requirements applied
- Delivery format matches client preference
- Follow-up communication drafted

**Product QA:**
- Product matches specification and listing description
- Packaging intact and correctly labeled
- All components included
- Functionality tested
- Shipping and logistics details verified

**GATE: Present the checklist for approval before adding workflow elements.**

## Phase 3: Workflow

Design the review process around the checklist.

### Review Workflow

```
## QA Review Workflow

**Step 1: Creator Review**
Creator runs the full checklist before submitting for review.
Time allocation: [X minutes]

**Step 2: Second-Reviewer Check** (where applicable)
Second reviewer checks critical items only.
Time allocation: [X minutes]

**Step 3: Fix Cycle**
Any failed items are corrected and re-checked.
Maximum fix cycles: 2 (if still failing after 2 rounds, escalate to team lead)

**Step 4: Final Approval**
Sign-off by [role] before delivery or publication.

**Step 5: Post-Delivery Spot Check**
Random 10% of deliverables get a post-delivery audit monthly.
```

### Defect Tracking

```
## Defect Log

| Date | Deliverable | Defect Found | Severity | Root Cause | Fix Applied | Preventive Action |
|------|------------|-------------|----------|-----------|-------------|------------------|
| | | | Critical/Important/Minor | | | |
```

## Phase 4: Improve

Build continuous improvement into the QA process.

### Monthly QA Review

- Review the defect log for patterns (same defect appearing 3+ times means the process is broken, not the person)
- Update the checklist to add checks for new defect types
- Remove checks that have not caught a defect in 3+ months (reduce checklist bloat)
- Recalibrate pass criteria if quality standards have shifted

### Checklist Versioning

Track changes with version notes:
```
**v1.0** — Initial checklist
**v1.1** — Added [check] after [incident]
**v1.2** — Removed [item] — redundant with new tool auto-check
```

## Anti-Patterns

- **Checklist too long** — more than 20 items and reviewers start rubber-stamping. Keep it under 15 and prioritize critical items.
- **Vague pass criteria** — "Looks good" is not a criterion. "Zero spelling errors in all client-facing text" is a criterion.
- **Skipping the checklist when under pressure** — the checklist exists because teams are under pressure. That is exactly when mistakes happen.
- **Creator and reviewer are the same person** — self-review catches roughly 60% of issues. A second reviewer catches closer to 90%.
- **Never updating the checklist** — a static checklist becomes irrelevant. Review quarterly at minimum.

## Recovery

- **A defect reaches a client:** Add the defect type to the checklist immediately. Run a brief root cause analysis — was it a missed check or a missing check?
- **QA is taking too long:** Split into "ship-blocking" and "nice-to-have" tiers. Only the ship-blocking tier is mandatory before delivery.
- **Team members skip the checklist:** Make the signed checklist a required attachment before delivery is marked complete. No sign-off, no ship.
- **Checklist does not catch real issues:** The checklist is testing the wrong things. Review actual client or customer complaints and reverse-engineer checks from those.
- **No bandwidth for a second reviewer:** Use a time-delay approach — complete the QA check, set it aside for at least 30 minutes, then review with fresh eyes before delivery.
