| Lecture | 2: Stakeholders | and System | Context |
| ------- | --------------- | ---------- | ------- |
Who matters, what surrounds the system, and where the boundary belongs
EECS4312
YorkUniversity
|     | Monday, September | 14, 2026 |     |
| --- | ----------------- | -------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 1/23

| Learning | objectives |               |        |        |             |     |
| -------- | ---------- | ------------- | ------ | ------ | ----------- | --- |
| By the   | end of     | this lecture, | you    | should | be able to: |     |
| identify |            | stakeholders  | beyond | direct | end users;  |     |
distinguish stakeholder roles, interests, influence, and concerns;
| construct |     | and critique    |     | a stakeholder | map;     |     |
| --------- | --- | --------------- | --- | ------------- | -------- | --- |
| define    | a   | system boundary |     | and           | context; |     |
distinguish assumptions, constraints, business rules, and external interfaces;
| explain | how | context | errors | become | requirements | errors. |
| ------- | --- | ------- | ------ | ------ | ------------ | ------- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 2/23

| Running | case: Campus | Equipment | Loan System |
| ------- | ------------ | --------- | ----------- |
York University wants to improve borrowing of cameras, microphones, laptops, and specialized
| lab equipment. | Initial request: |     |     |
| -------------- | ---------------- | --- | --- |
“Build a web application so students can reserve equipment online.”
Question: who should be involved before we decide what this means?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 3/23

| Stakeholder: |     | a practical |     | definition |     |     |
| ------------ | --- | ----------- | --- | ---------- | --- | --- |
A stakeholder is a person, group, organization, external system, or governing authority that:
| is affected |        | by the system; |        |          |     |     |
| ----------- | ------ | -------------- | ------ | -------- | --- | --- |
| can         | affect | the system     | or its | success; |     |     |
supplies requirements, constraints, resources, or information;
| operates, | supports,  |            | regulates,       | purchases, | or maintains | it; |
| --------- | ---------- | ---------- | ---------------- | ---------- | ------------ | --- |
| may       | experience | benefits,  | costs,           | risks,     | or harms.    |     |
| Common    | mistake    |            |                  |            |              |     |
| “Users”   | are only   | one subset | of stakeholders. |            |              |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 4/23

| Stakeholder |                | categories  |            | for the running |          | case          |                |
| ----------- | -------------- | ----------- | ---------- | --------------- | -------- | ------------- | -------------- |
| Direct      | / operational  |             |            |                 | Indirect | / governing   |                |
|             | students       | borrowing   | equipment  |                 |          | department    | administrators |
|             | equipment-desk |             | staff      |                 |          | IT/security   |                |
|             | instructors    | approving   | restricted | items           |          | accessibility | office         |
|             | technicians    | maintaining |            | equipment       |          | privacy/legal | staff          |
finance/procurement
|     |     |     |     |     |     | external | identity/payment systems |
| --- | --- | --- | --- | --- | --- | -------- | ------------------------ |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 5/23

Stakeholder identification techniques
Follow the workflow: who acts before, during, and after the system interaction?
Follow the data: who creates, owns, verifies, sees, retains, or deletes it?
Follow the money/resources: who pays, budgets, approves, or bears losses?
Follow the exceptions: who handles failures, disputes, emergencies, and appeals?
Follow governance: who sets policy, law, standards, or contractual constraints?
Follow lifecycle: who installs, operates, maintains, supports, audits, and retires the
system?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 6/23

| Stakeholder        | analysis           | needs more     | than a name |
| ------------------ | ------------------ | -------------- | ----------- |
| For each important | stakeholder,       | record:        |             |
| role and           | relationship       | to the system; |             |
| goals and          | desired outcomes;  |                |             |
| concerns           | and potential      | harms;         |             |
| influence          | or decision        | power;         |             |
| information        | they possess;      |                |             |
| dependencies       | on other           | stakeholders;  |             |
| likely conflicts;  |                    |                |             |
| evidence           | versus assumptions | about them.    |             |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 7/23

