# EECS 4312 – Lab 3: Stakeholders, Context, Assumptions & Candidate Requirements

**Course:** EECS 4312 – Software Requirements Engineering (York University – Fall 2026)  
**Project:** Public Transit Lost & Found System (TLFS) — Sprint 0 Clinic  
**Deliverable File:** `lab3.md` (All activities combined)  
**Status:** Completed & Pre-Submission Verified  

---

## Overview

This document contains the complete deliverables for **Lab 3 (Sprint 0 Pre-Submission Clinic)**. It stress-tests the Sprint 0 stakeholder profiles, validates system context and interface boundaries, audits evidentiary claims, refines candidate requirements for atomicity and premature design, and documents formal lab checkpoint corrections.

---

## Activity A – Stakeholder Map Stress Test

### 1. Analysis of Core Stakeholders

| Stakeholder Role | Primary Operational Goal | Key Concern / Risk | Influence Level | Potential Stakeholder Conflict |
|---|---|---|---|---|
| **Transit Passenger / Claimant** | Rapidly report lost property, receive automated match notifications, and reclaim items with minimal travel and wait time. | **Privacy & Fraud:** Risk of personal contact/ID details being leaked; risk of fraudulent claimants claiming their property before they can. **Premature despair** caused by 24–48h physical transit delays. | **High** *(System adoption & public reputation driver; primary beneficiary)* | **Conflict with Lost & Found Staff:** Passengers desire full public catalog transparency with clear photos and descriptions to search easily; Staff must withhold identifying details (e.g., engravings, wallpapers, distinctive marks) to prevent fraudulent claims. |
| **Transit Vehicle Operator** *(Bus, Streetcar, Subway)* | Quickly register found items at route terminals or depots with minimal overhead during tight shift turnarounds. | **Administrative Burden:** Extra duties cutting into scheduled rest periods; fear of disciplinary tracking for logging delays; lack of reliable in-vehicle mobile connectivity. | **Medium to High** *(Unionized frontline workforce; if friction is too high, items will not be logged promptly)* | **Conflict with Management & Central Staff:** Management and Central Staff demand rich metadata (exact vehicle number, seat coordinate, timestamp, condition); Operators require a sub-60-second workflow to prevent schedule disruptions. |
| **Lost & Found Central Office Staff** *(Bay Station)* | Efficiently intake, catalog, verify ownership, manage secure physical storage, and coordinate return or disposition of items. | **Volume Overload & Liability:** Being overwhelmed by unverified claims, phone inquiries, and holding legal custody for high-value items (cash, electronics, jewelry). | **High** *(Daily operational custodians; workflow efficiency dictates system throughput and return rates)* | **Conflict with Operations Management:** Management pushes for rapid inventory turnover and auctioning to free up warehouse space; Staff prioritize extended holding windows to give legitimate owners a fair opportunity to recover belongings. |
| **Transit Operations Management** | Minimize operating costs, improve customer satisfaction scores, automate audit trails, and reduce warehouse storage overhead. | **PR & Budgetary Risk:** High public backlash from lost items or privacy breaches; cost and maintenance overruns of third-party integrations (courier APIs, payment gateways). | **High** *(Procurement authority, budget holders, and final decision-makers on system scope)* | **Conflict with Claimants:** Management mandates that courier shipping and processing fees be 100% cost-recovered from claimants; Passengers expect low-cost or fare-subsidized recovery as part of public transit service. |

---

### 2. Missing Stakeholders, Regulators, and External Roles Identified

During the stress test, four critical missing roles and systems were identified and integrated into the system boundary:

