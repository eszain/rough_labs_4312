# GitHub Issues — Candidate Requirements

## Public Transit Lost & Found System

---

> **Instructions:** Create each issue below in your GitHub Classroom repository. Apply the specified labels to each issue. At Sprint 0, all issues should be in the **Candidate** column of your GitHub Project board.
>
> **Required Labels (create these first):**
> `type:business` · `type:stakeholder` · `type:functional` · `type:quality` · `type:constraint` · `status:candidate` · `status:accepted` · `status:rejected` · `priority:must` · `priority:should` · `priority:could` · `needs:clarification` · `needs:validation`

---

## Issue #1 — Centralized Lost-Property Records

**Labels:** `type:business`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall maintain a single, searchable record of lost-item reports and found-item records handled through the system.

**Source / Origin:** Transit Management, Lost & Found Staff

**Rationale:** Prevents information from being distributed across disconnected records (phone logs, paper notebooks, spreadsheets). A single source of truth is required for efficient operations.

**Priority:** Must

**Acceptance / Fit Idea:** Staff can search for any item record by category, date range, or description keywords and retrieve it within one interface.

**Dependencies / Related Requirements:** R2 (Item Traceability), R15 (Audit Logging)

**Unresolved Questions:** What are the exact search fields and filters needed? Should full-text search be supported or structured fields only?

---

## Issue #2 — Item Traceability

**Labels:** `type:business`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall maintain the current processing state of each found-item record from intake until return, disposal, or other final disposition.

**Source / Origin:** Transit Management

**Rationale:** Supports accountability and operational tracking throughout the item lifecycle. Management needs visibility into where each item stands in the process.

**Priority:** Must

**Acceptance / Fit Idea:** Every found-item record displays a current state from the defined lifecycle (Received → Cataloged → Matched → Claim Under Review → Verified → Returned/Disposed). State transitions are timestamped.

**Dependencies / Related Requirements:** R1 (Centralized Records), R8 (Final Disposition), R15 (Audit Logging)

**Unresolved Questions:** What are the exact state transitions? Can items move backward (e.g., from "Claim Under Review" back to "Cataloged" if a claim is rejected)?

---

## Issue #3 — Support Item Recovery

**Labels:** `type:stakeholder`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall support comparison of passenger lost-item reports with records of items received by the transit agency.

**Source / Origin:** Passenger, Lost & Found Staff

**Rationale:** The primary business objective is reconnecting lost property with legitimate owners. Without a comparison mechanism, staff must manually search through records.

**Priority:** Must

**Acceptance / Fit Idea:** When a new lost-item report or found-item record is entered, the system identifies and ranks potential matches based on shared attributes.

**Dependencies / Related Requirements:** R1 (Centralized Records), R6 (Lost-Item Details), R11 (Operator Intake)

**Unresolved Questions:** What matching algorithm is appropriate? What confidence threshold should trigger a notification to staff? Should matching run on submission or as a batch process?

---

## Issue #4 — Prevent Unauthorized Release

**Labels:** `type:stakeholder`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall support ownership verification before a found item is recorded as returned to a claimant.

**Source / Origin:** Passenger, Management, Lost & Found Staff

**Rationale:** Reduces the risk of property being released to the wrong person. High-value items especially require verification.

**Priority:** Must

**Acceptance / Fit Idea:** No found item can transition to "Returned" status without a staff member recording that ownership verification was completed and approved.

**Dependencies / Related Requirements:** R8 (Final Disposition), R15 (Audit Logging)

**Unresolved Questions:** What forms of proof are acceptable (description match, photos, serial numbers, receipts, ID)? What is the escalation process for disputed claims?

---

## Issue #5 — Submit Lost-Item Report

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall allow a passenger to submit a lost-item report.

**Source / Origin:** Passenger

**Rationale:** Provides the starting point for a passenger seeking a lost item. This is the primary passenger-facing function.

**Priority:** Must

**Acceptance / Fit Idea:** A passenger can complete and submit a lost-item report form from the public portal without creating an account.

**Dependencies / Related Requirements:** R6 (Lost-Item Details), R7 (Optional Transit Details), R9 (Tracking Code)

