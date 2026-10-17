# FX-SRC-03 — Synthetic lending operations workshop

Version 1. Scenario date: 2026-10-22. **Invented workshop notes, not observed operations or policy approval.** Participants are fictional Maya, an unnamed desk colleague, Aisha and Sam. FX-R premises are author-defined, review pending; [guide](README.md).

## O01 — Preparing collections

Maya: “I need the confirmed collections for the interval I'm working, not an inbox of requests to approve. Two bookings of similar tools need separate item labels. If one was cancelled while I had the screen open, that row mustn't authorize handing it out.”

Aisha: “The borrowing member's name and operational contact details are for arranging this collection, as in SRC-02 T03. That doesn't make the collection page a searchable membership directory.”

**FX-R06:** a desk coordinator can inspect confirmed, not-yet-collected bookings scheduled for a chosen collection interval, with item identity, requested interval, borrowing member and operational contact details. Cancelled and already collected bookings are not actionable collections. Distinguish an empty workload from inability to obtain it. A stale row may explain that collection is no longer eligible but cannot grant handover. No default “today”, date-boundary rule, phone/email field set, print/export or approval capability is established. Interval interpretation and contact minimization remain FX-Q01/10. Members cannot read the desk queue or its contact details.

## O02 — Actual handover is a separate event

Desk colleague: “I select the booking, compare the physical item label and borrower, and only record it once it actually leaves. Selecting an item is not collection.”

Maya: “What if I have the right model but the wrong physical item? Don't quietly swap the booking to that item. And if another coordinator already recorded collection, I need to know, not create another loan.”

**FX-R07:** in the extension, a coordinator may record actual handover for a confirmed, uncollected booking only when the applicable collection eligibility has been established. The outcome is one actual outstanding loan linked to that booking, member and physical item, with the actual handover fact; the booking is then known as collected. Do not create a loan before actual handover. Wrong item, cancelled booking or already-recorded handover produces no new loan and an explanation of the relevant mismatch/current state without exposing another borrower. Repeating the same handover or concurrent coordinator attempts must not create a second loan for the booking. No winner order or implementation mechanism is supplied.

**FX-R08:** members cannot record handover or return, even against their own booking/loan. Staff handover permission is not a grant to change membership, substitute an item, approve a booking, override eligibility or clear condition restrictions. Identity/proxy-collection proof, condition eligibility, early/late collection and checkout membership recheck are unresolved, not optional checks silently omitted from “eligible”. Conditional successful-path examples cannot establish a universal right to collect (FX-Q02/03/05/12).

## O03 — Finding the actual loan

Desk colleague: “Someone arrives with a tool but doesn't remember the booking date. I need the outstanding loan for that item, or the borrower's actual loans. Searching all bookings gives me old cancellations and future promises.”

**FX-R10:** a coordinator can locate outstanding actual loans by physical item identifier or borrowing member for a lending task, see the matching item, borrower, linked booking and recorded handover, and open the loan for return intake. Where a due obligation is known it may be shown, without guessing how it was derived. Results contain only outstanding lending records, not every membership record or unrelated returned history. No-match and inability-to-obtain-results are distinct. Member search matching and permitted contact fields remain unspecified. Members have their own loan view, not this cross-borrower search. The desk can find a not-yet-overdue loan without relying on an overdue classification.

## O04 — Routine return without a bookability shortcut

Desk colleague, unadopted proposal: “If I note no damage, I'd put it straight on the shelf and show Available. Otherwise aren't we adding another queue?”

Maya: “I physically receive the correct item and record receipt against its outstanding loan. That ends the member having it out. It doesn't certify that every component is fine or that the next reservation can go ahead.”

Desk colleague: “If I click twice, or another coordinator took it first, don't create two returns or move a different loan to returned. I want to see the recorded result.”

**FX-R11:** a coordinator recording receipt must identify the actual outstanding loan and its physical item. Successful return records actual receipt and makes that loan returned, no longer outstanding. A stale or repeated attempt against an already returned loan creates no second return and explains the current state. A mismatched item does not close some other loan; unresolved wrong-item/partial-kit paths require FX-Q09 rather than an invented workaround.

**FX-R12:** the routine path records a return with no damage noted by the coordinator, distinct from damaged receipt in FX-SRC-08. “No damage noted” is not certified safety or automatic bookability. This author-defined extension premise prevents the shelf-ready shortcut in FX-C03; it does not choose an inspection workflow or resolve canonical condition policy. Returning early/late does not rewrite the original requested interval; post-return inspection and future availability remain FX-Q03. Member self-return is not allowed. Members see recorded receipt through FX-R09, not another borrower's return detail.

## O05 — Access and unsupported exceptions

**FX-R20:** extension desk access is limited to the lending records needed for the collection, actual-loan and return tasks above, including related member problem reports. It does not grant editing another member's requested interval, cancelling their booking, changing due obligations, correcting historical records, broad directory access or staff override. Condition reviewer is a separately scoped fixture actor in FX-SRC-08. No role inheritance or production account model exists. Applicable record/actor rules must hold when a UI control is bypassed, following historical SRC-06 A01, without inventing APIs.

Sam: “There is no interface or identity provider to inspect yet. I can describe a denied operation leaving the lending record unchanged; I can't provide real selectors or an authentication setup.”

Unresolved operational items: wrong-item receipt, incomplete kit, borrowed-by-a-friend collection, manual corrections, walk-ins and extensions. Their absence is a readiness limit, not proof they never occur. See FX-Q09/12.