1. **Privacy & Legal Compliance Officer (Municipal Freedom of Information and Protection of Privacy Act - MFIPPA / IPC Regulator)**:
   - *Goal:* Ensure strict compliance with provincial privacy legislation regarding personal information collection, storage, and mandatory data destruction schedules.
   - *Concern:* Unauthorized storage of claimant photos, government ID copies, or unredacted serial numbers that could trigger regulatory investigations or privacy audits.
   - *Influence Level:* **High (Statutory Veto Power)** — Can mandate schema redesign or data purge rules.
   - *Conflict:* Conflicts with Central Staff and automated matching algorithms that perform better when retaining historical item descriptions and photos.

2. **Station Customer Service Agents (Station CSAs / Collectors)**:
   - *Goal:* Quickly accept found items dropped off by passengers at subway station fare booths and log custody transfer without halting passenger entry queues.
   - *Concern:* Lack of secure lockboxes at station booths and ambiguity regarding custody transfer timing to transit couriers.
   - *Influence Level:* **Medium** — Frontline intake point requiring lightweight custody logging.

3. **Law Enforcement / Police Liaison (Toronto Police Service Property Bureau)**:
   - *Goal:* Secure chain-of-custody transfer and immediate reporting for suspected stolen property, weapons, narcotics, or evidence in criminal investigations.
   - *Concern:* Civilian transit staff inadvertently returning stolen property or tampering with criminal evidence.
   - *Influence Level:* **High** — Statutory authority over contraband/stolen goods; supersedes standard 90-day retention policies.

4. **Third-Party Logistics / Delivery Courier (Canada Post / Purolator API)**:
   - *Goal:* Receive valid electronic shipping manifests, pre-paid postage confirmations, and dimension/weight data for item dispatches.
   - *Concern:* Transport of hazardous materials (e.g., damaged lithium-ion batteries) and delivery liability disputes for lost/damaged parcels.
   - *Influence Level:* **Medium** — Contracted operational external service.

---

## Activity B – Context & Boundary Consistency Check

### 1. Actor & External System Consistency Matrix

Every entity represented in the PlantUML Context Diagram (`context-diagram.puml`) is validated against the system scope and stakeholder documentation:

| Diagram Actor / External System | Documented in `stakeholders.md`? | Documented in `context.md`? | Directionality & Protocol | Boundary Classification |
|---|---|---|---|---|
| **Passenger / Claimant** | ✅ Yes (Section 1.1) | ✅ Yes (Section 2.1) | Bidirectional (Web HTTPS) | External Human Actor |
| **Transit Vehicle Operator** | ✅ Yes (Section 1.2) | ✅ Yes (Section 2.2) | Bidirectional (Mobile Web / Depot Terminal HTTPS) | External Human Actor |
| **Lost & Found Central Staff** | ✅ Yes (Section 1.3) | ✅ Yes (Section 2.3) | Bidirectional (Internal Portal HTTPS + 2FA) | External Human Actor (Admin) |
| **Transit Operations Management** | ✅ Yes (Section 1.4) | ✅ Yes (Section 2.4) | Bidirectional (Reporting Portal HTTPS) | External Human Actor (Admin) |
| **Transit CAD/AVL System** | ✅ Yes (Section 2.5) | ✅ Yes (Section 4.1) | **Unidirectional (Incoming Read-Only REST API)** | External Software System |
| **Payment Gateway (Stripe/Moneris)** | ✅ Yes (Section 2.7) | ✅ Yes (Section 4.2) | Bidirectional (REST Webhook / PCI Tokenized) | External Third-Party Service |
| **Courier / Delivery API (Canada Post)** | ✅ Yes (Section 2.8) | ✅ Yes (Section 4.3) | Bidirectional (REST API / Label Ingestion) | External Third-Party Service |
| **Notification Gateway (Twilio / SendGrid)** | ✅ Yes (Section 2.6) | ✅ Yes (Section 4.4) | Unidirectional Outgoing (SMTP / SMS API) | External Third-Party Service |

---

### 2. Boundary Verification & Scope Refinements

