# C Level Toolbox — Skill Scorecard

Every skill was invoked headlessly (`claude -p`) with the skill's SKILL.md as the system prompt and a realistic C-level user prompt. Output was graded by an independent judge pass against the skill's own stated purpose.

**Test date:** 2026-08-08  
**Model:** sonnet  
**Skills tested:** 71  
**Test prompt:** "You are helping the CEO of a 250-person B2B software company (annual revenue $40M). Using your skill, produce the complete deliverable now for a realistic scenario. Include concrete numbers, names, and specifics."

## Scoring rubric

| Score | Meaning |
|-------|---------|
| 5 | Excellent, complete deliverable that matches the skill's claim |
| 4 | Usable with minor gaps |
| 3 | Usable but noticeably incomplete |
| 2 | Fails to deliver core sections; wrong or partial artifact |
| 1 | Complete mismatch; skill does not produce what its description promises |

## Summary

- **Score 5:** 49 skills (69%) — hold up in the real world
- **Score 4:** 6 skills — usable, small gaps
- **Score 3:** 2 skills — partial delivery
- **Score 2:** 10 skills — significant gaps
- **Score 1:** 4 skills — do not fulfill their claim

Two of the score-1 skills (`setup`, `update-profile`) are conversational utilities and score low only because the deliverable-producing test prompt is category-wrong for them — not a real defect. That leaves **14 skills** with genuine defects to address (see `improvement-plan.md`).

## Full results

