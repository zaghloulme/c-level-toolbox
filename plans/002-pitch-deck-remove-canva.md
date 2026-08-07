# Plan 002: Convert pitch-deck from Canva MCP to Claude-native markdown output

> **Executor instructions**: Follow this plan step by step. Run every
> verification command and confirm the expected result before moving to the
> next step. If anything in the "STOP conditions" section occurs, stop and
> report — do not improvise. When done, update the status row in `plans/README.md`.
>
> **Drift check (run first)**: Open `skills/pitch-deck/SKILL.md` and confirm
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

The pitch-deck skill's entire output pipeline (Phases 3, 4, and 5) calls 12 Canva MCP tools to generate, edit, and export a presentation. Canva is a paid external tool; the MCP integration is optional and unavailable to most users. When Canva is not connected, every phase after the outline fails silently. The fix keeps Phases 1 and 2 intact (extraction and outline — pure Claude reasoning), replaces Phases 3–5 with slide-by-slide markdown output, and writes the result to a file. The Slide-by-Slide Content Guide and both examples are preserved; only the tool-calling machinery is replaced.

## Current state

**File:** `skills/pitch-deck/SKILL.md`

Frontmatter (lines 1-5, condensed):
```
---
name: Pitch Deck Builder (Canva)
description: "Creates professional investor or client pitch decks in Canva from a conversational brief..."
allowed-tools: Read Write Glob mcp__claude_ai_Canva__generate-design-structured mcp__claude_ai_Canva__request-outline-review mcp__claude_ai_Canva__get-design mcp__claude_ai_Canva__get-design-content mcp__claude_ai_Canva__start-editing-transaction mcp__claude_ai_Canva__perform-editing-operations mcp__claude_ai_Canva__commit-editing-transaction mcp__claude_ai_Canva__cancel-editing-transaction mcp__claude_ai_Canva__export-design mcp__claude_ai_Canva__get-export-formats mcp__claude_ai_Canva__list-brand-kits mcp__claude_ai_Canva__get-design-thumbnail
---
```

Phase 2 GATE (end of Phase 2):
```
**GATE: Do not proceed to Phase 3 until the outline is approved through the review widget.**
```
(The "review widget" is a Canva MCP call — this gate text must also be updated.)

Phase 3 heading and first line:
```
## Phase 3: Generate the Presentation

Create the actual presentation in Canva using the approved outline.
```

Phase 4 heading:
```
## Phase 4: Refine the Presentation
```

Phase 5 heading:
```
## Phase 5: Export the Deck
```

Recovery section — contains Canva-specific fallbacks starting with:
```
**Design generation fails:** Retry once with the same parameters...
**Editing transaction fails to commit:** Call `cancel-editing-transaction`...
**Export fails:** Call `get-export-formats`...
**No brand kit found:** Proceed with Canva's default professional styling...
```

## Scope

**In scope** (sections to replace):
- `skills/pitch-deck/SKILL.md` frontmatter (name, description, allowed-tools)
- Phase 2 GATE line (remove reference to "review widget")
- Phase 3 entire section
- Phase 4 entire section
- Phase 5 entire section
- Recovery section — replace Canva-specific items; keep "Brief is too vague" and "Outline review widget does not load" (rephrased)

**Out of scope** (do NOT touch):
- Phase 1 (extract pitch elements) — unchanged
- Phase 2 (build slide outline and table) — unchanged, except the GATE line
- Slide-by-Slide Content Guide — unchanged
- Both examples (Example 1 and Example 2) — keep Phase 1/2 execution shown; update Phase 3-5 references within them
- Anti-Patterns section — unchanged

## Steps

### Step 1: Update frontmatter

Replace the entire frontmatter block.

