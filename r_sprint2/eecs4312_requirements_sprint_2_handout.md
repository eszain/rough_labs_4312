# EECS4312 – Software Requirements Engineering

## Course Project – Requirements Sprint 2: Analysis, Quality, Prioritization & Negotiation

* **Course Code:** EECS4312  
* **Institution:** York University  
* **Term:** Fall 2026  
* **Sprint Period:** October 26 – November 8, 2026  
* **Requirements Sprint 2 Due:** Sunday, November 8, 2026, 11:59 PM  
* **Weight:** 8% of final course grade  
* **Submission:** GitHub Classroom team repository  
* **Scheduled Project-Support Lab(s):** October 29, November 5  
* **Key Lab Activity:** November 5 prioritization and simulated stakeholder-negotiation exercise.

---

## Preface

Requirements Sprint 1 produced your team’s Requirements Baseline v1.0. Sprint 2 asks a harder question:

> **Are these the right requirements, at the right level of quality and priority, and can the team justify the trade-offs among them?**

In this sprint you will move beyond collecting and writing requirements. You will reason about goals, obstacles, conflicts, quality attributes, dependencies, value, risk, cost, and stakeholder trade-offs. The result will be a more mature Requirements Baseline v2.0.

This is not a feature-development sprint. You are not graded on story-point completion, source-code volume, or how many screens your prototype contains. You are graded on the quality of your analysis and on the engineering rationale behind changes to the requirements baseline.

A strong Sprint 2 submission will almost certainly change some Sprint 1 decisions. Requirements may be:

* Refined;
* Split or merged;
* Reprioritized;
* Constrained by quality requirements;
* Linked to goals;
* Modified because an obstacle or conflict was discovered;
* Rejected or retired;
* Added because analysis revealed a missing concern.

Changing a requirement for a defensible reason is good Requirements Engineering. Silently changing it without preserving the history is not.

---

## 1. Sprint 1 Continuity

### 1.1 Preserve Baseline v1.0
Do not overwrite the final Sprint 1 submission after marking is complete. Sprint 2 must make the evolution of the project visible.

Before beginning substantive Sprint 2 changes, ensure that the repository contains a stable record of Baseline v1.0. Your team should create a Git tag such as:
```bash
requirements-baseline-v1.0
```
If your course repository policy prevents tags, preserve an equivalent immutable snapshot and document the method used.

### 1.2 Respond to Sprint 1 Feedback
Create:
```text
doc/sprint2/sprint1-feedback.md
```
For each important instructor/TA comment, record:
* Feedback received;
* Action taken;
* Affected requirement(s) or artifact(s);
* Whether the issue changes the baseline;
* Link to the relevant Issue, commit, pull request, or file where practical;
* Unresolved feedback and the reason it remains unresolved.

*Do not merely copy feedback. Show what changed because of it.*

### 1.3 Review the Sprint 1 Retrospective
Your Sprint 2 planning should explicitly consider the Sprint 1 retrospective, especially:
* Unresolved requirements uncertainty;
* Weak evidence;
* Unvalidated assumptions;
* Terminology problems;
* Model inconsistencies;
* Requirements that were difficult to specify or verify.

These should become analysis priorities in Sprint 2.

---

## 2. Sprint 2 Planning

Create:
```text
doc/sprint2/sprint2-plan.md
```

Document:
* Participants;
* Sprint 2 goal;
* The major uncertainties and analysis questions to be addressed;
* Goal-modeling responsibilities;
* Quality-requirements responsibilities;
* Prioritization responsibilities;
* Negotiation roles;
* Dependency-analysis responsibilities;
* Review assignments;
* Internal deadlines;
* Expected risks or blockers.

The plan should assign Requirements Engineering work, not programming tasks.

**Examples of appropriate Sprint 2 tasks include:**
* Refine business goal G-03 into operational subgoals;
* Analyze obstacles that can prevent SR-006 from being satisfied;
* Define a measurable response-time requirement for search;
* Evaluate privacy versus convenience trade-offs for persistent login;
* Perform weighted prioritization of candidate release requirements;
* Map dependencies among FR-012, FR-018, QR-004, and CON-003;
* Prepare stakeholder viewpoints for the negotiation exercise.

