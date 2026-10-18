# KitDesk simulated discovery checkpoint — 2026-10-18

## Approved fictional decisions — local requirements authority

**Status: approved by the user for this fictional demo on 2026-10-18.** After reviewing the summary and this checkpoint, the user replied **“looks good. You may proceed”**. DD-01–08 below are adopted role-play decisions, associated with fictional consultation roles Maya (lending), Aisha (membership/privacy), Leon (scope) and Sam (engineering advice). The approval is the user's, not evidence that characters or real stakeholders met or approved anything. No live service, implementation or test is claimed. UD-01–08 remain user role-play decisions and retain precedence within their scope.

The approved decisions and linked canonical AC settle **seven requirements stories** for the fictional demo, not production policy or software execution readiness. Their revised public Issue bodies and Ready statuses were subsequently verified at publication completion on **2026-10-18T14:28:46Z**; five workflows remained Backlog. This is a timestamped snapshot, not a real-time guarantee. Original FX/SRC sources, historical reviews and integration evidence remain baselines; the resolution table below identifies current supersession without rewriting their original findings. No application or tests exist. Repository documentation publication remains pending.

## Adopted fictional decisions — DD-01–08

### DD-01 — Clock, intervals and queue inclusion (Maya + Leon)

Use IANA `Europe/London`. Display local date/time with zone and UTC offset; store/compare the represented instants conceptually, without prescribing storage technology. A booking requires item, start and end; both timestamps must be valid, end strictly after start, and start at or after submission time. No maximum duration, advance window or opening-hours constraint is imposed in this demo. Minute precision is used. Reject nonexistent spring-forward times; for repeated fall-back times require the member to select one of the two displayed offsets before submission. Reject invalid/missing/ambiguous input with an explanation and no booking/reservation. Availability checking uses the same validation; invalid input is not an available/unavailable result.

Intervals are start-inclusive/end-exclusive. Gap comparison uses elapsed minutes between instants: at least 30 minutes in either request order, **exactly 30 allowed**, as UD-05 requires. A coordinator chooses a valid start/end interval under the same zone/DST rules (past intervals allowed for queue inspection). Include confirmed, uncollected bookings whose **start** is at or after queue start and before queue end; not every booking that overlaps it. Invalid queue input is explained without claiming an empty workload. No default today is selected. Worked boundaries: queue [09:00,12:00) includes a 09:00 start, excludes a 12:00 start. On 2026-03-29 London 01:30 is nonexistent; on 2026-10-25 01:30 requires +01:00 or +00:00 selection.

### DD-02 — Authoritative membership obligation, not a delivered service (Aisha + Maya)

The scenario's membership register is the business authority, keyed by the authenticated member's immutable member reference. No name/email matching establishes membership. Booking and each handover must obtain a current eligibility determination for that operation from this authority: active, inactive, or unable to verify. A previous booking check or cached result from a previous operation is not sufficient. Missing member link, missing record, missing/contradictory status, unavailable lookup or indeterminate result means unable to verify, not active or inactive. Only active permits the operation; inactive and unknown fail closed, explain their distinct reasons, and create no booking/loan. No override or training gate. Inactive members may still read their own retained records; membership eligibility is not read authorization.

The real adapter, freshness mechanism, authentication/member linking, failure simulation and access enforcement remain engineering prerequisites. A controlled fake register may supply explicit active/inactive/unknown fixture outcomes for future demo validation; no live register contract, accounts or integration proof is asserted or required to decide these requirements. SRC-07 remains an unapproved technical option.

### DD-03 — Consume explicit condition qualification; do not invent clearance (Maya)

An item must have an explicitly established current **lendable** qualification and no outstanding actual loan or active restriction to permit a new booking or handover. A known restriction, known non-lendable qualification or outstanding loan yields unavailable/refused. Missing/contradictory qualification or unavailable condition/possession data yields unable to determine and prevents confirmation/handover; unknown is never lendable. Re-evaluate at confirmation and handover, not just when browsing. Existing reservations are not silently cancelled when qualification changes. Members see only availability/qualification outcome, not damage notes, case details or borrower identity.

