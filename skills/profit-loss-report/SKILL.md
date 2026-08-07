---
name: Profit and Loss Report
version: 1.8.5
description: "Generates monthly or quarterly profit and loss statements from transaction data with revenue breakdowns, expense categories, and margin analysis — for internal performance review or stakeholder reporting."
---

# Profit & Loss Report

## Core Principle

A P&L REPORT MUST TELL THE TRUTH — CATEGORIZE EVERY DOLLAR, HIDE NOTHING, AND SHOW THE REAL MARGIN.

## Financial Disclaimer

**This report is for informational and planning purposes only. It does not constitute audited financial statements or accounting advice. Always consult a qualified accountant for official financial reporting, tax filings, and compliance matters. Accuracy depends entirely on the data provided.**

## Workflow

### Phase 1: Collect Financial Data

1. Determine the reporting period (month or quarter)
2. Gather revenue data — ask the user for one of:
   - CSV or spreadsheet file with transactions
   - Manual list of income sources and amounts
   - ERP, billing system, or payment processor export (Stripe, bank statement)
3. Gather expense data — same formats as above
4. Confirm the business type (service, product, SaaS, hybrid) to set appropriate categories

### Phase 2: Categorize Transactions

Sort all revenue into standard categories:

| Revenue Category | Examples |
|-----------------|----------|
| Product Sales | Physical goods, digital products |
| Service Revenue | Consulting, managed services, project work |
| Recurring Revenue | Subscriptions, retainers, maintenance contracts |
| License/Royalty | IP licensing, software licenses, franchise fees |
| Other Income | Interest, grants, miscellaneous |

Sort all expenses into standard categories:

| Expense Category | Examples |
|-----------------|----------|
| Cost of Goods Sold (COGS) | Materials, fulfillment, platform fees, delivery costs |
| Personnel | Salaries, benefits, bonuses, payroll taxes |
| Marketing & Advertising | Ads, events, sponsorships, content |
| Software & Technology | SaaS subscriptions, hosting, licenses |
| Contractors & Outsourced Work | Agencies, freelancers, specialist services |
| Facilities & Operations | Rent, utilities, office supplies |
| Professional Services | Legal, accounting, audit fees |
| Travel & Entertainment | Business travel, client entertainment |
| Insurance | Business liability, professional indemnity |
| Miscellaneous | Anything that does not fit above |

**GATE: If any transaction is ambiguous, ask the user to clarify before proceeding. Do not guess categories for amounts over $2,000.**

### Phase 3: Generate the P&L Report

Build the report using this format:

```
PROFIT & LOSS STATEMENT
[Organization Name] — [Division/Department if applicable]
Period: [Start Date] — [End Date]

═══════════════════════════════════════════════════
REVENUE
───────────────────────────────────────────────────
Product Sales                          $XX,XXX.XX
Service Revenue                        $XX,XXX.XX
Recurring Revenue                      $XX,XXX.XX
License/Royalty                        $XX,XXX.XX
Other Income                           $XX,XXX.XX
───────────────────────────────────────────────────
TOTAL REVENUE                          $XX,XXX.XX

═══════════════════════════════════════════════════
COST OF GOODS SOLD (COGS)
───────────────────────────────────────────────────
[Itemized COGS]                        $XX,XXX.XX
───────────────────────────────────────────────────
TOTAL COGS                             $XX,XXX.XX

═══════════════════════════════════════════════════
GROSS PROFIT                           $XX,XXX.XX
GROSS MARGIN                                XX.X%

═══════════════════════════════════════════════════
OPERATING EXPENSES
───────────────────────────────────────────────────
Personnel                              $XX,XXX.XX
Marketing & Advertising                $X,XXX.XX
Software & Technology                  $X,XXX.XX
Contractors & Outsourced Work          $X,XXX.XX
Facilities & Operations                $X,XXX.XX
Professional Services                  $X,XXX.XX
Travel & Entertainment                 $X,XXX.XX
Insurance                              $X,XXX.XX
Miscellaneous                          $X,XXX.XX
───────────────────────────────────────────────────
TOTAL OPERATING EXPENSES               $XX,XXX.XX

═══════════════════════════════════════════════════
NET PROFIT (LOSS)                      $XX,XXX.XX
NET MARGIN                                  XX.X%
═══════════════════════════════════════════════════
```

