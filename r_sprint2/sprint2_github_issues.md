# Sprint 2 GitHub Issues Specification and Synchronization Ledger

Project: Public Transit Lost and Found System (Group 11)  
Course: EECS 4312 (Software Requirements Engineering)  
Baseline: Requirements Baseline v2.0 (37 selected requirements + 2 deferred)  
Destination Repository: https://github.com/EECS4312F26/eecs4312-project-group-11

This document specifies the exact title, labels, and issue body for all 39 requirements in Baseline v2.0. It is divided into:
1. Existing Issues (#2 to #29) that require status, priority, and metadata updates.
2. New Issues (FR-016, QR-004/QR-005 child split, QR-006, QR-007, QR-010 to QR-016) to be created on GitHub.

## 1. Existing Issues to Update (#2 to #29)

### Issue #2: [BR-001] Authoritative recovery records
* Legacy ID: R-001
* Typed ID: BR-001
* Labels: type:business, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-10 (Custody accountability), G-14 (Reconstructable history), G-41 (Current updates)
* Statement: The system shall maintain a separately identifiable, searchable authoritative record for each loss report and recovered item, preserving its applicable lifecycle history and explicit links to associated claims.
* Rationale: Prevents conflicting station and claim records; an unmatched loss report does not require a physical storage bin.
* Verification Idea: Create an unmatched loss report and an unclaimed found item; assert distinct records and separate lifecycles; linking them preserves both identities without overwrite.
* Dependencies: Constrained by QR-001 (Audit), QR-003 (Access), QR-004 (Retention), QR-011 (Consistency).

### Issue #3: [BR-002] Authorized property release
* Legacy ID: R-002
* Typed ID: BR-002
* Labels: type:business, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-22 (Authorized release)
* Statement: The system shall permit release only against a current ownership approval recorded by authorized staff for the claimant and item, with no unresolved release restriction.
* Rationale: Prevents similarity, an expired approval, or an unresolved competing claim from authorizing handover.
* Verification Idea: Attempt property release with no approval, withdrawn approval, wrong claimant, and active dispute; all transactions must be rejected.
* Dependencies: Requires FR-003 (Ownership decision), FR-014 (Dispute block); constrained by QR-003 (Access), QR-011 (Consistency).

### Issue #4: [SR-001] Flexible loss reporting
* Legacy ID: R-003
* Typed ID: SR-001
* Labels: type:stakeholder, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-11 (Incomplete travel reporting), G-40 (Passenger participation)
* Statement: The system shall accept a loss report containing category, description, approximate loss-date window and contact information, with route, vehicle, station and photographs optional.
* Rationale: Allows legitimate passenger reporting even when exact transit vehicle or run numbers are unknown.
* Verification Idea: Submit report without vehicle/route/photo; accept valid approximate dates; verify validation errors identify missing required fields while retaining valid entries.
* Dependencies: Produces BR-001; constrained by QR-005 (Card minimization), QR-009 (Accessible tasks), QR-016 (Evidence minimization).

### Issue #5: [SR-002] Report reference and receipt
* Legacy ID: R-004
* Typed ID: SR-002
* Labels: type:stakeholder, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-11 (Report participation), G-44 (Protected lookup)
* Statement: After a loss report is durably accepted, the system shall provide its claimant with a unique persistent reference and receipt identifying that report.
* Rationale: Supports passenger follow-up without re-entering report details; receipt generation requires persistent save.
* Verification Idea: Verify distinct reports receive distinct references; assert receipt retrieves the report through authorized lookup; failed transaction yields no receipt.
* Dependencies: Requires SR-001, BR-001; constrained by QR-010 (Response time), QR-011 (Consistency).

### Issue #6: [SR-003] Protected current-status lookup
* Legacy ID: R-005
* Typed ID: SR-003
* Labels: type:stakeholder, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-41 (Current updates), G-42 (Private information), G-44 (Protected lookup)
* Statement: The system shall show the claimant the current permitted processing status and next action for their referenced report after authentication or proof of control of its registered contact channel.
* Rationale: Knowing a reference or email address alone does not establish authorization; status updates must be accessible without optional messages.
* Verification Idea: Verify claimant A cannot view claimant B report; distinguish candidate found, approved, ready for pickup, disputed, and returned states.
* Dependencies: Requires SR-002; shows decision and dispute states from FR-003 and FR-014 when present; constrained by QR-003, QR-009, QR-015.

### Issue #7: [FR-001] Found-item intake
* Legacy ID: R-006
* Typed ID: FR-001
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-10 (Custody accountability), G-12 (Accountable intake)
* Statement: When property is turned in, the system shall record an intake entry with a unique barcode tag, intake timestamp, initial receiving employee, receiving station or route, and physical storage location.
* Rationale: Establishes initial custody accountability at frontline handover without unrealistic form overhead.
* Verification Idea: Scan barcode tag and record intake; assert duplicate tag rejected; verify record establishes initial custodian and location.
* Dependencies: Contributes to BR-001; constrained by QR-001 (Audit), QR-003 (Access).

### Issue #8: [SR-004] Confirmed custody transfers
* Legacy ID: R-007
* Typed ID: SR-004
* Labels: type:stakeholder, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-10 (Custody accountability), G-13 (Clear handover responsibility)
* Statement: The system shall track each handover from initiation through receipt or discrepancy reconciliation, recording sender, intended receiver, location and time, retaining the last confirmed custodian until receipt is acknowledged, and requiring attributed reconciliation before closing a discrepancy.
* Rationale: An intended transfer destination must not be mistaken for confirmed custody.
* Verification Idea: Initiate transfer without receiver acknowledgment; assert sender remains confirmed custodian; mismatch keeps status in discrepancy until reconciled.
* Dependencies: Requires FR-001; constrained by QR-001 (Audit), QR-003 (Access), QR-011 (Consistency).

### Issue #9: [FR-002] Candidate match ranking
* Legacy ID: R-008
* Typed ID: FR-002
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-21 (Candidate review)
* Statement: The system shall compare lost-item reports and recovered-item inventory using available attributes, producing an ordered candidate list for authorized staff review with matched criteria and similarity indicators.
* Rationale: Aids staff in identifying candidate matches across large inventory volumes; algorithmic scores never authorize release.
* Verification Idea: Compare report with 100 test items; verify ranking sorts candidates by matching attributes; assert score alone cannot change claim state.
* Dependencies: Requires SR-001, FR-001; constrained by QR-013 (Useful candidate discovery).

### Issue #10: [FR-003] Ownership decision recording
* Legacy ID: R-009
* Typed ID: FR-003
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-22 (Authorized release), G-23 (Fair review)
* Statement: The system shall require an authorized staff member to record an ownership decision of Approved, Rejected, or Pending Clarification for an item-claim association, recording reviewer identity, timestamp, decision rationale, and supporting evidence references.
* Rationale: Enforces accountability for ownership decisions while supporting intermediate clarification states.
* Verification Idea: Attempt decision submission without staff ID or rationale; assert transaction rejected; verify Pending Clarification blocks release.
* Dependencies: Requires FR-002; feeds BR-002, FR-013, FR-014; constrained by QR-001, QR-003, QR-016.

### Issue #11: [FR-004] Urgent property classification
* Legacy ID: R-010
* Typed ID: FR-004
* Labels: type:functional, status:accepted, priority:should, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-24 (Urgent triage)
* Statement: The system shall flag reports and recovered property matching management-defined urgent categories (prescription medication, mobility devices, passports, essential keys) for expedited review.
* Rationale: Prioritizes critical personal belongings without bypassing ownership verification.
* Verification Idea: Submit report with prescription medication; verify urgent flag applied; submit non-urgent report and verify normal queue assignment.
* Dependencies: Refines SR-001, FR-001; feeds FR-005; constrained by QR-003.

### Issue #12: [SR-005] Restricted public catalogue
* Legacy ID: R-013
* Typed ID: SR-005
* Labels: type:stakeholder, status:accepted, priority:should, analysis:conflict
* Goal Link: G-26 (Passenger discovery), G-42 (Privacy protection)
* Statement: The system shall expose recovered items through a public catalogue limited to approved category-specific public attributes, excluding claimant information and details reserved for ownership verification. A category is published only after the Privacy Officer approves its public field list, and an image is published only after it passes the approved redaction checklist.
* Rationale: Facilitates rider discovery while protecting distinguishing features needed to authenticate owners.
* Verification Idea: Inspect public catalogue JSON response; verify serial numbers, unique markings, and private notes are excluded.
* Dependencies: Requires FR-001; constrained by QR-003, QR-005; extended by FR-016.

### Issue #13: [FR-007] Storage location tracking
* Legacy ID: R-014
* Typed ID: FR-007
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-10 (Custody accountability), G-14 (Locatable property)
* Statement: The system shall record the physical warehouse storage bin or locker location for each recovered item in central custody, updating the location upon internal relocations.
* Rationale: Ensures physical property is rapidly retrievable for verification and return.
* Verification Idea: Move item between bins; verify storage record updates with responsible staff ID and timestamp.
* Dependencies: Requires FR-001; feeds FR-013; constrained by QR-001.

### Issue #14: [FR-009] Final item disposition
* Legacy ID: R-016
* Typed ID: FR-009
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-10 (Custody accountability), G-15 (Authorized disposition)
* Statement: For unclaimed or unreturnable property past the retention window, the system shall require an authorized staff member to record disposition (auction, donation, destruction, or law enforcement handover) with authorization reference, date, and receiving party acknowledgment.
* Rationale: Prevents property shrinkage and guarantees lawful disposal compliance.
* Verification Idea: Attempt disposition without receiving party acknowledgment; assert status remains in storage; verify completed disposition archives item record.
* Dependencies: Requires FR-007; constrained by QR-001, QR-003, QR-004.

### Issue #15: [QR-001] Accountable audit history
* Legacy ID: R-019
* Typed ID: QR-001
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-14 (Reconstructable history), G-22 (Authorized release)
* Statement: The system shall retain an attributed audit record for each committed staff action before acknowledging that action as successful, limited to actor, action, affected record, time, outcome and decision reference, with no claimant contact detail. Corrections shall create a new attributed record rather than overwrite the original.
* Rationale: Guarantees non-repudiation while enforcing data minimization.
* Verification Idea: Perform intake and claim approval; verify audit log stores actor, action, record, timestamp, and outcome; confirm zero claimant contact detail in log payload.
* Dependencies: Constrained by QR-004, QR-016.

### Issue #16: [QR-003] Authorized access and private disclosure
* Legacy ID: R-021
* Typed ID: QR-003
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-22 (Authorized release), G-42 (Private information use)
* Statement: The system shall authorize each request against the user's current role and permitted records. Claimants shall access private claims only after authentication or verification of control over the registered contact channel. Staff shall access only records permitted for their assigned duties; administrator status alone shall not authorize claim decisions.
* Rationale: Restricts private personal data and property release actions to authorized roles.
* Verification Idea: Authenticate as station employee and attempt ownership release; assert HTTP 403 Forbidden; verify public requests return only approved attributes.
* Dependencies: Requires authentication provider; constrains SR-003, SR-005, FR-003, FR-014.

### Issue #17: [FR-005] Urgent review queue
* Legacy ID: R-011
* Typed ID: FR-005
* Labels: type:functional, status:accepted, priority:should, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-24 (Urgent triage)
* Statement: The system shall maintain an expedited verification queue for urgent claims, alerting claims officers and tracking elapsed triage time.
* Rationale: Directs staff attention to high-consequence items while tracking waiting time.
* Verification Idea: Verify urgent items appear in priority review queue ahead of standard items; verify standard items track waiting time to prevent starvation.
* Dependencies: Requires FR-004; constrained by QR-003.

### Issue #18: [FR-006] Urgent staff alerts
* Legacy ID: R-012
* Typed ID: FR-006
* Labels: type:functional, status:accepted, priority:should, analysis:goal-linked
* Goal Link: G-20 (Fair ownership decisions), G-24 (Urgent triage)
* Statement: When an urgent item intake is committed, the system shall generate a persistent staff notification for active claims officers.
* Rationale: Alerts claims personnel without blocking the operator intake transaction.
* Verification Idea: Simulate intake with claims staff offline; verify notification persists and displays upon subsequent staff login.
* Dependencies: Requires FR-001, FR-004; feeds FR-005.

### Issue #19: [FR-008] Processing guidance
* Legacy ID: R-015
* Typed ID: FR-008
* Labels: type:functional, status:accepted, priority:should, analysis:goal-linked
* Goal Link: G-40 (Passenger participation), G-43 (Dependable access)
* Statement: The system shall display service-specific processing guidance and intake status expectations on public portals, distinguishing local station intake from central facility transfers.
* Rationale: Sets accurate rider expectations regarding physical transfer latency without promising arbitrary timelines.
* Verification Idea: Inspect reporting portal; assert guidance reflects applicable station transfer estimates; verify next-action instructions are visible.
* Dependencies: Informs SR-001; constrained by QR-009.

### Issue #20: [FR-010] Courier dispatch record (Deferred)
* Legacy ID: R-017
* Typed ID: FR-010
* Labels: type:functional, status:accepted, priority:wont-now, analysis:dependency
* Goal Link: G-30 (Property returns), G-32 (Remote return)
* Statement: For an approved remote return, the system shall track approved delivery address, logistics carrier, tracking reference, and carrier handover state, keeping failed delivery incomplete under staff review.
* Rationale: Retained in baseline but deferred from first release pending third-party courier contracts and liability agreements.
* Verification Idea: Verify remote dispatch workflow can only be initiated when payment gate FR-011 confirms fee settlement.
* Dependencies: Requires BR-002, SR-004, FR-011.

### Issue #21: [FR-011] Paid-delivery release gate (Deferred)
* Legacy ID: R-018
* Typed ID: FR-011
* Labels: type:functional, status:accepted, priority:wont-now, analysis:dependency
* Goal Link: G-30 (Property returns), G-32 (Remote return)
* Statement: When courier delivery is chargeable, the system shall prevent carrier handover until confirmed payment status is received from the external payment gateway.
* Rationale: Prevents transit authority financial loss from uncollectible shipping fees; deferred with FR-010.
* Verification Idea: Attempt carrier dispatch with payment status unpaid; assert transaction blocked until payment webhook confirms settlement.
* Dependencies: Requires FR-010; constrains BR-002.

### Issue #22: [QR-004 / QR-005] Split origin: PII retention and card minimization
* Legacy ID: R-020
* Typed ID: QR-004, QR-005
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: Historical origin issue for the split of R-020 into QR-004 (policy-based retention with 90-day post-closure dispute purge) and QR-005 (automated payment card sanitization).
* Rationale: Preserves auditability of Sprint 1 feedback resolution while branching into dedicated child requirement issues.
* Verification Idea: Trace historical issue to child specifications QR-004 and QR-005.

### Issue #23: [QR-008] Passenger-service availability
* Legacy ID: R-024 (Replaces CON-001)
* Typed ID: QR-008
* Labels: type:quality, status:accepted, priority:should, quality:reliability
* Goal Link: G-40 (Passenger participation), G-43 (Dependable access)
* Statement: Each public reporting and lookup function shall provide at least 99.5% monthly availability measured via functional one-minute probes with a 10-second timeout boundary.
* Rationale: Converts former vague uptime constraint into a testable reliability requirement.
* Verification Idea: Execute synthetic HTTP probes every minute; compute monthly availability; confirm non-responding intervals count as downtime.
* Dependencies: Constrains SR-001, SR-002, SR-003.

### Issue #24: [QR-009] Accessible passenger task completion
* Legacy ID: R-025 (Replaces CON-002)
* Typed ID: QR-009
* Labels: type:quality, status:accepted, priority:must, quality:interaction
* Goal Link: G-11 (Incomplete travel reporting), G-40 (Passenger participation), G-43 (Dependable access)
* Statement: The system shall allow reporting, search, and status lookup tasks to be completed across 320 px to 414 px viewports, 200% zoom, keyboard-only navigation, and screen-reader modes without losing controls or inputs.
* Rationale: Ensures digital accessibility compliance (AODA) and usability across diverse transit rider devices.
* Verification Idea: Test core workflows at 320 px width and with screen-reader emulators; confirm zero horizontal scroll overflow and visible error associations.
* Dependencies: Constrains SR-001, SR-003, SR-006, QR-015.

### Issue #25: [FR-012] Claim notification outcomes
* Legacy ID: R-026
* Typed ID: FR-012
* Labels: type:functional, status:accepted, priority:should, quality:reliability
* Goal Link: G-40 (Passenger participation), G-45 (Delivered notifications)
* Statement: For an eligible claim event, the system shall queue an update through a permitted claimant channel, record attempt history and provider outcomes, and suppress obsolete messages prior to retry.
* Rationale: Provides reliable rider updates without treating message dispatch as confirmed delivery.
* Verification Idea: Simulate provider delivery failure and status change; verify obsolete notification is suppressed and failure is logged for staff review.
* Dependencies: Requires FR-003, SR-003; constrained by QR-012, QR-014.

### Issue #26: [FR-013] Acknowledged in-person return
* Legacy ID: R-027
* Typed ID: FR-013
* Labels: type:functional, status:accepted, priority:must, analysis:goal-linked
* Goal Link: G-30 (Property returns), G-31 (Completed pickup)
* Statement: The system shall mark an in-person return completed only after authorized staff record actual handover time, staff identity, claimant acknowledgment, and the verified identity-check method.
* Rationale: Distinguishes ownership approval from actual physical handover; prevents unrecorded property release.
* Verification Idea: Attempt transition to Returned without staff ID or acknowledgment; assert transaction blocked; record valid handover and confirm item archived.
* Dependencies: Requires BR-002, FR-007, FR-014; constrained by QR-001, QR-011, QR-016.

### Issue #27: [SR-006] Catalogue search and filtering
* Legacy ID: R-028
* Typed ID: SR-006
* Labels: type:stakeholder, status:accepted, priority:should, analysis:conflict
* Goal Link: G-26 (Passenger discovery)
* Statement: The system shall allow passengers to search the public catalogue by category, transit line or station, date range, and descriptive keywords, executing searches strictly over approved public fields.
* Rationale: Makes public browsing practical without exposing private verification attributes in search results.
* Verification Idea: Query catalogue with keywords contained in private serial number fields; confirm private fields yield no matching results or leaked snippets.
* Dependencies: Requires SR-005; constrained by QR-003, QR-009, QR-010.

### Issue #28: [FR-014] Disputed-claim release block
* Legacy ID: R-029
* Typed ID: FR-014
* Labels: type:functional, status:accepted, priority:must, analysis:conflict
* Goal Link: G-20 (Fair ownership decisions), G-22 (Authorized release), G-23 (Fair review)
* Statement: When authorized staff record two or more unresolved claims to the same item as competing, the system shall block release until an authorized supervisor records a reasoned resolution within 3 business days.
* Rationale: Prevents wrongful property handover when multiple passengers claim identical lost belongings.
* Verification Idea: Record two competing claims on an inventory item; verify release button is disabled; submit supervisor resolution and verify release is unlocked only with valid approval.
* Dependencies: Requires FR-003; constrains BR-002, FR-013; constrained by QR-001, QR-003, QR-011.

### Issue #29: [FR-015] Accessible clarification follow-up
* Legacy ID: R-030
* Typed ID: FR-015
* Labels: type:functional, status:accepted, priority:should, analysis:conflict
* Goal Link: G-20 (Fair ownership decisions), G-23 (Fair review)
* Statement: For claims needing clarification, the system shall record telephone or an approved accessible alternative contact attempt, set a due time of 5 business days for response, flag overdue follow-up, and escalate unreachable claimants to a named owner rather than automatically rejecting the claim.
* Rationale: Prevents unfair immediate rejection of vague loss reports while giving claimants adequate response time.
* Verification Idea: Advance system time past 5 business days without response; verify claim is flagged for staff review and not automatically rejected.
* Dependencies: Requires FR-003; constrained by QR-001, QR-009, QR-014.

---

## 2. New Requirements to Create as Issues

### New Issue: [FR-016] Passenger candidate referral
* Typed ID: FR-016
* Labels: type:functional, status:accepted, priority:should, analysis:goal-linked
* Goal Link: G-26 (Passenger discovery), G-21 (Candidate review)
* Statement: The system shall allow an authenticated or contact-verified claimant to associate a selected public catalogue item with their loss report for staff ownership review without exposing private item evidence or granting approval.
* Rationale: Connects passenger catalogue discovery directly to staff verification workflow without compromising fraud safeguards.
* Verification Idea: Associate public catalogue item with report; verify link is created in staff review queue; confirm claimant gains zero access to private verification notes.
* Dependencies: Requires SR-001, SR-003, SR-005; feeds FR-003; constrained by QR-003, QR-015.

### New Issue: [QR-004] Policy-based personal-data retention
* Typed ID: QR-004
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: The system shall apply category-specific retention rules, purge claimant contact detail at claim closure, and retain case material and minimal audit records for 90 calendar days after closure before automated purge, unless suspended by an active authorized dispute hold.
* Rationale: Enforces compliance with Ontario MFIPPA statutory data minimization while preserving records for dispute resolution.
* Verification Idea: Simulate claim closure; verify contact details removed immediately; advance clock 90 days; verify automated purge removes case records unless dispute hold is active.
* Dependencies: Constrained by QR-001; constrains BR-001, FR-009.

### New Issue: [QR-005] Payment-card data minimization
* Typed ID: QR-005
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: The system shall prevent full payment card numbers from being persisted in free-text fields, notes, or logs, retaining at most card issuer and the last four digits. Card images shall be obscured per the approved redaction checklist prior to publication.
* Rationale: Enforces PCI-DSS and privacy standards, preventing accidental exposure of passenger financial credentials.
* Verification Idea: Attempt pasting 16-digit card number into staff verification notes; assert system sanitizes text to issuer and last 4 digits; inspect published card images to confirm full number is obscured.
* Dependencies: Constrains SR-001, FR-001, FR-003, SR-005.

### New Issue: [QR-006] Protected transmission
* Typed ID: QR-006
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: The system shall transmit protected data only over encrypted, authenticated connections using approved security configurations, failing closed without plaintext fallback if security cannot be established.
* Rationale: Protects passenger personal data across network boundaries and external integration channels.
* Verification Idea: Attempt connection with invalid TLS credentials; assert transaction terminates with zero plaintext transmission.
* Dependencies: Constrains SR-003, FR-012, FR-010, FR-011.

### New Issue: [QR-007] Protected stored information
* Typed ID: QR-007
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: The system shall encrypt protected claimant data and ownership evidence at rest, storing encryption keys separately from the data stores they protect.
* Rationale: Protects database backups and archives against unauthorized inspection.
* Verification Idea: Inspect exported database records and backups; verify claimant data is encrypted; confirm ordinary application roles cannot retrieve decryption keys.
* Dependencies: Constrains BR-001, QR-004.

### New Issue: [QR-010] Responsive passenger operations
* Typed ID: QR-010
* Labels: type:quality, status:accepted, priority:should, quality:performance
* Goal Link: G-40 (Passenger participation), G-43 (Dependable access)
* Statement: The system shall complete catalogue searches and status inquiries within 2 seconds for 95% of requests and within 5 seconds for 99% of requests at the service boundary under baseline workload.
* Rationale: Bounds interactive waiting times for passengers checking reports or searching recovered items.
* Verification Idea: Run automated performance test suite under baseline concurrency; compute 95th and 99th percentile response latencies; assert targets met.
* Dependencies: Constrains SR-001, SR-002, SR-003, SR-006.

### New Issue: [QR-011] Consistent recovery records
* Legacy ID: None
* Typed ID: QR-011
* Labels: type:quality, status:accepted, priority:must, quality:reliability
* Goal Link: G-10 (Custody accountability), G-13 (Clear handover responsibility), G-22 (Authorized release)
* Statement: The system shall enforce idempotency and concurrency controls across custody and release operations, ensuring duplicate requests or retries do not create multiple handovers, release records, or split custody states.
* Rationale: Prevents race conditions and retry operations from corrupting custody audit trails or releasing property twice.
* Verification Idea: Send concurrent release requests for the same item; confirm exactly one succeeds and subsequent requests are rejected.
* Dependencies: Constrains SR-004, FR-007, FR-013, FR-014, BR-002.

### New Issue: [QR-012] Reliable notification processing
* Typed ID: QR-012
* Labels: type:quality, status:accepted, priority:should, quality:reliability
* Goal Link: G-40 (Passenger participation), G-45 (Delivered notifications)
* Statement: The system shall track notification delivery states, distinguish confirmed delivery from provider failure, and recheck current claim status before sending to suppress superseded messages.
* Rationale: Prevents sending outdated collection notices when a claim has transitioned to disputed or returned.
* Verification Idea: Transition claim to disputed while notification is queued; verify worker suppresses notification before dispatch.
* Dependencies: Requires FR-012, SR-003, FR-014; constrained by QR-014.

### New Issue: [QR-013] Useful candidate discovery
* Typed ID: QR-013
* Labels: type:quality, status:accepted, priority:should, quality:functional-appropriateness
* Goal Link: G-20 (Fair ownership decisions), G-21 (Candidate review), G-25 (Staff-assisted discovery)
* Statement: Under pilot test conditions, the candidate ranking algorithm shall place the genuine matching item within the top 5 candidates for at least 18 of 20 test reports in each completeness group.
* Rationale: Establishes an empirical retrieval benchmark to ensure algorithmic matching produces actionable shortlists for staff.
* Verification Idea: Run ranking algorithm against benchmark corpus of 100 recovered items with 20 test loss reports; verify top-5 hit rate exceeds 90%.
* Dependencies: Constrains FR-002, SR-001.

### New Issue: [QR-014] Permission for optional contact
* Typed ID: QR-014
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use)
* Statement: The system shall record explicit channel-specific consent before dispatching optional automated notifications; withdrawal of consent shall immediately halt messages without disabling portal lookup.
* Rationale: Ensures passenger contact details are not utilized for optional messaging without affirmative permission.
* Verification Idea: Withdraw notification consent; trigger claim status update; confirm zero automated messages dispatched while portal lookup continues to operate.
* Dependencies: Constrains FR-012, FR-015; links to SR-003.

