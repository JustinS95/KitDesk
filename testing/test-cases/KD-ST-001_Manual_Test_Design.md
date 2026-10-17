# Booking a tool, without promising it twice

Bell has drill A booked from minute 120 to minute 180. Ari wants to borrow it next. Starting at minute 209 leaves 29 minutes for inspection: not enough. Starting at minute 210 leaves exactly 30 minutes: enough, provided Ari is eligible and the item is otherwise available. The extra half hour is a gap **between bookings**, not extra time added to Ari's reservation.

That small example gives us a useful way to build tests, one question at a time:

1. **Can Ari book a free tool at all?** First check one eligible request with no competing booking. Ari should get a confirmed reservation in the portal, not a request waiting for the desk. Reopen it to check the tool and interval actually recorded, rather than trusting a success message alone.
2. **Does the half-hour rule have the right edge?** Try 29, 30 and 31 minutes. Then put Ari's booking *before* Bell's: an existing later booking must still be protected. Bell having requested first does not change the arithmetic.
3. **Are we protecting the right thing?** Drill B is a separate physical unit of the same model. Bell's drill A booking must not block drill B. A booking squeezed between two others must leave enough room on both sides.
4. **Can a failed request leave a mess?** Check both the explanation and the records. An inactive member, an unverifiable member and an unavailable interval are different outcomes; none should quietly create a confirmed booking or reservation.
5. **Can members learn too much?** Bell should be able to reopen Bell's confirmation; Gavi should not. Ari may learn that a time is unavailable, but not Bell's name or contact details.
6. **What if Ari and Elin ask together?** Do not pick a winner in advance. Inspect the resulting reservations for conflicts. With three requests, two may fit; “only one winner” is not the rule either.

The minutes and people are fictional. These are **manual test designs awaiting an approved application and environment**, not ready-to-run procedures or evidence that KitDesk works. Every case below is **Not run**.

## The contract and the data are different things

| Source | What it establishes |
|---|---|
| [KD-ST-001 — Book available equipment, v2, 2026-10-16](../../artifacts/stories/KD-ST-001-book-available-equipment.md), Acceptance criteria AC-01–AC-08; Scope and Open questions | Behavioral oracle. Refinement is approved for this scenario, not full implementation readiness. |
| [Discovery intake, user role-play decisions](../../artifacts/discovery/Discovery_Summary_KitDesk_20261016.md) and [AC trial decisions UD-05–UD-08](../../artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md) | Accepted scenario decisions incorporated into v2. No earlier staff-approval flow is reinstated. |
| [Fixture JSON](../data/booking-fixtures/kd-st-001-v2.json), pack `FX-BKG-PACK-001`, semantic schema 1.0; [guide / field contract](../data/booking-fixtures/README.md); [fixture coverage](../data/booking-fixtures/coverage.md) | Authored synthetic examples: 8 personas, 6 physical items, 5 baseline bookings, 24 contract-backed scenarios and 4 blocked prompts. Portable semantic records, **not** application payloads, accounts, seed instructions or a new product schema. |
| [Fixture static validation](../../evaluation/expanded-demo-01/fixture-validation.md), 2026-10-17 | Prior validation parsed the JSON and passed 559 static consistency assertions. Those are **not application test passes**. The guide's earlier “parser not run” note predates this report. This specimen does not rerun that validation. |

Contract scenarios conditionally assume permitted intervals and otherwise-available items; only named conflicts vary. Relative minutes do not settle calendar validity, time zone, DST, operating hours or input precision. Selected membership outcomes are test premises, not evidence of a real membership integration. No exact messages, response-time SLA, endpoint, selector, configured role or UI navigation is specified.

### Why this is a small suite, not every possible combination

- **Partitions:** active, inactive and cannot-verify membership have different outcomes. The last two use empty booking baselines so a conflict cannot mask the membership rule. Owner/non-owner and availability/outcome privacy are separate partitions too.
- **Boundaries:** 29/30/31 minutes sample just below, on and above the accepted threshold in both temporal directions. They do not define the application's smallest selectable time increment. Zero-gap touching and three strict overlap shapes catch different mistakes without deciding endpoint inclusion.
- **Decisions:** active + clear interval → confirmation; inactive + clear → active-membership explanation; unverifiable + clear → verification explanation; active + reservation conflict → unavailable explanation. Inactive + conflict and unverifiable + conflict are feasible but not selected: error precedence is unknown, and those combinations would not isolate either rule.
- **State:** distinguish a new confirmation/reservation from no creation; compare preserved baseline records; reopen an existing confirmation independently. There is no invented cancellation, expiry or return transition.
- **Concurrency:** test identical intervals, a short gap, a mixed compatible group and distinct-unit control. Sequential boundary tests do not count as concurrent boundary coverage. A compatible subset is a safety observation, not a promised winner count or liveness result.

