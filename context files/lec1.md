| Lecture  | 1: Introduction    | to Requirements |         | Engineering |
| -------- | ------------------ | --------------- | ------- | ----------- |
| Purpose, | software-intensive | systems,        | and the | role of RE  |
EECS4312
YorkUniversity
|     | Wednesday, | September | 9, 2026 |     |
| --- | ---------- | --------- | ------- | --- |
ConceptualfoundationadaptedfromSteveEasterbrook’sCSC340introductionslides(UniversityofToronto,2004–05),
usedwithattributionunderthesource’sstatedCreativeCommonsnon-commercialterms.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 1/27

What we will do today
1 Locate Requirements Engineering (RE) within software engineering.
2 Explain why useful software must be understood in its human and organizational context.
3 Introduce fitness for purpose as a requirements-centered view of quality.
4 Examine why many software problems are difficult or “wicked.”
5 Define RE as a bridge between real-world needs and software possibilities.
6 Preview the analyst’s core questions and the semester project.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 2/27

| Course  | positioning: |     | this | is not | “more UML” |
| ------- | ------------ | --- | ---- | ------ | ---------- |
| Central | question     |     |      |        |            |
How do we decide what problem is worth solving, for whom, under what conditions, and how
| we will     | know that   | a proposed | system | is  | fit for its purpose? |
| ----------- | ----------- | ---------- | ------ | --- | -------------------- |
| This course | emphasizes: |            |        |     |                      |
incomplete, ambiguous, conflicting, and changing information;
| stakeholders, |     | evidence, | goals, | assumptions, | and constraints; |
| ------------- | --- | --------- | ------ | ------------ | ---------------- |
specification, modeling, validation, traceability, and change;
engineering judgment rather than mechanical template filling.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 3/27

| How the    | course      | is organized |                  |             |
| ---------- | ----------- | ------------ | ---------------- | ----------- |
| Individual | work        |              | Team project     |             |
| Four       | individual  | assignments  | Teams of         | 3–4         |
| Midterm    | in          | lecture      | GitHub Classroom |             |
| Final      | examination |              | Requirements     | Sprints 0–4 |
Labs include individual participation Small validation prototype
|            |     |     | Recorded | final presentation |
| ---------- | --- | --- | -------- | ------------------ |
| Tomorrow’s | lab |     |          |                    |
Lab 1 is primarily team formation and a team-expectations agreement. Participation is the
| goal, not | polished | documentation. |     |     |
| --------- | -------- | -------------- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 4/27

| Opening | question: | when | does software   | become | useful?            |        |
| ------- | --------- | ---- | --------------- | ------ | ------------------ | ------ |
|         | Software  |      | Computer system |        | Software-intensive | system |
instructions / computations software + hardware technology + human activity
A program can execute perfectly and still be useless if it does not support the activity for
| which people | need it. |     |     |     |     |     |
| ------------ | -------- | --- | --- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 5/27

Software-intensive systems
A software-intensive system is not just code running on hardware. It includes the activities,
people, policies, organizations, and other systems with which the software interacts.
Example: university course registration
The software interacts with students, instructors, departments, prerequisites, degree rules, time
slots, room capacities, waitlists, financial holds, accessibility needs, and institutional policy.
Changing the software can change human behavior; changing policy or human behavior can
invalidate requirements.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 6/27

| A useful | mental | model              |         |           |             |                |       |
| -------- | ------ | ------------------ | ------- | --------- | ----------- | -------------- | ----- |
|          |        | Application        | /       |           | Machine     | /              | so-   |
|          |        | problem            | domain  | RE bridge | lution      | domain         |       |
|          |        | people, work,      | policy, |           | software,   | interfaces,    | data, |
|          |        | goals, constraints |         |           | algorithms, | infrastructure |       |
Problem-domain observations and constraints shape requirements.
Software capabilities create opportunities, but also introduce new assumptions and effects.
RE spends substantial effort on the left-hand side before committing to the right-hand side.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 7/27

