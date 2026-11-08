# Sprint 2 Progress Tracker — Group 11

Due: **Sun Nov 8, 2026, 11:59 PM** (today). Compared: handout §14 required files vs. `eecs4312-project-group-11/doc/sprint2/` as of today. Nothing committed/pushed by this review.

Legend: ✅ substantial draft exists · 🟡 exists but has gaps · ❌ missing

## 1. File status (handout §14)

| Required file | Rubric § (marks) | Status | Notes |
|---|---|---|---|
| sprint1-feedback.md | 1.1 (3) | 🟡 | 27 lines, table is good. Missing: links to Issues/commits/PRs, "unresolved feedback + reason" section, v1.0 tag still unchecked ("no tag created"). |
| sprint2-plan.md | 1.2 (3) | ❌ | Not started. Needs participants, goal, questions, per-member RE roles, deadlines, risks. |
| goals.md | 2 (16) | 🟡 | 186 lines, strong (G-10…G-40, AND/OR refinements, gaps, conflicts GC-01..). Missing the goal **model diagram** (see models/). |
| models/goal-model.[src+export] | 2.2 (5) | ❌ | `models/` folder does not exist. Biggest single gap in the goals section. |
| obstacles-conflicts.md | 3 (10) | ✅ | O-01 to O-05, C-01 to C-05 (C-03 added, fills the numbering gap), CH-01 to CH-09. |
| quality-requirements.md | 4 (20) | 🟡 | QR-001, 003–013 done in full format (+ trade-offs). QR-014–016 are only in baseline-v2 §3 — the handout/baseline-change say they must be merged into this file. Check ≥6 have fit criteria (looks fine) and that each numeric threshold has labelled origin. |
| prioritization.md | 5 (14) | ✅ (uploaded by teammate, commit fdcd261) | Stage A (MoSCoW), Stage B (20 reqs, 5 factors, pairwise weights), sensitivity, dependency check, final Priority Set all present. Remaining: verify arithmetic; links to `baseline-change-summary.md` currently broken (file is named `baseline-change.md`). |
| negotiation.md | 6 (12) | ✅ ready | 5 issues (C-01 to C-05) with role tables (interests, preferred outcome, alternative, concession, red line, basis), discussion, decision, rationale and recorded concerns. Team review table filled (Zain, Anirudh, Sufyan, Nov 8). Effects applied to baseline v2, quality-requirements.md, obstacles-conflicts.md (C-03, CH-09) and decisions.md. AI disclosure is in ai-use.md only. |
| dependencies.md | 7 (8) | ✅ ready | 117 links (50 structural, 67 QR constraints), 6 types, matrix with source markers, hubs, chains, conflicts, deferral, Sprint 3 use. Both cycles removed and the fixes applied to the SR-003 and FR-010 baseline entries (decisions DD-01 to DD-05). |
| models/requirements-dependency.[src+export] | 7.1 | ✅ ready | `.puml` source and `.svg` export, left-to-right layout, no cycles or back-edges. Regenerate with `java -jar plantuml.jar -tsvg requirements-dependency.puml`. |
| requirements-baseline-v2.md | 8.1 (4) | 🟡 | Updated with the negotiation outcomes and the SR-003 and FR-010 dependency fixes. Still to do: update the Issue links and statuses for the changed requirements, and do the section 9 baseline work. |
| baseline-change-summary.md | 8.1 | 🟡 | Exists as **`baseline-change.md`** (teammate renamed it from the handout name in commit 248718c). The handout requires `baseline-change-summary.md` and prioritization.md still links to that name, so one of the two must change. Section 9 lists unfinished integration items. |
| traceability.md | 8.2 (3) | ❌ | Not started. Chain: evidence → goal → req → QR → scenario → fit criterion → Issue; show negotiation/conflict refs. |
| decisions.md | 13.1 | 🟡 | Sprint 2 file now holds ND-01 to ND-05 (negotiation) and DD-01 to DD-05 (dependencies). Still add the earlier goal, quality-threshold, prioritization-weight and retirement decisions from goals.md, quality-requirements.md and prioritization.md. |
| retrospective.md | 9.1 (2) | ❌ | Not started (do after negotiation). Needs least-confident area + most change-vulnerable area. |
| ai-use.md | 9.2 (2) | 🟡 | AI-S2-01 to 05 cover dependencies, negotiation and decisions. Add entries for any other Sprint 2 file where AI was used. |
| github-sprint2-setup.md | 8.3 (3) | ❌ | Not started. |
| prototype/README.md | §12 | ❌ | Optional content, but README is listed as required; one short note ("no prototype change in Sprint 2" is acceptable). |

