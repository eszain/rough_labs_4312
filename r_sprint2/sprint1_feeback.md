# Requirements Sprint 1 - Marking Scheme

**Course:** Software Requirements Engineering  
**Sprint:** Requirements Sprint 1 - Elicitation & Initial Requirements Baseline  
**Team Name:** Group 11 — Public Transit Lost-and-Found System  
**GitHub Repository:** https://github.com/EECS4312F26/eecs4312-project-group-11  

**Raw total:** 80 marks  
**Course weight:** 5% of final course grade  

**Deadline snapshot:** [`0a0670ceb507`](https://github.com/EECS4312F26/eecs4312-project-group-11/commit/0a0670ceb5078496f7edb94dcab1a42a55b083cf) — committed October 25, 2026 at **10:56 PM EDT** (October 26, 02:56:42 UTC). The cutoff was October 25, 11:59 PM EDT. Subsequent `main` commits after 02:56 UTC are excluded. The team’s [PR #30](https://github.com/EECS4312F26/eecs4312-project-group-11/pull/30) opened at 11:28 PM EDT and received teammate approval at 11:57 PM EDT, both before the cutoff.



## 1. Sprint Planning and Sprint 0 Feedback - Max 4 marks

### 1.1 Sprint 1 planning - Max 2
- **2** = `sprint1-plan.md` clearly records participants, sprint goal, information gaps, RE activities, responsibilities/review roles, risks, and internal planning; work is distributed meaningfully across the team.
- **1** = Plan exists but important activities, responsibilities, information gaps, or review roles are vague/incomplete.
- **0** = Missing or provides little useful evidence of RE planning.

**Mark:** **2 / 2**

**Marker rationale (1.1):** [sprint1-plan.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/sprint1-plan.md) names the three team members, gives a measurable baseline goal, records nine specific Sprint 0 information gaps (G-01–G-09), schedules milestones and named author/reviewer responsibilities, and includes concrete risks and mitigations. Work is meaningfully distributed.

### 1.2 Response to Sprint 0 feedback - Max 2
- **2** = Important feedback is explicitly addressed; actions and affected artifacts/Issues are identified; unresolved items are acknowledged rather than ignored.
- **1** = Feedback response exists but is partial, generic, or difficult to connect to actual revisions.
- **0** = Missing, or significant feedback is ignored without explanation.

**Mark:** **2 / 2**

**Marker rationale (1.2):** [sprint0-feedback.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/sprint0-feedback.md) responds item by item to the actual four Sprint 0 marker findings. The updated [context.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/context.md), [glossary.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/glossary.md), [stakeholders.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/stakeholders.md), and [decisions.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/decisions.md) show substantial corrections to diagram readability, IPC/AODA terminology, missing partner roles, and dated decisions. The same response also documents Lab 6 corrections; unvalidated new rules should nevertheless be treated as open.

**Section total:** **4 / 4**

---

## 2. Elicitation Plan - Max 8 marks

### 2.1 Objectives and information gaps - Max 4
- **4** = Plan identifies specific uncertainties, assumptions, conflicts, and information needs carried from Sprint 0; elicitation objectives clearly correspond to these gaps.
- **3** = Good objectives and gaps with minor omissions or weak linkage.
- **2** = General elicitation goals are present but are broad, feature-oriented, or only weakly tied to known uncertainties.
- **1** = Mostly a list of questions/activities with little explanation of what the team needs to learn.
- **0** = Missing or irrelevant.

**Mark:** **4 / 4**

**Marker rationale (2.1):** [elicitation-plan.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/elicitation-plan.md) connects nine specific gaps to the exact Sprint 0 statements and appropriate investigation questions, including unknown report fields, item-versus-report states, custody receipt, disputed ownership, variable retention rules, and unsupported numeric thresholds. It tests uncertain knowledge rather than merely listing features.

### 2.2 Technique selection, questions, limitations, and ethics - Max 4
- **4** = At least three planned activities use at least two suitable techniques; target roles/sources, questions/tasks, evidence type, bias/limitations, privacy/ethics, responsibility, and timing are well considered.
- **3** = Appropriate plan with small omissions or some weak justification.
- **2** = Techniques are plausible but planning is mechanical; limitations, evidence type, questions, or ethics are incomplete.
- **1** = Minimal plan or techniques poorly matched to the information need.
- **0** = Missing.

**Mark:** **4 / 4**

**Marker rationale (2.2):** The plan specifies three suitable activities—public qualitative feedback, official/existing-system document analysis, and simulated scenario walkthroughs—with detailed tasks, source boundaries, privacy/ethics safeguards, schedule, roles and limitations. It explicitly acknowledges that simulations are not transit-operator interviews.

**Section total:** **8 / 8**

---

## 3. Elicitation Evidence and Synthesis - Max 12 marks

### 3.1 Quality and breadth of elicitation evidence - Max 6
- **6** = At least three credible activities using at least two techniques are documented; at least one is grounded in observable/documented evidence; notes are specific enough to support requirements decisions; sources and limitations are clear.
- **5** = Strong evidence with minor gaps in documentation, breadth, or source clarity.
- **4** = Required activities are substantially present but one is shallow or weakly connected to project uncertainties.
- **3** = Evidence exists but is mostly generic, repetitive, or dominated by unsupported simulation/assumption.
- **2** = Very limited elicitation evidence or significant documentation gaps.
- **1** = Activity is claimed with little usable evidence.
- **0** = Missing or materially fabricated/unusable.

**Mark:** **6 / 6**

**Marker rationale (3.1):** [elicitation-evidence.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/elicitation-evidence.md) contains specific identifiable public discussion sources (PF-01–06), documented service information (SYS sources), and five hypothetical walkthrough scenarios S-01–05. Source dates/links, separate observations, interpretation and limitations provide a strong audit trail; the companion [evidence.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/evidence.md) adds extensive working evidence. No direct TTC stakeholder interviews were performed, and the team discloses this clearly.

### 3.2 Evidence vs. interpretation vs. assumption - Max 3
- **3** = Team consistently distinguishes direct/documented evidence, analogy, simulation, interpretation, and assumption; unsupported statements are not presented as stakeholder facts.
- **2** = Distinction is usually clear but several findings blur evidence and inference.
- **1** = Evidence categories are mentioned but applied inconsistently; assumptions frequently appear as facts.
- **0** = No meaningful evidence discipline.

**Mark:** **3 / 3**

**Marker rationale (3.2):** The evidence file consistently distinguishes documented public service information, anecdotal Reddit posts, analogies, hypothetical walkthroughs, internal comparison, and hypotheses. It avoids presenting public feedback as representative data or simulation as confirmed institutional policy. This is excellent provenance discipline; the later baseline does not always follow its stated confidence boundaries (addressed separately in Sections 3.3 and 4).

### 3.3 Synthesis and effect on requirements - Max 3
- **3** = Synthesis identifies themes, conflicts, contradictions, new needs, changed assumptions, requirement additions/changes/rejections, unresolved questions, and current confidence; it clearly shows how elicitation changed the project.
- **2** = Useful synthesis but some changes/conflicts/uncertainties are weakly analyzed.
- **1** = Mostly summarizes activities without deriving requirements insight.
- **0** = Missing or not meaningful.

**Mark:** **2 / 3**

**Marker rationale (3.3):** [elicitation-synthesis.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/elicitation-synthesis.md) develops coherent themes, separates physical custody from report/claim states, documents competing interests, and identifies corrected R-026/R-027 statements and new edge-case candidates R-029/R-030. **Deduction:** its own conclusion calls 24–48-hour intake timing and quantitative thresholds provisional, yet [requirements-baseline-v1.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/requirements-baseline-v1.md) accepts mandatory 24–48-hour (FR-008), 48-hour telephone wait (FR-015), and $1,000 police referral (FR-009). The synthesis is stronger than the changes ultimately accepted.

**Section total:** **11 / 12**

---

## 4. Requirements Baseline v1.0 - Max 18 marks

### 4.1 Coverage, scope, and requirement types - Max 4
- **4** = Baseline has an appropriate scope (normally 25-40 requirements) and meaningful coverage of business, stakeholder, functional/system, quality, and constraint concerns; no obvious inflation or major functional gap.
- **3** = Strong coverage with a few noticeable omissions, repetitions, or type problems.
- **2** = Baseline is usable but narrow, uneven, inflated, or missing important requirement categories.
- **1** = Major scope problems; many requirements are trivial, missing, or disconnected from stakeholder needs.
- **0** = Missing or unusable.

**Mark:** **4 / 4**

**Marker rationale (4.1):** The baseline has **28 accepted requirements**, correctly distributed 2 BR + 6 SR + 15 FR + 3 QR + 2 CON. It covers reporting, physical intake and custody, matching, verification, return, notifications, security and operational constraints without artificial padding. Scope is suitable for Sprint 1.

### 4.2 Quality of requirement statements - Max 6
- **6** = Requirements are consistently understandable, atomic, appropriately precise, feasible, non-contradictory, and verifiable for the current stage; solution/design bias is limited to genuine constraints; terminology is controlled.
- **5** = High-quality set with only a few minor defects.
- **4** = Generally usable but several requirements contain ambiguity, compound statements, vague terms, or premature design.
- **3** = Frequent quality defects substantially weaken the baseline.
- **2** = Majority of requirements require significant rewriting.
- **1** = Requirements show little understanding of specification quality.
- **0** = Missing or largely unusable.

**Mark:** **4 / 6**

**Marker rationale (4.2):** The majority of statements are clear and test-oriented, but there are significant defects. [Issue #14](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/14)/FR-009 embeds a mandatory **$1,000 police escalation** not established as TTC policy; FR-008 asserts a universal 24–48-hour transit interval although the evidence found service-dependent timings; FR-015 makes an **unverified 48-hour** telephone grace period mandatory. QR-002 combines PII retention/purging and payment-card masking in one statement; BR-001 combines lost-report and found-item data with their histories; FR-014 has an incompletely defined competing-claim trigger. These are mostly usable, not defect-free requirements.

### 4.3 Source, rationale, priority, confidence, and verification metadata - Max 4
- **4** = Required metadata is consistently present and meaningful; source/evidence and rationale support the requirement; priority and confidence are defensible; acceptance/verification notes are useful.
- **3** = Metadata is mostly complete with minor inconsistencies or shallow rationale.
- **2** = Significant metadata gaps or many generic rationales/priorities/confidence labels.
- **1** = Metadata is mostly missing or not useful.
- **0** = No meaningful metadata.

**Mark:** **2 / 4**

**Marker rationale (4.3):** [requirements-baseline-v1.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/requirements-baseline-v1.md) does provide ID, type, statement, rationale, origin, priority, confidence, status, verification idea and Issue URL for all 28 rows. However, **High** confidence is assigned to many procedures supported primarily by scenarios, team decisions or analogies (e.g. FR-009 $1,000, FR-008 24–48 hours, FR-014 dispute handling). Several verification ideas enforce arbitrary precise numbers (10-character token, HTTP 403, 320-pixel viewport) or implementation details instead of independently established policy and measurable outcome. The metadata is complete structurally but confidence and evidence reliability are not consistently defensible.

### 4.4 Requirement lifecycle integrity - Max 2
- **2** = Rejected, split, merged, and replaced candidates remain traceable; status/rationale is documented; identifiers are stable and not silently reused.
- **1** = Some history is preserved but important changes are difficult to reconstruct.
- **0** = Requirements are deleted/replaced without meaningful history, or identifiers are unreliable.

**Mark:** **2 / 2**

**Marker rationale (4.4):** [requirements-baseline-v1.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/requirements-baseline-v1.md) Section 4.1 explicitly records the historical R-series candidate dispositions, corrected duplicate/mis-titled requirements (R-026/027), new requirements R-029/030, and deferred R-022/023. Legacy IDs and typed IDs are shown together rather than silently reused. The GitHub labels have not been synchronized with these decisions (graded in 7.2).

### 4.5 Consistency with revised foundation artifacts - Max 2
- **2** = Vision/scope, stakeholders, context, glossary/personas where relevant are reviewed/revised and are consistent with Baseline v1.0.
- **1** = Mostly consistent with a few outdated or contradictory elements.
- **0** = Major contradictions remain or foundational artifacts were not meaningfully reviewed.

**Mark:** **1 / 2**

**Marker rationale (4.5):** The Sprint 1 versions of [vision-scope.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/vision-scope.md), [stakeholders.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/stakeholders.md), [glossary.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/glossary.md), [personas.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/personas.md), and [context.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/context.md) are substantive and resolve key Sprint 0 feedback. **Deduction:** the foundation/evidence still cautions that timing, police escalation and verification thresholds need authoritative confirmation, while the accepted baseline treats several as fixed obligations. This is an important cross-artifact confidence inconsistency.

**Section total:** **13 / 18**

---

## 5. Scenarios, User Stories, Use Cases, and Acceptance Criteria - Max 10 marks

### 5.1 User stories and linkage - Max 2
- **2** = Approximately 8-12 relevant user stories use a consistent form, express meaningful user value, and link to baseline requirements.
- **1** = Stories are present but several are generic, malformed, feature-only, or weakly linked.
- **0** = Missing or not useful.

**Mark:** **2 / 2**

**Marker rationale (5.1):** [scenarios-use-cases.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/scenarios-use-cases.md) contains 10 relevant user-value stories linked to typed IDs and historical requirement IDs. They cover passenger, operator, station staff, claims staff and privacy officer roles and distinguish reporting, custody, ownership, retrieval and data protection.

### 5.2 Detailed use cases/scenarios - Max 4
- **4** = At least three strong use cases/scenarios cover at least two stakeholder roles and include clear goals, conditions, main flow, alternatives/exceptions, postconditions, and requirement links; non-happy paths reveal useful requirements detail.
- **3** = Good scenarios/use cases with minor omissions or weak exception handling.
- **2** = Basic flows exist but are shallow, inconsistent, or insufficiently connected to requirements.
- **1** = Mostly UI steps or informal narratives with little requirements value.
- **0** = Missing.

**Mark:** **4 / 4**

**Marker rationale (5.2):** Three substantial multi-actor use cases (UC-01 report/tracking, UC-02 recovered-item intake/handover, UC-03 ownership and return) specify goals, conditions, main steps, alternative/exception paths, postconditions and requirement links. Dispute handling, pending telephone verification, courier settlement and custody acknowledgment are treated as meaningful non-happy-path behaviors.

### 5.3 Acceptance criteria - Max 4
- **4** = At least 10 high-priority stories/functional requirements have clear, observable, testable acceptance criteria; criteria clarify behavior and important boundary/exception conditions.
- **3** = Criteria are generally testable with a few vague, incomplete, or repetitive cases.
- **2** = Several criteria merely restate the requirement or omit important conditions.
- **1** = Very few usable acceptance criteria.
- **0** = Missing.

**Mark:** **3 / 4**

**Marker rationale (5.3):** Ten identified Given/When/Then criteria address important report, custody, match, authorization, escalation, payment, masking and disputed-claim conditions. **Deduction:** only a portion of the 15 functional requirements have their own ACs; some ACs encode unsupported policy/numeric choices (e.g. $1,000 police referral), and key behavior such as FR-015 telephone triage and notification timeliness lacks a dedicated boundary-condition test.

**Section total:** **9 / 10**

---

## 6. Requirements Models - Max 8 marks

### 6.1 Domain/conceptual model - Max 3
- **3** = Model accurately captures important domain concepts/relationships, uses appropriate requirements-level abstraction, agrees with terminology, and helps clarify one or more requirements questions.
- **2** = Mostly useful/correct but contains some omissions, unclear relationships, or minor design leakage.
- **1** = Model exists but is superficial, software-design oriented, or inconsistent with requirements.
- **0** = Missing/unreadable.

**Mark:** **3 / 3**

**Marker rationale (6.1):** [Domain_Model.drawio.png](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/models/Domain_Model.drawio.png) is a substantive and readable requirements-level model, distinguishing Claimant, Lost-Item Report, Candidate Match, Found Item, Ownership Claim, Evidence, Verification Decision, Custody Transfer, Return Arrangement and Final Disposition. Multiplicities and links support discussion of important ownership/custody concepts.

### 6.2 Behavioral model - Max 3
- **3** = Appropriate behavioral representation clearly captures important states/events/flows/interactions and is linked to requirements/scenarios; model exposes or resolves useful requirements detail.
- **2** = Generally correct/useful with minor omissions or weak linkage.
- **1** = Superficial, confusing, design-heavy, or adds little information beyond the text.
- **0** = Missing/unreadable.

**Mark:** **3 / 3**

**Marker rationale (6.2):** Both [Behavioral_Model_Ownership_Verification.drawio.png](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/models/Behavioral_Model_Ownership_Verification.drawio.png) and [Behavioral_Model_Staff_Handling.drawio.png](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/models/Behavioral_Model_Staff_Handling.drawio.png) are substantive state diagrams with explicit transitions, disputed/pending verification, approval, handoff and disposition outcomes. The representation correctly separates verified ownership from physical return. One diagram labels a UC-04 from earlier materials rather than the three Sprint 1 UCs; that presentation detail does not outweigh the substantive modeling value.

### 6.3 Context update and model rationale/consistency - Max 2
- **2** = Context model is appropriately revised or confirmed; `models/README.md` explains purpose, links, learning, and discovered issues; models are mutually consistent with the baseline.
- **1** = Models are mostly consistent but rationale, context revision, or cross-model consistency is incomplete.
- **0** = Major contradictions or no explanation of model purpose.

**Mark:** **2 / 2**

**Marker rationale (6.3):** [Context_Model.drawio.png](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/models/Context_Model.drawio.png) clearly revises the system boundary and relevant external actors, and [README.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/models/README.md) links model purposes, questions and rationale across the four views. Some diagram annotations and policy assumptions still need confirmation, but the modeling package is internally coherent and professionally documented.

**Section total:** **8 / 8**

---

## 7. Traceability and GitHub Requirements Management - Max 8 marks

### 7.1 Traceability coverage and usefulness - Max 4
- **4** = Every baseline requirement traces backward to a meaningful origin; high-priority functional requirements trace forward to scenarios/use cases and acceptance criteria; links help answer why/who/how-to-verify questions.
- **3** = Strong traceability with a few gaps or weak links.
- **2** = Matrix/links exist but coverage is incomplete or many links are mechanical/uninformative.
- **1** = Minimal traceability that cannot support reasoning about the baseline.
- **0** = Missing.

**Mark:** **3 / 4**

**Marker rationale (7.1):** [traceability.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/traceability.md) provides a row for each of the 28 requirements, with evidence, goals, relevant stories/UCs, verification ideas, and live Issue URLs. **Deduction:** several high-priority functions have only generic verification ideas rather than standalone AC IDs, and traces repeat unvalidated numeric assumptions (e.g. disputed match similarity >80% described in the trace narrative without corresponding accepted specification). The matrix is useful but not uniformly credible as a verification chain.

### 7.2 GitHub Issues, labels, statuses, and Project state - Max 3
- **3** = Every baseline requirement has a matching Issue; IDs/statements/metadata are consistent; baseline/confidence/evidence/status labels are used sensibly; Project board reflects actual state; rejected/candidate items remain visible.
- **2** = Mostly correct tracking with several missing/inconsistent Issues, labels, statuses, or Project-board entries.
- **1** = GitHub is used mainly as storage; requirements state is difficult to determine.
- **0** = Requirements are not meaningfully managed in GitHub.

**Mark:** **1 / 3**

**Marker rationale (7.2):** There are 28 corresponding GitHub Issues, but **all 15 legacy Issue records [Issue #2](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/2)–[Issue #16](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/16) still have `status:candidate` at inspection**, while the submitted baseline declares the same requirements **Accepted**. The 13 newer Issues [Issue #17](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17)–[Issue #29](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/29) are labeled `status:accepted` but lack consistent `baseline:v1`, evidence, confidence and verification labels. The submitted PR claims 100% synchronization, which is incorrect. The Project board state was not independently accessible; no additional automatic deduction is made solely for that limitation.

### 7.3 Identifiers and cross-links - Max 1
- **1** = Stable IDs and links among baseline, Issues, scenarios/models, and traceability artifacts work consistently.
- **0** = Broken/inconsistent identifiers or links materially hinder marking.

**Mark:** **1 / 1**

**Marker rationale (7.3):** The typed IDs, corresponding R-series IDs, traceability rows, story/AC references and Issue links are present and mostly navigable, notwithstanding the substantive Issue-status problems and a few inconsistent UC/model annotations. Marking can follow the links reliably; Issue lifecycle **content** errors are scored under 7.2.

**Section total:** **5 / 8**

---

## 8. Requirements Quality Review and Pull Request - Max 6 marks

### 8.1 Review completeness and quality - Max 3
- **3** = Baseline receives systematic review for ambiguity, atomicity, consistency, feasibility, verifiability, source/rationale, duplication, scope, and related defects; at least two team members participate meaningfully.
- **2** = Review is useful but uneven, narrow, or incompletely documented.
- **1** = Review is largely superficial/checklist-only or covers only a small subset without justification.
- **0** = Missing.

**Mark:** **3 / 3**

**Marker rationale (8.1):** [quality-review.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/quality-review.md) names three participants and cross-review allocations, enumerates 13 quality dimensions, documents inspection of all 28 requirements by type and eight concrete findings (QR-F01–F08). The review is far more detailed than a sign-off-only checklist, though some of its conclusions require further verification.

### 8.2 Findings, disposition, and corrections - Max 2
- **2** = Significant findings are recorded, dispositioned, and linked to actual corrections/deferred questions; team does not manufacture findings merely to increase count.
- **1** = Findings exist but resolution/rationale is incomplete or difficult to verify.
- **0** = No meaningful defect disposition.

**Mark:** **1 / 2**

**Marker rationale (8.2):** Eight findings include severity, reviewers, proposed corrections and dispositions, and many corrections are visible in the baseline (R-026/027 fixes, R-029/030 additions). **Deduction:** critical unverified rules remain accepted despite their own elicitation caveats (24–48h intake, 48h triage, $1,000 police handoff); the review cites an unsupported "over 40%" vague-report rate and claims that all defects were resolved. The disposition/verification record overstates completed validation.

### 8.3 Baseline pull-request review - Max 1
- **1** = A meaningful Sprint 1 baseline PR summarizes changes, references relevant Issues, receives teammate review, and resolves comments appropriately.
- **0** = Required PR/review evidence is missing or purely ceremonial.

**Mark:** **0 / 1**

**Marker rationale (8.3):** [PR #30](https://github.com/EECS4312F26/eecs4312-project-group-11/pull/30) was opened October 25 at **11:28 PM EDT** and approved by a teammate at **11:57 PM EDT**, before the deadline; the PR summary is detailed and links to Issues. However, the teammate comments merely say the documents are consistent and "approved"; GitHub contains **no substantive review finding, inline correction, or resolution thread on that PR**, and the PR remained open. Under the same rubric standard applied to earlier groups, formal approval without meaningful review is ceremonial, so this specific point is not awarded. The separate internal review receives credit under 8.1/8.2.

**Section total:** **4 / 6**

---

## 9. Prototype Refinement - Max 2 marks

### 9.1 Requirements/elicitation value - Max 2
- **2** = Prototype is appropriately updated and clearly linked to important scenarios/requirements; README explains changes, elicitation questions, learning, and remaining assumptions; visual polish is not substituted for RE reasoning.
- **1** = Prototype is relevant but learning/questions/links are weak or poorly documented.
- **0** = Missing, unrelated, or presented mainly as implementation progress.

**Mark:** **2 / 2**

**Marker rationale (9.1):** [README.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/prototype/README.md) describes relevant passenger and staff low-fidelity screens, an activity flow, several scenarios, the Sprint 0–1 change to incomplete/contested verification, open research questions, and assumptions about reporting, triage and return. Images are linked through GitHub attachments in the README rather than saved as separate files in `prototype/`, but the artifact descriptions and changes are sufficiently useful for requirements elicitation.

**Section total:** **2 / 2**

---

## 10. Decisions, Retrospective, and AI Transparency - Max 2 marks

### 10.1 Process learning and transparency - Max 2
- **2** = Decision log records meaningful Sprint 1 decisions/rationale; retrospective identifies concrete practices to continue/change and unresolved uncertainty; AI-use log is complete or explicitly states no use.
- **1** = Required records exist but are shallow, incomplete, or weakly connected to project evolution.
- **0** = Missing or materially inadequate.

**Mark:** **2 / 2**

**Marker rationale (10.1):** [decisions.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/decisions.md) has ten dated, reasoned decisions with alternatives and open consequences; [retrospective.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/retrospective.md) identifies useful practices, inaccurate public-feedback generalizations, unresolved liability and concrete workflow changes; [ai-use.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/ai-use.md) discloses several AI tools, purposes, prompts, checking and corrections. The process record meets the rubric despite a few overstrong cross-document completion claims.

**Section total:** **2 / 2**

---

## 11. Overall Coherence and Professional Communication - Max 2 marks

### 11.1 Integrated quality - Max 2
- **2** = Submission reads as one coherent requirements baseline; terminology, IDs, scenarios, models, Issues, and traceability agree; diagrams are readable; links work; documentation is concise and professional.
- **1** = Generally understandable but contains noticeable contradictions, duplicated/outdated content, broken links, or presentation problems.
- **0** = Difficult to evaluate because artifacts are inconsistent, inaccessible, or substantially disorganized.

**Mark:** **1 / 2**

**Marker rationale (11.1):** The package is polished, professionally formatted, and easy to navigate. However, the repository does not support its strong assertion of "zero contradictory assertions": **15 Issue statuses conflict with the accepted baseline**, several supposedly verified operational thresholds are unsupported, and the ownership diagram refers to UC-04 rather than the three documented Sprint 1 use cases. These substantial consistency issues prevent full integrated-quality credit.

**Section total:** **1 / 2**

---

# Total Mark

| Section | Max | Mark |
|---|---:|---:|
| 1. Sprint Planning and Sprint 0 Feedback | 4 | **4** |
| 2. Elicitation Plan | 8 | **8** |
| 3. Elicitation Evidence and Synthesis | 12 | **11** |
| 4. Requirements Baseline v1.0 | 18 | **13** |
| 5. Scenarios / Stories / Use Cases / Acceptance Criteria | 10 | **9** |
| 6. Requirements Models | 8 | **8** |
| 7. Traceability and GitHub Requirements Management | 8 | **5** |
| 8. Requirements Quality Review and Pull Request | 6 | **4** |
| 9. Prototype Refinement | 2 | **2** |
| 10. Decisions, Retrospective, and AI Transparency | 2 | **2** |
| 11. Overall Coherence and Professional Communication | 2 | **1** |
| **TOTAL** | **80** | **67 / 80** |

**Scaled course contribution:** **4.1875 / 5%** (Sprint 1 mark: **83.75%**)

---

## Marker comments

**Strongest aspects of this baseline:**

- Exceptionally disciplined elicitation: public user anecdotes, official agency procedures, analogies, internal comparisons, and hypothetical workflow evidence are explicitly separated in [elicitation-evidence.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/elicitation-evidence.md).
- Twenty-eight comprehensively documented baseline requirements; 10 user stories, 3 detailed use cases, 10 identified acceptance criteria; useful lifecycle disposition of renamed/deferred/new requirements.
- Four substantive and readable domain, context, and state models, clearly distinguishing candidate matches, ownership decisions, physical custody, and completed return.
- Thorough Sprint 0 feedback response, dated decision log, introspective retrospective and declared AI assistance.
- Real before-deadline baseline PR with a teammate approval, though its review narrative is too generic to earn point 8.3.



**Highest-priority corrections before Sprint 2:**

1. **Reconcile GitHub requirement management:** update legacy [Issue #2](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/2)–[Issue #16](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/16) from candidate to accepted where appropriate, retain any actual rejections as candidates/rejected, and apply consistent baseline/confidence/evidence labels and meaningful Project states. Recheck each link from the 28 baseline entries.
2. **Remove or explicitly provisionally label unsupported operating rules** in FR-008 (24–48-hour general transfer), FR-009 ($1,000 police transfer), FR-015 (48-hour telephone triage). Seek actual transit-operator or verified policy evidence for each; distinguish a test scenario number from an established policy threshold.
3. Split compound QR-002 into distinguishable retention and payment-card-sanitization requirements and define actual approved retention periods, evidence standards and lawful disclosure restrictions.
4. Close the conflict between the baseline's high-confidence/status claims and [elicitation-synthesis.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/elicitation-synthesis.md)'s explicit warnings about unverified policy and source applicability.
5. Align all ten ACs with applicable high-priority requirements and add testable negative/exception criteria for triage, courier failure, retention, competing ownership and claimant communications.
6. Make substantive **inline or top-level baseline PR findings** with links to revised files and a disposition trail; a generic 'approved' comment is not an evidence-bearing requirements review.



**Requirements or assumptions that particularly need validation/refinement:**

- FR-009 / AC-07: whether the transit operator actually mandates police transfer at $1,000; who assesses value and what proof of transfer is required. The team's cited sources do **not** establish this as an adopted TTC policy.
- FR-015: whether 48 hours is an approved phone-triage window and whether rejection is automatically permissible when no reply arrives; protect against inaccessible phone contact and competing claims.
- FR-008: separate documented Wheel-Trans-specific or general receipt timelines from universal TTC notices; avoid stating a fixed interval without service-specific evidence.
- FR-014 / AC-10: how two plausible claims are linked, whether any match percentage alone triggers a lock, and the exact supervisory resolution and audit policy.
- QR-002: jurisdiction-specific retention/disposal obligations and protection of payment-card data; do not equate a general privacy statute with a verified precise implementation prescription.
- BR-001 / SR-004: what a 'complete' state/transfer history means when a physical handoff has not yet been acknowledged.
- CON-002: mobile 320-pixel width is a responsive-layout test but is **not sufficient by itself** to demonstrate full AODA accessibility compliance.



**GitHub / traceability / review issues to correct:**

- **Critical mismatch:** all 15 historical Issues [Issue #2](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/2)–[Issue #16](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/16) show `status:candidate`, despite those requirements being declared accepted in [requirements-baseline-v1.md](https://github.com/EECS4312F26/eecs4312-project-group-11/blob/0a0670ceb5078496f7edb94dcab1a42a55b083cf/doc/sprint1/requirements-baseline-v1.md). New Issues [Issue #17](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17)–[Issue #29](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/29) show accepted status, but lack many confidence/evidence/baseline labels. This contradicts the PR's 100%-synchronized claim.
- [PR #30](https://github.com/EECS4312F26/eecs4312-project-group-11/pull/30): PR opened before deadline and approved two minutes before the cutoff, but **no substantive defect discussion, inline comments or change-resolution record** appears on the PR. The PR remained open. Internal findings in `quality-review.md` were evaluated separately; **8.3 = 0/1**.
- Remove unsupported '>80% similar' trigger from traceability unless it is explicitly identified as a *candidate test heuristic*; the submitted FR-014 is about competing unresolved claims, not a proven score cutoff.
- The ownership-verification state diagram displays a **UC-04** label from earlier material, while the Sprint 1 use-case document contains UC-01 through UC-03. Reconcile the label and check model links.
- Add named ACs or explicit verification tests for high-priority requirements currently supported only by prose verification notes.
