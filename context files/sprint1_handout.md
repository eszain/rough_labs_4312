# EECS4312 - Software Requirements Engineering
## Course Project - Requirements Sprint 1: Elicitation & Initial Requirements Baseline

- **Course code:** EECS4312
- **Institution:** York University
- **Term:** Fall 2026
- **Sprint period:** September 28–October 25, 2026
- **Requirements Sprint 1 due:** Sunday, October 25, 2026, 11:59 PM
- **Weight:** 5% of final course grade
- **Submission:** GitHub Classroom team repository
- **Scheduled project-support lab(s):** October 1, October 8, October 22
- **Reading Week:** October 10–16, 2026 - no lecture, lab, or project deadline.

---

## PREFACE

You have completed Requirements Sprint 0 and established a preliminary understanding of your project's problem, scope, stakeholders, context, and candidate requirements. Sprint 1 moves from initial assumptions and candidate ideas toward a defensible Requirements Baseline v1.0.

The central question for this sprint is:
> What requirements can your team reasonably accept at this point, and what evidence, rationale, scenarios, models, and review support those decisions?

This is still not a software-development sprint. You are not graded on how many features you implement. You are graded on the quality of your requirements work: how systematically you elicit information, distinguish evidence from assumptions, refine requirements, model important aspects of the problem, define acceptance criteria, trace requirements to their origins, and review the resulting baseline.

Expect Sprint 0 artifacts to change. Discovering that an early assumption was wrong, that a stakeholder need was misunderstood, or that a candidate requirement should be split, merged, rejected, or rewritten is a sign of useful Requirements Engineering.

---

## 1. SPRINT 0 CONTINUITY

### 1.1 Preserve the Sprint 0 submission
Once Sprint 0 marking is complete, do not rewrite the submitted `doc/sprint0/` snapshot. Sprint 1 must show how your understanding evolved.

If Sprint 0 feedback requires corrections, record those corrections in Sprint 1 and create revised copies of affected artifacts under `doc/sprint1/` where appropriate.

### 1.2 Address Sprint 0 feedback
Create:
`doc/sprint1/sprint0-feedback.md`

For each important instructor/TA comment, record:
- the feedback received;
- whether the team agrees with the issue identified;
- action taken;
- affected artifact(s) or requirement(s);
- link to the relevant commit, Issue, or file where practical;
- any feedback item not yet resolved and why.

Do not copy feedback without responding to it.

---

## 2. SPRINT 1 PLANNING

Create:
`doc/sprint1/sprint1-plan.md`

The plan must document the team's Sprint 1 planning discussion and include:
- participants;
- Sprint 1 goal;
- major requirements-engineering activities to be completed;
- information gaps carried forward from Sprint 0;
- elicitation activities to be performed;
- artifacts/models to be produced;
- responsibilities and review assignments;
- important risks or blockers;
- internal deadlines;
- decisions about which candidate requirements require the most attention.

This is not a programming task breakdown. Tasks should describe RE work such as "analyze public policy documents," "review authentication requirements," "develop state model for reservation lifecycle," or "inspect FR-012 through FR-020 for ambiguity and testability."

Every team member should have meaningful RE responsibilities.

---

## 3. ELICITATION PLAN

Create:
`doc/sprint1/elicitation-plan.md`

### 3.1 Purpose
Requirements elicitation is not simply asking, "What features do you want?" Your plan should identify what the team does not yet know and select techniques that can reduce those uncertainties.

### 3.2 Required content
Document:
1. **Elicitation objectives** - what must the team learn?
2. **Information gaps** - which assumptions, conflicts, or unknowns from Sprint 0 require investigation?
3. **Target stakeholder roles or evidence sources** - who or what can provide relevant information?
4. **Techniques** - why each selected technique is suitable.
5. **Questions/prompts/tasks** - what will actually be asked, observed, inspected, or compared?
6. **Expected evidence type** - direct stakeholder evidence, public/documented evidence, analogy, simulation, or team assumption.
7. **Bias/limitations** - what could distort the findings?
8. **Ethics/privacy considerations** - what information should not be collected or retained?
9. **Responsibility and schedule** - who performs each activity and when?

