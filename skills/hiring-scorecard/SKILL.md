---
name: Hiring Scorecard
description: "Creates structured interview scorecards with competency ratings, weighted evaluation criteria, question-to-competency mapping, and a multi-interviewer calibration framework for objective hiring decisions."
allowed-tools: Read Write Glob
---

# Hiring Scorecard

## Core Principle

HIRING WITHOUT A SCORECARD IS HIRING ON VIBES — A STRUCTURED SCORECARD FORCES OBJECTIVE EVALUATION AGAINST ROLE-SPECIFIC CRITERIA, REDUCING BIAS AND BAD HIRES.

## Phase 1: Role Requirements

Define what the role needs before building the scorecard.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Role title** | "What role are you hiring for?" | No default |
| **Employment type** | "Full-time, part-time, or contractor?" | Full-time |
| **Top 3 outcomes** | "What does this person need to achieve in the first 90 days?" | No default |
| **Must-have skills** | "What skills are non-negotiable?" | No default |
| **Nice-to-have skills** | "What skills would be a bonus but not required?" | No default |
| **Culture traits** | "What working style or behaviors matter for this role?" | Ownership, clear communication |

### Competency Framework

```
## Role Competencies: [Role Title]

### Must-Have (Weighted 70%)
| Competency | Description | How to Assess |
|-----------|-------------|---------------|
| [Skill 1] | [What strong performance looks like] | [Interview question / test / portfolio] |
| [Skill 2] | [What strong performance looks like] | [Assessment method] |
| [Skill 3] | [What strong performance looks like] | [Assessment method] |

### Nice-to-Have (Weighted 20%)
| Competency | Description | How to Assess |
|-----------|-------------|---------------|
| [Skill 4] | [What strong performance looks like] | [Assessment method] |

### Culture Fit (Weighted 10%)
| Trait | Description | How to Assess |
|-------|-------------|---------------|
| [Trait 1] | [Observable behavior] | [Behavioral question] |
```

**GATE: Confirm competencies before building the scorecard.**

## Phase 2: Build Scorecard

```
## Hiring Scorecard: [Role Title]

**Candidate:** _______________
**Interviewer:** _______________
**Date:** _______________
**Interview stage:** [Screen / Technical / Final]

### Competency Ratings

| # | Competency | Weight | Score (1-5) | Weighted Score | Evidence / Notes |
|---|-----------|--------|-------------|---------------|-----------------|
| 1 | [Must-have 1] | [%] | [ ] | [ ] | |
| 2 | [Must-have 2] | [%] | [ ] | [ ] | |
| 3 | [Must-have 3] | [%] | [ ] | [ ] | |
| 4 | [Nice-to-have 1] | [%] | [ ] | [ ] | |
| 5 | [Culture trait 1] | [%] | [ ] | [ ] | |

### Scoring Guide

| Score | Definition |
|-------|-----------|
| 1 | No evidence of competency — significant concern |
| 2 | Below expectations — gaps in critical areas |
| 3 | Meets expectations — adequate for the role |
| 4 | Above expectations — strong evidence of competency |
| 5 | Exceptional — among the best candidates seen for this competency |

### Overall Assessment

**Total weighted score:** _____ / 5.0

**Recommendation:** [ ] Strong Hire  [ ] Hire  [ ] No Hire  [ ] Strong No Hire

**Top strengths:**
1.
2.

**Top concerns:**
1.
2.

**Signature:** _______________ **Date:** ___
```

### Automatic Disqualifiers

```
## Red Flags

- [ ] Cannot verify claimed experience or credentials
- [ ] Disrespectful to any interviewer or staff during the process
- [ ] Cannot articulate relevant experience with specific examples
- [ ] Scores 1 on any must-have competency
- [ ] [Role-specific disqualifier]
```

One automatic disqualifier overrides any overall score.

**GATE: Present scorecard for review before adding interview questions.**

## Phase 3: Align Questions

```
## Interview Question Map

| Competency | Question | What to Listen For | Red Flag |
|-----------|---------|-------------------|----------|
| [Skill 1] | "Tell me about a time you [relevant scenario]" | [Specific evidence] | [Vague or evasive] |
| [Skill 2] | "How would you approach [role-specific challenge]?" | [Structured thinking, specifics] | [Buzzwords, no substance] |
| [Culture] | "Describe a situation where you had to push back on a decision you disagreed with" | [Principled, respectful disagreement] | [Avoidance or pure compliance] |
```

Score each competency immediately after the relevant question. Write specific quotes and examples — not general impressions.

## Phase 4: Decision Framework

```
## Hiring Decision Guide

| Weighted Score | Recommendation | Action |
|---------------|---------------|--------|
| 4.5-5.0 | Strong Hire | Move fast — this candidate has other options |
| 3.5-4.4 | Hire | Solid candidate — proceed with offer |
| 2.5-3.4 | Needs Assessment | Second interview or practical test required |
| Below 2.5 | No Hire | Do not lower the bar |
```

### Multi-Interviewer Calibration

When multiple interviewers assess the same candidate:
1. Each interviewer completes their scorecard independently before discussing
2. Compare scores — discuss any competency where scores differ by 2+ points
3. Average the final weighted scores
4. The hiring manager makes the final call with full context

### 90-Day Scorecard Validation

At 90 days, compare scorecard predictions to actual performance:
- Were identified strengths confirmed?
- Did concerns materialize?
- Use this data to calibrate the assessment methods for future hires

## Anti-Patterns

- **Scores without evidence** — "I liked them" is not a score. Every rating needs a specific example from the interview.
- **Halo effect** — one strong answer biases all other scores. Score each competency independently.
- **Lowering the bar** — if no candidate scores above 3.0, either the role is unclear or the pipeline needs improvement. Do not hire a 2.5.
- **Ignoring disqualifiers** — a 4.5 weighted score with one automatic disqualifier is still a no hire.
- **Skipping the scorecard for "obvious" hires** — obvious hires need documentation for HR records and calibration data.

## Recovery

- **No scorecard used before:** Start simple — 3 must-have competencies, scored 1-5, with one specific evidence note per score. Add weighting and calibration after the first cycle.
- **All candidates scoring similarly:** The questions are not differentiating. Add a practical test or more specific behavioral scenarios.
- **Suspected interviewer bias:** Require written evidence for every score before scores are shared with the team.
- **Candidate scored well but is underperforming:** Review which competencies were misjudged and update the assessment method for those areas.
