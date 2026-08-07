---
name: Financial KPI Dashboard
version: 1.7.5
description: "Builds a financial KPI tracking dashboard structure with revenue, expenses, margins, runway, and trend analysis — limited to 8-12 metrics that directly answer whether the business is making money and will continue to."
---

# Financial Dashboard

## Core Principle

A DASHBOARD THAT TRACKS EVERYTHING TRACKS NOTHING — LIMIT TO 8-12 KPIS THAT DIRECTLY ANSWER "ARE WE MAKING MONEY AND WILL WE KEEP MAKING MONEY?"

## Financial Disclaimer

**This dashboard is for internal tracking and planning purposes only. It does not constitute audited financial reporting. Always consult a qualified accountant for official financial statements, tax filings, and compliance. Accuracy depends on the data entered.**

## Workflow

### Phase 1: Define the Business Model

1. Confirm the business type to select relevant KPIs:
   - **Service/consulting:** Focus on revenue per client, utilization rate, project margin
   - **Product/manufacturing:** Focus on gross margin, COGS, inventory turns, CAC
   - **SaaS/subscriptions:** Focus on MRR, churn, LTV, CAC
   - **Hybrid:** Combine relevant metrics from above
2. Determine tracking frequency: monthly (default) or weekly
3. Identify data sources (ERP, CRM, bank account, payment processor, spreadsheet)

### Phase 2: Select KPIs

Choose 8-12 KPIs from the master list below. Default selections are marked.

**Revenue KPIs:**

| KPI | Formula | Default For |
|-----|---------|-------------|
| Total Revenue | Sum of all income | All businesses |
| Monthly Recurring Revenue (MRR) | Recurring subscriptions/retainers | SaaS, memberships |
| Revenue by Source | Revenue broken down by channel/product | All businesses |
| Average Deal Value | Revenue / Number of deals | Service businesses |
| Revenue per Client | Revenue / Active clients | Service businesses |

**Profitability KPIs:**

| KPI | Formula | Default For |
|-----|---------|-------------|
| Gross Profit | Revenue - COGS | All businesses |
| Gross Margin % | (Gross Profit / Revenue) x 100 | All businesses |
| Net Profit | Revenue - All Expenses | All businesses |
| Net Margin % | (Net Profit / Revenue) x 100 | All businesses |
| Operating Expense Ratio | Operating Expenses / Revenue | All businesses |

**Growth and Health KPIs:**

| KPI | Formula | Default For |
|-----|---------|-------------|
| Month-over-Month Growth | (This Month - Last Month) / Last Month x 100 | All businesses |
| Cash Runway | Cash on Hand / Monthly Burn Rate | All businesses |
| Customer Acquisition Cost (CAC) | Marketing Spend / New Customers | Product, SaaS |
| Customer Lifetime Value (LTV) | Avg Revenue per Customer x Avg Retention (months) x Gross Margin % | SaaS, memberships |
| Accounts Receivable Aging | Outstanding invoices by days overdue | Service businesses |

### Phase 3: Build the Dashboard Structure

Create the dashboard layout with these sections:

```
╔══════════════════════════════════════════════════════════╗
║              FINANCIAL DASHBOARD — [MONTH YEAR]         ║
║              [Organization Name]                        ║
╠══════════════════════════════════════════════════════════╣
║                                                         ║
║  SNAPSHOT (Top-line numbers)                            ║
║  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  ║
║  │ Revenue  │ │ Expenses │ │Net Profit│ │Net Margin│  ║
║  │ $XX,XXX  │ │ $XX,XXX  │ │ $X,XXX  │ │  XX.X%   │  ║
║  │ ▲ +12%   │ │ ▲ +5%    │ │ ▲ +22%  │ │ ▲ +3.1pp │  ║
║  └──────────┘ └──────────┘ └──────────┘ └──────────┘  ║
║                                                         ║
║  REVENUE BREAKDOWN                                      ║
║  [Revenue by source — bar chart or table]              ║
║                                                         ║
║  EXPENSE BREAKDOWN                                      ║
║  [Top 5 expense categories — bar chart or table]       ║
║                                                         ║
║  TREND (Last 6 months)                                  ║
║  [Revenue, Expenses, Net Profit line over time]        ║
║                                                         ║
║  HEALTH INDICATORS                                      ║
║  [CAC, LTV, Runway, AR Aging — as applicable]          ║
║                                                         ║
╚══════════════════════════════════════════════════════════╝
```

