# See my actual loan status and recorded return

Local reference: **KD-ST-007**. Candidate pending user review, version 1.
Maturity: **draft complete under stated fixture premises** for bounded own-loan visibility, not implementation readiness.

## Summary and value

**As a** member, **I want to** see my actual loans and recorded receipt, **so that** I know whether the desk still records the item as out with me even while condition assessment continues.

A confirmed booking is a reservation, not proof that I collected the drill. A damaged drill can have been received back while its separate condition case remains open. Evidence: [FX-SRC-02 § M04, FX-R09 paragraph](../../sources/expansion-01/02-member-staff-interviews.md), [FX-SRC-05 § D04](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R09 is an **author-defined synthetic premise, review pending**. This is an own actual-loan view, not booking history, self-checkout, self-return, internal condition assessment or an overdue calculator. A due obligation is displayed only where separately established; this draft supplies none.

## Acceptance criteria

- [ ] **AC-01 — Show actual possession facts.** A member can view their own actual loans, distinguishing outstanding from recorded return, with physical item, linked booking, recorded handover and recorded return when present. A booking's confirmation alone does not make a loan appear collected. (FX-SRC-02 § M04, FX-R09.)
- [ ] **AC-02 — Do not invent an obligation or clearance.** A due obligation is shown only when established under an explicitly supplied policy; no overdue calculation is inferred. Recorded receipt is not presented as fault determination, completed condition review or future item bookability, including when a related damage case remains open. (FX-SRC-02 § M04, FX-R09; FX-SRC-06 § X04.)
- [ ] **AC-03 — Protect other records and internal notes.** Members cannot read another member's actual-loan detail by changing a reference. This own-loan view does not expose other borrowers' staff-only contact data or internal condition assessment notes. It offers no member-recorded handover or return; a bypassed member attempt cannot change those facts. (FX-SRC-02 § M04, FX-R09; FX-SRC-03 § O02/O04, FX-R08/12; FX-SRC-06 § X06; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-006 produces actual loans and KD-ST-009 produces recorded return facts; explicit assumed records allow separate review of this read capability. KD-ST-003 links from collected bookings. None of those links makes condition clearance or a due calculation a prerequisite to showing known possession. No empty-list interaction or retrieval-failure wording is supplied by FX-R09; those remain a coverage question rather than invented AC.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q06 | Maya + Leon: how is a due obligation established? | Blocks calculated due/overdue claims; does not block display of a separately known obligation. |
| FX-Q09/10 | Maya for disputes, Aisha for visibility/retention: what condition explanation and retained history may the member see? | No internal notes or indefinite history promise is added; member-facing disputed-condition detail remains outside this bounded draft. |
| M04/D04 coverage gap | Maya with member examples: what should no own loans or unavailable retrieval look like? | Read-state design is incomplete; no message or state behavior is fabricated. |

## Traceability

Coverage classification: **New** actual-loan view, not a duplicate booking confirmation. AC-01/02 use FX-R09; AC-03 uses FX-R09 with FX-R08/12's self-service prohibition. See [expanded traceability](../requirements/Expansion_01_Traceability.md). Draft-complete means the stated known-facts scope is expressed; it does not close the listed coverage gaps or verify software. All AC unchecked.
