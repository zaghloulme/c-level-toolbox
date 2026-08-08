---
name: Letter of Intent
version: 1.8.0
description: "Drafts non-binding letters of intent for corporate acquisitions, partnerships, joint ventures, and commercial agreements — covering deal structure, key terms, exclusivity, and due diligence conditions."
---

## Toolbox rules

Before starting: silently read `user-config.md` in the current directory. Match the user's tone preference and the "what to avoid" notes. If it does not exist, tell the user to run `/setup` first, then stop.

When multiple paths could work, pick the best one and state it in one line. Do not present a numbered list of choices for the user to pick from.

Follow the writing rules in `CLAUDE.md` at the plugin root: banned words, active voice, concrete over abstract, no formatting slop.

---

# Letter of Intent

## Core Principle

A LETTER OF INTENT ALIGNS BOTH PARTIES ON KEY TERMS BEFORE INVESTING IN EXPENSIVE LEGAL DRAFTING — IT IS A HANDSHAKE PUT ON PAPER.

## Phase 1: Transaction Details

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Transaction type** | "What type of deal? (acquisition, investment, joint venture, partnership, licensing)" | No default — must be provided |
| **Parties** | "Who are the parties involved?" | No default — must be provided |
| **Key terms** | "What are the proposed deal terms? (price, structure, timeline)" | No default — must be provided |
| **Binding provisions** | "Should confidentiality and exclusivity be binding?" | Yes — both binding |
| **Due diligence period** | "How long for due diligence?" | 30-60 days |
| **Target closing date** | "When is the target closing date?" | 60-90 days from LOI signing |

**GATE: Do not proceed without transaction type, parties, and key terms.**

## Phase 2: LOI Structure

```
## Letter of Intent

[Date]

[Recipient Name]
[Recipient Title]
[Recipient Company]
[Address]

Re: Letter of Intent — [Brief Description of Transaction]

Dear [Name],

This Letter of Intent ("LOI") sets forth the principal terms under
which [Acquiring/Investing Party] ("Buyer/Investor/Partner") proposes to
[acquire/invest in/partner with] [Target Company] ("Seller/Company/
Target"). This LOI is intended as the basis for further discussion and
negotiation of a definitive agreement.

### 1. Transaction Structure

[Description of the proposed transaction — asset purchase, share
purchase, investment, joint venture, licensing arrangement]

### 2. Consideration

- Total consideration: [Amount and currency]
- Structure: [Cash / shares / earnout / combination]
- Payment terms: [[X] at closing, [X] over [X] months, [X] based on
  performance milestones]

[For acquisitions, include:]
- Valuation basis: [Multiple of revenue / EBITDA / assets / other]
- Price adjustments: [Working capital adjustment / earn-out based
  on [metrics] over [period]]

### 3. Key Terms and Conditions

| Term | Detail |
|------|--------|
| Closing date | On or before [Date] |
| Employees | [Retained / offered employment / not included] |
| Assets included | [List key assets included] |
| Liabilities assumed | [List or "none"] |
| Representations and warranties | Standard for this type of transaction |
| Non-compete | [Duration and scope for seller] |
| Transition period | [X months of seller support] |

### 4. Conditions Precedent

The closing of this transaction is subject to:
a) Satisfactory completion of due diligence by [Buyer/Investor]
b) Negotiation and execution of a definitive agreement
c) Board approval by both parties
d) Applicable regulatory approvals
e) No material adverse change in the Target's business
f) [Other conditions specific to the deal]

### 5. Due Diligence

[Buyer/Investor] shall have [30-60] days from the execution of this
LOI to conduct due diligence, including review of:
- Financial statements and tax returns ([3-5] years)
- Customer and vendor contracts
- Employment and contractor agreements
- Intellectual property assets
- Legal proceedings and compliance
- [Other relevant areas]

[Seller/Target] agrees to provide reasonable access to information,
personnel, and premises during the due diligence period.

### 6. Exclusivity (BINDING)

During the period from the execution of this LOI until [date or
X days], [Seller/Target] agrees not to solicit, encourage, or
entertain any proposals or offers from third parties regarding a
similar transaction. [Seller/Target] shall immediately notify
[Buyer/Investor] if any unsolicited offers are received.

### 7. Confidentiality (BINDING)

Both parties agree to keep all information exchanged during
negotiations and due diligence strictly confidential. Neither party
shall disclose the existence or terms of this LOI to third parties
without the other party's written consent, except to professional
advisors bound by confidentiality obligations.

### 8. Non-Binding Nature

Except for Sections 6 (Exclusivity), 7 (Confidentiality), and
this Section 8, this LOI is not binding and does not create any
legal obligation for either party to consummate the proposed
transaction. A binding obligation arises only upon execution
of a definitive agreement.

### 9. Expenses

Each party bears its own costs and expenses (legal, accounting,
advisory) in connection with this LOI and the proposed transaction.

### 10. Governing Law

This LOI is governed by the laws of [Jurisdiction].

### 11. Expiration

This LOI expires if not executed by both parties by [Date — typically
7-14 days from delivery].

---

Sincerely,

[Name]
[Title]
[Organization]

ACKNOWLEDGED AND AGREED:

[Recipient Name]
[Recipient Title]
[Recipient Organization]
Date: _______________
```

## Phase 3: Review Key Terms

- Verify price and payment structure align with both parties' expectations
- Confirm exclusivity period is sufficient for due diligence
- Ensure binding vs. non-binding sections are clearly designated
- Check that conditions precedent are achievable within the timeline

## Phase 4: Delivery

```
## LOI Checklist

- [ ] Transaction structure clearly described
- [ ] Price and payment terms specified
- [ ] Due diligence period and scope defined
- [ ] Exclusivity period set (binding)
- [ ] Confidentiality clause included (binding)
- [ ] Non-binding nature clearly stated for all other provisions
- [ ] Expiration date included
- [ ] Conditions precedent listed
- [ ] Reviewed by legal counsel
- [ ] Sent with appropriate cover communication
```

## Example: Corporate Acquisition

**Transaction:** Buyer acquiring a regional distribution business. **Structure:** Total consideration EGP 12M — EGP 9M at closing, EGP 3M earnout over 18 months tied to maintaining 85% of trailing revenue. **Due diligence:** 45 days covering financials, customer contracts, warehouse leases, and key staff arrangements. **Exclusivity:** 60 days. **Conditions:** Clean audited financials, no undisclosed liabilities, seller non-compete for 36 months in the same geography. **Transition:** Seller provides 90 days of operational support post-closing.

## Anti-Patterns

- **Making the entire LOI binding** — only confidentiality, exclusivity, and governing law should be binding. Everything else is subject to the definitive agreement.
- **Vague price terms** — "a fair price to be agreed" is not a term. Include a specific figure or a defined formula.
- **No expiration date** — an LOI without a deadline can leave both parties in limbo indefinitely.
- **Skipping exclusivity** — without exclusivity, the other party can shop your offer to competitors. Always include an exclusivity period.
- **Using the LOI as the final agreement** — an LOI is a precursor, not a substitute for a definitive agreement drafted by counsel.

## Recovery

- **Other party pushes back on terms:** LOIs are negotiable. Identify must-haves vs. acceptable concessions. Focus on aligning critical terms first.
- **Due diligence reveals problems:** The LOI is non-binding for this reason. Renegotiate terms, adjust the price, or withdraw.
- **Exclusivity period expiring:** Extend by mutual agreement if due diligence requires more time. Do not let exclusivity lapse without a clear decision.
- **Other party wants to skip the LOI:** Recommend against it. Undocumented term alignment leads to expensive drafting disputes later. The LOI protects both parties.
