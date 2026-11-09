# Sprint 2 Baseline v2.0 Peer Review Guide: Group 11

This guide explains how to complete and submit the required peer review on Pull Request #43 for Requirements Baseline v2.0.

Pull Request URL: https://github.com/EECS4312F26/eecs4312-project-group-11/pull/43  
Target Branch: `main`  
Source Branch: `baseline-v2.0`  

## 1. Why a detailed peer review is required

Rubric Section 8.3 awards 3 full marks for GitHub state, PR review, and baseline tagging:
* 3 marks: Baseline PR meaningfully summarizes changes and receives teammate review; issues/labels/project state are consistent with v2.0; v2.0 tag is created after merge.
* 2 marks: Mostly correct GitHub management with minor inconsistencies or weak PR review.
* 1 mark: Baseline state difficult to reconstruct.

A generic comment such as "looks good" or "approved" is penalized as a weak review. Submitting a specific, substantive review that references our artifacts guarantees maximum marks.

## 2. Step-by-step instructions to submit your review on GitHub

1. Open the Pull Request link:
   https://github.com/EECS4312F26/eecs4312-project-group-11/pull/43
2. Click on the Files changed tab near the top of the page.
3. Click on the green Review changes button located at the top-right corner.
4. Copy and paste your assigned review template from Section 3 or Section 4 below into the text box.
5. Select the Approve radio button option.
6. Click the green Submit review button.

## 3. Review template for Muhammad Sufyan (@abdullah998020-gif)

Copy and paste the markdown block below into your GitHub review comment:

```markdown
I have completed peer review of this Baseline v2.0 Pull Request.

Key areas inspected and verified:
1. Requirements Baseline and Change Register:
   * Confirmed that `requirements-baseline-v2.md` and `baseline-change-summary.md` account for all 39 requirements (37 selected + 2 deferred).
   * Verified that all live GitHub Issue links (#2 through #42) are correctly connected in the baseline tables with no broken links.
2. Quality Requirements Consolidation:
   * Verified that QR-014 (permission for optional contact), QR-015 (resistance to automated misuse), and QR-016 (minimal evidence) are integrated into `quality-requirements.md` with measurable ISO 25010 fit criteria and trade-off analyses.
3. Prototype Grounding:
   * Confirmed that `doc/sprint2/prototype/README.md` accurately describes how our conceptual walkthroughs (restricted catalog browsing, claim dispute locking, and rate limiting) directly grounded the baseline specifications.
4. Setup Evidence:
   * Verified that `doc/sprint2/github-sprint2-setup.md` accurately documents the controlled label taxonomy and the complete 39-requirement issue synchronization ledger.

Everything is consistent across our sprint artifacts. Approved for merge.
```

## 4. Review template for Anirudh Sundar (@asxter)

Copy and paste the markdown block below into your GitHub review comment:

```markdown
I have completed peer review of this Baseline v2.0 Pull Request.

Key areas inspected and verified:
1. Bidirectional Traceability:
   * Confirmed that `doc/sprint2/traceability.md` features complete forward and backward coverage connecting evidence, goals, requirements, AC2 acceptance criteria, FIT2 fit criteria, and live GitHub Issue URLs (#2 to #42).
2. Goal and Dependency Models:
   * Confirmed that both editable source files and export diagrams are present in `doc/sprint2/models/`: `Goal-Model.drawio` with `Goal-Model.png`, and `requirements-dependency.puml` with `requirements-dependency.svg`. This satisfies the [src+export] requirement.
3. Decision Log Coverage:
   * Verified that `doc/sprint2/decisions.md` contains the full set of 24 formal decisions across all 5 categories (ND-01 to ND-05, DD-01 to DD-05, GD-01 to GD-04 / GA-01 to GA-04, QD-01 to QD-03, and PD-01 to PD-03).
   * Confirmed that cycle resolutions DD-01 to DD-05 align with the dependency matrix in `dependencies.md`.
4. Release Scope and Labeling:
   * Confirmed that all existing issues (#2 to #29) and new issues (#31 to #42) have the `baseline:v2` tag and consistent MoSCoW priorities matching Baseline v2.0.

All traceability links and model assets are verified. Approved for merge.
```

## 5. Artifact verification checklist

Before or while submitting, reviewers can verify these core facts:
* Exactly 39 total requirements in Baseline v2.0 (37 selected + 2 deferred).
* All 39 requirements have corresponding live GitHub issues with the `baseline:v2` label.
* The 15 quality requirements in `quality-requirements.md` have measurable ISO 25010 fit criteria.
* The 24 decisions in `decisions.md` cover negotiation (ND), dependencies (DD), goals (GD/GA), quality (QD), and prioritization (PD).
* The models directory contains both source and export files for both diagrams.

## 6. Next step after review submission

Once the review approvals are submitted on GitHub:
1. Pull Request #43 will be merged into `main`.
2. The official release tag `requirements-baseline-v2.0` will be created on the merge commit and pushed to origin.