Selection is risk-based, not exhaustive or claimed pairwise coverage. More overlap shapes, simultaneous exactly-30-minute requests, larger crowds and all privacy representations remain unsampled. Email, loans/handover, returns, cancellation/release, waitlists, retries and staff overrides are outside this story's test scope.

## Before anyone runs a case

All cases depend on **G1–G4**; individual cases add gates where relevant. These are execution prerequisites, not new acceptance criteria. No account, adapter or application interface currently exists in the supplied project.

| Gate | Needed before execution | Owner / handoff |
|---|---|---|
| G1 — Environment and authorization | Approved non-production application/version, execution permission, safe evidence destination and retention. No production or destructive operation is implied. | Application/test owner to be identified. |
| G2 — Identity and interfaces | Approved authentication/account references for each semantic member; documented booking, confirmation and member-availability interactions. For non-owner access, an approved way to target the same booking as a different authenticated member. No guessed routes or credentials. | Application/auth owner to be identified. |
| G3 — Data and observations | Reviewed adapters for the existing semantic records; independent baseline setup, booking/reservation readback, permitted before/after observation and authorized restoration. The observer must not expose privileged baseline details to the requesting member. | Application/test-data owner to be identified. |
| G4 — Time and availability premises | Policy-approved calendar mapping preserving each relative interval and gap, with supported precision; evidence items are otherwise available. OQ-01 date/time policy and OQ-05 condition policy are unresolved. If a sample cannot be represented, mark that row blocked rather than round it. | Maya; time-zone owner to confirm. |
| G5 — Membership evidence | An approved way to establish each specified verification outcome; integration authority/mechanics/freshness remain OQ-02. Hali needs verified-active membership without a training prerequisite, not an invented training field. | Aisha, with Maya on exceptions; application owner for adapters. |
| G6 — Contention | Authorized coordinated submission mechanism, independent authenticated sessions and sufficient observation to establish actual concurrent contention and relate each outcome to its request. Sequential clicking alone is insufficient. No timing window or scheduler is invented. | Application/test owner to identify mechanism. |

### Shared setup, observation and cleanup contract

These instructions apply **separately to every parameter row**. Rows are independent test executions, never steps chained onto one shared seeded world.

1. Assign a collision-safe run/case/row label in the approved test-data mapping. Preserve each `FX-BKG-*` identity as its semantic reference while mapping it to isolated application records. Do not add fields to the fixture JSON or treat fixture aliases/contact probes as login credentials.
2. Establish only the row's named baseline bookings as confirmed with reservations, using their exact owner, physical item and interval from the JSON. `None` means no baseline bookings, not “use whatever is there.” Establish the listed member's verification outcome. Contract items are otherwise available and intervals permitted, subject to G4/G5.
3. Capture a permitted baseline snapshot: application IDs mapped to fixture IDs, owner, selected physical item, requested interval, confirmation/reservation state and absence of records for the proposed requests. This is setup evidence, not a member entitlement to other borrowers' details.
4. Perform the case's member actions using only the approved mapped interaction. Capture each submission's actual result and any generated booking identity; read reservation effects through the approved observation channel. A portal message alone cannot prove a reservation exists or that a failed request created none. If readback is unavailable, mark that assertion blocked, not passed.
5. After each row, compare baseline owner/item/interval/confirmed-reservation state with the snapshot. Successful rows add only the specified request reservations; rejected rows add no confirmed booking/reservation for that request; view-only rows make no booking changes. Existing-reservation preservation is explicitly required for unavailable outcomes by AC-04; other comparisons are setup-integrity guards, not new business rules.

**Cleanup for every case/row:** retain permitted diagnostic evidence on failure. After capture, use only the separately authorized test-environment restoration adapter to remove that row's mapped synthetic state and restore its pre-setup snapshot, without touching other runs. No deletion/cancellation interface or reservation-release policy is assumed. If restoration authority is absent, stop before setup; do not leave shared test state or improvise cleanup.

**Reading the references below:** `S-001`, `M-001`, `I-001`, `B-001`, `R-001`, `O-001` mean the exact existing IDs `FX-BKG-S-001`, `FX-BKG-M-001`, etc. in the linked JSON. TC IDs are unique within this artifact. Each parameter row inherits the entire case procedure, gates, cleanup and Not run status. Actual result and evidence remain blank for a future authorized tester.

