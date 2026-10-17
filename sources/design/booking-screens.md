# SRC-05 — Text-only design export

Scenario version: wireframe 0.2, 2026-10-08. Proposed UI, not approved requirements. No Figma URL, node IDs, image, layout geometry or interactive prototype is supplied. Do not claim visual or live inspection.

## D01 — Member equipment list

Visible labels: Search equipment; Category; Available; Unavailable; Request booking.

Example card: Cordless Drill / Item KD-EQ-001 / Available. No explanation of whether availability is for now or a selected future interval. Empty results, loading, error and keyboard behavior are not described.

## D02 — Booking form

Fields: Item (read-only), Collection date/time, Return date/time, Notes (optional). Button: Confirm booking. Success panel: Your booking is confirmed.

This wording does not distinguish submission from desk approval. No validation rules, supported locale, time zone or maximum duration are specified.

## D03 — My bookings

Columns: Item, Dates, Status, Actions. Example rows show Pending and Approved. Both show a Cancel button. No cancellation confirmation, cutoff or concurrent handover behavior is supplied.

## D04 — Desk dashboard

Tabs: Pending requests, Today's collections, On loan, Overdue. Pending row actions: Approve, Reject. Rejection dialog has a Reason text area. On-loan row action: Record return. Return dialog has a Damage noted checkbox and a Notes field.

No unavailable-equipment management screen, denied-access state, conflict message, failed-save state or notification retry screen is supplied. No complete lifecycle diagram exists in this export.