**Old:**
```
---
name: Pitch Deck Builder (Canva)
description: "Creates professional investor or client pitch decks in Canva from a conversational brief about the business, product, or service for fundraising, client proposals, partnership pitches, or keynote presentations."
allowed-tools: Read Write Glob mcp__claude_ai_Canva__generate-design-structured mcp__claude_ai_Canva__request-outline-review mcp__claude_ai_Canva__get-design mcp__claude_ai_Canva__get-design-content mcp__claude_ai_Canva__start-editing-transaction mcp__claude_ai_Canva__perform-editing-operations mcp__claude_ai_Canva__commit-editing-transaction mcp__claude_ai_Canva__cancel-editing-transaction mcp__claude_ai_Canva__export-design mcp__claude_ai_Canva__get-export-formats mcp__claude_ai_Canva__list-brand-kits mcp__claude_ai_Canva__get-design-thumbnail
---
```

**New:**
```
---
name: Pitch Deck Builder
description: "Builds complete investor or client pitch decks as structured markdown — slide-by-slide content ready to paste into PowerPoint, Google Slides, or Keynote — for fundraising, client proposals, partnership pitches, or keynote presentations."
allowed-tools: Read Write Glob
---
```

**Verify**: `head -5 "skills/pitch-deck/SKILL.md"` → name is `Pitch Deck Builder` (no "Canva"), allowed-tools is `Read Write Glob`.

### Step 2: Fix the Phase 2 GATE line

Find the line:
```
**GATE: Do not proceed to Phase 3 until the outline is approved through the review widget.**
```

Replace with:
```
**GATE: Do not proceed to Phase 3 until the user confirms the outline is correct.**
```

**Verify**: `grep -n "review widget" "skills/pitch-deck/SKILL.md"` → no matches.

### Step 3: Replace Phase 3

Find and replace the entire Phase 3 section (from `## Phase 3:` heading through the Phase 3 GATE line).

**Old Phase 3** (begins with `## Phase 3: Generate the Presentation` and ends before `## Phase 4:`):

**New Phase 3:**
```
## Phase 3: Write the Slide Content

Write the full deck as structured slide content using the approved outline. Apply the rules from the Slide-by-Slide Content Guide for each slide.

Format each slide as:

```
---
**Slide [N]: [Title]**

[Body content — bullet points, one idea per line, max 30 words total]

_Speaker note: [one sentence on what to say or emphasize verbally]_
```

Write all slides in sequence without pausing. After the final slide, ask:

"Want me to save this as a file? I'll write it to `pitch-deck-[company-name].md` unless you specify a path."

If saving: use the Write tool to write the complete deck to the specified path.

**GATE: Present all slides before asking for refinements.**
```

**Verify**: `grep -n "generate-design\|brand kit\|mcp__claude_ai_Canva" "skills/pitch-deck/SKILL.md"` → no matches.

### Step 4: Replace Phase 4

Find and replace the entire Phase 4 section (from `## Phase 4:` through the paragraph ending "the problem may require manual editing in Canva's UI.").

**New Phase 4:**
```
## Phase 4: Refine the Deck

After the user reviews the slides, apply feedback directly to the markdown.

1. Accept specific change requests ("slide 7 needs the actual MRR number", "the ask slide should list use of funds")
2. Rewrite only the affected slides
3. Show the revised slides inline — do not reprint the entire deck for one change
4. If the user requests a full rewrite of a slide, replace it completely and mark it with `[revised]` in the title line for easy scanning

If 3 rounds of revision do not resolve the issue, ask: "What outcome are you trying to achieve on this slide?" — diagnose intent before iterating further.
```

**Verify**: `grep -n "editing-transaction\|commit-editing\|cancel-editing" "skills/pitch-deck/SKILL.md"` → no matches.

### Step 5: Replace Phase 5

Find and replace the entire Phase 5 section (from `## Phase 5:` through the end of that section, before `## Slide-by-Slide Content Guide`).

**New Phase 5:**
```
## Phase 5: Deliver the Final Deck

1. Write the final approved deck to a file using the Write tool: `pitch-deck-[company-name]-final.md`
2. Confirm the file path to the user
3. Provide paste instructions:

```
**To use this deck:**
- **Google Slides / PowerPoint / Keynote:** Create one slide per section. Copy the body content for each slide. Delete speaker notes before presenting or keep them in the notes panel.
- **Paste into a design tool:** The markdown structure maps directly to slide titles and bullets. One `---` separator = one new slide.
- **Send as a document:** The file reads cleanly as a standalone briefing document before the deck is designed.
```
```

