---
name: Project Tracker
version: 3.4.3
description: "Creates a project management task list in markdown with tasks, statuses, owners, due dates, and priorities — pre-populated from a project brief or scope document, for teams replacing spreadsheet-based task management."
---

# Project Tracker

## Fallback for thin input

**If the user has not supplied specific project details, do NOT ask a wall of questions.** Produce a realistic representative task list using reasonable defaults for a mid-sized B2B software company (~250 people, ~$40M revenue) — e.g. a 12-week product launch project with 10-15 tasks across owners, statuses, priorities, and dependencies. Clearly label the assumed context at the top, and after delivering the tracker, offer to swap in the user's real project data.

## Quick Reference: Project Tracker Features

| Feature | Details |
|---------|---------|
| Properties | 9 fields per task record |
| Status stages | 5 (Not Started through Blocked) |
| Priority levels | 4 (Urgent, High, Medium, Low) |
| Database views | 5 pre-built filtered views |
| Seeding | Bulk import from project brief, scope doc, or task list |
| Usage guide | Common operations documented for the user |

## Quick Reference: Database Schema

| Property | Type | Purpose | Default/Options |
|----------|------|---------|-----------------|
| Task Name | Title | Short, action-oriented task description | Required |
| Status | Select | Current state of the task | Not Started |
| Priority | Select | Urgency and importance level | Medium |
| Owner | Rich text | Person responsible for the task | Empty |
| Due Date | Date | Deadline for task completion | Empty |
| Project Phase | Select | Which phase of the project this task belongs to | See options below |
| Description | Rich text | Detailed requirements, acceptance criteria, or notes | Empty |
| Dependencies | Rich text | Other tasks that must complete before this one can start | Empty |
| Tags | Multi-select | Categories for filtering and grouping | See options below |

### Status Options

```
Not Started --> In Progress --> In Review --> Complete --> Blocked
```

| Status | Meaning | Action Required |
|--------|---------|-----------------|
| Not Started | Task is defined but work has not begun | Assign owner and due date if missing |
| In Progress | Actively being worked on | Owner updates Description with progress notes |
| In Review | Work is done, awaiting approval or feedback | Reviewer provides feedback within 2 business days |
| Complete | Task is finished and approved | No further action needed |
| Blocked | Cannot proceed due to a dependency or issue | Log the blocker in Description, escalate to project lead |

### Priority Options

| Priority | Color | When to Use |
|----------|-------|-------------|
| Urgent | Red | Blocks other tasks or has a deadline within 48 hours |
| High | Orange | Critical path item, needed this week |
| Medium | Yellow | Standard task, due within the current phase |
| Low | Gray | Nice-to-have, can slip without impacting the project |

### Default Project Phase Options

Phases are customized per project. If the user does not specify phases, use these defaults:

| Phase | Purpose |
|-------|---------|
| Planning | Research, requirements gathering, scoping |
| Design | Wireframes, mockups, architecture, strategy |
| Build | Development, writing, creation, production |
| Review | Testing, QA, feedback, revisions |
| Launch | Deployment, go-live, publishing, delivery |

### Default Tag Options

`milestone`, `client-facing`, `internal`, `content`, `design`, `development`, `admin`, `research`, `meeting`, `deliverable`

---

## Core Workflow

EVERY PROJECT TRACKER STARTS BY GATHERING THE PROJECT DETAILS AND CREATING THE DATABASE WITH THE FULL SCHEMA BEFORE ADDING ANY TASKS -- NEVER ADD PAGES TO A DATABASE THAT IS MISSING PROPERTIES.

### Phase 1: Gather Project Details

Collect these details from the user before building anything:

1. **Project name** -- what is this project called
2. **Project phases** -- custom phase names, or accept the 5 defaults (Planning, Design, Build, Review, Launch)
3. **Team members** -- list of people who will own tasks (names only; these go in the Owner field)
4. **Timeline** -- overall start date, end date, or phase-level deadlines
5. **Project brief or task list** -- a scope document, brief, bullet list, or verbal description of what needs to get done

If the user provides only items 1 and 2, proceed with all defaults and generate tasks from context. Ask only about missing critical details.

**Brief template for vague requests:**