**Unresolved Questions:** Should passengers be required to create an account, or should submission be anonymous with a tracking code? Should there be a CAPTCHA to prevent spam?

---

## Issue #6 — Record Lost-Item Details

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
A lost-item report shall record an item category, description, approximate loss date, approximate loss location, and passenger contact method.

**Source / Origin:** Passenger, Lost & Found Staff

**Rationale:** These attributes provide the basic information needed to investigate a loss and attempt matching against found-item records.

**Priority:** Must

**Acceptance / Fit Idea:** Every submitted lost-item report contains at minimum: item category (from a predefined list), free-text description, date (±1 day), location (station or route), and at least one contact method (email or phone).

**Dependencies / Related Requirements:** R5 (Submit Report), R3 (Item Recovery)

**Unresolved Questions:** What item categories should be predefined? How granular should location be (station name vs. specific platform)?

---

## Issue #7 — Optional Transit Details

**Labels:** `type:functional`, `status:candidate`, `priority:should`

**Requirement Statement:**
The system shall allow a passenger to provide route, vehicle, station, direction of travel, and approximate time when known.

**Source / Origin:** Passenger

**Rationale:** Passengers may know some transit details but should not be prevented from reporting when they do not. Additional details improve matching accuracy when available.

**Priority:** Should

**Acceptance / Fit Idea:** The lost-item report form includes optional fields for route number, vehicle number, station, direction, and time. The form submits successfully whether these fields are filled or left blank.

**Dependencies / Related Requirements:** R5 (Submit Report), R6 (Lost-Item Details)

**Unresolved Questions:** Should the system provide auto-complete suggestions for route/station names? Should vehicle numbers be validated against TTC fleet data?

---

## Issue #8 — Final Item Disposition

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall allow authorized staff to record the final disposition of an unclaimed item (returned, donated, disposed, transferred to police).

**Source / Origin:** Lost & Found Staff, Management

**Rationale:** Items may eventually leave the active lost-and-found process without being claimed. The system must record what happened for accountability.

**Priority:** Must

**Acceptance / Fit Idea:** An authorized staff member can select a disposition type (returned/donated/disposed/transferred), add notes, and finalize the item record. The disposition is timestamped and appears in the audit log.

**Dependencies / Related Requirements:** R2 (Traceability), R15 (Audit Logging)

**Unresolved Questions:** What is the exact holding period before items become eligible for disposition? Are different item categories subject to different policies (e.g., identity documents always transferred to police)?

---

## Issue #9 — Claim Tracking Identifier

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall generate and provide a unique tracking reference code to a passenger upon successful submission of a lost-item report.

**Source / Origin:** Passenger

**Rationale:** Enables passengers to look up and reference their specific inquiry without submitting duplicates or calling the phone line.

**Priority:** Must

**Acceptance / Fit Idea:** After submitting a lost-item report, the passenger is immediately shown a unique tracking code (e.g., "TTC-LF-2026-00142") and receives it via their chosen contact method.

**Dependencies / Related Requirements:** R5 (Submit Report), R10 (Check Status)

**Unresolved Questions:** What format should the tracking code use? Should it be human-memorable (short alphanumeric) or purely system-generated (UUID)?

---

## Issue #10 — Check Report Status

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall allow a passenger to look up the current processing state of their lost-item report using their tracking reference code and contact information.

**Source / Origin:** Passenger

**Rationale:** Reduces repetitive phone calls and counter visits by providing self-serve progress updates, relieving pressure on the Mon–Fri 12–5 PM phone line.

**Priority:** Must

**Acceptance / Fit Idea:** A passenger enters their tracking code and email/phone on the public portal and sees the current status of their report (e.g., "Report received", "Potential match found", "Ready for pickup").

**Dependencies / Related Requirements:** R9 (Tracking Code), R2 (Traceability)

**Unresolved Questions:** How much detail should be shown in the public status view? Should it show match details or only high-level status?

---

## Issue #11 — Rapid Operator Intake

**Labels:** `type:functional`, `status:candidate`, `priority:should`

