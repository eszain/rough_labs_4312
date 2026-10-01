| Lecture | 5: Planning | and Conducting | Requirements | Elicitation |
| ------- | ----------- | -------------- | ------------ | ----------- |
Interviews, workshops, observation, questionnaires, existing-system analysis, and
prototyping
EECS4312
YorkUniversity
|     |     | Wednesday, September | 23, 2026 |     |
| --- | --- | -------------------- | -------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 1/43

| Where this lecture fits |             |              |              |
| ----------------------- | ----------- | ------------ | ------------ |
| Problem, goals,         | Elicitation | Evidence and | Requirements |
| scope                   | planning    | synthesis    |              |
baseline
Today we move from what we still need to understand to how we will obtain credible
evidence about it.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 2/43

| Learning | objectives           |            |             |
| -------- | -------------------- | ---------- | ----------- |
| By the   | end of this lecture, | you should | be able to: |
build a focused elicitation plan from project uncertainties and information gaps;
select appropriate sources and elicitation techniques for different questions;
plan and conduct interviews, workshops, observation, questionnaires, document/system
| analysis, | and prototyping; |                |                         |
| --------- | ---------------- | -------------- | ----------------------- |
| recognize | common           | sources of     | bias and weak evidence; |
| combine   | techniques       | to triangulate | important requirements; |
record elicitation evidence so that later requirements are traceable to their sources.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 3/43

| Elicitation | is            | not “ask        | users          | what features | they want” |
| ----------- | ------------- | --------------- | -------------- | ------------- | ---------- |
| A weak      | elicitation   | question        | is:            |               |            |
| “What       | features      | should          | the new system | have?”        |            |
| A stronger  | elicitation   | effort          | investigates:  |               |            |
| goals       | and problems; |                 |                |               |            |
| current     | work          | and exceptions; |                |               |            |
| information |               | and decisions;  |                |               |            |
| constraints | and           | policies;       |                |               |            |
| quality     | expectations; |                 |                |               |            |
| conflicting | viewpoints;   |                 |                |               |            |
| assumptions |               | that need       | confirmation;  |               |            |
| possible    | future        | situations.     |                |               |            |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 4/43

| Why elicitation     | is difficult     |                  |           |             |
| ------------------- | ---------------- | ---------------- | --------- | ----------- |
| Important knowledge | is often:        |                  |           |             |
| distributed         | across people,   | documents,       | systems,  | and data;   |
| tacit: people       | use it routinely | but find         | it hard   | to explain; |
| inconsistent:       | different        | sources describe | different | rules;      |
context-dependent: the answer changes with workload, role, exception, or timing;
politically sensitive: stakeholders may gain or lose power, effort, or autonomy;
future-oriented: stakeholders may know the current process better than the desired one.
AdaptedinpartfromEasterbrook’sCSC340elicitationlecture: distributedknowledge,tacitknowledge,limited
observability,andbias.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 5/43

| The “say-do” | gap |     |
| ------------ | --- | --- |
A stakeholder may accurately describe the official process while routinely following a different
| practiced process. |         |     |
| ------------------ | ------- | --- |
| Equipment-loan     | example |     |
Policy: “Every return is inspected before the item is available again.”
| Interview: staff | say the inspection | always occurs. |
| ---------------- | ------------------ | -------------- |
Observation: during busy periods, low-risk items are placed directly back into circulation.
This does not automatically mean anyone is dishonest. It may reveal tacit rules, workload
pressures, exceptions, or a mismatch between policy and reality.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 6/43

| Start with | information |     | gaps, | not | techniques |
| ---------- | ----------- | --- | ----- | --- | ---------- |
Before choosing interviews or surveys, write down what you do not yet know.
Examples
| Why are | reservations |         | cancelled | after staff | approval? |
| ------- | ------------ | ------- | --------- | ----------- | --------- |
| Which   | exceptions   | require | human     | judgment?   |           |
What information do staff inspect before approving a high-value loan?
| How often | do             | borrowers | fail to | collect | reserved equipment?   |
| --------- | -------------- | --------- | ------- | ------- | --------------------- |
| Which     | policy defines |           | who may | borrow  | restricted equipment? |
A technique is useful only if it helps answer an important question.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 7/43

