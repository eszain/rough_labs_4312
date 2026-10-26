## Requirements Baseline v1.0 Submission — Pull Request Summary

**Course:** EECS 4312 — Software Requirements Engineering  
**Project:** Public Transit Lost & Found System (Group 11)  
**Sprint:** Requirements Sprint 1 — Elicitation & Initial Requirements Baseline  
**Date:** October 25, 2026  
**Team Members:** Mohammad Zain Al Syed (@eszain), Muhammad Sufyan (@abdullah998020-gif), Anirudh Sundar (@asxter)  

---

### 1. Executive Summary & Sprint Goal

This Pull Request represents the formal integration and submission of **Requirements Baseline v1.0** for EECS 4312 Group 11. Over Sprint 1, our team conducted systematic elicitation, synthesized evidence, resolved Sprint 0 evaluation feedback, and established an authoritative, verifiable requirements baseline composed of exactly **28 atomic requirements** (2 BR, 6 SR, 15 FR, 3 QR, 2 CON — zero artificial inflation).

All deliverables have been integrated strictly according to the layout specified in `sprint1_handout.md` Section 14 and verified against the criteria of `eecs4312_sprint_1_rubric.md`.

---

### 2. Summary of Changes and Deliverables

#### A. Sprint Planning & Continuity (Rubric Section 1)
* `doc/sprint1/sprint0-feedback.md`: Systematically addresses all 4 marker comments from Sprint 0 evaluation (readable context diagram, IPC/AODA glossary entries, external technical stakeholders, and ISO-dated decision records) along with Lab 6 defect corrections.
* `doc/sprint1/sprint1-plan.md`: Formally records roles, information gaps G-01–G-09, engineering activities, schedule, and risk management.

#### B. Elicitation Plan, Evidence, & Synthesis (Rubric Sections 2 & 3)
* `doc/sprint1/elicitation-plan.md`: Outlines 3 planned elicitation techniques (ELIC-01 public feedback analysis, ELIC-02 analog transit system benchmarking, ELIC-03 operational staff walkthrough simulations), ethical safeguards, and information gaps.
* `doc/sprint1/elicitation-evidence.md`, `doc/sprint1/evidence/README.md`, and `doc/sprint1/evidence.md`: Rigorous evidence discipline strictly separating direct/documented facts (SYS-01–05), public feedback (PF-01–06), analogies, simulations (S-01–05), and assumptions across 1000+ lines of consolidated records.
* `doc/sprint1/elicitation-synthesis.md`: Analyzes thematic discoveries (T-01–07), conflicts (C-01–07), and requirements evolution, contextualizing how elicitation pruned an initial exploratory pool of 38 candidate statements into the 28 atomic requirements accepted into Baseline v1.0.

#### C. Revised Foundation Artifacts (Rubric Section 4.5 & Handout Section 14)
* Standardized names implemented under `doc/sprint1/`: `context.md`, `glossary.md`, `personas.md`, `stakeholders.md`, `vision-scope.md`.
* `glossary.md` incorporates statutory definitions for **IPC** and **AODA**.
* `stakeholders.md` formally incorporates **TTC IT Services** (STK-09), **Delivery Partner / Logistics Courier** (STK-07), and **Third-Party Payment Gateway Service** (STK-10).
* `context.md` embeds a readable, high-resolution vector architecture diagram (`models/Context_Model.drawio.png`) resolving Sprint 0 diagram readability concerns.

#### D. Requirements Baseline v1.0 (Rubric Section 4)
* `doc/sprint1/requirements-baseline-v1.md`: Exactly 28 atomic requirements structured across 5 specification tables:
  * Business Requirements (BR): 2 requirements (`BR-001`, `BR-002`)
  * Stakeholder Requirements (SR): 6 requirements (`SR-001`–`SR-006`)
  * Functional Requirements (FR): 15 requirements (`FR-001`–`FR-015`)
  * Quality & Security (QR): 3 requirements (`QR-001`–`QR-003`)
  * Constraints & Usability (CON): 2 requirements (`CON-001`, `CON-002`)
