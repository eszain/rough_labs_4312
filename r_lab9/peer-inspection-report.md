# Lab 9: Cross-Team Requirements Inspection

## Activity A: Review Pairing and Inspection Packet

* Reviewing Team: Group 11 (Mohammad Zain Al Syed, Muhammad Sufyan, Anirudh Sundar)
* Inspected Team: Hospital Systems Team (Emergency Triage and Queue Optimization)
* Inspected Artifacts: Requirements Baseline (FR01 to FR31, Issues #6 to #73), Goal Tree (GL-1 to GL-4), Triage Queue Model.
* Defect Taxonomy Used: Ambiguity, Omission, Inconsistency / Contradiction, Unverifiability, Premature Design, Missing Parameter, Audit / Traceability Gap.
* Discussion Record: Conducted reviewer and author discussion during the in-lab period (4:42 PM - 4:52 PM) to clarify findings without negotiating away valid defects.

## Activity B: Consolidated Inspection Findings

We record five substantive findings covering core functional, clinical safety, queue ordering, and notification requirements:

1. FR13 vs. FR31: State Contradiction in Condition Updates
* Location: FR13 (Priority Recalculation, Issue #45) vs. FR31 (Hold Updates for Review, Issue #73).
* Defect Type: Contradiction / Inconsistency.
* Severity: Critical.
* Explanation: FR13 mandates immediate automatic priority recalculation upon receiving a non-urgent patient condition update, whereas FR31 mandates holding routine updates until clinical staff review them. The system cannot recalculate queue order upon submission if updates are held.
* Actionable Correction: Define a staged transition: place updates in a "Pending Review" status, executing FR13 recalculation only after staff review and approval under FR31.

2. FR26 and FR27 vs. FR02: Clinical Safety Risk in Patient Removal
* Location: FR26 (Missed Call Move Back, Issue #68), FR27 (Removal After 5 Missed Calls, Issue #69) vs. FR02 (Symptom Tier Ordering, Issue #38).
* Defect Type: Clinical Safety Risk / Omission.
* Severity: Critical.
* Explanation: Automated queue demotion and removal do not evaluate patient acuity. If an unresponsive patient in a high-acuity tier (Tier 1 or 2 resuscitation/emergent) misses calls due to medical collapse in the waiting area, the system demotes and purges them without clinical staff awareness.
* Actionable Correction: Add an acuity guard condition: "Automated demotion and removal shall apply only to non-urgent tiers. Tiers 1 and 2 shall trigger an immediate staff welfare check instead of queue removal."

3. FR11: Unverifiable Estimated Wait-Time Calculation
* Location: FR11 (Estimated Wait-Time Range, Issue #42).
* Defect Type: Unverifiability / Ambiguity.
* Severity: High.
* Explanation: The requirement mandates an estimated wait-time range without defining calculation algorithms, update intervals, or confidence bounds. Because the queue shifts dynamically with emergency arrivals (FR06) and symptom tiers (FR02), an undefined range is untestable and misleading to patients.
* Actionable Correction: Specify an objective fit criterion: "The system shall recalculate the wait-time range within 60 seconds of any queue change, using historical service rates with a 90% confidence interval, accompanied by an emergency override disclaimer."

4. FR03 and FR07 vs. FR22: Priority Inconsistency and Audit Liability
* Location: FR03 (Queue Override, Issue #6), FR07 (Revert Override, Issue #60) vs. FR22 (Override Log, Issue #25).
* Defect Type: Priority Inconsistency / Audit Gap.
* Severity: High.
* Explanation: FR03 (Staff override) is Must-have, but FR22 (Override log) is only Should-have. Permitting staff to alter clinical triage priority without mandatory audit logging introduces major clinical safety and legal compliance liabilities. FR07 also permits reverting overrides without recording reasons.
* Actionable Correction: Promote FR22 to Must-have as a mandatory prerequisite for FR03 and FR07: "Every queue override or revert shall require clinician ID, timestamp, and a structured clinical rationale recorded prior to queue reordering."

5. FR15 and FR16: Missing Escalation Threshold Parameters
* Location: FR15 (Alert Stays Until Acknowledged, Issue #48) vs. FR16 (Escalate Unacknowledged Alerts, Issue #50).
* Defect Type: Missing Parameter / Unverifiable Timing.
* Severity: Medium.
* Explanation: FR16 mandates escalating unacknowledged emergency alerts but specifies neither the escalation time threshold nor the target role. Without explicit parameters, the escalation logic cannot be verified in acceptance testing.
* Actionable Correction: Add concrete parameters: "If an emergency alert remains unacknowledged for 120 seconds, the system shall escalate the alert visually and audibly to the on-duty Charge Nurse workstation."

## Activity C: Reviewer and Author Discussion and Receiving Team Disposition

During the in-lab discussion, the receiving team confirmed the defects and agreed to the following disposition for Sprint 3 Phase A:
* Accept (Critical / High): Findings 1, 2, and 4 will be incorporated directly into the Sprint 3 requirements baseline to fix state contradictions, protect high-acuity patients, and mandate override logging.
* Clarify (High): Finding 3 will be reviewed with emergency department clinical leadership to determine acceptable wait-time calculation formulas and patient disclaimer wording.
* Defer (Medium): Finding 5 escalation timing is accepted for requirements, while specific hardware paging integration is deferred to Sprint 3 architecture design.

