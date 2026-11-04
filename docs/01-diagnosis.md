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
