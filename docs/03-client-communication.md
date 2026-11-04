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