```
I'll build your project tracker. Quick answers needed:

1. What is the project name?
2. What are the project phases? (default: Planning, Design, Build, Review, Launch)
3. Who are the team members? (names for task ownership)
4. What is the timeline? (start date, end date, or key deadlines)
5. Do you have a project brief, scope doc, or task list I should use to pre-populate tasks?
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

If saving: save the full trackerto the specified path.

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

---

## Example 1: Website Redesign Project

**User request:** "We are redesigning our company website. 4 phases: Discovery, Design, Development, QA/Launch. Team is Sarah (PM), Marcus (designer), Priya (developer), and James (copywriter). Timeline is March 3 to April 25. Here is our scope..."

**Execution:**

1. **Gather:** Project name "Website Redesign", 4 custom phases, 4 team members, 8-week timeline, scope document provided
2. **Parse:** 20 tasks extracted from scope doc and mapped to schema with phases, owners, priorities, and due dates.
3. **Output:** Task table written by phase. Saved to `tracker-website-redesign.md`.

```
DISCOVERY (5 tasks, Mar 3-10):
  Stakeholder kickoff meeting            — Urgent, Sarah, milestone
  Audit current site analytics           — High, Marcus
  Competitor analysis (5 sites)          — Medium, James
  Define sitemap and page hierarchy      — High, Sarah
  Compile brand guidelines and assets    — Medium, James

DESIGN (6 tasks, Mar 14-24):
  Create wireframes for 8 key pages     — High, Marcus
  Design homepage mockup                — Urgent, Marcus, milestone
  Design inner page templates           — High, Marcus
  Write homepage copy                   — High, James
  Write service page copy (4 pages)     — Medium, James
  Client design review and approval     — High, Sarah, client-facing

DEVELOPMENT (6 tasks, Mar 25 - Apr 7):
  Set up staging environment            — High, Priya
  Build homepage                        — Urgent, Priya
  Build inner page templates            — High, Priya
  Integrate contact form and CRM        — Medium, Priya
  Mobile responsive QA pass             — High, Priya
  Content migration (blog posts)        — Medium, James

QA/LAUNCH (3 tasks, Apr 11-25):
  Full QA testing across browsers       — High, Priya
  Client UAT and final approval         — Urgent, Sarah, milestone, client-facing
  DNS switch and go-live                — Urgent, Priya, milestone

Total: 20 tasks | Assigned: 20 | Milestones: 4 | Client-facing: 2
```

5. **Deliver:** View instructions + final summary with phase breakdown and next steps

---

## Example 2: Product Launch Project

**User request:** "We are launching a new product in 6 weeks. Phases are Pre-Launch, Launch Week, and Post-Launch. The team is small."

**Execution:**

1. **Gather:** Project name "Product Launch", 3 custom phases, small team, 6-week timeline
2. **Parse:** Tasks generated from the project type and phases (brief was vague — present for confirmation first).
3. **Output:** Task table written by phase after approval. Saved to `tracker-product-launch.md`.
4. **Seed tasks with approval before creation** (brief was vague — present for confirmation first)
5. **Deliver:** View instructions + final summary with phase breakdown and milestone checkpoints

---

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

---

## Recovery and Troubleshooting

### User Wants to Add More Columns Later

The markdown table can be extended by adding columns. To add a new column: add the header to the `|` row and a corresponding cell to every data row. If a file was previously saved, overwrite it with the updated version.

### User Wants to Add More Tasks Later

Parse the new tasks using the same mapping rules in Phase 2. Add new rows to the existing table grouped by Phase. If a file was previously saved, overwrite it with the updated rows appended.

### Duplicate Detection

Flag potential duplicates before creating pages. Present them to the user for confirmation. **NEVER output duplicate task rows** -- always confirm first.

---

## Anti-Patterns

- **DO NOT** create the database without the full property schema -- adding properties after pages exist causes data alignment issues
- **DO NOT** invent task details not present in the brief -- if the brief is vague, present generated tasks for approval first
- **DO NOT** assign owners that the user did not mention -- leave the Owner field empty for unassigned tasks
- **DO NOT** deliver without the view setup instructions -- the tracker is only valuable when the user can filter and sort tasks
- **DO NOT** set all tasks to "Urgent" or "High" -- a project where everything is urgent has no prioritization at all
- **DO NOT** promise automated reminders, notifications, or status updates -- this is a database, not a project management app with automations
