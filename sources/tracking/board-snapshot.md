# SRC-08 — Synthetic offline board snapshot

Scenario snapshot date: 2026-10-10. Manually invented for analysis exercises. **Not exported from ADO.** All labels use `SIM-` to avoid confusion with numeric remote IDs. No organization, team, real board field, revision, identity or state mapping is configured.

## M01 — Simulated workflow vocabulary

Display columns: Intake, Ready, Active, Blocked, Done. These labels are scenario data only, not discoverable ADO mappings or authorization for a move. Readiness criteria are not adopted; propose criteria and ask the user to confirm before a definitive readiness assessment.

## M02 — Simulated work items

| Local label | Title | Display column | Dependency/evidence |
|---|---|---|---|
| SIM-01 | Display request result in portal | Active | Waiting for final approval wording; request receipt UI and own-record access can be explored independently |
| SIM-02 | Membership integration contract | Done | Notes say draft contract written; no provider access, test endpoint or approved fallback is evidenced |
| SIM-03 | Enforce eligibility at request | Ready | Depends on SIM-02; eligibility states and failure behavior remain open in SRC-07 |
| SIM-04 | Record equipment return | Blocked | Depends on SIM-05 only for damaged returns; routine return flow may be separable pending scope confirmation |
| SIM-05 | Decide damaged-item release policy | Intake | Who can restore availability remains unresolved |
| SIM-06 | Build approved-booking cancellation | Ready | Depends on a cancellation decision not yet made; design button alone is not approval |
| SIM-07 | Overdue reminder emails | Intake | Proposed release-one inclusion, timing and recipients unconfirmed |

## M03 — Calibration and operations limits

No story-point scale, historical calibration, acceptance criteria, capacity or owners are supplied. An estimation exercise should state uncertainty and request team calibration, not treat these rows as sufficiently specified stories.

Offline exercises can recommend behavior-grounded follow-up, compare proposed readiness criteria, and draft comments. They cannot establish complete ADO extraction, genuine revision-safe updates, identity resolution, synchronization or verified board moves.
