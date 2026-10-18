# A member-to-return journey for KitDesk

A member finds the particular drill they need, checks an intended interval and books it. They can later retrieve their own reservation, cancel it if an agreed policy permits, or see the actual loan after collection. At the desk, staff prepare collections, record the physical handover, locate outstanding loans and record receipt. A damaged drill can be returned while a separate condition case stays open. Staff can inspect a separately assumed overdue workload; a member can report a problem without pretending to return the tool online.

Those are connected outcomes, not a promise that every difficult policy has been decided. A catalog card is not a reservation, a reservation is not possession, receipt is not clearance, and clearance is not a complete availability policy.

## What this backlog is

**Local demo backlog, version 2, 2026-10-18.** Derived from the nine version-1 [Expansion 01 sources](../../sources/expansion-01/README.md) and the explicitly adopted, user-authorized [simulated DD-01–08 checkpoint](../discovery/Demo_Readiness_Decisions_20261018.md). FX inputs are invented, not real research. DD outcomes are settled fictional demo decisions, not real stakeholder approval. Actual user role-play UD-01–08 are preserved in [KD-ST-001 v3](KD-ST-001-book-available-equipment.md). No application or live membership/qualification dependency exists.

The pack proposes 13 slices including KD-ST-001. Routine and damaged return are combined here because both record the same correct-item receipt, with damage initiating condition handling. That yields **12 stories total: 1 existing + 11 new**, not 13 padded stories. Condition assessment remains independently useful. Search/list/detail, denial, privacy, feedback and technical layers are not separate stories.

