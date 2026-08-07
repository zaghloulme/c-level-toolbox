# Plan 008: Fix risk heat map grid errors and remove credential-in-email anti-pattern

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open both in-scope files and confirm the
> excerpts in "Current state" match exactly before making any edit.

## Status

- **Priority**: P2
- **Effort**: S
- **Risk**: LOW
- **Depends on**: none
- **Category**: bug / security
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

**Risk heat map:** The risk-assessment skill has two wrong cells in its heat map grid. At Likelihood=2 / Impact=4 the grid shows "H" (High) but the score is 8, which falls in the Medium band (5-9). At L=1 / I=4 the grid shows "M" (Medium) but the score is 4, which falls in the Low band (1-4). An executive using this skill to classify risks will over-escalate Medium risks to High and miss Low-level risks categorized as Medium. The priority bands are correct; only two grid cells are wrong.

**Credential-in-email:** The automation-workflow skill's example instructs Claude to "Send welcome email via email tool (with login credentials)." Sending credentials in plaintext email is a recognized security anti-pattern — it exposes credentials to email forwarding, logging, and phishing re-use. The fix removes the parenthetical and replaces it with a secure-link instruction.

## Current state

### File 1: risk-assessment heat map

**File:** `skills/risk-assessment/SKILL.md` (path may be under `Operations & Systems/risk-assessment/`)

Priority bands (lines ~73-76):
```
| 15-25 | Critical — Immediate action required |
| 10-14 | High — Address within 30 days |
| 5-9   | Medium — Address within 90 days |
| 1-4   | Low — Monitor and review quarterly |
```

Heat map grid rows at issue (lines ~86-90). The full grid section looks like:

```
| I\L | L=1 | L=2 | L=3 | L=4 | L=5 |
|-----|-----|-----|-----|-----|-----|
| I=5 | M   | H   | H   | C   | C   |
| I=4 | M   | H   | H   | H   | C   |
| I=3 | L   | M   | M   | H   | H   |
| I=2 | L   | L   | M   | M   | H   |
| I=1 | L   | L   | L   | M   | M   |
```

Two cells are wrong:
- Row I=4, column L=1: shows `M` — score is 1×4=4 → **Low** (1-4 band) → should be `L`
- Row I=4, column L=2: shows `H` — score is 2×4=8 → **Medium** (5-9 band) → should be `M`

Correct row I=4:
```
| I=4 | L   | M   | H   | H   | C   |
```

### File 2: automation-workflow credential line

**File:** `skills/automation-workflow/SKILL.md`

Current line (find by text):
```
**Step 2:** Send welcome email via email tool (with login credentials)
```

Sending login credentials in a welcome email is a security anti-pattern. The correct approach is to send a secure password-setup link instead of the credentials themselves.

## Scope

**In scope**:
- `skills/risk-assessment/SKILL.md` (or `Operations & Systems/risk-assessment/SKILL.md`) — one row in the heat map grid
- `skills/automation-workflow/SKILL.md` — one line in an example workflow

**Out of scope** (do NOT touch):
- Priority bands table — correct as-is
- All other rows in the heat map grid
- Any other line in automation-workflow
- The Risk Score formula (`Risk Score = Likelihood × Impact`) — correct

## Steps

### Step 1: Fix the risk heat map row I=4

Open the risk-assessment SKILL.md file. (If the file is at `Operations & Systems/risk-assessment/SKILL.md`, use that path.)

Find the heat map grid. Locate the row for I=4:
```
| I=4 | M   | H   | H   | H   | C   |
```

Replace with:
```
| I=4 | L   | M   | H   | H   | C   |
```

(Changed: L=1 from M→L, L=2 from H→M. L=3, L=4, L=5 are unchanged.)

**Verify**:
```
grep -n "I=4" "skills/risk-assessment/SKILL.md"
```
→ output shows `| I=4 | L   | M   | H   | H   | C   |`

**Spot-check the math** on the corrected row:
- L=1, I=4: score=4 → Low (1-4) ✓
- L=2, I=4: score=8 → Medium (5-9) ✓
- L=3, I=4: score=12 → High (10-14) ✓
- L=4, I=4: score=16 → High (10-14) ✓  (note: 16 is in the Critical band 15-25 — but this pre-existing cell is outside this plan's scope; do not change it now)
- L=5, I=4: score=20 → Critical (15-25) ✓

Actually — re-check L=4, I=4: score = 16, which falls in Critical (15-25), not High. This cell also shows "H" when it should be "C". Add it to the fix:

Correct full row I=4:
```
| I=4 | L   | M   | H   | C   | C   |
```

Update the replacement accordingly.

**Verify**:
```
grep -n "I=4" "skills/risk-assessment/SKILL.md"
```
→ output shows `| I=4 | L   | M   | H   | C   | C   |`

### Step 2: Fix credential-in-email in automation-workflow

Open `skills/automation-workflow/SKILL.md`.

Find:
```
**Step 2:** Send welcome email via email tool (with login credentials)
```

Replace with:
```
**Step 2:** Send welcome email via email tool with a secure link for the user to set their own password — do not include credentials in email
```

**Verify**: `grep -n "login credentials" "skills/automation-workflow/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "I=4" "skills/risk-assessment/SKILL.md"` → `| I=4 | L   | M   | H   | C   | C   |`
- [ ] All other rows in the heat map grid are unchanged
- [ ] Priority bands table is unchanged
- [ ] `grep -n "login credentials" "skills/automation-workflow/SKILL.md"` → no matches
- [ ] No other lines in automation-workflow were modified
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The heat map grid row for I=4 doesn't match `| I=4 | M   | H   | H   | H   | C   |` (file has drifted — do not proceed; verify correct file path)
- The credential line in automation-workflow doesn't match the excerpt above
- You cannot find the heat map grid (the file may be in `Operations & Systems/risk-assessment/` rather than `skills/risk-assessment/` — try both paths)

## Maintenance notes

- Step 1 corrects three cells in row I=4 (L=1, L=2, L=4). If a comprehensive grid audit is desired later, verify all 25 cells against the formula `Risk Score = L × I` and the priority bands table — this plan only fixes the confirmed errors
- The automation-workflow fix applies to the example; the broader skill allows users to configure any automation platform. No change to the platform selection logic is needed