### 3.3 Minimum elicitation requirement
Complete at least three elicitation activities using at least two different techniques.

At least one activity must use observable or documented evidence, for example:
- analysis of an existing system;
- public documentation or policy;
- public workflow/process information;
- publicly available support material;
- public user feedback analyzed at an appropriate aggregate level;
- another instructor-approved source.

A simulated stakeholder interview or workshop may be used, including the course lab exercise, but it must be labeled as a simulation. A simulated stakeholder cannot establish facts about real users.

A real external stakeholder interview is not required.

### 3.4 Suitable elicitation techniques
Depending on the project, techniques may include:
- structured or semi-structured interview;
- workshop;
- observation/contextual inquiry where appropriate;
- document analysis;
- existing-system analysis;
- questionnaire or survey;
- scenario walkthrough;
- prototype-based elicitation;
- interface analysis;
- brainstorming used to generate hypotheses;
- domain or regulatory research.

Using several techniques is valuable only if each one addresses a real information need.

---

## 4. ELICITATION EVIDENCE AND SYNTHESIS

Create:
- `doc/sprint1/elicitation-evidence.md`
- `doc/sprint1/elicitation-synthesis.md`
- `doc/sprint1/evidence/`

### 4.1 elicitation-evidence.md
For each elicitation activity, record:
- activity ID;
- date;
- participants or evidence source;
- technique;
- purpose/questions investigated;
- concise notes/findings;
- direct observations or statements;
- interpretation by the team;
- assumptions that remain;
- candidate requirements created or affected;
- conflicts or contradictions discovered;
- unresolved follow-up questions;
- links/references to supporting material where appropriate.

Supporting files such as anonymized notes, screenshots of public systems, diagrams, questionnaires, or document-analysis tables may be placed under `doc/sprint1/evidence/`.

Do not upload confidential, private, copyrighted-in-full, or personally sensitive material merely to prove that an activity occurred. Summarize responsibly and link to public sources where appropriate.

### 4.2 Evidence discipline
For important findings, distinguish among:
- **Direct evidence** - information obtained from a real stakeholder or directly observable process;
- **Documented/public evidence** - information supported by a credible accessible source;
- **Analogy** - inference from a comparable system or process;
- **Simulation** - information produced by a role-play or instructor-provided stakeholder scenario;
- **Assumption** - a proposition created by the team that has not yet been supported.

Do not convert a plausible assumption into "stakeholder evidence" simply because the team agrees with it.

### 4.3 elicitation-synthesis.md
Synthesize the activities rather than repeating the notes.

Include:
- major themes discovered;
- new stakeholder needs;
- important constraints;
- newly discovered scenarios;
- conflicts among findings;
- findings that contradict Sprint 0 assumptions;
- requirements added, changed, split, merged, or rejected;
- unresolved questions to carry into Sprint 2;
- confidence assessment for the current understanding.

The strongest submissions will show how elicitation changed the project, not merely that elicitation was performed.

---

## 5. REVISED FOUNDATION ARTIFACTS

If your Sprint 1 work changes the foundation established in Sprint 0, place revised current versions under `doc/sprint1/`:
- `vision-scope.md`
- `stakeholders.md`
- `context.md`
- `glossary.md`
- `personas.md` *(only if materially revised)*

At minimum, `vision-scope.md`, `stakeholders.md`, `context.md`, and `glossary.md` must be reviewed for consistency with the new baseline. If no revision is needed, state this explicitly in `sprint0-feedback.md` or `elicitation-synthesis.md`.

Do not silently leave a contradiction between Sprint 0 and Sprint 1 artifacts.

---

## 6. REQUIREMENTS BASELINE v1.0

Create:
`doc/sprint1/requirements-baseline-v1.md`

### 6.1 What "baseline" means here
Requirements Baseline v1.0 is the set of requirements your team is prepared to accept for the current stage of the project.

