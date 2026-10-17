# Expansion 01 backlog: bounded author self-review

The central check was whether the journey could say “the item came back” without also claiming “it is safe and available again.” It can: the return story records possession ending, while the condition story records assessment of a separate concern. Full booking/collection qualification remains unanswered.

Version 1. **Author reasoning only, not independent validation, security verification or test execution.** Review boundary: unchanged KD-ST-001 v2 and its UD-01–08 decisions; the 11 new KD-ST-002–012 drafts; backlog, synthesis and traceability; all nine FX-SRC v1 files and pack guide; project context and SRC-06 § A01–A03. No remote board, application, identity provider, membership system or original-source corpus beyond the specifically read artifacts was inspected.

## Composition and coverage observations

- Source candidates total 13 including the existing booking. Combining routine/damaged return yields 12 stories total, 11 new. This is a source-supported merge (FX-SRC-09 § L02), not a lost damaged-return branch or a count target. Condition assessment remains distinct work after receipt.
- Search/list/detail serve one equipment-selection task. Own bookings and own loans stay separate because a reservation is not possession. Staff lookup stays separate from overdue because a not-yet-overdue loan must be findable without a booking date (FX-SRC-03 § O03).
- Privacy, denial, stale records, repeated mutations and uncertain outcomes are integrated with the capability they qualify, not authored as standalone stories. No frontend/backend, endpoint, button or universal permission story was added.
- Existing KD-ST-001 AC-01–08 retain automatic confirmation/reservation, both directions of the minimum gap with exactly 30 allowed, active membership without training, known booking failure branches and own-record privacy. FX-R21 was not added to canonical booking as a new transport contract.
- Exact UI copy, field limits, search matching, contact fields, due rules and production role names remain unspecified where evidence is absent. Text design controls confer no permission.
- Read-back caught a lifecycle wording risk in KD004 AC-03: saying every collected booking's loan “remains outstanding” could misdescribe an already returned loan. The criterion now preserves any actual-loan state and says only an outstanding loan stays outstanding, consistent with FX-SRC-04 § P01/P02. KD009 AC-04 also explicitly prevents closing the selected loan on an item mismatch, not merely closing a different loan. These were author wording corrections, not new policy decisions or executed security checks.

## Actor and operation review

The boundaries below are the draft's stated behavior under review-pending premises, not verified permissions. SRC-06 § A01 supports enforcement beyond a hidden button; it does not supply actors or fields.

| Operation / story AC | Fixture actor and record boundary | Protected content / denied outcome | Remaining limit |
|---|---|---|---|
| Browse/check interval, KD002 AC-01–04 | Member; physical catalog item and declared interval | No borrower identities/contact; no hold | FX-Q01/03/11 and matching details. |
| Retrieve bookings, KD003 AC-01–04 | Member's own retained confirmed/cancelled/collected records | Other-reference read denied without detail; no other-member cancellation offer | FX-Q10 retention; FX-Q02 no-show transition. |
| Cancel, KD004 AC-01–04 | Own confirmed/uncollected booking, separately eligible under future policy | Other target unchanged/no detail; collected loan not cancelled; known refusal versus uncertainty | FX-Q02 cutoff/race; no staff cancellation right. |
| Inspect collections, KD005 AC-01–04 | Coordinator, chosen-interval confirmed/uncollected lending task | Member denied queue/contact; no directory, approval or editing | FX-Q01/10 fields/interval; stale row is not eligibility. |
| Record handover, KD006 AC-01–04 | Coordinator; established-eligible actual handover of selected booking/item/member | Member attempt creates no loan; wrong/stale/repeated target no new loan; no override/substitution | FX-Q02/03/04/05/12 and borrower identity/timing. |
| Read own loan, KD007 AC-01–03 | Member, own actual loan | Other loan and internal assessments not disclosed; no member handover/return | FX-Q06/09/10; no invented empty/error-state design. |
| Lookup and report context, KD008 AC-01–04 | Coordinator, outstanding lending records only | Members denied cross-borrower search; no directory/history/general mutation authority | Exact matching and FX-Q10 fields/content; known due only. |
| Receipt, KD009 AC-01–06 | Coordinator, correct outstanding actual loan/item | Member return denied/unchanged; mismatch cannot close another loan; repeats no duplicate return/case | FX-Q03/09/10; no correction or bookability shortcut. |
| Case read/assessment, KD010 AC-01–05 | Separately designated fictional reviewer, specific open case | Members no internal assessments/clearance; ordinary coordinator clearance denied/unchanged; no default contacts | FX-Q08 actual authority/evidence/reversal and FX-Q10 fields; FX-Q03 availability. |
| Overdue read, KD011 AC-01–05 | Coordinator; explicitly assumed outstanding-overdue set | Members no borrower disclosure; no delivery/export/penalty | FX-Q06 calculation missing; FX-Q07 unadopted delivery. |
| Report submit/read, KD012 AC-01–04 | Own outstanding-loan member; related desk lending context | Other-reference read/write denied; returned target creates no report; internal assessment not exposed | FX-Q13 response, FX-Q10 sensitive content; no duplicate-report policy invented. |