## Manual cases

### TC-001 — Confirm one eligible request, then read back its reservation

**Basis/type:** KD-ST-001 v2 AC-01 (active/available → immediate portal confirmation, no approval/pending, training excluded), AC-02 (reserve selected item for requested interval), AC-05 (own item/interval visibility); Functional/state. **Risk:** a reassuring message with no reservation, a pending workflow, or an unnecessary training gate.

**Preconditions/setup:** shared isolated setup; no baseline bookings in either row. M-001 Ari and M-008 Hali are verified active. Hali has explicitly absent hypothetical training evidence; do not supply a training grant. **Dependencies:** G1–G5; approved confirmation readback. **Cleanup:** shared contract, independently per row.

| Row / scenario | Request | Member / physical item | Requested interval | Oracle |
|---|---|---|---|---|
| A / S-001 | R-001 | M-001 / I-003 projector | `[120,180]` | O-001 |
| B / S-024 | R-024 | M-008 / I-002 drill B | `[120,180]` | O-001; training absence is deliberate |

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter the row's selected item and interval as its member in the approved booking interaction. | The values under test identify that physical unit and interval; no training evidence is needed for this release-one request. |
| 2 | Submit that single request once. | It becomes confirmed with portal confirmation, without staff approval or a separate pending stage. No stopwatch SLA is asserted. |
| 3 | Reopen the resulting own confirmation using its captured identity. | The member can view the selected physical item and exact requested interval. Booking is not represented as a loan. |
| 4 | Read back the booking/reservation through the approved observation channel. | A confirmed booking reserves that physical item for exactly `[120,180]`, not an interval extended by inspection time. No unrelated baseline existed to change. |

**Overall oracle:** all success clauses above, not just the displayed confirmation. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-002 — Verified inactive is an eligibility denial, not a booking

**Basis/type:** KD-ST-001 v2 AC-03, all clauses; Negative. **Risk:** an ineligible reservation or an unexplained failure.

**Data/setup:** S-002 / R-002 / O-002; Corin M-003 verified inactive; I-004 sander `[120,180]`; baseline None. Otherwise available and permitted, so membership is the only failed condition. **Dependencies:** G1–G5. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter I-004 and `[120,180]` as M-003. | Selected values match R-002; the clear baseline leaves no reservation conflict. |
| 2 | Submit R-002. | Portal explains that active membership is required; it does not confirm the booking. Exact copy is unspecified. |
| 3 | Compare request-related booking/reservation readback with the empty baseline. | No confirmed booking or reservation was created for R-002. |

**Overall oracle:** meaningful active-membership explanation **and** no creation. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-003 — Cannot verify is not proof of inactive membership

**Basis/type:** KD-ST-001 v2 AC-08, all clauses; Negative. **Risk:** false confirmation or a misleading inactive-membership diagnosis.

**Data/setup:** S-003 / R-003 / O-003; Daya M-004 has the selected cannot-verify outcome; I-005 recorder `[120,180]`; baseline None. No competing unavailability. **Dependencies:** G1–G5; establishing inability to verify must not silently substitute verified inactive. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter I-005 and `[120,180]` as M-004. | Selected values match R-003, with the reviewed cannot-verify premise in place. |
| 2 | Submit R-003. | Portal explains that eligibility could not be verified. It neither represents confirmation nor claims the member is proven inactive. |
| 3 | Compare request-related booking/reservation readback with the empty baseline. | No confirmed booking or reservation was created for R-003. No automatic retry or pending behavior is prescribed by this test. |

**Overall oracle:** verification-specific explanation and no creation; a generic inactive denial is insufficient. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-004 — Conflicts must not displace Bell's reservation

**Basis/type:** KD-ST-001 v2 AC-02 (no overlap / sufficient separation), AC-04 (unavailable explanation, no creation, existing reservations unchanged); Negative/edge. **Risk:** incomplete interval comparison or overwriting an existing booking.

**Preconditions/setup:** each row independently has only B-001: Bell M-002, drill A I-001, `[120,180]`, confirmed/reserved. Ari M-001 is verified active; only the request relation varies. **Dependencies:** G1–G5. **Cleanup:** shared contract per row.

