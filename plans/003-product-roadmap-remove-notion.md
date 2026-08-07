# Plan 003: Convert product-roadmap from Notion MCP to Claude-native markdown output

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open `skills/product-roadmap/SKILL.md` and confirm
> the frontmatter and Phase 3 heading match the excerpts in "Current state"
> before making any edits.

## Status

- **Priority**: P1
- **Effort**: M
- **Risk**: LOW
- **Depends on**: none
- **Category**: bug / tech-debt
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

The product-roadmap skill requires a connected Notion workspace to do anything useful — Phases 3, 4, and 5 are entirely Notion MCP calls. Users without Notion get no output at all. The ICE scoring framework and schema design in the skill are genuinely valuable; the fix preserves all of that logic and outputs it as a clean markdown table + file, removing the Notion dependency entirely. The two worked examples are also preserved; only the Notion execution steps are replaced.

## Current state

**File:** `skills/product-roadmap/SKILL.md`

Frontmatter (lines 1-6):
```
---
name: Product Roadmap Builder (Notion)
description: "Creates product roadmaps in Notion with milestones, feature priorities, release timelines, and status tracking for products with iterative development cycles."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
---
```

Phase 1 asks for "Notion parent page" as question 4:
```
4. **Notion parent page** — where should the roadmap live (page name or URL)
```

Brief template in Phase 1 asks:
```
4. Which Notion page should I create the roadmap under?
```

Phase 3 heading:
```
### Phase 3: Search Notion for Parent Page
```

Phase 4 heading:
```
### Phase 4: Create the Roadmap Database
```

Phase 5 heading:
```
### Phase 5: Seed Features and Deliver
```

Pre-Delivery Checklist references Notion verification calls.

Recovery section contains Notion-specific troubleshooting.

## Scope

**In scope**:
- `skills/product-roadmap/SKILL.md` — frontmatter, Phase 1 question 4 + brief template, Phase 3, Phase 4, Phase 5, Pre-Delivery Checklist, Recovery section, both examples' execution steps 3-5

**Out of scope** (do NOT touch):
- Quick Reference table at the top — keep as-is
- Database Schema section — keep all 12 properties; they become markdown columns
- Status Flow table — keep as-is
- Effort Sizing line — keep as-is
- ICE Scoring Framework section — keep entirely as-is
- Phase 1 questions 1-3, 5-9 — keep as-is
- Phase 2 (ICE scoring and prioritization) — keep entirely as-is
- Anti-Patterns section — keep as-is, except remove the two Notion-specific items at the end

## Steps

### Step 1: Update frontmatter

**Old:**
```
---
name: Product Roadmap Builder (Notion)
description: "Creates product roadmaps in Notion with milestones, feature priorities, release timelines, and status tracking for products with iterative development cycles."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
---
```

**New:**
```
---
name: Product Roadmap Builder
description: "Creates product roadmaps in markdown with ICE-scored features, milestones, release timelines, and status tracking — output ready to paste into any project management tool."
allowed-tools: Read Write Glob
---
```

**Verify**: `head -6 "skills/product-roadmap/SKILL.md"` → name `Product Roadmap Builder` (no "Notion"), allowed-tools `Read Write Glob`.

### Step 2: Remove "Notion parent page" from Phase 1

**Old question 4 in Phase 1:**
```
4. **Notion parent page** — where should the roadmap live (page name or URL)
```
**Remove this line entirely.** Renumber questions 5-9 to 4-8.

**Old brief template line:**
```
4. Which Notion page should I create the roadmap under?
```
**Remove this line entirely.** Renumber the remaining template lines.

**Verify**: `grep -n "Notion page\|parent page" "skills/product-roadmap/SKILL.md"` → no matches.

### Step 3: Replace Phase 3 — remove Notion search, add output step

Find the entire Phase 3 section (`### Phase 3: Search Notion for Parent Page` through just before `### Phase 4:`).

**New Phase 3:**
```
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
```

**Verify**: `grep -n "notion-search\|notion-fetch\|notion-create" "skills/product-roadmap/SKILL.md"` → no matches.

### Step 4: Replace Phase 4 — remove Notion database creation

Find the entire Phase 4 section (`### Phase 4: Create the Roadmap Database` through just before `### Phase 5:`).

**New Phase 4:**
```
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
```

### Step 5: Replace Phase 5 — remove Notion seeding

Find the entire Phase 5 section (`### Phase 5: Seed Features and Deliver` through the end of that section, before `## Example`).

**New Phase 5:**
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
```

### Step 6: Replace the Pre-Delivery Checklist

Find the `## Pre-Delivery Checklist` section and replace it.

**New Pre-Delivery Checklist:**
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
```

### Step 7: Replace the Recovery section

Find the `## Recovery and Troubleshooting` section. Replace the three Notion-specific items; keep the last two (User Disagrees with ICE Scores + any non-Notion items).

**Remove entirely:**
- `### Notion Search Returns No Results` and its content
- `### Database Creation Fails` and its content
- `### Feature Seeding Partially Fails` and its content
- `### Notion API Rate Limits` and its content

**Keep and rename the section:**
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
```

### Step 8: Remove two Notion-specific Anti-Patterns

Find the Anti-Patterns section. Remove these two items:
- `- **DO NOT** skip parent page confirmation — creating under the wrong page is difficult to undo`
- `- **DO NOT** create views programmatically — Notion MCP does not support this`

**Verify**: `grep -n "Notion\|notion\|mcp__" "skills/product-roadmap/SKILL.md"` → no matches.

### Step 9: Update example execution steps 3-5

In **Example 1** (BillFlow), find steps 3-5 of the Execution section:
```
3. **Search:** `notion-search` "BillFlow Product" -> `pg_billflow123`
4. **Create:** Database "BillFlow Roadmap" with custom categories... -> `db_roadmap456`
5. **Seed and deliver:**
```

Replace with:
```
3. **Output:** Roadmap table written with 12 features, ICE scores, priorities, and phases. Saved to `roadmap-billflow.md`.
4. **Deliver:** Planning guide + next steps provided.
```
(Remove the old steps 3, 4, 5 and replace with these two lines. Renumber if needed.)

In **Example 2** (Ops Analytics), do the same replacement for steps 3-5.

**Verify**: `grep -n "notion-search\|notion-create\|pg_\|db_" "skills/product-roadmap/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "notion\|Notion\|mcp__" "skills/product-roadmap/SKILL.md"` → no matches
- [ ] `head -6 "skills/product-roadmap/SKILL.md"` → name `Product Roadmap Builder`, allowed-tools `Read Write Glob`
- [ ] ICE Scoring Framework section is unchanged
- [ ] Database Schema section is unchanged
- [ ] Both example ICE scoring tables are unchanged
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The frontmatter at the cited location doesn't match the excerpt above
- Any step requires modifying the ICE Scoring Framework or Database Schema
- You find a Notion reference in a section not listed in this plan's scope

## Maintenance notes

- The Database Schema section (12 properties) is kept intentionally — it now serves as the column spec for the markdown table rather than a Notion schema; no change needed
- If a future version adds export to a specific PM tool (Linear, Jira), Phase 3 is the right place to add that as an optional output step