**Verify**: `grep -n "export-design\|get-export-formats\|PPTX\|PDF.*Canva" "skills/pitch-deck/SKILL.md"` → no matches (note: PPTX may remain in paste instructions — that is fine).

### Step 6: Replace Canva-specific Recovery items

Find the Recovery section. Replace the four Canva-specific items while keeping "Brief is too vague".

**Items to remove** (find each by its bold heading and replace):

1. **Old:** `**Design generation fails:** Retry once with the same parameters...` (through "offer to write slide content as a markdown file for manual import")
   **New:** `**Slide content is too generic:** Ask for one concrete detail per vague slide — a real stat, a named competitor, an actual price. Generic inputs produce generic slides.`

2. **Old:** `**Outline review widget does not load:** Present the outline as a numbered list in chat...`
   **New:** `**User wants to skip the outline review:** Do not skip it. The outline gate exists to prevent writing 12 slides against a misunderstood brief. Show the outline and ask for a single yes/no.`

3. **Old:** `**Editing transaction fails to commit:** Call \`cancel-editing-transaction\`...`
   **Remove entirely** (no replacement needed — this was Canva-specific error handling).

4. **Old:** `**Export fails:** Call \`get-export-formats\`...`
   **Remove entirely.**

5. **Old:** `**No brand kit found:** Proceed with Canva's default professional styling...`
   **Remove entirely.**

Keep `**Brief is too vague:**` unchanged.

**Verify**: `grep -n "cancel-editing\|get-export-formats\|brand kit\|Canva's" "skills/pitch-deck/SKILL.md"` → no matches.

### Step 7: Update example Phase 3-5 references

In **Example 1** and **Example 2**, find the closing summary lines that reference Canva output (e.g., "Deck generated with brand kit. Exported as PPTX + PDF. 12 slides, ready for investor meetings.").

Replace each with a plain summary line:

**Example 1 — Old:**
```
**Phase 3-5:** Deck generated with brand kit. Exported as PPTX + PDF. 12 slides, ready for investor meetings.
```
**New:**
```
**Phase 3-5:** 12 slides written. Saved to `pitch-deck-workflowos.md`. Ready to paste into Google Slides or PowerPoint.
```

**Example 2 — Old:**
```
**Phase 3-5:** Deck generated with professional default styling. Exported as PPTX + PDF. 12 slides, ready to send to the prospect.
```
**New:**
```
**Phase 3-5:** 12 slides written. Saved to `pitch-deck-brand-strategy.md`. Ready to paste into Google Slides or PowerPoint.
```

**Verify**: `grep -n "brand kit\|Exported as PPTX\|Canva account" "skills/pitch-deck/SKILL.md"` → no matches.

## Done criteria

- [ ] `grep -n "mcp__claude_ai_Canva\|Canva\|brand kit\|editing-transaction\|export-design" "skills/pitch-deck/SKILL.md"` → no matches
- [ ] `head -5 "skills/pitch-deck/SKILL.md"` → name `Pitch Deck Builder`, allowed-tools `Read Write Glob`
- [ ] Phase 3 heading reads `## Phase 3: Write the Slide Content`
- [ ] Phase 4 heading reads `## Phase 4: Refine the Deck`
- [ ] Phase 5 heading reads `## Phase 5: Deliver the Final Deck`
- [ ] Phase 1, Phase 2, Slide-by-Slide Content Guide, and Anti-Patterns are unchanged
- [ ] `plans/README.md` status row updated to DONE

## STOP conditions

- The frontmatter content at the cited location doesn't match the excerpt above (file has drifted)
- Any step requires touching Phase 1, Phase 2, or the Slide-by-Slide Content Guide
- You find a Canva reference in a section not listed in this plan's scope

## Maintenance notes

- The output format (one markdown file per deck) relies on the Write tool already in allowed-tools — no further changes needed
- If a future version adds real-time collaboration features, the Phase 4 refinement loop is the right place to extend
- The Anti-Patterns section still says "DO NOT use generic stock imagery descriptions" — this remains valid advice for Claude to follow when writing visual descriptions for each slide