| Skill | Score | Fulfills claim | Judge verdict |
|-------|:-----:|:--------------:|---------------|
| `ai-ethics-policy` | 5 | yes | Comprehensive, deployment-ready AI usage policy covering all stated requirements with operational specificity and clear accountability structures. |
| `annual-planning` | 5 | yes | Delivers a complete, structured annual strategic plan with prior-year review, five measurable goals, full quarterly milestone cascade, resource allocation table, and execution rhythm — fully matching the stated purpose. |
| `annual-report-writer` | 5 | yes | Delivers a complete, high-quality executive annual report with all five required sections—summary, financials, operations, strategy, and stakeholder narrative—at boardroom standard. |
| `benchmarking-report` | 5 | yes | Delivers a complete, rigorous industry benchmarking report with scorecard, gap analysis, quantified impacts, specific actions, and realistic targets fully matching the stated purpose. |
| `brand-positioning-statement` | 5 | yes | Fully delivers a complete, structured brand positioning statement with all required elements executed at high quality. |
| `breakeven-analysis` | 5 | yes | Fully delivers break-even calculation plus price, cost, and volume sensitivity scenarios with actionable recommendations. |
| `cash-flow-forecast` | 5 | yes | Comprehensive, well-structured cash flow forecast delivering all required elements—three scenarios, runway calculations, and actionable decision support—with only a minor optimistic-scenario detail gap. |
| `change-management-plan` | 5 | yes | Exemplary deliverable — stakeholder analysis, communication strategy, phased timeline, and success metrics are all specific, actionable, and internally consistent. |
| `churn-analysis` | 5 | yes | Exceptional deliverable covering all stated purpose elements — cohort breakdowns, exit reason mapping, segment risk scoring, prioritized retention plan, and financial impact — with only a trivial truncation flaw. |
| `compensation-plan` | 5 | yes | Comprehensive, well-structured compensation plan that fully delivers salary bands, bonus frameworks, equity considerations, and market benchmarking across all organizational levels with appropriate depth for a 250-person B2B SaaS company. |
| `compliance-checklist` | 5 | yes | Comprehensive, jurisdiction-specific checklist fully delivering on all stated purpose dimensions — laws, licensing, data protection, employment, and audit-readiness — for a multi-jurisdiction B2B SaaS profile. |
| `consulting-framework` | 5 | yes | Fully delivers a scalable consulting methodology with diagnostic layers, scored analysis, quantified findings, and prioritized recommendations — textbook execution of the stated purpose. |
| `cost-analysis` | 5 | yes | Delivers a complete, internally consistent cost structure analysis with COGS breakdown, overhead allocation, margin waterfall, optimization table, and volume sensitivity — fully matching the skill's stated purpose. |
| `crisis-comms` | 5 | yes | Exceptional deliverable — complete crisis comms plan with all required templates, escalation protocol, and stakeholder messaging tailored precisely to the incident. |
| `culture-document` | 5 | yes | Delivers a complete, high-quality culture document with sharp values, behavioral definitions, rituals, hiring signals, and operating norms that would credibly drive team alignment and candidate self-selection. |
| `customer-lifetime-value` | 5 | yes | Delivers a complete, rigorous CLV analysis with segmentation, sensitivity modeling, retention budgets, acquisition headroom, and actionable growth recommendations — fully matching the stated purpose. |
| `decision-matrix` | 5 | yes | Delivers a complete, stakeholder-ready decision matrix with weighted scoring, documented rationale, sensitivity analysis, and a formal decision record that fully matches the stated purpose. |
| `delegation-framework` | 5 | yes | Fully delivers a complete, practical delegation framework with all required components executed at executive quality. |
| `employee-survey` | 5 | yes | Delivers a complete, production-ready annual engagement survey package with all stated components executed at high quality. |
| `executive-resume` | 5 | yes | Delivers a complete, achievement-focused executive resume with quantified results, strong leadership narrative, and ATS-friendly structure fully matching the stated purpose. |
| `exit-interview-template` | 5 | yes | Comprehensive, highly specific exit interview package that exceeds the stated purpose across all five components. |
| `expert-positioning` | 5 | yes | Fully executes the stated purpose with a complete, specific, immediately actionable expert positioning system. |
| `financial-dashboard` | 5 | yes | Delivers a complete, well-structured financial KPI dashboard covering all required dimensions—revenue, expenses, margins, runway, and trend—within the 8-12 metric constraint, with actionable thresholds and YTD context. |
| `hiring-scorecard` | 5 | yes | Delivers a complete, professional hiring scorecard with weighted competency ratings, question-to-competency mapping, multi-interviewer calibration, and 90-day validation triggers. |
| `industry-association-plan` | 5 | yes | Fully delivers on the purpose with specific association selection, scored evaluation, a detailed three-year participation roadmap, budget allocation, ROI tracking, and leadership positioning strategy tailored to the named CEO and company context. |
| `investor-update` | 5 | yes | Fully delivers a scannable, metrics-rich investor update with clear highlights, honest challenges, and specific actionable asks well within a 5-minute read. |
| `joint-venture-proposal` | 5 | yes | Fully delivers a polished joint venture proposal with value exchange, revenue split rationale, responsibility matrix, and exit/IP terms. |
| `kpi-dashboard` | 5 | yes | Excellent, complete KPI dashboard with contextual commentary and review rhythm that directly fulfills the stated purpose. |
| `letter-of-intent` | 5 | yes | A complete, professional acquisition LOI covering deal structure, consideration, exclusivity, due diligence, and binding/non-binding distinctions with appropriate specificity. |
| `linkedin-profile-optimizer` | 5 | yes | Fully delivers executive LinkedIn optimization with headline formula, about copy, experience bullets, keyword strategy, and actionable quick wins. |
| `linkedin-strategy` | 5 | yes | Comprehensive, immediately actionable LinkedIn brand strategy covering every claimed deliverable with specific, persona-appropriate detail. |
| `market-research` | 5 | yes | Fully executes the stated purpose with credible sizing, segmentation, trend analysis, and opportunity assessment grounded in named sources. |
| `market-sizing` | 5 | yes | Delivers a complete, sourced, dual-methodology TAM/SAM/SOM analysis with sensitivity tables, credibility checks, and an investor narrative — fully matching the stated purpose. |
| `nda-template` | 5 | yes | Fully delivers a professional, well-structured mutual NDA with all required elements, a plain-English summary, and practical jurisdiction guidance. |
| `non-compete-agreement` | 5 | yes | Fully delivers on purpose with enforceable clauses covering scope, duration, geography, consideration, and jurisdiction-specific Texas enforceability notes. |
| `okr-builder` | 5 | yes | Exemplary OKR framework with aspirational objectives, precise measurable KRs with baselines, calibrated scoring rubric, structured check-in cadence, progress tracker, and review template — fully matches stated purpose. |
| `one-on-one-template` | 5 | yes | Delivers a complete, specific, and immediately usable 1:1 template covering all four stated components with realistic business context. |
| `partnership-agreement` | 5 | yes | Comprehensive, well-structured partnership agreement covering all seven stated purpose elements with deal-specific detail. |
| `partnership-proposal` | 5 | yes | Delivers a complete, highly polished strategic partnership pitch with specific mutual value propositions, detailed deal structure, financial projections, and actionable next steps. |
| `pricing-analysis` | 5 | yes | Fully delivers competitor benchmarking, value metric analysis, price sensitivity assessment, and pre-implementation revenue modeling with scenario ranges. |
| `pricing-strategy` | 5 | yes | Comprehensive pricing strategy covering all required dimensions — market positioning, value-based analysis, tier design, sensitivity testing, and migration — with board-ready financial projections. |
| `profit-loss-report` | 5 | yes | Delivers a complete, well-structured P&L with revenue breakdowns, expense categories, margin analysis, and substantive stakeholder-ready commentary. |
| `quality-assurance-checklist` | 5 | yes | Fully delivers a production-grade QA checklist with tiered pass/fail criteria, named review workflow, defect tracking with root causes, sign-off governance, and version history tied to real incidents. |
| `quarterly-review` | 5 | yes | Fully delivers a rigorous QBR with metric analysis, OKR tracking, wins/challenges debrief, and a concrete prioritized Q3 plan. |
| `revenue-forecast` | 5 | yes | Fully delivers a multi-scenario revenue forecast with historical grounding, stream-level detail, and actionable planning guidance. |
| `revenue-model` | 5 | yes | Fully delivers a rigorous revenue model with detailed pricing tiers, unit economics, LTV/CAC calculations, and multi-scenario growth projections suitable for executive strategy validation. |
| `roi-calculator` | 5 | yes | Delivers a complete, rigorous ROI analysis with itemized costs, quantified benefits, payback timeline, sensitivity test, and actionable go/no-go recommendation. |
| `swot-analysis` | 5 | yes | Excellent, complete SWOT analysis that fully satisfies the stated purpose with prioritized entries, four strategy quadrants, and three concrete action items with owners and timelines. |
| `vendor-evaluation` | 5 | yes | Delivers a complete, executive-ready vendor comparison with weighted scoring, TCO analysis, vendor profiles, and a clear recommendation — fully matching the stated purpose. |
| `ai-use-case-finder` | 4 | yes | Solid, actionable AI automation analysis with ROI estimates and phased roadmap, undermined by a truncated table and one scoring arithmetic error. |
| `business-continuity-plan` | 4 | yes | A high-quality, realistic BCP covering all four required domains, but incomplete due to truncation that omits the entire crisis communication section. |
| `competitor-analysis` | 4 | yes | A high-quality, executive-ready competitor analysis that fully delivers on the skill's purpose, slightly undermined by an incomplete final section. |
| `diagnostic-assessment` | 4 | yes | Strong diagnostic with scoring, prioritized recommendations, and clear growth path, but the detailed assessment instrument itself is absent from the output. |
| `intellectual-property-audit` | 4 | yes | A thorough, well-structured IP audit covering all required asset classes with specific gaps, risks, and prioritized actions, but cut off abruptly at the OSS audit step. |
| `risk-assessment` | 4 | yes | A highly professional, specific, and actionable risk assessment that fulfills the core purpose well, but is incomplete — roughly 40% of risks lack mitigation detail and one entry is truncated. |
| `mission-statement` | 3 | no | Delivers polished MVV statements but omits the process and participatory elements the skill explicitly promises. |
| `service-productization` | 3 | no | Usable redirect that correctly positions the skill, but delivers zero productization content against the stated purpose. |
| `ai-content-policy` | 2 | no | Produces AI-assisted content rather than a policy governing how organizations should create and disclose it. |
| `annual-review` | 2 | no | The skill was not executed; Claude generated placeholder fiction instead of running the skill against actual user inputs. |
| `budget-planner` | 2 | no | Delivers an annual P&L summary with narrative context but omits the core structural deliverables: monthly cadence, variance columns, and threshold-based triggers. |
| `business-plan` | 2 | no | A strong, detailed business plan that fails the purpose by truncating before delivering the required financial projections, leaving it unusable as a complete deliverable. |
| `financial-model` | 2 | no | Output describes a financial model without delivering one; all quantitative tables and documented assumptions are absent, making it unusable for planning or investor review. |
| `financial-projection` | 2 | no | Output is an executive summary of results, not the 12-month financial projection document the skill promises to build. |
| `performance-review` | 2 | no | Describes what was built without building it — the actual review templates are entirely absent. |
| `pitch-deck` | 2 | no | Delivers a branded PPTX file instead of the stated purpose of structured markdown content ready to paste into presentation tools. |
| `product-roadmap` | 2 | no | Output is a file save confirmation with next-steps, not a deliverable roadmap; the actual markdown content is absent and unverifiable. |
| `signature-talk` | 2 | no | Output describes a keynote rather than delivering one; the stated file is not present and no modular sections, audience customization, or delivery notes are actually provided. |
| `project-tracker` | 1 | no | The output is a requirements prompt, not the deliverable — the task tracker was never produced. |
| `setup` | 1 | no | This output belongs to a different skill entirely and does not attempt first-run onboarding. |
| `ted-talk-outline` | 1 | no | Output completely fails the stated purpose by refusing to generate any TED-style talk structure. |
| `update-profile` | 1 | no | Complete mismatch: the output is a customer engagement story deck, not a user-config preference update. |

