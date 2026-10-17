# Record an equipment return and any observed damage

Local reference: **KD-ST-009**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for physical exceptions and condition/availability consequences.

## Summary and value

**As a** desk coordinator, **I want to** record receipt against the correct outstanding loan and capture any observed damage, **so that** the member is no longer recorded as holding an item actually returned and condition work can continue separately.

One intake covers a drill returned with no damage noted and a drill returned with casing damage. Damage does not mean the member still has it; receipt does not mean it is shelf-ready. Evidence: [FX-SRC-03 § O04/O05](../../sources/expansion-01/03-lending-operations-workshop.md), [FX-SRC-08 § C01/C04](../../sources/expansion-01/08-condition-return-workshop.md), [FX-SRC-06 § X04/X05](../../sources/expansion-01/06-staged-exception-observations.md).

## Scope and authority

FX-R08/11/12/13/19/20/21 are **author-defined synthetic premises, review pending**. Routine and damaged receipt are branches of one coherent capability, not separate quota-filling stories. Condition assessment is KD-ST-010. No automatic bookability, future-reservation cancellation, fine, fault finding, repair process, wrong-item workaround or historical correction is granted.

## Acceptance criteria

- [ ] **AC-01 — Record actual receipt.** Given the identified outstanding actual loan and correct physical item are received by the coordinator, successful return records the actual receipt and makes that loan returned, no longer outstanding. The coordinator sees the known recorded return. The routine branch records no damage noted, not certified safety or automatic bookability; an early/late receipt does not rewrite the original requested interval. (FX-SRC-03 § O04, FX-R11/12; FX-SRC-05 § D05.)
- [ ] **AC-02 — Initiate condition handling without denying receipt.** On correct-item damaged receipt, the loan becomes returned and a related operational condition case identifies the physical item, receipt context, observed concern and restriction pending review. The outcome does not assert fault, debt, changed membership, booking availability or cancellation of a future reservation. (FX-SRC-08 § C01, FX-R13; FX-Q03.)
- [ ] **AC-03 — Preserve member-reported facts separately.** The coordinator can see the related member problem report as a report during loan/return work. It is not treated as assessed damage, the cause of a later observation or proof of receipt; staff observation is a separate fact. The report alone does not create the damaged-return condition case. (FX-SRC-08 § C04, FX-R19; FX-SRC-06 § X04.)
- [ ] **AC-04 — Protect the actual loan and once-only outcome.** A repeated/stale receipt against an already returned loan creates no second return and explains the known current state; the same damaged receipt creates no duplicate case. A mismatched physical item does not close the selected loan or any other loan through this receipt attempt. Wrong-item/partial-kit resolution remains open rather than an implicit substitution or correction. (FX-SRC-03 § O04, FX-R11; FX-SRC-08 § C01, FX-R13; FX-Q09.)
- [ ] **AC-05 — Restrict receipt authority.** Members cannot record a return, even against their own loan, including through bypassed controls; the refused attempt leaves the loan unchanged. Staff return access stays within the lending task and does not grant historical correction, booking editing or condition clearance. Members see their own recorded receipt through KD-ST-007, not other borrowers' details or internal assessments. (FX-SRC-03 § O02/O04/O05, FX-R08/12/20; FX-SRC-08 § C02, FX-R14; SRC-06 § A01.)
- [ ] **AC-06 — Do not overstate interrupted completion.** Known failure/refusal before completion leaves the targeted facts unchanged and does not claim return/case creation. When completion is uncertain, do not claim successful receipt and case creation or assert unchanged state without reconciliation of the selected record. Repetition must preserve AC-04's once-only outcomes. (FX-SRC-06 § X05, FX-R21; FX-SRC-08 § C01, FX-R13.)

## Dependencies versus readiness

KD-ST-006 supplies the outstanding loan. KD-ST-008 is a useful independent lookup, not a mandated route to return. KD-ST-012 optionally supplies a report. This story produces receipt for KD-ST-007, condition cases for KD-ST-010 and a no-longer-outstanding fact for KD-ST-011. No reverse dependency on condition clearance or overdue classification is required to record known correct-item receipt. FX-Q03/09 block a fully qualified return service, not meaningful receipt/case work under stated premises.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q03 / FX-C03 | Maya: what inspection and condition-to-booking/collection rules apply, including future reservations? | Blocks bookability promises after either branch; no-damage receipt is not clearance. |
| FX-Q09 | Maya: wrong item, partial kit, disputed damage or erroneous return—who records/corrects what? | Blocks those physical/correction branches, not correct complete receipt. |
| FX-Q10 | Aisha: how are sensitive observations/reports minimized and retained? | Blocks exhaustive note visibility/retention; no automatic member exposure of staff notes. |

## Traceability

Coverage classification: **New** return capability; two source candidates merged without dropping damaged receipt. AC-01/04 use FX-R11; AC-01/05 use FX-R12; AC-02/04/06 use FX-R13; AC-03 uses FX-R19; AC-05 uses FX-R08/14/20; AC-06 uses FX-R21. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked; no receipt, case or test outcome is claimed.
