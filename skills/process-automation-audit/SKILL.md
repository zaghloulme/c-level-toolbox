---
name: Process Automation Audit
description: "Identifies automation opportunities across business processes with scoring, ROI estimates, tool recommendations, and a phased implementation roadmap — for operations teams and executives mapping where to reduce manual work."
allowed-tools: Read Write Glob
---

# Process Automation Audit

## Core Principle

AUTOMATE THE BORING, REPETITIVE, AND ERROR-PRONE — NEVER AUTOMATE WHAT REQUIRES JUDGMENT, CREATIVITY, OR HUMAN RELATIONSHIPS.

## Phase 1: Process Inventory

Map all current processes before identifying automation candidates.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Business type** | "What does the organization do and how is value delivered?" | No default — must be provided |
| **Pain points** | "Which tasks eat the most time or cause the most errors?" | No default |
| **Current tools** | "What tools and software are currently in use?" | No default |
| **Team size** | "How many people handle operations?" | No default — must be provided |
| **Budget for tools** | "Monthly budget for automation tooling?" | No default |
| **Tech capability** | "What is the team's technical capacity: no-code only, some dev, or full engineering support?" | No-code only |

### Process Mapping

For each process described, document:

```
## Process: [Name]

**Frequency:** [Daily/Weekly/Monthly]
**Time per occurrence:** [X minutes/hours]
**Monthly time cost:** [Frequency x Time]
**Error rate:** [Low/Medium/High]
**Current method:** [Manual/Semi-automated/Fully manual]
**Steps:**
1. [Step 1]
2. [Step 2]
3. [Step 3]
```

**GATE: Present the process inventory and confirm completeness before scoring.**

## Phase 2: Score and Prioritize

Evaluate each process for automation potential.

### Automation Scoring

Score each process on four dimensions (1-5):

| Dimension | 1 (Low) | 5 (High) |
|-----------|---------|----------|
| **Time savings** | Under 30 min/month | Over 5 hours/month |
| **Repeatability** | Varies every time | Same steps every time |
| **Error impact** | Errors are trivial | Errors cost money or reputation |
| **Ease of automation** | Requires custom development | Off-the-shelf tool exists |

```
## Automation Priority Matrix

| Process | Time Saved | Repeatability | Error Impact | Ease | Total | Priority |
|---------|-----------|---------------|-------------|------|-------|----------|
| Invoice sending | 5 | 5 | 4 | 5 | 19 | HIGH |
| Report generation | 3 | 3 | 3 | 2 | 11 | MEDIUM |
| Data reconciliation | 4 | 4 | 5 | 2 | 15 | HIGH |
```

### ROI Estimate

For each high-priority process:

```
**Process:** [Process name]
**Current time cost:** [X] hours/month
**Fully-loaded cost of that time:** [EGP/currency X]
**Monthly cost of manual process:** [Amount]
**Recommended tool:** [Tool name]
**Tool cost:** [Amount/month]
**Setup time:** [X] hours (one-time)
**Monthly time after automation:** [X] hours
**Monthly net savings:** [Amount after tool cost]
**Payback period:** [X weeks/months]
```

**GATE: Present priorities and ROI estimates before recommending tools.**

## Phase 3: Tool Recommendations

Match each automation opportunity with specific tools.

### Recommendation Format

For each process, recommend 1-2 tools:

```
## Recommended Automations

### 1. [Process Name] — Priority: HIGH

**Recommended tool:** [Primary recommendation]
**Alternative:** [Backup option]
**What it automates:** [Specific steps from the process map]
**What still needs human input:** [Steps that cannot be automated]
**Setup complexity:** [Low/Medium/High]
**Monthly cost:** [Amount]
**Integration with current stack:** [How it connects to existing tools]
```

### Automation Categories by Function

Reference these categories when making recommendations:

- **Finance operations:** Recurring invoices, payment reminders, expense categorization, reconciliation alerts
- **Reporting:** Scheduled report generation, metric alerts, dashboard updates
- **Scheduling and coordination:** Meeting booking, calendar management, team reminders
- **Client communications:** Follow-up sequences, onboarding emails, status notifications
- **Document workflows:** Contract generation, approval routing, e-signature
- **Data management:** CRM updates, lead routing, deduplication

## Phase 4: Implementation Roadmap

Deliver a phased plan for implementing automations.

### 90-Day Roadmap

```
## Automation Roadmap

**Month 1 — Quick Wins**
- [ ] Set up [Tool 1] for [Process] (estimated: [X] hours)
- [ ] Set up [Tool 2] for [Process] (estimated: [X] hours)
- Expected time savings: [X] hours/month

**Month 2 — Core Systems**
- [ ] Implement [Tool 3] for [Process] (estimated: [X] hours)
- [ ] Connect [Tool 1] to [Tool 3] via [integration]
- Expected time savings: [X] hours/month

**Month 3 — Optimization**
- [ ] Review automation performance
- [ ] Fix any broken workflows
- [ ] Identify next batch of processes to automate
- Expected total time savings: [X] hours/month
```

### Maintenance Schedule

Monthly 30-minute automation review: verify workflows are running, check error logs, update any broken integrations.

## Anti-Patterns

- **Automating everything at once** — implement one automation at a time. Stack failures are hard to debug.
- **Automating broken processes** — fix the process first, then automate. Automating a bad process makes bad things happen faster.
- **Over-engineering** — a no-code integration beats a custom-coded solution for most operational workflows.
- **Ignoring the human steps** — every automation has handoff points where review, approval, or judgment is required.
- **No error handling** — automations fail silently. Always set up failure notifications.

## Recovery

- **No budget available:** Recommend free tiers first. Most enterprise tools have generous trial plans. Prioritize automations that generate savings sufficient to justify paid upgrades.
- **Team is not technical:** Stick to no-code tools with visual builders. Avoid anything requiring API configuration or code.
- **An automation breaks:** Identify the failure point, set up error alerts, and create a manual fallback until the automation is repaired.
- **Process is too complex to automate fully:** Recommend partial automation — automate the repeatable steps and keep human judgment for exceptions.
- **Analysis paralysis on where to start:** Pick the single highest-ROI process from the priority matrix and start there. One working automation builds credibility for the next.
