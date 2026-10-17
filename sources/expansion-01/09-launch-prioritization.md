# FX-SRC-09 — Synthetic launch and scope prioritization discussion

Version 1. Scenario date: 2026-10-28. **Invented discussion, not a release commitment, approved backlog, estimate or actual stakeholder consensus.** All candidates remain provisional; [guide and source-to-scenario map](README.md#source-to-scenario-guide-and-next-backlog-derivation).

## L01 — Three competing demonstrations

Leon: “The shortest demonstration is find an item, book it, show my booking, collect and return. I don't want fifteen technical tickets that add up to no usable journey.”

Maya: “That misses the member cancelling, the desk finding a loan when the booking date is forgotten, and what happens when it comes back damaged. We should at least show where those cases stop.”

Aisha: “I'd show whose data each view contains, including a failed attempt to open someone else's booking. A denied read belongs in the capability, not on its own as a feature.”

Author interpretation: a connected backlog can be broader than a single demonstration, without turning every control, validation, failure branch or technical layer into a story. There is no accepted release cut, capacity, deadline, points scale or assignee list. FX-Q14 remains open.

## L02 — Candidate behavior slices, not work-item records

The [guide](README.md#source-to-scenario-guide-and-next-backlog-derivation) maps evidence for 13 total slices, including the existing KD-ST-001 and 12 extension candidates:

- Discover the right physical item and understand interval availability.
- Review own bookings and known lifecycle outcomes.
- Cancel an eligible own booking and release its reservation.
- Prepare the collection workload for a chosen interval.
- Record actual handover to create the loan once.
- View own actual-loan status and recorded receipt.
- Locate outstanding actual loans for desk work.
- Record routine return against the correct loan.
- Record damaged receipt and initiate condition handling.
- Assess a condition case and clear it or retain its restriction.
- Review overdue lending workload under an explicitly assumed classification.
- Report a problem on an own outstanding loan without self-returning.

These have distinct actor outcomes; none is a button/API/frontend/backend split or standalone denial story. Staff loan lookup is useful before a loan is overdue and when its booking details are unknown. Own bookings versus own loans deliberately distinguish reservation from actual possession. Routine and damaged return may be merged if they cannot sensibly be delivered separately; that would leave 12 total slices. Do not pad the count by splitting search, list and detail or individual validation messages.

## L03 — Candidate sequencing, with gates intact

| Learning/drafting group | What it could demonstrate | Gate that is not waived |
|---|---|---|
| Booking baseline plus discovery/own bookings | Find an individually lendable item; retrieve the confirmed reservation privately | KD001 questions stay open; no guessed time/condition defaults |
| Desk collection, actual handover and own loans | Reservation becomes an actual loan, no member self-checkout | FX-Q03/05 and collection identity/timing details limit eligibility |
| Loan lookup, routine/damaged return and condition review | Find possession record, record receipt, keep assessment separate | FX-Q03/08/09/10 limit availability, authority and exception handling |
| Cancellation, overdue view and member problem report | Recovery/information needs around the core journey | FX-Q02/06/13 block full policy; classification/report-response assumptions must remain visible |

This table is a suggested exercise order, not a mandatory architecture or implementation dependency graph. Cancellation may be high member value despite appearing in a later drafting group. Condition questions need discovery before claiming even the core happy path is fully ready.

## L04 — Reminders, exports and overrides are not a quiet phase two promise

Leon: “The old email idea keeps coming back. Could we put it on a later list?”

Facilitator: “We can preserve it as an unresolved candidate without promising a channel or launch. Same for the weekly overdue export. Neither needs a story until you can state its outcome, audience, data boundaries and priority.”

Maya: “And don't add an override to solve every difficult case. Show that the policy is missing.”

No notification delivery, waitlist, staff override, purchasing, financial penalty, transfer, recurrence or public signup is adopted. Unsupported walk-ins/proxies/substitutions/extensions remain FX-Q12, not automatically committed future features. No new hierarchy, remote mapping or fabricated implementation status follows from this discussion.

## L05 — Suggested next discovery and review

For a future authorized role-play, ask Maya about FX-Q01/02/03 with concrete interval, cancellation/handover and return scenarios; Aisha with Maya about FX-Q04/05; Maya/Leon about FX-Q06/08/13 and release priorities. Review FX-Q09/10 before broad note/history requirements. Identify missing accessibility perspectives for FX-Q11. No interviews, messages or operational data collection have occurred or are authorized by this suggestion.

Before writing a requirements synthesis, mark each candidate statement as inherited UD authority, review-pending FX premise, proposal, historical contradiction or open question. Preserve the source locator and impact of the gap. Before writing tests, distinguish an assumed setup/classification from an approved oracle, keep all unsupported outcomes unresolved, and do not claim execution. Before any public publication, review the actual proposed content and obtain separate authorization; local source authorship is not publication permission.
