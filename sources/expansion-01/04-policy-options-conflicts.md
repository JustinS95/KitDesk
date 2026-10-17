# FX-SRC-04 — Synthetic policy options and conflict memo

Version 1. Scenario date: 2026-10-23. **Author-created comparison of fictional statements and open options; not minutes of an actual decision.** FX-R04/05/16/17 below are conditional extension premises, review pending. [Authority and register](README.md).

## P01 — Cancellation options, not a chosen cutoff

Historical SRC-02 T04 suggested cancelling pending requests; SRC-03 E02 suggested cancellation until collection. Neither settled a cutoff or handover race. UD automatic booking supersedes pending approval but does not decide cancellation.

Invented Maya: “Let a member cancel while it hasn't left the desk.”

Invented desk colleague: “I'd rather stop cancellation before the collection shift. Otherwise I may have prepared it and be talking to the member while they cancel.”

**FX-R04:** the extension capability concerns a member cancelling their own confirmed booking that has not been handed over, **if eligible under a future agreed cancellation policy**. The member cannot cancel someone else's booking. A collected booking is not cancelled through this interaction and the actual loan remains outstanding. No cutoff instant, grace period, no-show outcome or race winner is established.

Options for FX-Q02: allow until actual handover; impose a pre-collection cutoff; retain desk-assisted cancellation. Each needs a definition of “handover in progress”, what a member observes if eligibility changes, and which operation can complete. None has been selected. A fictional clean eligible path may be used in a provisional draft; it cannot stand in for full policy.

## P02 — Cancellation outcomes under a future policy

**FX-R05:** where cancellation is eligible and completes before any competing handover outcome under that future policy, the booking becomes cancelled and its own reservation ceases to reserve that interval. Other bookings and any actual loans remain unchanged. The member sees cancellation as completed only after that outcome is known. Repeating cancellation of the same cancelled booking does not release another reservation or create a second lifecycle event. A refusal explains that cancellation was not completed; if completion is uncertain, do not claim either successful cancellation or an unchanged record without reconciliation (FX-R21).

Removing a reservation does not promise a new booking will succeed: other reservations, the preserved 30-minute separation and unresolved equipment-condition rules can still matter. A cancellation does not add an alternative booking, notify a waitlist, send email or alter membership. Cutoff-related refusals remain provisional until FX-Q02; do not invent “24 hours” or any other duration.

## P03 — Handover race and no-show boundary

Invented Sam: “We can insist that a single booking not end up both cancelled with its reservation released and handed over as though cancellation hadn't happened. That isn't enough to tell us whether a desk action already in progress should win.”

This is a consistency concern, not an agreed concurrency policy. Candidate discovery prompts: What physical step counts as handover? What if the member cancels after the desk selected the row but before the item leaves? What should the losing actor see? What restores a no-show item's availability, if anything? FX-Q02 needs a role-play decision before definitive race or expiry AC. No temporary holds, automatic cancellation or staff cancellation right is supplied.

## P04 — Overdue is not an agreed clock

Invented Leon: “I'd like to see what's overdue when I open the desk each morning.”

Invented Maya: “Do you mean anything past its return obligation right now, or a list frozen at opening? And a returned item awaiting inspection isn't still out with the member.”

**FX-R16:** for a conditional extension exercise, assume a stated set of outstanding loans has already been classified overdue under an explicitly declared, unresolved policy. A coordinator can view that workload with physical item, borrower, known due obligation and recorded handover, and open the actual loan for desk follow-up. A loan with recorded return no longer belongs to this outstanding-overdue workload even if its item has an open condition case. Empty and unable-to-determine workloads are distinct; inability to classify must not be displayed as “nothing overdue”. No actual threshold, clock, time zone, snapshot time, elapsed-duration display or authoritative classification service exists.

**FX-R17:** the view is for desk lending work, not a member-visible list of borrowers. It does not send reminders, choose recipients, export a weekly report, escalate to a manager or impose a fine. Other member names/contact details must not leak to members through this capability. Contact-field scope remains FX-Q10. “Morning” is a quoted preference, not a schedule.

