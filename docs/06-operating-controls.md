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