No assignment or notification routing is inferred from access. No named person is assigned work. Desk authority does not imply manager/reviewer/membership authority; those concepts remain distinct.

## Record and lifecycle review

| Business fact / source | Consumer comparison | Finding from the authored text |
|---|---|---|
| Confirmed booking/reservation, KD001 AC-01/02; FX-R03/04/05/07 | KD003/004/005/006 | Confirmation does not create a loan. Eligible cancellation releases only its own reservation. Missed collection is not assumed cancelled. Race outcome remains open. |
| One actual handover, FX-SRC-03 § O02 / FX-R07 | KD006 → KD003/007/008/009/011/012 | Correct item/member/booking links persist; repeated/concurrent recording creates no second loan. Physical eligibility is conditional, not waived. |
| Correct-item receipt, FX-SRC-03 § O04 / FX-R11/12 | KD009 → KD007/008/011 | Returned loan no longer outstanding, including when a condition case remains open. Requested interval is not rewritten. |
| Damaged-receipt case, FX-SRC-08 § C01 / FX-R13 | KD009 → KD010 | Receipt and restricted case are separate facts; repeats do not duplicate the same receipt/case. Uncertain completion is not falsely presented as both complete. |
| Member report, FX-SRC-02 § M04 / FX-R18; FX-SRC-08 § C04 / FX-R19 | KD012 → KD008/009 | Member report stays reported, not assessed cause/fault, return, case trigger or emergency response. Related staff context does not broaden access. |
| Specific assessment, FX-SRC-08 § C02/C03 / FX-R14/15 | KD010 versus KD001/002/006/009 | Clearance does not reopen the loan, erase concern, clear other concerns or settle future availability. No circular “return only after clearance” requirement is introduced. |
| Due/overdue, FX-SRC-04 § P04 / FX-R16/17; FX-R22 | KD007/008/011 | Known obligations may display, but no booking-end-to-due derivation or overdue clock is invented. Lateness alone does not change later bookings or extend a loan. |
| Membership evidence, UD-03/06/07/08; FX-SRC-07 § I01–I04 | KD001 versus KD006 | Booking outcomes remain settled while real evidence is missing; checkout recheck/failure policy remains separate. |

These are business record relationships, not invented technical canonical owners, snapshots, synchronization mechanisms or database fields.

## Links, dependencies and hierarchy

Record links are own-scope or operational-context links. Changed references and bypassed controls are included in access reasoning. There are no invitation, anonymous recipient, email tracking or token-lifetime workflows to review; authentication/link-bound identity mechanics remain unavailable rather than defaulted.

