# System Context

## Public Transit Lost & Found System

---

## 1. System Under Consideration

The **Public Transit Lost & Found System** is a web-based platform that manages the entire lifecycle of lost and found items across the TTC (Toronto Transit Commission) transit network. It connects passengers who have lost items with transit operators who find items and the centralized Lost & Found office at Bay Station that stores, matches, verifies, and returns property to legitimate owners.

The system replaces manual phone-based inquiries and paper logbooks with a digital workflow that supports item reporting (lost and found), automated matching, ownership verification, status tracking, audit logging, and administrative oversight.

---

## 2. Context Diagram

The context diagram is provided as a PlantUML file: [`context-diagram.puml`](file:///c:/Users/Zain/Documents/code/courses/4312/rough_lab3/context-diagram.puml)

*(See the accompanying PlantUML file for a renderable version.)*

### Diagram Overview

```
                    ┌─────────────────┐
                    │   Passenger     │
                    │   (Claimant)    │
                    └────────┬────────┘
                             │ submits lost-item reports
                             │ browses found-item catalog
                             │ checks claim status
                             │ receives notifications
                             ▼
┌──────────────┐    ┌─────────────────────────────┐    ┌───────────────────┐
│   Transit    │───▶│  Public Transit Lost &       │◀──│  Transit          │
│   Operator   │    │  Found System                │   │  Management       │
│              │    │  ─────────────────────────── │   │                   │
│ logs found   │    │  • Item reporting            │   │ sets policies     │
│ items        │    │  • Matching engine           │   │ manages roles     │
│              │    │  • Verification workflows    │   │ views reports     │
│              │    │  • Status tracking           │   │ audits activity   │
└──────────────┘    │  • Storage management        │   └───────────────────┘
                    │  • Audit logging             │
                    │  • Admin dashboard           │
                    └──────────┬──────────────┬────┘
                               │              │
                    ┌──────────▼──────┐  ┌────▼────────────────┐
                    │ Lost & Found    │  │ External Systems     │
                    │ Staff           │  │ ──────────────────── │
                    │                 │  │ • Email/SMS Gateway  │
                    │ reviews matches │  │ • Delivery Partner   │
                    │ verifies claims │  │   API (optional)     │
                    │ manages storage │  │ • Authentication     │
                    │ approves return │  │   Provider           │
                    └─────────────────┘  └──────────────────────┘
```

---

## 3. External Actors / Stakeholders

| Actor | Type | Interaction with System |
|---|---|---|
| **Passenger (Claimant)** | Human / External user | Submits lost-item reports; browses the redacted found-item catalog; checks claim status using tracking codes; receives email/SMS notifications; presents proof of ownership at pickup. |
| **Transit Operator** | Human / Internal user | Logs found items through a streamlined intake form; provides item category, route/vehicle, time, and location; receives confirmation of submission. |
| **Lost & Found Staff** | Human / Internal user | Reviews system-flagged match candidates; verifies ownership claims; manages physical storage assignments; approves item return or final disposition; maintains the item audit trail. |
| **Transit Management** | Human / Internal user | Configures policies and staff access; reviews performance reports and system statistics; audits item handling activity. |

---

## 4. External Software / Hardware Systems

| External System | Type | Interaction |
|---|---|---|
| **Email / SMS Notification Gateway** | Software service | The system sends outgoing notifications (status updates, match alerts, pickup instructions) to passengers via email and SMS through an external gateway. |
| **Delivery Partner API** *(optional / future)* | Software service | If the system supports optional item delivery, it dispatches shipment requests to a third-party courier and receives delivery confirmation with chain-of-custody signatures. |
| **Authentication Provider** | Software service | Staff and management authenticate through an identity provider (e.g., TTC internal SSO or similar). Passengers may use email-based verification or tracking codes without full account creation. |
| **Web Browser** | Hardware/Software | All users interact with the system through a standard web browser on desktop or mobile devices. |

---

## 5. Major Information / Interaction Flows

| Flow | From → To | Description |
|---|---|---|
| **Lost-item report** | Passenger → System | Passenger submits item description, category, loss date/time, loss location, and contact method. System returns a unique tracking reference code. |
| **Found-item intake** | Transit Operator → System | Operator logs a found item with minimal required fields (date, route/station, category, brief description). |
| **Match notification** | System → Lost & Found Staff | System runs matching algorithms and flags potential matches for staff review. |
| **Status update** | System → Passenger | Automated notifications sent when report status changes (e.g., potential match found, ready for pickup, claim closed). |
| **Claim verification request** | Lost & Found Staff → Passenger (via System) | Staff requests additional proof-of-ownership details from the claimant. |
| **Item return approval** | Lost & Found Staff → System | Staff records verified return, triggering audit log entry and status update. |
| **Administrative reports** | System → Transit Management | Aggregated statistics, item aging reports, staff activity logs, and performance dashboards. |
| **Policy configuration** | Transit Management → System | Management sets retention periods, access roles, verification thresholds, and workflow rules. |

---

## 6. Explicit System-Boundary Decisions

| Decision | Inside Boundary | Outside Boundary |
|---|---|---|
| **Item reporting and tracking** | ✅ Digital reporting, status tracking, and matching | ❌ Physical retrieval and transport of items between vehicles and Bay Station |
| **Ownership verification** | ✅ Digital evidence collection and review workflow | ❌ In-person ID checking at the Bay Station counter (the system supports the process but does not replace the physical handover) |
| **Notifications** | ✅ Triggering and composing notification messages | ❌ Email/SMS delivery infrastructure (delegated to external gateway) |
| **Authentication** | ✅ Role-based access enforcement within the system | ❌ Identity provisioning and credential management (delegated to external auth provider) |
| **Physical storage** | ✅ Recording storage locations (bin/shelf/locker identifiers) | ❌ Managing the physical storage facility at Bay Station |
| **Data retention** | ✅ Automated anonymization/purging of PII per policy | ❌ Defining the legal retention period (set by MFIPPA and transit management policy) |

---

## 7. Assumptions About the Environment

| # | Assumption | Evidence Basis |
|---|---|---|
| A1 | All transit operators have access to a mobile or in-vehicle device capable of submitting a web form during end-of-shift or at depots. | **[Assumption]** — requires validation with TTC operations. |
| A2 | The TTC Lost Articles Office at Bay Station remains the single centralized collection point for found items. | **[Fact]** — per publicly available TTC lost-and-found information. |
| A3 | Passengers have access to a smartphone or computer with internet connectivity to submit reports and check status. | **[Assumption]** — reasonable given urban transit demographics but not universally true. |
| A4 | An email/SMS notification gateway is available or can be procured. | **[Assumption]** — standard infrastructure for web applications. |
| A5 | Staff at Bay Station have desktop computer access during work hours. | **[Assumption]** — standard for office-based transit staff. |
| A6 | Items found on vehicles take 24–48 hours to reach the central Bay Station office. | **[Fact]** — stated in TTC public communications about lost-and-found processing times. |

---

## 8. Dependencies on External Services or Policies

| Dependency | Description | Risk if Unavailable |
|---|---|---|
| **Email/SMS Gateway** | Required for passenger notifications. | Passengers would not receive automated status updates and would need to manually check status via the portal. |
| **Authentication Provider** | Required for staff/management login. | Staff cannot access internal functions; system is effectively offline for internal users. |
| **MFIPPA (Municipal Freedom of Information and Protection of Privacy Act)** | Governs the retention and handling of personal information collected by the system. | Non-compliance could result in legal liability for the transit agency. The system must implement data purging per the defined retention window. |
| **TTC Lost-and-Found Policies** | Defines holding periods, item categories, proof-of-ownership requirements, and disposition rules. | Without clear policy, the system cannot enforce consistent verification and disposal workflows. |
| **Delivery Partner API** *(optional)* | Enables optional item delivery to passengers. | Feature would be unavailable; passengers must pick up items at Bay Station in person. |