| Quality               | as fitness | for purpose |     |
| --------------------- | ---------- | ----------- | --- |
| Requirements-centered |            | view        |     |
We cannot judge whether a system is “good” without knowing what purpose it is supposed to
| serve and | in what context.    |                  |                    |
| --------- | ------------------- | ---------------- | ------------------ |
| A         | technically correct | system may solve | the wrong problem. |
A fast system may still be unacceptable if it violates privacy.
A secure system may still fail if its workflow prevents staff from doing urgent work.
A feature may be valuable for one stakeholder and harmful to another.
Therefore: requirements are not merely a feature list; they are an argument about purpose
| and acceptable | outcomes. |     |     |
| -------------- | --------- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 8/27

| Mini-case:   | “Improve | the advising | system” |
| ------------ | -------- | ------------ | ------- |
| A department | says:    |              |         |
“We need a new AI-enabled advising portal because students complain that advising
| is too slow.”     |                 |      |                |
| ----------------- | --------------- | ---- | -------------- |
| Before discussing | implementation, | what | would you ask? |
What does “too slow” mean? Waiting time? Resolution time? Response quality?
Who experiences the problem? All students? Particular programs?
| What is | the current process? |     |     |
| ------- | -------------------- | --- | --- |
Is the cause insufficient staffing, poor information, policy complexity, or software?
| What outcomes | would | count as improvement? |     |
| ------------- | ----- | --------------------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 9/27

| The purpose        |     | is usually |       | complex   |             |
| ------------------ | --- | ---------- | ----- | --------- | ----------- |
| Software-supported |     | activities | often | involve:  |             |
| many stakeholder   |     | groups     | with  | different | objectives; |
rules that are incomplete, informal, or interpreted differently;
| exceptions   | that           | are rare   | but     | important; |             |
| ------------ | -------------- | ---------- | ------- | ---------- | ----------- |
| changing     | organizational |            | and     | regulatory | conditions; |
| dependencies |                | on systems | we      | do not     | control;    |
| values       | that cannot    | be         | reduced | to one     | number.     |
Consequence
“What should the system do?” rarely has one obvious, objective answer.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 10/27

| Why requirements |            | problems     |               | can be       | “wicked” |
| ---------------- | ---------- | ------------ | ------------- | ------------ | -------- |
| A wicked problem |            | may have:    |               |              |          |
| no single        | definitive | formulation; |               |              |          |
| no obvious       | stopping   | point        | for analysis; |              |          |
| multiple         | plausible  | solutions    | judged        | by competing | values;  |
important political, ethical, organizational, or professional dimensions;
new understanding that appears only after proposed solutions are explored.
RE implication
Elicitation is not simply “asking users what they want.” The analyst and stakeholders learn
| about the problem |     | while exploring | it. |     |     |
| ----------------- | --- | --------------- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 11/27

| Four ways   | to cope         | with complexity |                       |
| ----------- | --------------- | --------------- | --------------------- |
| Abstraction | Ignore selected | detail to       | see a larger pattern. |
Decomposition Break a problem into pieces that can be studied separately.
Projection Examine the same situation from different viewpoints or concerns.
Modularization Choose structures that localize likely change.
Each technique is useful, but each also hides something. A model is a deliberate simplification,
| not “the truth.” |     |     |     |
| ---------------- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 12/27

| Hard-system | and soft-system | perspectives |             |                       |     |
| ----------- | --------------- | ------------ | ----------- | --------------------- | --- |
| Hard-system | emphasis        |              | Soft-system | emphasis              |     |
| problem     | can be bounded; |              | problem     | is socially situated; |     |
requirements can be made precise; stakeholders have different goals and
| specification | can be verified; |              | values;       |              |       |
| ------------- | ---------------- | ------------ | ------------- | ------------ | ----- |
|               |                  |              | understanding | changes over | time; |
| solution      | correctness can  | be evaluated |               |              |       |
against the specification. participation and learning are essential.
| Most real projects | need elements | of both perspectives. |     |     |     |
| ------------------ | ------------- | --------------------- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 13/27

| When          | is the | “soft”        | side         | especially | important? |
| ------------- | ------ | ------------- | ------------ | ---------- | ---------- |
| Information   |        | systems       | that reshape | work       | practices  |
| Platforms     |        | with multiple | stakeholder  |            | groups     |
| Public-sector |        | or regulated  | systems      |            |            |
Systems involving privacy, accessibility, fairness, or safety
| Products |     | whose value | depends | on changing | user behavior |
| -------- | --- | ----------- | ------- | ----------- | ------------- |
Even technically constrained systems still have human interfaces and operational contexts.
The balance changes, but context never disappears completely.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 14/27

