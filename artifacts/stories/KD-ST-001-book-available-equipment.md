# KD-ST-001 — Book available equipment

Status: **Ready — fictional requirements only**. Version: 3, 2026-10-18. Not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v2 questions/review preserve provenance; the current supplement resolves their open impacts and controls where they conflict.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-001 (#1)](https://github.com/JustinS95/KitDesk/issues/1), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary

**As a** member with active membership,
**I want to** book an available equipment item for my requested interval and receive immediate confirmation,
**so that** I know the equipment is reserved for me without waiting for a desk decision.

This story follows the user's scenario decisions [UD-01–UD-04 in the discovery intake](../discovery/Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16) and [UD-05–UD-08 from the AC trial](../discovery/Booking_Decisions_AC_Trial_20261016.md). They replace the original staff-approval flow for launch. A successful request creates a confirmed booking and reservation, not a pending request or a loan. Active membership is sufficient for membership/training eligibility in release one; training checks are excluded. Bookings of the same physical item require at least 30 minutes between them for inspection. Staff handover and return remain separate capabilities.

## Business value

Members obtain a clear booking outcome without an email exchange or manual approval. Reserving the physical item for the booking interval addresses the risk of promising the same equipment to different members (SRC-01 B01; SRC-04 P01). No quantified improvement is asserted.

## Scope

One member booking one individually lendable item for a requested interval. The member can see the resulting confirmation in the portal. How they reach this interaction is not prescribed; discovery/search belongs to KD-ST-002 and booking-history retrieval to KD-ST-003.

No desk-approval step, pending-hold stage, temporary-hold expiry, waitlist, email delivery, payment, staff override, checkout, return or cancellation behavior is introduced. No endpoint, role identifier, database design, field limit or UI wording is mandated.

## Acceptance criteria

AC-01–08 preserve the user-approved v2 refinement; AC-09–12 complete this scope under DD-01–08. All checkboxes are unchecked requirements, not test results.

- [ ] **AC-01 — Immediate booking confirmation.** Given the member's membership has been verified as active and the selected item is available for the requested interval with the inspection separation in AC-02, when the member submits the booking request, it immediately becomes a confirmed booking without staff approval or a separate pending stage. The member sees confirmation in the portal. Training checks are not required for release one.
- [ ] **AC-02 — Reservation and inspection separation.** A confirmed booking reserves its selected physical item for the requested interval. Confirmed bookings of the same item must not overlap and must leave at least 30 minutes between the earlier booking's end and the later booking's start, regardless of the order in which they were requested. An interval separated by exactly 30 minutes is not rejected on inspection-gap grounds; a shorter separation is insufficient.
- [ ] **AC-03 — Inactive membership.** When a member whose membership is verified as inactive submits a booking request, the portal explains that active membership is required, and no confirmed booking or reservation is created for that request.
- [ ] **AC-04 — Requested interval unavailable.** If the selected item is unavailable for the requested interval at confirmation, including because the request overlaps an existing reservation or fails AC-02's inspection separation, no confirmed booking or reservation is created for the new request. The portal explains that the requested interval is unavailable, and existing reservations remain unchanged.
- [ ] **AC-05 — Own booking visibility.** The requesting member can view their booking confirmation with the selected item and requested interval. A member cannot view another member's booking details.
- [ ] **AC-06 — Protect other borrowers' details.** Availability and booking-outcome information presented to a member does not disclose another member's name or contact details, including when a reservation prevents the requested booking.
- [ ] **AC-07 — Simultaneous conflicting requests.** When otherwise eligible members simultaneously request the same physical item for intervals that overlap or fail AC-02's inspection separation, the resulting confirmed bookings must still satisfy AC-02. Requests that cannot be confirmed because of the competing reservation receive AC-04's outcome. No winning-request order or tie-break mechanism is prescribed.
- [ ] **AC-08 — Membership cannot be verified.** When membership cannot be verified for a booking request, no confirmed booking or reservation is created for that request. The portal explains that eligibility could not be verified; it does not represent that outcome as a confirmed booking or as proof of inactive membership.

Exact message copy is not mandated. “Immediately” means no approval wait or pending stage, not a quantified response-time SLA. The inspection gap separates bookings; it does not extend the member's requested booking interval or automatically clear damaged equipment.

## Historical v2 questions and readiness limits — resolved by current supplement

These are not accepted criteria or permission to implement defaults.

| Ref | Question | Owner | Impact |
|---|---|---|---|
| OQ-01 | What time zone and daylight-saving interpretation apply? What date/time selections are permitted? | Maya; time-zone owner to confirm | Blocks complete date/time criteria and tests. The inspection gap is resolved by UD-05: at least 30 minutes, with exactly 30 permitted. Intake Q05 is only partly resolved. |
| OQ-02 | What authoritative information establishes active membership? Are staff overrides ever permitted outside this member flow? | Aisha, with Maya on exceptions | Integration evidence remains unavailable. UD-07/08 resolves the unverified-membership outcome: prevent booking and explain. No override is added to this story; UD-03 does not settle checkout rechecks. |
| OQ-03 | Resolved: training checks are excluded from release one. | User scenario decision UD-06 | No longer a readiness blocker; active membership suffices for membership/training eligibility. |
| OQ-04 | Resolved for the three failure branches: inactive membership, inability to verify membership, and unavailable interval. | User scenario decisions UD-07/08 | AC-03/04/08 specify explanation and no new booking/reservation; AC-04 preserves existing reservations. Exact copy is not mandated. No waitlist, alternative-date suggestion or automatic retry is added. |
| OQ-05 | Which equipment conditions make an item unavailable, and who can restore availability after damage? | Maya | Blocks complete availability qualification, not the conditional available-item outline. Intake Q07. Returning an item must not be assumed to restore availability. |

Cancellation and reservation release rules remain unresolved in intake Q04; this story does not promise cancellation or define reservation expiry. Membership-check mechanics, authentication and actual application interfaces are not supplied. No runnable test readiness is claimed.

## Historical v2 traceability and existing coverage

At initial creation, the compared store `artifacts/stories/` contained only README.md and no existing stories; the original coverage classification was New locally. The v2 refinement updated that same canonical story, not a duplicate. No live ADO coverage comparison is claimed, and no tracking hierarchy or UUID registry has been adopted. This table records v2 coverage; the current DD resolution table below supersedes its unresolved-policy limits.

Source IDs resolve through [sources/INDEX.md](../../sources/INDEX.md). Original sources are version 1; the discovery intake includes the subsequent user decisions.

| Requirement / source locator | Coverage result | Story coverage | Decision status |
|---|---|---|---|
| Automatic confirmation without staff approval or pending stage — intake UD-01, UD-04 | Covered | AC-01 | Confirmed by user role-play; supersedes SRC-02 T02 staff approval |
| Reserve equipment for the requested interval — intake UD-02, UD-04 | Covered | AC-02 | Confirmed by user role-play |
| Active membership at request; training excluded — intake UD-03; AC-trial UD-06 | Covered | AC-01, AC-03 | Confirmed; authoritative integration information remains unresolved |
| Prevent overlapping bookings — SRC-02 T05, applied through UD-01/UD-04 | Covered | AC-02, AC-04, AC-07 | Simultaneous-request branch preserved separately; no tie-break rule invented |
| At least 30 minutes between bookings — AC-trial UD-05 | Covered | AC-01, AC-02, AC-04, AC-07 | Includes exactly-30-minute boundary; time-zone policy unresolved |
| Member sees own booking only — SRC-01 B02; SRC-02 T03/T07; intake UD-04 | Covered | AC-01, AC-05 | Strengthened record boundary; no full list/history scope added |
| Protect another member's name/contact details — SRC-02 T03; intake DI-02 | Covered | AC-06 | Recorded scenario privacy decision |
| Prevent booking when membership cannot be verified — AC-trial UD-07 | Covered | AC-08 | Confirmed by user role-play; distinct from inactive membership |
| Explain three failure outcomes and create no booking — AC-trial UD-08 | Covered | AC-03, AC-04, AC-08 | Confirmed meaning, not exact message copy |

Original staff rejection/reason behavior in SRC-02 T02/T07 is not carried into a newly invented manual approval story. User UD-01/UD-04 replaces that workflow; UD-08 now confirms automatic failure feedback. The lack of a later approval recheck (UD-03) introduces no extra approval step merely to state that a check is omitted.

## Historical v2 review and handoff

One coherent booking story is authored, rather than separate button, validation, reservation or frontend/backend stories. No tasks, assignees, priorities, estimates, tags, parent items or remote mappings are invented.

The user approved applying the [refinement proposal](../reviews/KD-ST-001-AC-refinement-proposal.md) with “Sounds good” in response to the request to apply it. AC-01–AC-06 identities are preserved; the concurrency branch moves from AC-04 to AC-07, and AC-08 adds the newly confirmed verification-failure outcome. Summary, questions and traceability were updated together.

See the [bounded consistency review and v2 follow-up](../reviews/KD-ST-001-draft-review.md). The accepted refinement is not full implementation readiness while the affected questions remain open. This artifact is not proof of implementation, security enforcement or test execution.

## Current demo decisions, AC and readiness — v3

The following unchecked requirements extend AC-01–08 without weakening UD-01–08. References are to the adopted **simulated** checkpoint above, not real stakeholder testimony. Summary and scope remain one booking with no approval, training, override, checkout or cancellation operation.

- [ ] **AC-09 — Validate resolved instants.** Apply DD-01: Europe/London minute-precision start/end, required item/timestamps, start at or after submission and end after start, nonexistent-time rejection and repeated-time offset selection. Invalid/missing/ambiguous input is explained and creates no booking/reservation. Display zone/offset and compare inspection separation in elapsed minutes, exactly 30 accepted in either request order.
- [ ] **AC-10 — Qualify current eligibility.** At confirmation obtain DD-02's operation-current membership determination for the authenticated member reference and DD-03's current item qualification/possession/restriction facts. Only active membership plus explicitly lendable, unrestricted item with no outstanding actual loan permits confirmation, subject to interval reservations. Inactive, unable-to-verify, known unavailable and unable-to-determine qualification are explained distinctly with no new booking/reservation and no existing record changed. No stale previous check, override or return/clearance shortcut permits success.
- [ ] **AC-11 — Bound confirmation data and access.** Show exactly DD-05's KD001 confirmation fields, absent optional facts as not recorded. Apply DD-06's booking visible-history window and outstanding-loan-context exception to later reads. Enforce authenticated own-record read and member submission boundaries even on substituted references/bypassed controls; unauthorized actions reveal no protected details, create no booking and leave existing records unchanged. No condition notes or other-member details are exposed. Inactive membership alone does not deny own retained-record reading.
- [ ] **AC-12 — Bounded accessible interaction.** Apply DD-08's descriptive controls, keyboard operation, visible focus and text outcomes/errors without claiming formal conformance or staff impersonation rights.

| Historical reference | Recorded resolution / AC trace | Remaining prerequisite, not an undecided booking rule |
|---|---|---|
| OQ-01 / intake Q05 | DD-01 → AC-09; AC-02's exact 30-minute rule retained | Implement time selection/validation and boundary fixtures |
| OQ-02 | DD-02 → AC-10/11; authoritative register/member reference, operation-current active only, no override | Real adapter/authentication/freshness mechanics or explicit controlled fake; no live service claimed |
| OQ-03, OQ-04 | UD-06–08 preserved → AC-01/03/04/08 | Implement known feedback branches |
| OQ-05 / intake Q07 | DD-03 → AC-10; known restrictions/non-lendable/outstanding refuse, unknown fails closed | Qualification source/fakes; creation/restoration remains KD009/010, not this mutation |

DD-05/06/08 → AC-11/12 close field/access/visible-history/interaction coverage. DD-04 preserves booking versus loan separation. Cancellation eligibility stays KD004 Backlog, not an added booking right. **Ready** for this bounded fictional requirements scope; implementation, accounts, adapters and test execution remain absent. Prior v2 readiness statements describe that earlier checkpoint only.
