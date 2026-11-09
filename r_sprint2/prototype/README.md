# Prototype Refinement Note — Sprint 2

## 1. Scope & Baseline Continuity
Requirements Sprint 2 emphasizes analytical modeling, quality attribute quantification, conflict analysis, and stakeholder negotiation rather than user interface expansion or code generation. In accordance with Section 12 of the EECS 4312 course handout, visual polish and source code volume receive no credit; the prototype’s role is strictly to ground requirements analysis.

The team preserved the low-fidelity screen mockups and state-driven storyboards established in Sprint 1 under `doc/sprint1/prototype/` without adding new UI screens or making code changes in Sprint 2.

## 2. Requirements Engineering Analysis Grounded in Prototype Walkthroughs
The team used conceptual walkthroughs of the existing Sprint 1 prototype flows to analyze and validate key requirements decisions:

1. **Restricted Public Catalogue vs. Verification Privacy (`SR-005`, `SR-006`, `FR-016`):**
   * *RE Question:* How can passengers discover candidate items in a public catalogue without exposing identifying marks, serial numbers, or features needed by staff to authenticate ownership?
   * *Walkthrough Insight:* Inspecting the public card layout confirmed that attributes must be segregated into public and private tiers. This validated the requirement that serial numbers remain masked and led directly to specifying `FR-016` (allowing a claimant to associate a public card to their report without exposing private verification fields).

2. **Claim Dispute Locking (`FR-014`, `BR-002`):**
   * *RE Question:* How should frontline staff interfaces behave when multiple independent claimants assert ownership over identical high-value items?
   * *Walkthrough Insight:* Tracing the claim decision flow demonstrated that displaying conflicting claims without an explicit system lock creates severe risk of accidental handover. This led to operationalizing `FR-014`, where the interface blocks release and flags an active dispute until a supervisor records a reasoned resolution.

3. **Rate Limiting, CAPTCHAs, and Accessibility (`QR-009`, `QR-015`):**
   * *RE Question:* How can automated brute-force scraping of loss reports be prevented without creating accessibility barriers for riders using screen readers or shared transit Wi-Fi?
   * *Walkthrough Insight:* Evaluating the status-lookup screens demonstrated that visual CAPTCHAs would violate `QR-009` (AODA/WCAG accessibility). As a result, the team specified progressive rate limiting per session and reference token in `QR-015`, coupled with telephone triage unlock fallback.

4. **Telephone Triage vs. Digital Self-Service (`FR-015`, `QR-014`):**
   * *RE Question:* How does the system handle claimants who lack persistent internet access or have withdrawn automated notification consent?
   * *Walkthrough Insight:* Walkthroughs of the intake status check confirmed that portal lookup must remain decoupled from message delivery consent, ensuring offline and phone-assisted claimants are not excluded from tracking their claims.