Power-interest matrix
Influence / power
| Privacy office  | Equipment      | desk |
| --------------- | -------------- | ---- |
| Keep satisfied  | Engage closely |      |
| Payment Systems | Students       |      |
| Monitor         | Keep informed  |      |
Interest
Placementishypothetical: thepointistodiscussengagementstrategy,nottopretendthechartisobjectivelymeasured.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 8/23

| Stakeholder      | conflicts   | are normal |
| ---------------- | ----------- | ---------- |
| Example tensions | in the loan | system:    |
Students want easy access; staff want strict eligibility and accountability.
Instructors want priority for course projects; students want first-come-first-served fairness.
Security wants stronger authentication; accessibility may be harmed by some mechanisms.
Technicians want maintenance blocks; borrowers want maximum availability.
Administration wants utilization data; privacy stakeholders want data minimization.
A conflict is not a failure of RE. Discovering it early is part of successful RE.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 9/23

| Context | answers: | what surrounds | the system? |
| ------- | -------- | -------------- | ----------- |
A system context identifies relevant elements outside the proposed software that interact with
| it or constrain | it. Typical        | elements:    |     |
| --------------- | ------------------ | ------------ | --- |
| human           | actors;            |              |     |
| external        | software/services; |              |     |
| devices         | and physical       | environment; |     |
| organizational  | processes;         |              |     |
| policies        | and regulations;   |              |     |
| data            | sources and        | sinks.       |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 10/23

| Context | diagram: | example |     |     |     |
| ------- | -------- | ------- | --- | --- | --- |
Inventory /
|     | Desk | Staff |           |      | Asset Registry |
| --- | ---- | ----- | --------- | ---- | -------------- |
|     |      |       | Equipment | Loan | York Identity  |
Student
|     |            |     | System |     | Service      |
| --- | ---------- | --- | ------ | --- | ------------ |
|     | Instructor |     |        |     | Notification |
Service
The diagram shows boundaries and interactions, not internal architecture.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 11/23

| The system           | boundary       | is an         | engineering | decision |
| -------------------- | -------------- | ------------- | ----------- | -------- |
| What is inside       | the system?    |               |             |          |
| reservation          | management?    |               |             |          |
| identity             | verification?  |               |             |          |
| inventory            | ownership      | records?      |             |          |
| payment              | of replacement | fees?         |             |          |
| email/SMS            | delivery?      |               |             |          |
| A different boundary | changes:       |               |             |          |
| what requirements    | belong         | to your       | system;     |          |
| which interfaces     | become         | dependencies; |             |          |
| which assumptions    | must           | be trusted;   |             |          |
| what risks           | are under      | your control. |             |          |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 12/23

Boundary mistakes
Too narrow Important work is pushed outside the model and hidden as “someone else’s
problem.”
Too broad The project claims responsibility for organizations, services, or policies it cannot
control.
Solution-shaped The boundary mirrors a preferred architecture instead of the problem context.
Actor confusion External human roles or services are modeled as internal components.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 13/23

| Assumption, | constraint, | or requirement? |
| ----------- | ----------- | --------------- |
Assumption Aconditionbelievedtrueforplanningoranalysis, butnotguaranteed
|     | by the system. |     |
| --- | -------------- | --- |
Constraint A restriction on acceptable solutions or operation, often imposed ex-
ternally.
Requirement A needed capability, quality, or outcome the system must satisfy.
Business rule A rule governing the domain or organization, which may generate
requirements.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 14/23

| Examples: | classify | these |     |     |
| --------- | -------- | ----- | --- | --- |
1 “York’s identity service will be available whenever reservations are made.”
“Only currently enrolled students may borrow category-A devices.”
2
| “The system | shall | prevent double-booking | of the same | asset.” |
| ----------- | ----- | ---------------------- | ----------- | ------- |
3
4 “The application must use the university-supported SSO service.”
| Possible classification: |     |     |     |     |
| ------------------------ | --- | --- | --- | --- |
1 assumption/dependency;
| business | rule (which | must be operationalized); |     |     |
| -------- | ----------- | ------------------------- | --- | --- |
2
| 3 functional          | requirement; |             |     |     |
| --------------------- | ------------ | ----------- | --- | --- |
| 4 solution/technology |              | constraint. |     |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 15/23

