# Sprint 1 Progress and Deliverables Audit

**Course:** EECS 4312 — Software Requirements Engineering  
**Project:** Public Transit Lost & Found System (Group 11)  
**Sprint:** Requirements Sprint 1 — Elicitation & Initial Requirements Baseline  
**Evaluation Standard:** Handout Sections 1–16 & Sprint 1 Marking Rubric (80 Marks / 5% Final Grade)  
**Last Updated:** October 25, 2026  

---

## 1. Executive Summary & Requirements Scope

### Requirements Count Analysis (Do we need 35–40?)
**No, 35–40 is not required.** The official handout (Section 6.2) and grading rubric (Criterion 4.1) state:
> *"The baseline should normally contain approximately 25–40 atomic requirements... These are guidelines rather than a reason to manufacture unnecessary requirements."*

Our Requirements Baseline v1.0 contains **exactly 28 atomic requirements**, perfectly satisfying every breakdown guideline:
- **Business Requirements (BR):** 2 (Guideline: 2–4)
- **Stakeholder Requirements (SR):** 6 (Guideline: 5–8)
- **Functional Requirements (FR):** 15 (Guideline: at least 15)
- **Quality & Security Requirements (QR):** 3 (Guideline: combined QR/CON at least 5)
- **Constraints & Usability (CON):** 2 (Guideline: combined QR/CON at least 5)
- **Total Atomic Requirements:** 28 (Within 25–40 range, zero artificial inflation)

---

## 2. Sprint 1 Progress by Handout Section

The table below maps our project progress strictly to each numbered section of `sprint1_handout.md`, cross-referenced with its corresponding rubric criteria and deliverable file paths.

