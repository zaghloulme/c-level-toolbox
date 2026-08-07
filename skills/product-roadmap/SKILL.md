---
name: Product Roadmap Builder
description: "Creates product roadmaps in markdown with ICE-scored features, milestones, release timelines, and status tracking — output ready to paste into any project management tool."
allowed-tools: Read Write Glob
---

# Product Roadmap

## Quick Reference

| Feature | Details |
|---------|---------|
| Properties | 12 fields per feature record |
| Prioritization | ICE scoring (default) or MoSCoW framework |
| Status stages | 6 (Backlog > Planned > In Progress > Testing > Shipped > Deferred) |
| Timeframes | 4 horizons (Now, Next, Later, Icebox) |
| Database views | 4 filtered views |
| Seeding | Bulk import from feature list or product brief |

## Database Schema

| Property | Type | Options/Default |
|----------|------|-----------------|
| Feature Name | Title | Required |
| Description | Rich text | Empty |
| Priority | Select | Must Have (red), Should Have (orange), Could Have (yellow), Won't Have (gray) |
| Status | Select | Backlog (gray), Planned (blue), In Progress (purple), Testing (orange), Shipped (green), Deferred (red) |
| Quarter/Phase | Select | Now (green), Next (blue), Later (yellow), Icebox (gray) |
| Effort | Select | XS (gray), Small (green), Medium (yellow), Large (orange), XL (red) |
| Impact | Number | 1-10 scale |
| Confidence | Number | 1-10 scale |
| Ease | Number | 1-10 scale |
| Owner | Rich text | Empty |
| Category | Select | Core (blue), Growth (green), Monetization (purple), Infrastructure (gray), UX/Design (pink), Integrations (orange) |
| Dependencies | Rich text | Empty |

### Status Flow

| Status | Meaning | Action |
|--------|---------|--------|
| Backlog | Idea captured, no timeline | Score with ICE, assign priority |
| Planned | Committed to a quarter | Assign owner, refine description |
| In Progress | Actively being built | Owner provides progress updates |
| Testing | Built, undergoing QA or beta | Testers provide feedback within 5 days |
| Shipped | Live and available to users | Mark release date in Description |
| Deferred | Intentionally postponed | Log reason, revisit next quarter |

### Effort Sizing

XS = less than 1 day | Small = 1-3 days | Medium = 1-2 weeks | Large = 3-4 weeks | XL = 5+ weeks

## ICE Scoring Framework

DEFAULT PRIORITIZATION METHOD. Use ICE unless the user explicitly requests MoSCoW-only.

**ICE Score = (Impact x Confidence x Ease) / 10**

| Dimension | Question | Scale |
|-----------|----------|-------|
| Impact | How much does this move the needle on revenue, retention, or satisfaction? | 1 (minimal) to 10 (transformative) |
| Confidence | How certain are we this will deliver the expected impact? | 1 (pure guess) to 10 (validated with data) |
| Ease | How easy is this to implement given current resources? | 1 (massive effort) to 10 (trivial to ship) |

| ICE Range | Action |
|-----------|--------|
| 50-100 | Prioritize immediately; move to Now |
| 25-49 | Plan for Next quarter |
| 10-24 | Keep in Later; refine scope |
| 1-9 | Move to Icebox; revisit when data improves |

**Scoring rules:**
- Score Impact on **business outcomes**, not feature appeal. A billing fix that reduces churn outscores a flashy animation.
- Score Confidence on **evidence.** Customer interviews = 8-10, gut feeling = 2-3, competitor has it = 5-6.
- Score Ease **relative to team size.** A solo developer rates a 2-week feature as 3; a 5-person team rates it 7.
- **NEVER give every feature the same scores.** If all features score 5/5/5, the framework provides zero signal.

## Core Workflow

EVERY PRODUCT ROADMAP STARTS BY GATHERING PRODUCT DETAILS AND CREATING THE DATABASE WITH THE FULL 12-PROPERTY SCHEMA BEFORE ADDING ANY FEATURES — NEVER ADD PAGES TO A DATABASE THAT IS MISSING PROPERTIES.

### Phase 1: Gather Product Details

1. **Product name** — what is the product called
2. **Product type** — SaaS, mobile app, web app, online course, physical product, marketplace
3. **Current stage** — idea, MVP, beta, launched, scaling
4. **Feature list** — known features, ideas, or backlog items to import
5. **Team size** — small (2-5), medium (6-15), or large (16+); affects Ease scoring
6. **Release cadence** — weekly, biweekly, monthly, quarterly, or milestone-based
7. **Stakeholder audience** — who will read this (team, investors, customers, board)
8. **Custom categories** — product areas beyond the 6 defaults

