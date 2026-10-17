# KD-ST-001 — Acceptance-criteria refinement proposal

Date: 2026-10-16. Status: **approved and applied to canonical story version 2**. User approval: “Sounds good” in response to the request to apply this proposal. Proposal text below is preserved as the change baseline; its original next-action statements are historical.

Baseline: [KD-ST-001 v1](../stories/KD-ST-001-book-available-equipment.md), AC-01–AC-06. Decision sources: initial intake UD-01–UD-04 and [AC-trial decisions UD-05–UD-08](../discovery/Booking_Decisions_AC_Trial_20261016.md). Original privacy source: SRC-02 v1 T03. This is text review, not application testing or independent verification.

## Findings and proposed changes

| Existing criterion | Finding | Proposed treatment / source |
|---|---|---|
| AC-01 | “Applicable eligibility rules” leaves the successful precondition undefined. | Replace with verified active membership; explicitly exclude training checks for release one (UD-06). Retain immediate confirmation and no pending/manual approval (UD-01/04). |
| AC-02 | Reservation outcome lacks the now-confirmed separation rule. | Add at least 30 minutes between bookings of the same item (UD-05); preserve actual requested booking interval. |
| AC-03 | State outcome exists but denied feedback is unspecified. | Add active-membership explanation (UD-08). |
| AC-04 | Existing conflict and simultaneous requests are separate test branches. | Retain existing conflict in AC-04, extend to inspection gap and approved failure feedback (UD-05/08); move simultaneous-request invariant to AC-07 without losing it. |
| AC-05 | “Cannot view another booking as their own” could permit reading it under someone else's name. | Strengthen to cannot view another member's booking details, matching SRC-02 T03. Keep the requesting member's item/interval confirmation. No UI-only enforcement or exact denial message is assumed. |
| AC-06 | Protecting other borrowers' names/contact details remains valid. | Preserve unchanged meaning across availability and failed booking outcomes (SRC-02 T03). |
| New AC-08 | Membership verification failure now has an approved outcome. | Prevent confirmation/reservation and explain inability to verify (UD-07/08); do not confuse unverified with inactive. |

## Proposed replacement criteria

- [ ] **AC-01 — Immediate booking confirmation.** Given the member's membership has been verified as active and the selected item is available for the requested interval with the inspection separation in AC-02, when the member submits the booking request, it immediately becomes a confirmed booking without staff approval or a separate pending stage. The member sees confirmation in the portal. Training checks are not required for release one.
- [ ] **AC-02 — Reservation and inspection separation.** A confirmed booking reserves its selected physical item for the requested interval. Confirmed bookings of the same item must not overlap and must leave at least 30 minutes between the earlier booking's end and the later booking's start, regardless of the order in which they were requested. An interval separated by exactly 30 minutes is not rejected on inspection-gap grounds; a shorter separation is insufficient.
- [ ] **AC-03 — Inactive membership.** When a member whose membership is verified as inactive submits a booking request, the portal explains that active membership is required, and no confirmed booking or reservation is created for that request.
- [ ] **AC-04 — Requested interval unavailable.** If the selected item is unavailable for the requested interval at confirmation, including because the request overlaps an existing reservation or fails AC-02's inspection separation, no confirmed booking or reservation is created for the new request. The portal explains that the requested interval is unavailable, and existing reservations remain unchanged.
- [ ] **AC-05 — Own booking visibility.** The requesting member can view their booking confirmation with the selected item and requested interval. A member cannot view another member's booking details.
- [ ] **AC-06 — Protect other borrowers' details.** Availability and booking-outcome information presented to a member does not disclose another member's name or contact details, including when a reservation prevents the requested booking.
- [ ] **AC-07 — Simultaneous conflicting requests.** When otherwise eligible members simultaneously request the same physical item for intervals that overlap or fail AC-02's inspection separation, the resulting confirmed bookings must still satisfy AC-02. Requests that cannot be confirmed because of the competing reservation receive AC-04's outcome. No winning-request order or tie-break mechanism is prescribed.
- [ ] **AC-08 — Membership cannot be verified.** When membership cannot be verified for a booking request, no confirmed booking or reservation is created for that request. The portal explains that eligibility could not be verified; it does not represent that outcome as a confirmed booking or as proof of inactive membership.

Exact message copy is not mandated. “Immediately” preserves the confirmed no-approval/no-pending workflow, not an invented response-time SLA. Examples using 10:00/10:30 illustrate the duration in one consistent clock context; a production time-zone policy remains unresolved.

## Proposed supporting updates, only after approval

- Preserve story ID, filename and existing AC-01–AC-06 references; add AC-07/08 and increment the story version.
- Link UD-05–UD-08. Update summary/context, traceability and questions to remove obsolete training, gap-duration and membership-failure blockers; do not leave contradictory provisional notes alongside the new criteria.
- Retain open questions about time zone, valid date/time choices, full equipment conditions, checkout/override rules and reservation release. Damage clearance is not automatically granted by a 30-minute gap.
- Refresh the bounded consistency review against the changed story, labeling its earlier v1 findings as historical rather than silently treating them as current.

## Coverage and readiness

Covered in proposed criteria: success/state outcome (AC-01/02), inactive denial (AC-03), booking conflict and feedback (AC-04), own-record access and protected data (AC-05/06), simultaneous conflicts (AC-07), membership integration failure outcome (AC-08). Time boundary is partly specified by UD-05; time zone, date validation and complete equipment-condition rules remain unresolved with the owners identified in the story.

Not applicable to this slice: editing, deletion, search matching/pagination, configuration administration and public API obligations. Duplicate submission/retry behavior has not been specified; it is an unexplored scenario, not an automatically approved idempotency requirement.

Review against UD-01–UD-08: no staff approval, pending state, training condition, skipped membership verification, guessed response codes or implementation choices are added. Thirty minutes applies between reservations, not as an unapproved extension to the member's booked interval. No new cross-story claims can be verified because no other stories exist in the selected store.

These criteria are more precise, not a declaration of full implementation readiness. Next action: user reviews proposed wording before the canonical story is updated. All boxes remain unchecked; no application tests ran.
