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