*Every team member must contribute meaningfully to the analysis.*

---

## 3. Goal-Oriented Requirements Analysis

Create:
```text
doc/sprint2/goals.md
doc/sprint2/models/goal-model.[source/export]
```

### 3.1 Purpose
Requirements should exist because they help satisfy stakeholder or organizational goals. A list of features without a defensible connection to goals is difficult to prioritize, negotiate, or validate. Sprint 2 therefore requires a goal-oriented analysis.

### 3.2 Minimum Expected Scope
As a guideline, the analysis should contain:
* At least 3 important high-level stakeholder/business goals;
* Approximately 12 or more meaningful goals/subgoals across the model;
* At least 2 OR-refinements or alternative ways of satisfying a goal;
* Meaningful AND-refinements where all subgoals are jointly necessary;
* Responsibility/ownership where appropriate;
* Links from important operational goals to requirements in the baseline.

*Do not add artificial goals simply to reach a number. The purpose is sufficient depth to support reasoning.*

### 3.3 Modeling Approach
You may use a lightweight KAOS-style goal model, an **i\*-inspired model**, or another instructor-approved goal-oriented notation.

At minimum the model should make clear:
* Goals;
* Refinements/decomposition;
* Alternatives;
* Stakeholder or actor responsibility where relevant;
* Links to important requirements.

### 3.4 Required Written Analysis
In `goals.md`, explain:
* The major goals and why they matter;
* Which stakeholders own or care about them;
* How goals were refined;
* Where alternatives exist;
* Which requirements operationalize important goals;
* Goals not yet adequately supported by requirements;
* Requirements that appear weakly justified by goals;
* Any important goal conflict discovered.

### 3.5 A Requirement Can Be Questioned
If the team discovers that a Sprint 1 requirement does not contribute meaningfully to any relevant stakeholder/business goal, do not force an artificial link. Instead ask whether the requirement should:
* Be justified differently;
* Be reframed;
* Be deprioritized;
* Or be removed from Baseline v2.0.

---

## 4. Obstacle and Conflict Analysis

Create:
```text
doc/sprint2/obstacles-conflicts.md
```

### 4.1 Obstacles
Identify and analyze at least 4 significant obstacles that could prevent important goals or requirements from being satisfied.

An obstacle may involve, for example:
* Unavailable or incorrect information;
* User error;
* Conflicting policies;
* External-system failure;
* Resource or capacity limits;
* Misuse or abuse;
* Regulatory restrictions;
* Poor network/device conditions;
* Incompatible stakeholder expectations;
* Organizational process limitations.

For each obstacle record:
* Obstacle ID;
* Affected goal(s)/requirement(s);
* Scenario in which it occurs;
* Why it matters;
* Likely consequence;
* Mitigation, requirement refinement, or new requirement needed;
* Residual uncertainty.

*This is requirements analysis, not a full risk-management exercise. Numerical probability calculations are not required.*

### 4.2 Requirements and Goal Conflicts
Identify at least 3 meaningful conflicts or trade-offs.

Examples include:
* Security versus convenience;
* Privacy versus personalization;
* Performance versus cost;
* Auditability versus data minimization;
* Configurability versus simplicity;
* Strict validation versus user flexibility;
* Stakeholder A's automation goal versus stakeholder B's control goal.

For each conflict record:
* Conflict ID;
* Affected goals/requirements/stakeholders;
* Why the concerns cannot all be maximized simultaneously;
* Realistic alternatives;
* Information needed to choose among them;
* Whether the conflict will be resolved in the Sprint 2 negotiation exercise.

### 4.3 Effect on the Baseline
Obstacle/conflict analysis should lead to visible changes where justified, for example:
* Adding a missing exception requirement;
* Introducing a quality constraint;
* Revising a vague requirement;
* Separating conflicting behavior into policies;
* Reprioritizing a requirement;
* Recording a deliberate trade-off.

