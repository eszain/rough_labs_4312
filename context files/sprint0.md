EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

EECS4312 - Software Requirements Engineering

Course Project - Requirements Sprint 0: Project Discovery & Scope

Course code: EECS4312
Institution: York University
Term: Fall 2026
Sprint period: September 9-27, 2026
Requirements Sprint 0 due: Sunday, September 27, 2026, 11:59 PM
Weight: 2% of final course grade
Submission: GitHub Classroom team repository
Scheduled project-support lab(s): September 10, September 17, September 24
Project approval checkpoint: Target approval during the September 17 lab; unresolved proposals
should be revised by the September 24 lab.

PREFACE

A major component of this course is a semester-long team project in which you will apply
Requirements Engineering (RE) techniques to a software-intensive system of your team’s choice.

You will work in teams of 3-4 students for the remainder of the semester. The purpose of the project
is not to build the largest or most technically impressive application. The product being assessed is
your requirements engineering work: how well you identify the problem, understand
stakeholders, discover and refine requirements, model the system, make trade-offs, validate
requirements, manage change, and justify engineering decisions.

Requirements Sprint 0 is the discovery and framing stage. Your goal is to establish a credible
problem, define an initial scope, identify the people and systems affected, create a preliminary
requirements backlog, and set up a disciplined team process in GitHub Classroom.

The deliverables may appear lighter than a programming sprint, but they require substantial
thinking. Weak problem framing in Sprint 0 will make later requirements work much harder.
Strong teams will be concise, specific, and explicit about what they know, what they infer, and what
they are assuming.

1. TEAM FORMATION

1.1 Team size

Teams must contain 3 or 4 students.

Once a team is approved, you should expect to remain with that team for the semester. Team
changes will be allowed only in exceptional circumstances and require instructor approval.

Page 1

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

1.2 Team expectations

The project assumes that team members contribute approximately comparable effort over the
semester. A team should not depend on one member doing most of the work.

Before joining a team, discuss:

•

•

•

•

•

•

•

your target level of effort and grade expectations;

typical weekly availability;

preferred communication method;

expected response time;

how decisions will be made;

how disagreements will be handled;

how work will be distributed and reviewed.

These agreements must be documented in doc/sprint0/team-agreement.md.

2. DECLARING YOUR TEAM AND PROJECT

Your team must:

1.

2.

3.

4.

5.

6.

7.

accept the GitHub Classroom team assignment;

create a meaningful project/team name;

complete doc/sprint0/TEAM.md;

complete and agree to doc/sprint0/team-agreement.md;

create the GitHub Project board used for requirements tracking;

create the required labels described later in this handout;

submit a project proposal suitable for Requirements Engineering.

Do not place private phone numbers or other unnecessary personal information in the repository.
The repository should contain only information needed for the course project.

3. PROJECT SELECTION

3.1 Student-selected topic

Your team chooses its own project topic, but instructor approval is required.

The project should describe a software-intensive system that solves a meaningful problem for
identifiable users or stakeholders. A project proposal should begin with the problem, not with a
technology stack.

Poor framing:

We will build a React/Node application with AI features.

Page 2

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

Better framing:

University students working in large project teams have difficulty identifying unresolved
requirements decisions and understanding how later changes affect earlier commitments.
We propose a collaborative requirements workspace that records requirements, rationale,
dependencies, and validation evidence.

3.2 Suitability criteria

A suitable project must:

•

•

•

•

•

•

•

•

•

•

address a non-trivial problem rather than merely implement a familiar CRUD application;

have at least three meaningful stakeholder roles;

contain potentially different or conflicting stakeholder goals;

have a clear system boundary and interactions with people and/or external systems;

support enough functionality for approximately 25-40 well-formed requirements by the
middle of the term;

contain meaningful quality requirements such as security, privacy, performance, reliability,
usability, accessibility, maintainability, or safety;

permit prioritization and trade-off decisions;

permit a meaningful requirements change later in the semester;

support a small prototype that can be used for validation;

be feasible to analyze within one semester.

Projects do not need access to real confidential data. Synthetic or fictional data is acceptable.

