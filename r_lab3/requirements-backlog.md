# Requirements Backlog

## Public Transit Lost & Found System

---

> **Note:** All requirements below are **candidate** requirements as of Sprint 0. They are preliminary and expected to change during later sprints. Requirements marked as assumptions have not been validated with real stakeholders.

---

## Backlog Summary

| Type | Count |
|---|---|
| Business / Stakeholder | 4 |
| Functional | 10 |
| Quality (Non-Functional) | 4 |
| Constraint / Compliance | 2 |
| **Total** | **20** |

---

## Requirements

### R1 – Centralized Lost-Property Records

| Field | Value |
|---|---|
| **ID** | R1 |
| **Title** | Centralized Lost-Property Records |
| **Statement** | The system shall maintain a single, searchable record of lost-item reports and found-item records handled through the system. |
| **Type** | Business Requirement |
| **Stakeholder / Source** | Transit Management, Lost & Found Staff |
| **Rationale** | Prevents information from being distributed across disconnected records (phone logs, paper notebooks, spreadsheets). |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#1 — Centralized Lost-Property Records](../../issues/1) |

---

### R2 – Item Traceability

| Field | Value |
|---|---|
| **ID** | R2 |
| **Title** | Item Traceability |
| **Statement** | The system shall maintain the current processing state of each found-item record from intake until return, disposal, or other final disposition. |
| **Type** | Business Requirement |
| **Stakeholder / Source** | Transit Management |
| **Rationale** | Supports accountability and operational tracking throughout the item lifecycle. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#2 — Item Traceability](../../issues/2) |

---

### R3 – Support Item Recovery

| Field | Value |
|---|---|
| **ID** | R3 |
| **Title** | Support Item Recovery |
| **Statement** | The system shall support comparison of passenger lost-item reports with records of items received by the transit agency. |
| **Type** | Stakeholder Requirement |
| **Stakeholder / Source** | Passenger, Lost & Found Staff |
| **Rationale** | The primary business objective is reconnecting lost property with legitimate owners. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#3 — Support Item Recovery](../../issues/3) |

---

### R4 – Prevent Unauthorized Release

| Field | Value |
|---|---|
| **ID** | R4 |
| **Title** | Prevent Unauthorized Release |
| **Statement** | The system shall support ownership verification before a found item is recorded as returned to a claimant. |
| **Type** | Stakeholder Requirement |
| **Stakeholder / Source** | Passenger, Management, Lost & Found Staff |
| **Rationale** | Reduces the risk of property being released to the wrong person. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#4 — Prevent Unauthorized Release](../../issues/4) |

---

### R5 – Submit Lost-Item Report

| Field | Value |
|---|---|
| **ID** | R5 |
| **Title** | Submit Lost-Item Report |
| **Statement** | The system shall allow a passenger to submit a lost-item report. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger |
| **Rationale** | Provides the starting point for a passenger seeking a lost item. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#5 — Submit Lost-Item Report](../../issues/5) |

---

### R6 – Record Lost-Item Details

| Field | Value |
|---|---|
| **ID** | R6 |
| **Title** | Record Lost-Item Details |
| **Statement** | A lost-item report shall record an item category, description, approximate loss date, approximate loss location, and passenger contact method. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger, Lost & Found Staff |
| **Rationale** | These attributes provide basic information needed to investigate a loss. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#6 — Record Lost-Item Details](../../issues/6) |

---

### R7 – Optional Transit Details

| Field | Value |
|---|---|
| **ID** | R7 |
| **Title** | Optional Transit Details |
| **Statement** | The system shall allow a passenger to provide route, vehicle, station, direction of travel, and approximate time when known. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger |
| **Rationale** | Passengers may know some transit details but should not be prevented from reporting when they do not. Additional details improve matching accuracy. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#7 — Optional Transit Details](../../issues/7) |

---

### R8 – Final Item Disposition

| Field | Value |
|---|---|
| **ID** | R8 |
| **Title** | Final Item Disposition |
| **Statement** | The system shall allow authorized staff to record the final disposition of an unclaimed item (returned, donated, disposed, transferred to police). |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Lost & Found Staff, Management |
| **Rationale** | Items may eventually leave the active lost-and-found process without being claimed. The system must record what happened. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#8 — Final Item Disposition](../../issues/8) |

---

### R9 – Claim Tracking Identifier

| Field | Value |
|---|---|
| **ID** | R9 |
| **Title** | Claim Tracking Identifier |
| **Statement** | The system shall generate and provide a unique tracking reference code to a passenger upon successful submission of a lost-item report. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger |
| **Rationale** | Enables passengers to look up and reference their specific inquiry without submitting duplicates. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#9 — Claim Tracking Identifier](../../issues/9) |

---

### R10 – Check Report Status

| Field | Value |
|---|---|
| **ID** | R10 |
| **Title** | Check Report Status |
| **Statement** | The system shall allow a passenger to look up the current processing state of their lost-item report using their tracking reference code and contact information. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger |
| **Rationale** | Reduces repetitive phone calls and counter visits by providing self-serve progress updates. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#10 — Check Report Status](../../issues/10) |

---

### R11 – Rapid Operator Intake

| Field | Value |
|---|---|
| **ID** | R11 |
| **Title** | Rapid Operator Intake |
| **Statement** | The system shall provide a streamlined intake form allowing frontline staff to log a found item using minimal required fields (date, route/station, broad category). |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Transit Operator |
| **Rationale** | Ensures shift drivers and station collectors can hand off property quickly without delaying schedules. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#11 — Rapid Operator Intake](../../issues/11) |

---

### R12 – Redacted Public Search

