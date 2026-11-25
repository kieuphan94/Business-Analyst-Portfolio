# Customer 360 — User Requirements Document

> **Portfolio sample.** Two representative functions extracted from a production URD (FPT Telecom — Customer 360). All sample values, pricing formulas, infrastructure fields, and internal account names are masked or fabricated under NDA. Purpose: demonstrate requirement specification, role-based access design, and edge-case handling — not an operational document.

---

## Document Control

| Attribute | Value |
|---|---|
| Document title | Customer 360 — User Requirements Document |
| Module | Portal Customer 360 — Search & Overview |
| Owner role | Business Analyst / UX Architect |
| Status | Sample (redacted) |
| Classification | Public portfolio — NDA-safe |
| AC notation | Gherkin (Given / When / Then) |

## Revision History

| Ver | Date | Type | Description | Author |
|---|---|---|---|---|
| 1.0.0 | 2025-01-03 | [A] | Initial baseline | BA |
| 1.0.1 | 2025-02-18 | [U] | Added field-level access matrix; refined search recognition logic | BA |

> **Legend —** `[A]` Add · `[U]` Update · `[D]` Delete

---

## 1. Introduction

### 1.1 Purpose

This document specifies the requirements for two core functions of the Customer 360 portal: **customer search with identity recognition** and **field-level access control**. Together they realise the project's foundational decision — shifting the data anchor from **Contract ID** to **Customer ID** — while enforcing privacy on personally identifiable information (PII).

### 1.2 Scope

| In scope | Out of scope |
|---|---|
| Search screen & input-type recognition | Churn-prediction insight logic |
| Result rendering, masking, pagination | Billing / tariff calculation |
| Field-level permission model (3 tiers) | Device & network-infrastructure fields |

### 1.3 Glossary

| Term | Definition |
|---|---|
| **EDW** | Enterprise Data Warehouse — the unified, deduplicated data source |
| **Host application** | A system that embeds Customer 360 (CRM, FSM, SOP…) |
| **PII** | Personally Identifiable Information |
| **Partial Match** | Search returning records that partially match the input string |
| `" "` | Literal text — rendered verbatim |
| `' '` | Dynamic value returned by the system |

---

## 2. Access Model

Field visibility resolves against a three-tier permission model, evaluated per host application and per user role.

### 2.1 Permission tiers

| Tier | Rendering behaviour |
|---|---|
| **Full view** | Field value shown in full |
| **Masked view** | Partially obscured — only a safe fragment exposed (e.g. last 4 digits) |
| **No view** | Value left blank; no PII placeholder rendered |

### 2.2 Precedence rule

| Priority | Rule source | Applies when |
|---|---|---|
| 1 (highest) | Special permission group | User belongs to a restricted group |
| 2 | Host-application default | No special-group override exists |

> A special-group restriction **overrides** the host-application default for the same field.

---

## 3. Non-Functional Requirements

| ID | Category | Requirement |
|---|---|---|
| NFR-01 | Performance | A resolved customer lookup returns in **< 1 second** |
| NFR-02 | Data freshness | EDW latency ~1 day; every screen (except Search) shows "Data current as of 'X'" where X = yesterday |
| NFR-03 | Privacy | PII fields obey the three-tier access model on every host application |
| NFR-04 | Usability | Table headers and current-page indicator remain fixed on scroll |
| NFR-05 | Resilience | On session expiry, the user is prompted to refresh before continuing |

---

## 4. Assumptions & Constraints

| # | Assumption / Constraint |
|---|---|
| 1 | Satellite tools already in production must not be disrupted by the rollout |
| 2 | Legacy infrastructure limits real-time sync; non-critical flows run in batch |
| 3 | One person may hold multiple contracts; identity must deduplicate to a single Customer ID |
| 4 | Billing is the source of truth when CRM and Billing conflict |

---

# FUNC-01 — Customer Search & Identity Recognition

## 1.1 Overview

| Attribute | Value |
|---|---|
| Objective | Resolve any input (contract no. / phone / name / address) to a single customer record |
| Primary actors | CS Agent · Field Technician · Sales |
| Pre-condition | User authenticated and granted Customer 360 access on the host application |
| Trigger | User submits a query via the search box (icon click or Enter) |

## 1.2 Input Recognition Logic

| Input type | Recognition signal | Action |
|---|---|---|
| **Contract No.** | 7 ≤ length ≤ 10; first 3 chars alphabetic, ends with a digit | Query by contract number |
| **Phone** | Exactly 10 digits, no separators | Query by phone number |
| **Name / Address** | Neither condition above satisfied | Query by customer name or installation address |

- Mechanism: **Partial Match Search**.
- Result cap: **100 records** maximum.