### Phase 4: Add Analysis

Below the report, include:
- **Top 3 expense categories** by dollar amount
- **Gross margin assessment:** Above 50% is healthy for services, above 30% for physical products, above 65% for SaaS
- **Net margin assessment:** Above 20% is strong, 10-20% is acceptable, below 10% warrants review
- **Period-over-period trend** if prior period data is available
- **One actionable observation** based on the numbers

### Phase 5: Deliver

Output the formatted P&L report, the analysis summary, and save to file if the user requests it.

## Example: Professional Services Division — Monthly P&L

**Input data:** January revenue: 4 retainer clients at $35,000 each, 2 project completions at $48,000 and $22,000. Expenses: personnel $165,000 (8 staff), office rent $12,000, software tools $4,200, outsourced research firm $18,000, marketing event $8,500, travel $3,100, legal retainer $2,500, insurance $1,800.

```
PROFIT & LOSS STATEMENT
Meridian Advisory Group — Consulting Division
Period: January 1 — January 31, 2026

═══════════════════════════════════════════════════
REVENUE
───────────────────────────────────────────────────
Recurring Revenue (4 retainers)       $140,000.00
Service Revenue (2 projects)           $70,000.00
───────────────────────────────────────────────────
TOTAL REVENUE                         $210,000.00

═══════════════════════════════════════════════════
COST OF GOODS SOLD (COGS)
───────────────────────────────────────────────────
Outsourced Research                   $18,000.00
───────────────────────────────────────────────────
TOTAL COGS                            $18,000.00

═══════════════════════════════════════════════════
GROSS PROFIT                         $192,000.00
GROSS MARGIN                              91.4%

═══════════════════════════════════════════════════
OPERATING EXPENSES
───────────────────────────────────────────────────
Personnel (8 staff)                  $165,000.00
Facilities & Operations               $12,000.00
Marketing & Advertising                $8,500.00
Software & Technology                  $4,200.00
Travel & Entertainment                 $3,100.00
Professional Services                  $2,500.00
Insurance                              $1,800.00
───────────────────────────────────────────────────
TOTAL OPERATING EXPENSES             $197,100.00

═══════════════════════════════════════════════════
NET PROFIT (LOSS)                    -$5,100.00
NET MARGIN                               -2.4%
═══════════════════════════════════════════════════
```

**Analysis:**
- **Top 3 expenses:** Personnel ($165K, 83.7%), Facilities ($12K, 6.1%), Marketing ($8.5K, 4.3%)
- **Gross margin: 91.4%** — Strong for a services business. Low COGS as a percentage of revenue.
- **Net margin: -2.4%** — Operating at a loss this month. Personnel cost ($165K) is the driver — 78.6% of revenue.
- **Observation:** The division needs revenue of at least $215,000/month to break even at current headcount. Adding one retainer client at $35K/month would move the division to +$30K net profit. Review whether the marketing event spend ($8.5K) is tied to pipeline activity that justifies it.

## Recovery and Fallback

- If the user cannot provide exact numbers, help reconstruct from bank statements or ERP exports
- If categories are unclear, ask the user for the three largest expenses and their purpose
- If personal and business transactions are mixed, flag this and only include clearly business-related items
- If prior period data is unavailable for comparison, note this in the report and recommend starting consistent monthly tracking

## Constraints

- **Always include the financial disclaimer**
- Do not estimate tax liability — recommend consulting an accountant for tax calculations
- Do not include owner draws in operating expenses unless explicitly requested
- If transactions mix personal and business, ask the user to separate them
- Round all amounts to two decimal places
- Use accrual basis by default (revenue when earned, expenses when incurred) — switch to cash basis if specified
- Do not provide investment advice based on P&L results
