---
name: Intellectual Property Audit
version: 1.5.5
description: "Conducts a structured audit of an organization's intellectual property assets — trademarks, patents, copyrights, trade secrets, and software — to identify ownership gaps, protection status, and exposure."
---

# Intellectual Property Audit

## Core Principle

YOUR IP IS OFTEN YOUR MOST VALUABLE BUSINESS ASSET — IF YOU DO NOT KNOW WHAT YOU OWN, YOU CANNOT PROTECT IT, LICENSE IT, OR USE IT.

## Phase 1: Business Inventory

### Required Inputs

| Input | What to Ask | Default |
|-------|------------|---------|
| **Organization name** | "What is the legal entity name?" | No default — must be provided |
| **Products/services** | "What does the organization sell or provide?" | No default — must be provided |
| **Brand assets** | "What brand names, logos, and slogans are in use?" | No default — list all |
| **Content and software** | "What original content, software, or designs has the organization created?" | No default — list all |
| **Processes and methods** | "Any proprietary processes, methods, or formulas?" | None |
| **Employee/contractor work** | "Have employees or contractors created IP for the organization?" | Yes |

**GATE: Do not proceed without brand assets and content inventory.**

## Phase 2: IP Inventory

### Trademark Assets

```
## Trademark Inventory

| Asset | Type | Status | Registration # | Class | Renewal Date |
|-------|------|--------|----------------|-------|-------------|
| [Organization name] | Word mark | [Registered/Pending/Unregistered] | [#] | [Class] | [Date] |
| [Logo] | Design mark | [Status] | [#] | [Class] | [Date] |
| [Product name] | Word mark | [Status] | [#] | [Class] | [Date] |
| [Slogan/tagline] | Word mark | [Status] | | | |
| [Domain names] | Domain | Active | N/A | N/A | [Renewal] |

### Trademark Gaps
- [ ] [Asset] — in commercial use but not registered
- [ ] [Asset] — potential conflict identified
```

### Copyright Assets

```
## Copyright Inventory

| Asset | Type | Created | Registered | Creator | Ownership |
|-------|------|---------|-----------|---------|-----------|
| [Software platform] | Software | [Date] | [Yes/No] | [Creator] | [Company/Assigned] |
| [Marketing materials] | Literary/Visual | [Date] | [No] | [Creator] | [Status] |
| [Technical documentation] | Literary work | [Date] | [No] | [Creator] | [Status] |
| [Training content] | Educational | [Date] | [Yes/No] | [Creator] | [Status] |
| [Designs/graphics] | Visual art | [Date] | [No] | [Creator] | [Status] |

### Copyright Gaps
- [ ] [Asset] — created by contractor without IP assignment clause
- [ ] [Asset] — high-value work with no formal ownership documentation
```

### Trade Secrets

```
## Trade Secret Inventory

| Asset | Description | Protection in Place |
|-------|-------------|-------------------|
| [Customer data models] | [Proprietary segmentation and data structures] | [NDA: Yes/No, Access restricted: Yes/No] |
| [Pricing methodology] | [Proprietary pricing and margin framework] | [NDA: Yes/No] |
| [Operational processes] | [Unique business processes or methods] | [Documented: Yes/No] |
| [Supplier terms] | [Vendor relationships and commercial terms] | [NDA: Yes/No] |

### Trade Secret Gaps
- [ ] [Asset] — no NDA covering access
- [ ] [Asset] — accessible to departing employees without restriction
```

### Patent Assets (if applicable)

```
## Patent Inventory

| Asset | Type | Status | Application # | Expiration |
|-------|------|--------|---------------|-----------|
| [Invention/technology] | [Utility/Design/Provisional] | [Granted/Pending/None] | [#] | [Date] |
```

## Phase 3: Risk Assessment

```
## IP Risk Assessment

### Protection Gaps (Action Required)
| Risk | Severity | Action Needed | Priority |
|------|----------|--------------|----------|
| [Brand name unregistered] | High | File trademark application | Immediate |
| [Contractor work without IP assignment] | High | Execute assignment agreements | Immediate |
| [No NDAs with staff accessing confidential assets] | Medium | Issue and execute NDAs | Within 30 days |
| [Key software not formally owned] | High | Legal review and assignment | Immediate |
| [Domain variations unsecured] | Low | Register key variations | Within 90 days |

### Infringement Risks
| Risk | Description | Action |
|------|-------------|--------|
| [Third party using similar brand] | [Details] | [Monitor / Cease and desist / Legal review] |
| [Content copied or republished] | [Details] | [Takedown notice / Legal review] |

### Contractual IP Issues
| Issue | Description | Action |
|-------|-------------|--------|
| [Contractor with no IP clause] | [Past work may not be owned by the organization] | Execute retroactive assignment |
| [Employee with no invention assignment] | [Inventions may be disputed] | Add clause to employment agreement |
```

## Phase 4: IP Management Plan

```
## IP Action Plan

### Immediate (Next 30 Days)
1. [ ] [Action — e.g., file trademark for primary brand name]
2. [ ] [Action — e.g., execute IP assignment with key contractors]
3. [ ] [Action — e.g., implement NDAs for all staff with access to trade secrets]

### Short-Term (30-90 Days)
1. [ ] [Action]
2. [ ] [Action]

### Ongoing
- [ ] Annual IP audit (schedule for [month])
- [ ] Trademark renewal tracking
- [ ] New product/software IP assessment before launch
- [ ] All contractor agreements include IP assignment clause as standard
- [ ] Monitor for infringement [monthly / quarterly]
```

## Example: Technology Company IP Audit

**IP assets:** Corporate brand name (registered), three product names (unregistered), software platform source code, API documentation, customer data models, proprietary algorithm, website content, partner agreement templates.

**Key findings:** Product names are not trademarked — competitors could adopt them. Software created partly by external contractors without IP assignment clauses — ownership is unclear for those components. Customer data models classified as trade secrets but accessible without NDA.

**Priority actions:** 1) File trademarks for product names. 2) Execute IP assignment agreements with all contractors who contributed to the platform codebase. 3) Implement NDAs and access controls for customer data models. 4) Add standard IP assignment clause to all future contractor agreements.

## Anti-Patterns

- **Assuming you own what you paid for** — without a written IP assignment, the creator may retain ownership. This applies especially to contractors.
- **Only auditing trademarks** — IP includes copyrights, trade secrets, and potentially patents. Audit all categories.
- **Ignoring domain names** — domains are brand assets. Secure key variations and common misspellings.
- **No regular audit cadence** — IP grows as the organization grows. Audit annually and after any acquisition or material product launch.
- **Treating trade secrets casually** — a trade secret that is not kept secret loses its legal protection.

## Recovery

- **Contractor created key assets without an IP clause:** Negotiate a retroactive assignment agreement. This may require additional compensation.
- **Discovered third-party infringement of your brand:** Document the infringement with dated evidence. Send a cease and desist. Involve IP counsel if they do not comply.
- **Trademark name already taken:** Assess the overlap (different class, different geography). Consult a trademark attorney for options.
- **No IP protections in place:** Start with the highest-value asset — typically the primary brand name (trademark) and core software or product content (copyright assignment and documentation).
