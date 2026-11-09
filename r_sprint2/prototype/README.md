# Public Transit Lost & Found System — Prototype Specification & RE Verification

* **Course:** EECS 4312 — Software Requirements Engineering
* **Project:** Public Transit Lost & Found System (Group 11)
* **Location:** `doc/sprint2/prototype/README.md`
* **Status:** Complete / Preserved Baseline

---

## Part 1: Sprint 1 Prototype Foundation (Low-Fidelity Mockups & Flows)

During Requirements Sprint 1, the team established low-fidelity interface mockups, state-driven activity storyboards, and screen flows to ground early elicitation discoveries (specifically addressing Themes T-01 through T-07 and Conflicts C-01 through C-07)[cite: 23]. 

The prototype modeled three critical operational interfaces[cite: 23]:

### 1. Frontline Intake & Telephone Triage Queue (`UC-02`, `FR-001`, `FR-003`, `FR-015`)
* **Interface Layout:** Designed for station agents and central facility intake staff[cite: 23]. Features quick-entry fields for physical intake: unique barcode tag scanning, receiving station/route, initial custodian ID, and warehouse storage bin assignment[cite: 23, 24].
* **Telephone Triage Queue Screen:** Displays candidate matches flagged with status `Pending Clarification` (formerly `Pending Telephone Triage`)[cite: 23, 31]. Includes scheduled follow-up timers, contact attempt logs, and escalation triggers for non-responsive claimants[cite: 24, 31].
* **RE Problem Addressed:** Elicitation revealed that frontline agents are overwhelmed by complex multi-step forms[cite: 24]. The triage screen minimizes intake friction while enforcing a structured review queue[cite: 24].

### 2. Disputed Claim System Lock & Supervisor Banner (`UC-03`, `FR-014`, `BR-002`)
* **Interface Layout:** Operational view accessed by claims officers and station supervisors[cite: 23, 24]. When two or more claimants assert ownership over identical high-value items (e.g., black smartphones, wireless earbuds, keys), the screen renders a prominent visual warning banner: **`[DISPUTE HOLD ACTIVE — RELEASE DISABLED]`**[cite: 23, 24].
* **State Machine Mechanics:** Completely disables the physical property handover and courier dispatch triggers[cite: 24]. Unlocking the item requires an authorized supervisor to access a dedicated dispute resolution pane and log a reasoned decision[cite: 24].
* **RE Problem Addressed:** Directly resolved Conflict C-02 by preventing premature or wrongful property handover when automated similarity scores match multiple passenger reports[cite: 23, 24].

### 3. Courier Settlement & Payment Gate (`UC-03`, `FR-010`, `FR-011`)
* **Interface Layout:** External remote-return dispatch screen for logistics staff and claimants opting for home delivery[cite: 23, 24]. Displays the calculated delivery quote, carrier tracking link, and payment status badge[cite: 24].
* **Release Interlock:** The courier dispatch action remains grayed out with an active gate constraint until an asynchronous webhook response from the third-party payment gateway confirms that fees have settled[cite: 24].
* **RE Problem Addressed:** Prevents transit authority financial loss and liability issues from uncollectible shipping charges prior to property release[cite: 24].

---

## Part 2: Sprint 2 RE Verification & Analytical Continuity

### 2.1 Scope Continuity (No UI Code Expansion)
Requirements Sprint 2 emphasizes analytical modeling, quality attribute quantification, conflict analysis, and stakeholder negotiation rather than UI expansion or code generation[cite: 1, 17]. In accordance with Section 12 of the EECS 4312 course handout, visual polish and source code volume receive no credit; the prototype’s role is strictly to ground requirements analysis[cite: 17].

The team preserved the low-fidelity screen mockups and state-driven storyboards established in Sprint 1 without adding new UI screens or making code changes in Sprint 2[cite: 17, 23].

### 2.2 Requirements Engineering Analysis Grounded in Prototype Walkthroughs
The team used conceptual walkthroughs of the existing Sprint 1 prototype flows to analyze and validate key requirements decisions[cite: 17]:

1. **Restricted Public Catalogue vs. Verification Privacy (`SR-005`, `SR-006`, `FR-016`):**
   * *RE Question:* How can passengers discover candidate items in a public catalogue without exposing identifying marks, serial numbers, or features needed by staff to authenticate ownership[cite: 17, 24]?
   * *Walkthrough Insight:* Inspecting the public card layout confirmed that attributes must be segregated into public and private tiers[cite: 17, 24]. This validated the requirement that serial numbers remain masked and led directly to specifying `FR-016` (allowing a claimant to associate a public card to their report without exposing private verification fields)[cite: 17, 24].

2. **Claim Dispute Locking (`FR-014`, `BR-002`):**
   * *RE Question:* How should frontline staff interfaces behave when multiple independent claimants assert ownership over identical high-value items[cite: 17, 24]?
   * *Walkthrough Insight:* Tracing the claim decision flow demonstrated that displaying conflicting claims without an explicit system lock creates severe risk of accidental handover[cite: 17, 24]. This led to operationalizing `FR-014`, where the interface blocks release and flags an active dispute until a supervisor records a reasoned resolution within 3 business days[cite: 17, 24].

3. **Rate Limiting, CAPTCHAs, and Accessibility (`QR-009`, `QR-015`):**
   * *RE Question:* How can automated brute-force scraping of loss reports be prevented without creating accessibility barriers for riders using screen readers or shared transit Wi-Fi[cite: 17, 24]?
   * *Walkthrough Insight:* Evaluating the status-lookup screens demonstrated that visual CAPTCHAs would violate `QR-009` (AODA/WCAG accessibility)[cite: 17, 24]. As a result, the team specified progressive rate limiting per session and reference token in `QR-015` (5 failures per 15-minute rolling window), coupled with telephone triage unlock fallback[cite: 17, 24, 26].

4. **Telephone Triage vs. Digital Self-Service (`FR-015`, `QR-014`):**
   * *RE Question:* How does the system handle claimants who lack persistent internet access or have withdrawn automated notification consent[cite: 17, 24]?
   * *Walkthrough Insight:* Walkthroughs of the intake status check confirmed that portal lookup must remain decoupled from message delivery consent, ensuring offline and phone-assisted claimants are not excluded from tracking their claims[cite: 17, 24].

---

## Part 3: Sprint 3 Readiness
These prototype flows and boundary conditions will serve as direct inputs for Sprint 3 inspection, test case derivation, and change-impact analysis against Baseline v2.0[cite: 22].
