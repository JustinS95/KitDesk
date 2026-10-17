# A member-to-return journey for KitDesk

A member finds the particular drill they need, checks an intended interval and books it. They can later retrieve their own reservation, cancel it if an agreed policy permits, or see the actual loan after collection. At the desk, staff prepare collections, record the physical handover, locate outstanding loans and record receipt. A damaged drill can be returned while a separate condition case stays open. Staff can inspect a separately assumed overdue workload; a member can report a problem without pretending to return the tool online.

Those are connected outcomes, not a promise that every difficult policy has been decided. A catalog card is not a reservation, a reservation is not possession, receipt is not clearance, and clearance is not a complete availability policy.

## What this backlog is

**Local candidate backlog, version 1, pending user review.** Derived from the nine version-1 [Expansion 01 sources](../../sources/expansion-01/README.md), which are invented fixtures, not real interviews, observations or stakeholder approvals. There is no application or verified dependency. UD-01–UD-08 remain the only actual user-confirmed booking decisions; [KD-ST-001 v2](KD-ST-001-book-available-equipment.md) is unchanged.

The pack proposes 13 slices including KD-ST-001. Routine and damaged return are combined here because both record the same correct-item receipt, with damage initiating condition handling. That yields **12 stories total: 1 existing + 11 new**, not 13 padded stories. Condition assessment remains independently useful. Search/list/detail, denial, privacy, feedback and technical layers are not separate stories.

All 11 new stories are candidates. Three are **draft complete under stated fixture premises** for their deliberately bounded information scope; eight are **provisional—specific clarification needed**. Neither label means stakeholder acceptance, implementation readiness or a board Ready state. All AC are unchecked.

## Story guide

| Local story | Useful outcome | Evidence maturity and main limit |
|---|---|---|
| [KD-ST-001 — Book available equipment](KD-ST-001-book-available-equipment.md) | Automatically confirm and reserve an eligible available interval | Existing user-approved refinement; not fully implementation-ready. Time/DST, membership evidence and condition qualification remain open. |
| [KD-ST-002 — Find the right equipment and check an interval](KD-ST-002-discover-equipment.md) | Choose the actual item, distinguish no matches and unknown interval availability | Provisional: FX-Q01/03/11 and unprovided search matching/category examples. |
| [KD-ST-003 — Review my bookings and what happened to them](KD-ST-003-review-own-bookings.md) | Retrieve own confirmed/cancelled/collected records privately | Draft complete under fixture premises for retained records; FX-Q10 retention and FX-Q02 no-show policy are not invented. |
| [KD-ST-004 — Cancel an eligible booking of my own](KD-ST-004-cancel-own-booking.md) | Release only the selected booking's reservation on known eligible completion | Provisional: FX-Q02 cutoff and cancellation/handover race. |
| [KD-ST-005 — Prepare the collection workload](KD-ST-005-prepare-collections.md) | Inspect chosen-interval collections with task-needed contact access | Provisional: FX-Q01 interval semantics and FX-Q10 exact contact fields. |
| [KD-ST-006 — Record actual equipment handover](KD-ST-006-record-handover.md) | Link one actual loan to the right confirmed booking/item/member | Provisional: FX-Q02/03/04/05/12 and borrower identity/collection timing evidence. |
| [KD-ST-007 — See my actual loan status and recorded return](KD-ST-007-view-own-loans.md) | Distinguish outstanding possession from receipt, without internal notes | Draft complete under fixture premises for known loan facts; FX-Q06 due derivation, FX-Q09/10 extra condition/history content and missing read-state design stay open. |
| [KD-ST-008 — Find an outstanding loan for desk work](KD-ST-008-locate-outstanding-loans.md) | Find the loan without a booking date or overdue classification | Draft complete under fixture premises for bounded lookup; exact borrower matching and FX-Q10 field/note rules are unfinished. |
| [KD-ST-009 — Record an equipment return and any observed damage](KD-ST-009-record-equipment-return.md) | Record receipt once; damaged receipt also creates an operational case | Provisional: FX-Q03 availability/inspection and FX-Q09 wrong-item, partial-kit and correction paths. |
| [KD-ST-010 — Assess an item condition case](KD-ST-010-review-condition-cases.md) | Record assessment; clear that case or retain its restriction | Provisional: FX-Q08 actual authority/evidence/reversals, FX-Q03 availability and FX-Q10 sensitive context. |
| [KD-ST-011 — Review the overdue lending workload](KD-ST-011-review-overdue-workload.md) | Inspect an explicitly assumed classified set without sending reminders | Provisional: FX-Q06 due/overdue policy and evidence; FX-Q07 delivery remains unadopted. |
| [KD-ST-012 — Report a problem with equipment I still have](KD-ST-012-report-loan-problem.md) | Attach a member report to an own outstanding loan, visible in desk context | Provisional: FX-Q13 response/urgency ownership and FX-Q10 sensitive content. Capture alone is useful but not a monitored-response service. |