This defines consumption of known item facts, not a new condition-editing, inspection, repair or clearance workflow. Explicit eligible/restricted/unknown fixtures support the seven stories independently of KD-ST-009/010 implementation. Receipt alone never changes qualification to lendable or clears a restriction; clearing one case alone is insufficient to establish lendability. Until a qualification is explicitly known, the consuming operation fails closed. Who establishes/restores qualification, inspection evidence and reversal/correction remain deferred with KD-ST-009/010. No shelf-ready shortcut or blanket safety certificate is adopted.

### DD-04 — Handover, identity, time and lifecycle races (Maya + Aisha + Leon)

Only an authorized desk coordinator records handover, and only during the booking interval: start <= actual handover instant < end. No early/late collection, walk-ins, proxies or physical-item substitutions. Compare the attending member's workshop membership card member reference to the booking's member reference and the physical asset label to its item reference; both must match. A missing/unreadable card/label or mismatch refuses recording with explanation, no new loan and no booking change. Do not retain card images/numbers beyond the existing member reference. The coordinator explicitly confirms actual transfer, not merely preparation or selection. Check DD-02/03 at completion. Success creates exactly one outstanding loan, actual handover timestamp and collected booking outcome linked to the same member/item/booking, plus DD-07's due obligation.

For competing transitions on the same booking, the **first successfully completed state transition wins**. If eligible cancellation completes first, handover is refused as cancelled with no loan. If handover completes first, cancellation cannot cancel the collected booking or change its loan. Preparation grants no lock. Concurrent/repeated handovers yield one linked loan and the known outcome, not duplicates. A known failed transition changes nothing; uncertain completion requires reconciliation before retry and must not claim success or unchanged state. This shared race invariant does not settle cancellation cutoff/eligibility or no-show remedies, so KD-ST-004 stays Backlog. A missed booking remains confirmed/uncollected (not auto-cancelled/expired), is refused handover outside its interval, and has no implied loan. No automatic reservation extension or future-booking remedy.

### DD-05 — Exact visible fields and purpose-scoped access (Aisha + Maya)

These are exhaustive field allowances for these views; absent optional facts display not recorded, not invented values. No contact directory, export, unrelated history or condition assessment access follows from a link.

| View | Allowed fields |
|---|---|
| KD002 catalog summary/detail | Physical item reference, display name, category, description, included-parts list, interval availability outcome and selected interval; missing description/parts explicitly not recorded |
| KD001 confirmation / KD003 own booking | Booking reference, own member reference, physical item reference/name, requested interval, outcome Confirmed/Cancelled/Collected, cancellation timestamp if present, linked loan reference if collected |
| KD005 collection queue/detail | Booking reference, physical item reference/name, requested interval, current booking outcome, borrower member reference/display name, recorded borrower email and phone if present; no other membership fields |
| KD006 handover context/result | KD005 fields, membership eligibility outcome (not membership history), qualification outcome (not internal notes), actual handover timestamp, loan reference, recorded due instant |
| KD007 own loan | Loan reference, own member reference, physical item reference/name, linked booking reference, handover timestamp, Outstanding/Returned status, receipt timestamp if present, explicit due instant if present |
| KD008 outstanding lookup/detail | Loan reference, physical item reference/name, borrower member reference/display name, recorded email/phone if present, linked booking reference, handover timestamp, Outstanding status, explicit due instant if present; selected-loan report context as below |

Desk contact fields are read only for the selected collection/outstanding lending task; missing contacts do not prevent read/handover and are not fabricated. Collection contact access ends at booking end or earlier cancellation/collection; a missed booking's retained historical queue row does not retain contact access. Show contacts as unavailable for that task after the boundary, not falsely not recorded. Members cannot use staff views, even for their own record. Member reads are authenticated own-record only across all statuses, including reference substitution/bypassed controls; denied access reveals no protected details. Unauthorized mutation leaves records unchanged and explains denial. Non-desk actors cannot obtain staff lending/contact data. No default operational person, role identifier, assignee or production account is invented.