| Handout Section | Section Name | Required Deliverables | Status | Deliverable File Location | Rubric Weight & Notes |
| :--- | :--- | :--- | :---: | :--- | :--- |
| **Section 1** | **Sprint 0 Continuity** | `sprint0-feedback.md` | ✅ Complete | `doc/sprint1/sprint0-feedback.md` | **2 marks** (Rubric 1.2). Explicitly addresses all 4 marker comments from Sprint 0 grading and Lab 6 defect corrections. |
| **Section 2** | **Sprint 1 Planning** | `sprint1-plan.md` | ✅ Complete | `doc/sprint1/sprint1-plan.md` | **2 marks** (Rubric 1.1). Records roles (Zain, Anirudh, Sufyan), gaps G-01–G-09, schedule, and risks. |
| **Section 3** | **Elicitation Plan** | `elicitation-plan.md` | ✅ Complete | `doc/sprint1/elicitation-plan.md` | **8 marks** (Rubric 2.1 & 2.2). Covers gaps G-01–G-09, 3 techniques (ELIC-01, ELIC-02, ELIC-03), ethics/privacy. |
| **Section 4** | **Elicitation Evidence & Synthesis** | `elicitation-evidence.md`<br>`elicitation-synthesis.md`<br>`evidence.md` | ✅ Complete | `doc/sprint1/elicitation-evidence.md`<br>`doc/sprint1/elicitation-synthesis.md`<br>`doc/sprint1/evidence.md` | **12 marks** (Rubric 3.1, 3.2, 3.3). Full evidence discipline separating direct, documented, analogy, simulation, and assumption. Consolidated evidence record (`evidence.md`, 1098 lines) committed by teammate. |
| **Section 5** | **Revised Foundation Artifacts** | Revised copies of:<br>- `glossary.md`<br>- `stakeholders.md`<br>- `context.md`<br>- `personas.md`<br>- `vision-scope.md` | ✅ Complete | `doc/sprint1/glossary.md`<br>`doc/sprint1/stakeholders.md`<br>`doc/sprint1/context.md`<br>`doc/sprint1/personas.md`<br>`doc/sprint1/vision-scope.md` | **2 marks** (Rubric 4.5). Revised foundation artifacts matching Handout Section 14 standard names. Directly resolves Sprint 0 feedback with IPC/AODA and external IT/Logistics/Payment stakeholders. |
| **Section 6** | **Requirements Baseline v1.0** | `requirements-baseline-v1.md` | 🔄 Action Needed | `doc/sprint1/requirements-baseline-v1.md` | **18 marks** (Rubric 4.1–4.4). 28 atomic requirements with 100% active GitHub issue links. **Action required per Rubric 4.3:** Add explicit `Rationale` and `Status` columns to table to guarantee 4/4 marks. |
| **Section 7** | **Scenarios, User Stories, Use Cases, & AC** | `scenarios-use-cases.md` | ✅ Complete | `doc/sprint1/scenarios-use-cases.md` | **10 marks** (Rubric 5.1, 5.2, 5.3). 10 user stories, 3 detailed use cases (UC-01, UC-02, UC-03) with rich exception flows, and 10 testable Given/When/Then ACs. |
| **Section 8** | **Requirements Models** | `models/README.md`<br>`Context_Model.drawio.png`<br>`Domain_Model.drawio.png`<br>`Behavioral_Model_Ownership_Verification.drawio.png`<br>`Behavioral_Model_Staff_Handling.drawio.png` | ✅ Complete | `doc/sprint1/models/` | **8 marks** (Rubric 6.1, 6.2, 6.3). Teammate committed all 4 high-resolution drawio models and comprehensive 300+ line `README.md` covering system boundary, domain entities, and behavioral states. |
| **Section 9** | **Traceability** | `traceability.md` | ✅ Complete | `doc/sprint1/traceability.md` | **4 marks** (Rubric 7.1). Bidirectional matrix tracing sources $\to$ requirements $\to$ user stories $\to$ use cases $\to$ AC $\to$ GitHub issues. Aligned to handout Section 14. |
| **Section 10** | **GitHub Issues & Project Tracking** | 28 GitHub Issues with metadata labels, Project board, and Baseline PR | ✅ Complete (Issues: 28/28)<br>🔄 PR at submission | GitHub Repo & Project #12 | **4 marks** (Rubric 7.2 & 7.3). All 28 requirements have live GitHub Issues with metadata labels (`#2`–`#29`). Project board updated. |
| **Section 11** | **Requirements Quality Review** | `quality-review.md` | 🔄 Action Needed | `doc/sprint1/quality-review.md` | **5 marks** (Rubric 8.1 & 8.2). Peer inspection using Lab 6 defect review, 13 quality dimensions, and disposition log. **Action required per Rubric 8.1:** Replace fictional persona names with actual 3 student team members. |
| **Section 12** | **Prototype Refinement** | `prototype/README.md`<br>Updated low-fi assets | ✅ Complete | `doc/sprint1/prototype/README.md` | **2 marks** (Rubric 9.1). Storyboards, activity diagram, and screen flows illustrating RE enhancements (phone triage, dispute lock, courier gate). Committed by Anirudh. |
| **Section 13** | **Decisions, Retrospective, & AI Use** | `decisions.md`<br>`retrospective.md`<br>`ai-use.md` | ✅ Complete | `doc/sprint1/decisions.md`<br>`doc/sprint1/retrospective.md`<br>`doc/sprint1/ai-use.md` | **2 marks** (Rubric 10.1). Dated decision records D-001–D-010 (resolves Sprint 0 comment), comprehensive retrospective, and AI declaration log. |
| **Section 14** | **Repository Structure & Integration** | Clean `doc/sprint1/` layout & Baseline PR | ✅ Complete<br>🔄 PR at submission | `doc/sprint1/` | **3 marks** (Rubric 8.3 & 11.1). Baseline PR ready for opening with reviewer approvals, no broken links, professional tone. |

---

## 3. Sprint 0 Marker Feedback Resolution Checklist

The marker comments in `feedback/Sprint0_grading.md` identified 4 specific issues that reduced our Sprint 0 score. Here is how each item is resolved in Sprint 1:

