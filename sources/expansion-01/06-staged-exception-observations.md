# FX-SRC-06 — Synthetic staged exception observations

Version 1. Scenario date: 2026-10-25. **Author-invented tabletop episodes, not actual observation, test results, defects or operational statistics.** Each episode has deliberately limited inputs. No record IDs, real accounts or clock defaults are allocated. These narratives are independent of the isolated KD001 booking QA dataset. [Premise and question register](README.md).

## X01 — Cancellation meets collection preparation

Staged setup: an own confirmed booking is still uncollected; a coordinator opened its collection row. The member starts cancellation while the coordinator prepares the physical item. Neither actual handover nor completed cancellation has yet been asserted.

Invented observation: the participants disagree whether preparation should stop cancellation. One points to the row being selected; another points to the item still being on the desk.

Interpretation: this is FX-C02, not a race result. Under FX-R04/05, a separately assumed clean eligible cancellation releases that reservation only; under FX-R07, a separately eligible completed handover creates one actual loan. The concurrent episode has no chosen winner. FX-Q02 must define eligibility and observable outcomes before executable race assertions are possible. Do not assert success for both, introduce a hold, or choose the first click as policy.

## X02 — Two coordinators and one physical collection

Staged setup: a confirmed booking has established collection eligibility for the example; the correct item is physically handed to the correct member once. Two coordinators had opened the collection context.

Required outcome **under review-pending FX-R07**: one actual loan linked to that booking; the second recording attempt does not create another. The second coordinator can learn the handover is already recorded without access to some other borrower's loan. This episode supplies no membership recheck policy, exact time window or technical retry mechanism. A different physical item with the same model is not an authorized substitute.

Negative access probe candidate, not executed: a member attempting staff handover against their own booking is refused under FX-R08, with no actual loan created by that attempt. This belongs in handover coverage, not a separate denial story.

## X03 — Late loan and the next reservation

Staged setup: an actual loan is explicitly **assumed classified overdue** for this episode; no due clock or threshold is supplied. The same item has a later confirmed reservation. The physical item has not returned.

Invented Maya: “I need to see the outstanding loan, not pretend the next borrower has it because their reservation starts. We also haven't decided who contacts them if collection becomes impossible.”

**FX-R22:** the late return situation does not itself extend the actual loan, rewrite another booking's interval, silently cancel the later reservation or choose compensation/substitution. FX-R16 permits staff to inspect the assumed overdue loan. FX-Q03/06/07/12 govern condition/availability, clocks, communications and alternative arrangements. No statement here redefines when a future interval is available in KD-ST-001.

Exercise: identify facts the desk needs now versus policies needed before promising the next collection. An email to either borrower is not an observed or authorized outcome.

## X04 — Return received while damage remains open

Staged setup: correct outstanding loan/item; staff physically receive it. A member had reported an unusual noise. Staff now note visible casing damage. A second coordinator still has the old outstanding-loan result open.

Required outcomes **under FX-R11/13/19**: record the actual loan returned once, preserve the member report as a report, and create a related operational condition case with the staff observation. The stale second attempt cannot create another receipt or close a different loan. A member can see recorded receipt of their own loan, but internal assessment notes are not automatically exposed.

Do not infer that the earlier noise caused the casing damage, that the member accepts fault, or that the item is safe after receipt. There is no fine. If that loan had been in an assumed overdue workload it is no longer outstanding; the separate condition case remains. Wrong-item and partial-kit variants stay FX-Q09.

## X05 — Interrupted confirmation

Staged setup: a coordinator records return, but the interaction stops before the coordinator receives a clear outcome. The episode deliberately does not establish whether the return completed.

**FX-R21:** distinguish a known refusal/failure before completion, which leaves the targeted booking/loan/case unchanged and must not falsely claim the requested state change, from uncertain completion. While uncertain, do not announce success or assert that nothing changed. Reconcile the selected record's known outcome before inviting action that could duplicate handover, receipt or condition handling. A repeat must respect the once-only business outcomes where specified. This is an observable consistency premise, not a prescribed retry, timeout, storage or transaction design.

The same principle applies to extension cancellation and member problem reports; it does not add new canonical KD001 criteria or invent a booking-transport contract. No timed retry, offline queue or guaranteed recovery interval is established.

## X06 — Cross-record and permission mistakes

Staged prompts: a member substitutes someone else's booking/loan reference; a coordinator opens a return result for one item but receives a different item; a coordinator without fictional reviewer designation tries to clear a condition case.

Expected **fixture-premise** boundaries: no other-member detail or mutation for the member (FX-R03/09/18); no closure of the mismatched loan (FX-R11); no condition clearance merely because the actor is desk staff (FX-R14/20). Read denial must protect details, not merely stop attribution “as your own”. Exact error strings and interface mechanics remain unspecified. These are tabletop reasoning candidates, not security verification or evidence of an implemented defect.