| A practical | elicitation-planning |      | cycle     |            |              |
| ----------- | -------------------- | ---- | --------- | ---------- | ------------ |
|             | 1. Identify          |      | 2. Select | 3. Select  | 4. Plan      |
|             | information          | gaps |           | techniques | session/data |
sources
|     |     |     | 7. Identify | 6. Synthesize | 5. Record |
| --- | --- | --- | ----------- | ------------- | --------- |
|     |     |     | follow-ups  | and compare   | evidence  |
Elicitation is iterative: new evidence normally creates new questions.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 8/43

Sources of requirements
Do not equate “source” with “stakeholder.” Useful sources include:
| People |     | Artifacts and | environments |
| ------ | --- | ------------- | ------------ |
end users and operators; policies, forms, contracts, legislation;
managers and decision-makers; current software and interfaces;
support and maintenance staff; logs, tickets, reports, usage data;
| compliance/security | specialists; | process | documentation; |
| ------------------- | ------------ | ------- | -------------- |
external partners and service providers. competitor/analogous systems.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 9/43

| Plan source          | coverage        | deliberately |           |                  |
| -------------------- | --------------- | ------------ | --------- | ---------------- |
| A convenient         | planning table: |              |           |                  |
| Question/uncertainty |                 | Source       | Technique | Expectedevidence |
Whydopickupsfail? Borrowers; staff; book- Interviews+logreview Causes, frequencies, excep-
|     |     | inglogs |     | tions |
| --- | --- | ------- | --- | ----- |
How are restricted items ap- Policy;seniorstaff Documentanalysis+in- Rule source + discretionary
| proved? |     |     | terview | cases |
| ------- | --- | --- | ------- | ----- |
Whathappensatthedeskunder Front-deskstaff Observation Actual workflow,
| load? |     |     |     | workarounds |
| ----- | --- | --- | --- | ----------- |
Would self-rescheduling be un- Representative borrow- Prototypewalkthrough Usabilityissues,missingrules
| derstandable? |     | ers |     |     |
| ------------- | --- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 10/43

| Technique         | selection: | no method       | is “best” | in general |
| ----------------- | ---------- | --------------- | --------- | ---------- |
| Choose techniques | based on   | the information | problem.  |            |
| Need              |            | Oftenuseful     |           | Why        |
Understandgoals,opinions,excep- Interviews Richprobingandfollow-up
tions
Resolveconflictingviewpoints Workshop Stakeholdersinteractdirectly
| Discovertacitworkpractices |     | Observation |     | Capturesworkincontext |
| -------------------------- | --- | ----------- | --- | --------------------- |
Reachmanysimilarusers Questionnaire Breadthandcomparableresponses
Learnrules/historyquickly Documents+currentsystem Existingevidencebeforemeetings
Exploreuncertainworkflow/UI Prototype Makesabstractideasconcrete
Quantifyfrequency/volume Logs/harddata Testsclaimsagainstoperationalevidence
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 11/43

| Triangulation: | combine | sources | and techniques |
| -------------- | ------- | ------- | -------------- |
For an important requirement, confidence increases when independent evidence converges.
|     |     | Interviews | Observation |
| --- | --- | ---------- | ----------- |
Candidate
requirement
|     | Documents | /   | logs Prototype |
| --- | --------- | --- | -------------- |
Triangulationdoesnotguaranteetruth. Ithelpsrevealagreement,disagreement,anduncertaintyacrossevidencesources.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 12/43

| Interviews:  | when           | they          | are strong   |             |
| ------------ | -------------- | ------------- | ------------ | ----------- |
| Interviews   | are especially | useful        | for:         |             |
| goals,       | motivations,   | frustrations, | and          | priorities; |
| exceptions   | and            | unusual       | cases;       |             |
| explanations | of             | decisions     | and business | rules;      |
| terminology  | and            | domain        | concepts;    |             |
| following    | unexpected     | leads         | in depth.    |             |
Weakness
Interview evidence is removed from the actual work context and is vulnerable to recall error,
tacit knowledge, post-hoc rationalization, and interviewer bias.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 13/43

