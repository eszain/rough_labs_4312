https://www.figma.com/resource-library/context-diagram/
StakeHolders 1 (Muhammad)
Name: Passenger who lost an Item
Interest: Report his lost item and recover lost item quickly and smoothly without spending
hours calling customer service or traveling to Bay Station just to inquire.
Goals: Report lost items easily, receive status updates, know whether the item is found,
prove ownership, and reclaim item before retention limits expire.
Responsibilities: Provide honest, detailed identifying marks (not generic guesses); hold
onto their claim tracking code; present government photo ID and unlock/verify the item upon
pickup.
Service Needed: A public portal to report missing property, a masked search/inquiry tool,
automated email/SMS status tracking, and clear pickup instructions for Bay Station.
Risks:
● Privacy: Entering personal identity info into a web form that could be mishandled.
● Fraud: Someone else spotting a listed item and fraudulently claiming it first.
● Premature loss of hope: Searching an hour after losing something, finding nothing,
and assuming it is gone forever because physical transit logistics take 24–48 hours.
Influence: Low formal decision power over how the TTC builds the system, but high
aggregate influence—if passengers find the site confusing or untrustworthy, they will bypass
it and overwhelm the phone lines anyway.
Conflicts with other stakeholders:
● With Transit Operators: Passengers expect immediate logging the minute an
operator picks up an item, but drivers must focus on transit schedules and safety.
● With Lost & Found Staff: Claimants get annoyed by the strict proof demanded before
high-value items are handed over.
How team’s knowledge about this stakeholder was obtained:
● [Fact]: The TTC Lost Articles Office counter is at Bay Subway Station, with phone
inquiry lines open only Monday to Friday, 12:00 PM to 5:00 PM.
● [Analogy]: Passenger behaviors on transit systems like Transport for London and
airline baggage portals show that lack of automated case tracking causes high
drop-off and repeated calls to support.
● [Assumption]: Most riders will search for or report their item from a smartphone
within 6 hours of realizing it was left behind.
Stakeholder 2 – Transit Operator
● Name / Role:
Transit Operator / Frontline Transit Employee.

● Interest: Wants lost items found on transit vehicles or handed in by passengers to
enter the lost-and-found process correctly. Operators would prefer a quick process
that does not significantly interrupt their normal duties.
● Goals: Report found items, Provide useful details such as item type, location, route,
vehicle, and approximate time found and Ensure the physical item reaches the
appropriate lost-and-found location.
● Responsibilities: Receive or identify found items, Submit relevant information about
the item through the proposed system, Transfer or store the physical item according
to transit procedures. Existing evidence suggests Public transit agencies use
centralized processes where found items are eventually recorded and stored.
● Services Needed:
○ A simple reporting interface.
○ Fields for item description, category, time, route, vehicle, and location.
○ Confirmation that the report was submitted.
○ Instructions for handling or transferring the physical item.
● Risks / Concerns:
○ Reporting could interfere with active transit duties.
○ Incomplete information could reduce matching accuracy.
○ Valuable or personal items could be mishandled.
● Influence: Medium influence, because operator reports may affect the quality of
information available to lost-and-found staff.
● Conflicts with Other Stakeholders:
○ Lost-and-found staff may want detailed reports, while operators may prefer
shorter forms.
○ Passengers may expect immediate help, while operators may only be able to
report or transfer the item.
● How Knowledge Was Obtained: Public transit lost-and-found procedures were
reviewed, Existing systems were used as analogies. Operator goals, concerns,
influence, and conflicts are primarily team assumptions requiring future validation.
The main assumptions are that transit operators value fast reporting, minimal
disruption, clear instructions, and simple forms.
StakeHolders 3 (zain)
Name: Lost and Found Staff (Central Inventory / Claims Officer)
Interest: Ensuring the centralized lost-and-found repository operates systematically,
incoming item records are kept up-to-date, and genuine owners are accurately matched
while eliminating fraud and administrative backlogs.
Goals: Minimize time spent manually cross-referencing lost reports against physical
inventory, verify ownership claims with high accuracy to prevent releasing property to
fraudulent claimants, and streamline outbound dispatching for owner pickup or delivery.
Responsibilities: Cataloging and categorizing physical items received from transit vehicles
and depots, reviewing and evaluating match candidates flagged by the system, validating

