# Booking fixture coverage — KD-ST-001 v2

**Design coverage only; no execution results.** Read the [guide](README.md) for the conditional premises and [JSON dataset](kd-st-001-v2.json) for exact bindings. Source: [KD-ST-001 v2, 2026-10-16](../../../artifacts/stories/KD-ST-001-book-available-equipment.md), AC-01–AC-08, refined by [UD-05–UD-08](../../../artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md).

In the tables, `S-009` means **`FX-BKG-S-009`**, and similarly for M/I/B/O/R IDs. Scenario IDs, not table appearances, are the counting unit: **28 distinct scenarios = 24 contract-backed + 4 exploratory/blocked**. A scenario covering multiple obligations is still one scenario. There are 8 personas, 6 items, 5 baseline bookings and 9 oracle profiles.

## AC obligations and selected examples

| Stable AC | Distinct obligation / branch | Scenario bindings | Design status / limit |
|---|---|---|---|
| AC-01 | Verified active + otherwise available → immediate confirmation, portal feedback; no approval/pending stage | S-001; O-001 | Contract-backed conditional design; no response-time SLA. |
| AC-01 | Release-one membership/training eligibility requires no training evidence | S-024, M-008; O-001 | Active member deliberately has no hypothetical training evidence; not a training schema. |
| AC-02 | Reserve selected physical item for requested interval, not interval plus inspection duration | S-001, S-009, S-012, S-015; O-001 | Check the actual requested interval, not an enlarged reservation. |
| AC-02 / AC-04 | Strict partial overlap; request inside existing interval; request encloses existing interval | S-004, S-005, S-006 respectively; O-004 | Three different geometric relations, not three labels for one request. |
| AC-02 / AC-04 | Touching endpoints still leave insufficient inspection gap | S-007; O-004 | Zero gap rejects without choosing endpoint-inclusion policy. |
| AC-02 / AC-04 | Later interval requested after earlier baseline: 29 rejected, 30 permitted, 31 permitted | S-008, S-009, S-010 | See exact arithmetic below. |
| AC-02 / AC-04 | Earlier interval requested after later baseline: 29 rejected, 30 permitted, 31 permitted | S-011, S-012, S-013 | Reverse temporal direction proves request order does not define the gap. |
| AC-02 | Physical-unit isolation, even with same model and identical intervals | S-014; S-023 concurrent control | Existing-state and concurrent controls are distinct setups; not a rule about pooled stock. |
| AC-02 | New interval must fit both neighboring bookings | S-015; B-002/B-003 | Exactly 30 minutes on each side, not just one comparison. |
| AC-03 | Verified inactive: no confirmation/reservation; active-membership explanation | S-002; O-002 | Isolated with available item and clear interval; no error precedence invented. |
| AC-04 | Unavailable at confirmation: no new booking/reservation; unavailable explanation; preserve existing reservations | S-004–008, S-011, S-019; O-004 | Each uses a named baseline whose item/owner/interval can be compared; reservation causes sampled, condition causes unresolved. |
| AC-05 | Own new confirmation shows selected item/interval | S-001 and other O-001 success designs | AC-01 and AC-05 share observations; not extra scenarios. |
| AC-05 | Own existing confirmation accessible; another member's details inaccessible | S-016 and S-017, same B-004; O-005/O-006 | M-002 is owner, M-007 is not. No history page, route, role or denial copy guessed. |
| AC-06 | Availability information hides another borrower's name/contact | S-018; O-007 | Bell's two synthetic probes and equivalent disclosures; no availability layout mandated. |
| AC-06 | Failed-booking outcome explains conflict without exposing name/contact | S-019; O-004/O-008 | Different presentation surface from S-018; not extra numeric-boundary coverage. |
| AC-07 / AC-02 | Simultaneous overlapping requests must leave a compatible confirmed subset | S-020; O-009 | Identical intervals, upper bound one; any actor may win, none prescribed. |
| AC-07 / AC-02 | Simultaneous non-overlap with insufficient separation also conflicts | S-021; O-009 | 29-minute gap; upper bound one, no tie-break. |
| AC-07 / AC-04 | A mixed group may permit more than one confirmation; competing-reservation failures receive AC-04 outcome and preserve state | S-022; O-009; also S-020/021 | Upper bound two plus pairwise compatibility; not a global one-winner rule or a promise that two succeed. |
| AC-08 | Cannot verify: no confirmation/reservation, explain inability; not proof of inactive membership | S-003; O-003 | Clear interval isolates this branch from unavailability. Service mechanics remain unknown. |

## Boundary derivation, without calendar assumptions