1. **Physical Handover vs. Digital Verification Boundary:**
   - *Issue Identified:* In initial drafts, the system was vaguely described as "handling item return at Bay Station."
   - *Correction / Boundary Rule:* The software system **only** validates claimant identity tokens and records staff disposition signatures. The physical verification of physical government photo IDs and the physical custody transfer across the counter at Bay Station remain strictly **external manual processes**.
2. **CAD/AVL Vehicle Telemetry Boundary:**
   - *Issue Identified:* Unclear permissions regarding vehicle fleet databases.
   - *Correction / Boundary Rule:* The interface is strictly **read-only**. The system queries run/block assignments to correlate vehicle IDs with route timestamps; it never writes to or interfaces with safety-critical vehicle control networks.
3. **PCI-DSS Compliance Boundary:**
   - *Correction / Boundary Rule:* All payment processing for shipping and handling occurs inside hosted fields provided by the PCI-compliant gateway. No payment card numbers, CVVs, or bank data cross into or reside within the Lost & Found system database.

---

## Activity C – Evidence Discipline (Audit of Six Claims)

In accordance with course standards, claims must be rigorously separated into **Direct Evidence**, **Documented/Public Evidence**, **Analogy**, **Simulation**, or **Assumption**. Statements presenting hypotheses as established facts have been rewritten.

### Claim Audit Matrix

| # | Current Claim Statement | Evidence Classification | Source / Justification | Rewritten Honest Statement |
|---|---|---|---|---|
| **1** | *"Items found on transit vehicles take 24 to 48 hours to reach the central Lost Articles Office at Bay Station."* | **Documented / Public Evidence** | Official TTC public Lost & Found portal guidelines, FAQs, and passenger advisory bulletins. | *Retained as an established operational baseline:* Public TTC documentation establishes that items found on surface vehicles or subway cars require 24–48 hours to be physically collected, sorted, and routed through central transit logistics to Bay Station. |
| **2** | *"Unclaimed items are retained for exactly 90 days before being auctioned off or donated, with proceeds supporting transit operations."* | **Documented / Public Evidence** | City of Toronto Municipal Code, TTC Corporate Policy on Unclaimed Property, and documented public auction contracts. | *Retained as an established policy constraint:* Published TTC administrative policies mandate a 90-day retention holding period for general lost property prior to commercial auction or charitable donation. |
| **3** | *"Automated multi-attribute matching will reduce staff manual claim review workload by 60%."* | **Analogy & Simulation** *(Previously mislabeled as a verified fact)* | Inferred from published case studies of airline baggage reconciliation systems (analogy) and preliminary project workflow models (simulation). | **Rewritten:** *"Based on an analogy with commercial airline baggage reconciliation systems, we hypothesize that automated attribute and keyword matching can reduce manual inquiry review by up to 60%; this time-savings projection is currently an unvalidated assumption that must be tested via staff workflow simulations in Sprint 1."* |
| **4** | *"Transit operators will log found items using their personal or agency-issued mobile devices before ending their shifts."* | **Assumption** *(Previously presented as a guaranteed workflow)* | Team assumption based on modern mobile web availability; no consultation with transit union (ATU 113) or fleet operations has taken place. | **Rewritten:** *"We assume that transit operators have access to either vehicle-mounted terminals or depot workstations to submit intake logs at shift end; operational feasibility, device provisioning, and union work-rule constraints remain unverified assumptions requiring operational stakeholder elicitation."* |
| **5** | *"Over 80% of passengers who lose items would prefer paying for home courier delivery rather than traveling to Bay Station in person."* | **Assumption** *(Previously framed as user demand)* | Unverified team assumption regarding passenger convenience and price elasticity. | **Rewritten:** *"It is assumed that a substantial segment of claimants would value home courier delivery over in-person collection at Bay Station; passenger willingness to pay full shipping costs is an unvalidated hypothesis that will be surveyed during Sprint 1 elicitation."* |
| **6** | *"Transit fleet schedules and vehicle block numbers can be queried in real time to match passenger travel dates/times with specific vehicles."* | **Direct / Public Evidence** | Publicly accessible GTFS (General Transit Feed Specification) real-time feeds and open TTC route schedule data. | *Retained as documented technical evidence:* Public GTFS-RT APIs provide route, trip, and vehicle block tracking data, confirming the feasibility of timestamp/route correlation, although integration permissions for internal vehicle telemetry remain to be confirmed. |