---

## 5. Quality Requirements

Create:
```text
doc/sprint2/quality-requirements.md
```

### 5.1 Quality is Part of the System Behavior
Statements such as:
> *"The system shall be fast."*  
> or  
> *"The interface shall be user-friendly."*

are not adequate quality requirements.

A useful quality requirement states what quality matters, under what conditions, to whom or what, and how satisfaction can be evaluated.

### 5.2 ISO/IEC 25010:2023
Use the product-quality characteristics from ISO/IEC 25010:2023 as a classification and elicitation aid, not as a checklist that requires every project to address every characteristic.

The current model includes:
* Functional suitability;
* Performance efficiency;
* Compatibility;
* Interaction capability;
* Reliability;
* Security;
* Maintainability;
* Flexibility;
* Safety.

*Select the characteristics that genuinely matter to your project.*

### 5.3 Minimum Expected Scope
Baseline v2.0 should normally contain approximately 8–12 meaningful quality requirements, covering at least 4 relevant quality characteristics.

At least 6 quality requirements should include a measurable or objectively assessable fit criterion.

*If a characteristic such as safety or compatibility is genuinely not relevant, do not manufacture a requirement simply to satisfy a category count.*

### 5.4 Quality Requirement Format
For each important quality requirement record:
* ID (`QR-nnn`);
* Quality characteristic;
* Stakeholder/goal served;
* Stimulus/event or situation;
* Operating conditions/environment;
* Affected system or function;
* Expected response/quality behavior;
* Measure or fit criterion;
* Rationale;
* Priority;
* Source/evidence or assumption;
* Linked functional requirements or scenarios;
* Proposed verification method;
* Uncertainty where applicable.

*A quality-attribute scenario format is encouraged.*

### 5.5 Example
* **Weak:**  
  `QR-004`: Search shall be fast.
* **Better:**  
  `QR-004`: Under the defined normal-load test profile, 95% of authenticated course-search requests shall return the first page of results within 800 ms measured at the service boundary.

*This is still incomplete if the team has not defined what normal load, service boundary, or the expected dataset means. Record those definitions or uncertainties.*

### 5.6 Do Not Invent Numbers Without Justification
A quantitative requirement is not automatically a good requirement.

If the team chooses a value such as 800 ms, 99.9%, or 5 minutes, document whether the value came from:
* Evidence;
* An external constraint;
* Comparison with a similar system;
* A stakeholder preference;
* Or a provisional team assumption.

*Unsupported precision is not evidence.*

### 5.7 Security, Privacy, Safety, and Regulatory Concerns
Where relevant, ensure the baseline contains explicit requirements for matters such as:
* Authentication/authorization;
* Confidentiality;
* Auditability;
* Consent;
* Data retention;
* Privacy/data minimization;
* Misuse/abuse prevention;
* Safety constraints;
* Regulatory or policy obligations.

If these are important to the project but absent from the baseline, Sprint 2 should correct that omission.

---

## 6. Requirements Prioritization

Create:
```text
doc/sprint2/prioritization.md
```

### 6.1 Why Priorities Need Evidence
A backlog in which everything is *Must* is not prioritized.

Prioritization should consider more than personal preference. Depending on the project, relevant factors may include:
* Stakeholder/business value;
* Urgency;
* Regulatory necessity;
* Risk reduction;
* Dependency;
* Expected implementation effort;
* Uncertainty;
* Quality impact;
* Differentiation from alternatives;
* Consequence of omission.

### 6.2 Stage A – Prioritization of the Full Baseline
Apply a simple, transparent method to all accepted Baseline v2.0 requirements. A suitable method is MoSCoW or another instructor-approved categorical scheme.

For every requirement, the priority must be defensible. *Must* should mean that there is a real reason the requirement cannot reasonably be deferred from the first plausible release or operational baseline.

