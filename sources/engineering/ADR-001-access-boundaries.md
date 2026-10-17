# SRC-06 — ADR-001: Enforce access beyond the UI

Status: accepted **within the fictional scenario**, 2026-10-07, by Sam Ortiz. This is a technical convention, not an authorization grant or real implementation claim.

## A01 — Decision

Protected operations and record reads must enforce the applicable approved actor and record-scope rules even when the UI control is bypassed. Hiding a button is not sufficient access enforcement. User-visible failures must not expose another member's personal data.

## A02 — Limits

This ADR does not define which staff may approve, eligibility overrides, cancellation policy, a role inheritance model, endpoint paths, response schemas or exact error strings. Business permission decisions still need their actual owner.

## A03 — Implementation status

No repository, application, authentication provider, framework, selectors or executable API contract has been supplied. Do not infer these from this ADR or write runnable automation using guessed routes.