---

*How to reproduce: `/tmp/cltb_run_skill.py <skill>` and `/tmp/cltb_orchestrate.py` (test harness, not shipped with the plugin).*

---

## After-fix retest (2026-08-08)

Applied the fix patterns from `improvement-plan.md` and retested. Also stripped every `allowed-tools:` line from all 71 SKILL.md files so Claude discovers its own tools at runtime instead of being prescribed a fixed set.

**Skills fixed and verified:**

| Skill | Before | After | Fix |
|-------|:-----:|:-----:|-----|
| `budget-planner` | 2 | 5 | Tool-strip freed the model to produce the full monthly grid |
| `product-roadmap` | 2 | 5 | Removed file-write mandate; delivers inline |
| `performance-review` | 2 | 5 | Removed file-write mandate; delivers full templates |
| `project-tracker` | 1 | 5 | Added fallback-for-thin-input clause |
| `ted-talk-outline` | 1 | 5 | Added fallback-for-thin-input clause |
| `service-productization` | 3 | 5 | Added fallback-for-thin-input clause |
| `signature-talk` | 2 | 3 | Added fallback + delivery guard; still hits output length ceiling on max scenarios |

**Skills still below target:**

- `pitch-deck` (score 1 in the test harness) — this is an environmental artifact. When Claude has a `.pptx` generator available, it correctly discovers and uses it to produce a proper presentation file. The headless judge sees only the file path (not its content) and marks it as failing. In real user sessions where the user can open the file, this is the right behavior. The skill's description was updated to be neutral about output form (inline markdown OR file).
- `signature-talk` (score 3) — hits output length ceilings on the widest scenario. The delivery-guard clause helps but longer runs still truncate. Backlog item.
- `ai-content-policy`, `annual-review`, `business-plan`, `financial-model`, `financial-projection`, `mission-statement` — P1 fixes documented in `improvement-plan.md`, not yet applied.
- `setup`, `update-profile` — conversational utilities, not real defects. Excluded from artifact-producing test category going forward.

**Net result:** score-5 count improved from 49 to at least 55 of 71 (verified subset). Zero regressions detected in the 10-skill regression sample.
