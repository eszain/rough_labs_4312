# Sprint 2 Progress Tracker: Group 11

Due: Sunday November 8, 2026, 11:59 PM. Evaluated against Handout Section 14 required files and Rubric criteria as of latest repository commit (469ddce).

Legend: [x] completed / ready · [~] substantial draft with open gaps · [ ] missing / not started

## 1. File status (Handout Section 14)

| Required file | Rubric Section (marks) | Status | Notes |
|---|---|---|---|
| sprint1-feedback.md | 1.1 (3) | [x] | Complete. Actionable feedback matrix with 9 items linked to Issues/PRs/commits, 2 unresolved items with technical justifications, and assessed v1.0 commit tag verified. |
| sprint2-plan.md | 1.2 (3) | [x] | Complete. Documents sprint goals, participants, 6 core RE analysis questions, per-member workload distribution, schedule milestones, and 5 technical/process risks with mitigations. |
| goals.md | 2.1, 2.3 (11) | [x] | Updated with KAOS goal model description and embedded diagram link. Comprehensive G-10 to G-40 breakdown with AND/OR refinements, gaps, and requirement links. |
| models/goal-model.[src+export] | 2.2 (5) | [~] | Goal-Model.png (1 MB) is present in models/ and embedded in goals.md. Export image is available; editable source file (.puml or .drawio) should be placed in models/ to fulfill [src+export]. |
| obstacles-conflicts.md | 3 (10) | [x] | Complete. Covers O-01 to O-05, C-01 to C-05 (including C-03 filling the earlier numbering gap), and CH-01 to CH-09. |
| quality-requirements.md | 4 (20) | [x] | Complete and consolidated. QR-001, QR-003 to QR-013, plus consolidated QR-014 (optional contact), QR-015 (misuse resistance), and QR-016 (minimal evidence). All 15 QRs have measurable fit criteria and trade-off analyses. |
| prioritization.md | 5 (14) | [x] | Complete. Stage A MoSCoW (39 requirements), Stage B 5-factor weighted scoring for 20 requirements, pairwise weights, sensitivity analysis, dependency cross-check, and final Priority Set. |
| negotiation.md | 6 (12) | [x] | Complete and ready. 5 issues (C-01 to C-05) analyzed with simulated stakeholder positions. Section 8 team review table filled with reviewer names, agreed decisions, and settled numbers (5-day response, 3-day dispute review, 90-day retention, 15-minute lockout). Zero provisional assumptions remaining. |
| dependencies.md | 7 (8) | [x] | Complete and ready. 117 links, 6 relation types, full matrix with source markers, hubs, chains, and 5 cycle break resolutions (DD-01 to DD-05). |
| models/requirements-dependency.[src+export] | 7.1 | [x] | Complete and ready. Both requirements-dependency.puml source and requirements-dependency.svg export are present in models/. |
| requirements-baseline-v2.md | 8.1 (4) | [x] | Complete. Contains 37 selected requirements + 2 deferred. Updated with negotiation and dependency fixes. Product baseline membership status set. Live issue links for #31 to #42 can now be connected. |
| baseline-change-summary.md | 8.1 | [x] | Complete. Renamed from baseline-change.md in commit 895e9bc and aligned in commit b8251ed. Contains full change register from v1.0 to v2.0 (13 additions, 2 deferrals, 24 edits) and priority shifts. |
| traceability.md | 8.2 (3) | [x] | Complete. Renamed from tracability.md to traceability.md in commit e829854 (62 KB). Features comprehensive forward and backward traceability across all 37 selected and 2 deferred requirements with AC2 acceptance checks and FIT2 fit criteria. |
| decisions.md | 13.1 | [~] | Contains 10 formal entries: ND-01 to ND-05 (negotiation) and DD-01 to DD-05 (dependencies). Earlier decisions (goal refinements, quality thresholds, prioritization weights) should be appended per Handout Section 13.1. |
| retrospective.md | 9.1 (2) | [x] | Complete. Full 8-part reflection covering RE practices, Sprint 3 adjustments, C-03 trade-off, least confident area (QR-013), and change vulnerability (FR-010/FR-011). |
| ai-use.md | 9.2 (2) | [~] | File exists but contains only a title heading. Needs complete disclosure of AI tools, prompts, verification methods, and human review across deliverables. |
| github-sprint2-setup.md | 8.3 (3) | [~] | In progress. All 12 new requirement issues (#31 to #42) created live on GitHub. Existing issues #2 to #29 synchronization, PR review evidence, and v2.0 tag report to be recorded here. |
| prototype/README.md | 12 | [ ] | Handout section 14 requires a prototype README note (a short note confirming no prototype changes were required in Sprint 2 and explaining the verification approach). |

## 2. Marks breakdown and current standing

* Total raw marks: 100 (scaled to 8% of course grade).
* Marks currently secure or substantially ready: approximately 88.5 / 100
  * Section 1: Continuity and Planning: 6 / 6
  * Section 2: Goal-Oriented Analysis: 15 / 16 (goal model source file pending)
  * Section 3: Obstacle and Conflict Analysis: 10 / 10
  * Section 4: Quality Requirements: 20 / 20 (QR-014 to QR-016 consolidated)
  * Section 5: Requirements Prioritization: 14 / 14
  * Section 6: Negotiation and Trade-Off Analysis: 12 / 12
  * Section 7: Dependency and Interaction Analysis: 8 / 8
  * Section 8: Baseline, Traceability, and GitHub: 7.5 / 10 (Baseline 4/4, Traceability 3/3, GitHub management 1.5/3)
  * Section 9: Retrospective, AI Transparency, and Coherence: 2.5 / 4 (Retrospective 2/2, AI disclosure 0.5/2)
* Marks remaining to reach 100 / 100: approximately 11.5 marks (AI disclosure log, GitHub PR/reviews/tagging, prototype note, decisions expansion, goal model source file).

## 3. Work remaining in priority order (to achieve 100 / 100)

1. ai-use.md (2 marks, Rubric 9.2):
   Write complete disclosure of AI tools, prompts, outputs, and human verification protocols in doc/sprint2/ai-use.md.

2. prototype/README.md (Handout Section 12 & 14):
   Create prototype/README.md with the required statement confirming no prototype code changes were needed for Sprint 2 and detailing the requirements verification strategy.

3. decisions.md expansion (Handout Section 13.1):
   Append earlier Sprint 2 decisions (goal decompositions GD-01 to GD-03, quality threshold origins QD-01 to QD-04, and prioritization criteria weighting PD-01) alongside the existing ND-01 to ND-05 and DD-01 to DD-05 entries.

4. Editable Goal Model Source File (Rubric 2.2, 5 marks):
   Add the editable PlantUML or Draw.io source file (models/goal-model.puml or models/goal-model.drawio) to doc/sprint2/models/ to pair with Goal-Model.png and satisfy the [src+export] requirement.

5. Update live Issue links in requirements-baseline-v2.md and traceability.md:
   Replace "Pending" and "Not yet assigned" entries with direct links to newly created GitHub Issues #31 to #42.

6. Synchronize existing GitHub Issues #2 to #29:
   Update titles, labels, and issue bodies for existing issues #2 through #29 using the prepared specification ledger in rough_labs_4312/r_sprint2/sprint2_github_issues.md.

7. github-sprint2-setup.md and Baseline v2.0 Pull Request (Rubric 8.3, 3 marks):
   Open a pull request for Baseline v2.0, conduct genuine teammate reviews from Sufyan and Anirudh, merge into main, apply the requirements-baseline-v2.0 git tag, and author doc/sprint2/github-sprint2-setup.md with setup evidence.

## 4. Three-person workload division and assigned responsibilities

### Member 1: Mohammad Zain Al Syed (eszain)
* Remaining primary responsibilities:
  1. GitHub repository management and github-sprint2-setup.md (Rubric 8.3, 3 marks): All 12 new Issues (#31 to #42) created live. Synchronize existing Issues #2 to #29, manage the baseline v2.0 PR, coordinate peer reviews, merge into main, apply requirements-baseline-v2.0 git tag, and author setup evidence document.
  2. Complete ai-use.md (Rubric 9.2, 2 marks): Author detailed AI transparency disclosure.
* Completed author responsibilities:
  * sprint2-plan.md (Rubric 1.2, 3 marks): Completed.
  * sprint1-feedback.md (Rubric 1.1, 3 marks): Completed.
  * retrospective.md (Rubric 9.1, 2 marks): Completed.
  * Creation of all 12 new requirement issues on GitHub (#31 to #42): Completed.
* Peer review responsibilities:
  * Review traceability.md authored by Anirudh.
  * Review quality-requirements.md consolidation authored by Sufyan.

### Member 2: Muhammad Sufyan (abdullah998020-gif)
* Completed author responsibilities:
  * quality-requirements.md consolidation (Rubric 4, 20 marks): Merged QR-014, QR-015, and QR-016 into doc/sprint2/quality-requirements.md (commit 0a8ac06).
  * baseline-change-summary.md & requirements-baseline-v2.md alignment (Rubric 8.1, 4 marks): Renamed file, verified requirement counts, and updated baseline status.
* Remaining author responsibilities:
  1. prototype/README.md (Handout Section 12): Write the required prototype directory note documenting Sprint 2 verification approach and confirming prototype code status.
* Peer review responsibilities:
  * Review sprint2-plan.md and retrospective.md authored by Zain.
  * Review traceability.md and decisions.md authored by Anirudh.
  * Conduct review on baseline v2.0 Pull Request.

### Member 3: Anirudh Sundar (asxter)
* Completed author responsibilities:
  * traceability.md (Rubric 8.2, 3 marks): Completed comprehensive 62 KB forward and backward traceability matrix connecting evidence, goals, requirements, quality attributes, scenarios, AC2 acceptance checks, FIT2 fit criteria, and issues. Renamed to traceability.md (commit e829854).
* Remaining author responsibilities:
  1. decisions.md expansion (Handout Section 13.1): Add earlier Sprint 2 decisions (goal decompositions, quality thresholds, prioritization weights) alongside existing ND-01 to ND-05 and DD-01 to DD-05 entries.
  2. Goal model source file preservation (Rubric 2.2): Save editable source file (.puml or .drawio) for Goal-Model.png into doc/sprint2/models/.
* Peer review responsibilities:
  * Review sprint1-feedback.md and github-sprint2-setup.md authored by Zain.
  * Review quality-requirements.md and baseline change summary authored by Sufyan.
  * Conduct review on baseline v2.0 Pull Request.

## 5. Cross-artifact consistency checklist

* Baseline naming: baseline-change-summary.md is confirmed and matches all references.
* Quality ID alignment: quality-requirements.md now contains all 15 QRs (QR-001, QR-003 to QR-016), perfectly matching Baseline v2.0.
* Traceability naming: traceability.md spelling is corrected and verified.
* Goal model diagram: Goal-Model.png is committed in models/; editable source file to be saved alongside it.
* Negotiation and dependencies numbers: Settled values (5-day response, 3-day supervisor review, 90-day dispute retention, 15-minute rolling lockout) in negotiation.md match decisions.md and baseline v2.0.
* Requirement counts: 37 selected requirements + 2 deferred (FR-010, FR-011) = 39 total active requirements across baseline v2.0, change summary, prioritization.md, and traceability.md.

## 6. Sprint 2 deliverables checklist (Handout Section 17)

* [x] requirements-baseline-v1.0 tag verified on assessed commit
* [x] Feedback response (linked matrix, unresolved justifications, v1.0 tag verified)
* [x] Sprint 2 plan (goals, questions, workload, milestones, risks)
* [x] Goal analysis and links to requirements
* [x] Goal model diagram (Goal-Model.png uploaded and linked)
* [x] Obstacle analysis (5 obstacles O-01 to O-05)
* [x] Conflict analysis (5 conflicts C-01 to C-05, C-03 resolved)
* [x] Quality requirements catalogue (all 15 QRs consolidated)
* [x] Measurable QRs with fit criteria
* [x] Threshold origins documented
* [x] Full-baseline MoSCoW prioritization
* [x] Analytical weighted prioritization (20 requirements, 5 factors)
* [x] Sensitivity and dependency analysis
* [x] Priority Set
* [x] Requirements negotiation and simulated roles
* [x] Requirements dependency analysis (117 links, 6 types)
* [x] Dependency diagram (.puml and .svg in models/)
* [x] Baseline v2.0 (all 39 requirements, updated status)
* [x] Baseline change summary (baseline-change-summary.md aligned)
* [x] Traceability matrix / report (doc/sprint2/traceability.md, 62 KB)
* [~] Decision log (ND-01 to ND-05, DD-01 to DD-05; earlier decisions pending)
* [x] Retrospective (full 8-part reflection completed)
* [~] AI-use disclosure (needs detailed log in ai-use.md)
* [x] All 12 new requirement issues created on GitHub (#31 to #42)
* [~] Existing GitHub Issues #2 to #29 synchronized
* [ ] Baseline v2.0 Pull Request with peer review
* [ ] requirements-baseline-v2.0 tag after merge
* [ ] GitHub setup report (github-sprint2-setup.md)
* [ ] Prototype README note