Accepted does not mean permanently correct or fully validated. It means that the requirement is sufficiently understood, justified, and reviewed to serve as the current reference point for subsequent work.

Later sprints may change the baseline through an explicit change process.

### 6.2 Expected scope
The baseline should normally contain approximately 25–40 atomic requirements.

It should include a meaningful mixture such as:
- approximately 2–4 business requirements/goals;
- approximately 5–8 stakeholder requirements;
- at least 15 functional/system requirements;
- at least 5 preliminary quality requirements and/or constraints.

These are guidelines rather than a reason to manufacture unnecessary requirements. A smaller or larger set may be acceptable if the team can justify the scope.

Detailed quantitative treatment of quality requirements will be strengthened in Sprint 2.

### 6.3 Requirement identifiers
Use stable identifiers such as:
- `BR-001` Business requirement
- `SR-001` Stakeholder requirement
- `FR-001` Functional/system requirement
- `QR-001` Quality requirement
- `CON-001` Constraint

Once an identifier has been used, do not silently reuse it for a different requirement.

### 6.4 Required metadata
For every baseline requirement, record:
- ID;
- concise title;
- requirement statement;
- type;
- source/evidence;
- stakeholder or goal served;
- rationale;
- priority;
- confidence level (high, medium, or low);
- current status;
- acceptance/verification note;
- dependencies where known;
- related scenario/use case where applicable;
- GitHub Issue link.

### 6.5 Requirement quality expectations
Requirements should, as appropriate, be:
- necessary;
- understandable;
- atomic;
- unambiguous enough for the current stage;
- feasible;
- internally consistent;
- implementation-independent unless a genuine constraint requires otherwise;
- verifiable or associated with a clear verification idea;
- traceable to an origin and rationale.

Avoid statements such as:
> The application shall be fast, intuitive, secure, and easy to maintain.

This combines several different quality concerns and provides no useful criterion for deciding whether they are satisfied.

### 6.6 Preserve rejected and changed requirements
Do not delete Sprint 0 Issues simply because the team no longer accepts them.

If a candidate requirement is rejected, split, merged, or replaced:
- update its status;
- explain why;
- link to replacement requirements where applicable;
- preserve the history.

Requirements Engineering includes understanding why decisions changed.

---

## 7. SCENARIOS, USER STORIES, USE CASES, AND ACCEPTANCE CRITERIA

Create:
`doc/sprint1/scenarios-use-cases.md`

### 7.1 User stories
Create approximately 8–12 user stories representing important user-facing capabilities.

Use a consistent form such as:
> As a [role], I want [capability] so that [benefit].

Each story must link to one or more baseline requirements. User stories do not replace system requirements; they provide a stakeholder-centered view.

### 7.2 Detailed use cases/scenarios
Document at least three detailed use cases or scenarios covering at least two stakeholder roles.

Each should contain, where relevant:
- use-case/scenario ID and name;
- primary actor;
- goal;
- trigger;
- preconditions;
- main success flow;
- alternative flows;
- exception/failure flows;
- postconditions;
- linked requirements;
- open questions.

At least one non-happy-path flow should be considered for each detailed use case.

### 7.3 Acceptance criteria
Provide clear, testable acceptance criteria for at least 10 high-priority user stories or functional requirements.

You may use structured bullets or Given/When/Then format.

Good acceptance criteria should clarify observable behavior, not repeat the requirement using different words.

**Example:**
> **Given** an authenticated student with no registration hold,  
> **When** the student submits a request for an open course section,  
> **Then** the system records the registration and displays the updated schedule.

Where the expected behavior depends on an unresolved policy or assumption, identify the uncertainty rather than inventing a rule.

---

## 8. REQUIREMENTS MODELS

Create:
```text
doc/sprint1/models/
├── README.md
├── context-v2.[source/export]
├── domain-model.[source/export]
└── behavioral-model.[source/export]
```

### 8.1 Updated context model
Revise the Sprint 0 context model if elicitation changed actors, external systems, flows, or boundary decisions.

