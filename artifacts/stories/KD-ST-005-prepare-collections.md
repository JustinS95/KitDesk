# Prepare the collection workload

Local reference: **KD-ST-005**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for interval selection and operational contact fields.

## Summary and value

**As a** desk coordinator, **I want to** inspect collections for a chosen interval, **so that** I prepare the correct physical items and can contact their borrowing members for that lending task.

Two similar drills need distinct item labels. A row opened before cancellation is not permission to hand an item over. Evidence: [FX-SRC-03 § O01/O05](../../sources/expansion-01/03-lending-operations-workshop.md), with [FX-SRC-05 § D03](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R06/20 are **author-defined synthetic premises, review pending**. This is a collection workload, not an approval queue or membership directory. Handover belongs to KD-ST-006. No default “today”, export, print, staff override or exact contact-field list is established.

## Acceptance criteria

- [ ] **AC-01 — Inspect a chosen workload.** Given an explicitly interpreted collection interval, a coordinator can inspect confirmed, not-yet-collected bookings scheduled for it, with physical item identity, requested interval, borrowing member and operational contact access limited to collection needs. Exact contact fields await FX-Q10. Selecting a record opens that collection context, not a general membership profile. (FX-SRC-03 § O01, FX-R06; FX-SRC-05 § D03; FX-Q01/10.)
- [ ] **AC-02 — Respect current collection state.** Cancelled or already collected bookings are not actionable collections. A stale row cannot authorize handover; when the current state is obtained it can explain that collection is no longer eligible rather than offering that row as authority. No approval or booking-editing operation is granted by queue access. (FX-SRC-03 § O01/O05, FX-R06/20.)
- [ ] **AC-03 — Distinguish empty and unavailable.** No collections for the chosen interval is distinguishable from inability to obtain the workload. (FX-SRC-03 § O01, FX-R06.)
- [ ] **AC-04 — Keep operational data within its task.** Members cannot read the desk queue or its member/contact details, including through substituted record references or bypassed controls. Queue access does not expose a general membership directory or unrelated lending history. (FX-SRC-03 § O01/O05, FX-R06/20; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-001 supplies confirmed bookings. Cancellation and handover outcomes from KD-ST-004/006 affect queue membership but are not prerequisites for drafting the basic read capability. KD-ST-006 must establish eligibility independently of a stale row. Chosen-interval examples and a minimal purpose-based contact concept allow partial work; they do not settle exact time semantics or privacy fields.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q01 | Maya + Leon; time-zone owner unconfirmed: what interval and date-boundary rules apply? | Blocks exhaustive queue inclusion/boundary criteria, not the chosen-interval concept. |
| FX-Q10 | Aisha: which contact fields are necessary and retained for collection? | Blocks final field-level access expectations; no phone/email fields are invented. |
| FX-Q02/12 | Maya + Leon: what happens to missed, early, late or proxy collections? | No new queue lifecycle or collection right is inferred. |
| FX-Q11 | Leon with missing accessibility participants: what desk/assisted interactions are needed? | Usability and accessibility remain unverified. |

## Traceability

Coverage classification: **New** operational read scope; no manual decision slice is restored. AC-01–04 use FX-R06; AC-02/04 use FX-R20, at O01/O05. See [expanded traceability](../requirements/Expansion_01_Traceability.md). Criteria are unchecked candidates, not evidence of a live queue.