| Structured, | semi-structured, | and open | interviews |
| ----------- | ---------------- | -------- | ---------- |
Structured: same prepared questions, similar order; easier comparison, less flexibility.
Semi-structured: prepared themes/questions plus probing; often a strong RE default.
Open / unstructured: broad conversation around a topic; useful early, harder to compare and
analyze.
For most project elicitation, a semi-structured interview guide gives enough consistency
| while still allowing | discovery. |     |     |
| -------------------- | ---------- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 14/43

| Interview      | planning:  | prepare         | a guide, | not a script |
| -------------- | ---------- | --------------- | -------- | ------------ |
| A useful guide | contains:  |                 |          |              |
| purpose        | and topics | to learn about; |          |              |
1
| 2 participant | role and             | why this person | was selected; |     |
| ------------- | -------------------- | --------------- | ------------- | --- |
| 6–10          | core open questions; |                 |               |     |
3
| likely | probes and follow-ups; |     |     |     |
| ------ | ---------------------- | --- | --- | --- |
4
| 5 artifacts             | to ask about: | forms, screens, | reports, | examples; |
| ----------------------- | ------------- | --------------- | -------- | --------- |
| 6 recording/note-taking |               | plan and        | consent; |           |
closing question: “What important issue have I not asked about?”
7
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 15/43

| Use a          | funnel: | context   | → examples |     | → details |
| -------------- | ------- | --------- | ---------- | --- | --------- |
| Equipment-loan |         | interview |            |     |           |
Broad: “Walk me through what happens from a reservation request until pickup.”
Example: “Tell me about the last reservation that required extra staff work.”
| Probe: | “What | made it exceptional? |     | Who decided | what to do?” |
| ------ | ----- | -------------------- | --- | ----------- | ------------ |
Clarify rule: “Does that always happen, or only under certain conditions?”
| Verify: “So | I understand | that | ... Is that | correct?” |     |
| ----------- | ------------ | ---- | ----------- | --------- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 16/43

| Avoid questions | that | manufacture | the answer |     |     |
| --------------- | ---- | ----------- | ---------- | --- | --- |
| Weak / leading  |      |             | Stronger   |     |     |
“Wouldn’t automatic reminders solve “What causes missed pickups?”
| this?”      |                   |                   | “How do      | you currently    | decide what  |
| ----------- | ----------------- | ----------------- | ------------ | ---------------- | ------------ |
| “How useful | would an          | AI assistant be?” | action to    | take?”           |              |
|             |                   |                   | “Where       | do delays occur? | Can you give |
| “Do you     | agree the current | system is too     |              |                  |              |
| slow?”      |                   |                   | an example?” |                  |              |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 17/43

| Useful interview   |        | probes      |              |          |            |           |              |
| ------------------ | ------ | ----------- | ------------ | -------- | ---------- | --------- | ------------ |
| When a stakeholder |        | makes       | an important |          | statement, |           | probe it:    |
| Example:           | “Can   | you         | give me      | a recent |            | example?” |              |
| Exception:         | “When  |             | would        | that not | be         | true?”    |              |
| Source:            | “Where | does        | that         | rule     | come       | from?”    |              |
| Frequency:         | “How   | often       | does         | that     | occur?”    |           |              |
| Decision:          | “What  | information |              | do       | you        | use to    | decide?”     |
| Consequence:       |        | “What       | happens      |          | if this    | step      | is skipped?” |
| Alternative:       |        | “How        | else could   | that     | goal       | be        | achieved?”   |
| Meaning:           | “What  | does        | ‘available’  |          | mean       | in this   | context?”    |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 18/43

| Workshops: | elicitation |     | through | structured | interaction |
| ---------- | ----------- | --- | ------- | ---------- | ----------- |
A requirements workshop brings multiple stakeholders together to produce or reconcile shared
artifacts.
| useful for | conflicting  | goals    | or terminology; |                     |     |
| ---------- | ------------ | -------- | --------------- | ------------------- | --- |
| allows     | participants | to react | to each         | other’s statements; |     |
| can create | agreement    | faster   | than serial     | interviews;         |     |
works well with visual artifacts: process maps, prototypes, story maps, models.
But
A workshop needs facilitation. Dominant participants, status differences, groupthink, and
unclear objectives can make the result look more consensual than it really is.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 19/43