### 8.2 Domain/conceptual model
Create a conceptual/domain model showing important domain concepts and relationships.

The model should help clarify terminology and requirements. It should not be a software class design diagram containing implementation classes, controllers, repositories, database tables, or framework details unless those items genuinely exist in the problem domain.

### 8.3 Behavioral model
Create at least one appropriate behavioral model for an important scenario. Suitable choices include:
- activity diagram;
- state-machine diagram;
- sequence/interaction model at a requirements level;
- another instructor-approved behavioral representation.

Choose the model because it exposes behavior, states, events, responsibilities, or missing requirements - not because the course requires "some UML."

### 8.4 models/README.md
For each model, explain briefly:
- what question the model addresses;
- which requirements/scenarios it relates to;
- what the team learned from creating it;
- any inconsistency or missing requirement the model exposed.

Models and textual requirements must agree. If they do not, resolve the conflict or explicitly document it as unresolved.

---

## 9. TRACEABILITY

Create:
`doc/sprint1/traceability.md`

Build a lightweight traceability structure connecting important requirements artifacts.

At minimum, every baseline requirement must trace backward to a source, evidence item, assumption, stakeholder need, or business goal.

High-priority functional requirements should also trace forward to relevant scenarios/use cases and acceptance criteria.

A table may use columns such as:

| Requirement | Source/Evidence | Stakeholder/Goal | Scenario/Use Case | Acceptance Criteria | Issue |
| :--- | :--- | :--- | :--- | :--- | :--- |
| FR-001 | ELIC-02 | SR-003 | UC-01 | AC-01 | #27 |

Traceability is not useful merely because links exist. The links should help answer questions such as:
- Why does this requirement exist?
- Who needs it?
- What evidence supports it?
- Where is the behavior explained?
- How would we determine whether it is satisfied?

---

## 10. GITHUB ISSUES AND PROJECT TRACKING

GitHub continues to serve as the project's lightweight requirements-management environment.

### 10.1 Requirement Issues
Every requirement in Baseline v1.0 must have a corresponding GitHub Issue.

Recommended Issue title:
`[FR-012] Search available course sections`

The Issue should agree with the baseline document and contain or link to its important metadata.

### 10.2 Required labels
Continue the Sprint 0 labels and add:
- `baseline:v1`
- `confidence:high`
- `confidence:medium`
- `confidence:low`
- `evidence:direct`
- `evidence:documented`
- `evidence:analogy`
- `evidence:simulation`
- `evidence:assumption`

Use only the evidence labels that apply.

### 10.3 Status expectations
By the end of Sprint 1:
- Baseline v1.0 requirements should normally be `status:accepted`;
- unresolved candidates may remain `status:candidate` and should not appear in the baseline as accepted requirements;
- rejected requirements remain visible with `status:rejected` and rationale;
- `needs:validation` may remain on accepted requirements that have not yet been validated.

Accepted is not the same as validated.

### 10.4 GitHub Project board
Update the board so that its status reflects the actual repository state. Do not leave all Issues in one column simply to satisfy the setup requirement.

### 10.5 Branches and pull requests
This course does not require one branch per requirement.

However, the Sprint 1 baseline must be integrated through at least one meaningful pull request that:
- identifies the Sprint 1 artifacts being baselined;
- summarizes important changes from Sprint 0;
- references relevant Issues;
- receives review from at least one teammate who was not the sole author of the changes;
- resolves review comments before merge where appropriate.

The purpose is peer review and visible engineering history, not Git ceremony.

Do not delete evidence needed for marking while the sprint is being assessed.

---

## 11. REQUIREMENTS QUALITY REVIEW

Create:
`doc/sprint1/quality-review.md`

Before declaring Baseline v1.0 complete, inspect it systematically.