**Requirement Statement:**
The system shall provide a streamlined intake form allowing frontline staff to log a found item using minimal required fields (date, route/station, broad category).

**Source / Origin:** Transit Operator

**Rationale:** Ensures shift drivers and station collectors can hand off property quickly without delaying schedules. A complex form would discourage operator compliance.

**Priority:** Should

**Acceptance / Fit Idea:** A transit operator can log a found item in under 60 seconds using a mobile-friendly form with three required fields and optional detail fields.

**Dependencies / Related Requirements:** R1 (Centralized Records), R3 (Item Recovery)

**Unresolved Questions:** Should the intake form be a separate mobile app or a responsive web form? Does the operator need to authenticate or can they use a shared station login?

---

## Issue #12 — Redacted Public Search

**Labels:** `type:functional`, `status:candidate`, `priority:should`

**Requirement Statement:**
The system shall display a public catalog of recently found items while automatically redacting sensitive identifiers (e.g., serial numbers, full names, specific bag contents).

**Source / Origin:** Passenger, Management

**Rationale:** Allows passengers to browse found items and recognize their property without exposing private details that could enable fraudulent claims.

**Priority:** Should

**Acceptance / Fit Idea:** A passenger can browse a list of recently found items showing category, general description, and date/location found. No serial numbers, personal names, or contents lists are visible.

**Dependencies / Related Requirements:** R18 (Data Privacy), R1 (Centralized Records)

**Unresolved Questions:** What fields should be shown vs. redacted? How long should items appear in the public catalog? Should passengers be able to filter/search the catalog?

---

## Issue #13 — Physical Storage Assignment

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall record the physical storage location (e.g., bin, shelf, or locker identifier at Bay Station) for each cataloged found item.

**Source / Origin:** Lost & Found Staff

**Rationale:** Prevents items from being misplaced inside the holding facility and speeds up retrieval during customer pickup.

**Priority:** Must

**Acceptance / Fit Idea:** Each found-item record includes a storage location field. Staff can update the location when items are moved. The location is displayed when preparing for a pickup.

**Dependencies / Related Requirements:** R1 (Centralized Records), R2 (Traceability)

**Unresolved Questions:** What is the physical storage layout at Bay Station? Are storage locations pre-defined in the system or free-text?

---

## Issue #14 — Intake Latency Notice

**Labels:** `type:functional`, `status:candidate`, `priority:should`, `needs:validation`

**Requirement Statement:**
The system shall display a clear notice informing passengers that items turned in on vehicles may take up to 24–48 hours to be processed at the central office.

**Source / Origin:** Passenger, Management

**Rationale:** Sets realistic expectations and prevents false assumptions that an unlisted item was permanently lost. **[Fact]** The TTC publicly states this processing delay.

**Priority:** Should

**Acceptance / Fit Idea:** A clearly visible notice appears on the lost-item report form and the public found-item catalog explaining the 24–48 hour processing delay.

**Dependencies / Related Requirements:** R5 (Submit Report), R12 (Public Search)

**Unresolved Questions:** Should the notice be a static banner or a contextual tooltip? Is 24–48 hours still the accurate processing time?

---

## Issue #15 — Staff Audit Logging

**Labels:** `type:functional`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall record which staff member created, updated, or marked an item as returned or disposed of, along with a timestamp.

**Source / Origin:** Management

**Rationale:** Maintains an immutable chain of custody and accountability for internal operations. Required for dispute resolution and compliance.

**Priority:** Must

**Acceptance / Fit Idea:** Every status change on a found-item record is logged with the staff member's identity and a timestamp. Logs are viewable by management and cannot be modified or deleted by staff.

**Dependencies / Related Requirements:** R2 (Traceability), R19 (RBAC)

**Unresolved Questions:** How long should audit logs be retained? Should logs be exportable for external audits?

---

## Issue #16 — Claim Data Retention & Purging

**Labels:** `type:quality`, `status:candidate`, `priority:must`, `needs:clarification`

**Requirement Statement:**
The system shall automatically anonymize or purge personal contact and identity information from resolved reports after a defined retention window (e.g., 90 days).

