# Explaining Lab 7: Goal/Obstacle Analysis & Measurable Quality Requirements

**Course:** EECS 4312 — Software Requirements Engineering (York University – Fall 2026)  
**Document:** Companion Guide to `goals-quality.md`  
**Location:** `c:\Extra\code\courses\4312\rough_labs_4312\r_lab7\explaining-goals-quality.md`

---

## 1. Overview and Purpose of Lab 7

### What is the Goal of this Lab?
In Requirements Engineering, moving from early ideas to a high-quality specification requires two crucial capabilities:
1. **Goal-Oriented Requirements Engineering (GORE):** Understanding *why* a system exists by starting from high-level stakeholder and business goals, systematically breaking them down into operational software requirements (AND-decomposition), and recognizing alternative architectural choices (OR-refinement). We also look for *obstacles*—things that could prevent goals from succeeding—and design requirements to resolve them.
2. **Quality Requirements Engineering:** Vague requirements like "the system shall be fast," "the portal must be user-friendly," or "data should be secure" cannot be tested or contracted. We convert vague qualitative desires into **measurable, testable specifications** (using operating conditions, stimulus-response scenarios, and concrete fit criteria), while honestly declaring whether numeric numbers come from real-world evidence or provisional engineering assumptions.

### How this Connects to the Semester Project
Lab 7 directly sets up our team's work for **Sprint 2** and **Assignment 2**:
* In Sprint 1, our team established **Requirements Baseline v1.0** (28 requirements).
* In Sprint 2, we will model goal hierarchies, engineer measurable non-functional quality requirements (NFQs/QRs), and analyze trade-offs before implementation.

---

## 2. Pre-Lab Activity: Weak Rationale Audit

### What are we supposed to do?
The handout requires us to bring 2–3 core project goals, current baseline quality requirements, and **one baseline requirement whose rationale is currently weak or unclear**, and explain how it will be refined.

---

### Detailed Point-by-Point Explanation

#### 1. Core Goals and Baseline QRs Brought to the Lab
* **Goal G-01 (Legitimate Property Recovery):** Protect transit passengers by returning property strictly to proven owners, avoiding municipal civil liability (`BR-002`, Decision `D-004`).
* **Goal G-02 (Chain of Custody Accountability):** Maintain an unbroken, timestamped audit trail from initial discovery by vehicle operators to station booths and central warehouse bins (`BR-001`, `SR-004`).
* **Existing Quality Requirements:** `QR-001` (append-only audit logs), `QR-002` (claimant PII data retention and credit card masking), and `CON-001` (99.5% web portal service availability).

#### 2. The Selected Weak Requirement: `FR-008` (Legacy `R-015`) — Central Processing Delay Notice
* **Baseline Statement:** *"The system shall display a standardized advisory notice on the public reporting portal and status views informing claimants that recovered items require 24 to 48 hours for central transfer and logging."*
* **Baseline Rationale:** *"Sets transparent rider expectations regarding physical transfer latency and curbs premature complaints."*

#### 3. Why is this rationale weak and incomplete?
* **Assumption of Rider Behavior:** The rationale asserts that displaying a static text banner "curbs premature complaints," but provides zero empirical proof that users read static text when distressed about a lost phone or wallet.
* **Failure to Account for Realistic Delays:** Transit items often take longer than 48 hours during holiday long weekends, severe weather, or when items sit in distant bus garages. When the clock passes 48 hours and the item is not logged, passengers assume their property was stolen and flood the call centre with urgent inquiries.
* **Lack of Measurability:** The rationale provides no metric to verify if the notice actually worked.

#### 4. How will our team refine this in Sprint 2?
We will replace the static text banner with **dynamic, route-based intake latency estimates** powered by actual operational telemetry (e.g., *"Subway Line 1 items typically log in 18 hours; bus route 60 items average 42 hours"*), and measure success by tracking whether call centre inquiry rates drop by $\ge 30\%$.

---

## 3. Activity A: Goal Model & Refinement