| Plan a     | workshop            | around          | a concrete | output |
| ---------- | ------------------- | --------------- | ---------- | ------ |
| Weak goal: | “Discuss            | the new booking | system.”   |        |
| Stronger   | workshop objective: |                 |            |        |
“Bytheendof60minutes,identifyandagreeonthenormalreservationflow,document
unresolved exceptions, and record at least three stakeholder conflicts requiring follow-
up.”
Useful structure:
| 1 objective  | + working        | rules;      |     |     |
| ------------ | ---------------- | ----------- | --- | --- |
| 2 individual | idea generation; |             |     |     |
| shared       | modeling         | / grouping; |     |     |
3
| challenge | assumptions | and exceptions; |     |     |
| --------- | ----------- | --------------- | --- | --- |
4
| 5 record | agreements | and open | issues; |     |
| -------- | ---------- | -------- | ------- | --- |
| assign   | follow-up  | owners.  |         |     |
6
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 20/43

| Observation:  |              | discover               | work   |               | in context               |
| ------------- | ------------ | ---------------------- | ------ | ------------- | ------------------------ |
| Observation   | is           | useful when:           |        |               |                          |
| work          | is difficult | to verbalize;          |        |               |                          |
| sequence,     |              | timing, interruptions, |        | or            | physical context matter; |
| workarounds   |              | are likely;            |        |               |                          |
| the           | official     | process may            | differ | from          | actual practice;         |
| collaboration |              | between                | roles  | is important. |                          |
Possible approaches include non-participant observation, shadowing, contextual inquiry, or
| participant | observation | where | appropriate. |     |     |
| ----------- | ----------- | ----- | ------------ | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 21/43

| Observation             | needs                | a protocol     |                        |
| ----------------------- | -------------------- | -------------- | ---------------------- |
| Do not simply           | “watch people        | work.”         | Decide what to record. |
| Example observation     | protocol             |                |                        |
| For each equipment      | return,              | record:        |                        |
| start/end               | time and             | interruptions; |                        |
| artifacts/screens/forms |                      | used;          |                        |
| handoffs                | between roles;       |                |                        |
| exceptions              | and workarounds;     |                |                        |
| questions               | asked of colleagues; |                |                        |
| information             | unavailable          | at decision    | time;                  |
| any difference          | from                 | documented     | procedure.             |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 22/43

Observation has its own biases
Watch for:
observer effect: people may behave differently while watched;
sampling bias: one hour may not represent month-end or peak periods;
interpretation bias: the analyst may assign the wrong meaning to an action;
privacy/confidentiality: observation may expose personal or sensitive information;
normalization: experienced workers may stop noticing their own workarounds.
Triangulate observations with follow-up questions, documents, and data.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 23/43

| Questionnaires:  |             | breadth        |            | rather       | than          | depth |
| ---------------- | ----------- | -------------- | ---------- | ------------ | ------------- | ----- |
| Questionnaires   | can         | be useful      | when:      |              |               |       |
| many respondents |             | share          | a          | comparable   | role;         |       |
| you need         | comparable  |                | responses  | across       | a population; |       |
| you want         | to estimate |                | prevalence | of           | known issues; |       |
| respondents      | are         | geographically |            | distributed; |               |       |
| interviews       | with        | everyone       | are        | impractical. |               |       |
They are usually weaker for discovering tacit requirements, complex exceptions, and unknown
categories.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 24/43

| Questionnaire | design | pitfalls |     |     |
| ------------- | ------ | -------- | --- | --- |
Common problems:
| leading or         | loaded questions; |           |                    |              |
| ------------------ | ----------------- | --------- | ------------------ | ------------ |
| ambiguous          | terms;            |           |                    |              |
| double-barrelled   | questions;        |           |                    |              |
| response           | options that omit | realistic | answers;           |              |
| inconsistent       | scales;           |           |                    |              |
| asking respondents | to estimate       |           | quantities they    | cannot know; |
| self-selection     | and sampling      | bias;     |                    |              |
| treating a         | small convenience | sample    | as representative. |              |
Rule
Pilot the questionnaire with a few representative people before wider use.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 25/43