### 6.3 Stage B – Analytical Prioritization of the Most Consequential Requirements
Select approximately 15–20 important or disputed requirements and apply a more analytical method, for example:
* Weighted scoring;
* Pairwise comparison;
* Cost-value analysis;
* $100 allocation combined with effort/risk;
* AHP-inspired comparison at an appropriate scale;
* Another instructor-approved method.

The analysis must use at least 3 explicit decision factors.

For each factor:
* Define what it means;
* Explain why it matters;
* Define the scale;
* Explain weighting if weights are used.

### 6.4 Effort Estimates are Uncertain
This is not a software-estimation assignment. Relative effort may be represented using coarse categories such as:
* Low / Medium / High
* Or a small relative scale.

If the team lacks enough design information to estimate effort confidently, record that uncertainty.

### 6.5 Sensitivity Check
Perform at least one small sensitivity analysis.

For example:
* Increase the weight of security;
* Reduce the weight of implementation effort;
* Prioritize one stakeholder's value more heavily;
* Treat one regulatory requirement as mandatory.

Explain whether the resulting ranking changes materially and what that tells the team.

### 6.6 Priority Set for a First Plausible Release
Based on the analysis, identify a Priority Set representing the requirements that should be satisfied in a first plausible release or operational baseline.

This is a requirements-scope decision, not an implementation commitment.

Document:
* Included requirements;
* Important deferred requirements;
* Mandatory dependencies;
* Known quality constraints;
* Unresolved priority questions.

---

## 7. Requirements Negotiation and Trade-Off Analysis

Create:
```text
doc/sprint2/negotiation.md
```

### 7.1 Purpose
Requirements conflicts are not resolved merely by choosing the loudest stakeholder or taking a majority vote. Engineering negotiation should make interests, alternatives, constraints, and trade-offs explicit.

Because this course does not require access to real external stakeholders, the negotiation exercise may use simulated stakeholder viewpoints. These viewpoints must be clearly labeled as simulations and grounded in the stakeholder goals, evidence, constraints, and assumptions already documented by the team.

### 7.2 Negotiation Preparation
Select at least 3 significant conflicts, trade-offs, or priority disputes.

For each, identify:
* Stakeholder roles represented;
* Each role’s goals/interests;
* Relevant requirements;
* Non-negotiable constraints;
* Preferred outcome;
* Acceptable alternatives;
* Likely concessions;
* Evidence or assumptions supporting the position.

### 7.3 Conduct the Negotiation
Hold a structured team negotiation meeting. Team members should represent different stakeholder viewpoints for at least part of the exercise.

Record:
* Participants and represented roles;
* Issue being negotiated;
* Alternatives considered;
* Important arguments/evidence;
* Concessions or compromises;
* Final decision;
* Dissent or unresolved concern;
* Affected requirements and priorities.

### 7.4 Decision Rationale
For every resolved negotiation issue, explain why the chosen outcome is preferred to the alternatives.

A statement such as *"the team voted 3–1"* is not sufficient engineering rationale.

### 7.5 Update the Baseline
Negotiation outcomes should be reflected in:
* Requirement statements;
* Priorities;
* Quality requirements;
* Constraints;
* Rationale;
* Decision log;
* GitHub Issues;
* Traceability.

---

## 8. Requirements Dependency and Interaction Analysis

Create:
```text
doc/sprint2/dependencies.md
doc/sprint2/models/requirements-dependency.[source/export]
```

### 8.1 Purpose
Requirements are rarely independent. A requirement may require another requirement, constrain it, conflict with it, refine it, or make it more valuable.

Understanding these relationships is essential for prioritization and later change-impact analysis.

### 8.2 Dependency Types
Use a small controlled set of relationship types. Suggested examples:
* `requires`
* `refines`
* `constrains`
* `conflicts-with`
* `enhances`
* `alternative-to`

You may use another set if it is clearly defined.

### 8.3 Expected Analysis
As a guideline, identify at least 12 meaningful dependency/interaction links involving a substantial subset of the baseline.

*Do not create meaningless links to reach a count.*

