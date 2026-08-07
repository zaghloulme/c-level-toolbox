# Plan 004: Convert project-tracker from Notion MCP to Claude-native markdown output

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open `skills/project-tracker/SKILL.md` and confirm
> the frontmatter and Phase 2 heading match the excerpts in "Current state"
> before making any edits.

## Status

- **Priority**: P1
- **Effort**: M
- **Risk**: LOW
- **Depends on**: none
- **Category**: bug / tech-debt
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

The project-tracker skill requires a connected Notion workspace — Phases 2, 3, and 4 are entirely Notion MCP calls to create and populate a database. Users without Notion get nothing. The task schema, status flow, and priority system in this skill are solid; the fix preserves all of it and outputs a markdown task table to a file instead. Both worked examples are kept; only the Notion execution is replaced.

## Current state

**File:** `skills/project-tracker/SKILL.md`

Frontmatter (lines 1-6):
```
---
name: Project Tracker
description: "Creates a project management database in Notion with tasks, statuses, owners, due dates, and priorities — pre-populated from a project brief or scope document, for teams replacing spreadsheet-based task management."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
---
```

Phase 1 asks for "Notion parent page" as question 2:
```
2. **Notion parent page** -- where should the tracker database live (page name or URL)
```

Brief template asks:
```
2. Which Notion page should I create the tracker under?
```

Phase 2 heading:
```
### Phase 2: Create the Database in Notion
```

Phase 3 heading:
```
### Phase 3: Pre-Populate Tasks from Project Brief
```

Phase 4 heading:
```
### Phase 4: Set Up Views and Confirm
```

Pre-Delivery Checklist contains Notion verification calls.

Recovery section contains Notion-specific troubleshooting under four headings.

## Scope

**In scope**:
- `skills/project-tracker/SKILL.md` — frontmatter, Phase 1 question 2 + brief template, Phase 2, Phase 3, Phase 4, Pre-Delivery Checklist, Recovery section, both examples' execution steps

**Out of scope** (do NOT touch):
- Quick Reference table
- Database Schema section (9 properties, status/priority/phase/tag options) — keep entirely; it becomes the column spec for the markdown table
- Status Flow diagram and table — keep as-is
- Priority Options table — keep as-is
- Default Project Phase Options — keep as-is
- Default Tag Options — keep as-is
- Core Workflow heading and the EVERY PROJECT TRACKER... rule line — keep as-is
- Phase 1 questions 1, 3-6 — keep as-is
- Anti-Patterns section — keep as-is except remove two Notion-specific items

## Steps

### Step 1: Update frontmatter

**Old:**
```
---
name: Project Tracker
description: "Creates a project management database in Notion with tasks, statuses, owners, due dates, and priorities — pre-populated from a project brief or scope document, for teams replacing spreadsheet-based task management."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
---
```

**New:**
```
---
name: Project Tracker
description: "Creates a project management task list in markdown with tasks, statuses, owners, due dates, and priorities — pre-populated from a project brief or scope document, for teams replacing spreadsheet-based task management."
allowed-tools: Read Write Glob
---
```

**Verify**: `head -6 "skills/project-tracker/SKILL.md"` → description contains "markdown", allowed-tools is `Read Write Glob`.

### Step 2: Remove "Notion parent page" from Phase 1

**Old question 2:**
```
2. **Notion parent page** -- where should the tracker database live (page name or URL)
```
**Remove this line.** Renumber questions 3-6 to 2-5.

**Old brief template line:**
```
2. Which Notion page should I create the tracker under?
```
**Remove this line.** Renumber remaining template lines.

**Verify**: `grep -n "Notion page\|parent page" "skills/project-tracker/SKILL.md"` → no matches.

### Step 3: Replace Phase 2 — remove Notion database creation, add markdown output

Find the entire Phase 2 section (`### Phase 2: Create the Database in Notion` through just before `### Phase 3:`).

