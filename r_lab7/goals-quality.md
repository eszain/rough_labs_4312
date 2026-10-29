# Lab 7: Goal/Obstacle Analysis & Measurable Quality Requirements

## Activity A: Goal Model & Refinement

<img width="1491" height="1055" alt="image" src="https://github.com/user-attachments/assets/40dc8cb5-63b3-49ef-a434-92274b7081b0" />


Root Goal: G-00 Return recovered transit property to verified owners without unauthorized handover.

### Goal Decomposition & Alternatives
* **G-10 (AND-Refinement):** Ingest found items and track intermediate custody.
  - **G-11:** Enable flexible passenger reporting without vehicle numbers -> Linked to **SR-001** (R-003).
  - **G-12:** Complete shift intake and barcode tag binding in $\le$ 45s -> Linked to **FR-001** (R-006).
  - **G-13:** Log station custody transfers between operators and CSAs -> Linked to **SR-004** (R-007).
* **G-20 (AND-Refinement):** Adjudicate ownership through verified claim matching.
  - **G-21:** Rank potential inventory matches by similarity score -> Linked to **FR-002** (R-008).
  - **G-22:** Mandate staff ID, timestamp, and notes for all decisions -> Linked to **FR-003** (R-009).
* **G-30 (OR-Alternative):** Restitution Pathways
  - **G-31 (Alternative 1):** In-person pickup with photo ID and claimant signature -> Linked to **FR-013** (R-027).
  - **G-32 (Alternative 2):** Remote courier delivery gated by payment settlement -> Linked to **FR-010** (R-017) and **FR-011** (R-018).

## Activity B: Obstacle and Conflict Analysis

1. **Obstacle 1: Vague Passenger Descriptions (Affects G-21 / FR-002)**
   - *Conflict:* Claimants omit brand or unique marks (`SR-001`), causing the ranking algorithm to produce dozens of tied low-confidence matches (~40–50%).
   - *Mitigation:* Implement `FR-015` (R-030) telephone triage, establishing a 48-hour clarification hold before permitting claim rejection.
   - *Trade-off:* Outbound calls prevent premature rejection of valid claims, but increase staff administrative overhead during intake surges.

2. **Obstacle 2: Public Catalog Transparency vs. Fraud Prevention (Affects G-00 / SR-005 vs SR-006)**
   - *Conflict:* Displaying detailed photos or unique marks enables fraudulent claims, while redacting all attributes prevents legitimate self-discovery.
   - *Mitigation:* Enforce a two-tier policy in `SR-005` displaying only broad category, station zone, and date window, requiring claimants to supply unprompted challenge attributes to verify.
   - *Trade-off:* Attribute redaction protects property custody, but lowers passenger self-service discovery rates.

## Activity C: Measurable Quality Requirements

1. **QR-M01 Frontline Intake Speed (Performance - Refines FR-001 / R-006):**
   - *Original Vague Statement:* "The staff interface should allow operators to log found items quickly during shifts."
   - *Measurable Specification:* During terminal shift turnaround with active cellular connection, median frontline intake and barcode binding shall complete in $\le$ 45 seconds across 10 sample trials, with backend API response round-trips $\le$ 1.5 seconds.
   - *Threshold Rationale:* 45 seconds is grounded in transit operational policy (3–5 minute turnaround layover window). The 1.5s API round-trip is an engineering assumption based on underground cellular jitter.

2. **QR-M02 Payment Card Sanitization (Security / Privacy - Refines QR-002 / R-020):**
   - *Original Vague Statement:* "The system must keep passenger credit card information safe in staff notes."
   - *Measurable Specification:* In free-text triage notes, the system shall detect and sanitize 100% of 15- and 16-digit sequences matching the Luhn algorithm, replacing them with `[CARD MASKED: <Issuer> ****-<Last4>]` before database write, resulting in 0 raw card numbers stored.
   - *Threshold Rationale:* 100% sanitization is grounded in statutory law (PCI-DSS Requirement 3.4 and Ontario MFIPPA). Retaining issuer and last 4 digits is an operational verification standard (Lab 5 Criterion 5).

3. **QR-M03 Public Web Availability (Reliability - Refines CON-001 / R-024):**
   - *Original Vague Statement:* "The public lost-and-found website should be reliable and available to riders at all times."
   - *Measurable Specification:* Public reporting and status endpoints shall maintain $\ge$ 99.5% monthly availability ($\le$ 3.6 hours unplanned downtime/month) via 60-second synthetic health probes, excluding pre-announced maintenance (48-hour advance notice, 2:00 AM – 5:00 AM window).
   - *Threshold Rationale:* 99.5% uptime is grounded in TTC IT Services Tier-2 application SLAs (`DEP-06`). The 60-second probe interval and 48-hour notice window are provisional operational assumptions.

## Pre-Lab Weak Rationale Audit (FR-008 / R-015 Central Delay Notice)
* *Weakness:* Current rationale ("curbs premature complaints") lacks empirical evidence that static 24–48h banners reduce inquiries, and provides no guidance for holiday weekend transit delays.
* *Refinement:* Replace static text with dynamic route-based intake latency estimates tied to call-volume metrics in Sprint 2.