proof-of-ownership documentation, managing secure storage, and approving items for
handoff or third-party delivery.
Service Needed: Automated matching algorithms that connect item attributes, a streamlined
verification interface showing claimant evidence against item logs, an audit trail for item
custody changes, and integration with the delivery partner API for shipment dispatch.
Risks: Releasing an item to the wrong individual due to vague descriptions; experiencing
inventory overflow caused by poor data entry from depot personnel; facing reputational or
legal fallout from lost, damaged, or mishandled high-value belongings.
Influence: High operational decision power regarding system usability, verification criteria,
and claim approval or rejection workflows. Can reject system features that add unnecessary
friction to daily inventory reconciliation.
Conflicts with other stakeholders:
● With Passengers: Staff require stringent proof of ownership and detailed
descriptions, which frustrated passengers may perceive as excessive delay or
bureaucratic gatekeeping.
● With Transit Employees / Drivers: Staff need granular, structured item intake details,
whereas drivers want ultra-quick, minimal logging that does not cut into turnarounds
or breaks.
● With Delivery Partners: Staff require signed chain-of-custody confirmation and
prompt pickup, while courier drivers prioritize strict delivery timetables and minimum
wait times at facility loading areas.
How team’s knowledge about this stakeholder was obtained:
● Facts supported by public/existing evidence: Review of public intake and claim
guidelines from metropolitan transit systems (e.g., STM Montreal, TTC Toronto,
Transport for London), which clearly state claim holding periods, proof-of-identity
mandates, and item intake categories.
● Analogies to existing systems: Workflows modeled on airport lost-and-found systems
(such as SITA WorldTracer) and parcel return centers, where multi-attribute matching
and chain-of-custody logging are standard operating procedure.
● Assumptions created by the team: We assume staff are willing to adopt an
automated match-scoring interface rather than sticking to legacy physical logbooks,
and that they possess standard digital literacy to review uploaded claimant images
and dispatch delivery requests directly through a web portal.

Stakeholder 4 – Transit Management
● Name / Role:
Transit Management / Transit Agency Administration.
● Interest: Interested in ensuring the lost-and-found process is efficient, consistent,
secure, and aligned with agency procedures. Management would want minimal
manual work while improving the quality of lost-item records.
● Goals:
○ Ensure lost and found items are handled using a standardized process.
○ Improve tracking and accountability for reported items.
○ Reduce delays, missing information, and unnecessary administrative effort.
○ Support a reliable service for passengers.
● Responsibilities:
○ Establish policies and procedures for handling lost property.
○ Define staff responsibilities and access permissions.
○ Oversee compliance with privacy, security, and operational requirements.
○ Approve or support changes to the lost-and-found process.
● Services Needed:
○ Access to reports and system statistics.
○ Ability to manage staff roles or permissions.
○ Visibility into item status and overall lost-and-found activity.
○ Tools for reviewing system performance and identifying recurring problems.
● Risks / Concerns:
○ Data breaches or improper access to personal information.
○ Inaccurate records or poor staff adoption.
○ Increased workload if the system is difficult to use.
○ System failures disrupting lost-and-found operations..
● Influence: High influence, because management would likely approve policies,
workflows, access rules, and deployment decisions.
● Conflicts with Other Stakeholders:
○ Staff may prefer simpler workflows, while management may require more
documentation.
○ Passengers may want more transparency or faster service, while
management must balance cost, privacy, and operational constraints.
● How Knowledge Was Obtained:
○ Public/existing evidence: The team reviewed publicly available transit
agency information about lost-and-found procedures, staff responsibilities,
privacy, and operational policies.
○ Analogy to existing systems: Existing transit lost-and-found services were
used to understand the likely role of management in overseeing workflows,
policies, and staff access.
○ Assumptions:The team assumes transit management prioritizes operational
efficiency, standardized procedures, privacy, accountability, accurate record
keeping, system reliability, and reporting tools that support oversight of
lost-and-found activities
:

5.6 context.md
Define the system context and boundary.
Include: •
a context diagram; •
the system under consideration; •
The system is the Public Transit Lost and Found System, which manages information about
lost and found items as well as report
external actors/stakeholders; •
external software/hardware systems; •
major information or interaction flows; •
explicit system-boundary decisions; •
assumptions about the environment; •
dependencies on external services or policies.
Candidate Requirements
ID Short Current Type Stakeholder Rationale Priority
Title Statement / Source
R1 Centraliz The system Business Transit Prevents information Must
ed shall maintain a Require Management from being distributed
Lost-Pro single ment , across disconnected
perty searchable Lost-and-Fou records.
Records record of nd Staff
lost-item reports
and found-item
records handled
through the
system.

| R2  Item  | The system  | Business  | Transit  | Supports  | Must  |
| --------- | ----------- | --------- | -------- | --------- | ----- |
Traceabil shall maintain  Require Management  accountability and
| ity  | the current  | ment  |     | operational tracking.  |     |
| ---- | ------------ | ----- | --- | ---------------------- | --- |
processing state
of each
found-item
record from
intake until
return, disposal,
or other final
disposition.
R3  Support  The system  Stakehol Passenger,  The primary business  Must
| Item    | shall support      | der     | Lost-and-Fou | objective is        |     |
| ------- | ------------------ | ------- | ------------ | ------------------- | --- |
| Recover | comparison of      | Require | nd Staff     | reconnecting lost   |     |
| y       | passenger          | ment    |              | property with       |     |
|         | lost-item reports  |         |              | legitimate owners.  |     |
with records of
items received
by the transit
agency.
R4  Prevent  The system  Stakehol Passenger,  Reduces the risk of  Must
| Unauthor | shall support   | der     | Management   | property being         |     |
| -------- | --------------- | ------- | ------------ | ---------------------- | --- |
| ized     | ownership       | Require | ,            | released to the wrong  |     |
| Release  | verification    | ment    | Lost-and-Fou | person.                |     |
|          | before a found  |         | nd Staff     |                        |     |
item is recorded
as returned to a
claimant.
R5  Submit  The system  Function Passenger  Provides the starting  Must
| Lost-Ite  | shall allow a  | al      |     | point for a passenger  |     |
| --------- | -------------- | ------- | --- | ---------------------- | --- |
| m Report  | passenger to   | Require |     | seeking an item.       |     |
|           | submit a       | ment    |     |                        |     |
lost-item report.

R6  Record  A lost-item  Function Passenger,  These attributes  Must
| Lost-Ite | report shall    | al      | Lost-and-Fou | provide basic          |     |
| -------- | --------------- | ------- | ------------ | ---------------------- | --- |
| m        | record an item  | Require | nd Staff     | information needed to  |     |
| Details  | category,       | ment    |              | investigate a loss.    |     |
description,
approximate
loss date,
approximate
loss location,
and passenger
contact method.
R7  Optional  The system  Function Passenger  Passengers may  Should
| Transit  | shall allow a      | al      |     | know some transit       |     |
| -------- | ------------------ | ------- | --- | ----------------------- | --- |
| Details  | passenger to       | Require |     | details but should not  |     |
|          | provide route,     | ment    |     | be prevented from       |     |
|          | vehicle, station,  |         |     | reporting when they     |     |
|          | direction of       |         |     | do not.                 |     |
travel, and
approximate
time when
known.
R8  Final  The system  Function Lost-and-Fou Items may eventually  Must
| Item  | shall allow  | al  | nd Staff,  | leave the active  |     |
| ----- | ------------ | --- | ---------- | ----------------- | --- |
Dispositi authorized staff  Require Management  lost-and-found
| on  | to record the      | ment  |     | process without being            |     |
| --- | ------------------ | ----- | --- | -------------------------------- | --- |
|     | final disposition  |       |     | claimed.                         |     |
of an unclaimed
item.
R9  Claim  The system  Function Passenger   Enables passengers  Must
| Tracking     | shall generate   | al      |     | to look up and      |     |
| ------------ | ---------------- | ------- | --- | ------------------- | --- |
| Identifier   | and provide a    | Require |     | reference their     |     |
|              | unique tracking  | ment    |     | specific inquiry    |     |
|              | reference code   |         |     | without submitting  |     |
|              | to a passenger   |         |     | duplicates.         |     |
upon successful
submission of a
lost-item report.

