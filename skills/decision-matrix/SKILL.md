---
name: Decision Matrix
version: 1.3.5
description: "Creates weighted decision matrices for business choices with criteria, scoring, recommendation logic, and sensitivity analysis — for removing bias from multi-criteria decisions and documenting rationale for stakeholders."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Decision Matrix

## Core Principle

A DECISION MATRIX DOES NOT MAKE THE DECISION FOR YOU — IT MAKES YOUR THINKING VISIBLE SO YOU CAN SPOT WHERE INTUITION AND DATA AGREE OR CONFLICT.

## Phase 1: Frame the Decision

Define the decision clearly before building the matrix.

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Decision statement** | "What specific decision is being made? State it as a question." | No default — must be provided |
| **Options** | "What are the 2-5 options under consideration?" | No default — minimum 2 required |
| **Criteria** | "What factors matter most? (cost, speed, quality, risk, strategic fit, etc.)" | Suggest 5-7 based on decision type |
| **Stakeholders** | "Who is affected by or needs to approve this decision?" | No default — must be provided |
| **Timeline** | "When does this decision need to be made?" | No default |

### Decision Types and Suggested Criteria

| Decision Type | Suggested Criteria |
|--------------|-------------------|
| **Tool/Software** | Cost, ease of use, features, integrations, scalability, vendor support |
| **Vendor/Partner** | Price, quality, reliability, communication, experience, contract terms |
| **Hire** | Skills match, culture fit, availability, compensation, track record |
| **Strategy** | Revenue impact, execution effort, risk, time to results, strategic alignment |
| **Market/Product** | Market size, competition, margin potential, execution difficulty |

**GATE: Confirm the decision statement, options, and criteria before building the matrix.**

## Phase 2: Weight and Score

Build the matrix with weighted criteria and score each option.

### Weighting Criteria

Assign weights that total 100% across all criteria:

```
## Criteria Weights

| Criteria | Weight | Rationale |
|----------|--------|-----------|
| [Criteria 1] | [X]% | [Why this weight] |
| [Criteria 2] | [X]% | [Why this weight] |
| [Criteria 3] | [X]% | [Why this weight] |
| [Criteria 4] | [X]% | [Why this weight] |
| [Criteria 5] | [X]% | [Why this weight] |
| **Total** | **100%** | |
```

### Scoring Options

Score each option 1-5 on every criterion with brief justification:

```
## Decision Matrix: [Decision Statement]

| Criteria | Weight | Option A | Score | Option B | Score | Option C | Score |
|----------|--------|----------|-------|----------|-------|----------|-------|
| [Criteria 1] | [X]% | [rationale] | [1-5] | [rationale] | [1-5] | [rationale] | [1-5] |
| [Criteria 2] | [X]% | [rationale] | [1-5] | [rationale] | [1-5] | [rationale] | [1-5] |
| [Criteria 3] | [X]% | [rationale] | [1-5] | [rationale] | [1-5] | [rationale] | [1-5] |

## Weighted Scores

| Option | Weighted Score | Rank |
|--------|---------------|------|
| Option A | [X.XX] | [1/2/3] |
| Option B | [X.XX] | [1/2/3] |
| Option C | [X.XX] | [1/2/3] |
```

**GATE: Present the scored matrix and validate scores with the decision-maker before delivering the recommendation.**

## Phase 3: Recommend

Deliver a clear recommendation with reasoning.

### Recommendation Format

```
## Recommendation

**Winner:** [Option] with a weighted score of [X.XX]

**Why this wins:** [2-3 sentences explaining the key differentiators]

**Key trade-off:** [What is given up by choosing this option vs. the runner-up]

**Gut check:** Does this match your intuition? If the matrix scores Option A but the team favors Option B, examine which criteria may be underweighted.
```

### Sensitivity Analysis

Test whether the result holds if weights shift:
- "If [criteria] weight increased by 10%, [Option X] would overtake [Option Y]"
- Flag any decision where the top two options are within 0.3 points — this means the decision is close and additional factors may matter

### Risk Flags

Note any option that scores below 2 on a high-weight criterion, even if the total score is competitive. A single critical weakness can disqualify an otherwise strong option.

## Phase 4: Document

Provide a decision record for future reference.

### Decision Record Template

```
## Decision Record

**Decision:** [Statement]
**Date:** [Date]
**Decision maker(s):** [Name(s) and role(s)]
**Chosen option:** [Option]
**Weighted score:** [X.XX]
**Key reasons:** [3 bullet points]
**Known risks:** [Risks of the chosen option]
**Review date:** [When to evaluate whether this was the right call]
```

## Anti-Patterns

- **Too many criteria** — more than 7 criteria dilutes the signal. Force-rank and keep the top 5-7.
- **Equal weights** — giving every criterion the same weight means no deliberate prioritization has been done.
- **Scoring without justification** — a score of 4 means nothing without a one-line rationale.
- **Ignoring intuition that conflicts with the matrix** — if the scores point one way and the leadership team points another, the weights are probably wrong. Revisit them.
- **Using a matrix for obvious decisions** — if there is already a clear answer, a matrix adds process without value.

## Recovery

- **Cannot identify criteria:** Suggest 5 based on the decision type (see table above) and remove any that do not apply.
- **Options are too similar to score differently:** Add differentiating criteria or increase scoring granularity to 1-10 instead of 1-5.
- **All scores cluster around 3:** Challenge the scoring — "A 3 means average. Is this option truly average on [criteria], or is it a 2 or a 4?" Push for honest differentiation.
- **Stakeholders disagree on weights:** Have each stakeholder assign weights independently, then average them. Discuss criteria where weights diverge by more than 15%.
- **Decision-maker disagrees with the result:** Ask which single score they would change. Re-scoring one criterion often reveals what they actually value most, which should be reflected in the weights.
