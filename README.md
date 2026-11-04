# Working at the Frontier — Module 8
## The Full Engagement Simulation

**Taller Academy capstone | Written engagement simulation | November 2026**

> **Simulation, not a real client engagement.** Meridian Health Services, its people, workflow figures and constraints are supplied by the training scenario. Recommendations, thresholds, dates and forecasts below are proposals, **not observed outcomes**. No client code, operational data, credentials, internal communications or other confidential information from my professional work appear here.

The challenge is to enter an unfamiliar organization, find out why work is slow, and make a meaningful improvement without assuming the organization needs another AI product.

### The answer in one minute

- Meridian takes **34 calendar days on average** to credential a provider, against a **30-day commitment**. About **40%** of cases miss that commitment.
- Staff perform **770 minutes (12 hours 50 minutes)** of active work per case. The resulting **flow efficiency is approximately 1.57%**. The problem is predominantly waiting, coordination and decision rights—not the speed of writing code.
- The three largest waits are **reference outreach (11 days)**, **committee review (7 days)** and **primary-source verification (5 days)**. They account for **23 days of identified waiting**.
- The recommended 90-day effort is a bounded credentialing pilot that improves the evidence packet, reference follow-up and committee scheduling **without handing regulated decisions to AI**.
- The **proposed** primary goal is to bring average end-to-end time from **34 to at most 27 days by February 6, 2027**, subject to a verified baseline and an authorized pilot. A separate quality measure must not worsen.

### Deliverables