| # | Marker Feedback on Sprint 0 | Exact Problem | Planned Resolution in Sprint 1 | Affected Artifact(s) |
|---|---|---|---|---|
| **1** | *"context.md: The diagram must be readable without zooming excessively"* | Font size was small and diagram elements were crowded when embedded in Markdown. | Create `context-v2` with large, crisp typography, clean visual boundaries, and explicit external system interactions in `Sprint1/models/` and `Sprint1/context.md`. | `Sprint1/models/context-v2.*`<br>`Sprint1/context.md` |
| **2** | *"Glossary: Include IPC and AODA"* | Statutory and regulatory abbreviations were omitted from the domain glossary. | Add formal definitions for **IPC** (Information and Privacy Commissioner of Ontario, covering MFIPPA compliance) and **AODA** (Accessibility for Ontarians with Disabilities Act, covering web accessibility standards) to revised `Sprint1/glossary.md`. | `Sprint1/glossary.md` |
| **3** | *"requirement-backlog: Three sources are not stakeholders in stakeholders.md: 'TTC IT' (R-022 to R-024), 'Logistics Provider' (R-017) and 'Payment Service' (R-018)"* | Candidate requirements cited external systems/organizations that were not analyzed as stakeholders. | Update `Sprint1/stakeholders.md` to formally document **TTC IT Services**, **Third-Party Logistics Provider (Courier)**, and **PCI-DSS Payment Gateway Service** as external technical/operational stakeholders. | `Sprint1/stakeholders.md`<br>`Sprint1/requirements-baseline-v1.md` |
| **4** | *"decision.md: instead of sprint0, specify the date when each decision was made"* | Decision log records used generic sprint labels rather than calendar timestamps. | Record explicit ISO calendar dates (e.g., `2026-10-20`, `2026-10-22`, `2026-10-24`) for every architectural and requirement decision in `Sprint1/decisions.md`. | `Sprint1/decisions.md` |

---

## 4. GitHub Issue Migration Status (Section 10) — 100% COMPLETE

All 28 baseline requirements are now fully represented as distinct GitHub Issues with matching titles, statements, metadata, priorities, and labels:

- **Sprint 0 Preserved Issues (15 Issues):**
  - `#2` — `[R-001] Recovery Rate Measurement`
  - `#3` — `[R-002] Custody Audit Trail Verification`
  - `#4` — `[R-003] Flexible Lost-Item Reporting`
  - `#5` — `[R-004] Submission Reference Token`
  - `#6` — `[R-005] Self-Service Claim Status Inquiry`
  - `#7` — `[R-006] Frontline Found-Item Intake`
  - `#8` — `[R-007] Intermediate Custody Tracking`
  - `#9` — `[R-008] Candidate Match Ranking`
  - `#10` — `[R-009] Ownership Verification Decision Recording`
  - `#11` — `[R-010] Urgent Property Classification`
  - `#12` — `[R-013] Privacy-Bounded Public Browsing`
  - `#13` — `[R-014] Physical Storage Bin Assignment`
  - `#14` — `[R-016] Final Disposition and Police Escalation`
  - `#15` — `[R-019] Staff Audit Trail Logging`
  - `#16` — `[R-021] Role-Based Access Control`

- **Sprint 1 Newly Created Issues (13 Issues):**
  - ✅ `#17` — `[R-011] Expedited Verification Queue`
  - ✅ `#18` — `[R-012] High-Priority Staff Notification`
  - ✅ `#19` — `[R-015] Central Processing Delay Notice`
  - ✅ `#20` — `[R-017] Remote Courier Dispatch Record`
  - ✅ `#21` — `[R-018] Remote Delivery Fee Settlement Gate`
  - ✅ `#22` — `[R-020] Claimant PII Retention and Masking`
  - ✅ `#23` — `[R-024] Public Web Service Availability`
  - ✅ `#24` — `[R-025] Responsive Mobile Viewport Layout`
  - ✅ `#25` — `[R-026] Automated Claim Status Notifications`
  - ✅ `#26` — `[R-027] In-Person Pickup Receipt Acknowledgment`
  - ✅ `#27` — `[R-028] Public Catalog Search and Filter`
  - ✅ `#28` — `[R-029] Disputed Claim Lock Mechanism`
  - ✅ `#29` — `[R-030] Telephone Triage Follow-Up Management`

**Remaining Issues in Queue:** **0** (All 28 requirements active on GitHub and linked in `requirements-baseline-v1.md`).

---

## 5. Roadmap to 80 / 80 Marks

