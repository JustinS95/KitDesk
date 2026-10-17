# KitDesk expansion: keep the promise, possession and condition distinct

A member reserves a particular drill, the desk records when it actually leaves, and staff later record that it came back. If it comes back damaged, the member need not remain recorded as possessing it while a reviewer assesses the concern. If the member reports a noise before returning it, that report is useful desk context—not receipt, proven damage or a guaranteed response.

This is the desired connected journey behind the [local candidate backlog](../stories/EXPANDED_BACKLOG.md). It expands the material available for BA/QA exercises without pretending the unresolved decisions have been made.

## Evidence and status

Version 1. Read the actual nine FX-SRC documents and [Expansion 01 guide](../../sources/expansion-01/README.md), [source index](../../sources/INDEX.md), project context, unchanged KD-ST-001 v2, its user-decision records and SRC-06 § A01–A03. The FX documents are version-1 **author-created synthetic fixtures**. Scenario dates only order the invented narrative. No real interviews, meetings, observations, messages, source-system inspection or tests occurred.

Authority order for this bounded synthesis:

1. Actual user role-play decisions UD-01–UD-08 and canonical KD-ST-001 v2 retain their stated scope.
2. FX-R01–FX-R22 are review-pending author-defined premises for extension exercises, not additional user decisions.
3. Invented wishes, design suggestions, conflicts and FX-Q questions remain proposals/unknowns. Later detail or apparent fictional consensus supplies no approval.
4. Historical SRC statements remain historical, including approval language in project context. That discrepancy is not silently rewritten.

No binding public API, exact message, layout or interaction contract is established. The source design is text, not an inspected interface. The existing story README's “no stories” statement is historical stale text; the actual store contains KD-ST-001. That README is outside this task's edit authority and remains unchanged.

## Preserved user decisions

| Authority | Settled behavior | Limit that must survive expansion |
|---|---|---|
| [Intake UD-01/04](Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16) | Eligible available booking immediately confirms, without staff approval or pending stage | Confirmation is not physical handover; no manual fallback or override is inferred. |
| Intake UD-02/04 | Confirmed booking reserves the physical item for the requested interval | Not a temporary pre-confirmation hold; cancellation/no-show release was not settled. |
| Intake UD-03; [AC-trial UD-06](Booking_Decisions_AC_Trial_20261016.md) | Verified active membership is sufficient for membership/training eligibility at booking; no training checks | Availability still applies; checkout recheck is unresolved. |
| AC-trial UD-05 | At least 30 minutes between reservations of the same item, in either request order; exactly 30 permitted | Not a loan extension, cutoff, safety certification or condition clearance. Zone/DST remain open. |
| AC-trial UD-07/08 | Inactive/unverifiable membership and unavailable interval prevent a new confirmed booking/reservation, with explanation | Unverifiable is not inactive; no invented source/mapping/cache/timeout. Existing reservations stay unchanged on unavailability. |
| Intake DI-02/UD-04; KD-ST-001 AC-05/06 | Own booking visibility; no other-borrower names/contact in availability/outcomes | Task-based desk contact access is not a directory or general staff mutation permission. |
| KD-ST-001 AC-07 | Simultaneous confirmations still respect overlap and inspection separation | No first-click or other tie-break mechanism is selected. |

The extension does not modify any of KD-ST-001's eight AC or resolve its OQ-01/02/05. Its resolved questions about training, gap duration and booking failure outcomes are not reopened.

## What the synthetic premises add

The compact groups below are author premises, not recommendations promoted to decisions. Exact per-AC locators are in [traceability](../requirements/Expansion_01_Traceability.md).

