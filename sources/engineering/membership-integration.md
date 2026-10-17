# SRC-07 — Membership integration proposal

Status: unapproved technical option, 2026-10-08. Author: Sam Ortiz (fictional).

## I01 — Proposal

KitDesk could consult the existing membership system to determine whether a member is currently eligible to borrow. The team has not verified the available API, identity mapping, freshness guarantees or test environment.

## I02 — Open questions

- What eligibility states exist and what does each permit?
- At which lifecycle points is eligibility rechecked?
- What should the user observe when membership information is unavailable?
- Is a staff override permitted, and if so by whom and with what outcome?

There are no approved URLs, credentials, payloads, timeout values or fallback rules here. A proposed API is not an available dependency merely because its work item is closed.