With all 28 requirements established, 100% of GitHub Issues created, and all team deliverables pulled and synchronized, the current status across all rubric sections is:
1. ✅ **All 28 GitHub Issues Created & Linked**: Requirements Baseline v1.0 table is 100% linked (`#2`–`#29`).
2. ✅ **Planning & Continuity (Sections 1 & 2)**: `sprint0-feedback.md` and `sprint1-plan.md` completed.
3. ✅ **Elicitation & Consolidated Evidence (Sections 3 & 4)**: `elicitation-plan.md`, `elicitation-evidence.md`, `elicitation-synthesis.md`, and `evidence.md` completed.
4. ✅ **Revised Foundations (Section 5)**: `context.md`, `glossary.md` (with IPC/AODA), `personas.md`, `stakeholders.md` (with TTC IT & Payment gateway), `vision-scope.md` committed.
5. 🔄 **Requirements Baseline v1.0 (Section 6)**: 28 atomic requirements with 100% issue links. Requires adding `Rationale` and `Status` columns per Rubric Criterion 4.3 before PR.
6. ✅ **Scenarios, Use Cases, & Acceptance Criteria (Section 7)**: 10 user stories, 3 detailed use cases (UC-01–03), 10 testable Given/When/Then ACs.
7. ✅ **Requirements Models (Section 8)**: 4 draw.io diagrams and comprehensive `models/README.md` in `doc/sprint1/models/`.
8. ✅ **Traceability Matrix (Section 9)**: `traceability.md` with bidirectional mapping from goals to issues.
9. 🔄 **Requirements Quality Review (Section 11)**: `quality-review.md` peer inspection records. Requires replacing fictional persona names with actual student team member names per Rubric Criterion 8.1 before PR.
10. ✅ **Prototype Refinement (Section 12)**: `prototype/README.md` with storyboards, activity diagrams, and screen flows.
11. ✅ **Decisions, Retrospective, & AI Use (Section 13)**: `decisions.md` (dated D-001–D-010), `retrospective.md`, and `ai-use.md` declaration log.
12. 🔄 **Final Submission PR (Section 14)**: Fix items 5 & 9 above, create the Baseline PR on GitHub with teammate review approvals, and submit.

---

## 6. Pre-PR Quality Audit & Action Items

A comprehensive cross-deliverable consistency audit conducted on October 25, 2026 revealed two specific items to address before opening the final Baseline v1.0 Pull Request:

### 1. Rubric 4.3 Metadata Gap in `requirements-baseline-v1.md`
- **Audit Finding:** Rubric Criterion 4.3 (*"Source, rationale, priority, confidence, and verification metadata — Max 4 marks"*) and Handout Section 6.4 explicitly require recording **Rationale** and **Current Status** (e.g., `Accepted (Baseline v1.0)`) for every baseline requirement.
- **Current State:** The table in `requirements-baseline-v1.md` currently includes `ID`, `Typed ID`, `Title`, `Statement`, `Source / Evidence`, `Priority`, `Confidence`, `Verification Idea`, and `GitHub Issue`, but omits explicit `Rationale` and `Status` columns (even though these exist in the individual GitHub Issues and `evidence.md`).
- **Required Action:** Add explicit `Rationale` and `Status` columns to each specification table in `doc/sprint1/requirements-baseline-v1.md`. This directly protects 4/4 marks under Rubric 4.3.

### 2. Rubric 8.1 Reviewer Names Discrepancy in `quality-review.md`
- **Audit Finding:** In `doc/sprint1/quality-review.md` (Section 2 and findings QR-F01–QR-F07), the reviewers are listed as *"Marcus Vance (MV), Elena Rostova (ER), Devon Brooks (DB), Priya Patel (PP)"*, and states *"All four Group 11 team members participated"*.
- **Contradiction:** Fictional persona names were used (e.g., Marcus Vance is Persona 4 in `personas.md`). Group 11 has exactly three student members: **Mohammad Zain Al Syed**, **Anirudh Sundar**, and **Muhammad Sufyan**. Rubric Criterion 8.1 requires that peer inspections reflect genuine evaluation by actual team members.
- **Required Action:** Update `doc/sprint1/quality-review.md` to list the 3 actual student team members and establish genuine 2-person inspection pairs (e.g., Zain inspecting intake/custody, Sufyan inspecting baseline/traceability, Anirudh inspecting verification/quality).

### 3. Contextualizing 38 Candidate Requirements in `evidence.md`
- **Audit Finding:** `evidence.md` (Section F) lists 38 draft candidate requirements explored during elicitation, whereas `requirements-baseline-v1.md` contains 28 accepted atomic requirements.
- **Assessment:** Not a contradiction—`evidence.md` clearly marks them as an unvalidated candidate pool. The Baseline PR summary should explicitly clarify that elicitation initially explored 38 candidate statements, which were consolidated and refined through quality inspection into the accepted 28 atomic requirements in Baseline v1.0.
