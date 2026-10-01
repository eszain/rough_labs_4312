# Sprint 0 Clinic Checkpoint

**Course:** EECS 4312 – Software Requirements Engineering  
**Project:** Public Transit Lost & Found System (TLFS)  
**Deliverable:** `sprint0-clinic.md`

This document is the formal Sprint 0 clinic checkpoint. It provides an expanded set of context corrections, an augmented evidence audit, additional requirement revisions, and a full list of unresolved questions.

---

## 1. Stakeholder & Context Corrections 

The initial system boundary and stakeholder map omitted important organizational details. The following two major corrections were applied:

1. Formally added a Privacy & Legal Compliance Officer (MFIPPA / IPC) to the stakeholder map. The initial model treated claimant data (names, IDs, phone numbers) as standard inventory data. The system must comply with the Municipal Freedom of Information and Protection of Privacy Act (MFIPPA), requiring automated data anonymization and strict retention periods for PII.
2. Added Station Customer Service Agents (CSAs) as intermediate custodians. The original model assumed items jumped directly from "Found by Passenger/Operator" to "Central Staff at Bay Station". Station CSAs at fare booths act as frontline intake points, requiring the system to handle intermediate, temporary custody logs before physical courier transport to the central hub.

---

## 2. Evidence Discipline Audit 

All claims within Sprint 0 were audited to separate documented evidence from analogies, simulations, and team assumptions.

| # | Current Claim Statement | Original Flaw | Audited Classification | Rewritten Honest Statement |
|---|---|---|---|---|
| **1** | *"Items found on transit vehicles take 24 to 48 hours to reach the central Lost Articles Office."* | None | **Documented / Public Evidence** | *Retained as evidence:* TTC public documentation establishes a 24–48 hour transit logistics delay for physical collection and sorting. |
| **2** | *"Unclaimed items are retained for exactly 90 days before auction or donation."* | None | **Documented / Public Evidence** | *Retained as evidence:* Mandated by City of Toronto Municipal Code and published TTC bylaws. |
| **3** | *"Automated multi-attribute matching will reduce staff manual claim review workload by 60%."* | Presented assumption as a fact | **Analogy & Simulation** | **Rewritten:** *"Based on analogies with airline baggage reconciliation, we hypothesize a 60% manual workload reduction."* |
| **4** | *"Transit operators will log found items using their personal mobile devices before ending their shifts."* | Unvalidated operational guess | **Assumption** | **Rewritten:** *"We assume operators can access mobile terminals to submit intake logs at shift end; operational feasibility remains an unverified assumption."* |
| **5** | *"Transit fleet schedules can be queried in real time to match passenger travel dates with specific vehicles."* | None | **Direct / Public Evidence** | *Retained as evidence:* Validated against published Open Transit GTFS-RT API documentation. |
| **6** | *"Passengers can accurately report the exact timestamp (within 5 minutes) of when they lost an item."* | Unvalidated human behavior | **Assumption** | **Rewritten:** *"While the system accepts precise timestamps, we must assume that passengers often only know a generalized time window (e.g., a 2-hour range) for when an item was lost."* |

---

## 3. Candidate-Requirement Revisions

The following seven candidate requirements were rewritten to resolve issues of atomicity, clarity, scope, premature design, and operational triage prioritization.

### Revision 1: R5 – Online Lost-Item Submission (Resolved Atomicity)
- **Before:** *"The system shall provide an online form allowing passengers to submit lost reports with category, brand, photos, automatically generate a tracking number, and send an email receipt."*
- **After (Atomic):**
  - **R5.1 (Data Capture):** *"The system shall allow claimants to submit a lost-item report capturing category, descriptive attributes, loss timestamp, and digital photographs."*
  - **R5.2 (Confirmation):** *"Upon successful submission, the system shall generate a unique reference token and dispatch an acknowledgement notification to the claimant."*

