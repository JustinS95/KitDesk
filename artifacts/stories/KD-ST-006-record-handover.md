# Record actual equipment handover

Local reference: **KD-ST-006**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for collection eligibility, identity and competing cancellation.

## Summary and value

**As a** desk coordinator, **I want to** record an eligible actual handover once, **so that** the confirmed reservation becomes an accurate record of who physically has that item.

Selecting a booking is not collection. A different drill of the same model is not an authorized substitute. Evidence: [FX-SRC-03 § O02/O05](../../sources/expansion-01/03-lending-operations-workshop.md), [FX-SRC-06 § X02/X05](../../sources/expansion-01/06-staged-exception-observations.md), [FX-SRC-07 § I03](../../sources/expansion-01/07-membership-readiness-brief.md).

## Scope and authority

FX-R07/08/20/21 are **author-defined synthetic premises, review pending**. Success below requires collection eligibility explicitly established for the example; confirmation at booking does not prove checkout eligibility. No training gate, override, substitution, membership change, approval, walk-in or proxy-collection right is introduced.

## Acceptance criteria

- [ ] **AC-01 — Link actual possession.** Given a confirmed, uncollected booking with collection eligibility explicitly established and the correct physical item actually handed to the correct borrowing member, a coordinator can record one outstanding actual loan linked to that booking, member and physical item, retaining the actual handover fact. The booking is known as collected and the completed result identifies its linked loan. No loan is created merely by selecting/preparing the collection. (FX-SRC-03 § O02, FX-R07; FX-SRC-05 § D03; FX-Q02/03/05/12.)
- [ ] **AC-02 — Do not create a mismatched or duplicate loan.** Wrong physical item, cancelled booking or an already-recorded handover produces no new loan and explains the relevant mismatch/current state without revealing another borrower's details. Repeated or concurrent coordinator recording of the same handover creates no second loan for the booking; the known recorded outcome is available to the coordinator. No technical mechanism or winning order is mandated. (FX-SRC-03 § O02, FX-R07; FX-SRC-06 § X02.)
- [ ] **AC-03 — Enforce the handover boundary.** A member cannot record handover, even for their own booking, including by bypassing a control; the denied attempt creates no loan and leaves the booking unchanged. Desk access does not grant another-member booking editing, membership changes, eligibility override or condition clearance. (FX-SRC-03 § O02/O05, FX-R08/20; FX-SRC-06 § X02; SRC-06 § A01.)
- [ ] **AC-04 — Distinguish failed from uncertain recording.** A known failure/refusal before completion leaves the targeted booking/loan facts unchanged and does not claim handover recorded. If completion is uncertain, do not assert success or unchanged state; reconcile the selected booking's known outcome before inviting another recording, respecting AC-02. (FX-SRC-06 § X05, FX-R21.)

## Dependencies versus readiness

KD-ST-001 supplies the confirmed booking; KD-ST-005 is a useful way to locate it, not proof of eligibility or a mandatory predecessor interface. This story creates loan facts consumed by KD-ST-007/008/009/011/012. Clean eligible-path and duplicate-recording reasoning are useful now. FX-Q03/05 and identity/timing/race gaps prevent full operational readiness; no membership interface or account setup is supplied.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q04/05 / FX-C04 | Aisha + Sam for membership evidence; Aisha + Maya for checkout policy: recheck, and what if inactive/unverifiable? | Blocks full handover eligibility, not KD-ST-001's settled booking failures. No override/default go/no-go is chosen. |
| FX-Q03 | Maya: what condition facts prevent collection? | Conditional success cannot waive unresolved condition eligibility. |
| FX-Q02 | Maya + Leon: what happens during concurrent cancellation and handover? | Blocks race outcome; duplicate handover AC does not choose a cancellation winner. |
| FX-Q01/12; O02 gap | Maya + Leon: how are collection timing and borrower identity established, and are proxies ever supported? | Blocks complete physical collection qualification; no proxy proof or early/late window is invented. |

## Traceability

Coverage classification: **New**, explicitly outside booking. AC-01/02 use FX-R07; AC-03 uses FX-R08/20; AC-04 uses FX-R21. I03 and X01 remain unresolved eligibility/race evidence, not extra permissions. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked; no handover or identity enforcement was tested.
