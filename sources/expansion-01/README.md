# Expansion 01 — Synthetic lending discovery pack

Version 1. **Fictional author-created source material, not real research or stakeholder approval.** All dialogue, observations and scenario events in this folder are invented. Maya, Leon, Aisha, Sam and the unnamed members are role-play characters, not people contacted for this exercise. There is no implemented application, verified integration or executed test behind these sources.

## Authority and baseline

1. Actual user-confirmed UD-01–UD-08 retain precedence. Read the [discovery intake](../../artifacts/discovery/Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16), [AC-trial decisions](../../artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md) and unchanged [KD-ST-001 v2](../../artifacts/stories/KD-ST-001-book-available-equipment.md).
2. Those decisions establish automatic confirmed booking/reservation, active membership sufficient without training checks, at least 30 minutes between reservations of the same item including the exact boundary, own-record privacy, and no booking when membership is inactive/unverifiable or the interval unavailable. Original staff approval/pending designs are historical, not launch requirements.
3. **FX-R01–FX-R22 are author-defined synthetic extension premises, review pending.** They make a richer fictional dataset possible; they are not decisions by the user or the characters. They apply only to extension exercises explicitly adopting this pack. Quoted wishes are evidence candidates, not additional premises unless registered below.
4. Proposals, conflicts and FX-Q questions are not rules. Greater detail, a later scenario date or apparent agreement in invented dialogue does not confer authority. No premise settles KD-ST-001's date/time, membership-dependency or equipment-condition questions, or narrows its conditional available-item behavior.
5. [Original sources](../INDEX.md) remain immutable historical evidence. The [project context](../../project-context/PROJECT.md) still contains original approval language; do not silently apply it over UD decisions or edit history to remove the discrepancy.

Payments/fines, purchasing, multi-site transfers, recurring bookings and public self-registration remain excluded. No launch email, waitlist, override, training gate, walk-in loan or loan extension is established here. In-portal state visibility is not message delivery.

## Source navigation

Each FX-SRC document is version 1; its scenario date is narrative ordering only. Cite ID plus stable heading locator, for example `FX-SRC-03 § O03`. All links are local.

| ID | Source | Best used for |
|---|---|---|
| FX-SRC-01 | [Sponsor follow-up](01-sponsor-follow-up.md) | Problem, scope, inherited decisions, competing success ideas |
| FX-SRC-02 | [Member and desk interviews](02-member-staff-interviews.md) | Discovery, own bookings/loans, member problem reports, privacy |
| FX-SRC-03 | [Lending operations workshop](03-lending-operations-workshop.md) | Collection queue, handover, staff loan lookup, routine return |
| FX-SRC-04 | [Policy options and conflict memo](04-policy-options-conflicts.md) | Cancellation, clocks, competing claims, unresolved questions |
| FX-SRC-05 | [Text design revision](05-text-design-revision.md) | Concrete information needs and missing interaction states; no visual inspection |
| FX-SRC-06 | [Staged exception observations](06-staged-exception-observations.md) | Lifecycle, interrupted work, competing actions and review exercises |
| FX-SRC-07 | [Membership readiness brief](07-membership-readiness-brief.md) | Available evidence versus assumed dependency; request/checkout distinction |
| FX-SRC-08 | [Condition and return workshop](08-condition-return-workshop.md) | Damage, member reports, condition review/clearance and limits |
| FX-SRC-09 | [Launch prioritization discussion](09-launch-prioritization.md) | Connected candidate slices, release tradeoffs, next discovery |

## Synthetic premise register

Every row has status **author-defined fixture premise; review pending**. The linked passage supplies scope, feedback and counterexamples. References to inherited behavior do not give these rows authority to alter KD-ST-001.

