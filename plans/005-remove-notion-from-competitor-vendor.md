# Plan 005: Remove Notion as primary save path from competitor-analysis and vendor-evaluation

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open both in-scope files and confirm the
> Step 4 / Option A headings and frontmatter match the excerpts in "Current state"
> before making any edits.

## Status

- **Priority**: P1
- **Effort**: S
- **Risk**: LOW
- **Depends on**: none
- **Category**: tech-debt
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

Both `competitor-analysis` and `vendor-evaluation` offer Notion as "Option A" (the primary save path) and markdown as "Option B" (the fallback). Notion is a paid external tool. The skills' core value — the scoring matrix, SWOT, recommendations — is pure Claude output that needs no external tool. Making markdown the primary path means the skill works for every user without any integration, while keeping the option to paste into Notion afterward. The analysis logic is unchanged.

## Current state

**File 1:** `skills/competitor-analysis/SKILL.md`

Frontmatter line 4:
```
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
```

Step 4 structure (find by heading `## Step 4: Act`):
```
### Option A: Save to Notion Database
[calls notion-search, notion-create-database, notion-create-pages]

### Option B: Save as Markdown File
If the user prefers a local file or does not have Notion connected:
1. Write the full analysis to a markdown file at the user's preferred path
2. Default filename: `competitor-analysis-[category].md`
3. Include all sections: matrix, SWOTs, gaps, threats, recommendations
```

Recovery section contains:
```
### Notion Save Fails
1. Call `notion-search` to verify workspace access
2. **Fallback:** Save the full analysis as a markdown file. All data can be transferred to Notion later.
```

Anti-Patterns section contains:
```
- **DO NOT** save to Notion before the user reviews and approves the analysis — always present first, save second
```

**File 2:** `skills/vendor-evaluation/SKILL.md`

Frontmatter line 4:
```
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search
```

Step 4 structure is the same pattern: Option A = Notion (primary), Option B = Markdown (fallback).

Recovery section contains:
```
### Notion Save Fails
1. Call `notion-search` to verify workspace access
2. **Fallback:** Save the full evaluation as a markdown file. All data can be transferred to Notion later.
```

Anti-Patterns section contains:
```
- **DO NOT save to Notion before the user reviews and approves the evaluation.** Present first, save second.
```

## Scope

**In scope** (the only changes to make):
- `skills/competitor-analysis/SKILL.md`: frontmatter allowed-tools, Step 4 Option A + Option B, "Notion Save Fails" recovery item, one Anti-Pattern line
- `skills/vendor-evaluation/SKILL.md`: same four locations

**Out of scope** (do NOT touch):
- Steps 1, 2, 3 in both skills (gather, analyze, present) — unchanged
- The GATE line before Step 4 — unchanged
- All scoring logic, matrices, and recommendation sections — unchanged
- All other Recovery items — unchanged
- All other Anti-Pattern items — unchanged

## Steps

### Step 1: Fix competitor-analysis frontmatter

Open `skills/competitor-analysis/SKILL.md`.

Find the `allowed-tools` line and replace the entire line:

**Old:**
```
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
```

**New:**
```
allowed-tools: Read Write Glob
```

**Verify**: `grep -n "allowed-tools" "skills/competitor-analysis/SKILL.md"` → `allowed-tools: Read Write Glob`

### Step 2: Replace competitor-analysis Step 4 save options

Find the section from `### Option A: Save to Notion Database` through the end of `### Option B: Save as Markdown File` (ending just before `### Suggest Review Cadence`).

**Replace with:**
```
### Save the Analysis

1. Write the full analysis to a markdown file using the Write tool
2. Default filename: `competitor-analysis-[category].md` — ask for a preferred path if the user specifies one
3. Include all sections: matrix, SWOTs, gaps, threats, recommendations

Confirm the file path after saving.
```

