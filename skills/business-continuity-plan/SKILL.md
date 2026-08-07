---
name: Business Continuity Plan
version: 1.6.0
description: "Develops business continuity plans with risk assessment, critical function mapping, recovery procedures, and crisis communication protocols — for organizations preparing for operational disruptions."
---

# Business Continuity Plan

## Core Principle

A BUSINESS CONTINUITY PLAN IS INSURANCE YOU WRITE YOURSELF — THE TIME TO BUILD IT IS WHEN YOU DO NOT NEED IT, BECAUSE WHEN YOU NEED IT, YOU WILL NOT HAVE TIME TO BUILD IT.

## Phase 1: Risk Assessment

Identify what could disrupt the business and how severely.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Business type** | "What does the organization do and how is value delivered?" | No default — must be provided |
| **Revenue streams** | "What are the main revenue sources?" | No default |
| **Critical systems** | "What tools and platforms are essential to daily operations?" | No default |
| **Team structure** | "What does the org chart look like? Key roles and dependencies?" | No default — must be provided |
| **Biggest exposure** | "What scenario would cause the most operational damage?" | No default |

### Risk Identification

Score each risk on likelihood (1-5) and impact (1-5):

```
## Risk Assessment Matrix

| Risk Scenario | Likelihood | Impact | Risk Score | Priority |
|--------------|-----------|--------|-----------|----------|
| Critical system or platform failure | 3 | 5 | 15 | HIGH |
| Key person unavailability (2+ weeks) | 3 | 4 | 12 | HIGH |
| Data loss or security breach | 2 | 5 | 10 | MEDIUM |
| Primary supplier failure | 2 | 3 | 6 | MEDIUM |
| Natural disaster or facility loss | 1 | 4 | 4 | LOW |
```

**GATE: Confirm risk assessment before building recovery procedures.**

## Phase 2: Recovery Procedures

Build specific recovery plans for each high and medium priority risk.

### Critical Functions Map

```
## Critical Business Functions

| Function | Systems Required | Recovery Time Objective | Primary Owner | Backup |
|----------|----------------|----------------------|--------------|--------|
| Client delivery | [systems] | 24 hours | [Role] | [Role] |
| Payment processing | [systems] | 4 hours | [Role] | [Role] |
| Communications | [systems] | 1 hour | [Role] | [Role] |
| Core operations | [systems] | [hours] | [Role] | [Role] |
```

### Recovery Procedure Template

For each high-priority risk, document:

```
## Recovery Plan: [Risk Scenario]

**Trigger:** [What indicates this scenario is occurring]
**Severity:** [Critical / Major / Minor]
**Recovery Time Objective:** [How fast operations must be restored]

### Immediate Actions (first 1-2 hours)
1. [Action step with specific instructions]
2. [Action step]
3. [Action step]

### Short-Term Recovery (24-72 hours)
1. [Action step]
2. [Action step]

### Return to Normal
1. [Action step]
2. [Post-incident review and plan update]

### Resources Needed
- [Tool, contact, document, or system access needed]
```

**GATE: Present recovery procedures for review.**

## Phase 3: Communication Protocol

Define who gets notified, when, and through what channel during a disruption.

### Stakeholder Communication Plan

```
## Crisis Communication Plan

| Stakeholder | Notify Within | Method | Message | Responsible |
|-------------|--------------|--------|---------|-------------|
| Active clients | 4 hours | Email | Service disruption notice | [Role] |
| Internal team | 1 hour | Phone/message | Operational update | [Role] |
| Key vendors | 24 hours | Email | Impact assessment | [Role] |
| Board / investors | 24 hours | Phone | Situation briefing | [Role] |
```

### Message Templates

Pre-written templates for each stakeholder group:

```
**Client notification:**
Subject: Service Update from [Organization Name]

Dear [Name],

We want to advise you of [brief description of situation]. Here is what this means for your work with us:
- [Impact on their deliverable or service]
- [What steps are being taken]
- [Expected resolution timeline]

We will send a further update by [date/time]. For urgent matters, contact [name] at [contact].

[Name and title]
```

## Phase 4: Maintenance

Keep the plan current and accessible.

### Plan Storage and Access

- Store the plan in at least 2 locations (cloud platform + secure local backup)
- Ensure backup owners have access and know where it is
- Include critical credentials in a secure password manager with documented emergency access procedures

### Review Schedule

- **Quarterly:** Verify contact information and system access
- **Biannually:** Test one recovery procedure end-to-end
- **Annually:** Full plan review and update
- **After any incident:** Update the plan with lessons learned

### Emergency Contacts Sheet

```
## Emergency Contacts

| Contact | Role | Phone | Email | When to Contact |
|---------|------|-------|-------|----------------|
| [Name] | Operations lead | [#] | [email] | Any major disruption |
| [Name] | IT / systems support | [#] | [email] | System or platform failure |
| [Name] | Legal counsel | [#] | [email] | Regulatory or liability exposure |
| [Name] | Finance lead | [#] | [email] | Financial or banking issues |
```

## Anti-Patterns

- **Plan exists but no one can find it** — a plan stored in a system that is down during the crisis is useless. Keep it accessible offline or in a secondary location.
- **Too detailed to be usable** — a 50-page plan will not be consulted during an active crisis. Keep recovery steps to 5-7 actions per scenario.
- **Single point of failure ignored** — if only one person holds credentials, knowledge, or authority, that dependency is the risk. Document and distribute.
- **Never tested** — an untested plan is a theory. Run a tabletop exercise at least once a year.
- **Written once and not maintained** — organizational change makes old plans irrelevant. Review on a set schedule.

## Recovery

- **No backup coverage for key roles:** Document the minimum information a replacement or temporary resource would need to keep critical functions running for 72 hours.
- **Too many risks to plan for:** Focus on the top 3 by risk score. A solid plan for 3 scenarios beats a vague plan for 20.
- **Organization has already experienced a disruption:** Use that incident as the starting case. Document what happened, what worked, what failed, and build the plan from the actual experience.
- **Leadership resists investing time in BCP:** Frame it as a board governance and insurance question, not an IT exercise. Regulators and institutional clients increasingly require it.