| Row / scenario | Request | Member / item | Interval | Isolated reason / oracle |
|---|---|---|---|---|
| A / S-004 | R-004 | M-001 / I-001 | `[150,210]` | Strict partial overlap / O-004 |
| B / S-005 | R-005 | M-001 / I-001 | `[135,165]` | Strictly inside B-001 / O-004 |
| C / S-006 | R-006 | M-001 / I-001 | `[90,210]` | Encloses B-001 / O-004 |
| D / S-007 | R-007 | M-001 / I-001 | `[180,240]` | Zero-minute gap / O-004; no endpoint-inclusion decision needed |

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter the row's item/interval as M-001. | Selected values match that row; B-001 remains the independent baseline. |
| 2 | Submit the row's request. | Portal explains the requested interval is unavailable; no confirmation is presented for it. |
| 3 | Read back the new request's booking/reservation effects. | No confirmed booking or reservation was created for that request. |
| 4 | Compare B-001 with its setup snapshot. | Bell's owner identity, I-001, `[120,180]` and confirmed/reserved state remain unchanged. |

**Overall oracle:** rejection, explanation, no creation and preservation must all hold in every row. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-005 — Walk across the 30-minute boundary in both directions

**Basis/type:** KD-ST-001 v2 AC-02 (at least 30, exact 30 permitted, independent of request order); rejected rows AC-04 all clauses; successful rows AC-01 and AC-05 own confirmation. Boundary/state. **Risk:** rejecting exactly 30, accepting 29, or comparing only bookings earlier in time.

**Preconditions/setup:** recreate only B-001, Bell M-002 / I-001 `[120,180]`, before **each** row. All new requests are active Ari M-001 / I-001. Earlier-in-time requests below are still submitted after B-001 exists. **Dependencies:** G1–G5; one-minute samples require representable approved mappings, not assumed input precision. **Cleanup:** shared contract per row.

| Row / scenario | Request | Interval | Gap calculation | Expected branch / oracle |
|---|---|---|---|---|
| A / S-008 | R-008 | `[209,269]` | `209 - 180 = 29` | Unavailable / O-004 |
| B / S-009 | R-009 | `[210,270]` | `210 - 180 = 30` | Confirm / O-001 |
| C / S-010 | R-010 | `[211,271]` | `211 - 180 = 31` | Confirm / O-001 |
| D / S-011 | R-011 | `[31,91]` | `120 - 91 = 29` | Unavailable / O-004 |
| E / S-012 | R-012 | `[30,90]` | `120 - 90 = 30` | Confirm / O-001 |
| F / S-013 | R-013 | `[29,89]` | `120 - 89 = 31` | Confirm / O-001 |

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter the row's I-001 interval as M-001. | Selected values match the row and preserve the stated gap to B-001. |
| 2 | Submit the row's request once. | **A/D:** unavailable explanation, no confirmation. **B/C/E/F:** immediate portal confirmation, no approval/pending stage or training prerequisite. |
| 3 | Read back the request's booking/reservation. | **A/D:** no new confirmed booking/reservation. **B/C/E/F:** confirmed reservation uses I-001 and the row's exact interval, not an extra 30 minutes. |
| 4 | For successful rows only, reopen the resulting own confirmation. | M-001 can view I-001 and the exact requested interval. A/D have no new confirmation to reopen. |
| 5 | Compare B-001 with its snapshot. | Its owner, physical item, interval and confirmed reservation remain unchanged. Successful intervals leave the calculated gap; rejected attempts do not displace it. |

**Overall oracle:** each row matches its branch. “At least 30” is not “more than 30.” **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-006 — Reserve drill B while drill A is booked

**Basis/type:** KD-ST-001 v2 AC-01, AC-02 (selected physical item), AC-05 own confirmation; Functional/control. **Risk:** model-wide locking mistaken for a physical-unit reservation.

**Data/setup:** S-014 / R-014 / O-001; only B-001, Bell M-002 / I-001 `[120,180]`. Active Ari M-001 requests the distinct I-002 drill B for `[120,180]`. **Dependencies:** G1–G5; preserve distinct unit mapping even though the model matches. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter I-002 and `[120,180]` as M-001. | Selected unit is drill B, not an alias for I-001. |
| 2 | Submit R-014. | Immediate portal confirmation without approval/pending or training gate; I-001's reservation does not block I-002. |
| 3 | Reopen the resulting own confirmation. | Ari can view I-002 and `[120,180]`. |
| 4 | Read back R-014's confirmed booking/reservation. | It reserves I-002 for `[120,180]`; the physical item reserved is drill B. |
| 5 | Compare B-001 with its snapshot. | Bell still has I-001 `[120,180]` confirmed/reserved, unchanged; two reservations relate to different units. |

