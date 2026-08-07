# Plan 007: Add legal disclaimers to non-compete-agreement and partnership-agreement

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open both in-scope files and confirm no
> `## Legal Disclaimer` section exists and the frontmatter matches. Run:
> `grep -n "Legal Disclaimer" "skills/non-compete-agreement/SKILL.md"` and
> `grep -n "Legal Disclaimer" "skills/partnership-agreement/SKILL.md"` — both
> should return no matches before you start.

## Status

- **Priority**: P2
- **Effort**: S
- **Risk**: LOW
- **Depends on**: none
- **Category**: security
- **Planned at**: no-git-repo, 2026-08-07

## Why this matters

The `non-compete-agreement` and `partnership-agreement` skills produce legally binding documents with jurisdiction-specific legal consequences. Neither skill has a legal disclaimer section. The `nda-template` skill in the same toolbox has one at lines 12–15 — these two skills are inconsistent with it and expose users to risk if they rely on AI-generated legal documents without professional review. The fix adds a disclaimer block to each skill using the same format as the NDA skill.

## Current state

**Reference — nda-template disclaimer** (this is the pattern to match):
File: `skills/nda-template/SKILL.md` lines 12-15:
```
## Legal Disclaimer

This skill generates NDA templates for reference and negotiation purposes. It does not constitute legal advice. Have any NDA reviewed by a qualified attorney in the governing jurisdiction before signing or enforcing.
```

**File 1:** `skills/non-compete-agreement/SKILL.md`
- No `## Legal Disclaimer` section (confirmed: `grep -n "Legal Disclaimer"` returns no output)
- Has `## Recovery` section near the end of the file
- The only attorney reference is buried in the Phase 4 checklist: `- [ ] Agreement reviewed by an attorney in the governing jurisdiction`

**File 2:** `skills/partnership-agreement/SKILL.md`
- No `## Legal Disclaimer` section (confirmed: `grep -n "Legal Disclaimer"` returns no output)

The disclaimer should appear immediately after the frontmatter block (after the closing `---`) and before the `# [Skill Name]` heading — matching the NDA skill's position.

## Scope

**In scope**:
- `skills/non-compete-agreement/SKILL.md` — add `## Legal Disclaimer` section after frontmatter
- `skills/partnership-agreement/SKILL.md` — add `## Legal Disclaimer` section after frontmatter

**Out of scope** (do NOT touch):
- Any other content in either file
- `skills/nda-template/SKILL.md` — already correct, do not modify
- The Phase 4 checklist attorney line in non-compete — keep it as a checklist item too

## Steps

### Step 1: Add disclaimer to non-compete-agreement

Open `skills/non-compete-agreement/SKILL.md`.

The file currently begins:
```
---
name: Non-Compete Agreement
description: "Drafts enforceable non-compete and non-solicitation clauses..."
allowed-tools: Read Write Glob
---

# Non-Compete Agreement
```

Insert the disclaimer block between the closing `---` and the `# Non-Compete Agreement` heading:

```
---
name: Non-Compete Agreement
description: "Drafts enforceable non-compete and non-solicitation clauses..."
allowed-tools: Read Write Glob
---

## Legal Disclaimer

This skill generates non-compete and non-solicitation templates for reference and drafting purposes. It does not constitute legal advice. Non-compete enforceability varies significantly by jurisdiction — some prohibit them entirely. Have any agreement reviewed by a qualified attorney in the governing jurisdiction before signing or enforcing.

# Non-Compete Agreement
```

**Verify**: `grep -n "Legal Disclaimer" "skills/non-compete-agreement/SKILL.md"` → match found on the line after the closing `---`.

### Step 2: Add disclaimer to partnership-agreement

Open `skills/partnership-agreement/SKILL.md`.

The file currently begins with frontmatter followed by `# Partnership Agreement` (or similar heading).

Insert the same disclaimer block between the closing `---` and the `#` heading, with wording appropriate for partnership agreements:

```
## Legal Disclaimer

This skill generates partnership agreement templates for reference and drafting purposes. It does not constitute legal advice. Partnership agreements carry significant legal and financial obligations. Have any agreement reviewed by a qualified attorney in the governing jurisdiction before signing or enforcing.
```

**Verify**: `grep -n "Legal Disclaimer" "skills/partnership-agreement/SKILL.md"` → match found.

### Step 3: Confirm both files are consistent with the NDA pattern

Run:
```
grep -A3 "Legal Disclaimer" "skills/nda-template/SKILL.md"
grep -A3 "Legal Disclaimer" "skills/non-compete-agreement/SKILL.md"
grep -A3 "Legal Disclaimer" "skills/partnership-agreement/SKILL.md"
```

All three should show a `## Legal Disclaimer` heading followed by a disclaimer sentence.

## Done criteria

- [ ] `grep -n "Legal Disclaimer" "skills/non-compete-agreement/SKILL.md"` → match found
- [ ] `grep -n "Legal Disclaimer" "skills/partnership-agreement/SKILL.md"` → match found
- [ ] Disclaimer appears immediately after the frontmatter closing `---` in both files
- [ ] No other content in either file was modified
- [ ] `grep -n "Legal Disclaimer" "skills/nda-template/SKILL.md"` → still present (unchanged)
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- A `## Legal Disclaimer` section already exists in either file (someone already applied this fix)
- The frontmatter or file structure doesn't match the description above
- The partnership-agreement file doesn't have a clear frontmatter block

## Maintenance notes

- If additional legal document skills are added to the toolbox in the future (e.g., employment-agreement, shareholder-agreement), apply the same disclaimer pattern
- The three-skill set (NDA, non-compete, partnership) now has consistent disclaimers — if the NDA disclaimer wording is ever updated, apply the same update to these two files