Provide either a dependency graph, matrix, or both. The representation should allow the reader to see important clusters and relationships.

Analyze:
* Requirements with many incoming/outgoing dependencies;
* Chains of dependency;
* Conflicting dependencies;
* Alternative requirements;
* Dependencies that affect priority;
* Dependencies that make a requirement impossible to defer;
* Cycles or suspicious relationships;
* Quality requirements that constrain several functional requirements.

### 8.4 Connection to Later Change Analysis
This dependency model will become a major input to Sprint 3 change-impact analysis. Build it so that it can actually support that task.

---

## 9. Requirements Baseline v2.0

Create:
```text
doc/sprint2/requirements-baseline-v2.md
doc/sprint2/baseline-change-summary.md
```

### 9.1 Baseline v2.0
Baseline v2.0 is the team's current accepted requirements set after goal analysis, quality analysis, prioritization, negotiation, and dependency analysis.

A typical project may now contain approximately 30–45 atomic requirements, including approximately 8–12 quality requirements, but the correct size depends on the project. Do not inflate the baseline to satisfy a number.

Every accepted requirement should include or link to appropriate metadata established in Sprint 1, including:
* Stable ID;
* Statement;
* Type;
* Source/evidence;
* Stakeholder/goal;
* Rationale;
* Priority;
* Confidence;
* Status;
* Verification/acceptance idea;
* Dependencies;
* Related scenarios/models;
* GitHub Issue.

Quality requirements should include the additional quality metadata described in Section 5.

### 9.2 `baseline-change-summary.md`
Summarize changes from Baseline v1.0 using categories such as:
* Added;
* Modified;
* Split;
* Merged;
* Reprioritized;
* Rejected;
* Retired;
* Unchanged but newly justified;
* Newly constrained by a quality requirement.

For significant changes explain the reason, for example:
* Goal analysis;
* Obstacle;
* Quality analysis;
* Conflict;
* Negotiation decision;
* Dependency;
* Instructor feedback;
* Corrected assumption.

### 9.3 Stable Identifiers
Do not renumber the entire baseline simply to make it look clean.

If `FR-014` is retired, keep the identifier retired. If it is split into `FR-031` and `FR-032`, preserve the relationship in the history.

---

## 10. Traceability v2

Create:
```text
doc/sprint2/traceability.md
```

Extend Sprint 1 traceability so that important requirements can be traced through analysis artifacts.

A useful chain may look like:
$$\text{Evidence} \rightarrow \text{Stakeholder Goal} \rightarrow \text{Requirement} \rightarrow \text{Quality Constraint} \rightarrow \text{Scenario} \rightarrow \text{Acceptance/Fit Criterion} \rightarrow \text{GitHub Issue}$$

Not every requirement needs every link type, but the traceability should answer relevant questions such as:
* Why does this requirement exist?
* Which goal does it support?
* Which evidence or assumption supports it?
* Which quality requirement constrains it?
* What depends on it?
* Which conflict or negotiation decision affected it?
* How could its satisfaction be evaluated?

At minimum:
* Every accepted requirement should trace to an origin and goal/rationale;
* Every quality requirement should link to relevant goals/functions/scenarios where applicable;
* High-priority requirements should link to acceptance or fit criteria;
* Important dependencies/conflicts should be visible;
* Negotiated changes should be traceable to the negotiation record/decision log.

---

## 11. GitHub Requirements Management

GitHub Classroom continues to serve as the project’s lightweight requirements-management environment.

### 11.1 Update Requirement Issues
Update every Issue affected by Sprint 2 analysis.

Do not create a second duplicate Issue merely because the requirement moved from Baseline v1.0 to Baseline v2.0.

Add or update:
* Goal links;
* Priority;
* Quality relationships;
* Dependency links;
* Conflict/negotiation references;
* Confidence;
* Status;
* Rationale;
* Verification/fit criterion.