### 11.1 Review questions
Review each requirement for relevant issues such as:
- unclear terminology;
- ambiguity;
- multiple requirements combined into one statement;
- missing conditions or exceptions;
- unverifiable wording;
- unnecessary implementation/design decisions;
- missing source or rationale;
- conflict with another requirement;
- duplicate requirement;
- infeasible or questionable assumption;
- scope inconsistency;
- missing dependency;
- inconsistent identifiers or terminology.

### 11.2 Review participation
At least two team members must participate meaningfully in the quality review. Where practical, a requirement should be reviewed by someone other than its primary drafter.

### 11.3 Findings and disposition
For each significant finding, record:
- finding ID;
- affected requirement/artifact;
- defect/issue type;
- severity or importance;
- reviewer;
- proposed correction;
- disposition: accepted, rejected, deferred, or needs clarification;
- final action/link.

Do not invent defects to reach a target count. A review with few findings can be credible if the review method and evidence are strong.

---

## 12. PROTOTYPE REFINEMENT

Update the Sprint 0 low-fidelity prototype only as needed to support elicitation and requirements clarification.

Place the current artifact and explanation under:
`doc/sprint1/prototype/`

Update `prototype/README.md` to state:
- what changed since Sprint 0;
- which requirements or scenarios the prototype represents;
- which elicitation questions it helped investigate;
- what assumptions remain;
- what must still be validated later.

A polished or fully implemented interface does not receive extra credit.

---

## 13. DECISION LOG, RETROSPECTIVE, AND AI USE

### 13.1 decisions.md
Continue the decision log in:
`doc/sprint1/decisions.md`

Record important Sprint 1 decisions, especially decisions involving:
- scope;
- requirement acceptance/rejection;
- conflicting evidence;
- alternative interpretations;
- model choices;
- priority;
- unresolved assumptions.

Include links to affected requirements and artifacts where practical.

### 13.2 retrospective.md
Create:
`doc/sprint1/retrospective.md`

After completing the sprint, record:
- participants;
- what RE practices worked well;
- what produced weak or misleading information;
- important unfinished work;
- recurring communication/review problems;
- one or more practices the team will continue;
- one or more practices the team will change in Sprint 2;
- the most important requirements uncertainty still remaining.

A retrospective is not a list of compliments. It should identify concrete process improvements.

### 13.3 ai-use.md
Create or update:
`doc/sprint1/ai-use.md`

Record substantive generative-AI use, including:
- tool/model;
- purpose;
- relevant prompt or concise prompt summary;
- output used;
- output rejected/corrected;
- verification performed.

AI may help generate questions, alternatives, candidate requirements, defect hypotheses, or model ideas where course policy permits. AI output is not stakeholder evidence and must not be cited as though it establishes domain facts.

If no AI was used, state that clearly.

---

## 14. REQUIRED SPRINT 1 REPOSITORY STRUCTURE

A typical Sprint 1 submission will resemble:

```text
doc/
├── sprint0/
│   └── preserved Sprint 0 submission ...
└── sprint1/
    ├── sprint0-feedback.md
    ├── sprint1-plan.md
    ├── elicitation-plan.md
    ├── elicitation-evidence.md
    ├── elicitation-synthesis.md
    ├── evidence/
    ├── vision-scope.md          # revised/current where needed
    ├── stakeholders.md          # revised/current where needed
    ├── context.md               # revised/current where needed
    ├── glossary.md              # revised/current where needed
    ├── personas.md              # if materially revised
    ├── requirements-baseline-v1.md
    ├── scenarios-use-cases.md
    ├── traceability.md
    ├── quality-review.md
    ├── decisions.md
    ├── retrospective.md
    ├── ai-use.md
    ├── models/
    │   ├── README.md
    │   ├── context-v2.*
    │   ├── domain-model.*
    │   └── behavioral-model.*
    └── prototype/
        ├── README.md
        └── prototype artifact(s) ...
```

The exact diagram source/export file extensions may differ.

---

## 15. SUBMISSION RULES

