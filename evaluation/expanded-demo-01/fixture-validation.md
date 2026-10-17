# Booking fixture static validation

Date: 2026-10-17. **Result: PASS for the bounded static checks below; no fixture defects found.** This is not application, workflow, concurrency or security execution evidence.

## Scope and provenance

Reviewed the canonical [KD-ST-001 v2 story](../../artifacts/stories/KD-ST-001-book-available-equipment.md), [fixture JSON](../../testing/data/booking-fixtures/kd-st-001-v2.json), [guide](../../testing/data/booking-fixtures/README.md) and [coverage matrix](../../testing/data/booking-fixtures/coverage.md). No expansion-source material was used. Only this report was written.

- Canonical story SHA256 matched the supplied baseline: `D198119A239AC2FF23FF2A6D23827B7EA4D32B4DC27B5CF8258ADC40DACFCE90`.
- Validated JSON SHA256: `46E21BE878D4C52489E01D68C0E6E32A5A5AA02E46D749982F9C4AE720266B98`.
- The JSON's historical `sources.baseline_hash: null` was not changed; the independently computed hashes above identify this validation snapshot.

## Checks actually performed

Authorized read-only inline PowerShell used `Get-Content -Raw | ConvertFrom-Json`, `Get-FileHash -Algorithm SHA256`, `Test-Path`, reference indexing, interval comparisons and small compatible-subset enumeration. Parsing succeeded. The completed consistency pass evaluated **559 static assertions with zero issues**. These assertions are not 559 application tests or a coverage percentage.

| Check | Result |
|---|---|
| Declared counts | 8 personas, 6 physical items, 5 baseline bookings, 9 oracle profiles, 28 scenarios: 24 contract-backed + 4 exploratory/blocked. There are 26 request records. Guide/matrix counts agree. |
| Definition uniqueness | 83 unique fixture definitions, including pack and request IDs; expected `FX-BKG-*` namespace. Repeated references are not duplicate definitions. |
| Reference consistency | Persona/member/owner/viewer/protected-person references, items, isolated baseline/target bookings, oracle profiles, ACs, open questions and declared incompatible request pairs resolve. Explicit shorthand IDs in guide/matrix resolve; source and Markdown relative file targets exist. |
| AC reachability | All canonical AC-01–AC-08 are reachable from contract-backed scenarios. Each scenario's AC set equals the union of its bound oracle-profile AC sets. Manual comparison found no contradictory business assertions. This is design traceability, not complete behavior coverage. |
| Sequential outcomes | Success requests have active-member fixtures and no same-item baseline conflict. Unavailable requests have an actual reservation overlap/insufficient gap and active membership. All request intervals have positive duration. Named baselines are mutually compatible within each isolated scenario. |
| Membership | S-002 uses verified-inactive M-003; S-003 uses cannot-verify M-004. Both isolate membership with clear intervals. Six personas are verified active; one is inactive; one cannot be verified. S-024 uses active M-008 with explicitly absent hypothetical training evidence. No live verification or integration policy is inferred. |
| Ownership and privacy | S-016's M-002 owns B-004; S-017's M-007 does not. The denial oracle prohibits viewing details, not merely misattribution. S-018 availability and S-019 rejection protect baseline owner M-002 from a different actor, with both invented name and `example.invalid` contact probes. |
| Physical-unit isolation | S-014 and S-023 bind different units I-001/I-002; their identical intervals do not create a cross-item conflict. Condition-exploration I-006 is absent from contract requests. |
| Exploratory separation | S-025–S-028 each have `expected: null`, empty `ac_refs`, resolving OQ references, a probe and a named decision blocker. No accepted date, DST, damage-clearance or membership-integration business oracle is invented. |

The first consistency-command attempt stopped because its local variable name `$pid` collided with PowerShell's read-only `$PID`. A renamed variable was used for the successful full rerun. This was a validator-command issue, not a fixture defect; neither attempt wrote fixture data.

## Boundary and conflict reasoning

All numbers below are hypothetical relative minutes, not approved calendar times. B-001 is `[120,180]`.

| Scenarios | Recomputed gap | Expected design binding |
|---|---|---|
| S-007 | `180 - 180 = 0` | Unavailable, O-004 |
| S-008 / S-009 / S-010, later request | `209/210/211 - 180 = 29/30/31` | Unavailable / success / success |
| S-011 / S-012 / S-013, earlier request | `120 - 91/90/89 = 29/30/31` | Unavailable / success / success |
| S-015, between B-002/B-003 | `150 - 120 = 30`; `240 - 210 = 30` | Success for requested `[150,210]`, not an extended reservation |
| S-019 | `209 - 180 = 29` | Unavailable plus outcome privacy |

Overlap cases S-004/005/006 respectively partially overlap, lie inside and enclose B-001. Their rejection/preservation oracle agrees with AC-02/04. Touching S-007 fails the zero-gap rule without deciding endpoint inclusion.

Static enumeration of request subsets confirms the stated safety upper bounds:

- S-020: identical same-item intervals; maximum compatible count 1.
- S-021: same-item separation `209 - 180 = 29`; maximum 1.
- S-022: A/B gap 29, B/C gap 31, A/C gap 120; maximum 2. Exactly A/B is incompatible; A+C and B+C are compatible pairs. A count bound alone would not exclude the forbidden A+B pair, so the pairwise invariant matters.

All three conflict scenarios bind O-009 and `winning_request_id: null`. The JSON, guide and matrix prescribe neither winning order nor a guaranteed winner count. Competing-reservation failures retain AC-04's explanation/no-creation/preservation expectation. Compatible subsets establish only mathematical safety of the fixture oracle, not scheduling, booking liveness or observed contention.

## Limits and disposition

- No fixture changes are needed from this review. No supporting-source contents beyond the canonical story were re-audited; their referenced file targets were checked. Markdown fragment targets were not automatically validated.
- OQ-01 calendar validity, time zone, DST, operating hours and precision remain unresolved; OQ-05 condition/clearance and OQ-02 authoritative membership evidence remain explicit blockers. Integer boundary samples do not define application precision, and 30 minutes does not clear damage.
- No formal JSON Schema conformance check was run: the pack documents a portable semantic convention, not an application schema. Parser success and targeted consistency checks are the claims made here.
- No application code/tests, adapters, accounts, membership service, setup/seed/cleanup operations, UI/API workflows, concurrent execution or security enforcement were exercised. All workflow designs remain **not run**; no canonical AC checkbox or execution status was changed.
