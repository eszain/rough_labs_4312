# Lab 6: Baseline v1.0, Modeling and Traceability Clinic

## Activity A: Five-Requirement Quality Sample

1. R-002 Legitimate Item Recovery (Stakeholder / Must / Issue #3):
The system shall support recovery of found property by a claimant only after an authorized ownership-verification decision has approved the associated claim. This is atomic with clear business intent, though authorization rules require child functional requirements. Verification will test that an unverified item cannot transition to release without an explicit approval record.

2. R-008 Candidate Match Ranking (Functional / Must / Issue #9):
The system shall produce an ordered list of potential found-item matches for a lost-item report using match attributes configured by the transit authority. This maintains clean separation between algorithmic matching and claim release per Decision D-004. Verification will submit a lost report matching three inventory items with varying time/color attributes to confirm results sort by similarity score.

3. R-009 Verification Decision Record (Functional / Must / Issue #10):
Before an item can be returned or released, the system shall require an authorized Lost & Found staff member to record a claim decision of approved or rejected with staff ID, timestamp, and result. This is atomic and auditable, but omits intermediate telephone triage states. Verification will attempt to record an approval without staff ID or timestamp and assert the system rejects the transaction.

4. R-019 Staff Audit Logging (Quality / Security / Must / Issue #15):
For every auditable staff action, the system shall create an audit entry containing authenticated staff identifier, action type, affected record identifier, and timestamp. This addresses an atomic security concern, though specific auditable actions require an explicit enum list in system documentation. Verification will execute custody and verification events and assert immutable log entries exist for each.

5. R-025 Mobile Responsive Interface (Constraint / Should / Untracked Issue):
The primary passenger workflows shall remain functionally complete at viewport widths of 320 px or greater without requiring horizontal page scrolling. This sets an objective and testable layout threshold, though the corresponding GitHub Issue must be opened. Verification will run automated layout tests across 320 px, 375 px, and 414 px viewports to assert zero horizontal scroll overflow.

## Activity B: Traceability Chains

1. Incomplete Descriptions and Phone Triage:
Lab 4 interview statement on vague clothing descriptions -> R-009 (Decision Record) -> UC-04 Exception 2a (Telephone Triage) -> Lab 5 Criterion 2 (Require phone attempt or rejection reason).
R-009 represents a weak link because it omits intermediate states like Pending Telephone Contact and provides no schema for logging call notes.

2. Unverified High-Value Police Escalation:
Lab 4 gaming mouse liability finding -> R-016 (Final Disposition) -> UC-04 Exception 4a (Police Escalation) -> Lab 5 Criterion 4 (Badge ID and occurrence number required for items >= $1000).
R-016 represents a broken link because it specifies disposition only after the 90-day retention window, lacking an immediate police transfer state and omitting the $1000 threshold.

3. Payment Card Privacy:
Lab 4 wallet recovery interview -> R-020 (Data Retention) and R-022 (Data Encryption) -> UC-04 Step 3 (In-person ID proof) -> Lab 5 Criterion 5 (Delete 15/16 digit card numbers, allow only issuer and last 4 digits).
R-020 and R-022 represent a weak link because they protect stored data but fail to provide an active input-validation rule blocking staff from typing card numbers into notes.

## Activity C: Model Interrogation

Auditing doc/sprint0/context-diagram.puml against the baseline revealed three defects:

1. Missing Transit Police Actor: The diagram includes payment and delivery gateways but omits Transit Police, which is the primary legal off-ramp for unverified high-value items established in Lab 4 and Lab 5.
2. Missing Telephone Communication Channel: The diagram depicts passenger contact only via web and email/SMS, omitting the outbound phone triage channel staff rely on for incomplete claims.
3. Architectural Decomposition Clutter: The diagram decomposes internal system modules (Reporting, Storage, Matching, Verification) rather than treating the system as a black box, directly causing the readability issues flagged in Sprint 0 grading.

## Activity D: Mini Walkthrough Preparation

Walkthrough agenda for the course TA:
* Walk through verification and disposition lifecycle across R-002, R-008, R-009, and R-016.
* Demonstrate forward linkage from Lab 4 interview findings to Lab 5 UC-04 scenarios and acceptance criteria.
* Show that concrete thresholds like $1000 valuation, 4-character badge IDs, and 320 px width provide objective pass/fail criteria.
* Present the backlog errors discovered during the clinic, specifically the duplicate R-027 statement and missing police boundary.

## Prioritized Pre-Submission Correction Plan

1. Priority 1 (Critical): Rewrite R-027 in requirements-backlog.md to specify in-person pickup acknowledgment instead of the duplicate R-025 mobile width statement, and align R-026 title with its notification statement. Assigned to Zain for Oct 23.
2. Priority 2 (High): Redraw context-diagram.puml as a clean black-box diagram, enlarge text for zero-zoom readability, and add Transit Police as an external actor. Assigned to Anirudh for Oct 24.
3. Priority 3 (High): Update R-016 and R-009 to include the Transferred to Police Custody disposition status and the $1000 valuation trigger. Assigned to Sufyan for Oct 24.
4. Priority 4 (Medium): Add missing external entities (TTC IT, Logistics Provider, Payment Service) to stakeholders.md and definitions (IPC, AODA) to glossary.md to close Sprint 0 feedback conditions. Assigned to Anirudh for Oct 24.
5. Priority 5 (Medium): Add requirement R-029 specifying regex validation to block 15/16-digit card numbers from staff verification notes. Assigned to Zain for Oct 25.
