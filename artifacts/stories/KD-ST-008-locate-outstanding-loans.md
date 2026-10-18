# Find an outstanding loan for desk work

Local reference: **KD-ST-008**. Version 2, 2026-10-18.
Maturity: **Ready — fictional requirements only**, not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v1 questions retain their original impacts; the current resolution table supersedes them for this scope.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-008 (#9)](https://github.com/JustinS95/KitDesk/issues/9), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary and value

**As a** desk coordinator, **I want to** locate the outstanding actual loan by item or borrower, **so that** I can receive a tool even when the member cannot recall the booking date.

The loan need not be overdue. Searching cancelled and future bookings would not establish who actually has the drill. Evidence: [FX-SRC-03 § O03/O05](../../sources/expansion-01/03-lending-operations-workshop.md), [FX-SRC-05 § D05](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R10/19/20 are adopted as refined by DD-05/06/07/08. This is a lending-task lookup, not membership browsing, returned-history search, overdue classification or correction authority. AC-05–08 specify exact item/borrower-reference matching, task fields/report content and interaction.

## Acceptance criteria

- [ ] **AC-01 — Locate actual outstanding records.** A coordinator undertaking a lending task can locate outstanding actual loans by physical item identifier or borrowing member, see the matching physical item, borrower, linked booking and recorded handover, and open the selected actual loan for return intake. A known due obligation may be shown without deriving a new one. A not-yet-overdue outstanding loan remains findable. (FX-SRC-03 § O03, FX-R10.)
- [ ] **AC-02 — Bound and explain the result.** Results contain outstanding lending records, not every membership record or unrelated returned history. A completed lookup with no matches has a distinct outcome from inability to obtain results. (FX-SRC-03 § O03, FX-R10.)
- [ ] **AC-03 — Keep the report attached to its loan.** Related member problem reports are visible in that selected loan's lending context as member-reported content, not verified damage or physical receipt. They do not extend staff access to unrelated records or themselves close the loan. (FX-SRC-08 § C04, FX-R19; FX-SRC-03 § O05, FX-R20.)
- [ ] **AC-04 — Protect cross-borrower access.** Members cannot use the staff cross-borrower search or obtain its other-member details by replacing a reference or bypassing a control. Staff lookup access grants no general directory, booking edit, due-date change, historical correction or override operation. (FX-SRC-03 § O03/O05, FX-R10/20; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-006 supplies actual loans; this lookup does not depend on KD-ST-011 or an overdue clock. KD-ST-012 supplies reports when present, not a prerequisite to finding an unreported loan; explicit report fixtures can cover that optional branch. KD-ST-009 consumes the selected loan for return. DD-05/06 settle matching/fields; no working search service or usable data connection is claimed.

## Historical v1 open questions — current resolutions below

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| O03 gap | Maya with Aisha on privacy: what borrower matching is appropriate? | Blocks exact ambiguous/partial-name search assertions, not the supported lookup purpose. |
| FX-Q10 | Aisha: what contact fields, sensitive report handling and retention are necessary? | No extra contact fields or unrelated notes are promised. Blocks exhaustive field-level privacy criteria. |
| FX-Q06 | Maya + Leon: what establishes the due obligation? | Known-fact display only; lookup still works without overdue classification. |

## Traceability

Coverage classification: **New**, independently useful before overdue and without booking-date knowledge. AC-01/02/04 use FX-R10; AC-03 uses FX-R19; AC-03/04 use FX-R20. See [expanded traceability](../requirements/Expansion_01_Traceability.md) and the current DD resolution table below. All AC unchecked; requirements readiness is not verified access or delivered search.

## Current demo decisions, AC and readiness — v2

- [ ] **AC-05 — Exact item/borrower lookup.** Choose item reference or borrower member reference, trim whitespace and apply DD-06's case-insensitive exact whole-reference matching. Empty query prompts for a reference and does not browse all loans; no name/partial/email/phone match or directory suggestions. Return all matching outstanding loans sorted loan-reference ascending, explicitly select one where multiple exist; never auto-select the first. `KD-EQ-001` matches that item's outstanding record, `KD-EQ-00` does not. Returned records do not match; preserve AC-02's distinct no-match/unavailable outcomes.
- [ ] **AC-06 — Exact task fields and due.** Show only DD-05's KD008 loan/item/borrower/contact/booking/handover/status/explicit-due fields, absent optional values as not recorded. DD-07 due is a loan fact displayed in DD-01 zone/offset, not inferred from booking or overdue. Email/phone are task-only read fields, not search keys/directory access. Recheck outstanding task scope on further reads/actions from a stale view; after receipt do not expose the record/contact/report through this outstanding lookup.
- [ ] **AC-07 — Bounded related report content.** For the selected outstanding loan, show only DD-05's related report reference, timestamp, same-borrower author reference and member description as inert text, labelled member-reported, not assessed damage or receipt. No active markup/attachments, internal assessments/moderation notes, unrelated reports or response/notification promise. Existing report fixtures support this optional branch without delivering KD012 submission/moderation.
- [ ] **AC-08 — Actor and interaction boundary.** Only authorized coordinators undertaking the lending task may use cross-borrower lookup/detail, including reference-substitution/bypass paths; other actors are denied without protected detail or changes. Enforce DD-05's field boundary and DD-08's descriptive keyboard controls/focus/text outcomes. Reading gives no editing, receipt, due-change, override or historical-correction right.

| Historical question | Current simulated resolution | AC trace |
|---|---|---|
| O03 matching gap | DD-06 exact reference alternatives, multi-match explicit selection and ordering | AC-01/02/05 |
| FX-Q10 | DD-05 exhaustive contact/report fields, inert reported text; DD-06 task lifetime | AC-03/04/06/07/08 |
| FX-Q06 | DD-07 explicit obligation or not recorded, no overdue classification | AC-01/06 |

FX-R10/19/20 are adopted for this read scope as refined above. **Ready** requirements; outstanding/report fixtures, access enforcement and lookup implementation remain engineering prerequisites. Report capture/moderation/response and receipt implementation remain separate Backlog work; no delivery evidence is claimed by their optional read branches.
