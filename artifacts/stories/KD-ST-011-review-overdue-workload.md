# Review the overdue lending workload

Local reference: **KD-ST-011**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for due obligation and overdue classification.

## Summary and value

**As a** desk coordinator, **I want to** inspect outstanding loans classified overdue, **so that** I can identify lending follow-up work without confusing a late loan with the next member's reservation.

This draft can show a stated, assumed overdue set. It cannot calculate whether 09:00, the due instant or opening the desk makes a loan overdue. Evidence: [FX-SRC-04 § P04](../../sources/expansion-01/04-policy-options-conflicts.md), [FX-SRC-06 § X03/X04](../../sources/expansion-01/06-staged-exception-observations.md), [FX-SRC-05 § D07](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R16/17/20/22 are **author-defined synthetic premises, review pending**. Any example must explicitly declare its assumed outstanding-overdue set and known due obligations; that setup is not a verified classification service or timing oracle. No reminder, email, export, escalation, fine, extension, compensation or automatic booking cancellation is added.

## Acceptance criteria

- [ ] **AC-01 — Inspect an explicitly assumed workload.** Given a stated set of outstanding loans already classified overdue under an explicitly declared policy assumption, a coordinator can view the workload with physical item, borrower, known due obligation and recorded handover, and open the actual loan for lending follow-up. This capability does not derive the due obligation or classification. (FX-SRC-04 § P04, FX-R16; FX-Q06.)
- [ ] **AC-02 — Remove received loans, not condition cases.** A loan with recorded return no longer belongs to this outstanding-overdue workload, even if its item has an open condition case. A later reservation does not stand in for actual handover of the still-outstanding item. (FX-SRC-04 § P04, FX-R16; FX-SRC-06 § X03/X04.)
- [ ] **AC-03 — Distinguish empty from unclassified.** An empty known workload differs from inability to determine the workload/classification. An inability to classify is not displayed as nothing overdue. (FX-SRC-04 § P04, FX-R16.)
- [ ] **AC-04 — Protect the operational view.** Members cannot read the staff overdue workload or other borrowers' names/contact details through it, including by bypassed controls or changed references. Staff access remains limited to desk lending work; it does not send messages, export data, escalate or impose a penalty. (FX-SRC-04 § P04, FX-R17; FX-SRC-03 § O05, FX-R20; SRC-06 § A01.)
- [ ] **AC-05 — Do not resolve lateness by changing unrelated facts.** The late-loan situation itself does not extend the loan, rewrite a later booking's interval, silently cancel the later reservation or select compensation/substitution. (FX-SRC-06 § X03, FX-R22.)

## Dependencies versus readiness

KD-ST-006 supplies actual loans; KD-ST-009 supplies recorded return for workload removal. KD-ST-008 can locate a loan regardless of overdue status and is not dependent on this view. Classification policy/evidence is an unresolved external prerequisite, not a missing predecessor story that can be called delivered. Assumed-set display can be reviewed now, but full calculated overdue behavior cannot.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q06 / FX-C05 | Maya + Leon: how are due obligations and overdue derived, including zone, DST, disputes and operational boundaries? | Blocks calculated inclusion, thresholds and boundary assertions; no grace window or morning schedule is chosen. |
| FX-Q07 | Leon + Aisha: are notifications needed; which events, recipients, channels and privacy/failure rules? | Delivery remains unadopted, not a prerequisite to viewing a known set. |
| FX-Q10 | Aisha: which contact fields and retention are necessary for follow-up? | No added contact-field list or export permission. |
| FX-Q03/12 | Maya + Leon: what happens to the next collection when equipment is still out? | No substitute, extension or reservation remedy is silently supplied. |

## Traceability

Coverage classification: **New** classified workload, distinct from general outstanding lookup. AC-01–03 use FX-R16; AC-04 uses FX-R17/20; AC-05 uses FX-R22. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All AC unchecked. Assumed classification is not proof of an implemented or approved overdue clock.