---

## Activity D – Candidate Requirements Clinic

Review of eight candidate requirements from the backlog (`requirements-backlog.md`) for **Atomicity**, **Clarity**, **Scope**, and **Premature Design**.

> **Note:** All items below remain strictly **Candidate Requirements**; Sprint 0 establishes an exploratory backlog rather than a frozen contractual baseline.

### 1. Requirement Review Table

| ID | Title & Original Statement | Atomicity Review | Clarity & Scope Review | Premature Design Check | Candidate Status |
|---|---|---|---|---|---|
| **R5** | **Online Lost-Item Report Submission:** *"The system shall provide an online form allowing passengers to submit lost-item reports with category, brand, color, date/time, route, and photo attachments, automatically generate a tracking number, and send an email receipt."* | **Violates Atomicity:** Bundles form submission, file ingestion, unique identifier generation, and email notification into one giant requirement. | Good clarity; matches Sprint 0 public intake scope. | Free of premature design, but mixes frontend interaction with background notification. | **Candidate** *(Requires decomposition into sub-requirements)* |
| **R6** | **Operator / Staff Item Intake:** *"The system shall provide a mobile-optimized intake form allowing operators to log items with barcode scanning, location tags, and secure custody transfers."* | **Violates Atomicity:** Combines item metadata recording, optical barcode scanning, and multi-party chain of custody. | Clear purpose, but scope is broad across multiple user personas. | **Premature Design:** Dictates "barcode scanning" specifically, excluding QR codes, RFID tags, or manual alphanumeric serial entry. | **Candidate** *(Needs technology-neutral wording)* |
| **R7** | **Automated Matching Engine:** *"The system shall automatically compare lost reports with found records using natural language processing (NLP) and image similarity algorithms to compute a confidence score."* | **Atomic:** Focuses on the single capability of match comparison and scoring. | Clear criteria, appropriate algorithmic scope. | **Severe Premature Design:** Prescribes implementation techniques ("NLP and image similarity algorithms") rather than specifying the required functional outcome (scoring similarity across attributes). | **Candidate** *(Must be rewritten to specify behavior, not ML implementation)* |
| **R8** | **Verification Workflow:** *"The system shall provide a verification queue for staff to inspect claimant evidence, approve or reject matches, and trigger pickup or delivery instructions."* | **Borderline Compound:** Combines queue viewing, decision recording, and notification dispatch. | Good clarity and operational alignment. | No premature tech design; describes operational staff workflow well. | **Candidate** *(Refine verification decision logging)* |
| **R9** | **Delivery Partner Integration:** *"The system shall integrate with Canada Post APIs to calculate shipping rates, collect payment via credit card, generate shipping labels, and track delivery status."* | **Violates Atomicity:** Blends postal rate calculation, merchant credit card processing, label printing, and external package tracking. | Exceeds minimum viable problem scope for Sprint 0. | **Premature Design:** Hardcodes a specific vendor ("Canada Post API") and specific payment instrument ("credit card"). | **Candidate** *(Optional / Should be split into distinct payment and shipping services)* |
| **R11** | **Public Catalog of Found Items:** *"The system shall publish a searchable catalog of found items with photo thumbnails, category, location, and date found."* | **Atomic:** Single functional viewing capability. | **Unclear & Risky Scope:** Lacks explicit privacy and anti-fraud masking constraints (e.g., does not specify withholding unique identifying markings). | Clean of tech bias, but operational rules must be tightened. | **Candidate** *(Must state privacy redaction rules)* |
| **R15** | **Intake Speed (Quality Requirement):** *"Staff and operators shall be able to complete item intake in under 60 seconds."* | **Atomic:** Specifies a single performance attribute. | **Unclear Boundary Condition:** Unspecified whether 60 seconds includes photographing the item, bagging, and applying a physical barcode tag, or solely digital form entry. | Clean of design bias; specifies measurable operational latency. | **Candidate** *(Needs clear operational test boundary)* |
| **R17** | **Security & Access Control:** *"The system shall enforce role-based access control (RBAC), multi-factor authentication for staff, and TLS 1.3 encryption across all communication."* | **Violates Atomicity:** Mixes authorization (RBAC), user authentication (MFA), and transport-layer cryptographic protocols. | High clarity; standard security requirement. | **Premature Design:** Dictates specific protocol version ("TLS 1.3") in a general security policy requirement. | **Candidate** *(Split into Authentication, Authorization, and Transport Security)* |

