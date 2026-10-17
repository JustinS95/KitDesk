# FX-SRC-05 — Synthetic text design revision

Version 1. Scenario date: 2026-10-24. **Invented text-only design, not a rendered UI, Figma inspection or approved interaction contract.** This revision is a source candidate, not implementation. FX-R references inherit the [pack's review-pending authority](README.md); controls/labels alone confer no permission. No routes, selectors, endpoints or exact copy are supplied.

## D01 — Equipment discovery and item view

Candidate content: search by equipment name/item identifier; category choice; individually lendable item cards with name, item label and brief description. Item detail includes listed parts. Interval context is visible when availability is shown for a requested interval.

Candidate outcomes: matching results, no matches, catalog unavailable; interval available, unavailable or unable to determine. Do not turn an unknown response into Available. Item discovery does not reserve equipment. Availability explanations must not name another borrower. No-match recovery could offer changing the query/category; that is a design proposal, not a mandated suggestion algorithm. Supports FX-R01/02; FX-Q01/03/11 remain.

## D02 — Own bookings

Candidate content: own item identity, requested interval and known confirmed/cancelled/collected outcome, with detail and linked actual loan when present. No Pending/Approve/Reject controls. Those were in historical SRC-05 and are deliberately not carried forward.

Candidate cancellation flow: show the selected own booking, ask the member to confirm the intended cancellation, then display completed, not eligible, no longer in expected state or uncertain outcome as applicable. The extra confirmation interaction is only a proposal. Showing Cancel everywhere is not a policy decision; cutoff/race behavior stays FX-Q02. No self-service cancellation for a collected loan. Supports FX-R03–05/21.

## D03 — Collection workspace

Candidate content: user-chosen collection interval, confirmed uncollected bookings, physical item, member identity and operational contact access. Distinct empty/error outcome. Selecting a row opens that booking's collection context, not a membership profile. A stale row is not eligibility evidence.

Candidate handover summary: selected item label, borrower, requested interval and relevant collection facts; record actual handover action only for the permitted coordinator. Show known completed collection/linked loan after success. Wrong-item/current-state feedback must not invite an implicit substitution or override. Membership/condition status cannot be designed as a green check before FX-Q03/05 is resolved. Supports FX-R06–08/20/21.

## D04 — Own loans and member problem report

Candidate content: own outstanding and returned loans, item, linked booking, recorded handover/return, due obligation only when established. Separate recorded receipt from ongoing condition assessment. No staff contact directory, other members' loans or self-return action.

For an outstanding own loan, a candidate report form accepts a problem description and distinguishes confirmed report receipt from failed/uncertain submission. The reported content can be shown back to its author. Do not display “staff alerted”, response time or safety instructions without evidence for FX-Q13. A report is not a recorded return. Internal assessment notes are not automatically copied into the member view. Supports FX-R09/18/21.

## D05 — Desk loan lookup and return intake

Candidate content: outstanding actual-loan search by item/borrower, results with item/borrower/recorded handover and known due obligation, open the selected actual loan. No match differs from retrieval failure; no broad membership browse.

Return intake emphasizes the physical item and outstanding loan, related member report if present, receipt and condition observation. Proposed routine/damage choice supports different outcomes, not two technical implementations. Completed receipt shows the known returned loan; damage adds a related condition case. Repeated/already-returned handling shows current facts without another return. Partial-kit, wrong-item and correction interactions have no chosen design because FX-Q09 is open. Supports FX-R10–13/19–21.

## D06 — Condition review workspace

Candidate content for the separately designated fictional reviewer: open condition cases by item, reported concern, staff receipt observation, related actual-loan context only where relevant to the assessment. Review action records an assessment and either retains the restriction or clears that condition case.

Tempting label deliberately rejected: “Mark available”. Clearing a case does not itself establish canonical bookability, cancel a future reservation or reopen a returned loan. Ordinary desk actor may see a related condition status for their lending task but does not gain clearance action from the dashboard. The exact assessment fields and actual authority remain FX-Q08/10. Supports FX-R13–15/20.

## D07 — Overdue workload

Candidate content: outstanding loans classified overdue under an explicitly assumed policy, item, borrower, known due obligation and actual loan link. Empty workload differs from unavailable classification. A returned loan drops out of the outstanding workload even while a condition case stays open.

There is no “Send all reminders”, daily schedule, export or member-accessible overdue board. Clock, threshold, recipients and channel are unanswered FX-Q06/07. Supports FX-R16/17, not a calculated-time oracle.

## D08 — Coverage limitations

This text supplies information/state candidates only. No layout, color contrast, keyboard order, screen-reader behavior, responsive behavior, visual approval or executable accessibility claim exists. Denied access, stale records, unavailable data and uncertain completion must be analyzed with their capability; exact UI copy and transport errors are not specified. If a prototype later reintroduces approval, email or unrestricted staff actions, compare it against source authority rather than treating the new control as consent.