| Fixture premises | Supported extension outcome / primary source |
|---|---|
| FX-R01/02 | Find physical items; distinguish catalog/no match/failure and conditional interval available/unavailable/unknown without borrower disclosure. FX-SRC-02 § M01/M02. |
| FX-R03 | Retrieve own known confirmed/cancelled/collected bookings, not pending approval. FX-SRC-02 § M03. |
| FX-R04/05 | Conditional own uncollected cancellation releases only its reservation on known eligible completion. No cutoff/race policy. FX-SRC-04 § P01/P02. |
| FX-R06 | Chosen-interval staff collections and task-needed contact access; empty differs from unavailable; stale row grants no handover. FX-SRC-03 § O01. |
| FX-R07/08 | Eligible actual handover creates one linked loan, not repeated loans; members do not record handover/return. FX-SRC-03 § O02. |
| FX-R09/10 | Own possession facts versus operational staff outstanding-loan lookup; neither is a membership directory or overdue calculator. FX-SRC-02 § M04; FX-SRC-03 § O03. |
| FX-R11/12/13 | Correct-item receipt once closes the loan; no-damage note is not bookability; damaged receipt also creates a related restricted condition case without debt/fault. FX-SRC-03 § O04; FX-SRC-08 § C01. |
| FX-R14/15 | A separately designated fictional reviewer inspects/assesses specific cases and clears or retains that restriction; actual authority and availability remain unresolved. FX-SRC-08 § C02/C03. |
| FX-R16/17 | Staff view a declared assumed overdue set; received loans leave that outstanding workload. No clock, delivery, export or fine. FX-SRC-04 § P04. |
| FX-R18/19 | Member report on an own outstanding loan, visible as reported content to author and task-scoped desk staff; not return or assessed damage. FX-SRC-02 § M04; FX-SRC-08 § C04. |
| FX-R20 | Staff access remains task/record-scoped; no general booking editing, correction, due change or override. FX-SRC-03 § O05. |
| FX-R21 | Known refusal/failure differs from uncertain completion; reconcile before potentially duplicating specified once-only outcomes. FX-SRC-06 § X05. |
| FX-R22 | Late possession does not extend the loan, rewrite/cancel the next booking or choose a remedy. FX-SRC-06 § X03. |

## Lifecycle and ownership tensions

These are business fact boundaries, not a storage design or claim about an implemented source of truth.

| Record/fact | Established transition and authorized fixture actor | Consumers and unresolved boundary |
|---|---|---|
| Booking/reservation | User-confirmed automatic booking; conditional own cancellation under FX-R04/05; eligible staff handover makes booking known as collected | Own history and collection workload consume these facts. No-show expiry, race winner and staff cancellation are not supplied. |
| Actual loan | Eligible coordinator records real handover once; coordinator records correct-item receipt once | Own loan, desk lookup and assumed overdue view consume possession. Member report does not change it; returned item is not still outstanding because its case is open. |
| Member problem report | Own outstanding-loan member submits a description; author and relevant desk staff can see it as reported | Not verified damage, a physical return, emergency monitoring or an automatic pre-return case/restriction. FX-Q03/13 remain. |
| Condition case | Damaged receipt creates the operational case/restriction; separately designated fixture reviewer assesses that specific case | Desk may consume related operational status; members do not read internal assessments. Clearing it does not settle canonical availability. Real authority, evidence and reversals remain FX-Q08. |
| Membership verification | Booking decision requires active evidence; inactive/unverifiable outcomes already settled | Source/identity/states/freshness unavailable. Staff task access does not grant membership editing; collection recheck is a separate policy decision. |
| Due/overdue | No derivation supplied; a stated assumed classification can support a bounded workload exercise | Cannot use requested booking end as a guessed due rule or “morning” as a clock. Notification timing is separately unadopted. |

## Conflicts retained, not voted away

| Conflict | Competing evidence and treatment | Affected scope |
|---|---|---|
| FX-C01 | Historical approval/pending sources versus UD automatic booking. Real user decisions supersede the old launch workflow; originals remain history. FX-SRC-01 § S02; FX-SRC-04 § P06. | No new approval story; KD-ST-001 unchanged. |
| FX-C02 | Cancel until handover versus earlier preparation cutoff. Neither selected. FX-SRC-04 § P01/P03; FX-SRC-06 § X01. | KD-ST-004/006; FX-Q02. |
| FX-C03 | “No damage noted” as shelf-ready versus receipt separate from assessment. FX-R12 forbids the shortcut only as a review-pending extension premise; it does not resolve canonical condition policy. FX-SRC-03 § O04. | KD-ST-001/002/006/009/010; FX-Q03. |
| FX-C04 | Recheck membership at collection versus avoid blocking during lookup failure. Neither selected. FX-SRC-07 § I03. | KD-ST-006; FX-Q04/05. |
| FX-C05 | Morning list versus due-instant classification; email desire versus portal visibility. No clock or channel selected. FX-SRC-04 § P04. | KD-ST-007/011; FX-Q06/07. |
| FX-C06 | Any coordinator clears damage versus designated reviewer. FX-R14 supplies an exercise designation, not a real authority resolution. FX-SRC-08 § C02. | KD-ST-009/010; FX-Q08. |

### Authored-source wording discrepancy — collected is not always outstanding

