# Prepare the collection workload

Local reference: **KD-ST-005**. Version 2, 2026-10-18.
Maturity: **Ready — fictional requirements only**, not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v1 questions retain their original impacts; the current resolution table supersedes them for this scope.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-005 (#6)](https://github.com/JustinS95/KitDesk/issues/6), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary and value

**As a** desk coordinator, **I want to** inspect collections for a chosen interval, **so that** I prepare the correct physical items and can contact their borrowing members for that lending task.

Two similar drills need distinct item labels. A row opened before cancellation is not permission to hand an item over. Evidence: [FX-SRC-03 § O01/O05](../../sources/expansion-01/03-lending-operations-workshop.md), with [FX-SRC-05 § D03](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R06/20 are adopted as refined by DD-01/04/05/06/08. This is a collection workload, not an approval queue or membership directory. Handover belongs to KD-ST-006. AC-05–08 specify inclusion, exact task fields/contact lifetime and interaction. No default “today”, export, print or staff override is added.

## Acceptance criteria

- [ ] **AC-01 — Inspect a chosen workload.** Given a valid chosen collection interval, a coordinator can inspect confirmed, not-yet-collected bookings selected under AC-05, with physical item identity, requested interval, borrowing member and operational contact access limited to collection needs under AC-06. Selecting a record opens that collection context, not a general membership profile. (FX-SRC-03 § O01, FX-R06; FX-SRC-05 § D03; DD-01/05/06.)
- [ ] **AC-02 — Respect current collection state.** Cancelled or already collected bookings are not actionable collections. A stale row cannot authorize handover; when the current state is obtained it can explain that collection is no longer eligible rather than offering that row as authority. No approval or booking-editing operation is granted by queue access. (FX-SRC-03 § O01/O05, FX-R06/20.)
- [ ] **AC-03 — Distinguish empty and unavailable.** No collections for the chosen interval is distinguishable from inability to obtain the workload. (FX-SRC-03 § O01, FX-R06.)
- [ ] **AC-04 — Keep operational data within its task.** Members cannot read the desk queue or its member/contact details, including through substituted record references or bypassed controls. Queue access does not expose a general membership directory or unrelated lending history. (FX-SRC-03 § O01/O05, FX-R06/20; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-001 supplies confirmed bookings. Cancellation and handover outcomes from KD-ST-004/006 affect queue membership; explicit fixtures can cover those branches without delivering all mutation workflows. KD-ST-006 must establish eligibility independently of a stale row. DD-01/05/06 settle time semantics and privacy fields; records and access enforcement remain engineering prerequisites.

## Historical v1 open questions — current resolutions below

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q01 | Maya + Leon; time-zone owner unconfirmed: what interval and date-boundary rules apply? | Blocks exhaustive queue inclusion/boundary criteria, not the chosen-interval concept. |
| FX-Q10 | Aisha: which contact fields are necessary and retained for collection? | Blocks final field-level access expectations; no phone/email fields are invented. |
| FX-Q02/12 | Maya + Leon: what happens to missed, early, late or proxy collections? | No new queue lifecycle or collection right is inferred. |
| FX-Q11 | Leon with missing accessibility participants: what desk/assisted interactions are needed? | Usability and accessibility remain unverified. |

## Traceability

Coverage classification: **New** operational read scope; no manual decision slice is restored. AC-01–04 use FX-R06; AC-02/04 use FX-R20, at O01/O05. See [expanded traceability](../requirements/Expansion_01_Traceability.md). Criteria are unchecked candidates, not evidence of a live queue.

## Current demo decisions, AC and readiness — v2

- [ ] **AC-05 — Exact queue inclusion.** Apply DD-01's Europe/London/DST and valid start/end rules, with past queue intervals allowed. Include confirmed/uncollected bookings with booking start >= queue start and < queue end, within DD-06's booking-history window; exclude at/after 365 elapsed days from its defined anchor. Order start then reference ascending with all matches. Explain invalid input without claiming empty data. A missed booking is not auto-cancelled; outside-interval handover is refused by KD006, not silently authorized by queue inclusion. No default today or early/late/proxy entitlement.
- [ ] **AC-06 — Minimal task data.** Show exactly DD-05's KD005 fields: booking/item references and item name, interval/outcome, borrower member reference/display name and recorded email/phone if present. Missing contact is not recorded, not fabricated or a denial of collection. Contact access ends at booking end or earlier cancellation/collection; a retained missed-booking row shows contact unavailable for this task, not falsely not recorded. Recheck eligibility on further reads/actions from a stale view; no contacts after task qualification ends.
- [ ] **AC-07 — Actor and lifecycle consistency.** Only authorized coordinators may read this queue/detail; non-desk actors including members are denied, including bypassed/replaced references, without protected detail or record changes. DD-04's known cancellation/collected transitions remove actionable collection; preparation grants no lock or handover authority. No directory, unrelated history, approval, booking edit, override or internal condition notes.
- [ ] **AC-08 — Bounded interaction.** Apply DD-08's descriptive controls, keyboard operation, visible focus and text results/validation/denial, without claiming research or formal conformance.

| Historical question | Current simulated resolution | AC trace |
|---|---|---|
| FX-Q01 | DD-01 exact interval inclusion/clock | AC-01/05 |
| FX-Q10 | DD-05 exact contact fields; DD-06 task-lifetime exposure | AC-01/04/06/07 |
| FX-Q02/12 | DD-04 missed booking unchanged, timing/proxy restrictions and race invariant | AC-02/05/07; KD004 cutoff/remedy remains deferred |
| FX-Q11 | DD-08 bounded interaction expectations | AC-08 |

FX-R06/20 are adopted for this task-scoped read story as refined above. **Ready** requirements; bookings/contact fixtures, authentication/access implementation and interaction verification remain engineering work. KD006, not a queue row, establishes current handover eligibility.
