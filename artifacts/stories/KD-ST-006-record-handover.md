# Record actual equipment handover

Local reference: **KD-ST-006**. Version 2, 2026-10-18.
Maturity: **Ready — fictional requirements only**, not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v1 questions retain their original impacts; the current resolution table supersedes them for this scope.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-006 (#7)](https://github.com/JustinS95/KitDesk/issues/7), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary and value

**As a** desk coordinator, **I want to** record an eligible actual handover once, **so that** the confirmed reservation becomes an accurate record of who physically has that item.

Selecting a booking is not collection. A different drill of the same model is not an authorized substitute. Evidence: [FX-SRC-03 § O02/O05](../../sources/expansion-01/03-lending-operations-workshop.md), [FX-SRC-06 § X02/X05](../../sources/expansion-01/06-staged-exception-observations.md), [FX-SRC-07 § I03](../../sources/expansion-01/07-membership-readiness-brief.md).

## Scope and authority

FX-R07/08/20/21 are adopted as refined by DD-01–05/07/08. AC-05–09 establish operation-current collection eligibility, identity/timing/race rules and explicit due creation; booking confirmation does not prove handover eligibility. No training gate, override, substitution, membership change, approval, walk-in or proxy-collection right is introduced.

## Acceptance criteria

- [ ] **AC-01 — Link actual possession.** Given a confirmed, uncollected booking with collection eligibility explicitly established and the correct physical item actually handed to the correct borrowing member, a coordinator can record one outstanding actual loan linked to that booking, member and physical item, retaining the actual handover fact. The booking is known as collected and the completed result identifies its linked loan. No loan is created merely by selecting/preparing the collection. (FX-SRC-03 § O02, FX-R07; FX-SRC-05 § D03; FX-Q02/03/05/12.)
- [ ] **AC-02 — Do not create a mismatched or duplicate loan.** Wrong physical item, cancelled booking or an already-recorded handover produces no new loan and explains the relevant mismatch/current state without revealing another borrower's details. Repeated or concurrent coordinator recording of the same handover creates no second loan for the booking; the known recorded outcome is available to the coordinator. No technical mechanism or coordinator-priority algorithm is mandated; AC-07 supplies the shared first-completed-transition invariant. (FX-SRC-03 § O02, FX-R07; FX-SRC-06 § X02; DD-04.)
- [ ] **AC-03 — Enforce the handover boundary.** A member cannot record handover, even for their own booking, including by bypassing a control; the denied attempt creates no loan and leaves the booking unchanged. Desk access does not grant another-member booking editing, membership changes, eligibility override or condition clearance. (FX-SRC-03 § O02/O05, FX-R08/20; FX-SRC-06 § X02; SRC-06 § A01.)
- [ ] **AC-04 — Distinguish failed from uncertain recording.** A known failure/refusal before completion leaves the targeted booking/loan facts unchanged and does not claim handover recorded. If completion is uncertain, do not assert success or unchanged state; reconcile the selected booking's known outcome before inviting another recording, respecting AC-02. (FX-SRC-06 § X05, FX-R21.)

## Dependencies versus readiness

KD-ST-001 supplies the confirmed booking; KD-ST-005 is a useful way to locate it, not proof of eligibility or a mandatory predecessor interface. This story creates loan facts consumed by KD-ST-007/008/009/011/012. DD-02/03/04 settle the former eligibility/identity/timing/race policy gaps for this scope. Actual adapters or controlled fakes, actor/member mapping and once-only transitions remain engineering prerequisites; no membership interface or account setup is supplied.

## Historical v1 open questions — current resolutions below

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q04/05 / FX-C04 | Aisha + Sam for membership evidence; Aisha + Maya for checkout policy: recheck, and what if inactive/unverifiable? | Blocks full handover eligibility, not KD-ST-001's settled booking failures. No override/default go/no-go is chosen. |
| FX-Q03 | Maya: what condition facts prevent collection? | Conditional success cannot waive unresolved condition eligibility. |
| FX-Q02 | Maya + Leon: what happens during concurrent cancellation and handover? | Blocks race outcome; duplicate handover AC does not choose a cancellation winner. |
| FX-Q01/12; O02 gap | Maya + Leon: how are collection timing and borrower identity established, and are proxies ever supported? | Blocks complete physical collection qualification; no proxy proof or early/late window is invented. |

## Traceability

Coverage classification: **New**, explicitly outside booking. AC-01/02 use FX-R07; AC-03 uses FX-R08/20; AC-04 uses FX-R21. I03 and X01 retain the original competing proposals; DD-02/04 now resolve the handover policy, not extra permissions or cancellation cutoff. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked; no handover or identity enforcement was tested.

## Current demo decisions, AC and readiness — v2

- [ ] **AC-05 — Actual qualified collection.** At completion require DD-04: confirmed/uncollected booking, actual transfer explicitly confirmed by the authorized coordinator, actual handover instant within [booking start, booking end), attending member's workshop card member reference matching the booking, and physical asset label matching its item reference. Missing/unreadable/mismatched proof, wrong borrower/item, early/late/proxy/substitute attempts are explained and create no loan or booking change. Retain no card image or extra card number.
- [ ] **AC-06 — Current membership and condition.** Obtain a new operation-current authoritative membership result under DD-02 and re-evaluate DD-03's current lendable/no-restriction/no-outstanding-loan facts, independently of queue/preparation/booking checks. Only active plus known qualified item permits completion. Inactive, unable-to-verify, known unavailable and unknown qualification are separately explained, with no loan/new collected outcome and existing records unchanged. No override, training gate, receipt shortcut or condition clearance operation.
- [ ] **AC-07 — First completed transition wins.** Apply DD-04 to same-booking cancellation/handover races: cancellation first means handover refused as cancelled and no loan; handover first means the booking is collected with one linked loan and cancellation cannot change it or its loan. Concurrent/repeated handover yields exactly one loan and shows the known result; preparation grants no lock. Preserve AC-04's uncertainty/reconciliation branch, not a blind retry or claimed unchanged state.
- [ ] **AC-08 — Explicit due fact and minimal result.** Success records actual handover instant, one outstanding loan linked to the exact booking/member/item and an explicit due obligation equal to the resolved booking-end instant at completion (DD-07). Show exactly DD-05's KD006 fields with DD-01 zone/offset; inherited collection contact access ends on collection, cancellation or booking end, with unavailable-for-task treatment and rechecks on stale reads/actions. Due is a retained loan fact, not later rederived, editable here or an overdue classification.
- [ ] **AC-09 — Consuming access and interaction.** Apply DD-05/08: only authorized desk coordinators may read this cross-borrower context or record handover, including through replaced references/bypassed controls; unauthorized attempts expose no protected details and change nothing. Use descriptive keyboard-operable controls, visible focus and text outcomes. Do not expose membership history, internal assessments or other fields outside the handover allowance.

| Historical question | Current simulated resolution | AC trace |
|---|---|---|
| FX-Q04/05 / FX-C04 | DD-02 names authority/link/current operation obligation, active only and fail closed; no override | AC-06 |
| FX-Q03 | DD-03 qualification consumption, restriction/outstanding/unknown outcomes | AC-06 |
| FX-Q02 | DD-04 first completed transition wins, missed booking unchanged | AC-07; KD004 eligibility/cutoff remains Backlog |
| FX-Q01/12; O02 identity/timing gap | DD-01/04 exact interval/card/asset match; no early/late/proxy/substitute | AC-05/08 |

DD-05/07/08 → AC-08/09 also settle fields, due fact and bounded interaction. FX-R07/08/20/21 are adopted for this scope as refined here. **Ready** requirements; actual membership/qualification adapters or controlled fakes, authenticated actor/member mapping and once-only state transition engineering remain prerequisites to execution. Their absence is not claimed resolved by a live service or by implemented KD009/010.