3.3 Projects that are usually too weak

The following are usually unsuitable unless the team can demonstrate unusual requirements
complexity:

•

•

•

•

•

•

a basic calculator;

a simple to-do list;

a static portfolio website;

a basic weather viewer;

a straightforward CRUD inventory application with one user role;

a clone of an existing app with no distinct stakeholder problem.

4. GITHUB CLASSROOM AND REQUIREMENTS TRACKING

GitHub will be used as a lightweight requirements-management environment.

4.1 Repository organization

All Sprint 0 deliverables must be placed under:

doc/sprint0/

Page 3

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

The starter repository contains templates. You may add files, diagrams, or supporting material, but
do not rename required files without permission.

4.2 GitHub Issues

In Sprint 0, GitHub Issues represent candidate requirements or important requirements
questions. These are preliminary and are expected to change.

Every candidate requirement Issue should include, when known:

•

•

•

•

•

•

•

•

•

an identifier;

requirement statement or question;

type;

source or origin;

rationale;

priority;

acceptance/fit idea;

dependencies or related requirements;

unresolved questions.

Do not invent evidence. If the source is your team’s assumption, say so explicitly.

4.3 Required labels

Create at least the following labels:

type:business
type:stakeholder
type:functional
type:quality
type:constraint

status:candidate
status:accepted
status:rejected

priority:must
priority:should
priority:could

needs:clarification
needs:validation

At Sprint 0, most requirements should still have status:candidate.

4.4 GitHub Project board

Create a project board with, at minimum, these states:

Page 4

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

Candidate -> Analyzing -> Accepted -> Validated -> Changed/Retired

You are not expected to have validated requirements in Sprint 0. The board establishes the
workflow that will be used later.

5. REQUIRED DELIVERABLES

All deliverables below are required unless explicitly stated otherwise.

5.1 TEAM.md

Identify:

•

•

•

•

•

•

project/team name;

team members;

school email addresses;

GitHub usernames;

tutorial/lab section if applicable;

primary team communication channel.

Keep this document factual and concise.

5.2 team-agreement.md

Document the team’s working agreement, including:

•

•

•

•

•

•

•

•

•

expected weekly contribution;

meeting frequency;

communication method and expected response time;

decision-making method;

approach to missed deadlines;

conflict-resolution process;

document/review responsibilities;

procedure if a member becomes unavailable;

agreement on responsible use of AI tools.

All team members must indicate agreement by adding their names and the date to the file.

5.3 vision-scope.md

Target length: approximately a 3-5 minute read.

Page 5

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

This is the most important Sprint 0 narrative document. It must allow a reader unfamiliar with your
project to understand what problem you intend to investigate.

Include:

1.

Problem statement - what problem exists today?

2. Motivation/value - why is the problem worth solving?

3.

4.

Project objectives - what outcomes should improve?

In scope - what your proposed system is expected to address.

5. Out of scope - what you deliberately will not address.

6. Major stakeholder groups - who is affected?

7.

8.

9.

Representative scenarios - 2-4 short examples of intended use.

Success indicators - how could you later tell whether the solution is useful?

Key assumptions/unknowns - what is currently uncertain?

Avoid implementation detail unless it represents an actual constraint.

5.4 stakeholders.md

Identify at least three meaningful stakeholder roles.

For each stakeholder, document:

•

•

•

•

•

•

•

•

•

role/name;

interest in the system;

goals;

responsibilities;

information or services needed;

concerns/risks;

influence or decision power;

likely conflicts with other stakeholders;

how the team’s knowledge about this stakeholder was obtained.

Include a stakeholder map or another visual representation of stakeholder relationships.

Because a real stakeholder interview is not required, clearly distinguish between:

•

•

•

facts supported by public/existing evidence;

analogies to existing systems;

assumptions created by the team.

Unsupported assumptions must not be presented as established facts.

Page 6

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

5.5 existing-solutions.md

Target length: approximately a 2-4 minute read.

Identify at least two existing products, services, processes, or analogous systems that address
part of the same problem.

