# Lab 9: Cross-Team Requirements Inspection Report

## 1. Inspection Overview and Review Metadata

* Date: Thursday, November 12, 2026 (4:00 PM - 5:00 PM)
* Reviewing Team: Group 11 (Mohammad Zain Al Syed, Muhammad Sufyan, Anirudh Sundar)
* Inspected Team: Group 04 (Retail POS and Inventory Migration System)
* Inspected Packet: Sprint 2 Requirements Packet for Cash-to-Digital Retail Transition (Requirements FR-101 to FR-112, FR-201 to FR-208, QR-301 to QR-305, SEC-401 to SEC-403; Checkout Activity Diagram; Traceability Matrix excerpt)
* Review Discussion: Findings reviewed with Group 04 authors during the in-lab discussion period (4:42 PM - 4:52 PM).

## 2. Defect Summary

| Defect Type | Critical | High | Medium | Low | Total |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Contradiction / Inconsistency | 1 | 0 | 0 | 0 | 1 |
| Unverifiability / Ambiguity | 0 | 1 | 0 | 0 | 1 |
| Omission | 0 | 1 | 0 | 0 | 1 |
| Model / Text Mismatch | 0 | 0 | 1 | 0 | 1 |
| Premature Design / Traceability Gap | 0 | 0 | 1 | 0 | 1 |
| Non-Atomic Wording | 0 | 0 | 0 | 1 | 1 |
| **Total** | **1** | **2** | **2** | **1** | **6** |

## 3. Detailed Inspection Findings

### Finding 1: Contradiction Between Item Scanning and Payment Confirmation
* Requirement ID: FR-104 vs. FR-202
* Defect Type: Contradiction / Inconsistency
* Severity: Critical
* Location: Section 3.1 (POS Checkout), page 3 vs. Section 3.3 (Inventory), page 5
* Problem: FR-202 states that scanning an item barcode immediately deducts that item count from active stock, whereas FR-104 states that sales transactions are committed only after card payment authorization succeeds. If a card declines, times out, or the customer cancels at the pin pad, stock counts become inaccurate because no cancellation rollback is specified.
* Actionable Recommendation: Update FR-202 so scanned items enter a temporary cart reservation state, committing permanent stock deductions only after the POS receives an approved authorization response from FR-104.

### Finding 2: Unverifiability in Offline Payment Processing
* Requirement ID: QR-301 (Offline POS Operation)
* Defect Type: Unverifiability / Ambiguity
* Severity: High
* Location: Section 4 (Quality Scenarios), page 7
* Problem: QR-301 states that "the checkout terminal should work smoothly and accept transactions even when the store network connection is unstable or down." Phrasing such as "smoothly" and "unstable or down" lacks measurable conditions, offline storage durations, or floor limit thresholds.
* Actionable Recommendation: Specify quantitative parameters: "During network outages up to 4 hours, the terminal shall process offline contactless transactions up to a maximum 50 dollar floor limit per transaction, buffering encrypted payment records locally for automatic settlement once connection returns."

### Finding 3: Omission of Split-Tender Payments and Cash Reconciliation
* Requirement ID: FR-108 (End-of-Day Register Reconciliation)
* Defect Type: Omission
* Severity: High
* Location: Section 3.1 (POS Checkout), page 4
* Problem: The specification treats payment processing as purely electronic. Because the store currently operates on cash only, customers and cashiers will continue handling cash alongside card payments. The packet omits split-tender transactions (part cash, part debit) as well as daily cash drawer balancing against total sales.
* Actionable Recommendation: Add requirement FR-108a to allow split-tender transactions across cash and electronic payment, and add FR-108b requiring end-of-day cash drawer counts to reconcile physical cash against logged cash receipts and card terminal totals.

### Finding 4: Model-to-Text Mismatch in Checkout Process Flow
* Requirement ID: Checkout Activity Diagram vs. FR-102
* Defect Type: Model / Text Mismatch
* Severity: Medium
* Location: Activity Diagram (`doc/sprint2/models/checkout-flow.png`) vs. Section 3.1 (FR-102)
* Problem: The Activity Diagram shows a parallel fork initiating card terminal interaction while items are still being scanned. In contrast, specification text in FR-102 states that total item tallying, tax computation, and cashier confirmation must complete before dispatching the payment request to the payment terminal.
* Actionable Recommendation: Redraw the Activity Diagram to place the card terminal activation step strictly after the subtotal and tax calculation join node.

### Finding 5: Premature Design and Missing Compliance Traceability
* Requirement ID: SEC-401 (Card Data Protection)
* Defect Type: Premature Design / Broken Traceability
* Severity: Medium
* Location: Section 5 (Security and Compliance), page 9; Traceability Matrix
* Problem: SEC-401 states that "the local store server shall encrypt customer card numbers using AES-256 before saving them to a local SQLite database." Storing primary account numbers locally creates unnecessary PCI-DSS compliance scope for a retail merchant. In addition, SEC-401 has no backward traceability link to a business goal or security standard.
* Actionable Recommendation: Redefine the requirement using tokenization: "The system shall rely on point-to-point encrypted terminal tokenization, storing only card type, last four digits, and processor authorization tokens." Add a backward traceability link to Goal G-04 (PCI-DSS Compliance).

### Finding 6: Non-Atomic Specification in Inventory Restocking
* Requirement ID: FR-205 (Shipment Ingestion and Reorder Dispatch)
* Defect Type: Non-Atomic Wording
* Severity: Low
* Location: Section 3.3 (Inventory Management), page 6
* Problem: FR-205 combines three separate functions into a single requirement statement: scanning supplier barcode manifests, incrementing active warehouse inventory, and automatically sending reorder purchase orders to distributors when minimum thresholds are reached.
* Actionable Recommendation: Divide FR-205 into two atomic requirements: FR-205a for barcode manifest scanning and stock incrementation, and FR-205b for automated supplier reorder notifications triggered by low stock thresholds.

## 4. Disposition Guidance for Inspected Team

* Recommended Acceptance: Findings 1, 2, and 4 should be accepted and fixed immediately for Sprint 3 Phase A, as they prevent inventory state corruption, clarify testable offline limits, and align the checkout model with text.
* Recommended Clarification: Finding 3 should be discussed with the shop owner to confirm cash handling workflows, maximum allowed drawer discrepancy thresholds, and split-tender frequency.
* Recommended Deferral or Phasing: Finding 5 should be accepted in requirements, while detailed payment processor integration and token schema selection can be finalized during Sprint 3 architecture design.