### Revision 2: R7 – Matching Engine (Resolved Premature Design)
- **Before:** *"The system shall automatically compare lost reports with found records using natural language processing (NLP) and image similarity algorithms to compute a confidence score."*
- **After (Implementation-Agnostic):** *"The system shall evaluate submitted lost reports against found records by comparing shared descriptive attributes and temporal proximity to compute and rank potential candidate matches."*

### Revision 3: R9 – Delivery Services (Resolved Atomicity & Vendor Lock-in)
- **Before:** *"The system shall integrate with Canada Post APIs to calculate shipping rates, collect payment via credit card, generate labels, and track delivery."*
- **After (Modular):**
  - **R9.1 (Shipping Dispatch):** *"For claimants verified for remote return, the system shall generate standardized electronic courier dispatch manifests with the designated logistics provider."*
  - **R9.2 (Fee Settlement):** *"The system shall confirm receipt of remote delivery fee payment prior to releasing an item from inventory to the carrier."*

### Revision 4: R17 – Security Controls (Resolved Compound Protocols)
- **Before:** *"The system shall enforce role-based access control (RBAC), multi-factor authentication for staff, and TLS 1.3 encryption across all communication."*
- **After (Separated Concerns):**
  - **R17.1 (Authorization):** *"The system shall restrict access to found-item records based on authenticated staff roles and privileges."*
  - **R17.2 (Transport Security):** *"All communications between external clients and system endpoints shall be encrypted using current industry-standard cryptographic transport protocols."*

### Revision 5: R6 – Operator Intake (Resolved Premature Design)
- **Before:** *"The system shall provide a mobile-optimized form allowing operators to log items with barcode scanning and secure custody transfers."*
- **After (Technology-Neutral):** *"The system shall allow transit operators to digitally log found items and attach a unique physical tracking identifier to the item during initial intake."*

### Revision 6: R11 – Public Catalog (Resolved Ambiguous Scope/Privacy)
- **Before:** *"The system shall publish a searchable catalog of found items with photo thumbnails, category, location, and date found."*
- **After (Privacy-Bounded):** *"The system shall publish a searchable catalog of found items that explicitly redacts uniquely identifying features (e.g., serial numbers, custom engravings, detailed contents) to prevent fraudulent claims."*

### Revision 7: R3 / R8 – Priority Categorization for Urgent Property (Resolved Scope & Operational Triage)
- **Before (Uniform Treatment / Scope Blindspot):** *"The system shall queue all lost-item reports and found-item records regardless of item category or urgency."*
- **After (Differentiated Priority & Triage):**
  - **R3.1 (Urgent Property Classification):** *"The system shall categorize high-impact personal essentials (e.g., smartphones, laptops, medical devices, government-issued IDs, wallets) as high-priority items upon intake or loss reporting."*
  - **R3.2 (Expedited Verification Triage):** *"The system shall prioritize high-priority items at the top of staff verification queues and trigger rapid matching alerts to speed up recovery before standard 24–48 hour batch processing."*


---

## 4. Unresolved Questions

1. Does the Amalgamated Transit Union (ATU Local 113) collective agreement permit vehicle operators to log items on mobile devices during shift turnarounds, or must logging occur exclusively at depot desktop terminals?
2. If a high-value item (e.g., laptop) is lost or damaged in transit by the third-party courier, who bears the legal and financial liability?
3. What is the exact API protocol and data refresh latency supported by the transit authority's internal vehicle dispatch system?
4. Do subway Station CSAs have secure lockboxes capable of holding large items (e.g., bicycles, large luggage) temporarily, or must such items bypass the booth?
5. What is the operational protocol and system disposition state for items deemed perishable (food) or hazardous (leaking batteries) upon intake?
6. If the primary payment gateway is offline, what is the fallback mechanism for processing delivery fees?
7. What specific WCAG compliance level (e.g., AA or AAA) is mandated by the transit agency for the public-facing claimant portal under the Accessibility for Ontarians with Disabilities Act (AODA)?