* Full Metadata Compliance (Rubric 4.3): Every requirement specification table includes explicit `ID`, `Typed ID`, `Title`, `Statement`, `Rationale`, `Source / Evidence`, `Priority`, `Confidence`, `Status` (`Accepted (Baseline v1.0)`), `Verification Idea`, and `GitHub Issue` link.
* Candidate Lifecycle Tracking (Rubric 4.4): Section 4.1 documents the disposition and rationale for deferred Sprint 0 items (R-022, R-023), corrected drafting errors (R-026, R-027), and newly added edge-case requirements (R-029, R-030).

#### E. Scenarios, User Stories, Use Cases, & Acceptance Criteria (Rubric Section 5)
* `doc/sprint1/scenarios-use-cases.md`:
  * 10 user stories (`US-01`–`US-10`) linked to baseline requirements.
  * 3 detailed operational use cases (`UC-01` passenger reporting, `UC-02` frontline intake & custody, `UC-03` claims verification & return) with extensive exception and alternative flows (phone triage, competing claim locks, police escalation, and courier settlement).
  * 10 structured Given/When/Then acceptance criteria (`AC-01`–`AC-10`) for automated and empirical verification.

#### F. Requirements Models (Rubric Section 6)
* `doc/sprint1/models/`:
  * `Context_Model.drawio.png`: Updated system boundary model with external actors and services.
  * `Domain_Model.drawio.png`: Requirements-level conceptual entity relationships.
  * `Behavioral_Model_Ownership_Verification.drawio.png`: State machine governing claim evaluation, telephone triage, and disputed locks.
  * `Behavioral_Model_Staff_Handling.drawio.png`: State machine governing physical custody transitions from vehicle recovery to disposal/police transfer.
  * `models/README.md`: 300+ line specification explaining model purpose, entity definitions, state transitions, discovered issues, and requirements linkages.

#### G. Bidirectional Traceability & GitHub Requirements Management (Rubric Section 7)
* `doc/sprint1/traceability.md`: Complete bidirectional traceability matrix linking backward to sources/goals and forward to stories, use cases, acceptance criteria, and repository issues.
* 100% GitHub Issue Coverage: All 28 baseline requirements have corresponding GitHub Issues with matching titles, statements, priorities, confidence, and metadata labels:
  * Preserved Sprint 0 Issues: #2, #3, #4, #5, #6, #7, #8, #9, #10, #11, #12, #13, #14, #15, #16
  * Sprint 1 Created Issues: #17, #18, #19, #20, #21, #22, #23, #24, #25, #26, #27, #28, #29

#### H. Requirements Quality Review (Rubric Section 8)
* `doc/sprint1/quality-review.md`: Formal peer inspection across 13 standardized quality dimensions conducted by real student team members (**Muhammad Sufyan** as Lead Reviewer, **Mohammad Zain Al Syed** and **Anirudh Sundar** as Peer Reviewers).
* Documents 8 significant findings (`QR-F01`–`QR-F08`), 2-person inspection allocations, and 8 accepted dispositions incorporating critical defect corrections.

#### I. Prototype Refinement (Rubric Section 9)
* `doc/sprint1/prototype/README.md`: Documents low-fidelity screen mockups, storyboards, and activity flows specifically illustrating the requirements changes discovered during elicitation (telephone triage queue, claim dispute lock banner, and courier settlement gate).

#### J. Governance, Decisions, Retrospective, & AI Transparency (Rubric Section 10)
* `doc/sprint1/decisions.md`: Dated architectural decisions `D-001` through `D-010` recording problem context, evaluated alternatives, engineering rationale, affected artifacts, and open consequences.
* `doc/sprint1/retrospective.md`: Comprehensive evaluation of Sprint 1 team practices, what worked well, what to adjust, and remaining uncertainties for Sprint 2.
* `doc/sprint1/ai-use.md`: Complete, transparent disclosure of AI assistance in accordance with course policy.

---

### 3. Verification & Cross-Document Consistency

All 28 requirements, identifiers, scenario names, model states, and issue references have been audited for strict cross-document consistency. There are zero dead links or contradictory assertions across the submission artifacts.

Reviewers: @asxter, @abdullah998020-gif — Please review and leave approval comments.
