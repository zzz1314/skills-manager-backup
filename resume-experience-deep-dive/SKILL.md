---
name: resume-experience-deep-dive
description: >
  Build evidence-grounded resumes, self-introductions, experience cards,
  role-specific interview preparation, and interview reviews from resumes,
  JDs, chat logs, PDFs, images, and notes. Use for campus recruiting and career
  evidence mining when personal claims must remain verified and defensible.
---

# Resume Experience Deep Dive

Use this skill when a user wants to recover forgotten experience details, revise
resume project descriptions, build an interview case bank, or preserve useful
career evidence for later job applications. Also use it for job research,
structured interview preparation, group-interview preparation, and interview
reviews when the work must remain grounded in verified personal facts.

## Core Principle

Treat each personal claim as an evidence-backed unit:

`context + goal + personal action + constraint + result + proof`

The output should make the user's contribution clearer. It must not make the
experience larger, more senior, or more successful than the evidence supports.

## First Pass

1. Build a scoped file inventory before reading: current resume, target JD,
   confirmed experience library, directly relevant evidence, and the latest
   application materials. Do not scan unrelated workspace files by default.
2. Read the latest user-edited resume or source document first.
3. Separate user instructions from the document's content.
4. Inventory every experience, date, identity, action, result, metric, and
   named organization.
5. Preserve conflicts. Do not silently choose the more impressive version.
6. Keep a list of unresolved questions before drafting polished wording.

## Mode Routing

Use the entrypoint for ordinary evidence extraction, resume revision, and role
mapping. For interview preparation, resume-to-question mapping, mock-interview
design, or post-interview review, also read
[references/interview-operating-system.md](references/interview-operating-system.md).
That reference contains the detailed workflow for material cards, answer depth,
intent hypotheses, observation-based review, and recruiting-funnel diagnosis.

For a spoken self-introduction, opening pitch, or an answer to "tell me about
yourself", also read
[references/self-introduction-design.md](references/self-introduction-design.md).
Use it to select evidence, connect it to the role, control duration, and avoid
turning the answer into a spoken copy of the resume.

## Evidence Tiers

Classify every claim:

1. `A confirmed`: directly stated by the user with enough detail.
2. `B repeated`: present in the latest resume and repeated consistently in
   later user conversations.
3. `C lead`: produced by prior model summaries, sample answers, or memory
   prompts and awaiting user confirmation.
4. `D speculation`: inferred from a role, industry, or likely scenario.

Only A and B claims may enter a final resume draft. C claims may appear in a
recall prompt or a clearly marked pending section. D claims must stay out of
personal experience records.

When the user explicitly confirms that a model-generated recall lead matches
their memory, promote only that specific confirmed detail to `A confirmed`.
Do not promote neighboring details, inferred context, or the entire model
paragraph. Keep the original lead and the user's confirmation trace together.
Numbers, dates, organization names, decision rights, and team results still
need their own confirmation.

## Campus Hiring Rules

For campus recruitment, evaluate evidence in three layers. Do not apply the
same performance standard used for experienced hires.

1. `Business outcome`: confirmed leads, activity attendance, content exposure,
   conversion, orders, project delivery, adoption, awards, or other results.
2. `Process evidence`: customer conversations, research scope, competitor
   analysis, materials produced, activities executed, stakeholders coordinated,
   proposals supported, or problems resolved.
3. `Capability evidence`: structured thinking, learning speed, communication,
   data handling, customer awareness, project execution, ownership, and
   reflection supported by a specific event.

Use the strongest available layer. A campus candidate without confirmed
revenue, contracts, collections, budgets, or full sales-cycle ownership must
not be written as if they had those outcomes. Research, school projects, and
activity organization can support transferable capability only when the
candidate can describe a real task, action, constraint, and result.

For a marketing role, identify the subtype before selecting evidence:
market research, product marketing, brand, content, activity, demand
generation, digital marketing, regional marketing, industry marketing, or
growth. Do not use one generic marketing standard for all of them.

For a supply-chain role, distinguish project coordination from procurement,
planning, warehousing, logistics, supplier management, quality, or delivery.
Do not claim a supply-chain function without direct evidence.

## Career System Boundaries

Maintain three separate layers:

1. `Skill`: reusable method, evidence rules, review criteria, and output
   structure.
2. `Fact library`: confirmed personal experiences, source files, proof,
   conflicts, metrics, and recall questions.
3. `Application record`: one company and one materially distinct role per
   record, containing the JD, dated company research, evidence map, tailored
   resume, interview preparation, and review log.

Do not store personal facts, old company research, target-specific keywords,
or previous tailored resumes as fixed skill rules. Do not let one company's JD
or terminology contaminate another application.

## Job Research Evidence

Treat personal experience evidence and job research evidence separately.

1. `R1 primary`: official company careers pages, annual reports, official
   product material, regulatory filings, official investor material, and
   first-party event transcripts.
2. `R2 direct`: a job description supplied by the recruiter or a confirmed
   conversation with a current employee. Record the date, role, and source.
3. `R3 secondary`: major media, industry reports, and public employee
   commentary. Use for leads and cross-check material facts.