| A working          | definition   | of Requirements | Engineering |
| ------------------ | ------------ | --------------- | ----------- |
| Working definition | for EECS4312 |                 |             |
Requirements Engineering is the set of activities used to identify, analyze, communicate,
document, validate, manage, and evolve the purposes and requirements of a software-intensive
| system in its | context of use. |     |     |
| ------------- | --------------- | --- | --- |
RE connects:
real-world needs and constraints ←→ software capabilities and opportunities
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 15/27

| RE is        | not a one-time      |            | phase         |         |         |               |
| ------------ | ------------------- | ---------- | ------------- | ------- | ------- | ------------- |
| A simplistic | lifecycle           | picture    | is:           |         |         |               |
|              |                     |            | requirements  | →       | design  | → code → test |
| But real     | projects repeatedly |            | discover      | that:   |         |               |
| prototypes   | reveal              | missing    | requirements; |         |         |               |
| design       | uncovers            | infeasible | assumptions;  |         |         |               |
| testing      | exposes             | ambiguity; |               |         |         |               |
| regulation   | or policy           | changes;   |               |         |         |               |
| stakeholder  | priorities          | shift;     |               |         |         |               |
| deployed     | behavior            | creates    | new needs.    |         |         |               |
| RE continues | as the              | system     | and its       | context | evolve. |               |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 16/27

| What | is a requirement? | First | approximation |
| ---- | ----------------- | ----- | ------------- |
A requirement describes a needed capability, quality, constraint, or outcome that matters to
some stakeholder or governing context. Later we will distinguish:
| business        | requirements; |               |        |
| --------------- | ------------- | ------------- | ------ |
| stakeholder     | requirements; |               |        |
| system/software | functional    | requirements; |        |
| quality         | requirements; |               |        |
| constraints,    | assumptions,  | and business  | rules. |
Important
A sentence written with the word “shall” is not automatically a good requirement.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 17/27

| Requirement | or premature | design? |     |
| ----------- | ------------ | ------- | --- |
Consider:
| “The system | shall store each | student record | in MongoDB.” |
| ----------- | ---------------- | -------------- | ------------ |
Possible interpretations:
legitimate constraint: infrastructure policy mandates MongoDB;
| design decision: | team simply | prefers MongoDB; |     |
| ---------------- | ----------- | ---------------- | --- |
proxy for a real need: flexible schema, availability, scale, or cost.
Analyst question: what underlying need or constraint justifies this statement?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 18/27

| The requirements |     | analyst | as an agent | of change |
| ---------------- | --- | ------- | ----------- | --------- |
The starting point is usually not “a set of requirements.” It is some perception of a problem,
opportunity, risk, or desired improvement. An analyst helps transform that initial concern into
| a defensible | understanding | of:         |             |     |
| ------------ | ------------- | ----------- | ----------- | --- |
| what         | needs         | to change;  |             |     |
| who          | is affected;  |             |             |     |
| why          | the change    | matters;    |             |     |
| what         | constraints   | apply;      |             |     |
| what         | outcomes      | would count | as success; |     |
| what         | uncertainty   | remains.    |             |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 19/27

| Core questions |         | a              | requirements |     |                    | analyst | asks      |
| -------------- | ------- | -------------- | ------------ | --- | ------------------ | ------- | --------- |
| 1 What         | problem | or opportunity |              |     | are we addressing? |         |           |
| Where          | does    | it occur       | – what       | is  | the context        | and     | boundary? |
2
| 3 Whose    | problem  | is     | it – who | are    | the stakeholders? |     |            |
| ---------- | -------- | ------ | -------- | ------ | ----------------- | --- | ---------- |
| 4 Why does | it       | matter | – what   | goals  | are involved?     |     |            |
| How might  | software |        | help     | – what | scenarios         | are | plausible? |
5
What constrains us – policy, technology, resources, law, time?
6
7 What could prevent success – risk, uncertainty, conflict, feasibility?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 20/27