**Overall oracle:** independent unit success, not merely two bookings of an ambiguous model. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-007 — Fit exactly between two bookings

**Basis/type:** KD-ST-001 v2 AC-01, AC-02 (both neighboring separations and exact requested reservation), AC-05 own confirmation; Boundary/state. **Risk:** checking one neighboring booking only or padding the requested interval.

**Data/setup:** S-015 / R-015 / O-001; only B-002 and B-003, both Bell M-002 / I-003 projector, `[60,120]` and `[240,300]`. Active Ari M-001 requests I-003 `[150,210]`. **Dependencies:** G1–G5. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter I-003 `[150,210]` as M-001. | Requested interval leaves `150 - 120 = 30` before and `240 - 210 = 30` after. |
| 2 | Submit R-015. | Immediate portal confirmation without staff approval/pending or a training prerequisite. |
| 3 | Reopen the resulting own confirmation. | Ari can view I-003 `[150,210]` exactly. |
| 4 | Read back R-015's confirmed booking/reservation. | It reserves I-003 `[150,210]` exactly. The inspection gaps do not enlarge the reservation. |
| 5 | Compare both baseline reservations with their snapshots. | B-002/B-003 retain Bell, I-003, their original intervals and confirmed/reserved state; all three intervals satisfy AC-02. |

**Overall oracle:** success with both 30-minute gaps, not a single-neighbor comparison. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-008 — Bell can reopen Bell's existing confirmation

**Basis/type:** KD-ST-001 v2 AC-05 own-view clause; Permission/functional. **Risk:** a confirmation accessible only at initial submission.

**Data/setup:** S-016 / O-005; only B-004, Bell M-002 / I-005 recorder `[120,180]`, confirmed/reserved; authenticated viewer M-002 owns B-004. No new request. **Dependencies:** G1–G4; approved existing-confirmation access, not a guessed full history/list page. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | As M-002, request to view mapped B-004 using the approved interaction. | Bell can view that own confirmation, including I-005 and `[120,180]`. |
| 2 | Compare B-004 and booking/reservation state with the baseline. | B-004 is unchanged; viewing did not create another booking or reservation (setup-integrity check). |

**Overall oracle:** owner can view the existing selected item and interval. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-009 — Gavi cannot view Bell's booking details

**Basis/type:** KD-ST-001 v2 AC-05 non-owner clause; Permission/negative. **Risk:** knowing a booking reference grants access, or correct attribution is mistaken for access control.

**Data/setup:** S-017 / O-006; independently recreate only B-004, Bell M-002 / I-005 `[120,180]`. Viewer Gavi M-007 is verified active but does not own it. No new request. **Dependencies:** G1–G4; an approved cross-member targeting method is essential. A hidden link alone cannot prove denial. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | As M-007, attempt to view mapped B-004 through the approved cross-member access interaction. | Bell's booking details are not available to Gavi. Showing the correct owner alongside those details is still a failure. No particular denial copy or status code is required. |
| 2 | Inspect the member-visible result of that attempt. | No target booking detail is disclosed through the supplied result or its member-accessible detail views. |
| 3 | Compare B-004 and booking/reservation state with the baseline through the separate observer. | Bell's booking/reservation remains unchanged; no new booking is created (setup-integrity check). |

**Overall oracle:** attempted non-owner access reveals no booking details; lack of a known access method leaves this blocked. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-010 — Availability can say “unavailable” without identifying Bell

**Basis/type:** KD-ST-001 v2 AC-06 availability-information clause; Privacy. **Risk:** borrower identity leaked before a request is submitted.

**Data/setup:** S-018 / O-007; only B-005, Bell M-002 / I-004 sander `[120,180]`. Viewer Ari M-001 examines I-004 `[120,180]`. Protected probes: `Bell Fixture` and `bell.fx-bkg@example.invalid`, plus other representations of Bell's name/contact. No submission. **Dependencies:** G1–G4; approved availability presentation and inventory of its member-visible surfaces. If that interaction is unknown, do not invent a calendar. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | As M-001, obtain the member-facing availability information for I-004 `[120,180]`. | Any information presented contains neither Bell's name nor contact details. No exact layout or wording is required. |
| 2 | Inspect all member-visible availability details exposed by that interaction. | Neither probe, nor an equivalent disclosure of name/contact, is present. Checking just one label is insufficient; record which surfaces were inspected. |
| 3 | Compare B-005 and booking/reservation state with the baseline through the separate observer. | The view-only interaction leaves B-005 unchanged and creates no booking/reservation (setup-integrity check). |

