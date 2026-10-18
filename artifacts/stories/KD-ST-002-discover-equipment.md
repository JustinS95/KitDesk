# Find the right equipment and check an interval

Local reference: **KD-ST-002**. Version 2, 2026-10-18.
Maturity: **Ready — fictional requirements only**, not implemented/tested; public publication snapshot below.

Current authority: [user-approved fictional decisions DD-01–08](../discovery/Demo_Readiness_Decisions_20261018.md), approved 2026-10-18 with “looks good. You may proceed”. Historical v1 questions retain their original impacts; the current resolution table supersedes them for this scope.

Publication snapshot — **2026-10-18T14:28:46Z**: seven revised public Issue bodies, including [KD-ST-002 (#3)](https://github.com/JustinS95/KitDesk/issues/3), and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3); five deferred Issues remained Backlog. Repository documentation publication remains pending. This is not a real-time guarantee or evidence of implementation or executed tests.

## Summary and value

**As a** member, **I want to** find an individually lendable item and check my intended interval, **so that** I choose the right physical tool rather than assume every drill is interchangeable or free next Saturday.

A carrying case and listed parts help distinguish similar items. Catalog presence is not a promise of interval availability. This capability informs a choice; it never reserves the item. Evidence: [FX-SRC-02 § M01–M02](../../sources/expansion-01/02-member-staff-interviews.md), supported by [FX-SRC-05 § D01](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

Browse, name/identifier search, category narrowing, item detail and interval information belong together. FX-R01/02 are adopted only as refined by user-approved DD-01/03/05/06/08, not as real stakeholder evidence. [KD-ST-001](KD-ST-001-book-available-equipment.md) alone owns confirmation and its availability recheck. AC-05–08 specify matching, fields and bounded interaction; no hold, borrower directory, spelling assistance or formal accessibility conformance is promised.

## Acceptance criteria

- [ ] **AC-01 — Identify the physical item.** A member can browse item summaries, search by equipment name or item identifier and narrow by category. Results identify the individually lendable item, description and listed included parts; opening a result preserves that same item identity. AC-05 supplies matching examples, category values and missing-field treatment. (FX-SRC-02 § M01, FX-R01; DD-05/06.)
- [ ] **AC-02 — Distinguish no match from missing catalog data.** A completed search with no matching items shows a no-results outcome. Failure to obtain the catalog is shown as unavailable data, not an empty equipment inventory. (FX-SRC-02 § M01, FX-R01.)
- [ ] **AC-03 — Qualify interval information.** Given a member-selected interval whose interpretation is explicitly established for the scenario, the item view distinguishes available, unavailable and unable-to-determine outcomes for that interval. Unknown is not shown as available or as proof of another booking. A listed item without that interval determination is not represented as a confirmed interval promise. (FX-SRC-02 § M02, FX-R02; FX-Q01/03.)
- [ ] **AC-04 — Preserve booking and privacy boundaries.** Browsing/checking availability creates no reservation. Availability may change before KD-ST-001 confirmation; neither catalog nor availability outcomes disclose other members' identities or contact details. (FX-SRC-02 § M01–M02, FX-R01/02; KD-ST-001 AC-02/04/06.)

## Dependencies versus readiness

No predecessor story is required to obtain catalog value. KD-ST-001 consumes the selected item/interval but is not a delivery prerequisite for browsing. DD-01/03/06 settle search/interval rules; catalog and explicit qualification facts or controlled fakes remain engineering inputs. No catalog service or application exists.

## Historical v1 open questions — current resolutions below

Owners are fictional consultation roles, not assignees.

| Reference | Question / owner | Scoped impact |
|---|---|---|
| FX-Q01 | Maya + Leon; time-zone owner unconfirmed: how are intervals, permitted ranges and DST interpreted? | Blocks complete AC-03 boundary coverage, not item identification. |
| FX-Q03 | Maya: which condition facts qualify availability? | Blocks an exhaustive availability decision, not the three information outcomes. |
| M01 gap | Maya with member examples: what name/identifier matching and categories are intended? | AC-01 is a supported capability, not an exact search oracle; sorting, spelling and limits remain unspecified. |
| FX-Q11 | Leon with missing accessibility participants: what accessible and assisted interactions are needed? | Blocks usable-access claims, not a fabricated conformance criterion. |

## Traceability

Coverage classification: **New** versus KD-ST-001's explicitly excluded discovery scope; AC-04 preserves rather than duplicates its booking/privacy rules. AC-01/02 map to FX-R01; AC-03/04 to FX-R02 at the cited M01/M02 paragraphs. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All criteria are unchecked requirements candidates, not executed checks.

## Current demo decisions, AC and readiness — v2

- [ ] **AC-05 — Exact catalog matching and fields.** Apply DD-06's trimmed, case-insensitive literal name/item-reference substring search, empty-query browse, exact category AND filter (Power tools, AV equipment, Hand tools), item-reference ascending ordering and all-match display. Show exactly DD-05's catalog fields; missing description/parts are not recorded. ` DRILL ` matches KD-EQ-001; `drill` filtered to AV equipment has no matches. Do not add fuzzy matching or borrower search.
- [ ] **AC-06 — Deterministic interval qualification.** Validate member intervals by DD-01, including zone/offset, future start, ordered endpoints and DST rejection/disambiguation; invalid input is explained rather than reported available/unavailable. For valid input use KD001's reservation/30-minute rule and DD-03's current qualification: known restriction/non-lendable/outstanding loan is unavailable, missing/contradictory facts are unable to determine, and only a known eligible unreserved interval is available. No receipt/clearance shortcut, hold or borrower/condition-note disclosure. Recheck at booking remains KD001's responsibility.
- [ ] **AC-07 — Member boundary.** Only authenticated members may use this member catalog/availability capability; a bypassed unauthorized read is denied without protected detail or any booking/reservation change. Display no fields outside DD-05's catalog allowance, even through changed item references.
- [ ] **AC-08 — Accessible bounded interaction.** Apply DD-08's descriptive controls, keyboard operation, visible focus and text search/availability/error outcomes, not color-only feedback or a claimed conformance certification.

| Historical question | Current simulated resolution | AC trace |
|---|---|---|
| FX-Q01 | DD-01 sets Europe/London, intervals, permitted inputs and DST | AC-03/06 |
| FX-Q03 | DD-03 settles consumption/fail-closed qualification; no clearance editing added | AC-03/06 |
| M01 matching/category/sort/limit gap | DD-05/06 adopts exact examples, field list and all-result order | AC-01/05 |
| FX-Q11 | DD-08 settles bounded keyboard/text/control behavior; research/conformance unverified | AC-08 |

FX-R01/02 are adopted for this story only as refined by these simulated decisions. **Ready** requirements; catalog, qualification source/fakes, authentication and interaction implementation/verification remain engineering work, not evidence of a running service. No dependency on delivering condition assessment to use explicitly qualified item fixtures.
