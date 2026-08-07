---
name: AI Use Case Finder and ROI Roadmap
description: "Identifies AI automation opportunities in business workflows with feasibility assessment, ROI estimates, and implementation roadmaps prioritized by impact and effort."
allowed-tools: Read Write Glob
---

# AI Use Case Finder

## Core Principle

AI SHOULD AUTOMATE THE REPETITIVE SO YOUR TEAM CAN FOCUS ON THE STRATEGIC — THE BEST AI USE CASES SAVE MEASURABLE TIME ON TASKS YOU ALREADY DO, NOT TASKS YOU IMAGINE DOING.

## Phase 1: Brief

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Business type** | "What does your business do?" | No default — must be provided |
| **Team size** | "How many people work in the business?" | No default — must be provided |
| **Weekly tasks** | "List the tasks your team spends the most time on each week." | No default — must be provided |
| **Pain points** | "Which tasks do you wish you could automate or eliminate?" | No default — ask for top 3 |
| **Current AI usage** | "Do you use any AI tools already? Which ones?" | None or basic |
| **Budget** | "What is your monthly budget for tools and software?" | No default — ask |

**GATE: Confirm the brief and task list before analyzing opportunities.**

## Phase 2: Audit and Identify

### Task Audit Framework

For each task the user listed, evaluate:

| Task | Hours/Week | Frequency | Repetitive? | Requires Judgment? | AI Potential |
|------|-----------|-----------|-------------|--------------------|----|
| [Task 1] | | | Yes/No | Low/Med/High | High/Med/Low |
| [Task 2] | | | Yes/No | Low/Med/High | High/Med/Low |

### AI Opportunity Scoring

Score each task on three dimensions:

| Dimension | Score 1-5 | Description |
|-----------|-----------|-------------|
| **Time savings** | 1=minimal, 5=hours saved weekly | How much time will AI save? |
| **Feasibility** | 1=complex, 5=tools exist today | Can current AI tools handle this? |
| **Impact** | 1=nice-to-have, 5=revenue-affecting | What is the business impact of automating this? |

**AI Priority Score = Time Savings x Feasibility x Impact (max 125)**

### Common High-Value AI Use Cases

| Business Area | Task | AI Solution | Time Saved |
|---------------|------|------------|-----------|
| **Content** | Writing first drafts | LLM (Claude, ChatGPT) | 5-10 hrs/week |
| **Email** | Drafting responses | AI email tools | 3-5 hrs/week |
| **Reporting** | Summary and narrative generation | LLM + template | 3-6 hrs/week |
| **Research** | Market and competitor research | AI search + summarization | 2-3 hrs/week |
| **Admin** | Meeting notes and summaries | AI transcription | 1-2 hrs/week |
| **Finance** | Invoice and expense categorization | AI bookkeeping tools | 1-2 hrs/week |
| **Customer support** | FAQ responses | Chatbots, templated AI | 3-5 hrs/week |
| **Data** | Basic analysis and visualization | AI analytics tools | 2-4 hrs/week |

**GATE: Present scored opportunities and confirm the top 3-5 to develop further.**

## Phase 3: Build the Implementation Plan

### For Each Top Opportunity

```
## Opportunity: [Task Name]

**Current state:** [How the task is done now]
**AI solution:** [Specific tool or approach]
**Time saved:** [Hours per week]
**Cost:** [Monthly tool cost]
**ROI:** [Time saved x hourly rate] vs. [Tool cost]
**Implementation effort:** [Hours to set up]
**Risk:** [What could go wrong]

### Setup Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

### Success Metric
[How to measure whether this is working]
```

### Implementation Roadmap

Sequence opportunities by quick wins first:

| Phase | Timeline | Tasks to Automate | Expected Savings |
|-------|----------|-------------------|-----------------|
| Quick wins | Week 1-2 | [Low effort, high impact tasks] | [X] hrs/week |
| Foundation | Week 3-4 | [Medium effort tasks] | [X] hrs/week |
| Advanced | Month 2-3 | [Higher effort, higher reward] | [X] hrs/week |

## Phase 4: Polish

### 1. ROI Summary

```
## AI Adoption ROI Summary

**Total tasks audited:** [X]
**Tasks with AI potential:** [X]
**Estimated weekly time savings:** [X] hours
**Monthly tool costs:** $[X]
**Monthly value of time saved:** $[X] (at $[hourly rate]/hour)
**Net monthly ROI:** $[X]
**Payback period:** [X] weeks
```

### 2. Risk Assessment

For each recommended AI implementation:
- **Quality risk:** Will AI output meet your standards? (Mitigation: human review)
- **Dependency risk:** What if the tool shuts down? (Mitigation: avoid single points of failure)
- **Cost risk:** Will pricing increase? (Mitigation: monitor usage and alternatives)

### 3. Quality Checklist

```
## AI Use Case Finder Checklist

- [ ] All major weekly tasks audited with time estimates
- [ ] Each task scored on time savings, feasibility, and impact
- [ ] Top 3-5 opportunities identified and prioritized
- [ ] Specific AI tools recommended for each opportunity
- [ ] ROI calculated (time saved vs. tool cost)
- [ ] Implementation steps outlined for each opportunity
- [ ] Roadmap sequences quick wins first
- [ ] Risks identified with mitigation strategies
- [ ] Success metrics defined for each implementation
- [ ] Total projected time savings and ROI summarized
```

## Example

**Organization:** Operations team at a 50-person company
**Top opportunity:**

```
## Opportunity: Management Reporting Package

**Current state:** Operations analyst manually compiles data from 4 systems into weekly reports.
Takes 6 hours per report across 4 report types = 24 hours/month.
**AI solution:** Claude + template. Feed structured data, generate narrative report draft,
human review and customize.
**Time saved:** 16 hours/month (from 24 to 8)
**Cost:** $20/month (Claude Pro)
**ROI:** 16 hours x $60/hour = $960/month value for $20 cost
**Implementation effort:** 4 hours to create templates and test
**Success metric:** Report creation time drops below 2 hours per report
```

## Anti-Patterns

- **Automating tasks you should eliminate** — if a task adds no value, do not automate it. Stop doing it.
- **Starting with the hardest use case** — begin with the simplest, most repetitive tasks. Build confidence before tackling complex workflows.
- **Ignoring quality requirements** — AI drafts need human review. Build review time into your time savings estimate.
- **Tool proliferation** — signing up for 10 AI tools creates complexity. Start with 1-2 tools that cover the most use cases.
- **Expecting perfection** — AI that saves 70% of the time on a task is a win. Waiting for 100% automation means waiting forever.

## Recovery

- **Team cannot identify repetitive tasks:** Walk through a typical work week hour by hour. Tasks become visible when mapped to time.
- **All tasks seem to require high judgment:** Break tasks into sub-steps. Research, drafting, and formatting sub-steps are often automatable even when the final decision is not.
- **Budget is constrained:** Focus on free tiers of AI tools. Many tools offer generous free plans sufficient for initial automation.
- **Team is overwhelmed by options:** Pick ONE task, ONE tool, and ONE week to try it. Expand only after the first win.
