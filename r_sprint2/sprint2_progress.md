# Sprint 2 Progress Tracker: Group 11

Due: Sunday November 8, 2026, 11:59 PM. Evaluated against handout section 14 required files and rubric criteria as of latest repository pull (commit 578872f).

Legend: [x] completed / ready · [~] substantial draft with open gaps · [ ] missing / not started

## 1. File status (Handout Section 14)

| Required file | Rubric Section (marks) | Status | Notes |
|---|---|---|---|
| sprint1-feedback.md | 1.1 (3) | [~] | Feedback table is good. Missing: explicit links to Issues/commits/PRs, unresolved feedback section with justifications, and confirmation of assessed v1.0 tag. |
| sprint2-plan.md | 1.2 (3) | [ ] | Not started. Needs participants, sprint goal, analysis questions, per-member RE responsibilities, internal deadlines, and risks. |
| goals.md | 2.1, 2.3 (11) | [x] | Updated with KAOS goal model description and embedded diagram link. Comprehensive G-10 to G-40 breakdown with AND/OR refinements, gaps, and requirement links. |
| models/goal-model.[src+export] | 2.2 (5) | [~] | Goal-Model.png (1 MB) is present in models/ and embedded in goals.md. Export image is available; editable source file (.drawio or .puml) is recommended to fulfill [src+export]. |
| obstacles-conflicts.md | 3 (10) | [x] | Complete. Covers O-01 to O-05, C-01 to C-05 (including C-03 filling the earlier numbering gap), and CH-01 to CH-09. |
| quality-requirements.md | 4 (20) | [~] | QR-001 and QR-003 to QR-013 documented in full format with trade-offs. QR-014 to QR-016 exist in baseline-v2 section 3 and need merging into this catalogue to complete the set. |
| prioritization.md | 5 (14) | [x] | Complete. Stage A MoSCoW (39 requirements), Stage B 5-factor weighted scoring for 20 requirements, pairwise weights, sensitivity analysis, dependency cross-check, and final Priority Set. |
| negotiation.md | 6 (12) | [x] | Complete and ready. 5 issues (C-01 to C-05) analyzed with simulated stakeholder positions. Section 8 team review table filled with reviewer names, agreed decisions, and settled numbers (5-day response, 3-day dispute review, 90-day retention, 15-minute lockout). Zero provisional assumptions remaining. |
| dependencies.md | 7 (8) | [x] | Complete and ready. 117 links, 6 relation types, full matrix with source markers, hubs, chains, and 5 cycle break resolutions (DD-01 to DD-05). |
| models/requirements-dependency.[src+export] | 7.1 | [x] | Complete and ready. Both requirements-dependency.puml source and requirements-dependency.svg export are present in models/. |
| requirements-baseline-v2.md | 8.1 (4) | [~] | Contains 37 selected requirements + 2 deferred. Updated with negotiation and dependency fixes. Still drafted as a proposed set pending team acceptance status and live GitHub Issue links. |
| baseline-change-summary.md | 8.1 | [~] | Exists as baseline-change.md (renamed in commit 248718c). Handout requires baseline-change-summary.md and prioritization.md links to that name; filename needs reconciliation. |
| traceability.md | 8.2 (3) | [ ] | Not started. Needs forward and backward traceability chain (evidence to goal to requirement to QR to scenario to fit criterion to Issue) with negotiation and conflict references. |
| decisions.md | 13.1 | [~] | Decision log created with 10 formal entries: ND-01 to ND-05 (negotiation) and DD-01 to DD-05 (dependencies). Earlier decisions (goal refinements, quality thresholds, prioritization weights) still to be added per handout section 13.1. |
| retrospective.md | 9.1 (2) | [ ] | Not started. Needs participants, RE practices review, Sprint 3 improvements, trade-offs, least confident area, and most change-vulnerable area. |
| ai-use.md | 9.2 (2) | [~] | File exists but contains only a title heading. Needs entries documenting tool use, prompts, and verification across Sprint 2 deliverables. |
| github-sprint2-setup.md | 8.3 (3) | [ ] | Not started. Awaits live GitHub Issue updates, labels, project board fields, reviewed PR, and v2.0 tag. |
| prototype/README.md | 12 | [ ] | Handout section 14 requires a prototype README note (a short note stating no prototype changes in Sprint 2 is acceptable). |