For each KPI, define:
- Green/Yellow/Red thresholds (what is healthy, warning, critical)
- Data source (where the number comes from)
- Update frequency

### Phase 4: Populate with Data

If the user provides financial data, populate the dashboard with real numbers. Calculate all derived metrics (margins, ratios, growth rates). Flag any KPIs in the red zone with specific commentary.

### Phase 5: Deliver

Output the complete dashboard structure, a data collection template (what to track and where to enter it), and threshold definitions.

## Example: Professional Services Division Dashboard

**Context:** 40-person professional services division, $1.2M/month revenue, mixed retainer and project work.

**Selected KPIs (10):** Total Revenue, Revenue per Client, Gross Margin, Net Profit, Net Margin, MoM Growth, Operating Expense Ratio, Utilization Rate, Accounts Receivable, Cash Runway

```
╔══════════════════════════════════════════════════════════╗
║         FINANCIAL DASHBOARD — JANUARY 2026              ║
║         Meridian Advisory Group                         ║
╠══════════════════════════════════════════════════════════╣
║                                                         ║
║  SNAPSHOT                                               ║
║  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  ║
║  │ Revenue  │ │ Expenses │ │Net Profit│ │Net Margin│  ║
║  │$1,240,000│ │ $892,800 │ │$347,200 │ │  28.0%   │  ║
║  │ ▲ +4.2%  │ │ ▲ +1.8%  │ │ ▲ +8.1% │ │ ▲ +0.9pp │  ║
║  └──────────┘ └──────────┘ └──────────┘ └──────────┘  ║
║                                                         ║
║  REVENUE BREAKDOWN                                      ║
║  Retainer Clients (12)           $780,000    62.9%     ║
║  Project Revenue (8 active)      $380,000    30.6%     ║
║  Advisory/Board Fees              $80,000     6.5%     ║
║                                                         ║
║  Revenue per Client: $72,941                           ║
║                                                         ║
║  EXPENSE BREAKDOWN                                      ║
║  Salaries & Benefits    $624,000    70.0%              ║
║  Operations & Facilities $142,000   15.9%              ║
║  Technology               $62,000    6.9%              ║
║  Marketing                $38,000    4.3%              ║
║  Other                    $26,800    3.0%              ║
║                                                         ║
║  TREND (Last 6 months)                                  ║
║  Aug  $1,050,000  ████████████                         ║
║  Sep  $1,090,000  █████████████                        ║
║  Oct  $1,130,000  █████████████                        ║
║  Nov  $1,160,000  ██████████████                       ║
║  Dec  $1,190,000  ██████████████                       ║
║  Jan  $1,240,000  ███████████████                      ║
║                                                         ║
║  HEALTH INDICATORS                                      ║
║  Operating Expense Ratio: 72.0% [target: <75%]         ║
║  Utilization Rate: 78% [target: >75%]                  ║
║  AR Aging: $186,000 outstanding (avg 34 days)          ║
║  Cash Runway: 4.2 months                               ║
║                                                         ║
╚══════════════════════════════════════════════════════════╝
```

**Threshold Definitions:**

| KPI | Green | Yellow | Red |
|-----|-------|--------|-----|
| Net Margin | >25% | 15-25% | <15% |
| MoM Growth | >3% | 0-3% | Negative |
| Utilization Rate | >75% | 60-75% | <60% |
| AR Aging | <30 days | 30-60 days | >60 days |
| Cash Runway | >3 months | 1-3 months | <1 month |

## Recovery and Fallback

- If there is no historical data, set up the dashboard structure with empty fields and start tracking from the current month
- If multiple payment systems exist, consolidate by listing all sources and running a monthly reconciliation
- If a KPI is in the red zone, provide one specific action to address it — not a list of options
- If the full dashboard is overwhelming, start with the 4-metric snapshot only (Revenue, Expenses, Net Profit, Net Margin) and add KPIs over time

## Constraints

- **Always include the financial disclaimer**
- Limit to 12 KPIs maximum
- Do not include vanity metrics (social followers, website visits) in a financial dashboard
- Do not calculate or estimate tax liability
- Cash runway calculation assumes zero revenue as worst-case — always note this
- Thresholds are guidelines, not rules — they vary by industry and maturity stage
- All financial data must come from the user — do not estimate or fabricate numbers
