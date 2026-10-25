# Sprint 1 GitHub Issues Tracking and Migration Plan

**Repository:** `EECS4312F26/eecs4312-project-group-11`  
**Purpose:** Rough work documenting updates for existing candidate issues and complete templates for new Baseline v1.0 issues.  
**Note:** Do not execute terminal commands to modify or create GitHub issues until the team authorizes submission.

---

## 1. Existing Issues Status and Planned Updates

The repository currently contains 15 issues created during Sprint 0. All 15 issues currently hold the label `status:candidate`. For Sprint 1 Baseline v1.0, their label must be updated to `status:accepted`, and their issue descriptions should be aligned with the refined baseline statements.

| Issue # | Stable ID | Typed ID | Current Title | Planned Label Update | Action Required |
|---|---|---|---|---|---|
| [#2](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/2) | R-001 | BR-001 | [R-001] Centralized and Traceable Item Records | `status:accepted` | Update description to reference complete lifecycle audit history. |
| [#3](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/3) | R-002 | BR-002 | [R-002] Legitimate Item Recovery | `status:accepted` | Clarify separation between candidate matching and verification approval. |
| [#4](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/4) | R-003 | SR-001 | [R-003] Lost-Item Report Submission | `status:accepted` | Add explicit note that vehicle ID is optional per ELIC-03 S-01. |
| [#5](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/5) | R-004 | SR-002 | [R-004] Submission Confirmation and Tracking Reference | `status:accepted` | Ensure token generation is specified as immediate. |
| [#6](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/6) | R-005 | SR-003 | [R-005] Check Report Status | `status:accepted` | Clarify dual authentication: reference token + verified contact info. |
| [#7](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/7) | R-006 | FR-001 | [R-006] Operator Found-Item Intake | `status:accepted` | Note barcode assignment at frontline intake. |
| [#8](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/8) | R-007 | SR-004 | [R-007] Station CSA Custody Transfer | `status:accepted` | Explicitly include custody acknowledgment receipt. |
| [#9](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/9) | R-008 | FR-002 | [R-008] Candidate Match Ranking | `status:accepted` | Clarify algorithmic score sorting per Decision D-004. |
| [#10](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/10) | R-009 | FR-003 | [R-009] Ownership Verification Decision Record | `status:accepted` | Expand to include intermediate Pending Telephone Triage state. |
| [#11](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/11) | R-010 | FR-004 | [R-010] Urgent Property Classification | `status:accepted` | List categories: medication, passports, keys, mobility aids. |
| [#12](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/12) | R-013 | SR-005 | [R-013] Privacy-Bounded Public Catalog | `status:accepted` | Specify exclusion of unpublicized verification attributes. |
| [#13](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/13) | R-014 | FR-007 | [R-014] Physical Storage Assignment | `status:accepted` | Ensure single active physical location constraint is highlighted. |
| [#14](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/14) | R-016 | FR-009 | [R-016] Final Item Disposition | `status:accepted` | Add immediate police escalation path for items valued >= $1,000. |
| [#15](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/15) | R-019 | QR-001 | [R-019] Staff Audit Logging | `status:accepted` | Pair with auditable action enum per Lab 6 findings. |
| [#16](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/16) | R-021 | QR-003 | [R-021] Role-Based Access Control | `status:accepted` | Confirm role definitions: Operator, CSA, Claims Officer, Admin. |
| [#17](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17) | R-011 | FR-005 | [R-011] Expedited Verification Queue | `status:accepted` | **Created on Oct 25.** Active in Sprint 1 Baseline. |
| [#18](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/18) | R-012 | FR-006 | [R-012] High-Priority Staff Notification | `status:accepted` | **Created on Oct 25.** Active in Sprint 1 Baseline. |

---

## 2. GitHub Issues Creation Status (11 Remaining)

Requirements **R-011** ([#17](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17)) and **R-012** ([#18](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/18)) have been created. The remaining 11 requirements below are accepted into Baseline v1.0 and ready for creation when authorized.

### Issue 1: [R-011] Expedited Verification Queue — CREATED ([#17](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17))
- **Status:** Created (`status:accepted`, `type:functional`, `priority:should`)
- **URL:** https://github.com/EECS4312F26/eecs4312-project-group-11/issues/17
- **Body:**
  ```markdown
  ### Requirement Statement
  When an item or report is classified as urgent, the system shall position its verification task ahead of standard items in the staff review queue according to priority rules.

  ### Metadata
  - **Typed ID:** FR-005
  - **Source:** ELIC-02 SYS-01; Sprint 0 Backlog
  - **Stakeholder:** Lost & Found Claims Officer, Passenger
  - **Rationale:** High-impact items cause severe passenger distress and require rapid staff attention.
  - **Verification:** Ingest standard and urgent items; verify staff task list orders urgent items at the top of the queue.
  ```

### Issue 2: [R-012] High-Priority Staff Notification — CREATED ([#18](https://github.com/EECS4312F26/eecs4312-project-group-11/issues/18))
- **Status:** Created (`status:accepted`, `type:functional`, `priority:should`)
- **URL:** https://github.com/EECS4312F26/eecs4312-project-group-11/issues/18
- **Body:**
  ```markdown
  ### Requirement Statement
  When an item classified as urgent enters central inventory, the system shall generate an automated notification alert to the on-duty claims verification officer within the same intake transaction.

  ### Metadata
  - **Typed ID:** FR-006
  - **Source:** Lost & Found Staff, Management; Sprint 0 Backlog
  - **Stakeholder:** Lost & Found Claims Officer
  - **Rationale:** Prevents urgent items from waiting in passive queues until staff manually refresh.
  - **Verification:** Intake an urgent item and assert an internal notification event is generated and delivered to active staff session.
  ```

### Issue 3: [R-015] Central Processing Delay Notice
- **Type:** `type:functional`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  The system shall display a standardized advisory notice on the public reporting portal and status views informing claimants that recovered items require 24 to 48 hours for central transfer and logging.

  ### Metadata
  - **Typed ID:** FR-008
  - **Source:** ELIC-01 PF-01; ELIC-02 SYS-01
  - **Stakeholder:** Passenger, Management
  - **Rationale:** Sets realistic expectations to reduce avoidable passenger phone inquiries while items are in transit.
  - **Verification:** Inspect submission form and status page to confirm explanatory 24–48 hour intake latency text is visible.
  ```

### Issue 4: [R-017] Remote Courier Dispatch Record
- **Type:** `type:functional`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  When an approved claimant requests remote return, the system shall create a dispatch record containing approved delivery address, designated logistics courier, and dispatch tracking state.

  ### Metadata
  - **Typed ID:** FR-010
  - **Source:** ELIC-01 PF-04; ELIC-02 SYS-02
  - **Stakeholder:** Claimant, Courier Partner
  - **Rationale:** Supports remote return for passengers unable to travel to the central facility.
  - **Verification:** Trigger remote delivery flow; verify dispatch record is generated with carrier reference and address fields.
  ```

### Issue 5: [R-018] Remote Delivery Fee Settlement Gate
- **Type:** `type:functional`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  When remote delivery requires payment, the system shall lock the item state and prevent status transition to Released to Carrier until payment confirmation is recorded from the payment service.

  ### Metadata
  - **Typed ID:** FR-011
  - **Source:** Claimant, Payment Gateway; Lab 5 Handout; Sprint 0
  - **Stakeholder:** Lost & Found Staff, Finance
  - **Rationale:** Protects the transit authority from shipping costs for uncollected carrier fees.
  - **Verification:** Attempt carrier release API call with payment status Unpaid; assert system rejects status change with error.
  ```

### Issue 6: [R-020] Claimant PII Retention and Masking
- **Type:** `type:quality`
- **Priority:** `priority:must`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  The system shall enforce data retention policies by anonymizing or purging resolved claim records after the approved retention period, and shall mask payment card numbers in staff notes, recording only card issuer and last 4 digits.

  ### Metadata
  - **Typed ID:** QR-002
  - **Source:** Privacy Officer (MFIPPA); ELIC-02 SYS-01; Lab 5 Criterion 5; Lab 6 Activity B
  - **Stakeholder:** Privacy Officer, Passenger
  - **Rationale:** Complies with privacy statutes and PCI-DSS requirements to prevent data breaches.
  - **Verification:** Attempt to paste a 16-digit card number into staff verification notes; assert system sanitizes text to issuer and last 4 digits.
  ```

### Issue 7: [R-024] Public Web Service Availability
- **Type:** `type:quality`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  The public web portal for report filing and status inquiries shall achieve at least 99.5% monthly uptime during scheduled operational periods, excluding pre-announced maintenance windows.

  ### Metadata
  - **Typed ID:** CON-001
  - **Source:** Passenger; IT Infrastructure; ELIC-02 SYS-01; Sprint 0 Backlog
  - **Stakeholder:** Passenger, TTC IT
  - **Rationale:** Riders report lost items at all hours, including weekends when the physical desk is closed.
  - **Verification:** Review automated ping/uptime monitoring telemetry over a 30-day simulated deployment interval.
  ```

### Issue 8: [R-025] Responsive Mobile Viewport Layout
- **Type:** `type:constraint`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  All public passenger workflows (report submission, catalog browsing, and status tracking) shall render without horizontal scrolling or functional truncation on mobile viewports down to a minimum width of 320 pixels.

  ### Metadata
  - **Typed ID:** CON-002
  - **Source:** Passenger; Usability; Lab 6 Activity A; Sprint 0 Backlog
  - **Stakeholder:** Passenger (Mobile Users)
  - **Rationale:** High proportion of transit users submit reports immediately from smartphones while traveling.
  - **Verification:** Run automated Playwright tests at viewport widths 320 px, 375 px, and 414 px; assert zero horizontal scroll overflow.
  ```

### Issue 9: [R-026] Automated Claim Status Notifications
- **Type:** `type:functional`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  The system shall dispatch an automated notification message via email or SMS to the claimant whenever their report status transitions to Match Found, Claim Approved, or Item Ready for Pickup.

  ### Metadata
  - **Typed ID:** FR-012
  - **Source:** Claimant; ELIC-01 PF-01; Sprint 0 Backlog; Lab 5
  - **Stakeholder:** Claimant, Lost & Found Staff
  - **Rationale:** Reduces repetitive status check calls and ensures claimants are informed promptly.
  - **Verification:** Update claim status to Ready for Pickup; assert simulated notification service receives outbound message payload.
  ```

### Issue 10: [R-027] In-Person Pickup Receipt Acknowledgment
- **Type:** `type:functional`
- **Priority:** `priority:must`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  When an approved item is released in person at the central facility, the system shall record collection timestamp, verifying staff ID, claimant signature acknowledgment, and presented government ID type before marking item Returned.

  ### Metadata
  - **Typed ID:** FR-013
  - **Source:** Lost & Found Staff; Claimant; Lab 5 UC-04; Lab 6 Clinic Priority 1
  - **Stakeholder:** Claims Officer, Transit Management
  - **Rationale:** Corrects the Sprint 0 text duplicate and legally closes the chain of custody for in-person handoffs.
  - **Verification:** Complete pickup flow with empty signature and ID fields; assert system refuses to mark item Returned.
  ```

### Issue 11: [R-028] Public Catalog Search and Filter
- **Type:** `type:functional`
- **Priority:** `priority:could`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  The public catalog interface shall allow claimants to filter displayed items by category, transit line/station, and date range, or enter descriptive text keywords to find candidate matches.

  ### Metadata
  - **Typed ID:** SR-006
  - **Source:** Passenger Needs; ELIC-01 PF-02; Sprint 0 Backlog
  - **Stakeholder:** Passenger
  - **Rationale:** Helps passengers discover whether their item was turned in without waiting for manual staff matching.
  - **Verification:** Filter by category Backpack and date range; verify results contain only records matching both criteria.
  ```

### Issue 12: [R-029] Disputed Claim Lock Mechanism
- **Type:** `type:functional`
- **Priority:** `priority:must`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  When two or more claimants file matching claims for the same recovered item and neither provides decisive proof, the system shall transition the item to Claim Disputed and block release to any party until supervisor review is logged.

  ### Metadata
  - **Typed ID:** FR-014
  - **Source:** Lost & Found Staff; Management; ELIC-03 S-03; Lab 5 Criterion 3
  - **Stakeholder:** Claims Officer, Legal / Risk Management
  - **Rationale:** Prevents accidental or fraudulent release when identical claims compete for high-value items.
  - **Verification:** Associate second claim to an item with an existing pending claim; assert status changes to Claim Disputed and release button is disabled.
  ```

### Issue 13: [R-030] Telephone Triage Follow-Up Management
- **Type:** `type:functional`
- **Priority:** `priority:should`
- **Status:** `status:accepted`
- **Body:**
  ```markdown
  ### Requirement Statement
  When a claim description is vague, the system shall permit staff to log outbound telephone inquiry attempts and set a 48-hour follow-up window before allowing claim rejection.

  ### Metadata
  - **Typed ID:** FR-015
  - **Source:** Lost & Found Staff; ELIC-03 S-01; Lab 5 Exception 2a; Lab 6 Activity B
  - **Stakeholder:** Claims Officer, Claimant
  - **Rationale:** Supports operational reality that generic reports require telephone outreach before being discarded.
  - **Verification:** Log telephone outreach event; verify follow-up expiration timestamp is set 48 hours in future and claim status updates to Pending Triage.
  ```

---

## 3. Terminal Execution Script (For Later Authorization)

*The following commands are documented for reference and must not be run until authorized:*

```bash
# Update existing 15 issues from candidate to accepted
for id in {2..16}; do
  gh issue edit $id --repo EECS4312F26/eecs4312-project-group-11 --add-label "status:accepted" --remove-label "status:candidate"
done

# Create new issues (13 items)
gh issue create --repo EECS4312F26/eecs4312-project-group-11 --title "[R-011] Expedited Verification Queue" --body "..." --label "type:functional,priority:should,status:accepted"
gh issue create --repo EECS4312F26/eecs4312-project-group-11 --title "[R-012] High-Priority Staff Notification" --body "..." --label "type:functional,priority:should,status:accepted"
# ... and remaining items through R-030
```