**Verify**: `grep -n "notion-search\|notion-create-database\|notion-create-pages\|notion-fetch" "skills/competitor-analysis/SKILL.md"` → no matches.

### Step 3: Remove competitor-analysis "Notion Save Fails" recovery item

Find and remove the entire `### Notion Save Fails` block:
```
### Notion Save Fails

1. Call `notion-search` to verify workspace access
2. **Fallback:** Save the full analysis as a markdown file. All data can be transferred to Notion later.
```

**Verify**: `grep -n "Notion Save Fails" "skills/competitor-analysis/SKILL.md"` → no matches.

### Step 4: Fix competitor-analysis Anti-Patterns line

Find the line:
```
- **DO NOT** save to Notion before the user reviews and approves the analysis — always present first, save second
```

Replace with:
```
- **DO NOT** save to file before the user reviews and approves the analysis — always present first, save second
```

**Verify**: `grep -n "Notion\|notion\|mcp__" "skills/competitor-analysis/SKILL.md"` → no matches.

### Step 5: Fix vendor-evaluation frontmatter

Open `skills/vendor-evaluation/SKILL.md`.

Find the `allowed-tools` line:
```
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search
```

Replace with:
```
allowed-tools: Read Write Glob
```

**Verify**: `grep -n "allowed-tools" "skills/vendor-evaluation/SKILL.md"` → `allowed-tools: Read Write Glob`

### Step 6: Replace vendor-evaluation Step 4 save options

Find the section from `### Option A: Save to Notion Database` through the end of `### Option B: Save as Markdown File` (ending just before `### Decision Summary for Stakeholders`).

**Replace with:**
```
### Save the Evaluation

1. Write the full evaluation to a markdown file using the Write tool
2. Default filename: `vendor-evaluation-[category].md` — ask for a preferred path if the user specifies one
3. Include all sections: scoring matrix, cost analysis, vendor profiles, recommendation, next steps

Confirm the file path after saving.
```

**Verify**: `grep -n "notion-search\|notion-create-database\|notion-create-pages" "skills/vendor-evaluation/SKILL.md"` → no matches.

### Step 7: Remove vendor-evaluation "Notion Save Fails" recovery item

Find and remove the entire `### Notion Save Fails` block:
```
### Notion Save Fails

1. Call `notion-search` to verify workspace access
2. **Fallback:** Save the full evaluation as a markdown file. All data can be transferred to Notion later.
```

**Verify**: `grep -n "Notion Save Fails" "skills/vendor-evaluation/SKILL.md"` → no matches.

### Step 8: Fix vendor-evaluation Anti-Patterns line

Find the line:
```
- **DO NOT save to Notion before the user reviews and approves the evaluation.** Present first, save second.
```

Replace with:
```
- **DO NOT save to file before the user reviews and approves the evaluation.** Present first, save second.
```

**Verify**: `grep -n "Notion\|notion\|mcp__" "skills/vendor-evaluation/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "notion\|Notion\|mcp__" "skills/competitor-analysis/SKILL.md"` → no matches
- [ ] `grep -n "notion\|Notion\|mcp__" "skills/vendor-evaluation/SKILL.md"` → no matches
- [ ] Both files have `allowed-tools: Read Write Glob`
- [ ] Both files have a single "Save the Analysis/Evaluation" section replacing the two-option block
- [ ] All analysis/scoring/recommendation content in both files is unchanged
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The `allowed-tools` line or Option A heading doesn't match the excerpt above (file has drifted)
- Any step requires touching the scoring logic or recommendation sections
- You find a Notion reference in a section not listed in this plan

## Maintenance notes

- The "Decision Summary for Stakeholders" section in vendor-evaluation (kept unchanged) and the "Suggest Review Cadence" block in competitor-analysis (kept unchanged) are standalone sections that don't reference Notion — no change needed there
- If a user later asks how to get their analysis into Notion: the markdown file can be pasted into any Notion page as a code block or table