Separately from the six registered FX-C conflicts, FX-SRC-04 § P01, FX-R04 says a collected booking cannot be cancelled and “the actual loan remains outstanding.” That clause is not accepted unconditionally: a cancellation attempt can occur after recorded return. FX-SRC-04 § P02, FX-R05 preserves actual-loan state, while FX-SRC-03 § O04, FX-R11/12 establishes receipt/return, reflected in KD-ST-009 AC-01. On refusal, an outstanding loan stays outstanding and an already returned loan stays returned. Existing KD-ST-004 AC-03 correctly preserves that boundary and needs no change. This is explicit source reconciliation across cancellation and receipt, not a new stakeholder policy or newest-text precedence; original source wording remains unchanged as evidence.

## Clarification order to propose in a future role-play

No interviews, assignments or deadlines are committed here. Owners are fictional roles to ask, not contacted people. This order follows shared-rule impact, not approved business priority.

| Order | Open question and evidence to seek | Fictional consultation owner | Scoped impact / useful work still possible |
|---|---|---|---|
| 1 | FX-Q01: agreed interval, zone, DST and permitted-date/duration examples, including exact 30-minute separation in both request orders | Maya + Leon; time-zone owner unconfirmed | Blocks exhaustive booking/discovery/queue timing, not physical item identification or known-record retrieval. |
| 1 | FX-Q03: routine receipt, damaged receipt, pre-return report and cleared-case examples through later booking/collection | Maya | Blocks complete availability and inspection consequences, not correct-item receipt or case recording under premises. |
| 2 | FX-Q04: authoritative membership source, member linkage, states, mapping, freshness and usable evidence | Aisha + Sam | Blocks real dependency readiness; preserve existing inactive/unverifiable booking outcomes. No interface is invented. |
| 2 | FX-Q05: compare collection with active/inactive/unverifiable membership and failed lookup; choose recheck policy | Aisha + Maya | Blocks full handover eligibility, not reasoning about a separately established eligible example. |
| 2 | FX-Q02: actual handover/preparation timeline, cancellation cutoff, losing actor's outcome and no-show treatment | Maya + Leon | Blocks cancellation/race/no-show assertions; own-record scope and conditional release remain useful. |
| 3 | FX-Q08: actual assessment authority, evidence, clearance and reversal examples | Maya + Leon | Blocks real clearance service; separately designated fixture reviewer supports bounded exercises only. |
| 3 | FX-Q09: wrong item, partial kit, dispute and erroneous return as separate physical/correction examples | Maya | Blocks those branches, not known correct complete receipt. |
| 3 | FX-Q10: purpose-by-field review of contacts, reports, assessments and retention | Aisha | Blocks exhaustive field/retention rules; no directory or automatic member exposure is inferred. |
| 3 | FX-Q11: include missing accessibility/assisted-use perspectives and supported device needs | Leon; participants not represented | No usable-access or conformance claim can be made from the text design. Cross-cutting discovery should not wait for a finished UI. |
| 4 | FX-Q06: establish due obligation, clock/DST, threshold and disputes with a concrete chronology | Maya + Leon | Blocks calculated overdue behavior, not lookup or display of an explicitly assumed classified set. |
| 4 | FX-Q13: define routine versus urgent report response, ownership and safety guidance | Maya + Leon | Blocks monitored-response/safety claims; own report capture and task-scoped visibility remain useful. |
| 4 | FX-Q12: choose whether no-shows, walk-ins, proxies, substitutes or extensions deserve scope | Leon + Maya | No unsupported branch is silently adopted; collection identity/timing still need explicit evidence. |
| 5 | FX-Q07: first decide whether notifications are needed, then events/channels/recipients/consent/failure | Leon + Aisha | Delivery is unadopted, not part of a portal state change or a promised phase two. |
| 5 | FX-Q14: compare a compact journey with exception coverage, agree success measures and a baseline approach | Leon + Maya | Blocks quantified benefit, approved launch priority and release-readiness claims, not provisional backlog drafting. |

Search matching/category examples (FX-SRC-02 M01), borrower matching (FX-SRC-03 O03), collection identity/timing (O02), own-loan empty/unavailable states (M04/D04), and report limits/repetition/editing (M04) are additional unprovided details, not extra settled premises. They are scoped in the affected stories rather than hidden as defaults or allocated new FX-Q IDs.

## Derivation outcome and boundary

The 13 source candidates become 12 local stories, including untouched KD-ST-001, by merging routine/damaged return. No other supported candidate is dropped. There are 11 new candidate stories: 3 draft complete under bounded fixture premises, 8 provisional with specific clarification needs. Detailed source-to-AC coverage and excluded proposals are in [Expansion_01_Traceability.md](../requirements/Expansion_01_Traceability.md).

No meeting actions were fabricated, no source was edited, no application/tests were run and no remote system was queried or changed. Actual public Issue 1 remains relevant only to the existing KD-ST-001; new source content has no publication authorization or remote identity.
