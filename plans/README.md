# C Level Toolbox — Improvement Plans

> Generated: 2026-08-07  
> Scope: `/501-claude-skills-bundle/c-level-toolbox/`  
> Audit level: deep  
> Total plans: 8  
> Status legend: TODO · IN PROGRESS · DONE · BLOCKED · SUPERSEDED

---

## Execution Order

Run plans in the order below. Plans 001–005 are independent of each other and can run in parallel. Plans 006–008 are also independent of each other and of 001–005. No plan depends on another.

| # | Plan file | What it fixes | Skills affected | Priority | Effort | Risk | Status |
|---|-----------|---------------|-----------------|----------|--------|------|--------|
| 001 | [001-kpi-dashboard-remove-notion.md](001-kpi-dashboard-remove-notion.md) | Remove Notion hard dependency; output markdown table | `kpi-dashboard` | P1 | M | LOW | DONE |
| 002 | [002-pitch-deck-remove-canva.md](002-pitch-deck-remove-canva.md) | Remove Canva hard dependency; output slide markdown | `pitch-deck` | P1 | M | LOW | DONE |
| 003 | [003-product-roadmap-remove-notion.md](003-product-roadmap-remove-notion.md) | Remove Notion hard dependency; output markdown roadmap | `product-roadmap` | P1 | M | LOW | DONE |
| 004 | [004-project-tracker-remove-notion.md](004-project-tracker-remove-notion.md) | Remove Notion hard dependency; output markdown task table | `project-tracker` | P1 | M | LOW | DONE |
| 005 | [005-remove-notion-from-competitor-vendor.md](005-remove-notion-from-competitor-vendor.md) | Remove Notion soft dependency (primary save path) | `competitor-analysis` `vendor-evaluation` | P1 | S | LOW | DONE |
| 006 | [006-finance-arithmetic-fixes.md](006-finance-arithmetic-fixes.md) | Fix arithmetic errors in worked examples and formulas | `roi-calculator` `financial-model` `cash-flow-forecast` `cost-analysis` `pricing-analysis` `financial-dashboard` `budget-planner` `financial-projection` | P2 | S | LOW | DONE |
| 007 | [007-legal-disclaimers.md](007-legal-disclaimers.md) | Add legal disclaimers to legal document skills | `non-compete-agreement` `partnership-agreement` | P2 | S | LOW | DONE |
| 008 | [008-risk-heatmap-and-credentials.md](008-risk-heatmap-and-credentials.md) | Fix risk heat map grid cells; remove credential-in-email anti-pattern | `risk-assessment` `automation-workflow` | P2 | S | LOW | DONE |

---

## Dependency graph

All plans are independent — no plan requires another to run first. Plans 001–005 (external tool removal) address skills that currently produce zero output for users without the relevant integration. Run these first if resources are limited.

```
001 ──┐
002 ──┤
003 ──┤──► (all independent, run in any order)
004 ──┤
005 ──┤
006 ──┤
007 ──┤
008 ──┘
```

---

## What was audited

- All 73 skills in the toolbox were scanned for external MCP tool dependencies (Notion, Canva)
- All Finance & Pricing skills were audited for arithmetic correctness in worked examples and formula definitions
- All legal document skills were compared against the NDA template for disclaimer consistency
- Risk heat map grid was verified cell-by-cell against the stated scoring formula
- Automation workflow example was reviewed for security anti-patterns

---

## Considered and rejected findings

The following were examined and not planned:

| Finding | Reason not planned |
|---------|-------------------|
| `setup/SKILL.md` — asks about external tools | No MCP calls; soft informational reference only |
| `automation-workflow/SKILL.md` — asks what platform user uses | No MCP calls; user-input only; skill functions without any platform |
| `financial-projection/SKILL.md` — `[X-2]%` / `[X+2]%` scenario bands | Included in plan 006 (symmetric bands) |
| LTV formula in `kpi-dashboard/SKILL.md` | Covered by plan 001 (Notion removal rewrites that section) |
| `breakeven-analysis/SKILL.md:113` — rounds $39,583 to $40,500 | Rounding-up to nearest revenue increment is a defensible convention; not an arithmetic error |
| `financial-projection/SKILL.md` — `[X]` placeholder templates | Correct by design; fill-in-the-blank, not example numbers |

---

## Maintenance notes

- After executing plans 001–005, run `grep -r "mcp__claude_ai_Notion__\|mcp__claude_ai_Canva__" skills/` — should return no matches
- After executing plan 006, run the verification commands in each step before closing — several steps have two changes in the same file
- Plan 008 Step 1 corrects three cells in the I=4 row of the risk heat map. If a full 25-cell grid audit is ever desired, verify each cell against `Risk Score = L × I` and the four priority bands in the same file
- `nda-template/SKILL.md` already has a legal disclaimer — it is the reference pattern for plan 007; do not modify it