**Overall oracle:** both name and contact protected across inspected availability surfaces; unobservable surfaces are a coverage limit. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-011 — Explain the conflict without naming its borrower

**Basis/type:** KD-ST-001 v2 AC-02 short gap; AC-04 all clauses; AC-06 booking-outcome clause; Negative/privacy. **Risk:** a helpful rejection exposes Bell or changes the blocking reservation.

**Data/setup:** S-019 / R-019 / O-004 and O-008; only B-005, Bell M-002 / I-004 `[120,180]`. Active Ari M-001 requests I-004 `[209,269]`: 29-minute gap. Protect `Bell Fixture`, `bell.fx-bkg@example.invalid` and equivalent disclosures. **Dependencies:** G1–G5; inspect all member-visible outcome details, not only the main message. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Enter I-004 `[209,269]` as M-001. | Request matches R-019 and the isolated 29-minute conflict. |
| 2 | Submit R-019. | Portal explains requested-interval unavailability, without confirmation and without Bell's name/contact. |
| 3 | Inspect all member-visible details of the booking outcome. | Neither probe nor an equivalent disclosure of Bell's name/contact appears. Exact error text is not mandated. |
| 4 | Read back R-019's booking/reservation effects. | No new confirmed booking or reservation exists for R-019. |
| 5 | Compare B-005 with its snapshot. | Bell's owner/item/interval/confirmed reservation remain unchanged. |

**Overall oracle:** useful explanation, both privacy protections, no creation and preservation. This is a second privacy surface, not a new numeric boundary. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-012 — Two simultaneous requests must not create a conflicting pair

**Basis/type:** KD-ST-001 v2 AC-07, AC-02 invariant, AC-04 competing-reservation failure clauses; Concurrency/negative. **Risk:** both requests pass a stale availability check.

**Preconditions/setup:** each row starts with baseline None. Ari M-001 and Elin M-005 are independently authenticated and verified active; both request I-001. G1–G6 required. **Cleanup:** shared contract per row. **Oracle:** O-009; no designated winner or promised number of confirmations.

| Row / scenario | Request A | Request B | Safety bound |
|---|---|---|---|
| A / S-020 | R-020A, M-001, `[120,180]` | R-020B, M-005, `[120,180]` | At most 1 confirmed; identical overlap |
| B / S-021 | R-021A, M-001, `[120,180]` | R-021B, M-005, `[209,269]` | At most 1 confirmed; gap 29 |

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Prepare each row's request values in its member's independent session. | Each session is mapped to the intended member, I-001 and interval; no baseline reservation exists. |
| 2 | Release the two submissions using the approved contention mechanism. | Capture both correlated outcomes and evidence of genuine concurrent contention. Do not infer which actor should win from A/B labels or arrival observation. |
| 3 | Inspect resulting confirmed bookings and their reservation readback. | At most one request is confirmed/reserved; the pair cannot both confirm. Any confirmed reservation uses its own requested item/interval. |
| 4 | Inspect each request prevented by a competing reservation. | AC-04: unavailable explanation, no confirmed booking/reservation for that request, and the competing existing reservation remains unchanged. If the cause cannot be established, mark this branch inconclusive. |

**Overall oracle:** safety and applicable failure clauses, not “exactly one wins.” A zero-confirmation outcome satisfies the count invariant alone but does not establish successful booking/liveness; retain causes for review against applicable success behavior. No fixed order, retry or latency guarantee is asserted. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-013 — Three requests: compatible pairs are allowed, not required

**Basis/type:** KD-ST-001 v2 AC-07, AC-02 invariant, AC-04 competing-reservation failure clauses; Concurrency. **Risk:** using a count alone, or imposing a global one-winner rule.