**Exactly seven requirements stories are Ready and five remain Backlog**, as below. The seven revised public Issue bodies and their Ready statuses were verified on [Project 3](https://github.com/users/JustinS95/projects/3) at completion on **2026-10-18T14:28:46Z**; the other five remained Backlog. This is a timestamped snapshot, not a real-time guarantee. Ready means the bounded behavior/AC questions are settled for the fictional demo; all engineering, software verification and deployment remain future work. All AC are unchecked. Historical question tables are retained with explicit current resolution/AC supplements on the seven stories.

## Story guide

| Local story | Useful outcome | Evidence maturity and main limit |
|---|---|---|
| [KD-ST-001 — Book available equipment](KD-ST-001-book-available-equipment.md) | Automatically confirm/reserve eligible interval | **Ready**: DD-01/02/03/05/06/08; real adapters, qualification facts/fakes and access implementation remain engineering work. |
| [KD-ST-002 — Find the right equipment and check an interval](KD-ST-002-discover-equipment.md) | Choose an item and distinguish interval outcomes | **Ready**: DD-01/03/05/06/08 settle time, qualification, matching/categories and interaction. Catalog implementation unbuilt. |
| [KD-ST-003 — Review my bookings and what happened to them](KD-ST-003-review-own-bookings.md) | Retrieve own known outcomes privately | **Ready**: DD-04/05/06/08 settle known lifecycle, exact fields/retention; cancelled/collected fixtures can support future validation. |
| [KD-ST-004 — Cancel an eligible booking of my own](KD-ST-004-cancel-own-booking.md) | Release selected reservation | **Backlog**: cancellation eligibility/cutoff and no-show remedies remain open; DD-04 settles shared race invariant only. |
| [KD-ST-005 — Prepare the collection workload](KD-ST-005-prepare-collections.md) | Read start-filtered collections and task contacts | **Ready**: DD-01/04/05/06/08 settle interval/fields/known transitions/access; queue implementation unbuilt. |
| [KD-ST-006 — Record actual equipment handover](KD-ST-006-record-handover.md) | One loan for correct booking/item/member | **Ready**: DD-01–05/07/08 settle qualification, recheck, proof, timing, races and due fact; adapters/fakes and once-only implementation remain. |
| [KD-ST-007 — See my actual loan status and recorded return](KD-ST-007-view-own-loans.md) | Own possession/receipt facts, not internal assessment | **Ready**: DD-03/05/06/07/08 settle fields/history/due/read states; explicit returned fixtures do not require KD009 implementation. |
| [KD-ST-008 — Find an outstanding loan for desk work](KD-ST-008-locate-outstanding-loans.md) | Exact item/borrower-reference task lookup | **Ready**: DD-05/06/07/08 settle matching/selection/contact/report allowance; optional report fixtures do not require KD012 submission. |
| [KD-ST-009 — Record an equipment return and any observed damage](KD-ST-009-record-equipment-return.md) | Receipt once plus damage case | **Backlog**: wrong-item/partial-kit/correction, inspection/qualification authority and sensitive observation policy remain. DD-03 forbids receipt-as-clearance. |
| [KD-ST-010 — Assess an item condition case](KD-ST-010-review-condition-cases.md) | Assessment and specific case outcome | **Backlog**: actual reviewer authority, evidence/reversals and assessment-context privacy remain; qualification consumption is not an implemented clearance workflow. |
| [KD-ST-011 — Review the overdue lending workload](KD-ST-011-review-overdue-workload.md) | Classified overdue set without delivery | **Backlog**: overdue threshold/grace/disputes/classifier and follow-up fields remain; DD-07 due fact is not overdue classification. |
| [KD-ST-012 — Report a problem with equipment I still have](KD-ST-012-report-loan-problem.md) | Own-loan report capture | **Backlog**: report capture/moderation/response/urgency service unresolved; DD-05 settles only existing reported-content consumption in KD008. |

## A sensible sequence to discuss, not an approved priority

1. **Explain the simulated decision checkpoint before promising a journey.** DD-01–08 settle the seven stories' rules, not a real workshop, code or tests. Future engineering must implement time, membership, qualification, access and once-only outcomes.
2. **Show finding and privately retrieving a reservation:** KD-ST-002 + KD-ST-001 + KD-ST-003 using explicitly known item/membership facts.
3. **Show reservation becoming possession:** KD-ST-005 + KD-ST-006 + KD-ST-007. A stale queue row is not collection eligibility. A confirmed booking is not a loan.
4. **Discuss physical receipt and separate assessment:** KD-ST-008 is Ready for lookup; KD-ST-009/010 remain Backlog. Use declared receipt fixtures only for read-branch discussion, not a claimed completed return service.
5. **Explore recovery and information around that journey:** KD-ST-004, KD-ST-011 and KD-ST-012. Cancellation can move earlier if review finds greater value; neither an overdue clock nor emergency report response is supplied by this sequence.

This adapts FX-SRC-09 § L03, whose order is also only a suggestion. No estimate, capacity, release cut, owner assignment or actual business priority has been approved. FX-Q14 asks how to choose and measure a launch outcome.

## Local dependencies are not readiness decisions

Here **A → B means A produces a business record/outcome consumed by B**. It is a local record prerequisite, not a mandated screen route, architecture or instruction to block all partial work until A is delivered.

| Producer → consumer | Actual prerequisite | What it does not mean |
|---|---|---|
| KD-ST-001 → KD-ST-003/004/005/006 | A confirmed booking/reservation exists | Discovery KD-ST-002 is not required to reach booking; queue access is not collection eligibility. |
| KD-ST-004/006 → KD-ST-003 | Cancelled/collected branches consume known cancellation/handover outcomes | Own confirmed-booking retrieval can be useful first; all later lifecycle workflows need not be complete. |
| KD-ST-006 → KD-ST-007/008/009/011/012 | An actual loan exists; each operation applies its own record/state scope | Booking confirmation alone cannot supply possession. Overdue still needs its own policy/classification. |
| KD-ST-009 → KD-ST-007/008/011 | Returned state is reflected in own status and exclusion from outstanding lookup/workload | Lookup/read stories do not require a return to show an outstanding record; this is an outcome-consumption branch, not a reverse dependency. |
| KD-ST-009 → KD-ST-010 | Damaged receipt creates a specific condition case | Receipt need not wait for reviewer assessment or clearance. |
| KD-ST-012 → KD-ST-008/009 | A related report is shown when present | Reports are optional context; finding or returning an unreported loan still has value. |

These edges have no directed cycle. Selecting a record through a particular screen is only an association: KD-ST-005 need not precede every handover, and KD-ST-008 is not a mandated return interface. DD-03 requires explicit known qualification facts, not delivery of KD-ST-010 or a clearance shortcut. Historical FX questions are not fabricated done predecessors; the DD checkpoint scopes which are resolved for seven stories and which remain on deferred work. Explicit fixtures permit future isolated validation, not a claim of implementation or execution.

## Gaps and unadopted candidates

- **Engineering prerequisites, not open seven-story business rules:** implement DD time/DST, current membership obligation/member linking, explicit qualification consumption, exact field/task retention and bounded keyboard/text interactions. Real adapters/accounts, production retention/deletion/compliance and usability/conformance validation are not established.
- **Unfinished deferred branches:** cancellation eligibility/cutoff/no-show remedies, wrong-item/partial-kit receipt, disputed damage, erroneous return/clearance correction, inspection evidence and reviewer delegation. Shared race/collection identity/timing and no-auto-transition rules are now settled by DD-04, not left to arbitrary defaults.
- **Problem-report service boundary:** capture is not notification, a monitored emergency channel, safety advice or a promised staff response.
- **Unadopted candidates:** reminders, notification channels, weekly exports, waitlists, walk-ins/proxies/substitutes/extensions and staff overrides require separate outcome/access/policy decisions. They are not promised phase-two work.
- **Excluded:** payments/fines, purchasing, transfers between workshops, recurring bookings and public self-registration. Training checks and manual/pending approval do not reappear in this backlog.
- **Measurement:** fewer desk emails or fewer mismatched handovers are competing proposals, not proven benefits or numeric targets.

## Evidence and publication status

Use the [discovery synthesis](../discovery/Expansion_01_Discovery_Synthesis.md) for historical derivation and current question disposition; [AC traceability](../requirements/Expansion_01_Traceability.md) for source/decision/AC mappings; and [historical bounded self-review](../reviews/Expansion_01_Backlog_Self_Review.md) for findings at that earlier checkpoint. The [DD provenance and supersession](../discovery/Demo_Readiness_Decisions_20261018.md#provenance-and-historical-review-supersession) identifies which findings are now resolved or remain deferred. The five Backlog bodies retain their original provisional questions: a shared DD answer supersedes a specific older claim, not the workflow's remaining blockers or readiness.

**Issue-body and board publication is complete for the seven Ready stories; repository documentation publication remains pending.** See the [publication snapshot](../discovery/Demo_Readiness_Decisions_20261018.md#public-issue-and-board-publication) for all twelve public Issue links and the verified seven/five partition. The earlier all-Backlog observation at 2026-10-18T13:25:32Z is historical, superseded by the completed publication snapshot above. Original sources and immutable integration evidence are preserved. This backlog is not implementation, release or test evidence.