## 2. Marks breakdown and current standing

* Total raw marks: 100 (scaled to 8% of course grade).
* Marks currently secure or substantially ready: approximately 60 / 100 (Goals, Obstacles/Conflicts, Prioritization, Negotiation, Dependencies).
* Marks currently missing or incomplete: approximately 40 / 100 (Planning, Quality catalogue consolidation, Traceability, Baseline finalization, Retrospective, AI use, GitHub setup).

## 3. Work remaining in priority order (marks at risk)

1. sprint2-plan.md (3 marks, Rubric 1.2):
   Create doc/sprint2/sprint2-plan.md covering sprint goal, participants, analysis questions, per-member RE responsibilities, internal deadlines, and risks.

2. traceability.md (3 marks, Rubric 8.2):
   Create doc/sprint2/traceability.md linking evidence, goals, requirements, quality constraints, scenarios, fit criteria, and Issues.

3. Merge QR-014 to QR-016 into quality-requirements.md (Rubric 4, 20 marks section):
   Move the full quality scenarios for QR-014, QR-015, and QR-016 from requirements-baseline-v2.md into quality-requirements.md so the quality catalogue is complete.

4. retrospective.md (2 marks, Rubric 9.1):
   Create doc/sprint2/retrospective.md answering the 7 required reflection prompts from handout section 13.2, including least-confident area and most change-vulnerable requirement.

5. ai-use.md (2 marks, Rubric 9.2):
   Document AI assistance for dependency modeling, negotiation simulation, and artifact drafting in doc/sprint2/ai-use.md.

6. Reconcile baseline-change-summary.md and requirements-baseline-v2.md (Rubric 8.1):
   Rename baseline-change.md to baseline-change-summary.md (or update internal links), update baseline-v2 status from draft to accepted, and add decisions.md references.

7. sprint1-feedback.md updates (Rubric 1.1):
   Add links to concrete Issues and commits, and complete the section explaining unresolved feedback items with rationale.

8. prototype/README.md (Handout Section 12):
   Create prototype/README.md with a brief note confirming the Sprint 2 prototype status.

9. Live GitHub repository integration (3 marks, Rubric 8.3):
   Update Issues #2 to #29 and add new Issues for added requirements, configure labels and Project board, create the baseline v2.0 PR with substantive teammate review, merge, tag requirements-baseline-v2.0, and record evidence in github-sprint2-setup.md.

## 4. Three-person workload division and assigned responsibilities

This division assigns primary authoring and cross-review duties across the three group members to ensure even workload distribution and fulfill Rubric Section 1.2.

### Member 1: Mohammad Zain Al Syed (eszain)
* Primary author responsibilities:
  1. sprint2-plan.md (Rubric 1.2, 3 marks): Author the sprint planning document with sprint goals, participants, analytical RE questions, schedule, member workload breakdown, and risk mitigations.
  2. sprint1-feedback.md (Rubric 1.1, 3 marks): Add explicit links to GitHub Issues, commits, and PRs, author the unresolved feedback section with technical justifications, and verify the v1.0 tag reference.
  3. retrospective.md (Rubric 9.1, 2 marks): Complete the 7 required retrospective sections from handout 13.2, documenting what worked, Sprint 3 improvements, major trade-offs, the least-confident requirement area, and the area most vulnerable to change.
  4. ai-use.md (Rubric 9.2, 2 marks): Expand the AI disclosure log with specific entries for tools, prompts, outputs, and verification across Sprint 2 modeling, negotiation, and documentation.
* Peer review responsibilities:
  * Review traceability.md authored by Anirudh.
  * Review quality-requirements.md additions authored by Sufyan.

### Member 2: Muhammad Sufyan (abdullah998020-gif)
* Primary author responsibilities:
  1. requirements-baseline-v2.md & baseline-change-summary.md (Rubric 8.1, 4 marks): Rename baseline-change.md to baseline-change-summary.md, update baseline v2.0 status from draft to accepted, verify requirement counts, and align cross-file markdown links.
  2. quality-requirements.md consolidation (Rubric 4, 20 marks): Migrate the complete quality scenarios for QR-014 (optional contact), QR-015 (misuse resistance), and QR-016 (minimal evidence) from baseline-v2 into the main quality catalogue, ensuring all 15 QRs are represented.
  3. prototype/README.md (Handout Section 12): Write the required prototype directory note documenting the Sprint 2 verification approach and confirming no code changes were needed for this phase.