| Field | Value |
|---|---|
| **ID** | R12 |
| **Title** | Redacted Public Search |
| **Statement** | The system shall display a public catalog of recently found items while automatically redacting sensitive identifiers (e.g., serial numbers, full names, specific bag contents). |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Passenger, Management |
| **Rationale** | Allows passengers to browse found items and recognize their property without exposing private details that could enable fraudulent claims. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#12 — Redacted Public Search](../../issues/12) |

---

### R13 – Physical Storage Assignment

| Field | Value |
|---|---|
| **ID** | R13 |
| **Title** | Physical Storage Assignment |
| **Statement** | The system shall record the physical storage location (e.g., bin, shelf, or locker identifier at Bay Station) for each cataloged found item. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Lost & Found Staff |
| **Rationale** | Prevents items from being misplaced inside the holding facility and speeds up retrieval during customer pickup. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#13 — Physical Storage Assignment](../../issues/13) |

---

### R14 – Intake Latency Notice

| Field | Value |
|---|---|
| **ID** | R14 |
| **Title** | Intake Latency Notice |
| **Statement** | The system shall display a clear notice informing passengers that items turned in on vehicles may take up to 24–48 hours to be processed at the central office. |
| **Type** | Functional Requirement / Usability |
| **Stakeholder / Source** | Passenger, Management |
| **Rationale** | Sets realistic expectations and prevents false assumptions that an unlisted item was permanently lost. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#14 — Intake Latency Notice](../../issues/14) |

---

### R15 – Staff Audit Logging

| Field | Value |
|---|---|
| **ID** | R15 |
| **Title** | Staff Audit Logging |
| **Statement** | The system shall record which staff member created, updated, or marked an item as returned or disposed of, along with a timestamp. |
| **Type** | Functional Requirement |
| **Stakeholder / Source** | Management |
| **Rationale** | Maintains an immutable chain of custody and accountability for internal operations. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#15 — Staff Audit Logging](../../issues/15) |

---

### R16 – Claim Data Retention & Purging

| Field | Value |
|---|---|
| **ID** | R16 |
| **Title** | Claim Data Retention & Purging |
| **Statement** | The system shall automatically anonymize or purge personal contact and identity information from resolved reports after a defined retention window (e.g., 90 days). |
| **Type** | Quality / Compliance (Non-Functional) |
| **Stakeholder / Source** | Management, Passenger |
| **Rationale** | Ensures compliance with Ontario municipal privacy legislation (MFIPPA) by not holding PII indefinitely. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#16 — Claim Data Retention & Purging](../../issues/16) |

---

### R17 – System Availability

| Field | Value |
|---|---|
| **ID** | R17 |
| **Title** | System Availability |
| **Statement** | The public-facing portal (lost-item reporting, status checking, found-item browsing) shall be available 24/7 with at least 99.5% uptime measured monthly. |
| **Type** | Quality Requirement (Non-Functional) |
| **Stakeholder / Source** | Passenger, Management |
| **Rationale** | Passengers may realize they lost an item at any time of day. Unlike the current phone line (Mon–Fri 12–5 PM), the digital system should not restrict when reports can be submitted. **[Assumption]** — the 99.5% target is a team assumption and requires validation with TTC IT. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#17 — System Availability](../../issues/17) |

---

### R18 – Passenger Data Privacy

| Field | Value |
|---|---|
| **ID** | R18 |
| **Title** | Passenger Data Privacy |
| **Statement** | The system shall encrypt all personal information (contact details, identity documents) in transit and at rest. |
| **Type** | Quality Requirement (Non-Functional) |
| **Stakeholder / Source** | Management, Passenger |
| **Rationale** | Protects passenger PII from unauthorized access and supports compliance with MFIPPA and TTC data security policies. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#18 — Passenger Data Privacy](../../issues/18) |

---

### R19 – Role-Based Access Control

| Field | Value |
|---|---|
| **ID** | R19 |
| **Title** | Role-Based Access Control |
| **Statement** | The system shall enforce role-based access control so that passengers, transit operators, Lost & Found staff, and transit management each have access only to functions and data appropriate to their role. |
| **Type** | Quality Requirement (Non-Functional) |
| **Stakeholder / Source** | Management |
| **Rationale** | Prevents unauthorized access to sensitive data and ensures staff can only perform actions within their job function. |
| **Priority** | Must |
| **Status** | Candidate |
| **GitHub Issue** | [#19 — Role-Based Access Control](../../issues/19) |

---

### R20 – Mobile-Responsive Interface

| Field | Value |
|---|---|
| **ID** | R20 |
| **Title** | Mobile-Responsive Interface |
| **Statement** | The passenger-facing portal shall be fully functional on mobile devices with screen widths as small as 320px. |
| **Type** | Constraint |
| **Stakeholder / Source** | Passenger |
| **Rationale** | **[Assumption]** Most passengers will report lost items from a smartphone. The interface must be usable without a desktop computer. |
| **Priority** | Should |
| **Status** | Candidate |
| **GitHub Issue** | [#20 — Mobile-Responsive Interface](../../issues/20) |

---

## Priority Distribution

| Priority | Requirements |
|---|---|
| **Must** | R1, R2, R3, R4, R5, R6, R8, R9, R10, R13, R15, R16, R18, R19 |
| **Should** | R7, R11, R12, R14, R17, R20 |
| **Could** | *(none yet — expected to emerge in Sprint 1)* |

---

## Type Distribution

| Type | Requirements |
|---|---|
| **Business** | R1, R2 |
| **Stakeholder** | R3, R4 |
| **Functional** | R5, R6, R7, R8, R9, R10, R11, R12, R13, R14, R15 |
| **Quality (Non-Functional)** | R16, R17, R18, R19 |
| **Constraint** | R20 |