| Document         | analysis:                    | learn before          | consuming    | stakeholder | time |
| ---------------- | ---------------------------- | --------------------- | ------------ | ----------- | ---- |
| Useful artifacts | include:                     |                       |              |             |      |
| policies,        | procedures,                  | contracts, standards, | regulations; |             |      |
| forms,           | reports, templates,          | emails, help          | pages;       |             |      |
| organization     | charts and                   | role descriptions;    |              |             |      |
| previous         | requirements/specifications; |                       |              |             |      |
| support          | tickets and                  | incident reports;     |              |             |      |
| training         | and onboarding               | material.             |              |             |      |
Documents help build domain vocabulary and prepare better interview questions.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 26/43

| But documents |         | describe | an intended | or historical | reality |
| ------------- | ------- | -------- | ----------- | ------------- | ------- |
| A document    | may be: |          |             |               |         |
outdated;
incomplete;
| written | for a different | audience; |     |     |     |
| ------- | --------------- | --------- | --- | --- | --- |
normative (what should happen), not descriptive (what does happen);
| internally | inconsistent | with other | documents; |     |     |
| ---------- | ------------ | ---------- | ---------- | --- | --- |
| silently   | bypassed in  | practice.  |            |     |     |
Treat documents as evidence to investigate, not as automatically correct requirements.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 27/43

Existing-system analysis: the running system is also a source
| Inspect      | the current | system          | when      | available: |
| ------------ | ----------- | --------------- | --------- | ---------- |
| screens      | and         | workflows;      |           |            |
| data         | fields      | and validation  |           | rules;     |
| reports      | and         | exports;        |           |            |
| permissions  |             | and roles;      |           |            |
| error        | messages    | and             | exception | handling;  |
| integrations |             | and interfaces; |           |            |
| logs,        | usage       | analytics,      | support   | tickets;   |
| undocumented |             | behaviors       | users     | depend on. |
Donotassumethateveryexistingfeatureisstillrequired. Legacybehaviormayreflectobsoleteconstraints.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 28/43

| Hard data   |            | can test        | stakeholder  |               | claims             |
| ----------- | ---------- | --------------- | ------------ | ------------- | ------------------ |
| Suppose     | interviews | suggest:        |              |               |                    |
| “Missed     | pickups    | are             | a major      | problem.”     |                    |
| Operational | data       | might           | help answer: |               |                    |
| What        | fraction   | of reservations |              | are not       | collected?         |
| Which       | categories | of              | equipment    | are affected? |                    |
| Does        | the rate   | differ          | by borrower  | type,         | day, or lead time? |
| How         | much       | staff time      | is spent     | recovering    | from the problem?  |
Data tells us what happened; interviews and observation often help explain why.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 29/43

| Prototyping | as  | elicitation, |     | not | just | design |
| ----------- | --- | ------------ | --- | --- | ---- | ------ |
A prototype makes an abstract future system concrete enough to provoke useful reactions.
| wireframes | can | expose | missing | information |     | and terminology; |
| ---------- | --- | ------ | ------- | ----------- | --- | ---------------- |
clickable flows reveal exception paths and navigation assumptions;
| paper prototypes |              | support | rapid | alternatives; |               |           |
| ---------------- | ------------ | ------- | ----- | ------------- | ------------- | --------- |
| mock data        | can          | expose  | data  | and privacy   | requirements; |           |
| prototype        | walkthroughs |         | help  | formulate     | acceptance    | criteria. |
The prototype is a question-generating instrument, not proof that requirements are correct.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 30/43

| Low fidelity    | first when | uncertainty | is high         |                  |             |
| --------------- | ---------- | ----------- | --------------- | ---------------- | ----------- |
| Low fidelity    |            |             | Higher fidelity |                  |             |
| sketches;       |            |             | clickable       | prototype;       |             |
| paper screens;  |            |             | realistic       | data;            |             |
| wireframes;     |            |             | partial         | implementation.  |             |
| storyboards.    |            |             | Useful later,   | but stakeholders | may mistake |
|                 |            |             | polish for      | completeness or  | commitment. |
| Fast to change; | encourages | criticism.  |                 |                  |             |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 31/43