If the user provides only items 1, 4, and 5, proceed with all defaults.

**Brief template:**
```
I'll build your product roadmap in markdown. Quick answers needed:
1. Product name?
2. Product type? (SaaS, app, course, physical, other)
3. Current stage? (idea, MVP, beta, launched, scaling)
4. Feature list or backlog to import?
5. Team size? (2-5, 6-15, 16+)
6. Release cadence? (weekly, biweekly, monthly, quarterly)
7. Who will read this roadmap? (team, investors, customers, board)
```

### Phase 2: Prioritize Features with ICE Scoring

1. Score every feature with Impact, Confidence, Ease (1-10 each)
2. Calculate ICE Score: (I x C x E) / 10
3. Assign MoSCoW Priority: ICE 50+ = Must Have, 25-49 = Should Have, 10-24 = Could Have, below 10 = Won't Have
4. Assign Quarter/Phase: Must Have -> Now, Should Have -> Now/Next, Could Have -> Next/Later, Won't Have -> Icebox
5. Present scored list for user approval:

```
 #  Feature                    Impact  Conf  Ease  ICE   Priority      Phase
 1  Stripe payment integration    9      8     6   43.2  Must Have     Now
 2  Email onboarding sequence     8      7     7   39.2  Should Have   Now
 3  Team member roles             7      6     5   21.0  Could Have    Next
 4  Dark mode                     3      4     8    9.6  Won't Have    Icebox

Approve this prioritization, or tell me which scores to adjust.
```

**NEVER skip prioritization.** Even if the user says "just add them all," score every feature first.

### Phase 3: Output the Roadmap

Using the approved prioritized list from Phase 2, output the full roadmap as a markdown table:

```
## [Product Name] Roadmap

| # | Feature | Priority | Phase | Status | Effort | Impact | Conf | Ease | ICE | Owner | Category | Dependencies |
|---|---------|----------|-------|--------|--------|--------|------|------|-----|-------|----------|--------------|
| 1 | [Feature] | Must Have | Now | Backlog | Small | 9 | 8 | 6 | 43.2 | [Owner] | Core | — |
```

After outputting the table, ask: "Do you want me to save this as a file? I'll use `roadmap-[product-name].md` unless you specify a path."

If saving: use the Write tool to write the roadmap to the specified path.

### Phase 4: Deliver the Planning Guide

After the roadmap table, deliver this guide:

```
## Roadmap Operating Guide

**QUARTERLY REVIEW (60 min):**
1. Mark shipped features as Shipped
2. Re-score features whose Impact/Confidence changed
3. Pull top Backlog features into Planned for next quarter
4. Assign owners to all Now features

**WEEKLY CHECK-IN (15 min):**
1. Update statuses for In Progress features
2. Check for blocked features — note blockers in Dependencies column
3. Review features with Impact ≥ 7 and Ease ≥ 7 in Backlog for fast shipping

**ADDING NEW IDEAS:** Add a row with Status=Backlog, Phase=Icebox, score ICE, assign Priority

**STAKEHOLDER VIEWS:**
- Board/Investors: share rows filtered to Must Have + Should Have, hide ICE columns
- Customers: share Now + Next rows, show Feature, Status, and Phase only
- Internal: full table, all columns
```

### Phase 5: Confirm and Close

Report the final roadmap summary:

```
Roadmap complete: [Product Name]

  NOW ([N] features): [list feature names with priority and ICE score]
  NEXT ([N] features): [list feature names]
  LATER ([N] features): [list feature names]
  ICEBOX ([N] features): [list feature names]

Total: [N] features | Assigned: [N] | Unassigned: [N] | Must Have: [N]

File saved to: [path] (or "Not saved — copy the table above to use it")
```

Provide 3-4 next steps: assign any unassigned owners, write specs for Must Have features, schedule the first quarterly review, and share the stakeholder-filtered view.

**IF THE FEATURE LIST IS VAGUE:** Generate reasonable features based on product type and stage, present with ICE scores for approval BEFORE writing the table. NEVER output inferred features without user confirmation.

## Example 1: SaaS Invoicing Tool Roadmap

