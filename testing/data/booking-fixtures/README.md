# KD-ST-001 v2 — synthetic booking scenarios

**Test design, not execution.** This local pack contains 8 fictional member personas, 6 fictional physical items, 5 reusable baseline bookings and 28 independent scenarios: **24 contract-backed conditional designs and 4 exploratory/blocked prompts**. There are no observed results or passed acceptance-criterion checkboxes.

## Start with the booking problem

Bell already has drill A reserved from minute 120 to minute 180. Ari asks for the same drill starting at minute 209: that leaves only 29 minutes, so the request cannot be confirmed. Starting at minute 210 leaves exactly 30 minutes and is allowed on inspection-gap grounds. Asking for an earlier interval ending at minute 90 also leaves 30 minutes, even though Bell's later booking was requested first. Drill B is a different physical unit; drill A's reservation does not reserve it.

Those are imaginary **relative minutes**, not times on an approved business calendar. The examples teach the settled inspection rule without pretending the time zone, permitted dates or damaged-equipment policy is known.

- [Dataset: kd-st-001-v2.json](kd-st-001-v2.json) — portable semantic fixture data, **not** an application schema, API request, database seed or runnable test suite.
- [Coverage matrix](coverage.md) — obligations, scenario IDs, boundary derivation and deliberate gaps.

## Source and version boundary