**New Phase 2:**
```
### Phase 2: Parse Tasks from Brief

Parse the user's project brief, scope document, or task list into discrete tasks. For each task, map to the 9-property schema:

- **Task Name** — short, action-oriented (start with a verb: "Design homepage wireframe", "Write onboarding email sequence")
- **Status** — default "Not Started" for all new tasks
- **Priority** — infer from context; milestone and deadline-sensitive tasks get High or Urgent; default Medium
- **Owner** — assign based on user instructions; leave empty if no team info provided
- **Due Date** — calculate from timeline if provided; leave empty if not
- **Project Phase** — assign based on task nature (Planning, Design, Build, Review, Launch — or user's custom phases)
- **Description** — key details, acceptance criteria, or specs from the brief (keep brief — one line max)
- **Dependencies** — note if a task explicitly depends on another (e.g., "depends on: Design homepage wireframe")
- **Tags** — infer from content (client deliverable → `client-facing` + `deliverable`, research → `research`)

**IF THE BRIEF IS VAGUE OR INCOMPLETE:**
Generate reasonable tasks based on the project type and phases. Present the generated task list to the user for approval BEFORE outputting:
```
I generated [N] tasks from your brief. Here is the breakdown by phase:

PLANNING ([N] tasks):
  1. [Task name] — [Priority]
  2. [Task name] — [Priority]

Want me to proceed, or add, remove, or modify any tasks?
```
**NEVER output a task table without confirmation when data is inferred rather than explicit.**
```

**Verify**: `grep -n "notion-search\|notion-create-database\|notion-fetch" "skills/project-tracker/SKILL.md"` → no matches.

### Step 4: Replace Phase 3 — remove Notion page creation, add markdown table output

Find the entire Phase 3 section (`### Phase 3: Pre-Populate Tasks from Project Brief` through just before `### Phase 4:`).

**New Phase 3:**
```
### Phase 3: Output the Task Table

Output the full task list as a markdown table, grouped by Project Phase:

```
## [Project Name] Tracker

### [Phase Name]

| # | Task | Status | Priority | Owner | Due Date | Tags | Dependencies |
|---|------|--------|----------|-------|----------|------|--------------|
| 1 | [Task name] | Not Started | High | [Owner] | [Date] | milestone | — |
```

(Repeat the table for each phase.)

After the table, provide a summary line:
```
Total: [N] tasks | Assigned: [N] | Unassigned: [N] | Milestones: [N]
```

Then ask: "Do you want me to save this as a file? I'll use `tracker-[project-name].md` unless you specify a path."

If saving: use the Write tool to write the full tracker to the specified path.
```

**Verify**: `grep -n "notion-create-pages" "skills/project-tracker/SKILL.md"` → no matches.

### Step 5: Replace Phase 4 — remove Notion views, add filtering guidance

Find the entire Phase 4 section (`### Phase 4: Set Up Views and Confirm` through end of that section, before `## Example`).

**New Phase 4:**
```
### Phase 4: Deliver and Close

After the task table and file save, provide this usage guide:

```
**How to use this tracker:**

- **Sort by priority:** Look at Urgent rows first, then High. These define your week.
- **Check blockers daily:** Any task with Status "Blocked" needs a resolution before it cascades.
- **Weekly update:** Change Status values as work progresses. Update Due Dates when timelines shift.
- **Add new tasks:** Add a row with Status=Not Started. Assign Phase, Priority, Owner, and Due Date before starting work.
- **Paste into a spreadsheet:** The table pastes directly into Google Sheets or Excel. Use conditional formatting on the Status column for visual tracking.
```

Finish with 3-4 concrete next steps: assign any unassigned tasks, confirm due dates with team members, schedule a weekly check-in, identify and resolve any existing blockers.
```

### Step 6: Replace the Pre-Delivery Checklist

Find `## Pre-Delivery Checklist` and replace it.

**New:**
```
## Pre-Delivery Checklist

**DO NOT SKIP ANY ITEM.**

```
Pre-Delivery Checklist:
  [ ] All tasks parsed from brief (or generated and approved)
  [ ] Status set to Not Started for all new tasks
  [ ] Priority assigned for every task
  [ ] Project Phase assigned for every task
  [ ] Owners assigned where team info was provided
  [ ] Due dates set where timeline was provided
  [ ] Milestones tagged
  [ ] Dependencies noted where applicable
  [ ] Task table output by phase
  [ ] Summary line included (total, assigned, unassigned, milestones)
  [ ] Usage guide delivered
  [ ] File saved (if user requested)
  [ ] No duplicate tasks
