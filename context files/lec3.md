| Lecture | 3: Problems, | Goals,          | Scope,          | and Business | Requirements |
| ------- | ------------ | --------------- | --------------- | ------------ | ------------ |
|         | From         | a vague request | to a defensible | project      | mission      |
EECS4312
YorkUniversity
|     |     | Wednesday, | September | 16, 2026 |     |
| --- | --- | ---------- | --------- | -------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 1/24

| Learning | objectives  |          |            |             |
| -------- | ----------- | -------- | ---------- | ----------- |
| By the   | end of this | lecture, | you should | be able to: |
distinguish a problem, symptom, goal, requirement, and proposed solution;
| formulate |     | a useful | problem | statement; |
| --------- | --- | -------- | ------- | ---------- |
separate the as-is situation from the desired to-be situation;
| define | project | vision | and scope | boundaries; |
| ------ | ------- | ------ | --------- | ----------- |
write preliminary business requirements and success measures;
identify assumptions, dependencies, and feasibility questions before detailed elicitation.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 2/24

| The dangerous | starting |     | point: | “We | need an | app” |
| ------------- | -------- | --- | ------ | --- | ------- | ---- |
Examples:
| “We need | a mobile     | app for  | campus          | parking.”      |     |     |
| -------- | ------------ | -------- | --------------- | -------------- | --- | --- |
| “We need | AI to answer | advising |                 | questions.”    |     |     |
| “We need | blockchain   | for      | credential      | verification.” |     |     |
| “We need | a dashboard  | for      | lab equipment.” |                |     |     |
Each statement proposes a solution form before the underlying problem has been
demonstrated.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 3/24

| Problem, | symptom, | goal, requirement, | solution |
| -------- | -------- | ------------------ | -------- |
Symptom Observable indication that something may be wrong or improvable.
Problem Conditionormismatchthatcausesundesirableeffectsforstakeholders.
| Goal | Desired | state or outcome. |     |
| ---- | ------- | ----------------- | --- |
Requirement Needed capability/quality/constraint contributing to a goal.
Solution Design or implementation choice intended to satisfy requirements.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 4/24

Example decomposition
Initial request:
| “Build an | AI chatbot because | advising | email takes too long.” |
| --------- | ------------------ | -------- | ---------------------- |
Possible analysis:
| Symptom: | students wait | several days | for answers. |
| -------- | ------------- | ------------ | ------------ |
Possible problem: high volume of repetitive questions blocks advisors from complex
cases.
Goal: reduce response time while preserving correctness for policy-sensitive questions.
Requirement candidate: common factual questions should receive validated answers
| without | advisor intervention. |     |     |
| ------- | --------------------- | --- | --- |
Possible solution: chatbot – but not the only possible solution.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 5/24

| Ask “why?” | before “how?” |     |
| ---------- | ------------- | --- |
A lightweight root-cause approach is to repeatedly ask why the undesirable outcome occurs.
Example
Students miss equipment pickups. Why? Reminders are missed. Why? Reminders are sent
only by email. Why? Existing system supports only email. Why does that matter? Missed
| pickups waste | scarce equipment | capacity. |
| ------------- | ---------------- | --------- |
The useful requirement may concern reliable notification and confirmation – not necessarily a
| particular channel. |     |     |
| ------------------- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 6/24

| A useful  | problem                | statement       |                     |
| --------- | ---------------------- | --------------- | ------------------- |
| A strong  | problem statement      | usually         | names:              |
| the       | affected stakeholders; |                 |                     |
| the       | current undesirable    | condition;      |                     |
| evidence  | or observable          | consequences;   |                     |
| why       | the issue matters;     |                 |                     |
| important | context                | and boundaries; |                     |
| without   | prematurely            | dictating       | the implementation. |
Weak
| “The problem | is that | we do not | have a mobile app.” |
| ------------ | ------- | --------- | ------------------- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 7/24

| Problem-statement |     | template |     |
| ----------------- | --- | -------- | --- |
Template
For [stakeholder/group], the current [process/situation] causes [undesirable outcome],
especially when [context/condition]. This matters because [impact/evidence]. The project
will investigate how to achieve [desired outcome] within [important constraints], without
| assuming     | a specific implementation | prematurely.         |         |
| ------------ | ------------------------- | -------------------- | ------- |
| The template | is a thinking             | aid, not a mandatory | format. |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 8/24

| As-is versus | to-be             |                          |         |
| ------------ | ----------------- | ------------------------ | ------- |
| As-is        | To-be             |                          |         |
| current      | workflow          | desired outcomes         |         |
| current      | actors            | changed responsibilities |         |
| pain points  | and workarounds   | proposed system          | role    |
| existing     | rules and systems | improved quality         | targets |
current performance or failure patterns changed policies/processes if needed
Requirements connect the two – but they should not erase useful knowledge about the current
situation.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 9/24