KD008 may read a related report's reference, submission timestamp, author's member reference (which must match this loan's borrower), and member-submitted description as **member-reported**, not verified damage/receipt. Render description as inert text, never active markup; do not load attachments or expose internal assessments/moderation notes. This task-specific allowance does not authorize general report search or promise sanitized personal content, emergency monitoring, notification or response time. New report capture, sensitive-content moderation and response handling remain KD-ST-012's unresolved service work. Existing synthetic report fixtures may be consumed without implementing submission.

### DD-06 — Retrieval, matching, ordering and visible-history window (Aisha + Maya)

KD002: trim leading/trailing query whitespace and match case-insensitive literal substrings of display name or item reference; no stemming, spelling correction or other-field search. Empty query browses all. Category is an exact selected value: `Power tools`, `AV equipment`, `Hand tools`; no selection means all; combine query/category with AND. Sort item reference ascending and show all matches (no pagination/result cap in this small demo). Thus ` DRILL ` matches KD-EQ-001 Cordless Drill, `KD-EQ-003` matches Portable Projector; `drill` + `AV equipment` has no matches. These rules adopt the sample categories, not a claim that its condition labels are authoritative qualification.

KD008: choose item reference or borrower member reference; trim whitespace, case-insensitive exact whole-reference match only. No name, partial-name, email or phone searching and no member-directory suggestions. An empty query prompts for a reference and does not browse all loans. One borrower may match several outstanding loans; list all sorted by loan reference ascending, require explicit selection, never auto-select the first. Returned loans never match. No match differs from unavailable results. `KD-EQ-001` matches that item's outstanding record; `KD-EQ-00` does not. Borrower reference remains a supported borrower lookup, not a scope reduction to item-only search.

KD003 lists all visible own bookings in requested-start descending order, then booking reference ascending; KD007 lists outstanding first, then handover descending and loan reference ascending; no result cap/pagination. KD005 sorts booking start ascending then booking reference. Empty own-loan list shows no loans, retrieval failure shows unavailable data, not no loans. No exact message copy or latency SLA is mandated.

Visible-history retention: bookings are visible until **365 elapsed days after the later of requested end, cancellation timestamp or handover timestamp**, ignoring absent events; at that boundary exclude them from ordinary member/history reads and collection-queue reads, even if still confirmed/uncollected. Outstanding loans remain visible for their entire outstanding lifetime; returned loans remain visible until **365 elapsed days after actual receipt**, then are excluded. An outstanding loan keeps its linked booking available in own loan context even if the ordinary booking-history window ended; no other-member detail is exposed. Contacts/report context in staff views are available only while the selected collection/outstanding task qualifies, not after it ends; an already open stale view must recheck before further reads/actions. Collection contact scope ends under DD-05 even before its row's history window ends; outstanding-loan contact/report scope ends on receipt. No indefinite-history promise. Physical deletion, legal holds, audit/archive administration and access outside these views are not implemented by this read slice and need separate policy before real deployment. This is a concrete demo visibility/retention decision, not a production compliance claim.

### DD-07 — Explicit due obligation, without an overdue clock (Maya + Leon)

On successful handover record the booking's resolved end instant as that loan's **explicit due obligation**, visible in handover result and own/staff loan views. Preserve it as a loan fact; do not later recalculate it from a changed booking or infer it from receipt/lateness. No due-date editing or extension is authorized. Legacy/synthetic loans without a due fact display due not recorded; do not backfill by guessing. Known fixtures may include a stated due instant. This resolves the seven stories' due display/creation, not KD-ST-011's overdue threshold, grace, disputes or notification policy. A due instant alone does not adopt an overdue classifier.

### DD-08 — Bounded interaction contract and accessibility limits (Leon + Maya)

For the seven demo stories all read/submit controls have descriptive names, are keyboard-operable, show visible focus, and expose results, validation and denial as text rather than color alone. A coordinator may explain the interface but cannot impersonate a member's booking action or override eligibility. No alternate proxy workflow is adopted. This settles the bounded interaction expectations formerly FX-Q11 on KD002/005; missing participant research, formal conformance targets and usability testing remain real-world validation prerequisites, not fictional completed research or a compliance certification.

<a id="question-closure-ac-propagation-and-readiness"></a>

## Question closure, AC propagation and local readiness

The user-approved decisions resolve the following historical questions for the bounded seven-story scope. Each canonical story retains its question history and current decision-to-AC resolution table. Readiness means requirements-ready **for the fictional demo**, not implemented or tested. Public body/board publication is recorded separately below; it does not establish independent requirements review or software verification.

| Local story | Historical blocker resolution | Current AC supplement | Engineering or connected work still required | Local requirements status |
|---|---|---|---|---|
| [KD-ST-001](../stories/KD-ST-001-book-available-equipment.md) | OQ-01/02/05 → DD-01/02/03; fields/history DD-05/06 | AC-09–12 | Adapter/authentication/qualification fixtures; no live service or tests | Ready |
| [KD-ST-002](../stories/KD-ST-002-discover-equipment.md) | FX-Q01/03/11, M01 gap → DD-01/03/06/08; fields DD-05 | AC-05–08 | Catalog/availability implementation, accessible interaction verification | Ready |
| [KD-ST-003](../stories/KD-ST-003-review-own-bookings.md) | FX-Q02/10 → DD-04/05/06 | AC-05–07 | Known cancelled/collected fixtures; cancellation workflow still deferred | Ready |
| [KD-ST-005](../stories/KD-ST-005-prepare-collections.md) | FX-Q01/02/10/11/12 → DD-01/04/05/06/08 | AC-05–08 | Booking/contact fixtures, access enforcement and queue implementation | Ready |
| [KD-ST-006](../stories/KD-ST-006-record-handover.md) | FX-Q01/02/03/04/05/12, FX-C04, O02 gap → DD-01–05/07 | AC-05–09 | Membership/condition adapters or explicit fakes; atomic transition implementation | Ready |
| [KD-ST-007](../stories/KD-ST-007-view-own-loans.md) | FX-Q06/09/10, M04/D04 gap → DD-03/05/06/07 | AC-04–06 | Loan/receipt fixtures; KD009 implementation need not precede a read fixture | Ready |
| [KD-ST-008](../stories/KD-ST-008-locate-outstanding-loans.md) | O03 gap, FX-Q06/10 → DD-05/06/07 | AC-05–08 | Outstanding/report fixtures; KD012 submission and KD009 receipt remain separate | Ready |

**Five stories remain Backlog:** KD-ST-004 (cancellation eligibility/cutoff, no-show remedies), KD-ST-009 (wrong-item/partial-kit/correction and inspection authority), KD-ST-010 (reviewer authority/evidence/reversals), KD-ST-011 (overdue classification/disputes), KD-ST-012 (capture/moderation/response service). Their bodies remain historical provisional drafts, not fully propagated current DD specifications. Shared DD rules supersede their older statements only where explicitly resolved: notably DD-01 clock, DD-03 qualification consumption, DD-04 shared race and DD-07 due creation. None settles the remaining workflow gaps. See the [current backlog](../stories/EXPANDED_BACKLOG.md) for the exact seven/five partition. The all-Backlog observation at 2026-10-18T13:25:32Z is historical; the later verified publication snapshot follows below.

## Provenance and historical review supersession

An earlier revision preceded decision approval and was explicitly provisional. The user's subsequent approval above supplies the current fictional requirements authority. This preserves the sequence; it does not retroactively turn earlier author reasoning or checks into approval or independent review.

The [historical author self-review](../reviews/Expansion_01_Backlog_Self_Review.md) and [KD001 review](../reviews/KD-ST-001-draft-review.md) remain unchanged. Their originally open findings were valid at their timestamps. Current supersession: F01 → DD-03 for consumption only (qualification establishment/restoration stays deferred); F02 → DD-02/04 for handover/recheck/race (cancellation eligibility stays deferred); F04 → DD-07 for due creation only (overdue classification stays deferred); F05 → DD-05/06/08 for the seven scoped read/interaction contracts (report service, production compliance and participant validation remain absent); F06 navigation is corrected in current indexes. F03 reviewer authority remains unresolved on KD010. The same DD-01/02/03 resolution closes KD001's historical OQ-01/02/05 within its bounded scope.

Author reconciliation compares actor/task fields, own/staff record boundaries, reservation versus loan versus receipt/qualification, first-completed-transition races, due versus overdue, and optional fixture producers versus deferred workflows. It is not independent review, operational evidence or a new policy decision. The subsequent public Issue/Status update does not change those limits.

<a id="proposed-board-handoff--no-mutation-performed"></a>

## Public Issue and board publication

**Verified at completion on 2026-10-18T14:28:46Z:** seven revised public Issue bodies were published and their items moved to Ready on [Project 3](https://github.com/users/JustinS95/projects/3). The final twelve-item verification confirmed the five deferred Issues remained unchanged in Backlog. This timestamped snapshot supersedes the earlier all-Backlog baseline and proposed publication handoff; it is not a real-time board guarantee.

| Story | Public Issue | Verified Status | Public body |
|---|---|---|---|
| KD-ST-001 | [#1](https://github.com/JustinS95/KitDesk/issues/1) | Ready | Revised |
| KD-ST-002 | [#3](https://github.com/JustinS95/KitDesk/issues/3) | Ready | Revised |
| KD-ST-003 | [#4](https://github.com/JustinS95/KitDesk/issues/4) | Ready | Revised |
| KD-ST-004 | [#5](https://github.com/JustinS95/KitDesk/issues/5) | Backlog | Unchanged |
| KD-ST-005 | [#6](https://github.com/JustinS95/KitDesk/issues/6) | Ready | Revised |
| KD-ST-006 | [#7](https://github.com/JustinS95/KitDesk/issues/7) | Ready | Revised |
| KD-ST-007 | [#8](https://github.com/JustinS95/KitDesk/issues/8) | Ready | Revised |
| KD-ST-008 | [#9](https://github.com/JustinS95/KitDesk/issues/9) | Ready | Revised |
| KD-ST-009 | [#10](https://github.com/JustinS95/KitDesk/issues/10) | Backlog | Unchanged |
| KD-ST-010 | [#11](https://github.com/JustinS95/KitDesk/issues/11) | Backlog | Unchanged |
| KD-ST-011 | [#12](https://github.com/JustinS95/KitDesk/issues/12) | Backlog | Unchanged |
| KD-ST-012 | [#13](https://github.com/JustinS95/KitDesk/issues/13) | Backlog | Unchanged |

**Repository documentation publication remains pending.** Publishing Issue bodies and board statuses did not publish the canonical repository story files or `team.yaml`. No application, executed tests, release or deployment is implied.

## Verification provenance and limits

- A prior revision records 67 structure/readiness/AC-sequence/decision/mapping/config assertions, 172 relative link targets and 11 heading fragments across 16 Markdown files, and 25 historical-question references. Those checks concerned the earlier broader state and do not verify this reconciled revision or establish approval. They were document checks, not software tests or semantic proof.
- Author connected-scope re-review covered member/desk access and exact fields, first-transition/one-loan invariants, qualification versus receipt/clearance, explicit due versus overdue, and optional fixture producers versus the five deferred workflows. KD001's twelve-AC composition was reviewed without artificial splitting.
- Historical document checks did not execute application/security/accessibility tests or establish live dependency behavior. They are separate from the later verified public Issue/board publication above.

At the earlier local reconciliation checkpoint, read-only static checks reported 16 scoped Markdown files, 190 local link targets, 16 heading/explicit-anchor fragments, twelve sequential unchecked AC sets, eight DD headings and the exact seven-Ready/five-Backlog index partition; no issues were found. Further checks covered 24 historical resolution-row labels and their AC references, core DD invariant wording and the then-applicable publication limitation. These results describe that revision, not a fresh check of subsequent edits. Historical unresolved questions remain intentionally labelled and mapped, not erased. These were document checks, not application tests, independent review or semantic completeness proof. Structured YAML parsing was not run.
