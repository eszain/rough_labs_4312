# Explaining Baseline v1.0 Review: Detailed Concepts and Real-World Examples

This companion guide explains every point in the Lab 6 review artifact with practical examples and real-world transit context.

---

## Activity A: Five-Requirement Quality Sample

### 1. R-002: Legitimate Item Recovery
* **The Concept:** This is a core **stakeholder requirement** stating that property cannot be released until an authorized staff member explicitly approves the claim.
* **Why it matters:** It stops the system from blindly releasing an item simply because a report matches an inventory item.
* **Real-World Example:** Suppose Alice reports a lost **black iPhone 15** at Finch Station. An algorithm identifies a matching phone in central storage. If the system allowed automated release, anyone browsing the portal could claim it and walk away. Under **R-002**, the phone remains locked in **Unverified** status until staff verifies proof (such as Alice unlocking the screen with her passcode).
* **Verification Test:** An automated test sends an API call attempting to transition an item directly from `Candidate_Match` to `Released`. The test passes if the system rejects the call with an **HTTP 403 Forbidden** error.

### 2. R-008: Candidate Match Ranking
* **The Concept:** A **functional requirement** where the algorithm scores and ranks potential matches based on time, location, and descriptive attributes.
* **Why it matters:** In Sprint 0, Decision **D-004** established that matching is separate from verification. Software only **suggests and ranks** candidates; human staff make the legal decision.
* **Real-World Example:** A rider reports a **blue Herschel backpack** lost at 8:30 AM at Pioneer Village. Central storage has three blue backpacks: Backpack A (found at 8:45 AM at Pioneer Village), Backpack B (found at 2:00 PM at York University Station), and Backpack C (found two days earlier at Kipling). The system scores them and displays **Backpack A (95% match)** at the top, **Backpack B (60% match)** second, and **Backpack C (25% match)** third.
* **Verification Test:** Feed mock inventory records with known attribute differences into the matching engine and assert that the output array sorts strictly in descending order of **similarity score**.

### 3. R-009: Verification Decision Record
* **The Concept:** A **functional requirement** mandating that every approval or rejection decision must record the staff ID, timestamp, and verification outcome.
* **Why it matters:** It provides **auditability and non-repudiation**. If an item is released to the wrong person, management has a legal paper trail showing who authorized the handoff.
* **Real-World Example:** Staff member **Zain (Staff ID: STF-402)** inspects a claimant's receipt and confirms it matches a recovered laptop serial number. When Zain clicks **Approve** at **2:14 PM on Oct 22**, the system writes a permanent database record: `StaffID: STF-402, Timestamp: 2026-10-22T14:14:00Z, Decision: Approved`.
* **The Defect/Omission:** Currently, R-009 assumes a simple binary world: **Approved** or **Rejected**. When staff must call a claimant for more information, the claim sits in an undefined limbo state because R-009 lacks an intermediate **Pending Telephone Triage** state.
* **Verification Test:** Attempt to submit an approval transaction with an empty `staff_id` or null `timestamp`; assert that database constraints reject the record.

### 4. R-019: Staff Audit Logging
* **The Concept:** A **quality and security requirement** ensuring that every sensitive staff action creates an immutable, append-only log record.
* **Why it matters:** It prevents internal fraud or unauthorized data snooping. Staff cannot secretly change an item's status to "Disposed" and steal it without leaving an audit record.
* **Real-World Example:** If an employee views a claimant's personal phone number or changes an item's storage bin from **Shelf A** to **Shelf C**, the system automatically logs the authenticated user ID, action type, affected record, and exact timestamp.
* **The Defect/Omission:** The phrase "auditable staff action" is ambiguous. The requirement must be paired with an **explicit enum list** defining exactly which actions trigger audit entries.
* **Verification Test:** Execute five distinct operations (intake, bin move, claim view, approval, police transfer) and assert that five corresponding rows appear in the `audit_logs` table.