### 11.2 Recommended Labels
Continue prior labels and add where useful:
* `baseline:v2`
* `priority:must`
* `priority:should`
* `priority:could`
* `priority:wont-now`
* `analysis:goal-linked`
* `analysis:conflict`
* `analysis:negotiated`
* `analysis:dependency`
* `quality:performance`
* `quality:security`
* `quality:reliability`
* `quality:interaction`
* `quality:maintainability`
* `quality:flexibility`
* `quality:safety`

*Do not create labels that are never used. A project with a smaller, well-controlled label set is preferable to dozens of meaningless labels.*

### 11.3 GitHub Project Board
The Project board should make the current requirements state understandable. At minimum the team should be able to filter or inspect requirements by:
* Status;
* Priority;
* Type;
* Baseline;
* Validation state where applicable.

*If GitHub Project custom fields are available, they may be preferable to excessive labels.*

### 11.4 Baseline v2.0 Pull Request
Integrate Baseline v2.0 through a meaningful pull request.

The PR must summarize:
* Major changes from v1.0;
* Goal/obstacle discoveries;
* Major new or revised quality requirements;
* Prioritization results;
* Negotiated changes;
* Major dependencies;
* Remaining unresolved concerns.

*At least one teammate who was not the sole author of the changes must review the PR.*

### 11.5 Create the v2.0 Baseline Tag
After the baseline PR is reviewed and merged, create:
```bash
requirements-baseline-v2.0
```
Do not move the tag later to conceal post-deadline changes.

---

## 12. Prototype Use in Sprint 2

A major prototype expansion is not required in Sprint 2.

However, the team may refine the prototype when doing so helps investigate or explain:
* An interaction/usability quality requirement;
* A workflow conflict;
* An alternative requirement;
* A security/privacy trade-off;
* An exception scenario;
* A negotiation decision.

If the prototype changes, update:
```text
doc/sprint2/prototype/README.md
```
Explain what requirements question the change helped answer.

*Visual polish and implementation complexity receive no extra credit.*

---

## 13. Decision Log, Retrospective, and AI Use

### 13.1 Decision Log
Create or continue:
```text
doc/sprint2/decisions.md
```
Record important Sprint 2 decisions, especially:
* Goal-refinement decisions;
* Quality thresholds;
* Assumptions behind quantitative values;
* Prioritization method/weights;
* Negotiation outcomes;
* Conflict resolutions;
* Requirement retirements;
* Priority changes;
* Unresolved disagreements.

*A useful entry records the alternatives considered and why the chosen option was preferred.*

### 13.2 Sprint 2 Retrospective
Create:
```text
doc/sprint2/retrospective.md
```
Record:
* Participants;
* What analysis practices worked well;
* What should change in Sprint 3;
* One requirement decision the team would handle differently if repeated;
* The most difficult trade-off in Sprint 2;
* The most important unresolved assumption;
* The part of Baseline v2.0 in which the team has least confidence;
* What the team expects to be most vulnerable to change.

*The final two items should directly inform Sprint 3 validation and change-impact work.*

### 13.3 AI Use
Update:
```text
doc/sprint2/ai-use.md
```
Follow the course AI policy.

AI may assist with tasks such as:
* Proposing candidate goal refinements;
* Identifying possible ambiguities;
* Generating alternative quality scenarios;
* Checking calculations in a prioritization table;
* Suggesting possible dependency relationships.

However, AI output is not stakeholder evidence and must not be presented as such.

**Do not let an AI system invent:**
* Stakeholder preferences;
* Quality thresholds;
* Legal/regulatory obligations;
* Negotiation outcomes;
* Project evidence.

*When AI materially influences a Sprint 2 decision, record the use and how the output was verified.*

---

## 14. Required Sprint 2 Repository Structure

At minimum, the Sprint 2 submission should contain:

