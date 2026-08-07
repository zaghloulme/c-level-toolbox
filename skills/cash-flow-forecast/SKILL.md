---
name: Cash Flow Forecast
version: 1.3.7
description: "Projects monthly cash flow for 3-12 months from revenue and expense inputs with three scenarios, runway calculations, and decision support for hiring, investment, and spending decisions."
---

# Cash Flow Forecast

## Core Principle

**CASH FLOW IS NOT PROFIT. A profitable organization can run out of cash. This forecast tracks when money actually enters and leaves the account.**

## Financial Disclaimer

**This tool provides estimates for planning purposes. It is not financial advice. Consult a qualified accountant or financial advisor for formal financial planning.**

## Workflow

### Step 1: Gather Financial Inputs

Ask for:

1. Current cash on hand (bank balance)
2. Monthly revenue sources and amounts (be specific: retainer clients, product sales, subscriptions, contract revenue)
3. Monthly fixed expenses (rent, software, subscriptions, salaries)
4. Monthly variable expenses (ads, materials, contractors)
5. Any upcoming one-time expenses or revenue (equipment purchase, tax payment, contract signing)
6. Forecast period (default: 6 months)

**Minimum needed: questions 1, 2, and 3.**

### Step 2: Build the Forecast Table

Create a month-by-month table:

| | Month 1 | Month 2 | Month 3 | Month 4 | Month 5 | Month 6 |
|---|---------|---------|---------|---------|---------|---------|
| **Starting Cash** | | | | | | |
| Revenue Line 1 | | | | | | |
| Revenue Line 2 | | | | | | |
| **Total Revenue** | | | | | | |
| Fixed Expense 1 | | | | | | |
| Fixed Expense 2 | | | | | | |
| Variable Expenses | | | | | | |
| One-Time Expenses | | | | | | |
| **Total Expenses** | | | | | | |
| **Net Cash Flow** | | | | | | |
| **Ending Cash** | | | | | | |

### Step 3: Calculate Key Metrics

- **Monthly Burn Rate:** Average total expenses per month
- **Revenue Coverage Ratio:** Total revenue / total expenses (above 1.0 = cash positive)
- **Cash Runway:** Starting cash / (monthly expenses - monthly revenue) = months until $0. If revenue ≥ expenses (cash-flow positive), output "N/A — cash-flow positive; runway is not the binding constraint" instead of calculating.
- **Break-Even Month:** First month where cumulative cash flow turns positive
- **Lowest Cash Point:** The month with the lowest ending cash balance

### Step 4: Scenario Modeling

Build three scenarios:

| Scenario | Revenue Assumption | Expense Assumption |
|----------|-------------------|-------------------|
| Conservative | 80% of projected revenue | 110% of projected expenses |
| Base Case | 100% of projected | 100% of projected |
| Optimistic | 120% of projected revenue | 95% of projected expenses |

Use the **conservative scenario** as the planning baseline.

### Step 5: Recommendations

Based on the forecast, provide:
- Cash danger zones (months where ending cash drops below 1 month of expenses)
- Specific recommendations (cut expenses, accelerate revenue, build reserve)
- Decision support for the original question

## Examples

### Example 1: Operations Team Evaluating a New Hire

**Inputs:**
- Cash on hand: $420,000
- Revenue: $180,000/month (mixed retainer and project contracts)
- Fixed expenses: $140,000/month (salaries, facilities, software, insurance)
- Proposed hire: $8,500/month (fully loaded)
- Forecast: 6 months

**Forecast (Base Case):**

| | M1 | M2 | M3 | M4 | M5 | M6 |
|---|-----|-----|-----|-----|-----|-----|
| Starting Cash | $420K | $451.5K | $483K | $514.5K | $546K | $577.5K |
| Revenue | $180K | $180K | $180K | $180K | $180K | $180K |
| Fixed Expenses | -$140K | -$140K | -$140K | -$140K | -$140K | -$140K |
| New Hire | -$8.5K | -$8.5K | -$8.5K | -$8.5K | -$8.5K | -$8.5K |
| **Net Cash Flow** | **$31.5K** | **$31.5K** | **$31.5K** | **$31.5K** | **$31.5K** | **$31.5K** |
| **Ending Cash** | **$451.5K** | **$483K** | **$514.5K** | **$546K** | **$577.5K** | **$609K** |

**Conservative Scenario** (revenue at 80% of base, expenses at 110% of base from month 3):

| | M1 | M2 | M3 | M4 | M5 | M6 |
|---|-----|-----|-----|-----|-----|-----|
| Ending Cash | $451.5K | $483K | $487K | $458K | $429K | $400K |

**Key Metrics:**
- Burn rate with hire: $148.5K/month
- Revenue coverage: 1.21x (base) / 1.02x (conservative)
- Cash runway (conservative): 21+ months
- Lowest cash point: $400K (month 6, conservative)

**Recommendation:** The hire is financially viable under both scenarios. Even with a 15% revenue drop, cash remains well above a 2-month reserve. Proceed.

### Example 2: Seasonal Business — Inventory Planning

**Inputs:**
- Cash on hand: $85,000
- Revenue: $120,000/month average, but seasonal (Oct-Dec: $280,000, Jan-Feb: $40,000)
- Fixed expenses: $60,000/month
- Q3 inventory buy: $95,000 in August

**Key Finding:** Cash drops to $14,000 in September (after inventory buy, before peak season). Recommendation: secure a credit facility before August or pre-sell contracts in July.

## Recovery and Fallbacks

- **Inputs are ranges, not exact numbers:** Use the low end of the range (conservative). "Revenue is probably $150K-$180K/month" → model at $150K.
- **Revenue is highly variable:** Use the lowest 3-month average as the baseline, not the overall average.
- **No financial records:** Start with bank statements. Total deposits = revenue, total debits = expenses. It's rough but usable.
- **Forecast shows negative runway:** Present options — cut specific expenses, accelerate a revenue initiative, or bridge with credit. Name the options, let the user decide.

## Constraints

- **Always include the financial disclaimer**
- **Never present forecasts as guarantees** — they are estimates based on stated assumptions
- Always show assumptions beneath every projection
- Use conservative scenario as the planning baseline
- Flag any month where ending cash drops below 1 month of expenses
- Round to whole dollars