**User:** "Building a SaaS invoicing tool called BillFlow. Post-MVP with 50 beta users. Team: me (product), Priya (engineer), Marcus (designer). Monthly releases. Here are 12 features..."

**Execution:**

1. **Gather:** BillFlow, SaaS, post-MVP, 3-person team, monthly, internal audience
2. **Prioritize:** Score 12 features:

```
 #  Feature                       Impact  Conf  Ease  ICE    Priority      Phase
 1  Payment reminder emails          8      8     7   44.8   Must Have     Now
 2  Stripe payment integration       9      8     6   43.2   Must Have     Now
 3  CSV export for accountants       6      7     7   29.4   Should Have   Now
 4  Recurring invoice automation     9      7     5   31.5   Should Have   Now
 5  Dashboard with revenue metrics   7      6     6   25.2   Should Have   Now
 6  Late fee auto-calculation        6      7     5   21.0   Could Have    Next
 7  Team member roles                7      6     5   21.0   Could Have    Next
 8  Custom invoice templates         5      6     6   18.0   Could Have    Next
 9  QuickBooks sync                  8      5     4   16.0   Could Have    Next
10  Dark mode                        2      9     8   14.4   Could Have    Later
11  Client self-service portal       7      5     4   14.0   Could Have    Later
12  Multi-currency support           6      4     3    7.2   Won't Have    Icebox
```

3. **Output:** Roadmap table written with 12 features, ICE scores, priorities, and phases. Saved to `roadmap-billflow.md`.
4. **Deliver:** Planning guide + next steps provided.

## Example 2: Enterprise Internal Tool Roadmap

**User:** "Building an internal analytics dashboard for our operations team, post-MVP with 30 internal users. Team of 6. Quarterly releases. Here are 8 features..."

**Prioritize:** Score 8 features (team of 6 = mid-range Ease scores):

```
 #  Feature                         Impact  Conf  Ease  ICE    Priority      Phase
 1  Real-time KPI dashboard            9      8     7   50.4   Must Have     Now
 2  Automated weekly report emails     7      7     8   39.2   Should Have   Now
 3  Core data pipeline (12 sources)   10      9     4   36.0   Must Have     Now
 4  Alert thresholds + notifications   8      7     6   33.6   Should Have   Now
 5  Exportable PDF reports             5      8     8   32.0   Should Have   Now
 6  Team-level access controls         6      6     7   25.2   Could Have    Next
 7  Predictive trend analysis          8      4     3    9.6   Won't Have    Icebox
 8  External client portal             6      3     5    9.0   Won't Have    Icebox
```

## Pre-Delivery Checklist

**DO NOT SKIP ANY ITEM.**

```
Pre-Delivery Checklist:
  [ ] All features scored with ICE
  [ ] Priority assigned (Must Have / Should Have / Could Have / Won't Have)
  [ ] Phase assigned (Now / Next / Later / Icebox)
  [ ] Effort assigned for all features
  [ ] Owner assigned where team info was provided
  [ ] Dependencies noted where applicable
  [ ] User approved prioritization before outputting table
  [ ] Roadmap table output successfully
  [ ] Planning guide delivered
  [ ] File saved (if user requested)
```

## Recovery and Troubleshooting

### User Disagrees with ICE Scores
1. Ask which features to re-score and discuss their reasoning
2. Adjust scores, recalculate ICE, re-sort priorities
3. Present revised list for approval before outputting the table

### Feature List Is Vague
Generate reasonable features based on product type and stage. Present for approval before outputting. Never output inferred features without confirmation.

### Too Many Features (more than 30)
Group into categories first. Present category-level priorities, then expand the highest-priority categories into individual features. A roadmap with 40 ungrouped features is a backlog, not a roadmap.

## Anti-Patterns

- **DO NOT** create the database without the full 12-property schema — adding properties after pages exist causes alignment issues
- **DO NOT** skip ICE scoring — prioritization is the core value of a roadmap, not the list itself
- **DO NOT** use dates that imply commitments unless the user confirms deadlines — use relative horizons (Now, Next, Later), not calendar dates
- **DO NOT** add more than 20 features without grouping into categories — uncategorized lists are backlog dumps, not roadmaps
- **DO NOT** assign all features to "Now" — if everything is Now, nothing is prioritized
- **DO NOT** give every feature the same ICE scores — identical scores defeat the framework
- **DO NOT** promise automated notifications, sprint planning, or burndown charts — this is a database, not a full PM tool