### What are we supposed to do?
1. Create a compact goal model starting from our root system mission.
2. Show at least one **AND-decomposition** (breaking a big goal into sub-goals that must all be achieved).
3. Show at least one **OR-refinement** (showing alternative ways to satisfy an operational goal).
4. Link at least **three operational goals** directly to concrete requirements in our baseline.

---

### Detailed Point-by-Point Explanation

#### Root Goal: `G-00` — Trustworthy and Accessible Lost Property Restitution
* **The Concept:** The ultimate purpose of the public transit lost-and-found system is to reunite passengers with their belongings without releasing items to the wrong people.
* **Why it matters:** Transit agencies handle over 50,000 lost items annually. Without a clear system, property is stolen, stockpiled in station closets, or discarded.

#### AND-Refinement 1: `G-10` — Rapid Frontline Intake & Custody Accountability
To achieve `G-00`, the agency *must* first get items into the system quickly and account for who holds them.
* **`G-11` (Flexible Public Reporting):** Passengers can report losses with approximate times and routes without knowing the 4-digit bus number $\rightarrow$ **Linked to `SR-001` (`R-003`)**.  
  *Real-World Example:* A commuter knows they left an umbrella on a northbound Spadina streetcar around 5:15 PM, but did not memorize the streetcar vehicle ID number.
* **`G-12` (Fast Intake under 45s):** Operators must log items and bind a barcode in under 45 seconds $\rightarrow$ **Linked to `FR-001` (`R-006`)**.  
  *Real-World Example:* A bus driver at a 3-minute turnaround layover quickly scans a pre-printed barcode sticker onto a found backpack so the bus can depart on schedule.
* **`G-13` (Intermediate Station Custody Logging):** Transferring items from an operator to a station booth CSA must be logged $\rightarrow$ **Linked to `SR-004` (`R-007`)**.  
  *Real-World Example:* The bus driver hands the backpack to the Finch Station CSA booth; the CSA scans the barcode, immediately transferring legal custody in the database to `Station Held`.

#### AND-Refinement 2: `G-20` — Verifiable & Fair Ownership Adjudication
Getting items is not enough; staff must evaluate claims objectively.
* **`G-21` (Algorithmic Match Candidate Ranking):** Algorithms sort candidate items by descending similarity score $\rightarrow$ **Linked to `FR-002` (`R-008`)**.  
  *Real-World Example:* Staff clicks an active report for a "black winter coat," and the system displays recovered coats sorted with the closest date, route, and size at the top.
* **`G-22` (Authorized Decision Audit Trail):** Every release must record staff ID, timestamp, and notes $\rightarrow$ **Linked to `FR-003` (`R-009`)**.
* **`G-23` (Telephone Triage):** Staff must outreach before rejecting vague claims $\rightarrow$ **Linked to `FR-015` (`R-030`)**.

#### OR-Refinement: `G-30` — Restitution Pathways (Alternative Options)
Once ownership is approved, how does the passenger get their item back? There are **two alternative operational pathways**:
* **Alternative 1 (`G-31`): In-Person Handoff at Central Facility $\rightarrow$ Linked to `FR-013` (`R-027`).**  
  *How it works:* The passenger visits the central Lost & Found office in person. Staff examines their government photo ID, captures a digital/physical signature, and marks the item `Returned`.
* **Alternative 2 (`G-32`): Remote Third-Party Courier Dispatch $\rightarrow$ Linked to `FR-010` (`R-017`) and `FR-011` (`R-018`).**  
  *How it works:* The passenger lives outside the city or has limited mobility. Staff generates a courier shipping manifest (`FR-010`), but the system **enforces a hard payment lock** (`FR-011`): the package cannot be released to FedEx/Canada Post until the passenger pays the delivery fee online.

---

## 4. Activity B: Obstacle and Conflict Analysis

### What are we supposed to do?
Identify at least **two real-world obstacles or conflict conditions** that threaten our goals, explain which goals and requirements are affected, describe the conflict, and state a concrete mitigation and trade-off question.

