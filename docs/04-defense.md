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