```text
doc/
└── sprint2/
    ├── sprint1-feedback.md
    ├── sprint2-plan.md
    ├── goals.md
    ├── obstacles-conflicts.md
    ├── quality-requirements.md
    ├── prioritization.md
    ├── negotiation.md
    ├── dependencies.md
    ├── requirements-baseline-v2.md
    ├── baseline-change-summary.md
    ├── traceability.md
    ├── decisions.md
    ├── retrospective.md
    ├── ai-use.md
    ├── github-sprint2-setup.md
    ├── models/
    │   ├── goal-model.[source]
    │   ├── goal-model.[export]
    │   ├── requirements-dependency.[source]
    │   └── requirements-dependency.[export]
    └── prototype/
        ├── README.md
        └── [optional updated prototype artifacts]
```

*The exact diagram file format may vary. Always include an easily viewable exported version such as PDF, PNG, or SVG in addition to a proprietary/source format where practical.*

---

## 15. Submission Rules

1. Submit through the GitHub Classroom team repository.
2. Required Sprint 2 artifacts must be committed before the deadline.
3. Preserve Sprint 0 and Sprint 1 evidence needed for comparison.
4. Do not rewrite history to conceal late work.
5. Keep stable requirement IDs.
6. Do not silently delete rejected/retired requirements.
7. Ensure links in Markdown files and GitHub Issues work.
8. Ensure diagram exports can be viewed without proprietary software.
9. Create the `requirements-baseline-v2.0` tag only after the baseline review is complete.
10. Do not include private or sensitive information merely as evidence.
11. Where AI use must be disclosed, the disclosure is part of the submission.

---

## 16. How Sprint 2 Will Be Evaluated

* Sprint 2 is worth **8%** of the final course grade.
* The raw marking scheme is out of **100 marks** and will be scaled to the 8% course weight.

**The largest emphasis is placed on:**
* Goal-oriented reasoning;
* Measurable quality requirements;
* Defensible prioritization;
* Negotiation/trade-off analysis;
* Requirements dependencies;
* Coherent evolution from Baseline v1.0 to Baseline v2.0.

*A visually attractive diagram receives little value if the reasoning behind it is weak. Likewise, a complicated prioritization spreadsheet receives little value if the scales, weights, or conclusions are arbitrary.*

---

## 17. Sprint 2 Checklist

Before submission, verify that your team has:

- [ ] Preserved Baseline v1.0 and created/confirmed the v1.0 tag;
- [ ] Responded to Sprint 1 feedback;
- [ ] Documented the Sprint 2 plan;
- [ ] Built a meaningful goal model;
- [ ] Linked important goals to requirements;
- [ ] Analyzed at least four significant obstacles;
- [ ] Identified at least three meaningful conflicts/trade-offs;
- [ ] Produced approximately 8–12 quality requirements across at least four relevant quality characteristics;
- [ ] Made at least six quality requirements objectively measurable/assessable;
- [ ] Documented the origin/assumption behind numerical thresholds;
- [ ] Prioritized the full baseline using a simple method;
- [ ] Analytically prioritized approximately 15–20 important/disputed requirements;
- [ ] Performed at least one sensitivity check;
- [ ] Identified a defensible first-release Priority Set;
- [ ] Conducted and documented a simulated requirements negotiation;
- [ ] Analyzed important requirement dependencies/interactions;
- [ ] Produced Baseline v2.0;
- [ ] Documented the v1.0-to-v2.0 change summary;
- [ ] Extended traceability to goals, quality, conflicts, dependencies, and decisions;
- [ ] Updated GitHub Issues/Project state;
- [ ] Submitted Baseline v2.0 through a reviewed pull request;
- [ ] Created the `requirements-baseline-v2.0` tag after merge;
- [ ] Updated the decision log;
- [ ] Completed the Sprint 2 retrospective;
- [ ] Updated the AI-use record where required.

---

## 18. What Happens Next

Sprint 3 will treat Baseline v2.0 as the starting point for validation, inspection, traceability, and change-impact analysis.

You should expect the next sprint to challenge your current baseline with:
* Structured peer review;
* Validation evidence;
* Requirements defect disposition;
* Stronger traceability;
* One or more significant change requests;
* Impact analysis across requirements, goals, models, quality constraints, dependencies, and acceptance criteria.

*The dependency and rationale work completed in Sprint 2 should make that analysis possible.*