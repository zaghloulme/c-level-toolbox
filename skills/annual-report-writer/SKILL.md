---
name: Annual Report Writer
version: 1.6.5
description: "Produces structured annual reports with executive summary, financial performance, operational highlights, strategic outlook, and stakeholder narrative — for organizations reporting to boards, investors, or regulatory bodies."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Annual Report Writer

## Core Principle

AN ANNUAL REPORT TELLS THE STORY OF YOUR YEAR — NUMBERS PROVIDE PROOF, BUT THE NARRATIVE PROVIDES MEANING AND DIRECTION.

## Phase 1: Brief

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Organization name** | "What is the organization?" | No default — must be provided |
| **Reporting period** | "What year or period does this cover?" | Previous calendar year |
| **Audience** | "Who reads this? Board, investors, regulators, partners?" | Board and investors |
| **Key metrics** | "Share the most important numbers: revenue, growth, key operational KPIs." | No default — must be provided |
| **Major milestones** | "What were the 3-5 biggest achievements this year?" | No default — must be provided |
| **Challenges** | "What went wrong or was harder than expected?" | None stated — will probe |
| **Next year priorities** | "What are the top strategic priorities for the coming year?" | No default — must be provided |

**GATE: Confirm all inputs before outlining.**

## Phase 2: Outline

### Annual Report Structure

```
1. Letter from the CEO (~300 words)
2. Year at a Glance — key metrics dashboard
3. Major Milestones & Achievements (~500 words)
4. Challenges & Lessons Learned (~300 words)
5. Financial Highlights (~400 words)
6. Organizational & Operational Highlights (~300 words)
7. Strategic Outlook — priorities for next year (~300 words)
8. Closing Statement (~100 words)
```

**GATE: Approve outline before writing.**

## Phase 3: Write

### 1. CEO Letter

```
## Letter from [Name], Chief Executive Officer

[Opening — personal reflection on the year, 2-3 sentences]

[Key theme of the year — what defined this period for the organization]

[Top 2-3 achievements in brief]

[Honest acknowledgment of one challenge and what was learned]

[Forward-looking statement — strategic direction for the year ahead]

[Sign-off]
[Name]
```

Rules: First person, direct but professional. Authentic, not corporate. Under 300 words.

### 2. Year at a Glance

```
## [Year] at a Glance

| Metric | [Year] | [Previous Year] | Change |
|--------|--------|-----------------|--------|
| Revenue | [X] | [X] | [+/-X%] |
| [Operating metric] | [X] | [X] | [+/-X%] |
| [Key metric 3] | [X] | [X] | [+/-X%] |
| [Key metric 4] | [X] | [X] | [+/-X%] |

**Highlight:** [One standout number with context — e.g., "Revenue grew 31%, the strongest year-on-year performance in the company's history."]
```

### 3. Milestones Section

For each milestone:
```
### [Milestone Name]

[What happened — 2-3 sentences]
[Why it matters — 1-2 sentences on business impact]
[Supporting metric if available]
```

### 4. Challenges Section

```
## Challenges & Lessons Learned

[Honest but constructive framing. Not "we failed at X" but "X was harder than expected, and here is what we learned."]

- **[Challenge 1]:** [What happened + what was learned + what changed]
- **[Challenge 2]:** [Same format]
```

### 5. Strategic Outlook

```
## Strategic Outlook: [Next Year]

**Priority 1:** [Goal] — [Why it matters, 1 sentence]
**Priority 2:** [Goal] — [Why it matters]
**Priority 3:** [Goal] — [Why it matters]

[Closing statement — confidence in direction, 2-3 sentences]
```

### Writing Rules

| Rule | Detail |
|------|--------|
| **Tone** | Professional, transparent, direct |
| **Data** | Every claim backed by a number |
| **Challenges** | Acknowledge at least one — credibility requires honesty |
| **Length** | 2,500–4,000 words for most organizations |
| **Visuals** | Mark where charts, graphs, and photos should appear |

## Phase 4: Polish

### Report Checklist

```
## Annual Report Checklist

- [ ] CEO letter is personal and specific (not generic boilerplate)
- [ ] Key metrics presented with year-over-year comparison
- [ ] At least 3 milestones highlighted with context
- [ ] Challenges acknowledged honestly
- [ ] Strategic outlook section has 3 specific priorities
- [ ] Visual/chart placements noted
- [ ] Tone is consistent throughout
- [ ] Report tells a coherent story from beginning to end
```

### Design Notes

Provide layout suggestions for visual presentation (charts, photos, pull quotes).

### Distribution Plan

Suggest how to share the report: board pack, investor communication, regulatory filing, staff briefing, or public PDF.

## Example: Regional Financial Services Firm

```
CEO letter theme: "The year we extended our reach and deepened client trust"
Key metrics: Revenue $48M (+14% YoY), AUM $380M (+22%), client retention 94%
Milestones: Opened second branch, launched institutional product line, completed ISO 27001 certification
Challenge: Integration of acquired portfolio took two quarters longer than planned — resourcing and process gaps identified and resolved
Strategic outlook: Reach $60M revenue, expand retail product suite, enter two new governorates
```

## Anti-Patterns

- **All positive, no challenges** — a report with zero setbacks reads as dishonest. Acknowledge at least one difficulty.
- **Numbers without context** — revenue figures mean nothing without comparison to prior year, plan, or sector benchmark. Always show the change.
- **Vague corporate language** — "We created value for stakeholders through strategic initiatives" tells nobody anything. Use plain language and specific results.
- **No forward-looking section** — a report that only looks backward misses the opportunity to build confidence in leadership's direction.
- **Length mismatched to audience** — board packs and public filings have different standards. Match format and depth to the specific audience.

## Recovery

- **No full financial data available:** Focus on operational metrics (headcount, projects, contracts, milestones) and qualitative achievements. Note what financial data was excluded and why.
- **Year was difficult:** Frame around decisions made and lessons applied. "This year tested the organization — here is what we learned and the structural changes made as a result."
- **No prior-year comparison (first full year):** Compare against founding targets or sector benchmarks instead.
- **Multiple audiences with different needs:** Write one core narrative report. Add a financial appendix for investors and a board-specific summary with KPIs and risks.
- **Key metrics not tracked consistently:** Report what is available. Flag data gaps as a governance action item for next year.