1. Submit through the assigned GitHub Classroom team repository.
2. Sprint 1 deliverables must be under `doc/sprint1/` unless the handout explicitly says otherwise.
3. The repository state at the deadline is the submitted state.
4. Preserve the previously marked Sprint 0 snapshot.
5. Every Baseline v1.0 requirement must correspond to a GitHub Issue.
6. Important diagrams must have a repository-viewable export such as PNG, SVG, or PDF if the source format is not directly viewable.
7. All external links used as evidence must be accessible to the teaching team where reasonably possible.
8. Do not fabricate stakeholder interviews, observations, policies, user quotations, or other evidence.
9. Do not upload private/sensitive information or recordings without appropriate permission.
10. Do not delete branches, Issues, pull requests, review comments, or history needed for marking while marking is in progress.
11. All work must comply with course academic-integrity and AI-use policies.

---

## 16. HOW SPRINT 1 WILL BE EVALUATED

Sprint 1 is worth 5% of the final course grade. The detailed rubric is provided separately.

Evaluation emphasizes:

- **Elicitation quality**
  - Did the team identify genuine information gaps?
  - Were techniques chosen for a reason?
  - Is evidence distinguished from interpretation and assumption?
  - Did elicitation materially refine the team's understanding?

- **Requirements quality**
  - Is Baseline v1.0 appropriately scoped?
  - Are requirements atomic, understandable, justified, and traceable?
  - Are important requirements associated with acceptance/verification ideas?
  - Did the team preserve and explain rejected/changed candidates?

- **Analysis and modeling**
  - Do scenarios and models reveal behavior and domain structure?
  - Are textual and visual artifacts consistent?
  - Did modeling expose any missing or conflicting requirements?

- **Engineering discipline**
  - Is there meaningful traceability?
  - Does GitHub reflect the true requirements state?
  - Was the baseline reviewed before acceptance?
  - Are decisions and uncertainties visible?

- **Communication**
  - Can an instructor/TA understand the current requirements state without reconstructing it from scattered files?
  - Are diagrams readable and links functional?
  - Is the documentation concise and internally consistent?

---

## 17. SPRINT 1 CHECKLIST

Before submission, verify that you have:
- [ ] `sprint0-feedback.md`
- [ ] `sprint1-plan.md`
- [ ] `elicitation-plan.md`
- [ ] at least 3 elicitation activities using at least 2 techniques
- [ ] at least 1 elicitation activity grounded in observable/documented evidence
- [ ] `elicitation-evidence.md` + any appropriate supporting evidence
- [ ] `elicitation-synthesis.md`
- [ ] revised foundation artifacts where necessary
- [ ] `requirements-baseline-v1.md`
- [ ] approximately 25–40 justified baseline requirements
- [ ] stable requirement IDs
- [ ] GitHub Issue for every baseline requirement
- [ ] approximately 8–12 linked user stories
- [ ] at least 3 detailed use cases/scenarios
- [ ] acceptance criteria for at least 10 high-priority stories/functional requirements
- [ ] updated context model
- [ ] domain/conceptual model
- [ ] behavioral model
- [ ] `models/README.md`
- [ ] `traceability.md`
- [ ] updated GitHub labels/statuses/Project board
- [ ] meaningful baseline pull request with teammate review
- [ ] `quality-review.md`
- [ ] updated prototype + `prototype/README.md`
- [ ] `decisions.md`
- [ ] `retrospective.md`
- [ ] `ai-use.md`
- [ ] all important links and exported diagrams are accessible
- [ ] the team has checked cross-document consistency

---

## 18. WHAT HAPPENS NEXT

Sprint 1 establishes Requirements Baseline v1.0, but the course is not finished with requirements.

In Sprint 2 you will deepen analysis by:
- developing goal-oriented requirements models;
- refining domain and behavioral models;
- engineering measurable quality requirements;
- analyzing dependencies and conflicts;
- prioritizing requirements systematically;
- negotiating trade-offs;
- developing a more defensible release/requirements plan;
- strengthening traceability and rationale.

A strong Sprint 1 baseline is therefore not the baseline that never changes. It is the baseline whose assumptions, evidence, rationale, and links make later change understandable and manageable.