* Peer review responsibilities:
  * Review sprint2-plan.md and retrospective.md authored by Zain.
  * Review traceability.md and decisions.md authored by Anirudh.

### Member 3: Anirudh Sundar (asxter)
* Primary author responsibilities:
  1. traceability.md (Rubric 8.2, 3 marks): Construct the complete forward and backward traceability matrix connecting evidence to goals, requirements, quality attributes, scenarios, fit criteria, and GitHub Issues, including references to conflicts and negotiation decisions.
  2. decisions.md expansion (Handout Section 13.1): Add the earlier Sprint 2 decisions (goal refinements, quality thresholds, prioritization weights) alongside the existing ND-01 to ND-05 and DD-01 to DD-05 entries.
  3. Goal model source file preservation (Rubric 2.2): Save and commit the editable source file (.drawio or .puml) for Goal-Model.png into doc/sprint2/models/.
  4. GitHub repository management and github-sprint2-setup.md (Rubric 8.3, 3 marks): Synchronize live Issues #2 to #29 and create new Issues, apply labels and Project board fields, create the baseline v2.0 PR, conduct genuine teammate reviews, merge into main, apply the requirements-baseline-v2.0 git tag, and author the setup evidence document.
* Peer review responsibilities:
  * Review sprint1-feedback.md and ai-use.md authored by Zain.
  * Review requirements-baseline-v2.md and quality-requirements.md authored by Sufyan.

## 5. Cross-artifact consistency checklist

* Baseline naming: baseline-change.md vs required baseline-change-summary.md.
* Quality ID alignment: quality-requirements.md has 12 QRs (001, 003 to 013), whereas baseline v2.0 lists 15 (001, 003 to 016).
* Goal model diagram: Goal-Model.png is committed in models/ and embedded in goals.md; save the source file (.drawio or .puml) alongside it if possible.
* Negotiation and dependencies numbers: The settled values (5-day response, 3-day supervisor review, 90-day dispute retention, 15-minute rolling lockout) in negotiation.md match decisions.md and baseline v2.0.
* Requirement counts: 37 selected requirements + 2 deferred (FR-010, FR-011) = 39 total active requirements across baseline v2.0, change summary, and prioritization.md.

## 6. Sprint 2 deliverables checklist (Handout Section 17)

* [ ] requirements-baseline-v1.0 tag verified on assessed commit
* [~] Feedback response (needs issue links and unresolved section)
* [ ] Sprint 2 plan
* [x] Goal analysis and links to requirements
* [x] Goal model diagram (Goal-Model.png uploaded and linked)
* [x] Obstacle analysis (5 obstacles O-01 to O-05)
* [x] Conflict analysis (5 conflicts C-01 to C-05, C-03 resolved)
* [~] Quality requirements catalogue (12 in catalogue, 15 in baseline)
* [x] Measurable QRs with fit criteria
* [x] Threshold origins documented
* [x] Full-baseline MoSCoW prioritization
* [x] Analytical weighted prioritization (20 requirements, 5 factors)
* [x] Sensitivity and dependency analysis
* [x] Priority Set
* [x] Requirements negotiation and simulated roles
* [x] Requirements dependency analysis (117 links, 6 types)
* [x] Dependency diagram (.puml and .svg in models/)
* [~] Baseline v2.0 (drafted, needs acceptance status and Issue links)
* [~] Baseline change summary (rename from baseline-change.md)
* [ ] Traceability matrix / report (traceability.md)
* [~] Decision log (ND-01 to ND-05, DD-01 to DD-05; earlier decisions pending)
* [ ] Retrospective (retrospective.md)
* [~] AI-use disclosure (needs detailed log)
* [ ] GitHub Issues, labels, and Project board updates
* [ ] Baseline v2.0 Pull Request with peer review
* [ ] requirements-baseline-v2.0 tag after merge
* [ ] GitHub setup report (github-sprint2-setup.md)
* [ ] Prototype README note