## 1.3 Result Column Specification

| Column | Display rule | Masking |
|---|---|---|
| Contract No. | Full value | — |
| Customer Name | Full name, full view | — |
| Phone | Mask characters 4–7 with `*` (e.g. `093****012`) | Yes |
| Status | Full value | — |
| Address | Street + Ward + District + Province only | Partial |

**Pagination**

| Rule | Value |
|---|---|
| Default rows per page | 15 |
| Selectable blocks | 15 / 30 / 50 / 100 |
| Page indicator | `"Results:" 'first' "–" 'last' "of" 'total'` (e.g. Results: 1–15 of 50) |
| Fixed elements on scroll | Table header + page indicator; Page 1 pinned |

## 1.4 User Story & Acceptance Criteria

> **US-01** — As a CS Agent, I want to look a customer up by phone or national-ID so that I see one customer record with all their contracts, instead of querying each Contract ID across systems.

| AC ID | Given | When | Then |
|---|---|---|---|
| AC-01.1 | Input is exactly 10 digits | Agent submits the search | System recognises it as a phone number; returns partial matches (≤ 100); phone column masked (chars 4–7) |
| AC-01.2 | Customer holds ≥ 2 active contracts under one national-ID | Agent searches by phone or national-ID | System returns exactly **one** Customer record with the full contract list |
| AC-01.3 | Input matches no EDW record | Agent submits the search | System shows "No matching result. Please try another keyword." |
| AC-01.4 | Search box is empty | Agent submits the search | No action is taken |

## 1.5 Edge Cases

| # | Scenario | Handling rule |
|---|---|---|
| 1 | One national-ID bound to two phone numbers | Merge by national-ID; flag duplicate phone |
| 2 | Customer is a business entity | Add recognition by Tax Code |
| 3 | Contract already terminated | Still returned, labelled as *History* status |
| 4 | Host application in masked view | Phone and address follow §1.3 masking rules |
| 5 | Input cleared after a prior result | Previously returned results are cleared |

---

# FUNC-02 — Field-Level Access Control (PII)

## 2.1 Overview

| Attribute | Value |
|---|---|
| Objective | Protect customer PII by rendering fields per the three-tier access model |
| Primary actors | Any Customer 360 user; System Owner (configuration) |
| Pre-condition | Host application configured in the Permission Matrix (§2) |
| Design principle | Privacy by design |

## 2.2 Field Specification & Permission

| Field | Full view | Masked view | No view |
|---|---|---|---|
| National-ID / Passport | Full value | Last 4 digits; rest `*` | — |
| Tax Code (business) | Full value | Last 4 digits; rest `*` | — |
| Primary Phone | Full value | Mask chars 4–7 | — |
| Secondary Phone | Inherits primary-phone tier | Inherits primary-phone tier | — |
| Email | Full value | — | Blank |
| Installation Address | Full + map link | Street→Province; no map link | — |
| Customer Segment | Full value | — | Blank |

> **Entity rule —** For a **business** customer, the National-ID field is suppressed and replaced by Tax Code (rendered per its own tier).

## 2.3 User Story & Acceptance Criteria

> **US-02** — As a System Owner, I want to configure PII visibility per host application, so that each application sees only the data it is authorised for, protecting customer privacy.

| AC ID | Given | When | Then |
|---|---|---|---|
| AC-02.1 | Host app set to masked view for National-ID | User opens an individual customer | National-ID shows last 4 digits, rest `*` |
| AC-02.2 | Customer is a business entity | User opens the profile | National-ID suppressed; Tax Code shown per its tier |
| AC-02.3 | User belongs to a special permission group | User accesses a contract field | Special-group rule applied, overriding host-app default |
| AC-02.4 | Email field set to no view | User opens the profile | Email value rendered blank; no placeholder |

## 2.4 Edge Cases

| # | Scenario | Handling rule |
|---|---|---|
| 1 | User in special permission group | Special-group rule takes precedence over host-app default |
| 2 | Business customer in masked view | Suppress National-ID; show Tax Code last 4 digits |
| 3 | Field configured as no view | Leave blank; render no PII placeholder |
| 4 | Secondary phone while primary is masked | Secondary phone masked by the same mechanism |
| 5 | Address in masked view | Hide "Open map" alongside address truncation |

---

## Appendix — Notes

| Note |
|---|
| This extract covers 2 of 4 functions in the source URD, chosen to demonstrate identity resolution and privacy-by-design. |
| All example values are fabricated; tariff formulas, network-infrastructure fields, and internal account names are removed under NDA. |
| Acceptance Criteria follow the Given/When/Then convention for direct conversion into test cases. |
