# Find the right equipment and check an interval

Local reference: **KD-ST-002**. Candidate pending user review, version 1.
Maturity: **provisional—specific clarification needed** for interval interpretation, condition qualification and search behavior.

## Summary and value

**As a** member, **I want to** find an individually lendable item and check my intended interval, **so that** I choose the right physical tool rather than assume every drill is interchangeable or free next Saturday.

A carrying case and listed parts help distinguish similar items. Catalog presence is not a promise of interval availability. This capability informs a choice; it never reserves the item. Evidence: [FX-SRC-02 § M01–M02](../../sources/expansion-01/02-member-staff-interviews.md), supported by [FX-SRC-05 § D01](../../sources/expansion-01/05-text-design-revision.md).

## Scope and authority

Browse, name/identifier search, category narrowing, item detail and conditional interval information belong together. FX-R01/02 are **author-defined synthetic premises, review pending**, not stakeholder approvals. [KD-ST-001](KD-ST-001-book-available-equipment.md) alone owns booking confirmation and its availability recheck. No hold, borrower directory, spelling assistance, exact matching algorithm or accessibility conformance is implied.

## Acceptance criteria

- [ ] **AC-01 — Identify the physical item.** A member can browse item summaries, search by equipment name or item identifier and narrow by category. Results identify the individually lendable item, description and listed included parts; opening a result preserves that same item identity. Matching examples and category values must be supplied before detailed search assertions are finalized. (FX-SRC-02 § M01, FX-R01.)
- [ ] **AC-02 — Distinguish no match from missing catalog data.** A completed search with no matching items shows a no-results outcome. Failure to obtain the catalog is shown as unavailable data, not an empty equipment inventory. (FX-SRC-02 § M01, FX-R01.)
- [ ] **AC-03 — Qualify interval information.** Given a member-selected interval whose interpretation is explicitly established for the scenario, the item view distinguishes available, unavailable and unable-to-determine outcomes for that interval. Unknown is not shown as available or as proof of another booking. A listed item without that interval determination is not represented as a confirmed interval promise. (FX-SRC-02 § M02, FX-R02; FX-Q01/03.)
- [ ] **AC-04 — Preserve booking and privacy boundaries.** Browsing/checking availability creates no reservation. Availability may change before KD-ST-001 confirmation; neither catalog nor availability outcomes disclose other members' identities or contact details. (FX-SRC-02 § M01–M02, FX-R01/02; KD-ST-001 AC-02/04/06.)

## Dependencies versus readiness

No predecessor story is required to obtain catalog value. KD-ST-001 consumes the selected item/interval but is not a delivery prerequisite for browsing. Conditional interval examples can be drafted now; complete search and availability behavior cannot be inferred from them. No catalog service or application exists.

## Open questions

Owners are fictional consultation roles, not assignees.

| Reference | Question / owner | Scoped impact |
|---|---|---|
| FX-Q01 | Maya + Leon; time-zone owner unconfirmed: how are intervals, permitted ranges and DST interpreted? | Blocks complete AC-03 boundary coverage, not item identification. |
| FX-Q03 | Maya: which condition facts qualify availability? | Blocks an exhaustive availability decision, not the three information outcomes. |
| M01 gap | Maya with member examples: what name/identifier matching and categories are intended? | AC-01 is a supported capability, not an exact search oracle; sorting, spelling and limits remain unspecified. |
| FX-Q11 | Leon with missing accessibility participants: what accessible and assisted interactions are needed? | Blocks usable-access claims, not a fabricated conformance criterion. |

## Traceability

Coverage classification: **New** versus KD-ST-001's explicitly excluded discovery scope; AC-04 preserves rather than duplicates its booking/privacy rules. AC-01/02 map to FX-R01; AC-03/04 to FX-R02 at the cited M01/M02 paragraphs. See [expanded traceability](../requirements/Expansion_01_Traceability.md). All criteria are unchecked requirements candidates, not executed checks.