| Assumptions      | are dangerous | when | invisible |
| ---------------- | ------------- | ---- | --------- |
| Suppose the team | assumes:      |      |           |
“Every borrower has a smartphone and receives push notifications.”
If
| never documented,      | this assumption | may silently | shape: |
| ---------------------- | --------------- | ------------ | ------ |
| reminder requirements; |                 |              |        |
| late-return            | procedures;     |              |        |
accessibility;
| emergency | contact workflows; |     |     |
| --------- | ------------------ | --- | --- |
UI choices.
Visible assumptions can be challenged, validated, or turned into explicit constraints.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 16/23

| Domain | language |     | and | the | glossary |
| ------ | -------- | --- | --- | --- | -------- |
A requirements specification often fails because people use the same word differently. For the
| equipment   | case, | define         | terms such         | as: |        |
| ----------- | ----- | -------------- | ------------------ | --- | ------ |
| asset       | vs.   | equipment      | type;              |     |        |
| reservation |       | vs. checkout;  |                    |     |        |
| borrower    |       | vs. requester; |                    |     |        |
| overdue     | vs.   | late;          |                    |     |        |
| maintenance |       | hold           | vs. administrative |     | block. |
Rule
If a term matters to a requirement, define it before relying on it.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 17/23

| Evidence | versus | assumption |     |     | about | stakeholders |
| -------- | ------ | ---------- | --- | --- | ----- | ------------ |
If no real stakeholder interview is available, you may still make a useful provisional model – but
| label its basis. |     |     |     |     |     |     |
| ---------------- | --- | --- | --- | --- | --- | --- |
Evidence: official policy, existing system documentation, observed workflow
| Analogy:         |     | behavior inferred | from            | a      | comparable  | system |
| ---------------- | --- | ----------------- | --------------- | ------ | ----------- | ------ |
| Simulation:      |     | role played       | in a            | course | exercise    |        |
| Assumption:      |     | plausible         | but currently   |        | unsupported |        |
| This distinction |     | is central        | to the EECS4312 |        | project.    |        |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 18/23

| Activity: | expand | the | stakeholder | map |
| --------- | ------ | --- | ----------- | --- |
For the Campus Equipment Loan System, add at least five stakeholders not already shown.
| For each, | state:               |     |                      |     |
| --------- | -------------------- | --- | -------------------- | --- |
| 1 one     | goal or interest;    |     |                      |     |
| 2 one     | concern;             |     |                      |     |
| one       | piece of information |     | they may contribute; |     |
3
| 4 one | possible conflict | with | another stakeholder. |     |
| ----- | ----------------- | ---- | -------------------- | --- |
Then ask: which stakeholder would be most damaging to omit from elicitation, and why?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 19/23

| From stakeholder/context | analysis | to requirements |
| ------------------------ | -------- | --------------- |
Stakeholders Goals / concerns Context / rules Candidate requirements
A requirement without a credible source, goal, constraint, or rationale deserves extra scrutiny.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 20/23

| What Sprint       | 0 expects         | from this | material |
| ----------------- | ----------------- | --------- | -------- |
| Your team will    | need:             |           |          |
| problem statement | and initial       | scope;    |          |
| stakeholder       | analysis/map;     |           |          |
| context diagram   | and system        | boundary; |          |
| assumptions       | and dependencies; |           |          |
glossary;
candidate requirements linked to evidence, analogy, simulation, or assumption.
Thursday’s lab is a project-approval clinic: arrive with a project idea concrete enough to
| discuss these artifacts. |     |     |     |
| ------------------------ | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 21/23

Key takeaways
| Stakeholders | are broader | than end users. |
| ------------ | ----------- | --------------- |
Stakeholder analysis should capture goals, concerns, influence, knowledge, and conflicts.
Context and system boundary determine what the project is responsible for.
Assumptions, constraints, business rules, and requirements are different things.
Hidden assumptions and omitted stakeholders are major sources of downstream
| requirements | defects. |     |
| ------------ | -------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 22/23

Suggested reading
Pohl, Requirements Engineering, 2nd ed.: sections on system context and stakeholders.
Wiegers & Beatty, Software Requirements, 3rd ed.: vision/scope and stakeholder/user
classes.
Review your Sprint 0 handout before Thursday’s project-approval lab.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 23/23