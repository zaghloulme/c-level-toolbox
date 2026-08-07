---
name: KPI Dashboard Builder
description: "Builds KPI tracking dashboards in markdown — metrics, targets, status indicators, and trend tracking for centralized business performance visibility."
allowed-tools: Read Write Glob
---

# KPI Dashboard Builder

## Core Principle

A DASHBOARD THAT TRACKS EVERYTHING TRACKS NOTHING — LIMIT TO 5-8 KPIs THAT DIRECTLY REFLECT BUSINESS HEALTH.

## Workflow

### Step 1: Identify Key Metrics

Ask the user:
1. What type of business? (e-commerce, SaaS, service, content creator)
2. What are you trying to improve right now? (revenue, growth, efficiency, retention)
3. How often will you review this? (weekly, monthly, quarterly)
4. Who else will see this dashboard? (executive team, board, investors)

**Minimum needed: question 1.**

### Step 2: Select KPIs by Business Type

**E-commerce:**
| KPI | Formula | Target Example | Frequency |
|-----|---------|---------------|-----------|
| Revenue | Total sales | $25,000/mo | Weekly |
| Average Order Value | Revenue / Orders | $58 | Weekly |
| Conversion Rate | Orders / Visitors | 2.5% | Weekly |
| Customer Acquisition Cost | Ad Spend / New Customers | < $25 | Monthly |
| Return Rate | Returns / Orders | < 5% | Monthly |

**SaaS / Subscription:**
| KPI | Formula | Target Example | Frequency |
|-----|---------|---------------|-----------|
| MRR | Sum of active subscriptions | $15,000 | Weekly |
| Churn Rate | Lost customers / Total customers | < 5%/mo | Monthly |
| LTV | Avg revenue per customer × avg lifespan | > $500 | Quarterly |
| CAC | Sales + Marketing spend / New customers | < $100 | Monthly |
| LTV:CAC Ratio | LTV / CAC | > 3:1 | Quarterly |

**Professional Services:**
| KPI | Formula | Target Example | Frequency |
|-----|---------|---------------|-----------|
| Revenue | Invoiced amount | $12,000/mo | Monthly |
| Utilization Rate | Billable hours / Available hours | > 70% | Weekly |
| Pipeline Value | Sum of proposal values | $50,000 | Weekly |
| Close Rate | Won proposals / Total proposals | > 40% | Monthly |
| Client Retention | Returning clients / Total clients | > 80% | Quarterly |

**Content / Media:**
| KPI | Formula | Target Example | Frequency |
|-----|---------|---------------|-----------|
| Revenue | Sponsorships + Products + Affiliate | $8,000/mo | Monthly |
| Email List Size | Total subscribers | 10,000 | Weekly |
| Email Open Rate | Opens / Delivered | > 40% | Weekly |
| Engagement Rate | (Likes + Comments) / Followers | > 3% | Weekly |
| Content Published | Posts/videos/episodes produced | 12/mo | Weekly |

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

### Step 4: Provide Filtering Guidance

After delivering the dashboard, provide these instructions for working with it:

```
**How to use this dashboard:**

- **Weekly focus:** Look for 🔴 Off Track rows first, then 🟡 At Risk. These need attention.
- **Trend check:** Any KPI with ↓ Down and 🟢 On Track is worth watching — it may cross into At Risk next period.
- **Update frequency:** Replace "Current" values at the cadence in your review rhythm. Update the "Updated" date.
- **If pasting into a spreadsheet:** The table pastes directly into Google Sheets or Excel. Add conditional formatting on the Status column to preserve the color coding.
```

### Step 5: Set Up Review Rhythm

Provide a review checklist:
- **Weekly (15 min):** Update all weekly KPIs, flag anything Off Track
- **Monthly (30 min):** Update all KPIs, compare to previous month, adjust targets if needed
- **Quarterly (60 min):** Full review, set new targets, add/remove KPIs

## Examples

### Example 1: E-commerce Dashboard

| KPI | Current | Target | Status | Trend |
|-----|---------|--------|--------|-------|
| Monthly Revenue | $22,400 | $25,000 | At Risk | Up |
| Average Order Value | $62 | $58 | On Track | Up |
| Conversion Rate | 1.8% | 2.5% | Off Track | Flat |
| New Customers | 180 | 200 | At Risk | Up |
| Return Rate | 3.2% | < 5% | On Track | Down |
| Email List Growth | +340 | +500 | At Risk | Flat |
| Ad ROAS | 3.2x | 3.0x | On Track | Up |

**Weekly Review Notes:**
> Revenue trending up but still below target — conversion rate is the bottleneck. AOV is strong (above target), so traffic quality may be the issue. Action: Review ad targeting this week, check landing page bounce rate.

### Example 2: Professional Services Dashboard

| KPI | Current | Target | Status | Trend |
|-----|---------|--------|--------|-------|
| Monthly Revenue | $9,800 | $12,000 | At Risk | Flat |
| Utilization Rate | 58% | 70% | Off Track | Down |
| Pipeline Value | $42,000 | $50,000 | At Risk | Up |
| Active Clients | 3 | 4 | At Risk | Flat |
| Close Rate | 45% | 40% | On Track | Up |
| Avg Project Value | $4,200 | $4,000 | On Track | Up |

**Insight:** Close rate is strong but pipeline is light. The constraint is generating leads, not converting them.

## Recovery

- **User doesn't know what to track:** Start with revenue + one growth metric + one efficiency metric. Three KPIs beats zero KPIs.
- **User wants to track 20+ metrics:** Push back. A dashboard with 20 metrics is a spreadsheet. Force-rank and pick the top 5-8.
- **User wants a spreadsheet instead of markdown:** The table in Step 3 pastes directly into Google Sheets or Excel. Provide the markdown output and note they can paste it in.
- **Metrics aren't improving:** Dashboards show problems; they don't fix them. When a KPI is Off Track for 3+ periods, it needs an action plan.

## Constraints

- **NEVER include more than 8 KPIs** on the primary dashboard — create a secondary "detail" view for nice-to-haves
- Every KPI must have a defined target — a metric without a target is just a number
- Include status indicators (On Track / At Risk / Off Track) for at-a-glance reading
- Always include a "Last Updated" field to prevent stale data from looking current
- Provide the review rhythm — a dashboard nobody looks at is useless
