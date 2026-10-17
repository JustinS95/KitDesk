# Cancel an eligible booking of my own

Local reference: **KD-ST-004**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for cancellation eligibility and the handover race.

## Summary and value

**As a** member, **I want to** cancel an eligible uncollected booking of my own, **so that** an interval I will not use stops being reserved by that booking.

If the desk has only prepared the drill, it is not yet agreed whether cancellation can still complete. This draft covers a separately established eligible path, not a cutoff disguised as a requirement. Evidence: [FX-SRC-04 § P01–P03](../../sources/expansion-01/04-policy-options-conflicts.md) and [FX-SRC-06 § X01/X05](../../sources/expansion-01/06-staged-exception-observations.md).

## Scope and authority

FX-R04/05/21 are **author-defined synthetic premises, review pending**. They do not approve a cancellation policy. No staff cancellation right, hold, no-show expiry, alternative booking, email, waitlist or fixed duration is introduced. A confirmation prompt in FX-SRC-05 D02 remains a design proposal, not mandatory AC.

## Acceptance criteria

- [ ] **AC-01 — Complete an established eligible cancellation.** Given an own confirmed, uncollected booking is eligible under an explicitly supplied cancellation policy and cancellation completes before any competing handover outcome under that policy, its outcome becomes cancelled and only its reservation ceases to reserve the interval. Other bookings and actual loans remain unchanged. The member sees completion only when known. (FX-SRC-04 § P01–P02, FX-R04/05; FX-Q02.)
- [ ] **AC-02 — Preserve the target on repeat.** Repeating cancellation of the same cancelled booking does not release another reservation or create another lifecycle event; the known cancelled outcome is shown. Releasing this reservation does not promise that another booking will succeed. (FX-SRC-04 § P02, FX-R05; KD-ST-001 AC-02/04.)
- [ ] **AC-03 — Refuse unsupported targets.** A member cannot cancel another member's booking, including by replacing the selected reference; no other-member details are disclosed and that booking is unchanged. A collected booking cannot be cancelled through this interaction; an outstanding actual loan stays outstanding, and no actual-loan state is changed. Known refusals explain that cancellation was not completed, without pretending that a missing cutoff policy is settled. (FX-SRC-04 § P01–P02, FX-R04/05; FX-SRC-06 § X06; SRC-06 § A01.)
- [ ] **AC-04 — Report only a known outcome.** A known refusal/failure before completion does not claim cancellation or release and leaves the target unchanged. If completion is uncertain, neither successful cancellation nor an unchanged record is asserted until the selected booking's outcome is reconciled; a repeat must respect AC-02. (FX-SRC-04 § P02, FX-R05; FX-SRC-06 § X05, FX-R21.)

## Dependencies versus readiness

KD-ST-001 supplies the booking/reservation to cancel. KD-ST-003 displays the resulting outcome; KD-ST-005/006 consume collection eligibility but are related consumers, not predecessors required to exercise a clean cancellation. FX-Q02 blocks complete eligibility/race AC, not review of reservation release and ownership. No concurrent winner, no-show transition or readiness claim is supplied.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q02 / FX-C02 | Maya + Leon: cancel until actual handover, impose a cutoff, or desk assistance? What counts as handover in progress, which action can complete and what does the other actor see? | Blocks definitive eligibility and concurrent cancellation/handover outcomes. X01 does not select a winner. |
| FX-Q01 | Maya + Leon; zone owner unconfirmed: if a time-based cutoff is selected, what clock/interval interpretation applies? | Conditional blocker only; no time-based cutoff is assumed. |
| FX-Q02/12 | Maya + Leon: how are uncollected bookings handled? | No-show behavior remains outside these criteria, not automatic cancellation. |

## Traceability

Coverage classification: **New**, explicitly outside KD-ST-001. AC-01/03 use FX-R04; AC-01–04 use FX-R05; AC-04 uses FX-R21 at the cited paragraphs. FX-SRC-04 P03 and FX-SRC-06 X01 are unresolved race evidence, not positive race oracles. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked; no cancellation has been implemented or tested.