## A sensible sequence to discuss, not an approved priority

1. **Clarify shared policy before promising a complete journey.** Use concrete time/DST and condition examples (FX-Q01/03), establish membership evidence and collection policy (FX-Q04/05), and resolve identity/race boundaries. These are discovery needs, not additional implementation stories or permission to contact people.
2. **Show finding and privately retrieving a reservation:** KD-ST-002 + existing KD-ST-001 + KD-ST-003. Conditional item/interval examples are useful while complete time/condition policy is unresolved.
3. **Show reservation becoming possession:** KD-ST-005 + KD-ST-006 + KD-ST-007. A stale queue row is not collection eligibility. A confirmed booking is not a loan.
4. **Show physical receipt and separate assessment:** KD-ST-008 + KD-ST-009 + KD-ST-010. Review FX-Q08/09/10 before claiming the service handles real damage disputes or broad note access.
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

These edges have no directed cycle. Selecting a record through a particular screen is only an association: KD-ST-005 does not have to be delivered before every handover, and KD-ST-008 is not a mandated return interface. KD-ST-010 does not produce a settled availability decision for KD-ST-001/002/006. FX-Q01–14 are policy/evidence gaps, not fabricated “done” predecessor items. Explicit assumed records permit draft review, not implementation or test execution.

## Gaps and unadopted candidates

- **Cross-cutting qualification:** time/DST and allowed intervals; authoritative membership identity/states/freshness; condition-to-booking/collection rules; staff contact minimization, note handling and retention; accessible/assisted interactions. Unknowns do not authorize arbitrary defaults.
- **Unfinished operational branches:** cancellation versus handover, no-shows, collection identity/timing, wrong-item/partial-kit receipt, disputed damage, erroneous return/clearance correction and real reviewer delegation. Supported core branches remain useful without pretending these are solved.
- **Problem-report service boundary:** capture is not notification, a monitored emergency channel, safety advice or a promised staff response.
- **Unadopted candidates:** reminders, notification channels, weekly exports, waitlists, walk-ins/proxies/substitutes/extensions and staff overrides require separate outcome/access/policy decisions. They are not promised phase-two work.
- **Excluded:** payments/fines, purchasing, transfers between workshops, recurring bookings and public self-registration. Training checks and manual/pending approval do not reappear in this backlog.
- **Measurement:** fewer desk emails or fewer mismatched handovers are competing proposals, not proven benefits or numeric targets.

## Evidence and local-only boundary

Use the [discovery synthesis](../discovery/Expansion_01_Discovery_Synthesis.md) for decisions, conflicts and clarification order; [AC traceability](../requirements/Expansion_01_Traceability.md) for exact source paragraphs/premises/questions; and [bounded self-review](../reviews/Expansion_01_Backlog_Self_Review.md) for reasoning and compromises.

**No remote writes or queries were performed for this expansion.** Existing public Issue 1 corresponds only to KD-ST-001; it is not evidence that any expansion text is published or approved. No new story has a remote ID/mapping. Original KD-ST-001, original historical source document contents and historical integration records remain unchanged; the new source pack is additive and project navigation was updated separately. This local backlog is not an implementation, release note or test result.