I inspected the producer/consumer rows in the [backlog](../stories/EXPANDED_BACKLOG.md#local-dependencies-are-not-readiness-decisions) in the direction **A → B = A supplies the consumed record/outcome to B**. No self-edge or directed cycle was found by reasoning over those stated rows. Optional report/return/lifecycle consumers are labelled as branch prerequisites, not reasons to block all earlier read work. All local story endpoints are present in the set. There is no hierarchy, UUID registry, tag vocabulary, assignee, points scale or remote mapping to validate or invent.

## Unresolved findings retained in the drafts

Severity is a review suggestion about impact, not approved priority. These are inherited specification/evidence gaps, not observed software defects.

| Finding | Provenance and competing claim / missing evidence | Impact and proposed follow-up | Draft treatment |
|---|---|---|---|
| F01 — High: condition does not yet determine availability | FX-C03; FX-SRC-03 § O04 shelf-ready proposal versus FX-R12; FX-SRC-08 § C01/C03 restriction/clearance caveats | Ask fictional Maya for FX-Q03 worked booking/collection/return/clearance examples. Core eligibility remains incomplete. | KD001 untouched; KD002/006/009/010 explicitly limit qualification. Operational restriction is not smuggled into canonical booking AC. |
| F02 — High: collection eligibility and cancellation race | FX-SRC-04 § P01/P03 and FX-SRC-06 § X01 have no winner; FX-SRC-07 § I03 has rival membership recheck positions | Ask fictional Maya/Leon/Aisha, Sam for evidence as appropriate, FX-Q02/04/05 plus identity/timing examples. | KD004/006 stay provisional; clean conditional paths and duplicate handover do not decide the race. |
| F03 — High: reviewer authority is synthetic | FX-SRC-08 § C02/C03; FX-R14 defines an exercise designation, FX-Q08 real evidence/reversal absent | Ask fictional Maya + Leon who may assess/clear and on what evidence; Aisha for minimized context. | KD010 provisional; ordinary staff denied clearance and member internal-case reads excluded. |
| F04 — Medium: overdue oracle absent | FX-C05; FX-SRC-04 § P04 and FX-SRC-06 § X03 explicitly assume classification | Ask fictional Maya + Leon for FX-Q06 chronology before any calculated inclusion/boundary assertions. | KD011 consumes declared assumed set only; no clock, grace window or reminders invented. |
| F05 — Medium: field/privacy and service boundaries unfinished | FX-SRC-04 § P05 FX-Q10/11/13; FX-SRC-02 § M01/M04 and FX-SRC-03 § O03 omit detailed matching/read-state/report rules | Ask fictional Aisha for purpose/field review; Maya/Leon for report service; include missing accessibility perspectives. | No exact fields/validation/safety copy introduced. Capture/known-fact drafts remain useful, but not complete operational/usable-access contracts. |
| F06 — Low: stale story navigation text | Existing `artifacts/stories/README.md` says no stories; actual store has canonical KD001 | Parent may decide a separately authorized housekeeping edit; it is not permission for this task to change it. | New backlog is self-contained; existing README remains untouched and mismatch is disclosed in synthesis. |

All source conflicts FX-C01–06 and open FX-Q01–14 are retained in synthesis/traceability, including unadopted notifications, unsupported physical exceptions and launch-measure questions. No fictional consultation is claimed complete.

## Controlled compromises and maturity

- **Three draft-complete information stories (KD003/007/008)** express only the stated fixture retrieval scope. Retention, exact matching, additional fields, empty/error-state gaps where unsourced and fuller condition explanations are explicitly not resolved. “Draft complete” is not a claim that all desirable interaction details or implementation inputs exist. If a broader service boundary is requested, these labels need reconsideration.
- **Eight provisional stories (KD002/004/005/006/009/010/011/012)** keep specific missing rules beside supported branches. Open questions do not prohibit all meaningful partial drafting or record-based examples.
- **No count padding:** 11 new instead of about 12 because routine/damaged receipt is one coherent capability. Separate assessment still has independent value.
- **Repeated boundaries are intentional cross-capability enforcement, not new duplicate features:** report facts are consumed by lookup/return; receipt is consumed by own-loan/overdue views; own-record privacy must survive every relevant entry point.
- **No global defaulting:** no pending stage, training check, cutoff, due clock, email, staff override, arbitrary input limit, exact UI text or “clear = available” policy was adopted to make the journey look finished.

## Checks actually performed and limits

Performed: targeted source reads, comparison with canonical booking and UD decisions, author-level AC/source mapping, and connected actor/record/lifecycle/dependency reasoning recorded above. The new files were read back for scoped content review. Findings are about text, not running behavior.

Not performed: executable static validation, automated link checking, application/UI/API tests, security or accessibility verification, membership dependency checks, live-board comparison, external research, publication or remote changes. No checkboxes were marked complete. Any separate static validation or independent review must report its own results; this self-review cannot stand in for it.