**Data/setup:** S-022 / O-009; baseline None; independently authenticated active M-001 Ari, M-005 Elin, M-006 Faro; all request I-001. R-022A / M-001 `[0,60]`; R-022B / M-005 `[89,149]`; R-022C / M-006 `[180,240]`. A/B gap 29; B/C gap 31; A/C gap 120. **Dependencies:** G1–G6. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Prepare the three requests in their mapped member sessions. | Each session contains the specified unit/interval; all eligibility premises are established without baseline bookings. |
| 2 | Release all three using the approved contention mechanism. | Capture correlated outcomes and genuine contention evidence; A/B/C labels do not establish priority. |
| 3 | Read back the full resulting confirmed subset and reservations. | Each reserves I-001 for its own requested interval; no overlap and every pair leaves at least 30 minutes. Count is at most two **and** A/B are never both confirmed. A+C or B+C can satisfy the rule; neither pair is required. Smaller compatible subsets also satisfy this safety-only oracle. |
| 4 | Inspect each request prevented by a competing reservation. | AC-04 unavailable explanation and no confirmed booking/reservation for that prevented request. If causality cannot be established, record the branch as inconclusive. |
| 5 | Compare the competing reservations before/after prevented attempts through the approved observer. | Existing competing reservations remain unchanged. If preservation cannot be observed, record that assertion as inconclusive. |

**Overall oracle:** pairwise compatibility, not just count. No guaranteed winner count, order or liveness claim; an empty subset is not proof of successful service. **Execution:** Not run. **Actual result:** — **Evidence:** —

### TC-014 — Concurrent requests for different physical units are a success control

**Basis/type:** KD-ST-001 v2 AC-01, AC-02 selected-unit reservation, AC-05 own confirmation; Functional/concurrency control, **not** an AC-07 conflicting-request case. **Risk:** mistakenly rejecting all concurrent same-model requests.

**Data/setup:** S-023 / O-001 applied independently to each request; baseline None. Active Ari M-001 requests R-023A / I-001 `[120,180]`; active Elin M-005 requests R-023B / I-002 `[120,180]`. Distinct physical units, otherwise available. **Dependencies:** G1–G6; no shared alias for I-001/I-002. **Cleanup:** shared contract.

| Step | Tester action | Observable expected result |
|---|---|---|
| 1 | Prepare each request in its member's independent session. | The sessions select different physical drills for the same interval. |
| 2 | Release the submissions using the approved contention mechanism. | Each request immediately confirms in its member's portal without approval/pending or training prerequisite. No cross-item reservation conflict exists under these premises. |
| 3 | Reopen each own confirmation separately as its requester. | Ari sees I-001 `[120,180]`; Elin sees I-002 `[120,180]`. This step does not grant either access to the other's details. |
| 4 | Read back both resulting reservations through the approved observer. | Each physical unit is reserved for its own requested interval; neither reservation substitutes for or changes the other. |

**Overall oracle:** both independent success oracles apply under the conditional premises. Unlike TC-012/013, this is not a safety-only competing-request oracle. **Execution:** Not run. **Actual result:** — **Evidence:** —

## Semantic AC coverage — designed observations, not passes

Each row identifies a meaningful clause, not merely an `ac_refs` label. References are to KD-ST-001 v2 Acceptance criteria; fixture oracle profiles never add authority to those clauses.