---

## Lab Checkpoint & Synthesis Deliverables

### (1) Two Stakeholder & Context Corrections

1. **Correction 1 (Stakeholder & Legal Modeling):**  
   *Problem:* The initial Sprint 0 model treated Lost & Found data as generic transactional inventory, ignoring municipal privacy and regulatory liabilities.  
   *Correction:* Formally added the **Privacy & Legal Compliance Officer (MFIPPA / IPC)** and **Station Customer Service Agents** to `stakeholders.md`. Added a mandatory data retention and automated PII anonymization constraint governing claimant records once claims are closed or abandoned.

2. **Correction 2 (Context Diagram & Interface Boundary):**  
   *Problem:* The context diagram did not clearly isolate software boundaries from physical actions, creating the false impression that physical identity inspection and parcel handover were automated inside the software.  
   *Correction:* In `context.md` and `context-diagram.puml`, clearly marked the Bay Station in-person ID check and counter handover as **External Physical Workflow**. Clarified that the transit CAD/AVL link is **strictly unidirectional (read-only)** to preserve rail/bus operational safety boundaries.

---

### (2) The Six-Claim Evidence Audit Summary

| Claim # | Claim Focus | Original Flaw | Audited Category | Corrective Action Taken |
|---|---|---|---|---|
| **1** | 24–48h item transit delay | None | **Documented / Public Evidence** | Retained with citation to official TTC Lost & Found operational rules. |
| **2** | 90-day retention holding rule | None | **Documented / Public Evidence** | Retained with citation to City of Toronto Municipal Code & TTC bylaws. |
| **3** | 60% staff workload reduction | Presented assumption as a fact | **Analogy & Simulation** | Rewritten as an unvalidated hypothesis derived from airline baggage analogies. |
| **4** | Operator mobile logging on shift | Unvalidated operational guess | **Assumption** | Rewritten as an assumption requiring depot workflow & union consultation. |
| **5** | 80% claimant courier demand | Speculative customer preference | **Assumption** | Rewritten as an unverified market hypothesis to be surveyed in Sprint 1. |
| **6** | GTFS real-time schedule lookup | None | **Direct / Public Evidence** | Validated against published Open Transit GTFS-RT API documentation. |

---

### (3) Four Candidate-Requirement Revisions

The following four candidate requirements have been rewritten to resolve issues of atomicity, clarity, scope, and premature design:

#### Revision 1: R5 – Online Lost-Item Submission (Resolved Atomicity)
- **Before (Compound):**  
  *"The system shall provide an online form allowing passengers to submit lost-item reports with category, brand, color, date/time, route, and photo attachments, automatically generate a tracking number, and send an email receipt."*
- **After (Atomic & Clean):**  
  - **R5.1 (Intake Data Capture):** *"The system shall allow claimants to submit a lost-item report capturing item category, descriptive attributes, loss timestamp, estimated transit route/location, and digital photographs."*
  - **R5.2 (Report Confirmation):** *"Upon successful submission of a lost-item report, the system shall generate a unique reference token and dispatch an acknowledgement notification to the claimant's registered contact address."*