### 5. R-025: Mobile-Responsive Passenger Interface
* **The Concept:** A **usability constraint** mandating that all passenger workflows remain functional on viewports as narrow as 320 pixels without horizontal scrolling.
* **Why it matters:** Most transit passengers submit lost-property reports or check status directly from their mobile phones while on platforms or buses.
* **Real-World Example:** A student opens the lost-and-found portal on an older **iPhone SE** (screen width 320 px). The text boxes, file upload buttons, and status tables reflow vertically so the user never has to scroll horizontally to read content or tap "Submit".
* **The Defect/Omission:** While the requirement is clear and testable, the team failed to track it with an official **GitHub Issue** during candidate backlog creation.
* **Verification Test:** An automated browser test suite (such as Playwright) loads the portal at a viewport width of 320 px and asserts that `document.documentElement.scrollWidth` equals `window.innerWidth`.

---

## Activity B: Traceability Chains and Weak Links

### 1. Incomplete Descriptions and Phone Triage Chain
* **The Trace:** Lab 4 Stakeholder Interview $\rightarrow$ **R-009 (Decision Record)** $\rightarrow$ **UC-04 Exception 2a (Telephone Triage)** $\rightarrow$ **Lab 5 Acceptance Criterion 2**.
* **Real-World Example:** A passenger rushes off a train and submits a form saying only *"Lost jacket on Line 1"*. Because thousands of jackets are lost, staff cannot verify ownership from that alone. Instead of immediately rejecting the claim, staff calls the passenger: *"Does the jacket have any interior labels or items in the pockets?"* The passenger replies: *"Yes, it's a Zara bomber with a green lanyard in the left pocket."*
* **The Weak Link:** The current backlog requirement **R-009** only describes approving or rejecting. It does not mention telephone outreach, logging call attempts, or managing a **48-hour retry window**. A developer following R-009 would build only an Approve/Reject form and completely omit the telephone triage tracking features.

### 2. Unverified High-Value Police Escalation Chain
* **The Trace:** Lab 4 Gaming Mouse Finding $\rightarrow$ **R-016 (Final Disposition)** $\rightarrow$ **UC-04 Exception 4a (Police Escalation)** $\rightarrow$ **Lab 5 Acceptance Criterion 4**.
* **Real-World Example:** Staff holds an unbranded **$1,200 gaming laptop** or a **$150 gaming mouse** with no name or serial number. Two claimants step forward, but neither has receipts or distinctive photos. Central Lost & Found does not want legal liability for giving an expensive item to the wrong person, so they transfer the property to **Transit Police**.
* **The Broken Link:** Requirement **R-016** currently covers only standard property leaving storage after the **90-day municipal retention window** (auction, donation, destruction). It has no status for **immediate police transfer** and omits the **$1,000 value threshold** established in Lab 5.

### 3. Payment Card Privacy Chain
* **The Trace:** Lab 4 Passenger Wallet Interview $\rightarrow$ **R-020/R-022 (Data Protection)** $\rightarrow$ **UC-04 Step 3 (In-Person Verification)** $\rightarrow$ **Lab 5 Acceptance Criterion 5**.
* **Real-World Example:** A rider claims a lost leather wallet at the central office. Staff looks inside and confirms the rider's photo ID, then asks: *"What are the last 4 digits of your credit card inside?"* The rider says *"4192"*, and staff confirms the card ending.
* **The Weak Link:** Requirements **R-020** and **R-022** state that stored data must be encrypted, but they do not actively prevent staff from typing the full 16-digit card number into the verification notes box (`"Verified Visa card 4500 1234 5678 4192"`). Saving raw card numbers violates **PCI-DSS compliance**. The system needs an active **regex filter** that blocks full payment card numbers from being typed into notes.

---

## Activity C: Model Interrogation and System Defects

### 1. Missing Transit Police Actor
* **The Defect:** The Sprint 0 context diagram (`context-diagram.puml`) included external systems like Payment Gateways and Delivery Partners, but completely omitted **Transit Police / Law Enforcement**.
* **Why it is a defect:** Lab 4 and Lab 5 established that police escalation is the primary legal off-ramp for expensive, unverified property. Without a Police actor in the context model, developers will not build interfaces to record **Officer Badge IDs** or **Police Occurrence Numbers**.

