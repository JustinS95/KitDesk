# Review my bookings and what happened to them

Local reference: **KD-ST-003**. Candidate pending user review, version 1.
Maturity: **draft complete under stated fixture premises** for bounded retrieval, not implementation or board readiness.

## Summary and value

**As a** member, **I want to** retrieve my bookings and their known outcomes, **so that** I can tell a still-confirmed reservation from one I cancelled or already collected.

For example, a collected drill booking should lead to its actual loan, not imply that confirmation itself created a loan. Evidence: [FX-SRC-02 § M03](../../sources/expansion-01/02-member-staff-interviews.md), with [FX-SRC-05 § D02](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

Own list/detail retrieval extends KD-ST-001's immediate confirmation. FX-R03 is an **author-defined synthetic premise, review pending**. The lifecycle concepts below are not exact labels or an exhaustive state model. Cancellation execution belongs to KD-ST-004; handover belongs to KD-ST-006. No editing, rebooking, auto-expiry, approval, notification or retention duration is added.

## Acceptance criteria

- [ ] **AC-01 — Retrieve own booking facts.** The requesting member can list and open their own bookings with physical item identity, requested interval and known outcome: confirmed, cancelled through completed cancellation, or collected. A collected booking links to its actual loan; a confirmed booking alone is not shown as possession. (FX-SRC-02 § M03, FX-R03.)
- [ ] **AC-02 — Do not invent a lifecycle event.** A cancelled booking is not represented as awaiting collection; a missed collection is not automatically represented as cancelled. Retrieval introduces no Pending/Approved stage. (FX-SRC-02 § M03, FX-R03; UD-01/04.)
- [ ] **AC-03 — Distinguish empty from unavailable.** A member with no bookings receives a no-bookings outcome distinct from inability to obtain their list. (FX-SRC-02 § M03, FX-R03.)
- [ ] **AC-04 — Protect every lifecycle branch.** Another member's booking detail cannot be read by changing a record reference, including cancelled and collected records. Other members' records and cancellation operations are not offered as the requesting member's own; denied access discloses no protected booking detail. (FX-SRC-02 § M03, FX-R03; FX-SRC-06 § X06; SRC-06 § A01.)

## Dependencies versus readiness

Local record prerequisite: KD-ST-001 creates confirmed bookings. Cancelled/collected examples additionally consume outcomes from KD-ST-004/006; those branches can use explicitly assumed records for draft review rather than requiring every workflow before retrieval work starts. The loan destination is KD-ST-007. These are record relationships, not approved implementation order.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q10 | Aisha: how long is history retained and what extra historical information is appropriate? | Retention/deletion policy is excluded; the draft covers retained own records only, without promising indefinite history. |
| FX-Q02 | Maya + Leon: what happens to a no-show? | No automatic no-show transition is specified; existing known outcomes remain reviewable. |

## Traceability

Coverage classification: **New** retrieval/list scope; existing own-confirmation privacy is **Covered** by KD-ST-001 AC-05/06 and preserved here across history. AC-01–04 map to FX-R03, FX-SRC-02 § M03; AC-04 also uses the bypass boundary in SRC-06 § A01 via FX-SRC-06 § X06. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All criteria remain unchecked; no access enforcement has been verified.
