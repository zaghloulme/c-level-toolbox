# Plan 001: Convert kpi-dashboard from Notion to Claude-native markdown output

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open `skills/kpi-dashboard/SKILL.md` and confirm
> the frontmatter and Step 3 content match the excerpts in "Current state" before
> making any edits.

## Status

- **Priority**: P1
- **Effort**: S
- **Risk**: LOW
- **Depends on**: none
- **Category**: bug / tech-debt
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

The kpi-dashboard skill currently instructs Claude to build a Notion database — a paid external tool requiring a separate MCP integration the user may not have. The `allowed-tools` frontmatter is also broken: it lists only `Read Write Glob` but the skill body calls `notion-create-database` and `notion-create-pages`, meaning the skill silently fails at runtime even for users who do have Notion. The fix replaces Notion output with a pure Claude/markdown dashboard — same KPIs, same structure, same review rhythm, no external dependency.

## Current state

**File:** `skills/kpi-dashboard/SKILL.md`

Frontmatter (lines 1-6):
```
---
name: KPI Dashboard Builder (Notion)
description: "Sets up KPI tracking dashboards in Notion with metrics, targets, status indicators, and trend tracking for centralized business performance visibility."
allowed-tools: Read Write Glob
---
```

Step 3 (lines 63-82) — the Notion build step:
```
### Step 3: Build the Notion Dashboard

Create a Notion database with these properties:

- **KPI Name** (Title)
- **Current Value** (Number)
- **Target** (Number)
- **Status** (Select: On Track / At Risk / Off Track)
- **Trend** (Select: Up / Flat / Down)
- **Period** (Select: This Week / This Month / This Quarter)
- **Category** (Select: Revenue / Growth / Efficiency / Retention)
- **Last Updated** (Date)
- **Notes** (Rich text — for context on changes)

Add a **formula property** for % of Target: `(Current Value / Target) × 100`

Set status rules:
- **On Track:** ≥ 90% of target
- **At Risk:** 70-89% of target
- **Off Track:** < 70% of target
```

Step 4 (lines 84-89) — Notion views:
```
### Step 4: Create Dashboard Views

1. **Summary View** — Gallery view showing all KPIs with status color-coding
2. **Weekly Review** — Table filtered to weekly KPIs, sorted by status
3. **Trend View** — Board view grouped by trend (Up / Flat / Down)
4. **Category View** — Board view grouped by category
```

Recovery line (line 132) referencing Notion/Airtable:
```
- **User doesn't use Notion:** Adapt the dashboard to Google Sheets or Airtable. The structure is the same — only the tool changes.
```

Constraints section begins at line 135.

## Scope

**In scope** (the only file to modify):
- `skills/kpi-dashboard/SKILL.md` — frontmatter name/description/allowed-tools, Step 3, Step 4, recovery line

**Out of scope** (do NOT touch):
- Steps 1, 2, 5 — KPI selection logic and review rhythm are correct and unchanged
- The KPI tables in Step 2 — keep all four business-type tables exactly as-is
- The two example dashboards in the Examples section — keep as-is
- The Constraints section — keep as-is

## Steps

### Step 1: Update frontmatter

Replace the entire frontmatter block (lines 1-6):

**Old:**
```
---
name: KPI Dashboard Builder (Notion)
description: "Sets up KPI tracking dashboards in Notion with metrics, targets, status indicators, and trend tracking for centralized business performance visibility."
allowed-tools: Read Write Glob
---
```

**New:**
```
---
name: KPI Dashboard Builder
description: "Builds KPI tracking dashboards in markdown — metrics, targets, status indicators, and trend tracking for centralized business performance visibility."
allowed-tools: Read Write Glob
---
```

**Verify**: `head -6 "skills/kpi-dashboard/SKILL.md"` → name is `KPI Dashboard Builder` (no "Notion"), description contains "markdown", allowed-tools unchanged.

### Step 2: Replace Step 3 — remove Notion build, add markdown output

Replace the entire Step 3 section with a markdown dashboard output instruction.

**Old Step 3** (find by heading `### Step 3: Build the Notion Dashboard`):
```
### Step 3: Build the Notion Dashboard

Create a Notion database with these properties:

- **KPI Name** (Title)
- **Current Value** (Number)
- **Target** (Number)
- **Status** (Select: On Track / At Risk / Off Track)
- **Trend** (Select: Up / Flat / Down)
- **Period** (Select: This Week / This Month / This Quarter)
- **Category** (Select: Revenue / Growth / Efficiency / Retention)
- **Last Updated** (Date)
- **Notes** (Rich text — for context on changes)

Add a **formula property** for % of Target: `(Current Value / Target) × 100`

Set status rules:
- **On Track:** ≥ 90% of target
- **At Risk:** 70-89% of target
- **Off Track:** < 70% of target
```