| Prototype   | risk:    | solution     |          | fixation    |               |
| ----------- | -------- | ------------ | -------- | ----------- | ------------- |
| A prototype | can      | accidentally | narrow   | the         | conversation: |
| “Do         | you want | the Submit   |          | button here | or there?”    |
| when the    | more     | important    | question | is:         |               |
“Why must this information be submitted at all, and who needs it?”
Use prototypes to test hypotheses. Keep alternative workflows visible when the problem is still
uncertain.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 32/43

Technique comparison: strengths and blind spots
Technique Strongfor Weakfor Typicalrisk
Interview motivations,exceptions,depth actualbehavioratscale recall/interviewerbias
Workshop conflict,sharedunderstanding sensitiveminorityviews dominance/groupthink
Observation tacitworkflow,context futurepossibilities observer+samplingeffects
Questionnaire breadth,comparableresponses unknownneeds,nuance poorwording/samplebias
Documents/system rules,history,terminology currentinformalpractice obsolete or normative evi-
dence
Prototype futureworkflow,concretefeed- underlyinggoalsifoverused fixation/falsecompleteness
back
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 33/43

| A worked       | elicitation | plan: equipment-loan |           | system            |
| -------------- | ----------- | -------------------- | --------- | ----------------- |
| Informationgap |             | Source               | Technique | Follow-upevidence |
Why do borrowers miss pick- Borrowers+logs 5 interviews + booking- Comparestatedcauseswithpat-
| ups? |     |     | datasample | ternsinleadtime/cancellations |
| ---- | --- | --- | ---------- | ----------------------------- |
Howareexceptionshandled? Frontdesk Observation + debrief Document exception categories
|     |     |     | interview | anddecisioninputs |
| --- | --- | --- | --------- | ----------------- |
Whichrulesaremandatory? Policy+manager Documentanalysis+in- Separate policy constraint from
|     |     |     | terview | localpractice |
| --- | --- | --- | ------- | ------------- |
Canborrowersself-reschedule? Borrowers+staff Paper prototype work- Record failure cases, conflicts,
|     |     |     | shop | andrevisedrules |
| --- | --- | --- | ---- | --------------- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 34/43

| Evidence            | record:              |               | capture     |             | more      | than             | “meeting  | notes” |
| ------------------- | -------------------- | ------------- | ----------- | ----------- | --------- | ---------------- | --------- | ------ |
| For each            | important            | elicitation   |             | activity,   |           | record:          |           |        |
| date,               | participants/source, |               |             | technique,  |           | and purpose;     |           |        |
| questions/tasks     |                      |               | used;       |             |           |                  |           |        |
| observations        |                      | or statements |             | relevant    |           | to requirements; |           |        |
| direct              | quotes               | only          | when        | useful      | and       | permitted;       |           |        |
| analyst             | interpretation       |               |             | separately  | from      | source           | evidence; |        |
| contradictions      |                      | with          | other       | sources;    |           |                  |           |        |
| assumptions         |                      | created       | or          | challenged; |           |                  |           |        |
| follow-up           | questions;           |               |             |             |           |                  |           |        |
| requirements/issues |                      |               | potentially |             | affected. |                  |           |        |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 35/43

| Separate | evidence   | from interpretation |                 |                |     |
| -------- | ---------- | ------------------- | --------------- | -------------- | --- |
| Evidence |            | Interpretation      |                 |                |     |
| “During  | 8 observed | returns, staff      |                 |                |     |
|          |            |                     | “The new system | should contain | an  |
consultedapaperchecklist6times.” electronic inspection checklist.”
The interpretation may be reasonable, but it is still a design/requirements inference that needs
| justification | and validation. |     |     |     |     |
| ------------- | --------------- | --- | --- | --- | --- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 36/43

| Ethics and | practical | safeguards |     |     |
| ---------- | --------- | ---------- | --- | --- |
Before eliciting:
| explain | the purpose | of the | activity; |     |
| ------- | ----------- | ------ | --------- | --- |
do not misrepresent a simulation as real stakeholder evidence;
| ask permission | before           | recording; |         |             |
| -------------- | ---------------- | ---------- | ------- | ----------- |
| collect        | only information | needed     | for the | RE purpose; |
avoid placing sensitive personal data in project repositories;
| clarify | whether responses |     | will be attributed; |     |
| ------- | ----------------- | --- | ------------------- | --- |
respect organizational confidentiality and access restrictions;
| tell participants | how | follow-up/validation |     | will occur. |
| ----------------- | --- | -------------------- | --- | ----------- |
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 37/43

