# See my actual loan status and recorded return

Local reference: **KD-ST-007**. Version 2, 2026-10-18.
Maturity: **Ready — fictional requirements only**, not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v1 questions retain their original impacts; the current resolution table supersedes them for this scope.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-007 (#8)](https://github.com/JustinS95/KitDesk/issues/8), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary and value

**As a** member, **I want to** see my actual loans and recorded receipt, **so that** I know whether the desk still records the item as out with me even while condition assessment continues.

A confirmed booking is a reservation, not proof that I collected the drill. A damaged drill can have been received back while its separate condition case remains open. Evidence: [FX-SRC-02 § M04, FX-R09 paragraph](../../sources/expansion-01/02-member-staff-interviews.md), [FX-SRC-05 § D04](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R09 is adopted as refined by DD-03/05/06/07/08. This is an own actual-loan view, not booking history, self-checkout, self-return, internal condition assessment or an overdue calculator. DD-07 establishes explicit due creation at handover; this read view displays that loan fact or due not recorded, never a guessed derivation.

## Acceptance criteria

- [ ] **AC-01 — Show actual possession facts.** A member can view their own actual loans, distinguishing outstanding from recorded return, with physical item, linked booking, recorded handover and recorded return when present. A booking's confirmation alone does not make a loan appear collected. (FX-SRC-02 § M04, FX-R09.)
- [ ] **AC-02 — Do not invent an obligation or clearance.** A due obligation is shown only when established under an explicitly supplied policy; no overdue calculation is inferred. Recorded receipt is not presented as fault determination, completed condition review or future item bookability, including when a related damage case remains open. (FX-SRC-02 § M04, FX-R09; FX-SRC-06 § X04.)
- [ ] **AC-03 — Protect other records and internal notes.** Members cannot read another member's actual-loan detail by changing a reference. This own-loan view does not expose other borrowers' staff-only contact data or internal condition assessment notes. It offers no member-recorded handover or return; a bypassed member attempt cannot change those facts. (FX-SRC-02 § M04, FX-R09; FX-SRC-03 § O02/O04, FX-R08/12; FX-SRC-06 § X06; SRC-06 § A01.)

## Dependencies versus readiness

KD-ST-006 produces actual loans and KD-ST-009 produces recorded return facts; explicit fixtures allow separate validation of this read capability without implementing return. KD-ST-003 links from collected bookings. None of those links makes condition clearance or an overdue calculation a prerequisite to showing known possession. DD-06/08 settle empty/unavailable and bounded interaction behavior in AC-06; no exact message wording is mandated.

## Historical v1 open questions — current resolutions below

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q06 | Maya + Leon: how is a due obligation established? | Blocks calculated due/overdue claims; does not block display of a separately known obligation. |
| FX-Q09/10 | Maya for disputes, Aisha for visibility/retention: what condition explanation and retained history may the member see? | No internal notes or indefinite history promise is added; member-facing disputed-condition detail remains outside this bounded draft. |
| M04/D04 coverage gap | Maya with member examples: what should no own loans or unavailable retrieval look like? | Read-state design is incomplete; no message or state behavior is fabricated. |

## Traceability

Coverage classification: **New** actual-loan view, not a duplicate booking confirmation. AC-01/02 use FX-R09; AC-03 uses FX-R09 with FX-R08/12's self-service prohibition. See [expanded traceability](../requirements/Expansion_01_Traceability.md) and the DD resolution table below for closure of this scope's former coverage gaps. All AC are unchecked; no software verification is claimed.

## Current demo decisions, AC and readiness — v2

- [ ] **AC-04 — Exact own facts, history and order.** Apply DD-05/06's exhaustive KD007 field list: loan/own-member/item references and item name, linked booking, actual handover, Outstanding/Returned, receipt if recorded and explicit due if recorded. Missing optional facts show not recorded. Outstanding loans remain visible while outstanding, returned loans until 365 elapsed days after receipt and not at/after that boundary. List all, outstanding first then handover descending/reference ascending. Only outstanding loans retain linked booking-detail access within the own-loan context after the ordinary booking-history window expires; returned loans may retain the approved booking reference but do not extend expired booking-detail access. Inactive members may read their own retained facts; no other-member/internal/contact data.
- [ ] **AC-05 — Due fact and return are not inferred policy.** Display the explicit loan due obligation under DD-07 using DD-01 zone/offset; absent due is not recorded, never guessed from a booking. Recorded receipt shows returned even if a restriction remains; DD-03 forbids equating receipt/one case clearance with lendability. No overdue label/calculation, condition dispute assessment or self-return operation.
- [ ] **AC-06 — Read states and interaction.** No visible own loans shows no loans; retrieval failure shows unavailable data, not an empty list (DD-06). Apply DD-08 keyboard/descriptive controls/focus/text outcomes; all reads, including substituted linked-record references, preserve AC-03's own-record and denied-mutation boundary beyond the UI. Reading grants no mutation right.

| Historical question | Current simulated resolution | AC trace |
|---|---|---|
| FX-Q06 | DD-07 explicit handover due fact, legacy absence allowed; overdue remains KD011 | AC-02/04/05 |
| FX-Q09/10 | DD-03 no clearance inference; DD-05 exact facts/no internal assessments; DD-06 visible retention | AC-03/04/05 |
| M04/D04 read-state gap | DD-06 empty versus unavailable; DD-08 interaction | AC-06 |

FX-R09 and relevant self-service prohibitions are adopted as refined above. **Ready** requirements; explicit outstanding/returned/absent-due fixtures can validate this read scope later without KD009's return workflow implemented. No runnable application, test execution or disputed-condition service is claimed.