**New Step 3:**
```
### Step 3: Build the Dashboard

Output the dashboard as a formatted markdown table. If the user has provided current values, populate them now. If not, use `—` as the placeholder.

```
## KPI Dashboard — [Business Name] — [Month Year]

| KPI | Formula | Current | Target | % of Target | Status | Trend | Category | Updated |
|-----|---------|---------|--------|-------------|--------|-------|----------|---------|
| [KPI Name] | [Formula] | [Value] | [Target] | [X]% | [🟢 On Track / 🟡 At Risk / 🔴 Off Track] | [↑ Up / → Flat / ↓ Down] | [Revenue/Growth/Efficiency/Retention] | [Date] |
```

Status rules:
- **🟢 On Track:** ≥ 90% of target
- **🟡 At Risk:** 70–89% of target
- **🔴 Off Track:** < 70% of target

If the user has current data, calculate % of Target as `(Current / Target) × 100` and assign status automatically. If targets are directional (e.g., "< 5% churn"), note whether the metric is moving in the right direction instead of using the percentage formula.

After outputting the dashboard, ask: "Do you want me to save this as a markdown file? If yes, provide a file path or I'll use `kpi-dashboard-[YYYY-MM].md`."

If saving: use the Write tool to write the dashboard to the specified path.
```

**Verify**: `grep -n "Notion database" "skills/kpi-dashboard/SKILL.md"` → no matches.

### Step 3: Replace Step 4 — remove Notion views, add navigation guidance

**Old Step 4** (find by heading `### Step 4: Create Dashboard Views`):
```
### Step 4: Create Dashboard Views

1. **Summary View** — Gallery view showing all KPIs with status color-coding
2. **Weekly Review** — Table filtered to weekly KPIs, sorted by status
3. **Trend View** — Board view grouped by trend (Up / Flat / Down)
4. **Category View** — Board view grouped by category
```

**New Step 4:**
```
### Step 4: Provide Filtering Guidance

After delivering the dashboard, provide these instructions for working with it:

```
**How to use this dashboard:**

- **Weekly focus:** Look for 🔴 Off Track rows first, then 🟡 At Risk. These need attention.
- **Trend check:** Any KPI with ↓ Down and 🟢 On Track is worth watching — it may cross into At Risk next period.
- **Update frequency:** Replace "Current" values at the cadence in your review rhythm. Update the "Updated" date.
- **If pasting into a spreadsheet:** The table pastes directly into Google Sheets or Excel. Add conditional formatting on the Status column to preserve the color coding.
```
```

**Verify**: `grep -n "Gallery view\|Board view\|Trend View\|Category View" "skills/kpi-dashboard/SKILL.md"` → no matches.

### Step 4: Fix the Recovery line referencing Notion/Airtable

**Old line** (find by text):
```
- **User doesn't use Notion:** Adapt the dashboard to Google Sheets or Airtable. The structure is the same — only the tool changes.
```

**New line:**
```
- **User wants a spreadsheet instead of markdown:** The table in Step 3 pastes directly into Google Sheets or Excel. Provide the markdown output and note they can paste it in.
```

**Verify**: `grep -n "Notion\|Airtable" "skills/kpi-dashboard/SKILL.md"` → no matches.

## Done criteria

- [ ] `head -6 "skills/kpi-dashboard/SKILL.md"` — name is `KPI Dashboard Builder` with no "Notion"
- [ ] `grep -n "notion\|Notion\|Airtable" "skills/kpi-dashboard/SKILL.md"` → no matches
- [ ] `grep -n "mcp__" "skills/kpi-dashboard/SKILL.md"` → no matches
- [ ] Step 3 heading reads `### Step 3: Build the Dashboard`
- [ ] Step 4 heading reads `### Step 4: Provide Filtering Guidance`
- [ ] Steps 1, 2, 5 and all KPI tables are unchanged
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The frontmatter or Step 3 content at the cited location doesn't match the excerpts above
- Any step requires modifying the KPI tables or Examples section
- You find Notion tool calls in a section not listed in this plan

## Maintenance notes

- The LTV formula in Step 2's SaaS table (`Avg revenue per customer × avg lifespan`) omits gross margin — a separate plan (plan 006) corrects this
- The "save as file" instruction in Step 3 relies on the Write tool, which is already in `allowed-tools` — no frontmatter change needed