| ID | Extension premise, compactly stated | Primary locator |
|---|---|---|
| FX-R01 | Discover physical items by name/identifier and category; no-result is not service failure | [FX-SRC-02 M01](02-member-staff-interviews.md#m01--finding-the-right-physical-item) |
| FX-R02 | Distinguish catalog presence, interval availability and unknown availability; no borrower disclosure | [FX-SRC-02 M02](02-member-staff-interviews.md#m02--availability-is-not-a-promise) |
| FX-R03 | Member list/detail covers only own confirmed, cancelled and collected bookings; no pending approval state | [FX-SRC-02 M03](02-member-staff-interviews.md#m03--my-bookings-and-the-missed-collection) |
| FX-R04 | Own confirmed, not-handed-over booking is a cancellation candidate; cutoff/race eligibility remains conditional | [FX-SRC-04 P01](04-policy-options-conflicts.md#p01--cancellation-options-not-a-chosen-cutoff) |
| FX-R05 | Successful eligible cancellation releases only that booking's reservation; refusal/uncertainty is not success | [FX-SRC-04 P02](04-policy-options-conflicts.md#p02--cancellation-outcomes-under-a-future-policy) |
| FX-R06 | Desk collection queue is for a chosen interval and operational contact needs, not an approval queue/directory | [FX-SRC-03 O01](03-lending-operations-workshop.md#o01--preparing-collections) |
| FX-R07 | Eligible staff handover links one actual loan to the confirmed booking/item/member; repetition must not create another | [FX-SRC-03 O02](03-lending-operations-workshop.md#o02--actual-handover-is-a-separate-event) |
| FX-R08 | Members do not self-handover or record returns; staff authority does not imply every other permission | [FX-SRC-03 O02](03-lending-operations-workshop.md#o02--actual-handover-is-a-separate-event) |
| FX-R09 | Own loan status distinguishes outstanding from recorded return and keeps other members' details private | [FX-SRC-02 M04](02-member-staff-interviews.md#m04--my-loan-and-a-problem-during-use) |
| FX-R10 | Staff locate actual outstanding loans by item/borrower for desk work; no membership directory or unrelated history | [FX-SRC-03 O03](03-lending-operations-workshop.md#o03--finding-the-actual-loan) |
| FX-R11 | Staff record return against the actual outstanding loan; repeated/stale attempts cannot record a second return | [FX-SRC-03 O04](03-lending-operations-workshop.md#o04--routine-return-without-a-bookability-shortcut) |
| FX-R12 | Routine return records actual receipt and closes the loan, but does not establish item bookability | [FX-SRC-03 O04](03-lending-operations-workshop.md#o04--routine-return-without-a-bookability-shortcut) |
| FX-R13 | Damaged return closes the actual loan and creates an operational condition case; no silent cancellation or debt | [FX-SRC-08 C01](08-condition-return-workshop.md#c01--return-receipt-and-condition-are-different-facts) |
| FX-R14 | A separately designated fictional condition reviewer can access condition cases; desk/manager titles alone do not grant clearance | [FX-SRC-08 C02](08-condition-return-workshop.md#c02--who-reviews-the-condition-case) |
| FX-R15 | Reviewer records assessment and clears the condition case or retains its restriction; neither outcome alone proves availability | [FX-SRC-08 C03](08-condition-return-workshop.md#c03--review-outcomes-and-what-they-do-not-do) |
| FX-R16 | Staff overdue view consumes an explicitly assumed classification; clock/threshold derivation remains open | [FX-SRC-04 P04](04-policy-options-conflicts.md#p04--overdue-is-not-an-agreed-clock) |
| FX-R17 | Overdue view is staff operational visibility, not member-wide disclosure, email, export or escalation | [FX-SRC-04 P04](04-policy-options-conflicts.md#p04--overdue-is-not-an-agreed-clock) |
| FX-R18 | Member may report a problem on own outstanding loan, without self-returning or changing its due obligation | [FX-SRC-02 M04](02-member-staff-interviews.md#m04--my-loan-and-a-problem-during-use) |
| FX-R19 | Staff see the member report on that loan/return intake; it is a report, not a verified damage assessment | [FX-SRC-08 C04](08-condition-return-workshop.md#c04--member-report-before-return) |
| FX-R20 | Extension staff permissions remain task/record-scoped; no general other-member booking editing or override | [FX-SRC-03 O05](03-lending-operations-workshop.md#o05--access-and-unsupported-exceptions) |
| FX-R21 | Failed/refused actions do not claim a state change; uncertain completion requires reconciliation, not a false success/failure | [FX-SRC-06 X05](06-staged-exception-observations.md#x05--interrupted-confirmation) |
| FX-R22 | Late return does not itself extend the loan, rewrite a later reservation or choose compensation | [FX-SRC-06 X03](06-staged-exception-observations.md#x03--late-loan-and-the-next-reservation) |

## Conflict and question register

All questions remain **open**. Owners below are fictional decision roles to ask in a future role-play, not people assigned real work. Detailed options and impacts are in [FX-SRC-04 P05](04-policy-options-conflicts.md#p05--question-register) and [FX-SRC-07 I04](07-membership-readiness-brief.md#i04--evidence-needed-before-readiness).

| Conflict | Competing evidence | Treatment |
|---|---|---|
| FX-C01 | SRC-02 T02 / SRC-05 D03–D04 staff approval versus UD automatic booking | Resolved by real user decisions; old UI remains a historical trap |
| FX-C02 | Maya wants cancellation until handover; desk colleague wants earlier cutoff | No chosen cutoff/race policy; FX-Q02 |
| FX-C03 | Routine return means shelf-ready versus condition assessment remains separate | FX-R12 prevents the shortcut in extension exercises; canonical condition qualification remains FX-Q03 |
| FX-C04 | Recheck membership at checkout versus avoid blocking collection during lookup failure | Neither selected; FX-Q04/05 |
| FX-C05 | Morning list versus due-instant overdue classification; email versus portal only | No clock or notification decision; FX-Q06/07 |
| FX-C06 | Any coordinator clears damage versus designated reviewer | FX-R14 supplies a fictional exercise actor only; actual authority remains FX-Q08 |

| Question | Decision needed | Owner to role-play |
|---|---|---|
| FX-Q01 | Time zone, DST ambiguity, permitted booking ranges/durations and queue interval interpretation | Maya + Leon; time-zone owner unconfirmed |
| FX-Q02 | Cancellation cutoff, cancellation/handover race, and handling no-show bookings | Maya + Leon |
| FX-Q03 | Condition-to-availability rules, future reservation impact and post-return inspection | Maya |
| FX-Q04 | Authoritative membership states, mapping, freshness and usable evidence | Aisha + Sam |
| FX-Q05 | Membership recheck/failure policy at handover; no assumed override | Aisha + Maya |
| FX-Q06 | Due obligation, overdue clock/threshold, DST and disputed timing | Maya + Leon |
| FX-Q07 | Whether notifications exist, channels/recipients/timing and consent/privacy | Leon + Aisha |
| FX-Q08 | Actual reviewer authority, evidence for clearance and review reversals | Maya + Leon |
| FX-Q09 | Wrong-item/partial-kit return, disputed damage and correction permissions | Maya |
| FX-Q10 | History retention, staff contact-field minimization and sensitive note handling | Aisha |
| FX-Q11 | Accessible discovery/desk interactions, supported devices and assistance needs | Leon; accessibility participants not represented |
| FX-Q12 | No-show, walk-in, substitute item and loan-extension scope | Leon + Maya |
| FX-Q13 | Member problem-report urgency, safety guidance and response ownership | Maya + Leon |
| FX-Q14 | Validating outcome measures and choosing a launch boundary | Leon + Maya |

## Source-to-scenario guide and next backlog derivation

These are **13 connected candidate behavior slices in total**, not authored stories, approved scope, remote IDs or implementation-ready commitments. Keep KD-ST-001 canonical; do not create a replacement. For each extension, carry FX premise status and relevant questions into any draft AC/test cases. Denial, stale-state and privacy outcomes belong with their capability, not as standalone stories. Split routine/damaged returns only if their distinct receipt/condition outcomes justify separate delivery; merging them still leaves a 12-slice set.

| Candidate outcome | Evidence to start with | Useful scenario / readiness limit |
|---|---|---|
| Existing KD-ST-001: book available equipment | Canonical story + UD; FX-SRC-07 I01–I04 | Preserve all v2 branches; do not promote fixture premises into canonical AC |
| Discover an appropriate item and inspect interval availability | FX-SRC-02 M01–M02; FX-SRC-05 D01 | Similar items, empty/unknown availability; FX-Q01/03/11 |
| Review own bookings and their lifecycle | FX-SRC-02 M03; FX-SRC-05 D02 | Own cancelled/collected record; another member's detail denied; FX-Q10 |
| Cancel an eligible own booking | FX-SRC-04 P01–P03; FX-SRC-06 X01 | Reservation release versus handover race; FX-Q02 blocks full eligibility |
| Prepare the collection workload | FX-SRC-03 O01; FX-SRC-05 D03 | Chosen interval, stale entry, contact minimization; FX-Q01/10 |
| Record actual handover | FX-SRC-03 O02; FX-SRC-06 X02; FX-SRC-07 I03 | Correct physical item, repeat attempt, unknown checkout eligibility; FX-Q03/05 |
| See own loan status | FX-SRC-02 M04; FX-SRC-05 D04 | Booking is not loan; receipt is not condition clearance; FX-Q06/10 |
| Locate an outstanding loan for desk work | FX-SRC-03 O03; FX-SRC-05 D05 | Find actual borrower/item without a booking list or directory; FX-Q10 |
| Record routine return | FX-SRC-03 O04; FX-SRC-06 X04 | Close correct loan once, preserve condition uncertainty; FX-Q03/09 |
| Record damaged return and initiate condition handling | FX-SRC-08 C01; FX-SRC-06 X04 | Receipt despite damage, restricted case, no fines; FX-Q03/09 |
| Assess and clear/retain an item condition case | FX-SRC-08 C02–C03; FX-SRC-05 D06 | Designated reviewer versus ordinary desk actor; FX-Q03/08 |
| Review overdue workload | FX-SRC-04 P04; FX-SRC-06 X03; FX-SRC-05 D07 | Assumed overdue classification, returned row removal; FX-Q06/07 |
| Report a problem on an own outstanding loan | FX-SRC-02 M04; FX-SRC-08 C04 | Report visible to desk, not self-return or proven damage; FX-Q13 |

Recommended exercise order: source-grounded discovery summary and conflict analysis; lifecycle/ownership map; provisional connected backlog; AC for supported branches with explicit gaps; test design and change-impact review. Use [FX-SRC-09](09-launch-prioritization.md) for a release tradeoff exercise, not as approval. Do not execute tests, publish issues or claim acceptance from these sources.

## Deliberate traps and fixture isolation

- Invented apparent consensus is not user approval; a design action is not permission. Distinguish FX premises from wishes and open options.
- An available-looking catalog card is not confirmed interval availability. A report of damage is not a returned item. A returned loan is not a cleared item. A cleared condition case is not a canonical bookability policy.
- No pending-approval backlog, training gate, implicit email, automatic overdue threshold, cutoff, staff override or temporary reservation hold should reappear.
- Compare both directions of the 30-minute booking separation and preserve exactly 30 minutes. Do not treat that gap as loan duration, cancellation cutoff or inspection sign-off.
- Actor/record scope must survive direct access attempts, stale views and changed item/loan references; do not invent endpoint contracts or authentication.
- FX-SRC/FX-R/FX-Q/FX-C are local evidence labels only. This folder does not allocate record identifiers, remote IDs or the separate isolated `FX-BKG-*` KD001 QA namespace. Do not merge scenario events here into that dataset or assume its accounts/data are provisioned.