Options for FX-Q06 include classification at the due instant or at an agreed operational boundary. No grace window is assumed. FX-Q07 separately asks whether any notification capability is in scope; adopting a view does not adopt a delivery channel.

## P05 — Question register

These questions are intentionally unresolved. “Owner” identifies a fictional role to consult, not an actual assignee or authorization. The [pack guide](README.md#conflict-and-question-register) has a compact cross-source register.

| ID | Precise gap and why it matters | Owner / evidence sought |
|---|---|---|
| FX-Q01 | Which zone, ambiguous/nonexistent DST times, permitted dates/durations and interval boundaries apply? Blocks complete booking/queue time criteria, not the known 30-minute minimum. | Maya + Leon; time-zone owner to confirm; worked boundary examples |
| FX-Q02 | What cancellation cutoff and handover-race outcome apply; what happens to uncollected bookings? Blocks definitive cancellation and no-show behavior. | Maya + Leon; conflicting physical-work scenarios in P01–P03 |
| FX-Q03 | Which condition facts prevent booking/collection, what post-return inspection is required, and what happens to future reservations? Blocks full condition-to-availability qualification in KD001 and extensions. | Maya; trace routine, damaged and cleared-item examples without assuming auto-cancellation |
| FX-Q04 | What membership source/states/mapping/freshness establish active status? Blocks actual dependency readiness. UD already supplies inactive/unverifiable booking outcomes. | Aisha + Sam; source evidence and approved examples, not an invented API |
| FX-Q05 | Is membership rechecked at actual handover, and what happens on inactive/unverifiable status then? Blocks full collection eligibility; no staff override follows. | Aisha + Maya; compare uninterrupted versus failed lookup collection |
| FX-Q06 | How is due obligation established and overdue derived, including clocks/DST/disputes? Blocks calculation/boundary assertions and reminder timing. | Maya + Leon; concrete agreed chronology |
| FX-Q07 | Are notifications in launch at all; what events, channels, recipients, consent and failure outcomes? Blocks delivery claims; portal state remains separate. | Leon + Aisha; review necessity before choosing channel |
| FX-Q08 | Who actually may assess/clear a condition restriction, with what evidence and reversal rules? Blocks real authority; FX-R14 is only a fictional exercise designation. | Maya + Leon; delegated authority and example assessment |
| FX-Q09 | How are wrong-item, incomplete-kit, disputed-damage and erroneous-return corrections handled? Blocks these exception branches, not correct-item receipt. | Maya; separate physical receipt, responsibility and correction needs |
| FX-Q10 | Which staff contact fields, note visibility and retention rules apply? Blocks exhaustive privacy/retention criteria; not permission for broad access. | Aisha; field-purpose review of collection, loan and condition views |
| FX-Q11 | Which accessible interactions, supported devices and assisted routes are needed? Current fictional perspectives do not establish usable access. | Leon; identify accessibility participants and needed discovery |
| FX-Q12 | Are walk-ins, proxies, substitutions and loan extensions in scope; how are no-shows treated operationally? Blocks assuming these are supported. | Leon + Maya; separately scoped outcome proposals |
| FX-Q13 | Who receives/acts on member problem reports; what urgency and safety guidance applies? Blocks monitored-response or safety claims. | Maya + Leon; distinguish routine information from emergency handling |
| FX-Q14 | Which outcomes define success and launch priority, with what baseline? Blocks quantified benefit and release-readiness claims. | Leon + Maya; measures and scope comparison, not invented targets |

## P06 — Conflict handling exercise

For FX-C01, preserve historical approval evidence but apply actual UD precedence. For FX-C02/04/05, retain both fictional statements and ask the owner; chronology and majority vote do not decide. FX-C03/06 have explicit author-defined extension premises to permit conditional exercises, but those are not stakeholder resolutions of canonical condition policy or real permissions. If a downstream draft drops the premise labels or question impacts, the apparent certainty is a defect in that draft, not a new decision here.