| Lab exercise | Written artifact |
|---|---|
| 1 — Diagnosis | [Flow analysis, four initiative failures, three conditions, organizational finding](docs/01-diagnosis.md) |
| 2 — Engagement design | [Outcome, 90-day scope, two workflows, permissions, hybrid handoffs](docs/02-engagement-design.md) |
| 3 — Client communication | [Two-page COO proposal, VP dialogue, early bad-news memo, next gain](docs/03-client-communication.md) |
| 4 — Defense | [Answers to all ten challenges, with framework versus judgment labels](docs/04-defense.md) |
| 5 — Self-assessment | [Eight evidence items and an update to my existing 90-day learning plan](docs/05-self-assessment-and-doubt.md) |
| 6 — Return to my doubt | [Evidence-bound reflection; original Module 1 statement not fabricated](docs/05-self-assessment-and-doubt.md#exercise-6--return-to-my-doubt) |
| Supporting implementation detail | [Metric definitions, role matrix, audit chain and triggers](docs/06-operating-controls.md) |

### Assumptions and evidence boundaries

1. **Kickoff of this hypothetical engagement:** November 9, 2026. Day 90 (inclusive) is February 6, 2027. These dates make the deliverables testable; they were not supplied by the scenario.
2. The scenario says **34 days average** and **770 minutes active work**. Its individually listed waits total **32.5 days**, which, after adding active work, equals about **33.03 days** rather than 34. That approximately 0.97-day gap is a data-reconciliation question to resolve during discovery—not a reason to silently modify the source figures.
3. The scenario gives no case-level history, audit failure rate, implementation permissions, pilot enrollment size, capacity limits or consent approvals. The proposal explicitly treats these as **to be checked**.
4. **No new platform licenses** means reusing approved capabilities and existing systems; it does not make cloud compute, storage, personnel effort or security review free.
5. I have not spoken with Diane, the VP, a real security officer or a mock panel. The conversation and defense are written simulations.
6. My original personal doubt from *Working at the Frontier* Module 1 was not available in the records I could verify. I do not present a newly written concern as a historical quote.

### What success means

Not a new model or a successful demo. Success would be a measurable, quality-preserving improvement in credentialing flow; an audit trail a reviewer can follow; and a process the client's own people can operate when the engagement ends.


---

# Full Submission

## Exercise 1 — Diagnosis

## 1a. Flow analysis

I would start by looking at the work as it moves through the system rather than at the performance of any one team.

| Measure | Calculation or evidence | Result |
|---|---|---:|
| Average elapsed time | Scenario's operations report | **34 calendar days** |
| Working time | 20 + 45 + 210 + 90 + 120 + 120 + 15 + 60 + 90 minutes | **770 minutes = 12 h 50 min** |
| Elapsed time in minutes | 34 × 24 × 60 | **48,960 minutes** |
| Flow efficiency | 770 / 48,960 × 100 | **1.57%** |
| Average over contractual promise | 34 − 30 | **4 days** |
| P90 end-to-end duration | Scenario | **41 days** |
| Share missing the 30-day promise | Scenario, approximately | **40%** |

**The three longest waits, in order:**

1. **Reference outreach and follow-up: 11 days.**
2. **Credentialing committee decision: 7 days.**
3. **Primary-source verification: 5 days.**

Together they represent **23 days** of waiting, or about **67.6% of the reported 34-day cycle**. The biggest visible constraint is the reference-follow-up queue, closely coupled with a committee cadence that introduces another large fixed delay. A step with only 15 minutes of committee work contributes seven days of waiting: that is a decision-calendar issue, not primarily a code issue.

**Data quality note:** The listed waits add to 32.5 days. With 770 minutes of working time (0.535 days), that is about 33.03 days, short of the stated 34-day average. I would ask Operations whether time was rounded, some handoffs were omitted, or averages were computed from different samples. I would use 34 days as the *provisional scenario baseline*, preserving the discrepancy until it is reconciled.

**How I would explain this to Diane and her CEO:**

> For every 100 hours a credentialing case spends in our process, people are actively working on it for less than two hours. Most of the delay is waiting for information, handoffs or a decision. Making individual tasks faster will help a little; reducing the time between those tasks is where the significant improvement could come from.

## 1b. Why the four AI efforts did not produce a business result

| Initiative | Likely failure mechanism | Missing condition or evidence | What I would test next |
|---|---|---|---|
| Policy chatbot, **4% weekly use** | A tool was deployed without being embedded in a task people have to complete. Low use is a signal, not a full explanation. | **Shared context:** the policies are fragmented and the three retrieval efforts may answer inconsistently. **Accountability:** no link from a chatbot response to a completed workflow or measurable saved time. | Observe real policy lookups during credentialing, identify the repeated question and determine whether a source-linked answer removes a wait or a review step. |
| Copilot for **140 engineers**, unchanged **two-week release cadence** | Individual coding may be faster while the release constraint remains elsewhere: reviews, testing, integration, approvals or accumulated technical debt. This is a *non-bottleneck speedup*. | **Accountability:** faster typing is self-reported, but no measured change in end-to-end lead time. **Context:** code generation does not repair missing interface knowledge, environment instability or fragile tests. | Map the path from PR opened to production, including queue time, build failures, regression work and approvals. Address the dominant source of delay before buying more seats. |
| Classification pilot, **91% test accuracy**, not released | A good aggregate accuracy figure did not answer the question compliance needed: who corrects wrong routing and can the original decision be reconstructed? | **Identity:** unclear which actor classified or reclassified. **Accountability:** no documented exception path, reviewer, provenance or auditable correction record. | Define error consequences by document class; run a human-reviewed, source-linked shadow test and record false classifications, overrides and outcomes before discussing production. |
| Three independent retrieval systems | Local optimization duplicated effort and produced competing views of policy knowledge. More retrieval does not automatically create a shared source of truth. | **Shared context:** owners, definitions and source versions are disconnected. **Identity/accountability:** different retrieval services may have unclear ownership, access scopes and evaluation history. | Inventory the three systems, their owners, document scopes, retrieval quality and consumers. Reuse viable components rather than create a fourth platform. |

**The VP of Engineering has a valid point.** If unreliable tests, integration coupling or change approvals dominate the time from merge to release, Copilot will not change a two-week release train. Technical-debt reduction might be the highest-return engineering intervention in that workflow. I would ask the VP to help identify the specific release constraint and agree that our pilot must not create another system his team is forced to maintain.

## 1c. Assess the three conditions

### Severity 1 — Shared context (critical)

Evidence: approximately **400,000 SharePoint files with no consistent taxonomy**, three separate retrieval systems, an Oracle store, a mainframe eligibility dependency, inconsistent ServiceNow usage and a spreadsheet that contains the verification team's working knowledge.

The reconstruction cost lands on the **11 experienced verification specialists**, each new reviewer, anyone preparing the committee packet and anyone trying to interpret policies across systems. A question that should have an answer becomes another message, another lookup or another handoff. A broad document ingestion effort would make this worse if it indexed ambiguity without resolving which sources are authoritative.

### Severity 2 — Accountable execution (critical)

Meridian can report average elapsed time, the P90, active work and contract misses, but it has not demonstrated attribution from a particular case delay to an owner, a decision, a correction or an automated action. The failed classifier is the clearest warning: compliance could not explain what would happen when the system was wrong.

The priority is to connect the **case**, **step**, **actor**, **source evidence**, **decision**, **reviewer**, **exception** and **outcome**, then make it possible for an auditor to retrieve the chain. The sponsor's complaint about $3.4 million of spend with no movement in operations reporting is also an accountability problem.

### Severity 3 — Identity for automated actors (high, deployment-blocking)

The scenario mentions an Azure tenant and a strict security team, but gives **no evidence** that agents have their own identities, narrowly scoped access, durable history or enforceable separation of duties. I will not assume they exist or assume they do not. Until security verifies those controls, **no agent receives live provider data**.

This is third in the diagnostic ranking because the largest known loss is waiting and fragmented coordination. It is a **hard prerequisite** for any deployment that lets an automated actor handle regulated information. A lower diagnostic rank does not imply permission to bypass it.

## 1d. The uncomfortable, non-technology finding

The credentialing committee meets only twice a month and contributes roughly seven days of waiting to a fifteen-minute decision. Even a perfect AI assistant cannot change the committee's decision rights, calendar or bylaws.

I would tell **Diane and the committee chair together**: *“We can improve the quality of the information reaching the committee, but we will not get the full benefit unless the people who own the decision process agree on a faster, compliant way to handle routine cases. This is a governance and scheduling decision. It needs your sponsorship and the committee's participation, not another software purchase.”*


---

## Exercise 2 — Engagement Design

## 2a. Define the outcome before starting

**Primary outcome:** Mean calendar days from a provider application being received to that provider being fully enabled in the required systems, measured across **all eligible credentialing cases** in the defined pilot population.

- **Provisional baseline:** **34 calendar days**, reported in the training scenario. A further **41 days at P90** and approximately **40% over 30 days** provide context.
- **Baseline verification:** During days 1–10, Operations and I would reconcile ServiceNow events, the verification spreadsheet, committee decisions and actual system-enablement timestamps in the approved source systems. The scenario does not supply the underlying records, so I cannot claim that this verification has already happened. Diane and Operations must approve the final definition and baseline before we launch changes.
- **Target and date:** **At most 27 mean calendar days by February 6, 2027** (simulation day 90, assuming a November 9, 2026 kickoff), for a prespecified pilot cohort. This is a **proposed target**, not a prediction presented as fact.
- **Reproducible method:** Use one unique case ID, the first valid receipt timestamp and the final enablement timestamp across all four required systems; calculate `(enablement_utc - receipt_utc) / 86,400` for each completed case and the arithmetic mean. Measure in calendar days, not business days. Publish count, median, P90 and share over 30 days alongside the mean. Include all submitted cases in cohort accounting: open, paused, withdrawn, rejected and incomplete cases are reported separately rather than erased from the denominator. Report aged open cases to prevent improving the mean by finishing only easy work. Segment by case type and complexity; avoid comparing unrelated populations.
- **What falsifies success:** If the agreed pilot cohort's mean is **above 27 days** at the specified checkpoint, the primary outcome is not met. I would also **withhold any success claim** if the measurement cannot be reproduced, if aged open cases have accumulated, if case mix makes the comparison misleading, or if the safety measure below worsens.

**Secondary guardrail — decision quality and compliance:** The proportion of completed cases with complete primary-source evidence, the required human committee authorization, and the documented rationale **at the moment of activation**. Target: **100% evidence-and-authorization completeness in the pilot**; independently sample decisions for substantive verification errors and require that the verified error/rework rate does **not exceed its pre-pilot baseline**. The current baseline for this quality measure is **unknown** and must be established from a pre-pilot audit. Any unauthorized activation is a stop-and-escalate event, regardless of the average time saved. A fast but poorly verified credential is not a success.

**Who owns measurement:** Operations owns the source-of-truth definition; Compliance verifies the audit sample; the sponsor signs off on the metric and target. Engineering builds reproducible extraction, not a private spreadsheet with a changing formula.

## 2b. Ninety-day scope: one focused lane, not a transformation program

**Pilot population (proposed, pending approval):** One credentialing case type and one bounded provider-network queue, selected with Operations for volume, repeatability and compliance suitability. The exact population is fixed **before** comparing results. We use the existing SharePoint, ServiceNow, Oracle and Azure capabilities, plus the current mainframe interface operated by authorized staff.

| Phase | Work | Evidence and decision |
|---|---|---|
| **Days 1–5: understand** | Interview Diane, the committee chair, verification leads, engineering and security; walk actual cases; map time worked versus time waiting; reconcile the source figures. | Signed workflow map, decision-owner map and provisional measurement definition. No automation proposed on day one. |
| **Days 6–10: decide** | Agree case type, baseline method, quality guardrails and a small intervention. Select authoritative documents and define what agents must never do. | Two-part diagnosis: where time leaks and what will ship. Security and compliance feasibility check. |
| **Days 11–19: first shipment** | Deliver a **human-reviewed completeness/evidence checklist** connected to the pilot cases in ServiceNow, with curated links to authoritative policy material. Start with ordinary rules and manually selected references, **no live model access required**. | **By November 27, 2026:** a usable checklist in the approved pilot workflow, staffed and reviewed. It counts as shipped only if the approved users actually use it and it survives a basic operational check. |
| **Days 20–35: stabilize** | Fix gaps based on cases; make decision records mandatory on interface changes; set up a case-level event trail and daily waiting-time report. | Verified ownership, dated event history and quality sample. Stop if the evidence packets are unreliable. |
| **Days 36–60: attack waits** | Trial structured reference follow-up, clearer escalation ownership and agreed committee queue visibility. Test any automated assistance in shadow mode first. | Wait distributions, contact response rates and reviewer feedback; a clear go/no-go decision on expansion. |
| **Days 61–90: expand carefully** | If approved by the committee, test an additional human-led review cadence or authorized asynchronous decisions for routine cases. Compare pilot with baseline and a comparable non-pilot cohort if available. Transfer ownership and support guidance. | Reproducible outcome report, exceptions and maintenance handoff. **February 6, 2027** is the proposed final checkpoint. |

**Explicitly out of scope:** Retaxonomizing 400,000 SharePoint files; replacing the mainframe, Oracle or ServiceNow; changing insurer contracts; buying Echo, Chiron or other platform licenses; automating medical/compliance judgment; changing committee authority without its chair and Legal/Compliance; deploying autonomous agents that can activate providers; taking over the engineering release pipeline; promising a 30-day guarantee before the data supports it.

**What I would say to the ticket board owner:** “I can pick up that task. Before I do, I want to map the actual waiting time for a few days so we choose a task that removes a constraint instead of adding another feature to the backlog.”

## 2c. Two workflow versions

### Version 1 — Put AI into the current workflow (the driveshaft)

Keep all nine steps, every handoff, the eleven-day reference wait, the seven-day committee queue and the same approval rights. Let an assistant help draft summaries, check completeness or prepare committee packets, with human review.

**Illustrative best-case arithmetic:** Even if assistance reduced **50% of all 770 active minutes**—a large *assumed* speedup—it would save **385 minutes = 6 h 25 min = 0.267 days**. Average cycle time would move from **34 to about 33.73 days** if waiting remained unchanged. That is only about **0.8% faster** end to end. The 50% is a sensitivity assumption, **not a measured AI gain**.

This version might improve staff experience, but it will not reliably meet a 30-day commitment by itself. Automating documentation around an unchanged queue is not the same as changing the queue.

### Version 2 — Change the workflow

1. **At intake:** One durable case record is opened in ServiceNow with a checklist, missing-evidence status, policy links and a named human owner. Catch missing information early instead of discovering it at committee preparation.
2. **Primary-source checks:** Authorized people perform regulated verification. Approved tools may gather candidates and flag inconsistencies; they do not declare a credential valid. Run independent checks in parallel where policy permits, rather than serially waiting on a completed previous step.
3. **Reference outreach:** Record the contact attempts, approved channel, response status, due date and escalation owner in the case. Use human-approved templates and timed follow-up reminders instead of relying on an isolated spreadsheet. First establish why the 11-day wait exists: unresponsive references, outdated contact data, unclear responsibility, policy requirements or simple idle queue time. Do **not** automatically send more messages just because a queue is slow.
4. **Committee packet:** Build the packet incrementally as evidence arrives. A missing item remains visibly blocked with its reason and owner; no undocumented final clean-up handoff.
5. **Committee decision:** With the committee chair, Legal and Compliance, consider a short additional meeting, a scheduled routine-case review window, or asynchronous voting **only if permitted by the applicable rules**. Physicians retain decision authority. Complex or contested cases stay with full deliberation.
6. **Contract and enablement:** Prepare nonbinding information in parallel when safe, but hold legally or contractually irreversible actions until human authorization. Activation remains a controlled, audited operational action across the required systems.

**Scenario model, not a forecast:** If reference wait moved from **11 to 7 days**, committee wait from **7 to 3**, and primary-source wait from **5 to 4**, the combined reduction would be **9 days**, suggesting **about 25 days average** from the stated 34-day starting point, assuming delays do not simply move elsewhere. That is the *potential* in redesign. I would set the measured day-90 target more conservatively at **27 days** because adoption, case mix and unexpected queues will reduce the realized benefit. The committee change is not an engineering commitment until its owners authorize it.

**The harder, human part:** Verification specialists have years of tacit knowledge, and a rushed automation proposal could make them feel that their judgment is being replaced or monitored unfairly. I would ask them to help design the checklist, select exceptions, test templates and own review criteria, with time protected for that work. The committee chair may legitimately reject a new cadence. Legal and Compliance may require stricter evidence. The proposal could fail for organizational reasons even if the software is good; I would report that honestly rather than engineer around consent.

## 2d. Recreate shared context, identity and accountability using what exists

### Shared context

**Where it lives:** Small version-controlled `docs/` files next to the integration/configuration code for technical decision records and interface constraints; a **governed SharePoint pilot library** for authoritative policy excerpts and approved committee/verification guidance; links from each ServiceNow case to the relevant approved policy version and decision record. The shared spreadsheet becomes an input during transition, **not** an untracked second source of truth.

**What we capture, in order:** (1) decision log stating who chose what and why, (2) glossary for terms like “complete application,” “verified,” “ready for committee” and “activated,” (3) owner/system map showing Oracle, mainframe, SharePoint, ServiceNow and four enablement endpoints, (4) ten critical constraints such as regulated checks and approval boundaries.

**400,000-file SharePoint boundary:** Do **not** index everything. Start with **one approved library or site and a curated set of roughly 50–100 current, high-use documents** identified by the experienced verification team. That size is a planning limit, not a count supplied by Meridian. Verify owner, currency, superseded versions, access rights and applicable geography before including a document. No authority means no agent answer. Keep original documents in their governed location rather than cloning the corpus into a new store.

**How it stays current:** An interface-changing PR cannot merge without a linked decision record; a policy owner approves any change to the curated library; a resolved ambiguity updates the glossary or ServiceNow workflow definition as part of closing the issue. The agent can read only authorized, versioned material and must return a citation/source identifier and a “needs human review” state when uncertain.

### Identity and permission enforcement

**Status:** This is a proposed design. Security must verify tenant configuration, licenses and regulatory boundaries before activation. Neither Entra membership nor a prompt is a substitute for the downstream application's own access control.

| Agent role | Allowed work | Enforcement and boundaries | Memory and history |
|---|---|---|---|
| **Completeness assistant** | Read assigned pilot cases and approved checklist/policy documents; **write only a draft completeness recommendation** to a restricted ServiceNow field. | Dedicated Microsoft Entra application/managed identity. Microsoft Graph `Sites.Selected` with explicit **read** grant to the selected site; ServiceNow dedicated integration identity with **table/field ACLs** allowing pilot-case read and draft-only write. Network route and API identity allowlist. **No Oracle, mainframe, contract or activation writes.** | Corrections become human-approved case notes and versioned rules; each run logs case reference, source IDs, recommendation and reviewer. |
| **Evidence-support assistant** | Retrieve preapproved source pointers and flag missing or contradictory evidence to a human reviewer. Optional Oracle data only through specifically approved **SELECT-only views** if necessary. | Separate Entra identity, separate Graph selected-site grant; Oracle **database grants on named read-only views**, plus an isolated database credential in Azure Key Vault **if** the approved integration cannot use a managed identity. Azure RBAC controls Key Vault access, **not Oracle's database privileges**. No direct mainframe account. No final verification status write. | Reviewable evidence-index entries, human overrides and versioned source IDs in ServiceNow/approved SharePoint; Azure run logs. |
| **Reference follow-up assistant** | Create suggested reminders, contact-status summaries and **draft** messages from approved ServiceNow fields; a staff member decides whether to send. | Dedicated Entra/workload identity and scoped ServiceNow integration role. ACL limits writes to draft and reminder fields. **No external send permission, mass-contact authority or provider-status writes.** An eventual sending capability requires explicit Security/Legal approval and a separately enforced identity. | ServiceNow contact-attempt timeline, approved template version, draft approval status and event logs. |

**Cross-cutting enforcement:** Entra service principals or managed identities per role; Azure RBAC for approved Azure resources; Key Vault only where a secret is unavoidable; resource-side permissions in SharePoint, ServiceNow and Oracle; network allowlists/private connectivity where supported; explicit API endpoint allowlists; rate limits and workload budgets at the execution gateway; least-privilege logging. Never use a staff member's credential or a shared general-purpose agent account. Agents may be disabled individually without stopping the human workflow.

**Residency:** Before any production model processes provider-related information, Security must approve the exact service, Azure deployment type, processing geography, logging destination, retention, subprocessors and egress policy. A “global” inference endpoint is **not** automatically compatible with a residency requirement. If approval is not granted, use deterministic rules and human review inside approved systems; no provider data is sent to an external model.

### Accountability

- **One number:** The approved end-to-end cycle-time metric and guardrails, calculated from ServiceNow case events and authoritative enablement timestamps; reporting and methodology accessible to Diane and Operations.
- **Decisions:** Version-controlled records for interface/security decisions; ServiceNow approval and committee decisions for individual cases. A PR or change request links to its decision record.
- **Traceability:** For any draft recommendation, find its ServiceNow case, Azure run ID, dedicated actor identity, source references/version, model or rules version, input classifications (not raw data copied to logs), reviewer, human approval and eventual outcome. The detailed field map is in [operating controls](docs/06-operating-controls.md).
- **Cost attribution:** Every AI call, if approved, carries a workflow tag, agent identity, run ID, measured token usage and service cost. Aggregate cost **per run**, **per agent per week**, and **trend**, with an approved spike alert. A deterministic check records zero model tokens rather than pretending it used AI. Azure monitoring/storage has its own operating cost.
- **Corrections:** A human override is linked to a reason and an approved update to the rules/context where appropriate. The agent does not silently train itself on decisions.

## 2e. Hybrid allocation by verification cost and consequence

| Workflow step | Owner of the consequential action | Optional agent contribution | Context passed in and back |
|---|---|---|---|
| Application received/logged | **Human + existing workflow automation** | Deterministic completeness precheck; create a **draft** list of missing fields | In: submission ID, authorized attachments and provenance. Out: receipt timestamp, case owner, checklist version, unresolved fields. |
| Completeness check | **Both; human approves** | Read-only comparison with an approved checklist, evidence links and uncertainties | In: case, document list, glossary. Out: proposed missing items, source links and staff approval/correction. |
| Primary-source verification | **Human** | Collect possible source references or highlight inconsistencies **without declaring verification complete** | In: approved source, identity match rules, risk flags. Out: source/version, time, mismatch/uncertainty and human attestation. |
| Malpractice-history review | **Human** | Organize source references for review; no autonomous regulated conclusion | In: access-approved evidence. Out: reviewed finding, source, responsible reviewer and escalation status. |
| Reference outreach/follow-up | **Both; human approves external outreach** | Suggest reminders, draft approved-language follow-ups, track response state | In: verified contact permission, attempt history, approved wording. Out: draft, approval, response, next due time and exception. |
| Committee preparation | **Both; human signs off** | Assemble a proposed packet and flag missing evidence | In: evidence trail, open exceptions and policy rules. Out: packet version, missing items, analyst signoff. |
| Committee decision | **Human committee only** | Scheduling assistance and display of source-linked packet; no vote or decision | In: approved packet and decision authority. Out: signed decision, rationale, dissent/conditions if required, meeting date. |
| Contract generation/countersign | **Human authorized signatories** | Prefill a **draft** from approved data; never execute a signature | In: committee authorization and current terms. Out: reviewed contract, signature status and exception record. |
| Enablement across four systems | **Human-authorized operations, deterministic integrations** | Surface readiness and cross-system consistency checks; **no agent activation** | In: signed approval, contract state, system-specific readiness. Out: each system's activation time, operator identity, evidence of completion. |

**One board, one standard:** All human and agent work is visible in the **same ServiceNow workflow**, with the same acceptance criteria, review gates and case ownership. When uncertainty is material, the agent asks or produces a flagged draft; it does not guess. Every clarification changes the documented checklist, case note or decision record so the next reviewer does not start from zero.


---

## Exercise 3 — Client Communication

## 3a. Proposal to Diane Okafor, Chief Operating Officer

**To:** Diane Okafor, COO, Meridian Health Services  
**Subject:** A 90-day pilot to reduce provider credentialing delays  
**Date:** November 13, 2026 (*simulation date, after first-week discovery*)  
**Decision requested:** Authorize a bounded credentialing pilot, its owners and its measurement rules

### Page 1 — The problem worth solving

Diane,

You told us something important at the start: Meridian has invested substantially in AI, but the operations report does not show a result you can confidently explain to your CEO. I do not think the right response is to buy another tool or add one more pilot. I think we need to change one process that is already costing the company time.

The clearest candidate is **provider credentialing**. Meridian takes **34 calendar days on average** to complete a case, while its insurer commitments call for **30 days**. Around **40%** of cases miss that commitment. The 90th-percentile case takes **41 days**. The cost is not just contractual penalties; slow onboarding also creates a risk that providers choose a different network.

Your teams spend approximately **12 hours and 50 minutes** actually working on a credentialing case. The remaining time is mostly waiting. The three largest pauses are **11 days for references**, **7 days for committee review**, and **5 days before primary-source verification**. Two of those are partly coordination and decision-design problems. No software can make a committee meet more often without the committee's agreement.

The previous AI investments tell a consistent story:

- The policy chatbot is available, but at **4% weekly use**, it has not become part of a regular job people need to finish.
- Engineers say Copilot helps them work faster, but releases still happen every two weeks. Faster coding does not automatically shorten the slowest part of a release process.
- The document-classification pilot reached **91% testing accuracy**, but no one had an acceptable way to handle or explain wrong classifications. Compliance was right to stop it.
- Three independent policy-search systems reflect real effort, but they also show that knowledge is being rebuilt separately rather than shared.

I would not call those efforts pointless. They taught us that technical capability is ahead of workflow design, reliable context and accountability. The right next step is to use those lessons rather than blame the people who approved or built the tools.

I also agree with the VP of Engineering that technical debt is real. We should not create another complex platform for his team to inherit. The pilot must rely on Meridian's approved systems and leave a simpler process behind.

### Page 2 — What we will do and how you will know

**Our proposal is a focused 90-day credentialing pilot.** We will begin with one agreed case type and operating queue. The team will establish an auditable start-to-finish time measure, identify the actual source of reference delays and make it easier to carry verified information forward between steps.

In the first two weeks we will confirm where cases wait, who decides what, which documents are authoritative, and what cannot change under compliance policy. We will then deliver one practical improvement: **a shared, staff-reviewed checklist and evidence packet in the existing workflow by November 27**. It should help reviewers see what is missing before a case reaches the next queue. It will count as delivered only when staff use it successfully in normal work.

Over the following weeks, we will test clearer reference follow-up, named ownership for stalled cases and more complete committee packets. We will ask the committee chair whether an additional review slot or a different compliant process for routine cases is feasible. **Only the authorized committee will decide provider eligibility.** We will not let an AI model approve a provider, sign a contract or activate access.

The **proposed success measure** is a reduction in average end-to-end credentialing time from **34 to no more than 27 days by February 6, 2027**. Those are the scenario's current baseline and a target, not a claimed result. We will agree on a reproducible calculation, verify the starting figure and report the sample size, the cases still waiting, the longest cases and the share that miss 30 days. We will also require complete documented approval evidence and no deterioration in verification quality. A faster process that skips a safety check is a failure.

A simple improvement could be visible early. The larger result will take longer because it requires disciplined recordkeeping, clean handoffs, secure access, staff time, committee decisions and measurement—not merely building an attractive demo. We will show those costs and risks at the outset. **There are no new platform licenses in the proposal**, but there will be time and operational costs, which Engineering and Finance need to approve.

**What we need from you by November 17** (*proposed simulation decision date*):

1. Name an **Operations owner** who can approve the pilot cohort, the case record and measurement rules.
2. Introduce us to the **credentialing committee chair**, with authority to discuss meeting cadence and decision policy. We do not need you to overrule the physicians.
3. Give protected discovery and review time to **two experienced verification specialists**, with input from the full 11-person team as needed.
4. Ask the **VP of Engineering** to nominate one technical counterpart and identify any technical-debt constraint that would make the pilot unsafe or unsustainable.
5. Ask **Security and Compliance** to confirm what source material can be used, which access boundaries apply and what approvals are needed before any assistant handles live provider information.

For your **November CEO discussion**, our honest report should be: we know where the time is being lost, we have an agreed way to measure it, and we have started a bounded improvement with named owners. I would not claim a cycle-time reduction before a full set of pilot cases has been measured.

The difference I want you to see is not a better slide about AI. It is a workflow that can get faster, remain safe, and be run by Meridian when we leave.

---

## 3b. Three exchanges with the VP of Engineering

**Exchange 1 — Respect the objection**

**Me:** “I understand why you see another AI engagement as a distraction. You've still got a two-week release cadence, and adding another dependency could make it worse. I don't want to arrive with a platform your team never asked for. Where does a change spend the most time between being ready for review and reaching production?”

**VP:** “Usually testing, integration problems and the approvals around changes. Developers writing code faster hasn't changed any of those.”

**Me:** “Then Copilot is speeding up something that isn't the bottleneck. I wouldn't measure the engineering part of this engagement by lines of code or prompts. Could we identify the smallest credentialing change that uses your current systems and doesn't add another fragile integration?”

**Exchange 2 — Find a shared interest**

**VP:** “Your proposal still sounds like more code, more documentation and a new support burden for my team.”

**Me:** “That's a fair concern. I want to start with a structured checklist and a clear case record, not a new platform. We can use a small version-controlled decision log for interface changes, and the workflow owner will maintain the operational checklist. If we can't identify maintainers and a safe support path before the pilot starts, we cut scope rather than hand your team another orphaned service.”

**VP:** “And what do you want from my engineers?”

**Me:** “One named reviewer who can tell us whether the existing integration can support the case record safely. I also want your team's definition of a low-risk change and the release tests it has to pass. We will use your review standard, including for agent-generated work.”

**Exchange 3 — Agree on a stop condition**

**VP:** “What happens if the pilot slows down delivery or starts generating more incidents?”

**Me:** “We stop expansion. If the checklist causes rework or the evidence trail is unreliable, we fix it or roll it back. We won't make provider decisions automatic. I'll show you the change cost and any new operational burden alongside the outcome metric. Would you be willing to sign off on a design that has a rollback plan, a named owner and no mandatory new platform?”

**VP:** “If the scope stays that small and Security signs off, I'll put an engineer in the review.”

**Me:** “That's enough to begin discovery. I'll document what we agree, what is still uncertain and the point where you can say no.”

---

## 3c. Bad news memo — week six (under 200 words)

**To:** Diane Okafor  
**Subject:** Reference follow-up pilot — response-rate decline and immediate action  
**Timing:** Send as soon as the week-six result is known, before a fix is confirmed

> Diane,
>
> We found a problem in the reference follow-up pilot. Responses to the automated outreach are **20% lower than with the previous manual approach**. This is a relative decline in the scenario; we have not been given the absolute response rates.
>
> That puts our credentialing-time target at risk. I do not yet know whether the main cause is message wording, sender recognition, timing or something else, and I do not want to keep expanding a process that may be making the wait longer.
>
> I am pausing expansion of automated outreach and moving the affected cases back to the approved human-led follow-up process. With the verification lead, I will compare contact patterns and review a small set of responses and non-responses, without changing compliance controls.
>
> I need your support to protect the specialists' time for that review and approval to keep the pilot limited while we investigate.
>
> I will send you an evidence-based update **within two working days**, including what we found, the impact on the target and a recommendation to fix, change or stop the automation.

*Word count of memo body: fewer than 200 words. The described pause is a proposed simulation response, not a claim that a real automation was disabled.*

---

## 3d. The next meaningful gain

“Working on credentialing showed us another opportunity: a decision can take **15 minutes** of committee time while a case waits **7 days** to reach that decision. If the committee approves a compliant faster route for routine cases, reducing that wait to **3 days** would save approximately **4 calendar days per affected case** before we automate anything else. I would validate how many cases qualify, the quality safeguards and the committee's capacity before recommending rollout to other credentialing queues. The business opportunity is faster provider readiness, not a larger AI footprint.”


---

## Exercise 4 — The Defense

I wrote these responses rather than claiming to have performed a live role-play. Each answer has a label: **Framework** means it follows a specific principle from the course; **Judgment / improvised** means the case required a local decision that the framework does not settle for me. Some answers necessarily use both.

## Diane Okafor, COO

### 1. “The last three vendors told me they would fix this. Why is this different?”

**Answer:** “I would not ask you to trust a promise. By the end of week two, I want you to have a workflow map, an agreed baseline and the list of people who can actually change the process. By the end of the third week, I want a small piece of the workflow in use, not another demo. If our numbers do not move without quality getting worse, we should say that in your report rather than count model usage as success. The difference needs to show up in your operations report, or it isn't different enough.”

**Basis:** Framework — outcomes, baseline, bounded shipment, honesty about evidence.

### 2. “You are proposing to change how the credentialing committee works. Those physicians don't report to me. How do you expect me to make that happen?”

**Answer:** “I don't expect you to order them to change their decisions or meeting schedule. I need you to help convene the chair, Legal, Compliance and Operations around the cost of the seven-day queue. We can show them the data and give them options—one more short review slot, an authorized routine-case route, or better packets that reduce the work they receive. If they decline, we do not bypass them. We update the model and pursue the waits we can change.”

**Basis:** Framework plus judgment — recognizes decision rights; committee consent and options are local negotiations.

### 3. “What happens if this doesn't work? What do I tell my CEO in November?”

**Answer:** “In November, tell the CEO what we know, not what we hope: the process averages 34 days, we've identified where waiting concentrates, and we're running a pilot with a defined measure and quality safeguards. The final 90-day result will not exist yet. If the pilot misses the goal, I'll give you the measured result, the reason we think it missed, which options remain and what we recommend stopping. You will have a decision, not a story about effort.”

**Basis:** Framework — calibrated uncertainty and outcome reporting.

### 4. “Can I do a smaller version first?”

**Answer:** “Yes. That's where I would start. One case type, one team, one checklist, and no automated credential decisions. We can see whether missing information gets found earlier, whether staff actually use the record, and whether the audit trail works. The smaller test won't prove the final cycle-time target, but it will prove whether the operating method is safe enough to expand.”

**Basis:** Framework — bounded work that ships; staged, verifiable exposure.

## VP of Engineering

### 5. “We already have Copilot. What are you adding?”

**Answer:** “Copilot may help your developers write code, and I don't want to take that away from them. But your release cadence hasn't changed. I'm looking at the wait between activities: unclear handoffs, policy lookups, review queues and decision timing. The addition is a way to connect actual changes to an operational outcome, not another coding assistant.”

**Basis:** Framework — the bottleneck and local productivity gap.

### 6. “You want my team to write decision records. They will not do it. What is your plan for when they do not?”

**Answer:** “I wouldn't depend on them remembering. For an interface-changing PR, the repository template will require a link to a short decision record, and an automated check will block merging until that link exists and the referenced file follows the required structure. The technical owner can approve an explicit emergency exception, but the exception is recorded and a follow-up becomes part of the change workflow. We will keep the record short enough to be useful, review whether the rule creates noise, and remove requirements that don't earn their keep.”

**Basis:** Framework plus implementation judgment — **event-triggered enforcement**, not goodwill or a recurring reminder. A CI check can validate structure and link presence; **human review must judge whether the decision content is meaningful**.

### 7. “Who maintains all this after you leave?”

**Answer:** “We identify owners before we ship: Operations owns the case checklist and turnaround metric, Verification owns approved work instructions, the committee chair owns decision rules, Compliance owns the evidence standard, and Engineering owns only the small integrations it has accepted. Updates attach to existing events—case closure, policy revision and interface PRs—rather than an extra monthly meeting someone will forget. The last month includes a handover, a runbook, a rollback test and a check that those owners can operate it without me. If no one will own a component, we should not deploy it.”

**Basis:** Framework plus judgment — mechanisms for sustainability and explicit refusal of orphaned ownership.

## Head of Security

### 8. “You want service accounts for AI agents with access to provider data. Walk me through the blast radius if one is compromised.”

**Answer:** “There isn't one account with access to everything. A compromised completeness assistant should only be able to read an approved pilot case subset and a specifically granted SharePoint site, then write draft recommendations to a restricted field. It must not activate providers, alter primary-source verification, access the mainframe or send messages. The evidence assistant has different credentials and only approved read views. We would disable that one identity, revoke its SharePoint resource grant and downstream integration access, stop the workload, preserve logs and review exactly which case references it touched. Before launch, we'll test denied actions as well as allowed ones. I cannot claim the impact is contained until those boundaries are demonstrated.”

**Basis:** Framework plus implementation judgment — per-role identity, downstream authorization, fail-closed revocation and audit.

### 9. “Where does the data go? We refused a project over data residency.”

**Answer:** “That refusal is a requirement, not friction to work around. We will map every location where source documents, case records, processing inputs, model inference, logs, backups and human reviews happen. A service being hosted in Azure is not proof that inference stays in an approved geography; the specific deployment type matters. Until you approve the full path, we will use deterministic checks or synthetic cases and keep regulated data inside authorized systems. If an approved model setup is unavailable, the pilot will run without one.”

**Basis:** Framework plus security judgment — residency boundary before model choice; no hidden exception.

### 10. “How do I audit what an agent did six months from now?”

**Answer:** “Pick any recommendation and start with its case ID. From ServiceNow, you should find the draft, the human reviewer and final action. The attached run ID should lead to an access-controlled Azure event record naming the dedicated agent identity, approved source references and versions, the rules or model version, time, cost and any exception. The decision record explains why the workflow was allowed to run that way. We will test this chain with an auditor and set retention for at least six months **only after Legal and Security approve the actual retention period**. If a link is missing, we do not call the system auditable.”

**Basis:** Framework plus implementation judgment — specific traceability test and retention caveat.

## Where I was least certain

Questions **2** and **9** require the most client-specific judgment: the committee's legal authority and the real data-residency boundaries are not supplied. I can propose conversations and controls, but not manufacture approvals or assert that a particular Azure deployment is compliant. Question **6** is the clearest engineering mechanism: a required PR-linked record backed by an automated merge check, with human quality review. Question **7** is the sustainability test: if no operational owner accepts the handoff, the right answer is to reduce scope.


---

## Exercises 5 and 6 — Self-Assessment and Return to a Doubt

## Exercise 5 — Self-assessment against the eight readiness items

This is a **written simulation**. It demonstrates structured reasoning, not competence validated by a real client, a live role-play, or a production deployment. For clarity, I use **Written = shown by an artifact**, **Partial = an artifact supports the claim but the full skill has not been tested**, and **Not yet = the necessary real-world evidence is missing**. This is not a course-defined numeric scale.

| Readiness evidence item | Assessment | Evidence produced in this simulation | What is still missing |
|---|---|---|---|
| 1. Explain Taller, the productivity gap and role architecture without a script | **Partial** | [Diagnosis](docs/01-diagnosis.md): why faster coding does not change a two-week release constraint; [proposal](docs/03-client-communication.md) explains outcomes in plain language | Spoken, unscripted explanation tested by someone else. |
| 2. Diagnose through shared context, identity and accountability | **Written** | [Diagnosis §1b–1c](docs/01-diagnosis.md) identifies the failure mechanisms and ranks all three conditions | Confirmation from actual stakeholders and source data. |
| 3. Propose practical conditions without Echo or Chiron | **Written** | [Design §2d](docs/02-engagement-design.md) uses SharePoint, ServiceNow, Oracle, Entra and Azure; [control appendix](docs/06-operating-controls.md) defines gates | Security review, resource-level permission tests and a running implementation. |
| 4. Scope and lead bounded work end to end | **Partial** | [90-day scope](docs/02-engagement-design.md) identifies a pilot, first shipment, acceptance and rollback | Delivery and operational handover by me in a real environment. |
| 5. Communicate plans, risks, decisions, progress and outcomes | **Written** | [COO proposal, VP dialogue and bad-news memo](docs/03-client-communication.md) | Live conversation, challenge handling and proof the communication changed a decision. |
| 6. Show disciplined AI use, verification, cost and quality controls | **Partial** | [Agent permissions, human checkpoints and cost attribution](docs/02-engagement-design.md); [audit and control design](docs/06-operating-controls.md) | Demonstrated agent runs, actual cost records, security test outcomes and measured errors. |
| 7. Find the next business-process opportunity beyond immediate engineering | **Written** | [Next gain](docs/03-client-communication.md): proposed reduction in committee waiting from seven to three days | Committee consent, a real test and verified cohort volume. |
| 8. Show simulation or field evidence of client readiness | **Partial: written simulation only** | All six exercises and [defense responses](docs/04-defense.md) | A scored live simulation with a critical reviewer, followed by coached client exposure. |

### Weakest item and the next move

The weakest readiness item in this work is **#8: evidence that I can make and defend these decisions in the room, not only in a document**. Question 9 in the defense—data residency—is the answer I would most want a security expert to challenge. It is easy to say “we will keep data where it belongs”; it is harder to demonstrate the complete processing, logging and retention chain for a particular service.

The remedy is **guided practice and validation**, not another general course: run a scored 30-minute defense with a senior engineer and a security reviewer, record which assumptions fail, revise the permission matrix and attempt a source-to-decision audit trace in a synthetic environment.

### Add the gap to my existing 90-day development plan

I already maintain a personal plan focused on delivering an **evaluated, synthetic AI ticket-classification feature**, with weekly updates, a reproducible evaluation set and explicit failure handling. The capstone does not justify abandoning that plan or quietly adding five competing goals.

**Proposed amendment within the same capability work:**

- **By day 30:** In the ticket-classifier design, write down the data flow and permission assumptions, including what may leave the local environment and who makes the final decision. Use only synthetic examples.
- **By day 60:** Ask a senior engineer or security-minded reviewer to challenge the permission map, retention choices and fallback behavior. Record actual feedback and changes; if no review can be arranged, mark it as pending.
- **By day 90:** Demonstrate a traceable result: synthetic input → agent identity → model/rules version → output validation → human-review fallback → measured evaluation result and cost. Have another person reproduce it if possible.

These are **proposed additions**, not calendar events, reviews or completed deployments. They strengthen the existing artifact instead of creating a second large project.

### Which defense question went worst, and why?

**Question 9: “Where does the data go?”** I can describe the kind of evidence Security needs, but the actual approved regions, service configuration, contractual data restrictions and logging controls are absent from the scenario. That is not a failure of the framework: it is a gap in **client-specific evidence** and, for me, an area where implementation experience needs stronger validation. I should request a real design review and learn to produce a defensible data-flow diagram with tested controls.

**What I would change if I ran the simulation again tomorrow:** I would begin by asking the committee chair and one verification specialist to walk through a recent delayed case before I proposed any automation. I would also use a small time-series diagram showing when each decision was possible and when it actually happened. That would make the nontechnical constraint and its human impact harder to overlook.

---

## Exercise 6 — Return to my doubt

### Evidence boundary

The original Module 1 statement about the part of Taller's thesis I doubted **was not available in the personal materials I could verify for this capstone**. I cannot honestly quote it or claim that the following words are exactly what I wrote then. The reflection below is my **current, retrospective objection**, offered transparently so the exercise remains substantive. Recovering and comparing the original statement is an **open step** rather than a completed one.

### My current doubt, sharpened by the course

I agree that better models do not automatically make organizations more productive. Shared context, identity and accountable execution are necessary for work that can be trusted and reused. But I am less convinced that installing those conditions is sufficient to change a business result when the constraint is **authority, incentives or regulation**.

Meridian makes the objection concrete: a committee's calendar can add seven days of waiting to a fifteen-minute decision. Even the best evidence packet does not change that calendar on its own. The team can build perfect traces and still be unable to shorten the flow unless the decision owners agree to a different operating arrangement.

### What changed in my view across the course?

The course helped me distinguish **a local speedup** from **end-to-end improvement**. Earlier, I might have started with document classification because there was already a 91%-accurate pilot. Now I would first ask why the process waits and whether wrong classifications can be safely reviewed. I also better understand that identity and auditability are what allow an agent to take on a meaningful job rather than remain a demo.

I have become more convinced of the conditions themselves, and more skeptical of any claim that technology can substitute for the human authority needed to change a workflow.

### What is the strongest version of my objection now?

**Context, identity and accountability may be necessary but not sufficient.** A Frontier Engineer also needs access to real decision-makers and an organizational mandate to change the queue where work waits. Without that, an engagement can become a polished measurement system attached to the same slow process.

### What observable evidence would settle it?

Run the bounded credentialing pilot with verified timestamps and a comparable case population. First improve context and evidence packets **without changing committee cadence**; measure what moves. Then, only if the committee authorizes it, test a faster human-led decision path and measure again. Look at mean and P90 time, aged open cases, share over 30 days, quality exceptions, staff workload and maintenance effort. If the improvement survives after the project team leaves, the argument for the full approach gets much stronger. If it stalls at the organizational boundary, we should name that boundary in the model rather than treat the engineering work as a hidden success.

### One honest follow-up

When I recover the actual Module 1 doubt, I should put it side by side with this reflection and record whether I changed my mind, refined the objection or identified a genuinely different concern. I will not manufacture a retrospective quote to make the capstone appear complete.


---

# Supporting Artifact — Operating Controls, Metrics and Auditability

This is an implementation-oriented proposal for the simulation, not a claim about Meridian's current configurations. Each mechanism must be confirmed with Security, Compliance and the owner of the relevant system before deployment.

## A. Reproducible measurement contract

**Primary metric name:** `credentialing_end_to_end_calendar_days`.

| Rule | Definition |
|---|---|
| Unit | Calendar days, fractional allowed; consistent UTC timestamps. |
| Start event | First valid application receipt event for a unique credentialing case; do not restart the clock when an application is marked incomplete or resubmitted. |
| End event | Latest **authorized and confirmed** enablement timestamp among the four required systems, after committee authorization and required contract approval. |
| Formula | For each completed case, `(last_enablement_timestamp - first_receipt_timestamp) / 86400`; cohort mean is the arithmetic average. |
| Pilot cohort | All cases entering a prespecified provider type/queue between documented dates, including cases that remain open at the checkpoint. |
| Closed cases | Report mean, median, P90, count and share completing within 30 days. |
| Open/withdrawn/rejected cases | Publish separate counts, age distributions and reasons; show total cohort and open-case backlog; do not exclude difficult cases invisibly. |
| Comparison | Same definitions for the verified pre-pilot baseline and, if practical, a non-pilot cohort; segment by provider category and complexity. |
| Source systems | ServiceNow intake/status events, committee approval record, contracting record, timestamps from each authorized system of record. |
| Reconciliation | Operations signs off event definitions and checks the scenario's roughly 0.97-day difference between step sum and stated average. |
| Falsification | Target misses; audit chain cannot reproduce the number; aged open cases spike; or safety guardrail worsens. |

**Why the mean alone is insufficient:** Completing the easiest cases first could make the completed-case average look good while difficult cases age. Therefore the COO receives both the completed-case metric and the full-cohort queue: case counts, open-case ages, P90, missed deadlines and rework. This prevents a convenient success narrative from hiding unfinished work.

## B. Secondary safety and experience controls

- **Authorization completeness:** Every activated case must have a human committee decision, source evidence and a responsible reviewer. Report the proportion satisfying all three; target 100% for the pilot.
- **Verification quality:** Independently audit a sample of pre- and post-pilot cases for incorrect or unsupported credentialing conclusions. Establish the actual pre-pilot rate before claiming non-inferiority; pause or investigate any material increase.
- **Unapproved activation:** Any case activated without required authorization triggers immediate stop/escalation and incident handling.
- **Reference response quality:** Track delivered outreach, replies, requests for clarification, opt-out/complaint signals and median wait; do not optimize message volume alone. The week-six 20% decline is a scenario test that triggers a pause.
- **Workload transfer:** Track review minutes and queue size for the 11 verification specialists. Faster end-to-end time should not come from quietly overloading them.

## C. Agents, permission tests and kill switches

| Actor | Positive permission test | Negative permission test | Emergency stop |
|---|---|---|---|
| Completeness assistant | Can read the granted pilot SharePoint site and assigned ServiceNow case; can write only the designated draft field | Cannot read an unrelated SharePoint site, change the verified status, read mainframe data or activate a provider | Disable the dedicated Entra app/managed workload, revoke selected-site grant and ServiceNow integration role; stop the workload |
| Evidence-support assistant | Can access approved document references and, if separately permitted, named Oracle SELECT-only views | Cannot enumerate the whole SharePoint tenant, access unrestricted Oracle tables or update verified findings | Remove site grant; revoke Oracle SELECT grants/credential; disable its workload identity |
| Reference follow-up assistant | Can read approved case fields and create a reminder/draft | Cannot send external messages or change final case/contract state | Revoke ServiceNow role and disable the dedicated workload |
| Human committee | Can sign or reject only according to its legitimate authority | An agent cannot impersonate committee authority | Revoke human access by ordinary identity administration and use established operational incident procedures |

**Enforcement layers:** Microsoft Entra service principals / managed identities; Microsoft Graph `Sites.Selected` **plus an explicit site-level grant**; ServiceNow roles, table- and field-level ACLs; Oracle database `GRANT SELECT` on narrowly scoped views; Azure RBAC for Azure resources; Key Vault for permitted secret storage only if a downstream system cannot use token-based identity. Entra permissions do not magically restrict an Oracle database; Oracle must enforce its own privileges.

**Testing boundary:** Test negative permissions with synthetic, non-sensitive records in a separate approved environment. Log the denied action. Security signs off before allowing any real provider data.

## D. Audit trace: output to outcome

For each proposed recommendation, the following chain must be reconstructable **without** placing full confidential source content into operational logs:

1. **Output:** ServiceNow draft/recommendation ID, version, status, creation time and case ID.
2. **Execution run:** Correlation/run ID, timestamp, approved workflow ID, step version and workload environment, kept in Azure's approved monitoring store.
3. **Identity:** Dedicated Entra application/managed-identity ID for the agent role, plus downstream authorized integration identity; no human account sharing.
4. **Inputs:** ServiceNow case reference, approved SharePoint document/site IDs and versions, named Oracle view/query ID where allowed, input sensitivity classification and source-access timestamp. Do not log raw identity documents or full sensitive prompts by default.
5. **Model/rule details:** Approved deployment or deterministic ruleset version, prompt/template version, evaluation result, error/uncertainty flags and sanitized processing metadata.
6. **Human oversight:** ServiceNow reviewer, decision time, approval/correction reason, and an immutable reference to any required committee authorization.
7. **Outcome:** Contract/signature status, enablement events across four systems, final measured cycle time and any subsequent quality exception.
8. **Cost:** Agent role, workflow tag, model usage and cost for that run. A deterministic operation has no model-token cost, but normal compute/storage costs still apply.

**Retention:** Agree the minimum auditable retention period and confidentiality controls with Legal, Security and records management. The simulated security challenge asks about six-month recall; retention of at least that long must be approved and implemented if the question is to be answerable. Do not invent a legal retention requirement.

**How to validate it:** Have Compliance choose one completed pilot case and one rejected/overridden recommendation. An engineer not involved in the build must walk from final status back to the reviewer, original authoritative evidence, agent role, run and approval. Time the exercise and record any broken link. Fix it before expanding the pilot.

## E. Decision record and change gates

A short decision record should contain:

- ID, date, author, actual decision owner and status.
- Problem and outcome affected.
- Considered options and why one was chosen.
- Security/compliance constraints and what remains uncertain.
- Expected effect, quality guardrail, and evidence needed to revisit.
- Related case/workflow and PR or ServiceNow change request.

**Trigger:** Any PR changing an interface, permissions, error behavior or authoritative data contract must link to a record. A CI merge gate checks for the link and file structure. It does **not** judge whether the reasoning is good; a human owner checks that. Approved emergency exceptions have a recorded owner and scheduled follow-up. Documentation updates are part of accepting a change, not a quarterly housekeeping task.

**Workflow handoff rule:** When an agent drafts a finding, it must hand back **source references, uncertainty, proposed action, alternative explanations and what the human must verify**. When a human corrects the agent, the correction becomes a structured case record and an approved rules/context update where warranted. Do not allow private, invisible adaptive learning from provider cases.

## F. Cost and risk dashboard

| View | Method | Why it matters |
|---|---|---|
| Cycle time | Verified source-of-truth events and cohort accounting | Keeps the engagement tied to an operational result. |
| Step waits | Time between end of one stage and start of the next; owner and reason code | Identifies whether the constraint moved rather than disappeared. |
| Quality | Evidence completeness, audit exceptions, incorrect verification and human overrides | Prevents a fast but unsafe process. |
| Agent cost | Approved per-call token/compute accounting grouped by workflow, identity, run and week | Reveals cost per useful result and hidden retry loops. |
| Alert | Agreed threshold for unusual repeated calls, unexpected permissions or cost spikes | Gives a named responder a chance to intervene before cost or exposure grows. |
| Adoption with purpose | Percentage of pilot cases with an actual, reviewed evidence packet | Measures workflow use, but is **never** substituted for reduced cycle time or preserved quality. |

**No claim of deployment:** The dashboard is a specification. Its values, alerts, dashboards, reviewers and access policies have not been created or tested in Meridian's environment.