For each, discuss:

•

•

•

•

•

what problem it addresses;

who appears to use it;

useful capabilities;

limitations relevant to your proposed stakeholders;

lessons for your own requirements work.

This is not a marketing comparison. The purpose is to improve your understanding of the problem
domain and avoid rediscovering obvious requirements.

Include links/references where appropriate.

5.6 context.md

Define the system context and boundary.

Include:

•

•

•

•

•

•

•

•

a context diagram;

the system under consideration;

external actors/stakeholders;

external software/hardware systems;

major information or interaction flows;

explicit system-boundary decisions;

assumptions about the environment;

dependencies on external services or policies.

The diagram may be created with Mermaid, draw.io, Lucidchart, PlantUML, or another suitable tool.
If the source format is not directly viewable in GitHub, also export a PDF/PNG/SVG version.

The diagram must be readable without zooming excessively and must agree with the accompanying
text.

5.7 glossary.md

Create an initial domain glossary containing approximately 10-20 important terms.

Page 7

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

Each entry should define the term in the context of your project. Include acronyms and domain
terms that could otherwise be interpreted in more than one way.

The glossary should reduce ambiguity. Do not define obvious general computing terms merely to
increase the count.

5.8 requirements-backlog.md and GitHub Issues

Create an initial backlog of approximately 15-25 candidate requirements. This is not yet your
requirements baseline.

The backlog should contain a meaningful mixture of:

•

•

•

•

•

business/stakeholder requirements;

functional requirements or user stories;

quality requirements;

constraints;

unresolved requirements questions where appropriate.

For each backlog item include:

•

•

•

•

•

•

•

•

•

requirement/Issue ID;

short title;

current statement;

type;

stakeholder/source;

rationale;

preliminary priority;

status;

link to the corresponding GitHub Issue.

At least 15 candidate requirements must be represented as GitHub Issues.

The strongest submissions will demonstrate breadth and insight, not simply produce many
superficial requirements.

Do not assume that all Sprint 0 requirements are correct. Later sprints are expected to refine, split,
merge, reject, and add requirements.

5.9 personas.md

Create 2-3 provisional personas or user profiles representing important user categories.

Each should include only details that help explain likely interactions with the system, such as:

•

role/context;

Page 8

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

•

•

•

•

•

•

relevant experience or domain knowledge;

goals;

frustrations or constraints;

technology comfort where relevant;

accessibility or environmental considerations where relevant;

representative system tasks.

Avoid irrelevant demographic decoration. Do not invent sensitive personal details.

Because these personas may be based partly on assumptions, label them as provisional and state
what evidence or assumptions support them.

5.10 prototype/

Create a very low-fidelity visual representation of at least one important scenario.

Suitable artifacts include:

•

•

•

•

•

wireframes;

storyboard;

screen-flow sketch;

command-line interaction mockup;

clickable mockup if easily available.

At this stage, the purpose is to expose assumptions and clarify the user journey. Visual polish is not
required and will not earn additional marks.

Place the artifact(s) under doc/sprint0/prototype/ and explain them in prototype/README.md.

5.11 process.md

Target length: approximately a 2-4 minute read.

Explain how the team will carry out Requirements Engineering work.

Address:

•

•

•

•

•

•

•

•

team roles/responsibilities for Sprint 0;

how requirements decisions are made;

how disagreements are resolved;

how candidate requirements are prioritized;

how GitHub Issues/Projects will be maintained;

how documents/models are reviewed before submission;

meeting frequency;

what the team intends to improve in Sprint 1.

Page 9

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

Do not merely repeat the team agreement. team-agreement.md defines expectations; process.md
explains the engineering workflow.

5.12 decisions.md

Maintain a lightweight decision log.

For every important scope or requirements decision record:

•

•

•

•

•

•

•

•

decision ID;

date;

question/decision;

alternatives considered;

decision made;

rationale;

affected requirements/artifacts;

unresolved consequences, if any.

Sprint 0 should normally contain at least 3 meaningful decisions.

5.13 ai-use.md

Submit this file even if your team did not use generative AI.