**Source / Origin:** Management, Passenger

**Rationale:** Ensures compliance with Ontario municipal privacy legislation (MFIPPA) by not holding PII indefinitely. Protects passenger privacy after the business need for the data has ended.

**Priority:** Must

**Acceptance / Fit Idea:** 90 days after a report is resolved (item returned or claim closed), all PII associated with that report is automatically anonymized. Anonymized records remain in the system for statistical purposes but cannot be linked to an individual.

**Dependencies / Related Requirements:** R18 (Data Privacy), R15 (Audit Logging)

**Unresolved Questions:** What is the exact retention window required by MFIPPA? Should the retention period be configurable by management? Does anonymization extend to audit logs?

---

## Issue #17 — System Availability

**Labels:** `type:quality`, `status:candidate`, `priority:should`, `needs:validation`

**Requirement Statement:**
The public-facing portal (lost-item reporting, status checking, found-item browsing) shall be available 24/7 with at least 99.5% uptime measured monthly.

**Source / Origin:** Passenger, Management

**Rationale:** Passengers may realize they lost an item at any time. Unlike the current phone line (Mon–Fri 12–5 PM), the digital system should not restrict when reports can be submitted.

**Priority:** Should

**Acceptance / Fit Idea:** The system achieves at least 99.5% uptime in any given calendar month, measured by an external monitoring service. Planned maintenance windows are excluded if communicated 48 hours in advance.

**Dependencies / Related Requirements:** None

**Unresolved Questions:** **[Assumption]** The 99.5% target is a team assumption. What uptime SLA is realistic given TTC IT infrastructure? Is a lower target acceptable if a maintenance window is needed?

---

## Issue #18 — Passenger Data Privacy

**Labels:** `type:quality`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall encrypt all personal information (contact details, identity documents) in transit and at rest.

**Source / Origin:** Management, Passenger

**Rationale:** Protects passenger PII from unauthorized access and supports compliance with MFIPPA and TTC data security policies.

**Priority:** Must

**Acceptance / Fit Idea:** All API communication uses TLS 1.2+. All PII fields in the database are encrypted at rest using AES-256 or equivalent. No PII is logged in plaintext in application logs.

**Dependencies / Related Requirements:** R16 (Data Retention), R19 (RBAC)

**Unresolved Questions:** Does the TTC have existing encryption standards that must be followed? Are uploaded photos/documents considered PII requiring encryption?

---

## Issue #19 — Role-Based Access Control

**Labels:** `type:quality`, `status:candidate`, `priority:must`

**Requirement Statement:**
The system shall enforce role-based access control so that passengers, transit operators, Lost & Found staff, and transit management each have access only to functions and data appropriate to their role.

**Source / Origin:** Management

**Rationale:** Prevents unauthorized access to sensitive data and ensures staff can only perform actions within their job function.

**Priority:** Must

**Acceptance / Fit Idea:** Four distinct roles are defined (Passenger, Operator, Staff, Management) with different permissions. A transit operator cannot approve a claim return. A passenger cannot view staff audit logs.

**Dependencies / Related Requirements:** R15 (Audit Logging), R18 (Data Privacy)

**Unresolved Questions:** Should there be a system administrator role separate from transit management? How are staff roles provisioned — through the system or through an external directory?

---

## Issue #20 — Mobile-Responsive Interface

**Labels:** `type:constraint`, `status:candidate`, `priority:should`

**Requirement Statement:**
The passenger-facing portal shall be fully functional on mobile devices with screen widths as small as 320px.

**Source / Origin:** Passenger

**Rationale:** **[Assumption]** Most passengers will report lost items from a smartphone. The interface must be usable without a desktop computer.

**Priority:** Should

**Acceptance / Fit Idea:** All passenger-facing pages (report form, status check, found-item catalog) pass a responsive design test at 320px, 375px, and 768px viewport widths without horizontal scrolling or broken layouts.

**Dependencies / Related Requirements:** R5 (Submit Report), R10 (Check Status), R12 (Public Search)

**Unresolved Questions:** Should the operator intake form also be mobile-responsive, or will operators always use a depot terminal?