```
```

### Step 7: Replace the Recovery section

Find `## Recovery and Troubleshooting`. Remove all four Notion-specific headings and their content:
- `### Notion Search Returns No Results`
- `### Database Creation Fails`
- `### Task Seeding Partially Fails`
- `### Notion API Rate Limits`

Keep `### User Wants to Modify the Schema Later` — rephrase it slightly:

**Old:**
```
### User Wants to Modify the Schema Later

**Notion MCP does not support modifying existing database schemas.** Instruct the user:
- To add a property: open the tracker, click "+" in the header row, choose type, name it
- To modify a property: click the column header, select "Edit property", change type/name/options
```

**New:**
```
### User Wants to Add More Columns Later

The markdown table can be extended by adding columns. To add a new column: add the header to the `|` row and a corresponding cell to every data row. If the file was saved, use the Write tool to overwrite it with the updated version.
```

Keep `### User Wants to Add More Tasks Later` — rephrase:

**Old:** references `notion-fetch`, `notion-create-pages`
**New:**
```
### User Wants to Add More Tasks Later

Parse the new tasks using the same mapping rules in Phase 2. Add new rows to the existing table grouped by Phase. If the file was saved, use the Write tool to overwrite it with the updated rows appended.
```

Keep `### Duplicate Detection` as-is but remove the "NEVER create duplicate task records" line — replace with "NEVER output duplicate task rows".

**Verify**: `grep -n "Notion\|notion\|mcp__" "skills/project-tracker/SKILL.md"` → no matches.

### Step 8: Remove two Notion-specific Anti-Patterns

Find the Anti-Patterns section. Remove:
- `- **DO NOT** skip the parent page confirmation — creating a tracker under the wrong page is difficult to undo`
- `- **DO NOT** create views programmatically — Notion MCP does not support this; provide manual instructions instead`

**Verify**: `grep -n "parent page\|views programmatically" "skills/project-tracker/SKILL.md"` → no matches.

### Step 9: Update example execution steps

**Example 1 (Website Redesign):** Find steps 2-5 of the Execution section:
```
2. **Search:** `notion-search` for "Active Projects" -> found `pg_active456`, confirmed
3. **Create:** `notion-create-database`... -> `db_redesign789`
4. **Seed 20 tasks:**
```

Replace steps 2-3 with:
```
2. **Parse:** 20 tasks extracted from scope doc and mapped to schema with phases, owners, priorities, and due dates.
3. **Output:** Task table written by phase. Saved to `tracker-website-redesign.md`.
```
Keep the task list content (DISCOVERY, DESIGN, etc.) and the final summary line. Remove the `notion-create-database` and `notion-search` lines.

**Example 2 (Product Launch):** Find and similarly replace the Notion-specific execution steps 2-3. Keep the rest.

**Verify**: `grep -n "notion-search\|notion-create\|pg_\|db_" "skills/project-tracker/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "notion\|Notion\|mcp__" "skills/project-tracker/SKILL.md"` → no matches
- [ ] `head -6 "skills/project-tracker/SKILL.md"` → description contains "markdown", allowed-tools `Read Write Glob`
- [ ] Database Schema section (9 properties) is unchanged
- [ ] Status Flow and Priority Options tables are unchanged
- [ ] Both example task lists (the 20-task DISCOVERY/DESIGN/etc. blocks) are unchanged
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The frontmatter at the cited location doesn't match the excerpt above
- Any step requires modifying the Database Schema or Status Flow sections
- You find a Notion reference in a section not covered by this plan

## Maintenance notes

- The "Duplicate Detection" section in Recovery still makes sense for the markdown output case — flag when the same task name appears twice in the parsed brief
- If a future version adds export to Jira or Linear, Phase 3 is the right extension point