If AI was used, record substantive uses including:

•

•

•

•

•

•

tool/model;

purpose;

relevant prompt or concise prompt summary;

how the output was checked;

what was accepted;

what was rejected or corrected.

If no AI was used, state that clearly.

AI-generated material is not stakeholder evidence. A language model may suggest questions, risks,
requirements, or alternatives, but those outputs remain untrusted hypotheses until the team
justifies or validates them.

6. PROJECT APPROVAL

The instructor/TA may request revision of a proposal that is:

•

too small;

Page 10

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

•

•

•

•

•

•

•

primarily an implementation exercise;

too similar to a basic tutorial application;

missing meaningful stakeholder diversity;

dependent on inaccessible confidential information;

ethically inappropriate for a course project;

impossible to analyze within the semester;

unlikely to support meaningful quality requirements, trade-offs, validation, or change
analysis.

Approval of Sprint 0 does not imply that the initial requirements are correct. It only confirms that
the project is suitable for further RE work.

7. SUBMISSION RULES

1.

2.

3.

4.

5.

6.

7.

8.

9.

Submit through the assigned GitHub Classroom team repository.

Required files must be in doc/sprint0/.

The repository state at the deadline is the submitted state.

Commit early and often enough that the evolution of the work is visible.

Do not make one final repository dump immediately before the deadline.

Links to diagrams or external artifacts must be accessible to instructors/TAs.

Keep a viewable/exported copy of important diagrams in the repository.

Do not delete or rewrite repository history after submission while marking is in progress.

All submitted work must comply with course academic-integrity and AI-use policies.

8. HOW SPRINT 0 WILL BE EVALUATED

Sprint 0 is worth 2% of the final course grade. The detailed marking rubric is provided separately.

Evaluation emphasizes both content and communication.

Content

Your work should:

•

•

•

•

•

•

•

make sense as one coherent project;

demonstrate that the team understands the underlying problem;

distinguish evidence from assumptions;

contain meaningful stakeholders and scenarios;

establish a defensible scope;

contain a useful initial set of candidate requirements;

expose important uncertainties rather than hide them.

Page 11

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

Communication

Your work should:

•

•

•

•

•

•

be clear and concise;

use diagrams where they improve understanding;

use consistent terminology;

link related artifacts;

avoid unnecessary repetition;

allow an instructor/TA to understand the project without asking the team to explain every
document.

A large quantity of text does not imply high quality. If the same information can be communicated
more clearly with fewer words, do so.

9. SPRINT 0 CHECKLIST

Before submission, verify that the repository contains:

•

•

•

•

•

•

•

•

•

•

•

•

•

•

•

•

•

•

 ☐ TEAM.md

 ☐ team-agreement.md

 ☐ vision-scope.md

 ☐ stakeholders.md

 ☐ existing-solutions.md

 ☐ context.md + context diagram

 ☐ glossary.md

 ☐ requirements-backlog.md

☐

 at least 15 candidate requirement GitHub Issues

☐

 required GitHub labels

☐

 GitHub Project board

 ☐ personas.md

 ☐ prototype/README.md + prototype artifact(s)

 ☐ process.md

 ☐ decisions.md

 ☐ ai-use.md

☐

 all links accessible

☐

 team has reviewed the entire submission for consistency

10. WHAT HAPPENS NEXT

Sprint 0 creates a candidate understanding, not a frozen specification.

Page 12

EECS4312 - Software Requirements Engineering | Requirements Sprint 0 | Fall 2026

In later Requirements Sprints you will:

•

•

•

•

•

•

•

•

•

•

plan and perform deeper elicitation;

refine and restructure requirements;

build goal, domain, and behavioral models;

define measurable quality requirements;

prioritize and negotiate requirements;

validate the requirements and prototype;

establish traceability;

receive and analyze a significant change request;

revise the baseline;

produce a final integrated requirements package and recorded project presentation.

Expect your Sprint 0 artifacts to change. Discovering that an early assumption or requirement was
wrong is not a project failure; recognizing and correcting it is evidence that Requirements
Engineering is working.

Page 13