| AC / obligation | Case and decisive observation | Limit |
|---|---|---|
| AC-01: verified-active + otherwise available request becomes immediately confirmed | TC-001 steps 1–2; TC-005 successful rows, TC-006/007; TC-014 each request | Conditional availability/date premises; no quantified SLA. |
| AC-01: no staff approval or separate pending stage | TC-001 step 2, repeated in success branches | Inspect the outcome/workflow; not established by reservation count alone. |
| AC-01: no release-one training check | TC-001 row B, M-008 with absent training evidence | A normal active persona alone would not isolate this clause. No training schema inferred. |
| AC-01: member sees portal confirmation | TC-001 step 2; success branches including TC-014 | A privileged readback alone is not portal feedback. |
| AC-02: selected physical item reserved for requested interval | TC-001 steps 3–4; TC-006 step 4; TC-007 step 4; TC-014 step 4 | Check reservation readback, not just confirmation text; do not add the gap to the interval. |
| AC-02: no same-item overlap | TC-004 rows A–C; TC-012 row A; TC-013 pairwise readback | Three strict shapes plus concurrent identical interval, not every topology. |
| AC-02: shorter gap insufficient, including touching | TC-004 row D; TC-005 A/D; TC-012 row B | Zero-gap rejection does not decide endpoint inclusion. |
| AC-02: exactly 30 permitted, at least 30, either request order | TC-005 B/C/E/F; TC-007 both neighbors | Both temporal directions; existing baseline requested first. Concurrent exact-30 boundary not selected. |
| AC-02: physical unit, not model-wide exclusion | TC-006; TC-014 concurrent control | Distinct I-001/I-002 mapping required. |
| AC-03: inactive → active-membership explanation | TC-002 step 2 | Clear interval isolates membership; exact copy unspecified. |
| AC-03: no confirmed booking **and** no reservation | TC-002 step 3 | Requires both readbacks; explanation alone is insufficient. |
| AC-04: unavailable at confirmation → no confirmed booking/reservation | TC-004 step 3; TC-005 A/D; TC-011 step 4; applicable TC-012/013 failures | Reservation-caused unavailability sampled; condition causes blocked. |
| AC-04: requested-interval-unavailable explanation | TC-004 step 2; TC-005 A/D step 2; TC-011 step 2; TC-012/013 failure observations | Do not substitute membership diagnosis or require exact text. |
| AC-04: existing reservations unchanged | TC-004 step 4; TC-005 A/D step 5; TC-011 step 5; TC-012 step 4 / TC-013 step 5 | Compare owner, item, interval and confirmed/reserved state; concurrency causality may be unobservable. |
| AC-05: requesting member views own item/interval | TC-001 step 3; TC-008 step 1; other success readbacks | Separate new and pre-existing confirmation designs; no full history list promised. |
| AC-05: another member cannot view booking details | TC-009 steps 1–2, M-007 targeting M-002's B-004 | Owner attribution or link hiding is not access denial; access adapter absent. |
| AC-06: availability hides other's name **and** contact | TC-010 steps 1–2 | Both probes plus equivalent disclosures; surface inventory needed. |
| AC-06: booking outcome hides other's name **and** contact, including blocking reservation | TC-011 steps 2–3 | Outcome surface is separate from availability; no universal privacy audit claimed. |
| AC-07: otherwise eligible simultaneous overlap or insufficient gap still satisfies AC-02 | TC-012 both rows, step 3; TC-013 step 3 | Genuine contention required; count alone insufficient for mixed group. |
| AC-07: competing-reservation failures receive AC-04 outcome | TC-012 step 4; TC-013 steps 4–5 | Causality and preservation must be observable or assertion stays inconclusive. |
| AC-07: no prescribed winner/order | TC-012/013 safety oracles accept any compatible subset | No “exactly one”/“first arrival wins” claim; safety is not liveness. |
| AC-08: no confirmed booking/reservation when unverifiable | TC-003 step 3 | Membership outcome fixture is not live integration evidence. |
| AC-08: explain inability, neither confirmation nor proof of inactive membership | TC-003 step 2 | Different semantic diagnosis from TC-002, not just another generic failure. |

**Accounting:** 14 stable cases bind all 24 contract-backed fixture scenarios. Four cases are parameterized (TC-001: 2 rows; TC-004: 4; TC-005: 6; TC-012: 2); ten are single-scenario cases, giving **24 independent scenario/parameter executions** if later authorized. The pack's 26 request records include multi-request concurrency; requests, steps, assertions and AC references are not extra cases. None has been executed.

## Exploratory / blocked handoff — no pass/fail oracle yet

These four existing fixture prompts have `expected: null` and no AC coverage. They are not additional manual cases, failed tests or accepted validation rules. Do not turn a plausible bad input into a required rejection without a decision.

| Fixture prompt / exact bindings | Discovery action before designing further cases | Decision owner / blocker |
|---|---|---|
| S-025; M-001 / I-003; OQ-01 | Establish permitted dates, past/future selection, equal/reversed endpoints, ranges, precision and operating hours. Only then derive approved input partitions and boundaries. | Maya; time-zone owner to confirm. No field-range or calendar oracle. |
| S-026; M-001 / I-003; OQ-01 | Agree business time zone and mapping of repeated/skipped local times, including hypothetical local 01:30, before calculating real-clock gaps. | Maya; time-zone owner to confirm. Relative-minute arithmetic cannot resolve DST. |
| S-027; M-001 / I-006; OQ-05 | Determine whether the hypothetical damage report blocks availability, and the authority/evidence for clearance. Do not infer that 30 minutes or a return clears damage. | Maya. No condition-classification or clearance oracle. |
| S-028; M-004 / I-005; OQ-02 | Identify authoritative membership evidence, verification mechanics and freshness. Define approved integration observations without inventing service codes, cache or retry policy. | Aisha, with Maya on exceptions. Once cannot-verify is established, TC-003 already covers its accepted member outcome. |

G1–G6 remain execution blockers as applicable even for contract-backed cases. A future tester should record **Blocked** for an unmet prerequisite or **Inconclusive** for an unavailable assertion observation, rather than infer a pass. Actual outcomes, evidence and any new policy decisions belong to a separately authorized run/refinement; this specimen changes no canonical AC, fixture, implementation or execution status.