## 2. Order of work

Sprint 1 lost 7 marks because requirements and Issues did not relate to the other documents, so the team is working in handout order. Negotiation (6) comes first, then dependencies (7, drafted), then the baseline and traceability (9, 10), since negotiation outcomes change the baseline. A teammate says the baseline requirements prototype is already on GitHub for part 6; it is not in the local copy, so pull before starting 9.

## 2a. What is left, in priority order (marks at risk)

1. **Section 7 and 8 are done.** Next in handout order: baseline v2 acceptance, traceability.md, then GitHub.
2. **Goal model diagram** (part of 16): add `models/goal-model.puml` and `.svg`. The dependency model is done (draft), so only this diagram is missing from `models/`. After negotiation, recheck dependencies.md §7 items and the C-03 / QR-015 vs QR-009 conflict.
3. **Fix quality-requirements.md** — fold in QR-014–016; keep ID list consistent with baseline (20 marks section).
4. **traceability.md** (not started), and the remaining decisions.md entries.
5. **sprint2-plan.md, sprint1-feedback.md additions** — plan must show all members with RE tasks and review assignments (note: being written on the due date; be honest about timing, don't backdate).
6. **GitHub work (not started per docs; needs user/team action):**
   - Confirm/create tag `requirements-baseline-v1.0` on assessed commit `0a0670ce…` *before* merging Sprint 2.
   - Update Issues #2–#29 (goal links, priority, QR, deps, confidence, status), create Issues for new IDs (FR-016, QR-014–016, etc.), labels `baseline:v2`, `priority:*`, `analysis:*`, `quality:*`.
   - Project board fields (status, priority, type, baseline, validation).
   - Baseline v2.0 PR with summary + **genuine teammate review**, merge, then tag `requirements-baseline-v2.0`.
   - Write `github-sprint2-setup.md`.
7. **retrospective.md, ai-use.md, prototype/README.md** — last, short.

## 3. Cross-artifact consistency issues found

- `baseline-change.md` vs. required name `baseline-change-summary.md` (links elsewhere already assume the latter).
- Obstacles/conflicts: no **C-03** (C-01, C-02, C-04, C-05 only). dependencies.md proposes QR-015 vs QR-009 as a new conflict that could take C-03. Decide with the team.
- Dependency cycles (FR-003, FR-016, SR-003 and FR-010, FR-011) come from the baseline "Requires" wording; fix in baseline v2 once negotiation is done.
- Quality catalogue lists 12 QRs (001, 003–013); baseline has 15 (adds 014–016, in the baseline file only).
- Baseline v2 says "Selected" = proposed; change doc says negotiation and acceptance are incomplete → update both once negotiation is done.
- Counts to re-verify after edits: 37 v2.0 reqs + 2 deferred = 39 (prioritization) vs. change doc table (37 selected, 2 deferred); "22 Must / 9 Should" with 8 deferred/inactive.
- Relative links point to `../sprint1/…`, `../../labs/…`, `../../feedback/…` — verify they resolve (handout §15.7).
- The draft docs avoid claiming a negotiation meeting or GitHub updates have happened — keep that honesty; do not mark them done until true.

## 4. Strengths to preserve

Goal set with owners and AND/OR refinements, 8 obstacle/change pairs, detailed QR scenarios with fit criteria, 5-factor weighted scoring with sensitivity analysis and dependency-aware Priority Set, stable-ID history (QR-002 split, CON-001/002 replaced).

## 5. Rough checklist (handout §17)

- [ ] v1.0 preserved/tagged
- [~] Feedback response (needs links + unresolved section)
- [ ] Sprint 2 plan
- [~] Goal model (text done, diagram missing)
- [x] Goals linked to requirements
- [x] ≥4 obstacles
- [~] ≥3 conflicts (4 present; C-03 gap)
- [~] 8–12 QRs / ≥4 characteristics (15 in baseline, 12 in catalogue)
- [x] ≥6 measurable QRs
- [~] Threshold origins documented (verify each)
- [x] Full-baseline MoSCoW
- [x] 15–20 analytical prioritization
- [x] Sensitivity check
- [x] Priority Set
- [x] Negotiation
- [x] Dependency analysis + model
- [~] Baseline v2.0 (draft)
- [~] Change summary (rename)
- [ ] Traceability v2
- [ ] GitHub Issues/Project updates
- [ ] Reviewed PR
- [ ] v2.0 tag after merge
- [ ] Decision log
- [ ] Retrospective
- [ ] AI-use record