The base reservation B-001 is I-001, `[120,180]`. Each row is a separate isolated request by active M-001. All other eligibility/availability conditions are held satisfied **as hypothetical premises**. Integer samples around 30 minutes are deliberate representatives, not a specification of application input resolution.

| New interval position | Requested relative interval | Computation | Expected under the premises | Scenario |
|---|---|---|---|---|
| Later, touching | `[180,240]` | `180 - 180 = 0` | Unavailable; baseline unchanged | S-007 |
| Later | `[209,269]` | `209 - 180 = 29` | Unavailable; baseline unchanged | S-008 |
| Later | `[210,270]` | `210 - 180 = 30` | Confirm; reserve `[210,270]` only | S-009 |
| Later | `[211,271]` | `211 - 180 = 31` | Confirm | S-010 |
| Earlier, requested later | `[31,91]` | `120 - 91 = 29` | Unavailable; baseline unchanged | S-011 |
| Earlier, requested later | `[30,90]` | `120 - 90 = 30` | Confirm; reserve `[30,90]` only | S-012 |
| Earlier, requested later | `[29,89]` | `120 - 89 = 31` | Confirm | S-013 |

S-015 checks a new `[150,210]` between B-002 `[60,120]` and B-003 `[240,300]`: `150 - 120 = 30`, `240 - 210 = 30`. Neither gap extends the requested booking interval. Overlap cases S-004/005/006 do not require negative-gap arithmetic or guessed endpoint semantics.

## Partitions, interactions and concurrency reasoning

| Derivation | Representative selection | Meaningful distinction / deliberate omission |
|---|---|---|
| Membership outcomes | Active S-001, inactive S-002, cannot-verify S-003 | Supplied fixture outcomes, not live membership service responses. Both failures isolate their rule. |
| Availability shapes | Clear S-001; partial/inside/enclosing overlap S-004/005/006; gap S-007–013; both neighbors S-015 | No claim to every overlap topology, date validation or condition status. |
| Record relationship | Owner S-016 vs non-owner S-017 using the same baseline | Identity/attribution alone does not establish authorized access. |
| Privacy surfaces | Availability S-018 vs rejection S-019 | Name and contact are both meaningful probes; extra appearances of AC-06 do not create more scenarios. |
| Request concurrency | Identical overlap S-020; 29-minute non-overlap S-021; mixed compatibility S-022 | Not repeated sequential submissions. Execution requires an authorized mechanism able to establish genuine contention. |
| Separate-unit controls | Existing reservation S-014; simultaneous submissions S-023 | Prevent a mistaken model/category-wide conflict rule. |

For S-022: A `[0,60]`, B `[89,149]`, C `[180,240]` all request I-001. A/B gap is 29 (incompatible), B/C gap is 31, A/C gap is 120. The maximal compatible pairs are **A+C** and **B+C**; smaller compatible subsets also satisfy this safety-only oracle. The count `<= 2` is necessary but not sufficient: **A+B must never both confirm**. No particular actor or required number of winners is selected. If a competing reservation prevents confirmation, AC-04's explanation/no-creation/preservation applies. This does not invent an all-fail policy or certify booking liveness.

Selection is risk-based, not exhaustive or claimed pairwise coverage. It retains rule-isolating failures, both gap directions, record privacy and concurrency invariants. Inactive + conflict and unverifiable + conflict combinations are feasible but not selected: explanation precedence is not approved, and they would not isolate either rejection rule. Higher-volume contention and simultaneous exactly-30-minute same-item requests are feasible but not selected; the exact boundary is represented sequentially in both temporal directions, not claimed concurrency-boundary execution coverage.

## Explicit blocked questions — no accepted expected outcome

| Scenario | Canonical question | Prompt / decision needed | Owner / status |
|---|---|---|---|
| S-025 | OQ-01 | Permitted dates, interval selections, precision and hours; past/zero/reversed are proposals for discussion, not validation oracles | Maya; time-zone owner to confirm. `expected: null`. |
| S-026 | OQ-01 | Business zone and repeated/skipped-clock mapping before DST/gap cases | Maya; time-zone owner to confirm. `expected: null`. |
| S-027 | OQ-05 | Equipment condition/clearance; elapsed inspection gap alone does not clear damage | Maya. `expected: null`. |
| S-028 | OQ-02 | Authoritative membership verification evidence/mechanics/freshness; outcome already covered conditionally by S-003 | Aisha, with Maya on exceptions. `expected: null`. |

These four records do not count as AC pass/fail coverage. No story checkbox is checked by this matrix. Unknown navigation, authentication, configured capabilities, data adaptation and before/after observation channels block execution of even the contract-backed designs. Email, checkout/return, cancellation/release, pending holds, waitlists, retries, staff overrides and implementation internals are outside this pack.