### 2. Missing Telephone Communication Channel
* **The Defect:** The diagram depicts passenger communication solely through web portal forms and automated SMS/email notifications.
* **Why it is a defect:** In everyday operation, staff frequently use **telephone calls** to clarify vague lost reports. Because telephone voice lines are an out-of-band communication channel rather than an automated software API, the model omitted them, obscuring the need for telephone triage logging in the system UI.

### 3. Architectural Decomposition Clutter
* **The Defect:** A **System Context Diagram** must represent the target system as a **single black box**. Group 11's Sprint 0 diagram instead opened the box and drew 7 internal modules (`Reporting`, `Storage`, `Matching`, `Verification`, `Audit`, `Admin`, `Tracking`).
* **Why it is a defect:** It mixes high-level requirements context with internal software architecture. Drawing all those internal components and crisscrossing lines made the diagram tiny and unreadable, directly causing the grade deduction in Sprint 0.

---

## Activity D: Mini Walkthrough Preparation

### What the Team Explains to the TA
* **Verification Lifecycle Scope:** Demonstrating the end-to-end path an item takes through reporting, matching, verification, and return across **R-002**, **R-008**, **R-009**, and **R-016**.
* **Forward Traceability Evidence:** Showing how every functional requirement and exception flow directly links back to interview data collected during Lab 4.
* **Objective Testability:** Proving that criteria are measurable and testable through deterministic values—such as the **$1,000 threshold**, **4-character badge IDs**, and **320 px layout boundaries**.
* **Proactive Defect Discovery:** Explaining to the TA that the team discovered defects (like the copy-pasted R-027 statement and missing police boundary) during internal review and scheduled fixes before freezing Baseline v1.0.

---

## Prioritized Pre-Submission Correction Plan

### 1. Priority 1 (Critical): Fix R-027 and R-026 Copy-Paste Errors
* **The Defect:** In commit `87731b8`, a team member added R-027 ("Physical In-Person Pickup Acknowledgment") but accidentally pasted the text from R-025 ("The primary passenger workflows shall remain functionally complete at viewport widths of 320 px..."). Furthermore, R-026 had an automated notification title but described in-person handoff logging.
* **The Fix:** Zain will rewrite R-027 to specify physical handoff acknowledgment and staff sign-off, and align R-026's statement with automated notification dispatch. (Assigned to Zain, target Oct 23).

### 2. Priority 2 (High): Redraw Context Diagram as a Clean Black Box
* **The Defect:** The context diagram decomposes internal modules and is unreadable without excessive zooming.
* **The Fix:** Anirudh will redraw the diagram as a single central black box with larger fonts and add **Transit Police** as an external actor. (Assigned to Anirudh, target Oct 24).

### 3. Priority 3 (High): Formalize Police Escalation in R-016 and R-009
* **The Defect:** The candidate backlog does not recognize police transfer as an official disposition state or specify the $1,000 threshold.
* **The Fix:** Sufyan will update R-016 to add **Transferred to Police Custody** and add the **$1,000 valuation trigger** to R-009. (Assigned to Sufyan, target Oct 24).

### 4. Priority 4 (Medium): Add Missing Stakeholders and Glossary Terms
* **The Defect:** Sprint 0 feedback docked marks because TTC IT, Logistics Provider, and Payment Service were cited in requirements but missing from `stakeholders.md`, and IPC and AODA were missing from `glossary.md`.
* **The Fix:** Anirudh will add these definitions and stakeholders to satisfy Sprint 0 grading conditions. (Assigned to Anirudh, target Oct 24).

### 5. Priority 5 (Medium): Add R-029 for Payment Card Input Masking
* **The Defect:** Free-text verification notes currently permit staff to type full 16-digit credit card numbers into the database.
* **The Fix:** Zain will add candidate requirement R-029 specifying an active **regex filter** that blocks 15/16-digit card sequences. (Assigned to Zain, target Oct 25).