4. `R4 unverified`: social posts, interview tip accounts, model summaries,
   copied prompts, and anonymous comments.

R4 may generate research questions. It cannot support claims about a company,
manager, customer, compensation, interview process, or business strategy.
Always record publication date for time-sensitive business information.

## Job Research Workflow

Before preparing a role-specific answer, build a compact research brief:

1. Define the company, business unit, city, role name, and application stage.
2. Gather at least one current official job description and extract repeated
   responsibilities, success measures, collaborators, and hard constraints.
3. Translate each requirement into a likely work scene. Mark each translation
   as an inference rather than a fact.
4. Map verified personal evidence to the requirement. Keep unsupported gaps
   visible rather than filling them with generic wording.
5. Research the company through primary sources first: business model,
   products, customers, financial or operating changes, strategy, and current
   public developments.
6. Draft one question for each unresolved point: role expectations, team
   operating model, onboarding, evaluation, and current business challenge.
7. Run a source and date check before using the brief in an interview.

For sales, marketing, and supply-chain roles, distinguish clearly between
general job logic and the target company's actual process.

Do not claim to know an ATS pass rate, an employer's hidden screening rules,
or an interviewer preference without direct evidence. Treat ATS checks as
parseability, terminology coverage, structural clarity, and human readability
reviews. Any numeric score is an internal prioritization aid, not an observed
probability of passing.

## Interview Preparation

Prepare from verified experience material before drafting question-specific
scripts. A useful interview plan should show which resume statement or job
requirement each answer is meant to support, which evidence it uses, and which
parts still need confirmation.

For self-introductions, route to the dedicated reference above. Do not draft a
polished introduction until the target role, available speaking time, and the
evidence status of each included claim are known. When one of these inputs is
missing, return a bounded draft with visible placeholders or confirmation
questions.

Treat an interviewer's likely intent as a hypothesis. Consider more than one
plausible intent when the wording is ambiguous, answer the literal question
first, and then address the most relevant concern. Do not label ordinary
questions as traps without evidence.

### Answer Design

Use one stable structure:

`direct answer + context + personal goal + key judgment + action + result + review`

For experience questions, use a fuller version:

`background + task + discovery + analysis + action + result + reflection`

The answer must begin with a direct response in the first two sentences. Use
one detailed scene rather than a list of vague claims. The review should name
one concrete adjustment, limitation, or lesson that the user can defend.

Prefer flexible answer depths over memorized scripts. Prepare a short
conclusion, a core version, and optional evidence modules for follow-up. Exact
durations depend on the interview format and should not be treated as fixed
rules.

### Sales Scenario Questions

Prepare general scenarios with this order:

1. Stabilize the conversation and clarify the customer's concern.
2. Gather decision criteria, stakeholders, timing, and constraints.
3. Protect compliance, service quality, and reasonable commercial boundaries.
4. Present an option with the customer's expected value and implementation
   conditions.
5. Agree on the next action, owner, and follow-up time.

Do not promise price reductions, commercial approval, technical capabilities,
or delivery terms that the user would not have authority to offer.

### Group Interviews

Prepare three contributions before entering:

1. An initial decision framework that can be stated within one minute.
2. Two dimensions that make the analysis more complete, such as customer
   impact, feasibility, cost, risk, timeline, or stakeholder coordination.
3. A short synthesis that identifies the team's agreed recommendation,
   rationale, risk, and next step.

During discussion, contribute early enough to establish value, invite quieter
members to add relevant evidence, and leave time for a final synthesis. Do not
fight for a leader label. The useful role is the person who improves structure,
evidence, pace, or decision quality.

### Pressure Interviews

Maintain a short and concrete response:

1. State the conclusion.
2. Name the criterion or principle behind the decision.
3. Give one credible action.
4. Explain the boundary or escalation point.

If interrupted, answer the immediate question first, then ask whether the
interviewer wants the detail. Do not recite company values without connecting
them to a verified action or informed judgment.

### Reverse Questions

Select one or two questions according to the interview stage:

1. What output should a new hire produce in the first three to six months?
2. What is the team's most pressing problem, and where could this role help?
3. How are responsibilities, reporting lines, and cross-functional
   collaboration arranged?
4. What behaviors distinguish people who perform well in this role?
5. What does the onboarding and feedback process look like?

Prioritize work content and evaluation in early interviews. Discuss
compensation, benefits, and contract terms at the appropriate recruitment
stage.

## Interview Review Workflow

Complete the review within 24 hours when possible:

1. Record each question, the answer given, follow-up questions, and the
   interviewer's visible response.
2. Separate an observation from an interpretation. For example, "the
   interviewer asked twice about metrics" is an observation; "they doubted my
   ownership" is an interpretation to test.
3. Locate the weak point: missing fact, unclear structure, weak role
   understanding, unverified metric, insufficient company research, or
   communication issue.
4. Rewrite only the affected answer. Preserve the original answer for
   comparison.
5. Add a test question that could expose the same weakness next time.