| Vision:   | what          | future             | are | we trying   | to create?      |
| --------- | ------------- | ------------------ | --- | ----------- | --------------- |
| A concise | vision should | explain:           |     |             |                 |
| who       | benefits;     |                    |     |             |                 |
| what      | important     | problem            | or  | opportunity | is addressed;   |
| what      | broad         | capability/outcome |     | the         | system enables; |
what differentiates the proposed improvement from the current situation.
| Equipment-loan |     | vision |     |     |     |
| -------------- | --- | ------ | --- | --- | --- |
Enable eligible borrowers and staff to coordinate scarce equipment transparently, reducing
avoidable conflicts and missed pickups while preserving institutional control and accountability.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 10/24

| Goals are | desired | outcomes, | not features |
| --------- | ------- | --------- | ------------ |
Compare:
| Feature-like: | “Provide | a calendar | view.” |
| ------------- | -------- | ---------- | ------ |
Goal: “Borrowers can understand equipment availability before committing to a
reservation.”
| Feature-like: | “Send | SMS reminders.” |     |
| ------------- | ----- | --------------- | --- |
Goal: “Reduce missed pickups caused by overlooked notifications.”
Features may be ways to satisfy goals. Goals help us evaluate alternative features.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 11/24

| Business | objectives | should be | assessable |
| -------- | ---------- | --------- | ---------- |
A business objective becomes more useful when it includes a direction and measure.
Weak
| Improve | the equipment-loan | process. |     |
| ------- | ------------------ | -------- | --- |
Stronger
Reduce staff time spent resolving reservation conflicts during the first term of operation, while
| maintaining | or improving | successful equipment | utilization. |
| ----------- | ------------ | -------------------- | ------------ |
The exact target may initially be uncertain; uncertainty should be recorded rather than hidden.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 12/24

| Requirements | exist | at different          | levels                |            |
| ------------ | ----- | --------------------- | --------------------- | ---------- |
|              |       | Business requirements | /                     | objectives |
|              |       | Why the organization  | is                    | investing  |
|              |       | Stakeholder           | requirements          |            |
|              |       | What stakeholders     | need                  | to achieve |
|              |       | System /              | software requirements |            |
|              |       | What the system       | must do               | or be like |
Traceability should allow us to ask: Which higher-level need justifies this detailed requirement?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 13/24

| Example: | levels      | of requirements |
| -------- | ----------- | --------------- |
| Business | requirement |                 |
BR-01: Reduce avoidable loss of reservable equipment capacity caused by no-shows
| and unresolved | booking     | conflicts. |
| -------------- | ----------- | ---------- |
| Stakeholder    | requirement |            |
SR-04: Equipment staff need timely visibility of reservations at risk of becoming un-
used.
| System requirement |     | candidate |
| ------------------ | --- | --------- |
FR-12: The system shall identify reservations that have not been collected within the
| configured | pickup | window. |
| ---------- | ------ | ------- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 14/24

| Scope: | what |     | is this | project | responsible | for? |
| ------ | ---- | --- | ------- | ------- | ----------- | ---- |
Scope includes:
| capabilities             |        | and         | workflows  | included; |                      |     |
| ------------------------ | ------ | ----------- | ---------- | --------- | -------------------- | --- |
| stakeholder              |        | groups      | addressed; |           |                      |     |
| locations/organizational |        |             |            | units     | covered;             |     |
| data                     | and    | interfaces  | managed;   |           |                      |     |
| explicit                 |        | exclusions; |            |           |                      |     |
| boundaries               |        | with        | existing   | systems   | and human processes. |     |
| Scope                    | is not | “everything |            | useful”   |                      |     |
A disciplined project states what it will not attempt to solve.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 15/24

| In-scope                | / out-of-scope    |              | example |                       |                |
| ----------------------- | ----------------- | ------------ | ------- | --------------------- | -------------- |
| In scope                |                   |              | Out     | of scope              |                |
| browse                  | reservable        | inventory    |         | university-wide       | procurement    |
| request/reserve         |                   | eligible     | items   | full asset accounting |                |
| staff                   | checkout/check-in |              |         | repair-work-order     | management     |
| maintenance/unavailable |                   |              | status  | student disciplinary  | process        |
| reminders               | and               | cancellation |         | identity-provider     | implementation |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 16/24

| Scope | creep versus | legitimate | discovery |
| ----- | ------------ | ---------- | --------- |
Scope creep: uncontrolled expansion without explicit analysis or approval. Legitimate
discovery: RE reveals that an omitted capability is necessary to satisfy the project’s accepted
| goals or | constraints. |     |     |
| -------- | ------------ | --- | --- |
Example
You may discover that maintenance holds are essential to preventing unsafe reservations.
Adding them is not automatically “bad scope creep” if the original business goal cannot be
| met without | them.                 |            |          |
| ----------- | --------------------- | ---------- | -------- |
| The key     | is explicit rationale | and change | control. |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 17/24