#### Revision 2: R7 – Matching Engine (Resolved Premature Design)
- **Before (Premature Implementation Dictation):**  
  *"The system shall automatically compare lost reports with found records using natural language processing (NLP) and image similarity algorithms to compute a confidence score."*
- **After (Implementation-Agnostic):**  
  *"The system shall evaluate submitted lost-item reports against registered found-item records by comparing shared descriptive attributes, geographic routing, and temporal proximity to compute and rank potential candidate matches."*

#### Revision 3: R9 – Delivery Services (Resolved Atomicity & Vendor Lock-in)
- **Before (Compound & Vendor-Specific):**  
  *"The system shall integrate with Canada Post APIs to calculate shipping rates, collect payment via credit card, generate shipping labels, and track delivery status."*
- **After (Modular & Technology-Neutral):**  
  - **R9.1 (Shipping Quotation & Dispatch):** *"For claimants verified for remote item return, the system shall calculate applicable shipping fees and generate standardized electronic courier dispatch manifests with the designated logistics provider."*
  - **R9.2 (Handling Fee Settlement):** *"The system shall confirm receipt of claimant payment for remote delivery fees prior to releasing an item from inventory to the delivery carrier."*

#### Revision 4: R17 – Security Controls (Resolved Compound Protocols & Design Bias)
- **Before (Compound & Version-Specific):**  
  *"The system shall enforce role-based access control (RBAC), multi-factor authentication for staff, and TLS 1.3 encryption across all communication."*
- **After (Separated Concerns):**  
  - **R17.1 (Role-Based Authorization):** *"The system shall restrict access to found-item records, claimant personal data, and custody status changes based on authenticated staff roles and administrative privileges."*
  - **R17.2 (Data in Transit Protection):** *"All communications between external clients and system endpoints shall be encrypted using current industry-standard cryptographic transport protocols."*

---

### (4) Short List of Unresolved Questions for Sprint 1

1. **Transit Union & Shift Work Rules:**  
   *Does the collective agreement (ATU Local 113) permit transit vehicle operators to log lost items on mobile devices during turnaround recovery time, or must digital logging be restricted to end-of-shift depot terminals?*
2. **Delivery Liability & Chain of Custody:**  
   *If a high-value item (e.g., laptop or jewelry) is damaged or lost in transit by the third-party courier, who bears legal liability: the transit agency, the courier, or the claimant? What insurance verification is required prior to shipping?*
3. **MFIPPA Photographic Retention Limits:**  
   *Under Ontario privacy guidelines, what is the maximum lawful retention window for uploaded personal photos (which may contain claimant faces or personal background details) once an item has been successfully claimed or closed?*
4. **CAD/AVL Fleet Telemetry Latency:**  
   *What is the update frequency and query rate limit of the transit agency’s internal vehicle dispatch API when linking historical vehicle block runs to passenger-reported timestamps?*
5. **In-Person Unclaimed Property Return at Subway Stations:**  
   *Can station CSAs accept lost items from passengers and hold them in lockboxes, or does transit policy strictly mandate that only vehicle operators and central office staff handle property intake?*

---

## Conclusion & TA Verification Checklist

- [x] **Activity A:** Complete stakeholder stress test with goals, concerns, influence ratings, conflicts, and 4 missing roles added.
- [x] **Activity B:** Context consistency cross-referenced across actors, external systems, and interface boundaries.
- [x] **Activity C:** Six claims audited and classified; all assumptions previously presented as facts rewritten honestly.
- [x] **Activity D:** Eight candidate requirements reviewed for atomicity, clarity, scope, and premature design.
- [x] **Lab Checkpoint:** Two context corrections, 6-claim audit matrix, 4 requirement revisions, and 5 unresolved sprint questions provided.
