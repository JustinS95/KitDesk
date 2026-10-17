# Find an outstanding loan for desk work

Local reference: **KD-ST-008**. Candidate pending user review, version 1.
Maturity: **draft complete under stated fixture premises** for bounded operational lookup, with matching/field details still open.

## Summary and value

**As a** desk coordinator, **I want to** locate the outstanding actual loan by item or borrower, **so that** I can receive a tool even when the member cannot recall the booking date.

The loan need not be overdue. Searching cancelled and future bookings would not establish who actually has the drill. Evidence: [FX-SRC-03 § O03/O05](../../sources/expansion-01/03-lending-operations-workshop.md), [FX-SRC-05 § D05](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R10/19/20 are **author-defined synthetic premises, review pending**. This is a lending-task lookup, not membership browsing, returned-history search, overdue classification or correction authority. No exact borrower-search matching rule or contact-field list is adopted.

## Acceptance criteria

- [ ] **AC-01 — Locate actual outstanding records.** A coordinator undertaking a lending task can locate outstanding actual loans by physical item identifier or borrowing member, see the matching physical item, borrower, linked booking and recorded handover, and open the selected actual loan for return intake. A known due obligation may be shown without deriving a new one. A not-yet-overdue outstanding loan remains findable. (FX-SRC-03 § O03, FX-R10.)
- [ ] **AC-02 — Bound and explain the result.** Results contain outstanding lending records, not every membership record or unrelated returned history. A completed lookup with no matches has a distinct outcome from inability to obtain results. (FX-SRC-03 § O03, FX-R10.)
- [ ] **AC-03 — Keep the report attached to its loan.** Related member problem reports are visible in that selected loan's lending context as member-reported content, not verified damage or physical receipt. They do not extend staff access to unrelated records or themselves close the loan. (FX-SRC-08 § C04, FX-R19; FX-SRC-03 § O05, FX-R20.)
- [ ] **AC-04 — Protect cross-borrower access.** Members cannot use the staff cross-borrower search or obtain its other-member details by replacing a reference or bypassing a control. Staff lookup access grants no general directory, booking edit, due-date change, historical correction or override operation. (FX-SRC-03 § O03/O05, FX-R10/20; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-006 supplies actual loans; this lookup does not depend on KD-ST-011 or an overdue clock. KD-ST-012 supplies reports when present, not a prerequisite to finding an unreported loan. KD-ST-009 consumes the selected loan for return. Known records permit useful review while exact borrower matching and fields remain unresolved; no working search service or usable data connection is claimed.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| O03 gap | Maya with Aisha on privacy: what borrower matching is appropriate? | Blocks exact ambiguous/partial-name search assertions, not the supported lookup purpose. |
| FX-Q10 | Aisha: what contact fields, sensitive report handling and retention are necessary? | No extra contact fields or unrelated notes are promised. Blocks exhaustive field-level privacy criteria. |
| FX-Q06 | Maya + Leon: what establishes the due obligation? | Known-fact display only; lookup still works without overdue classification. |

## Traceability

Coverage classification: **New**, independently useful before overdue and without booking-date knowledge. AC-01/02/04 use FX-R10; AC-03 uses FX-R19; AC-03/04 use FX-R20. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked; draft completeness is not a claim of complete search design or verified access.