Do not infer an interview result from politeness, note-taking, interview
length, follow-up depth, or discussion of start dates. Record such items as
observations. Interpret them only as tentative signals and compare them with
the eventual outcome when available.

When enough comparable applications exist, review performance at three
levels: one interview, a small set of similar interviews, and the current
application stage. Calculate funnel rates only with explicit numerators,
denominators, time windows, and comparable role groups. A low rate identifies
where to investigate; it does not establish a single cause.

## Ethical Boundaries

Do not turn job preparation into manipulation or information extraction.

1. Do not seek private social-media access, confidential business information,
   customer data, internal hiring data, or personal details unrelated to the
   role.
2. Do not suggest gifts, entertainment, inducements, or personal favors to
   influence interviewers, managers, customers, suppliers, or public-sector
   contacts.
3. Do not use social posts, anonymous interview tips, or copied prompts as
   factual proof.
4. Do not present sample answers, personal labels, or flattering language as
   evidence of competence.
5. Do not manufacture urgency, competing offers, geographic constraints, or
   personal connections.

## Fact Ledger

For each experience, record:

1. Time and place.
2. Organization or project.
3. User's exact identity.
4. Original objective.
5. Personal actions in chronological order.
6. Constraints and difficult moments.
7. Result type and metric definition.
8. Evidence or proof source.
9. Team result versus personal result.
10. Unresolved questions.

Use explicit labels such as `confirmed`, `needs_confirmation`,
`model_lead`, and `do_not_use`.

## Adversarial Review

Before writing a resume bullet or interview answer, test the claim against:

### Role inflation

Can the user explain who assigned the task, who made the final decision, and
what authority the user actually had?

### Metric integrity

Can the user state the numerator, denominator, baseline, period, data source,
and whether the number belongs to the user, a team, a store, or a whole project?

### Contribution boundary

Can the user identify the exact action they personally completed? Team awards
must remain team awards.

### Timeline integrity

Do the date, duration, sequence, and project stage remain consistent across
the resume and interview answers?

### Result integrity

Is the result a delivery, award, exposure, lead, order, revenue, retention
change, or subjective feedback? Do not replace one result type with another.

### Proof test

Could the user show a document, screenshot, message, link, certificate,
version history, or a person who can verify the claim?

### Stress test

Ask at least five follow-ups:

1. What exactly did you do?
2. Why did you choose that action?
3. What was the hardest disagreement?
4. How did you measure the result?
5. What would you change if you did it again?

If the answer collapses under these questions, downgrade the claim or leave it
as a pending recall item.

## Experience Mining Workflow

### Step 1: Extract

Build a raw inventory from the resume, attachments, and user statements. Keep
the original wording and source file name.

### Step 2: Normalize

Merge duplicate descriptions of the same project. Preserve conflicting dates,
roles, metrics, and outcomes in a conflict table.

### Step 3: Classify

Sort each item into:

1. final-resume fact,
2. interview-only fact,
3. recall prompt,
4. unsuitable or unsupported material.

### Step 4: Deepen

Ask the smallest set of questions that can materially improve credibility:
scope, decision rights, difficult moment, personal action, result definition,
and proof.

### Step 5: Map to target roles

Map each confirmed action to role capabilities such as customer discovery,
prospecting, solution communication, project coordination, stakeholder
management, content operation, business analysis, or supply coordination.
Do not claim a capability solely from a superficial similarity.

### Step 6: Draft two versions

Create:

1. Resume version: short, evidence-heavy, result-oriented.
2. Interview version: chronological, natural, and ready for follow-up.

Keep different levels of detail. Do not create a stronger fact in the
interview version.

### Step 7: Audit

Run the adversarial review again. Mark every unresolved claim beside the
sentence that depends on it.

## Output Contract

For each important experience, return:

1. Confirmed facts.
2. Evidence tier.
3. Role value.
4. Personal contribution.
5. Difficulty and response.
6. Result and metric caveat.
7. Resume wording.
8. Oral wording.
9. Likely interviewer questions.
10. Missing evidence and next questions.

For role-specific preparation, also return:

1. Research source table with dates and evidence grades.
2. JD-to-work-scene translation table, with inferences labelled.
3. Evidence map from verified personal experiences to the role.
4. A self-introduction at the requested duration, plus a shorter fallback,
   key questions, scenario answer outlines, and selected reverse questions.
5. A review log after the interview.

When the user asks to save the work, create a durable case library, a
methodology document, and a short memory update. Do not write personal claims
into long-term memory unless they are clearly labelled as confirmed or pending.

## Style And Safety

1. Use restrained Chinese.
2. State uncertainty directly.
3. Never fabricate companies, clients, authority, budgets, revenue, metrics,
   awards, or technical details.
4. Do not convert a personal activity into a business result without evidence.
5. Do not use model-generated sample answers as proof.
6. Do not recommend adding every experience to the resume. Select by target
   role and evidence quality.
7. Do not "beautify" data. You may clarify units, round only when the original
   source supports the rounding, and improve presentation without changing the
   fact.
8. Do not use invented seniority, such as a fictional number of years in
   recruitment or sales, as a substitute for source-grounded judgment.