### New Issue: [QR-015] Resistance to automated misuse
* Typed ID: QR-015
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-40 (Passenger participation), G-42 (Private information use), G-43 (Dependable access)
* Statement: The system shall restrict unauthenticated verification attempts to 5 failures per 15 minutes and new submissions to 10 per 10 minutes per claimant reference, maintaining active sessions and providing a staff-assisted unlock route.
* Rationale: Mitigates automated scraping and credential guessing while avoiding lockouts for riders sharing municipal Wi-Fi.
* Verification Idea: Trigger 5 failed verification attempts; assert 6th is rejected with rate-limit response; verify phone triage staff unlock restores access.
* Dependencies: Constrains SR-001, SR-003, FR-016; constrained by QR-009.

### New Issue: [QR-016] Minimum necessary ownership evidence
* Typed ID: QR-016
* Labels: type:quality, status:accepted, priority:must, quality:security
* Goal Link: G-20 (Fair ownership decisions), G-22 (Authorized release), G-42 (Private information use)
* Statement: The system shall collect and retain only evidence fields required for ownership verification, storing staff identity-verification checks without preserving full copies of government identity documents.
* Rationale: Upholds data minimization under privacy standards by avoiding retention of reusable identity document scans.
* Verification Idea: Verify return record logs staff verification of claimant ID type and match without requiring an uploaded scan or photo of the ID card.
* Dependencies: Constrains FR-003, FR-013, SR-001.