R10  Check  The system  Function Passenger   Reduces repetitive  Must
| Report   | shall allow a  | al      | phone calls and       |
| -------- | -------------- | ------- | --------------------- |
| Status   | passenger to   | Require | counter visits by     |
|          | look up the    | ment    | providing self-serve  |
|          | current        |         | progress updates.     |
processing state
of their lost-item
report using
their tracking
reference code
and contact
information.
R11   Rapid  The system  Function Transit  Ensures shift drivers  Should
Operator  shall provide a  al  Operator   and station collectors
| Intake   | streamlined  | Require | can hand off property  |
| -------- | ------------ | ------- | ---------------------- |
|          | intake form  | ment    | quickly without        |
|          | allowing     |         | delaying schedules.    |
frontline staff to
log a found item
using minimal
required fields
(date,
route/station,
broad category).
R12  Redacte The system  Function Passenger,  Ensures shift drivers  Should
d Public  shall display a  al  Management   and station collectors
| Search   | public catalog of  | Require | can hand off property  |
| -------- | ------------------ | ------- | ---------------------- |
|          | recently found     | ment    | quickly without        |
|          | items while        |         | delaying schedules.    |
automatically
redacting
sensitive
identifiers (e.g.,
serial numbers,
full names,
specific bag
contents).

R13  Physical  The system  Function Lost-and-Fou Prevents items from  Must
| Storage  | shall record the   | al      | nd Staff   | being misplaced         |
| -------- | ------------------ | ------- | ---------- | ----------------------- |
| Assignm  | physical storage   | Require |            | inside the holding      |
| ent      | location (e.g.,    | ment    |            | facility and speeds up  |
|          | bin, shelf, or     |         |            | retrieval during        |
|          | locker identifier  |         |            | customer pickup.        |
at Bay Station)
for each
cataloged found
item.
R14  Intake  The system  Function Passenger,  Sets realistic  Should
| Latency  | shall display a  | al          | Management   | expectations and     |
| -------- | ---------------- | ----------- | ------------ | -------------------- |
| Notice   | clear notice     | Require     |              | prevents false       |
|          | informing        | ment /      |              | assumptions that an  |
|          | passengers that  | Usability   |              | unlisted item was    |
|          | items turned in  |             |              | permanently lost.    |
on vehicles may
take up to
24–48 hours to
be processed at
the central
office.
R15  Staff  The system  Function Management   Maintains an  Must
| Audit     | shall record  | al      |     | immutable chain of     |
| --------- | ------------- | ------- | --- | ---------------------- |
| Logging   | which staff   | Require |     | custody and            |
|           | member        | ment    |     | accountability for     |
|           | created,      |         |     | internal operations.   |
updated, or
marked an item
as returned or
disposed of,
along with a
timestamp.
R16   Claim  The system  Non-Fun Management Ensures compliance  Must
| Data      | shall           | ctional  | , Passenger   | with Ontario          |
| --------- | --------------- | -------- | ------------- | --------------------- |
| Retentio  | automatically   | Require  |               | municipal privacy     |
| n &       | anonymize or    | ment /   |               | legislation (MFIPPA)  |
| Purging   | purge personal  | Complia  |               | by not holding PII    |
|           | contact and     | nce      |               | indefinitely.         |
identity
information from
resolved reports
after a defined
retention

window (e.g., 90
days).