| Why early | requirements | work | matters |
| --------- | ------------ | ---- | ------- |
For this course, we focus on the robust engineering principle:
Principle
A misunderstood need can propagate into design, implementation, tests, documentation,
training, deployment, and operations. The later it is discovered, the more dependent work may
| need to     | change.      |                      |         |
| ----------- | ------------ | -------------------- | ------- |
| This is why | traceability | and early validation | matter. |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 21/27

| Class exercise: | one sentence,     |            | many        | questions |
| --------------- | ----------------- | ---------- | ----------- | --------- |
| A library asks  | for this feature: |            |             |           |
| “Students       | should be able    | to reserve | study rooms | quickly.” |
In
pairs, identify at least five different unanswered questions. Possible dimensions:
| stakeholder          | and eligibility; |               |     |     |
| -------------------- | ---------------- | ------------- | --- | --- |
| meaning of           | “reserve”;       |               |     |     |
| availability         | and conflicts;   |               |     |     |
| meaning and          | measurement      | of “quickly”; |     |     |
| cancellation/no-show | policy;          |               |     |     |
accessibility;
| authentication | and privacy. |     |     |     |
| -------------- | ------------ | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 22/27

| From    | vague | concern | to engineered |             | requirement |            |              |     |
| ------- | ----- | ------- | ------------- | ----------- | ----------- | ---------- | ------------ | --- |
| Problem | /     | Context | +             | Elicitation | +           | Analysis + | Requirements | +   |
opportunity
|            |         | stakeholders |        | evidence   |     | models     | rationale |     |
| ---------- | ------- | ------------ | ------ | ---------- | --- | ---------- | --------- | --- |
|            |         |              |        | validation |     | / learning |           |     |
| The arrows | are not | a waterfall. | Expect | iteration. |     |            |           |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 23/27

| How this | maps | to your semester | project |
| -------- | ---- | ---------------- | ------- |
Sprint 0 Problem, scope, stakeholders, assumptions, candidate requirements
| Sprint | 1 Elicitation | and Requirements | Baseline v1.0 |
| ------ | ------------- | ---------------- | ------------- |
Sprint 2 Goals, quality, prioritization, negotiation, Baseline v2.0
Sprint 3 Verification, validation, traceability, controlled change, Baseline v3.0
Sprint 4 Integrated professional requirements package and final baseline
Your repository is the evidence trail of how the requirements understanding evolved.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 24/27

Key takeaways
| Software | is useful only | in       | a context | of human | activity. |
| -------- | -------------- | -------- | --------- | -------- | --------- |
| Quality  | depends on     | purpose: | “fitness  | for      | purpose.” |
Requirements problems are often socially and organizationally complex.
RE is a bridge between the problem/application domain and software possibilities.
| RE is iterative, | not | merely | an early | lifecycle | phase. |
| ---------------- | --- | ------ | -------- | --------- | ------ |
The analyst’s job begins with questions, evidence, and boundaries – not with a feature list.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 25/27

| Before   | next         | lecture    |          |                 |     |
| -------- | ------------ | ---------- | -------- | --------------- | --- |
| Tomorrow | (Thu         | Sep 10,    | 4–5      | PM): Lab 1      |     |
| team     | formation;   |            |          |                 |     |
| team     | expectations | agreement; |          |                 |     |
| initial  | discussion   | of         | possible | project topics. |     |
For Monday:
Think of one software system whose biggest challenge is not programming, but
| understanding |          | people,  | policy,  | or competing       | goals. |
| ------------- | -------- | -------- | -------- | ------------------ | ------ |
| Be            | ready to | identify | at least | five stakeholders. |        |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 26/27

| Sources and | attribution |     |
| ----------- | ----------- | --- |
Steve Easterbrook, CSC340 Requirements Engineering – Introduction, University of
Toronto, 2004–05. Conceptual source for software-intensive systems, fitness-for-purpose,
wicked problems, hard/soft systems, RE-as-bridge, and analyst questions. Source states
| non-commercial | Creative Commons | use with attribution. |
| -------------- | ---------------- | --------------------- |
Klaus Pohl, Requirements Engineering: Fundamentals, Principles, and Techniques, 2nd
| ed., Springer, | 2025. |     |
| -------------- | ----- | --- |
Karl Wiegers and Joy Beatty, Software Requirements, 3rd ed., Microsoft Press.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 27/27