The behavior oracle is [KD-ST-001, version 2, 2026-10-16](../../../artifacts/stories/KD-ST-001-book-available-equipment.md), AC-01–AC-08. Supporting decisions are [initial intake UD-01–UD-04](../../../artifacts/discovery/Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16), [AC-trial UD-05–UD-08](../../../artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md) and the [approved/applied refinement](../../../artifacts/reviews/KD-ST-001-AC-refinement-proposal.md). The [v2 review follow-up](../../../artifacts/reviews/KD-ST-001-draft-review.md#version-2-follow-up--after-approved-refinement) records the remaining readiness limits. Earlier provisional statements do not override these decisions.

No baseline hash was available in those reviewed references, and none was computed or invented: JSON `sources.baseline_hash` is `null`. The canonical story and source files were not modified. This pack adds no authority to the original requirements and relies on no expansion material or remote record.

## What is fixed, and what is still a question?

| Fixed for the contract-backed design | Still unresolved or absent |
|---|---|
| Each scenario is a fresh isolated world with only its named baseline bookings. | No provisioned environment, accounts, authentication, interfaces, adapters or setup/cleanup permissions. |
| Verified active, verified inactive and cannot-verify are supplied semantic outcomes. | Authoritative membership source, mechanics and freshness are not evidenced by these labels. |
| Contract scenarios assume otherwise-available items and permitted intervals, varying only the specified reservation conflict. | OQ-01: calendar validity, time zone, DST, hours and input precision; OQ-05: complete condition/clearance rules. These premises are not defaults for the product. |
| Hypothetical monotonic minute axes; a gap is later start minus earlier end. | A minute-axis interval cannot be converted to a real date/time until policy is supplied. Integer samples do not establish one-minute application precision. |
| Same physical item: no overlap, gap at least 30, either request order. | Endpoint inclusion is not defined here: strict overlaps are unambiguous, and touching endpoints fail the zero-gap rule regardless. |
| Successful requests immediately confirm and reserve the requested interval; no pending/manual approval, release-one training check or loan. | No response-time SLA, training schema, staff override, retry/idempotency policy or reservation release policy. |
| Own confirmation access; other members' booking details denied; names/contact details protected in availability and outcome information. | No guessed role identifiers, routes, selectors, messages, status codes or storage model. |

`exploratory_blocked` records S-025–S-028 have `expected: null`, no accepted AC coverage, and named questions/owners. They are discussion prompts, not failures to test, approved validation rules or executable cases. In particular, damage is not automatically cleared by 30 minutes.

## IDs and JSON field contract

All fixture identities use the isolated `FX-BKG-*` namespace. They are not real accounts or existing CSV identifiers. Names are invented demonstration aliases; `example.invalid` contact markers are only privacy probes and never credentials or deliverable addresses. Personas describe member capabilities and relationships, **not configured application roles**. This is a library-owned portable semantic convention; it does not change the reusable skill library or define KitDesk's implementation.

| Field / ID family | Meaning |
|---|---|
| `fixture_pack_id`, `schema_version` | Pack identity `FX-BKG-PACK-001` and local documentation schema version `1.0`, not product/API versions. |
| `sources`, `premises` | Provenance, assumptions and execution limits. Source paths are relative to this directory. |
| `personas`, `FX-BKG-M-001`–`008` | Selected membership outcome, ownership relationship, invented display/contact probes. Values are not membership-policy enums. Hali explicitly lacks hypothetical training evidence. |
| `items`, `FX-BKG-I-001`–`006` | Distinct physical units; I-001 and I-002 are the same fictional model but different units. I-006 is reserved for blocked condition exploration. |
| `baseline_bookings`, `FX-BKG-B-001`–`005` | Confirmed/reserved semantic baseline catalog, all owned by Bell. A scenario includes **only** its `baseline_booking_ids`; never seed the whole catalog as shared state. |
| `oracle_profiles`, `FX-BKG-O-001`–`009` | Reusable expected behavioral assertions with stable AC references. These are expectations, not observations. |
| `scenarios`, `FX-BKG-S-001`–`028` | Unique scenario objective, `basis`, `ac_refs`, isolated baseline, semantic action and expected oracle binding, or unresolved prompt. |
| `requests`, `FX-BKG-R-*` | Proposed member/item/interval bindings; concurrency suffixes A/B/C distinguish actors, not processing priority. Gaps in request numbering mirror non-submission scenarios. |
| `interval: [start, end]` | Relative-minute start and end, not timestamps or application payload fields. All contract request intervals have positive duration. |
| `action` | A semantic activity: submit, concurrent submit, view confirmation or inspect member availability; not a navigation or API instruction. |
| `viewer_id`, `target_booking_id`, `protected_persona_ids` | Bind access relationships and whose name/contact must not be exposed. No entitlement to submit on another member's behalf is implied. |
| `expected.oracle_profile_ids` | Apply all referenced assertions to the scenario; O-001 applies per request in S-023. `gap_minutes` and related fields document arithmetic, not extended reservation durations. |
| `maximum_confirmed`, `incompatible_request_pairs` | Concurrency safety constraints, not a required winner count. The pairwise gap invariant must also hold: a count alone is insufficient. `winning_request_id: null` means no designated winner, not no confirmation. |
| `question_refs`, `probe`, `blocked_on`, `expected: null` | Exploratory discovery material with no accepted expected business outcome. OQ references resolve to the canonical story's open questions. |

There are no actual-result fields. `execution_status: not_run` applies to the entire pack. Repeated AC references or several requests in one scenario are **not** extra scenarios or proof of independent coverage. See the matrix for distinct branches.

## How to use the pack in a skill demonstration

1. **Read and reason first.** Compare S-008/009 and S-011/012 against AC-02. Calculate both gap directions. Compare S-014 with S-004 to distinguish a physical unit from a model/category. This requires no application.
2. **`writing-test-cases`:** derive future cases from a selected subset and the matrix. Bind each case to its scenario, version and oracle; include own/non-owner and both privacy surfaces. Keep missing navigation/authentication/setup blocked rather than inventing steps. The pack itself is not an executable case collection.
3. **`writing-test-plans`:** use the distinct branches for risk selection and list OQ-01/02/05 plus environment/data authority as gates. Do not claim complete date/condition coverage or call a handpicked sample pairwise coverage.
4. **`writing-playwright-tests`:** this pack can supply semantic data bindings only after approved application interfaces, selectors, authorized identities, isolated setup and observability exist. It cannot supply runnable authentication or seed payloads. Authoring tests still does not authorize execution.
5. **`post-test-evidence`:** use the pack to explain why expected oracle assertions are not run evidence. No pass/fail, checked AC, screenshots or remote evidence publication can be derived from this file alone.

Before any later authorized execution, the executor would need a reviewed adapter that preserves identities/relationships, maps relative intervals using approved policy, establishes each independent baseline, captures permitted before/after observations and defines authorized retention/restoration. No such adapter, seeding, cleanup commands or application action is included or authorized here. Preserve the supplied baseline when designing unavailable-request observations; do not use a destructive workaround.

## Coverage, limitations and author checks

The matrix provides design examples for every AC-01–AC-08, not a coverage percentage or readiness claim. Simultaneous conflicts allow any compatible resulting subset and no designated actor wins. A zero-confirmation observation would not violate the **safety-only** O-009 oracle by itself; it would not establish successful booking/liveness either. Assess that separately against applicable approved success behavior and observed causes, without inventing a tie-break or guaranteed winner count.

Not included: email, checkout, return, loans, pending holds, waitlists, cancellation, automatic retries, implementation checks, remote actions or any new story. Full overlap topology, every multi-factor combination, higher-volume contention and all privacy representations are not exhaustively enumerated. Selected clear-interval membership failures deliberately isolate membership rules; multi-invalid error precedence remains unspecified. Known unavailable outcomes are illustrated through reservations; equipment-condition classification remains blocked.

Author checks are static/manual only:

- [x] Compared selected expectations with the reviewed v2 AC and approved decisions; kept unresolved outcomes separate.
- [x] Manually checked ID/reference consistency, interval arithmetic, stated counts and relative Markdown/source links.
- [x] Kept edits confined to new booking-fixture files and an additive data-directory link; no canonical content edited.
- [ ] JSON parser/schema validation — **not run**; request a safe parser-only check from the coordinator if desired. This is not a claim of validated machine syntax.
- [ ] Application tests, adapter/seed validation, concurrency execution or security verification — **not run** and not authorized by this design.

These author-review checkboxes are not canonical AC checkboxes, observed test results or independent review.