---

### Detailed Point-by-Point Explanation

### Obstacle 1: Vague Passenger Descriptions
* **The Conflict:** In `SR-001`, we deliberately allow passengers to submit reports without mandatory fine-grained details so the reporting process is accessible. But when a passenger submits *"Lost black winter jacket on Line 1"*, the matching algorithm (`FR-002`) cannot distinguish it from 40 other black jackets in storage. All items receive identical $\approx 45\%$ match scores.
* **Affected Goals:** `G-21` (Algorithmic Match Ranking) and `G-20` (Fair Adjudication).
* **The Mitigation (`FR-015` / `R-030`):** Instead of immediately rejecting the claim, the system places it into `Pending Telephone Triage` for **48 hours**. A claims officer calls the passenger: *"Does the jacket have any brand tags, inner pocket items, or unique zipper pulls?"* If the passenger says *"There is a red gym fob in the left pocket"*, staff confirms the match and approves the return.
* **The Engineering Trade-off Question:** Telephone calls consume valuable staff labor. How many call attempts (e.g. 2 vs. 3) and what waiting duration (48 hours vs. 72 hours) minimizes passenger abandonment without overflowing central storage lockers?

### Obstacle 2: Public Catalog Transparency vs. Fraud Prevention
* **The Conflict:** Passengers want to browse an online catalog of found items (`SR-006`) to see if their lost belongings were found. However, if the catalog publicly displays detailed photos, engraved initials, or serial numbers, dishonest users can browse the website, note those exact details, and file fraudulent claims. Conversely, if we hide everything down to generic labels ("Phone"), legitimate riders cannot identify their belongings.
* **Affected Goals:** `G-00` (Rider Self-Discovery vs. Fraud Prevention) and requirements `SR-005` vs. `SR-006`.
* **The Mitigation (`SR-005` / `R-013`):** Implement a **two-tier public/private challenge architecture**:
  1. *Public View:* Displays only broad category (e.g. "Smart Phone"), general brand ("Apple"), transit zone ("Subway Line 1"), and a 3-day date window. Photos and distinguishing marks are withheld.
  2. *Challenge Verification:* When filing a claim against that catalog entry, the claimant must supply an unprompted private identifier (such as the phone's lock-screen photo or passcode) that matches hidden fields in the database before staff reviews the claim.
* **The Engineering Trade-off Question:** Does redacting photos completely protect property at the expense of fewer riders claiming items, or can computer-vision blurring of logos and unique marks strike a better balance?

---

## 5. Activity C: Measurable Quality Requirements Workshop

### What are we supposed to do?
Rewrite at least **three vague quality statements** into measurable, testable specifications. Each must specify:
1. Operational conditions / context.
2. Observable response / behavior.
3. Defensible quantitative threshold / fit criterion.
4. Short rationale explaining whether the threshold comes from **documented evidence / law** or is a **provisional engineering assumption**.

---

### Detailed Point-by-Point Explanation

### 1. `QR-001`: Staff Audit Trail Logging (Auditability & Non-Repudiation — Refines `QR-001` / `R-019`)
* **Vague Statement:** *"The system shall log staff activity and keep an audit trail of user actions for security and compliance."*  
  *(Why this is bad: Which actions? What fields must be logged? How fast? Can staff delete them? You cannot test this without concrete criteria.)*
* **Measurable Specification:** For 100% of auditable staff transactions (intake creation, bin movements, claim reviews, phone triage notes, status changes, and physical releases), the system shall write an immutable append-only audit record containing authenticated staff ID, action enum, record ID, and UTC timestamp within **$\le 1.0$ second** of commit, with **zero update or delete operations** permitted on the audit log.
* **Threshold Rationale:**
  * **100% Transaction Capture & Append-Only Storage (Statutory Compliance & Legal Non-Repudiation):** Grounded in municipal compliance and regulatory audit standards (**Ontario MFIPPA**). Transit agencies are legally required to maintain non-repudiable logs showing which employee accessed confidential property or authorized releases to prevent internal theft or wrongful release liability.
  * **$\le 1.0$ Second Logging Latency (Provisional Engineering Assumption):** Asynchronous database write buffers ensure that audit logging does not stall frontline user transactions, allowing records to be written safely within a 1.0-second window.

### 2. `QR-002`: Payment Card PII Sanitization (Security & Privacy — Refines `QR-002` / `R-020`)
* **Vague Statement:** *"The system must keep passenger credit card information safe in staff notes."*  
  *(Why this is bad: How do you prove data is "safe"? What types of cards?)*
* **Measurable Specification:** In all free-text triage notes entered by staff, client-side and server-side validation shall detect and sanitize **100%** of 15- and 16-digit numeric sequences matching the Luhn algorithm, replacing the card number with `[CARD MASKED: <Issuer> ****-<Last4>]` before database write, resulting in **0 raw card numbers** in storage or logs.
* **Threshold Rationale:**
  * **100% Luhn Sanitization (Statutory Law & Industry Standards):** Under **PCI-DSS Requirement 3.4** and **Ontario MFIPPA Section 42**, transit agencies face severe financial penalties and mandatory privacy breach disclosures if raw payment card numbers are stored in unencrypted text fields.
  * **Retaining Issuer and Last 4 Digits (Operational Verification Standard):** Claims officers verifying lost wallets routinely confirm identity by asking the claimant for the issuing bank and last 4 digits (e.g. "TD Visa ending in 4192"). Preserving only those attributes satisfies verification without storing actionable payment data (Lab 5 Criterion 5).

### 3. `CON-001`: Public Web Service Availability (Reliability — Refines `CON-001` / `R-024`)
* **Vague Statement:** *"The public lost-and-found website should be reliable and available to riders at all times."*  
  *(Why this is bad: 100% uptime is impossible; what about planned server updates?)*
* **Measurable Specification:** Public reporting and status tracking endpoints shall maintain **$\ge 99.5\%$ monthly uptime** (permitting at most **$\le 3.6$ hours** of unplanned downtime per 30-day month) evaluated by automated synthetic probes running every **60 seconds**, excluding pre-announced maintenance scheduled between 2:00 AM and 5:00 AM with at least **48 hours advance notice**.
* **Threshold Rationale:**
  * **99.5% Monthly Uptime (Enterprise Transit IT SLA — `DEP-06`):** Lost & Found is a public service system, but not a safety-critical train signaling system (which requires 99.99% "four nines" uptime). 99.5% provides reliable 24/7 access while keeping hosting infrastructure costs within public transit municipal budgets.
  * **60-Second Probe & 48-Hour Notice (Provisional Operational Assumptions):** 60-second polling detects outages quickly without overloading servers; 48 hours gives riders adequate warning before scheduled overnight maintenance.

---

## 6. How to Walk Through this Artifact with the TA (Sign-Off Guide)

When presenting `goals-quality.md` to the TA at the end of the lab:

1. **Goal-to-Requirement Check:**
   - Point to **Goal `G-32` (Remote Courier Delivery)**.
   - Explain how it represents an **OR-alternative** to in-person pickup (`G-31`).
   - Show how it traces directly to **`FR-010` (Dispatch Record)** and **`FR-011` (Delivery Fee Payment Gate)** to prevent unpaid shipping costs.
2. **Quality Requirement Check:**
   - Point to **`QR-M02` (Payment Card Sanitization)**.
   - Highlight the **measurable fit criterion** (100% Luhn sanitization; 0 raw card sequences stored).
   - Show the **evidence discipline**: 100% sanitization is rooted in statutory law (PCI-DSS and MFIPPA), whereas retaining the last 4 digits is rooted in operational wallet verification practice.
3. **Show the Clean Pre-Lab Audit:**
   - Mention that requirement `FR-008` (Delay Notice) was evaluated, and its weak static rationale will be replaced with dynamic telemetry in Sprint 2.

