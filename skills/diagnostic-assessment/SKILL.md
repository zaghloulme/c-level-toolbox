---
name: Client Diagnostic Assessment Tool
version: 1.5.5
description: "Builds diagnostic assessment tools for consulting engagements with scoring, benchmarking, and recommendation logic that show clients where they stand and what to do next."
---

# Diagnostic Assessment

## Core Principle

A DIAGNOSTIC ASSESSMENT DOES TWO THINGS — IT SHOWS THE CLIENT WHERE THEY STAND AND MAKES THE PATH FORWARD OBVIOUS. THE SCORE REVEALS THE GAP. THE RECOMMENDATIONS CLOSE IT.

## Phase 1: Assessment Design

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Assessment topic** | "What area does this assessment evaluate?" | No default — must be provided |
| **Target audience** | "Who takes this assessment — executive teams, department heads, project teams?" | Leadership teams |
| **Number of categories** | "How many areas should the assessment cover?" | 5-7 categories |
| **Purpose** | "Is this for client engagements, pre-sale qualification, or both?" | Client engagements |
| **Scoring model** | "Simple (1-5 scale) or weighted scoring?" | Simple 1-5 scale |

**GATE: Confirm topic and categories before building questions.**

## Phase 2: Assessment Structure

### Category Design

Define 5-7 assessment categories:

```
## [Assessment Name] — Categories

1. [Category 1] — [What it evaluates]
2. [Category 2] — [What it evaluates]
3. [Category 3] — [What it evaluates]
4. [Category 4] — [What it evaluates]
5. [Category 5] — [What it evaluates]
```

### Question Format

Write 3-5 questions per category:

```
## Category: [Category Name]

**Q1:** [Statement to rate]
Rate 1-5: (1 = Strongly Disagree, 5 = Strongly Agree)

**Q2:** [Statement to rate]
Rate 1-5

**Q3:** [Statement to rate]
Rate 1-5

**Category Score:** Sum of answers / Number of questions = [X/5]
```

### Question Writing Rules

- Write statements, not questions — "We have a documented process for X" vs. "Do you have a process?"
- Make each level distinguishable — a score of 2 should look clearly different from a score of 4
- Avoid double-barreled statements — one concept per question
- Include both positive and negative indicators to prevent all-high scoring
- Test with 3-5 people to ensure questions are understood consistently

## Phase 3: Scoring & Benchmarks

### Scoring Matrix

```
## Scoring Guide

### Category Scores
| Score | Level | Meaning |
|-------|-------|---------|
| 1.0-2.0 | Critical | Significant gaps requiring immediate attention |
| 2.1-3.0 | Developing | Foundation exists but major improvements needed |
| 3.1-4.0 | Competent | Solid performance with room for optimization |
| 4.1-5.0 | Advanced | Strong performance — focus on fine-tuning |

### Overall Score
| Range | Grade | Summary |
|-------|-------|---------|
| 5-12 | Needs Foundation | Multiple critical areas — prioritize fundamentals |
| 13-20 | Building | Some strengths, significant gaps remain |
| 21-28 | Growing | Good foundation — strategic improvements will accelerate results |
| 29-35 | Optimizing | Strong across the board — fine-tune for excellence |
```

### Results Presentation

```
## Assessment Results — [Client Name]

**Date:** [Date]
**Overall Score:** [X/35] — [Grade Level]

### Category Breakdown

| Category | Score | Level | Priority |
|----------|-------|-------|----------|
| [Category 1] | X/5 | [Level] | [High/Med/Low] |
| [Category 2] | X/5 | [Level] | [High/Med/Low] |
| [Category 3] | X/5 | [Level] | [High/Med/Low] |

### Strengths (Scores 4+)
- [Category] — [What they are doing well]

### Priority Gaps (Scores under 3)
- [Category] — [What needs immediate attention]

### Recommended Actions
1. **[Action]** — Addresses [category]. Expected impact: [outcome].
2. **[Action]** — Addresses [category]. Expected impact: [outcome].
3. **[Action]** — Addresses [category]. Expected impact: [outcome].
```

## Phase 4: Implementation

### As a Pre-Sale Tool

- Offer the assessment during initial engagement conversations
- Use results to frame the scope of the engagement and justify the investment
- Segment prospects by score level to tailor your proposal
- Include assessment results in your engagement proposal to anchor the problem

### As a Client Engagement Tool

- Use the assessment during the first session of every engagement
- Repeat the assessment at the end to show measurable improvement
- Benchmark against industry averages if data is available
- Include results in the engagement report to demonstrate ROI

### Assessment Delivery Options

| Format | Best For | Effort |
|--------|----------|--------|
| PDF worksheet | In-person or call-based assessments | Low |
| Google Form + auto-score spreadsheet | Self-serve or pre-sale qualification | Medium |
| Interactive web tool (Typeform, ScoreApp) | Scalable lead qualification | High |
| Facilitated workshop | Group assessments or leadership team diagnostics | High |

## Anti-Patterns

- **Too many questions** — more than 25 questions causes abandonment. Keep it tight and focused.
- **No actionable recommendations** — a score without next steps is just a report card. Map every score range to specific actions.
- **Subjective scoring without anchors** — "Rate your operations 1-5" means different things to different people. Use behavioral descriptors.
- **One-size-fits-all recommendations** — tailor recommendations to the gap size, not the topic.
- **No follow-up** — sending results without offering to discuss them wastes the diagnostic's value.

## Recovery

- **Assessment results are all high scores:** Either the client is genuinely advanced (shift to optimization framing) or the questions are too easy. Add more discriminating questions.
- **Client disagrees with their score:** Walk through the specific questions and their answers. Ask what evidence would change the score.
- **Assessment is too long:** Cut to 3 questions per category. Focus on the questions that most differentiate strong from weak performers.
- **No industry benchmarks available:** Use your own client data to build benchmarks over time. Start with qualitative levels (foundational, intermediate, advanced).
- **Client overwhelmed by results:** Prioritize the top 2-3 improvements. Present them as phases, not a simultaneous to-do list.
