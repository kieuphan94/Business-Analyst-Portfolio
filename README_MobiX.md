# MobiX — Field Service Management Modernization

> **Case study:** Consolidating 12 fragmented applications into a task-oriented field-service platform for 10,000+ technicians across 63 provinces in Vietnam.

## Project Overview

MobiX was an operational modernization initiative at FPT Telecom. The project aimed to simplify field-service workflows, reduce application fragmentation, and release development capacity constrained by legacy-system maintenance.

The challenge was not simply to combine 12 applications. Each system had evolved around different departmental processes, data structures, and ownership boundaries. The result was a fragmented experience for technicians and a growing technical-maintenance burden for development teams.

| Project metric | Context |
|---|---|
| Users served | 10,000+ field technicians |
| Geographic coverage | 63 provinces |
| Applications in scope | 12 |
| Legacy maintenance burden | More than 60% of each development sprint, as reported in the project context |
| Reported business outcomes | Approximately 25% lower direct operating costs and 250,000+ field-work hours saved annually |

## Business Problem

The fragmented application landscape created problems at both operational and technical levels.

**For field technicians**
- Technicians had to switch between multiple applications to complete a single job.
- Important information, including materials and work-order details, was spread across separate systems.
- The fragmented workflow made it harder to prepare correctly before leaving a branch and increased avoidable back-and-forth trips.

**For development teams**
- Multiple legacy applications and versions increased maintenance complexity.
- More than 60% of sprint capacity was reportedly spent fixing defects and maintaining existing systems.
- Limited development capacity made it harder to respond quickly to new business and sales-policy requirements.

The underlying issue was not the number of screens or applications alone. It was the mismatch between application boundaries and the end-to-end workflow technicians needed to complete.

## My Contribution

I contributed to translating the modernization direction into user-centred workflow and product decisions.

My work included:

- **Field research:** Shadowed technicians at branch level to understand their actual work sequence, application usage, and operational constraints.
- **Workflow analysis:** Identified friction in the preparation and materials-checking process, and examined how fragmented tools affected job completion.
- **Requirement prioritization:** Used field evidence and operational needs to establish a shared prioritization principle: whether a capability helped technicians complete their work more effectively in the field.
- **Experience and navigation redesign:** Reorganized the MobiX navigation around the technician's task flow rather than departmental ownership. The Materials module was promoted to a primary navigation level.
- **Stakeholder alignment:** Worked across business and technical stakeholders to clarify requirements and address competing views on feature ownership and application scope.
- **Migration collaboration:** Worked with the technical team on a phased transition approach intended to reduce disruption to ongoing field operations.

## Key Insight

Field observation revealed that technicians were adapting their behaviour to the structure of the systems, rather than the systems supporting the natural sequence of their work.

For example, a technician could need to open several applications to check location, materials, and assigned work orders before starting a job. Materials readiness was especially important: if the required equipment was missing, the technician might have to return to the branch, disrupting the rest of the day's schedule.

This led to a practical decision principle:

> **Prioritize capabilities that reduce friction in the technician's end-to-end workflow and help them complete field work with the right information and materials.**

This principle provided a user-centred basis for prioritization and stakeholder discussions.

## Solution Approach

### 1. Reorganize the experience around real work

The MobiX experience was restructured around the technician's workflow rather than the structure of individual departments.

A key example was moving **Materials** from a deeply nested location to a primary navigation tab, making it easier for technicians to access materials-related information as part of job preparation.

### 2. Migrate in phases rather than using a big-bang replacement

Because field operations had to continue throughout the transition, the project followed a phased migration approach.

The project sequence included:

1. **Discovery and scope assessment** — review existing capabilities and operational usage to distinguish core workflows from low-value or redundant functionality.
2. **Core-scope definition** — prioritize the capabilities required to keep essential field operations running.
3. **Technical foundation and integration** — collaborate with the technical team on data organization and integration between existing and modernized components.
4. **Pilot and validation** — validate the new approach with a limited user group, gather feedback, and refine workflow logic before broader rollout.
5. **Incremental rollout** — release capabilities progressively and transition corresponding workflows from legacy applications.
6. **Legacy decommissioning** — retire old components as their replacement capabilities become stable and operationally ready.

The migration was approached as a risk-managed transition, not a one-time cutover. The rollout was sequenced by first validating the approach with four lower-risk internal applications, followed by the eight more complex field applications.

### 3. Coordinate around shared operational outcomes

With multiple systems and teams involved, application ownership could easily dominate prioritization discussions. Field-work evidence helped shift the conversation toward a common question: which change would improve the technician's ability to complete the job?

This gave stakeholders a more consistent basis for discussing scope and trade-offs.

## Outcomes

Following the rollout, the project reported the following operational outcomes:

- Consolidation of 12 fragmented applications into a more unified field-service experience.
- Support for more than 10,000 technicians across 63 provinces.
- Approximately **25% reduction in direct operating costs**.
- More than **250,000 field-work hours saved annually**.
- Reduced legacy-maintenance burden, helping restore development capacity for new business requirements.

*Note: The cost and annual-hours figures are project-reported business outcomes. They are not presented as metrics independently measured by me.*

## What This Case Demonstrates

This project demonstrates my ability to:

- Investigate operational problems beyond the initial project brief.
- Translate field observations into workflow and product decisions.
- Prioritize requirements using user and business evidence.
- Align stakeholders with competing ownership and delivery concerns.
- Contribute to phased modernization while protecting business continuity.

**Key takeaway:** Effective modernization starts by understanding how work actually happens, then aligning process, product, and technology decisions around that reality.

---

## Project Artifacts

The following materials can be added to this section when sanitized for public sharing:

- Current-state and future-state process flows (BPMN).
- Workflow and navigation diagrams.
- Sample business requirements and user stories.
- Requirements traceability and acceptance-criteria examples.
- Redacted product screenshots or wireframes.

*All artifacts should be anonymized and reviewed to ensure that internal, customer, employee, and system-sensitive information is not disclosed.*

## Confidentiality

This case study describes the project at a high level. Internal system names, source code, production data, customer information, and confidential company documentation are intentionally excluded.