| In-class | exercise: |     | choose | an  | elicitation | strategy |
| -------- | --------- | --- | ------ | --- | ----------- | -------- |
A university wants to replace its informal graduate-room booking process. Current tools
include email, spreadsheets, and door signs. Complaints include double bookings, unused
| reservations, |     | and unclear | priority | rules. |     |     |
| ------------- | --- | ----------- | -------- | ------ | --- | --- |
In groups, choose three important information gaps. For each:
| 1 identify |     | the best | source(s);  |            |     |     |
| ---------- | --- | -------- | ----------- | ---------- | --- | --- |
| select     | one | primary  | elicitation | technique; |     |     |
2
| 3 explain  | why | that             | technique | fits;       |             |             |
| ---------- | --- | ---------------- | --------- | ----------- | ----------- | ----------- |
| 4 identify |     | one likely       | bias or   | limitation; |             |             |
| name       | a   | second technique |           | that could  | triangulate | the result. |
5
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 38/43

Possible debrief
| Examples of | defensible choices:         |           |              |
| ----------- | --------------------------- | --------- | ------------ |
| Priority    | rules: policy/administrator | documents | + interview; |
Actual workarounds: coordinator observation + follow-up interview;
| Frequency | of no-shows: | spreadsheet/history | analysis; |
| --------- | ------------ | ------------------- | --------- |
Different student needs: semi-structured interviews across user groups;
Future self-service workflow: low-fidelity prototype workshop;
Breadth of preference: questionnaire after qualitative categories are understood.
There is rarely one uniquely correct technique. The justification matters.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 39/43

Connection to EECS4312 Sprint 1
Your Sprint 1 elicitation work should show:
a clear information gap / elicitation question;
a justified source;
a justified technique;
a record of the evidence obtained;
separation of evidence, analogy, simulation, and assumption;
contradictions and unresolved uncertainty;
follow-up questions;
traceability from evidence toward candidate/baseline requirements.
Key principle
Do not perform three elicitation activities merely to satisfy a project count. Each activity
should answer a real question.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 40/43

Takeaways
1 Start with what you need to learn, not your favorite elicitation technique.
2 Sources include people, documents, systems, data, and the work environment.
3 Interviews provide depth; workshops provide interaction; observation provides context;
questionnaires provide breadth.
4 Documents and existing systems are evidence, not unquestionable truth.
5 Prototypes are especially useful for eliciting reactions to an uncertain future workflow.
6 Important requirements should normally be supported by more than one kind of
evidence when feasible.
7 Record evidence in a form that can later support traceability and validation.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 41/43

Further reading and online references
Steve Easterbrook, University of Toronto CSC340, Eliciting Requirements:
https://www.cs.toronto.edu/ sme/CSC340F/slides/07-elicitation.pdf
CSC340 course archive and elicitation reading list (includes Hickey & Davis on technique selection):
https://www.cs.toronto.edu/ sme/CSC340F/
IREB/CPRE, Requirements Elicitation module overview and resources:
https://cpre.ireb.org/en/concept/requirements-elicitation
IREB/CPRE Download Center, Requirements Elicitation syllabus/handbook:
https://cpre.ireb.org/en/downloads-and-resources/downloads
IEEE Computer Society, SWEBOK v4.0, Software Requirements knowledge area:
https://www.computer.org/education/bodies-of-knowledge/software-engineering/v4
TheEasterbrookCSC340teachingmaterialsarepublishedfornon-commercialeducationalusewithattributionunderCC
BY-NC-SA2.5,asstatedonthecoursesite.
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 42/43

Next step
| From collecting | evidence   | to turning    | evidence       | into precise |
| --------------- | ---------- | ------------- | -------------- | ------------ |
| scenarios,      | use cases, | user stories, | and acceptance | criteria.    |
Before Lab 4, review your project’s biggest unanswered questions. Which ones are best
explored through a simulated interview, and which should be addressed using another
technique?
EECS4312–SoftwareRequirementsEngineering YorkUniversity–Fall2026 43/43