| Assumptions | and | dependencies |     | affect | feasibility |
| ----------- | --- | ------------ | --- | ------ | ----------- |
Ask early:
| Do we depend     | on an  | external     | service       | or data | source? |
| ---------------- | ------ | ------------ | ------------- | ------- | ------- |
| Do policies      | permit | the proposed | workflow?     |         |         |
| Is the necessary | data   | available    | and reliable? |         |         |
Can stakeholders realistically perform the new responsibilities?
| Are quality | targets | technically | and economically |     | plausible? |
| ----------- | ------- | ----------- | ---------------- | --- | ---------- |
Are privacy, accessibility, safety, or regulatory constraints likely to dominate the design
space?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 18/24

| Feasibility | is broader | than | “can | we code | it?” |
| ----------- | ---------- | ---- | ---- | ------- | ---- |
Consider:
Technical Can the capability be built/integrated at required quality?
| Operational  | Will it fit   | real workflows  | and      | responsibilities?    |       |
| ------------ | ------------- | --------------- | -------- | -------------------- | ----- |
| Economic     | Are expected  | benefits        | worth    | the costs/resources? |       |
| Schedule     | Can useful    | scope be        | achieved | in the available     | time? |
| Legal/policy | Is it allowed | and governable? |          |                      |       |
Organizational Is there authority, ownership, and willingness to adopt it?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 19/24

| Activity: | repair |     | a project | pitch |
| --------- | ------ | --- | --------- | ----- |
Pitch:
“Our project is an AI-powered smart parking app that predicts empty spaces and
| automatically |           | charges    | users.” |            |
| ------------- | --------- | ---------- | ------- | ---------- |
| In small      | groups,   | produce:   |         |            |
| 1 one         | plausible | underlying | problem | statement; |
| two           | business  | goals;     |         |            |
2
| 3 three | major       | stakeholders; |           |               |
| ------- | ----------- | ------------- | --------- | ------------- |
| 4 two   | assumptions |               | that must | be validated; |
| one     | explicit    | out-of-scope  | item;     |               |
5
| 6 one | feasibility | risk. |     |     |
| ----- | ----------- | ----- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 20/24

| Project       | approval:                 |            | what         | the         | TA should           | be able  | to see |
| ------------- | ------------------------- | ---------- | ------------ | ----------- | ------------------- | -------- | ------ |
| By Thursday’s |                           | Lab 2,     | your team    | should      | be able to          | explain: |        |
| a             | real problem/opportunity, |            |              | not         | merely a technology | idea;    |        |
| at            | least three               | meaningful |              | stakeholder | roles;              |          |        |
| competing     |                           | goals      | or plausible | conflicts;  |                     |          |        |
enough functional richness for roughly 25–40 eventual atomic requirements;
| meaningful |                 | quality | requirements;       |         |             |     |     |
| ---------- | --------------- | ------- | ------------------- | ------- | ----------- | --- | --- |
| a          | small prototype |         | that can            | support | validation; |     |     |
| a          | scope suitable  |         | for a semester-long |         | RE project. |     |     |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 21/24

| What not | to do | in Sprint 0 |
| -------- | ----- | ----------- |
Do not treat personas as verified facts unless you have evidence.
Do not write 40 implementation details to make the project look large.
Do not lock every candidate requirement as “accepted” immediately.
| Do not | hide uncertainty. |     |
| ------ | ----------------- | --- |
Do not use a polished prototype as a substitute for problem analysis.
Do not let GitHub become merely file storage – Issues should begin to represent
| candidate | requirements. |     |
| --------- | ------------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 22/24

Key takeaways
| Start from | problems | and goals, not | preferred technologies. |     |
| ---------- | -------- | -------------- | ----------------------- | --- |
Distinguish symptoms, problems, goals, requirements, and solutions.
| Understand | both the | as-is and desired | to-be situation. |     |
| ---------- | -------- | ----------------- | ---------------- | --- |
Business requirements explain why investment/change is justified.
| Scope and | feasibility | are requirements-engineering |     | concerns. |
| --------- | ----------- | ---------------------------- | --- | --------- |
Explicit assumptions and exclusions make later reasoning more trustworthy.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 23/24

| Suggested | reading | and next | steps |
| --------- | ------- | -------- | ----- |
Pohl, Requirements Engineering, 2nd ed.: context, goals, and requirements framework
sections.
Wiegers & Beatty, Software Requirements, 3rd ed.: business requirements, vision and
scope.
Before Lab 2, bring your team project idea and enough context to discuss approval
| criteria | with the TA. |     |     |
| -------- | ------------ | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 24/24