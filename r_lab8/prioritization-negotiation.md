# Lab 8: Requirements Prioritization & Stakeholder Negotiation

## Activity A: Prioritization Method and Scoring

We use a weighted scoring model across three criteria on a 1 to 5 scale:
- User Value (UV, weight 0.35): Direct benefit to passenger property recovery and self-service convenience.
- Risk Reduction & Compliance (RC, weight 0.35): Fraud prevention, municipal privacy compliance (MFIPPA), and custody accountability.
- Implementation Simplicity (IS, weight 0.30): Ease of construction and absence of external API dependencies (5 = lowest effort, 1 = highest complexity).

| Requirement ID | Requirement Title | UV (0.35) | RC (0.35) | IS (0.30) | Weighted Score | Baseline Rank |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| R-010 / FR-004 | Urgent Property Classification | 5 | 5 | 4 | 4.70 | 1 |
| R-008 / FR-002 | Candidate Match Ranking | 5 | 4 | 3 | 4.05 | 2 |
| R-026 / FR-012 | Automated Claim Notifications | 5 | 3 | 4 | 4.00 | 3 |
| R-030 / FR-015 | Telephone Triage Management | 4 | 4 | 4 | 4.00 | 3 |
| R-013 / SR-005 | Privacy-Bounded Public Browsing | 4 | 4 | 3 | 3.70 | 5 |
| R-028 / SR-006 | Public Catalog Search & Filter | 4 | 2 | 4 | 3.30 | 6 |
| R-018 / FR-011 | Delivery Fee Settlement Gate | 3 | 4 | 2 | 3.05 | 7 |
| R-017 / FR-010 | Remote Courier Dispatch Record | 3 | 2 | 2 | 2.35 | 8 |

## Activity B: Sensitivity Analysis

To test ranking stability under constrained Sprint 2 engineering capacity, we shift weights to emphasize implementation simplicity:
- Modified weights: Implementation Simplicity 0.50, User Value 0.25, Risk Reduction 0.25.
- Recalculated scores and shifts:

| Requirement ID | Requirement Title | UV (0.25) | RC (0.25) | IS (0.5) | Weighted Score | Baseline Rank |
|---|---|:---:|:---:|:---:|:---:|:---:|
| R-010 / FR-004 | Urgent Property Classification | 5 | 5 | 4 | 4.50 | 1 |
| R-008 / FR-002 | Candidate Match Ranking | 5 | 4 | 3 | 3.75 | 4 |
| R-026 / FR-012 | Automated Claim Notifications | 5 | 3 | 4 | 4.00 | 2 |
| R-030 / FR-015 | Telephone Triage Management | 4 | 4 | 4 | 4.00 | 2 |
| R-013 / SR-005 | Privacy-Bounded Public Browsing | 4 | 4 | 3 | 3.50 | 5 |
| R-028 / SR-006 | Public Catalog Search & Filter | 4 | 2 | 4 | 3.50 | 5 |
| R-018 / FR-011 | Delivery Fee Settlement Gate | 3 | 4 | 2 | 2.75 | 7 |
| R-017 / FR-010 | Remote Courier Dispatch Record | 3 | 2 | 2 | 2.25 | 8 |

  -    R-010 (Urgent Classification): Score 4.50 (retains Rank 1).
  - R-026 (Notifications): Score increases to 4.00 (rises from Rank 3 to tied Rank 2).
  - R-030 (Phone Triage): Score 4.00 (rises from Rank 3 to tied Rank 2).
  - R-008 (Match Ranking): Score drops to 3.75 (slips from Rank 2 to Rank 4 due to algorithmic complexity).
  - R-013 (Public Browsing): Score drops to 3.50 (ties R-028 at Rank 5).
  - R-017 / R-018 (Courier & Payment): Scores fall to 2.25 and 2.75 (remain locked at bottom).
- Sensitivity observation:
The analysis demonstrates that the prioritization model is partially robust rather than completely stable. R-010 remains the highest priority regardless of weighting changes, while the middle-ranked requirements are more sensitive to engineering constraints. This distinction is important because it identifies requirements that should remain priorities under different circumstances and those that may be rescheduled depending on available development capacity.

Consequently, Sprint 2 should prioritize R-010, R-026, and R-030. R-008 should remain a valuable requirement but may be scheduled after simpler, higher-return features. R-017 and R-018 should be deferred until their external dependencies, vendor agreements, and implementation arrangements are sufficiently established.

## Activity C: Role-Based Stakeholder Negotiation

1. Stakeholder Roles and Positions:
- Zain (Passenger Advocate): Demands self-service public browsing (R-013) and remote courier delivery (R-017, R-018) in Sprint 2 to eliminate in-person trips to central lost and found.
- Anirudh (Transit Operations & Privacy Officer): Prioritizes fraud prevention and statutory privacy. Opposes public browsing without strict attribute redaction, and rejects courier shipping until payment settlement is automated.
- Sufyan (Technical Lead): Warns that courier logistics and payment gateways (DEP-04, DEP-05) exceed remaining Sprint 2 developer hours, threatening core inventory stabilization.

2. Negotiation Conflict:
Releasing remote delivery (R-017, R-018) versus public catalog discovery (R-013, R-028) under strict Sprint 2 capacity limits.

3. Negotiated Alternatives and Concessions:
- Alternative 1: Attempt both features, risking an unstable release with untested payment handling. Rejected by Technical Lead.
- Alternative 2: Defer both features and restrict Sprint 2 strictly to internal staff intake workflows. Rejected by Passenger Advocate.
- Alternative 3 (Accepted Compromise): Deliver privacy-bounded catalog browsing (R-013) with basic search (R-028) in Sprint 2. Defer remote courier dispatch (R-017) and payment settlement (R-018) to Sprint 3 once third-party gateway contracts are signed.
- Concessions: Zain concedes remote delivery in Sprint 2 in exchange for guaranteed public catalog search filters. Anirudh concedes staff review bandwidth to support public intake inquiries, provided catalog attributes remain redacted.

4. Resulting Baseline Scope and MoSCoW Adjustments:
- R-013 (Privacy-Bounded Public Browsing): Retained as Should Have in Sprint 2 release scope.
- R-028 (Public Catalog Search & Filter): Promoted from Could Have to Should Have for Sprint 2.
- R-017 (Remote Courier Dispatch Record): Reclassified from Should Have to Could Have, deferred to Sprint 3.
- R-018 (Delivery Fee Settlement Gate): Reclassified from Should Have to Could Have, deferred to Sprint 3.

