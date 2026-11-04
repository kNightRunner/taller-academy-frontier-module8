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
