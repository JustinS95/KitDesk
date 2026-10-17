# Report a problem with equipment I still have

Local reference: **KD-ST-012**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for report response ownership, urgency and sensitive content handling.

## Summary and value

**As a** member with an outstanding loan, **I want to** record a problem description on that loan, **so that** desk staff have the reported concern before return without my falsely marking the item returned.

A drill making a noise is a member report, not proof of assessed damage or receipt. Evidence: [FX-SRC-02 § M04, FX-R18 paragraph](../../sources/expansion-01/02-member-staff-interviews.md), [FX-SRC-08 § C04](../../sources/expansion-01/08-condition-return-workshop.md), [FX-SRC-05 § D04](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

FX-R18/19/20/21 are **author-defined synthetic premises, review pending**. This is information attached to an own outstanding loan, not emergency monitoring, staff notification delivery, self-return, fault assessment or due-date pause. No attachments, character limits, edit or duplicate-report policy is invented.

## Acceptance criteria

- [ ] **AC-01 — Record an own outstanding-loan report.** A member can submit a problem description against their own outstanding actual loan. A completed submission is visible as a report on that same loan to its author, without recording receipt, closing/extending the loan, deciding fault or cancelling any reservation. (FX-SRC-02 § M04, FX-R18.)
- [ ] **AC-02 — Supply lending context without assessing damage.** Staff undertaking that loan's lending/return task can see the related description identified as member-reported content. The report does not itself establish assessed damage or create the damaged-return condition case; staff receipt/observation is separate. It does not expand access to unrelated records or disclose internal staff assessment notes to the member. (FX-SRC-08 § C04, FX-R19; FX-SRC-03 § O05, FX-R20.)
- [ ] **AC-03 — Enforce ownership and outstanding status.** Another member cannot read or submit on the loan by substituting its reference or bypassing controls; no report is added to that other member's loan and no protected detail is exposed. A returned loan is not eligible for this interaction; the member is told it is no longer outstanding rather than shown success for a new report, and no new report is created through this interaction. (FX-SRC-02 § M04, FX-R18; FX-SRC-06 § X06; SRC-06 § A01.)
- [ ] **AC-04 — Distinguish submission from response or uncertainty.** Known failure/refusal before completion leaves the target unchanged and does not claim a recorded report. If completion is uncertain, neither successful submission nor unchanged state is asserted before reconciling the selected loan's known result. Confirmed report receipt is not represented as staff alerted, a promised response time, safety guidance or email acknowledgement. (FX-SRC-06 § X05, FX-R21; FX-SRC-05 § D04; FX-SRC-08 § C04; FX-Q13.)

## Dependencies versus readiness

KD-ST-006 supplies the outstanding loan. KD-ST-007 is a related own-loan view, not a mandated interface prerequisite. KD-ST-008/009 consume the report when present; a return can still be recorded without one. Bounded report capture/visibility is meaningful partial work. FX-Q13 prevents claiming a complete monitored-response service, not writing the supported submission outcomes.

## Open questions

| Reference | Question / fictional owner | Scoped impact |
|---|---|---|
| FX-Q13 | Maya + Leon: who acts on reports, with what urgency and safety guidance? | Blocks monitored/urgent response claims and a complete service boundary; no real action commitment is assigned. |
| FX-Q03 | Maya: should a pre-return concern restrict an item or affect later reservations? | No such automatic restriction is included; damaged receipt remains a separate trigger. |
| FX-Q10; M04 gap | Aisha on sensitive content/retention; Maya on report interaction: what limits, repeated reports, editing or attachments are appropriate? | Blocks those unprovided branches; no arbitrary field validation or duplicate policy is adopted. |

## Traceability

Coverage classification: **New** own-loan report capability; shared staff visibility is integrated rather than split into a feedback story. AC-01/03 use FX-R18; AC-02 uses FX-R19/20; AC-04 uses FX-R21. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All criteria unchecked; no report submission, alert or test was executed.
