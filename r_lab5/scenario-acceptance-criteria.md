# Lab 5: Scenarios, Use Cases and Acceptance Criteria

## Activity A: Scenario and Use Case Specification

### Use Case: UC-04 Central Ownership Verification

* Primary Actor: Central Lost & Found Staff (STK-04).
* Secondary Actors: Passenger Claimant (STK-01), Transit Police Liaison.
* Goal: Verify that a claimant owns a recovered item before authorizing return and log the decision.
* Trigger: A candidate match between a lost report and a found item enters the verification queue.
* Preconditions: The recovered item has an intake barcode in storage, a matching lost report exists, and staff is logged in with verification permissions.
* Postconditions: The claim status updates to "Claim Verified", "Claim Rejected", or "Escalated to Police", and an audit log entry is saved with the staff ID and timestamp.

### Main Success Flow

1. Staff opens the verification queue and selects an item with a candidate match.
2. The system displays the unpublicized claimant attributes alongside the physical intake record.
3. Staff checks the stored item and confirms that at least two unpublicized attributes match the claimant description.
4. Staff enters a verification note, selects "Approved", and submits the decision.
5. The system sets the claim status to "Claim Verified", sends a pickup notification to the claimant, and logs the decision.

### Alternative and Exception Flows

#### Exception 2a: Incomplete Description (Telephone Triage)
If the claimant description is too generic to verify, staff places an outbound call to ask for identifying details without revealing item contents. When the claimant provides matching details over the phone, staff records the notes and resumes the approval flow; otherwise, staff marks the claim rejected after two failed call attempts across 48 hours.

#### Exception 3a: Competing Claims on Identical Items
When two claimants file matching reports for the same recovered item, the system automatically marks the item as "Claim Disputed" and blocks release. Staff requests secondary proof such as receipts or bank timestamps from both claimants, approving the verified owner or escalating the case to a supervisor if neither can prove ownership.

#### Exception 4a: Unverifiable High-Value Property (Police Escalation)
If an item has an estimated value of $1000 or more and staff cannot verify ownership through description or phone contact, staff selects "Escalate to Police". Staff enters the police occurrence number and badge ID, and the system transitions the item to "Transferred to Police Custody" while notifying the claimant.

## Activity B: Acceptance Criteria

1. Given a candidate match with matching unpublicized attributes, when staff submits an approved decision, the system must update the record to "Claim Verified" and write an audit event with staff ID and timestamp within 1 second.
2. Given a lost report with fewer than two descriptive attributes, the system must disable the "Approve" button and require staff to either log a phone contact attempt or enter a rejection reason.
3. When two distinct lost reports match the same recovered item above an 80% similarity threshold, the system must automatically set the item status to "Claim Disputed" and lock the release action for both claims.
4. When staff escalates an unverified item valued at $1000 or greater to the police, the system must require a valid police occurrence number and officer badge ID of at least 4 characters before allowing status transition to "Transferred to Police Custody".
5. During in-person wallet verification, the system must reject any free-text staff notes containing a 15-digit or 16-digit payment card number, allowing only the card issuer and last 4 digits to be recorded.

## Activity C: Peer Review and Revision

### Peer Review Feedback 

1. The initial high-value escalation rule was untestable because it did not state a dollar threshold or required police tracking fields.
2. The initial competing claims flow did not specify an automated lock, creating a risk that staff could accidentally release the item to one claimant while a dispute was pending.
3. The initial draft allowed staff to write card numbers in verification notes, which violated privacy policies and lacked concrete validation limits.

### Revision Summary

1. Added a measurable $1000 valuation threshold and mandatory 4-character input checks for police occurrence number and badge ID in Exception 4a and Criterion 4.
2. Added an automated system lock in Exception 3a and Criterion 3 that sets the status to "Claim Disputed" whenever two claims exceed an 80% match similarity threshold.
3. Added input validation in Criterion 5 that blocks full 15-digit and 16-digit card numbers from being entered into verification notes.
