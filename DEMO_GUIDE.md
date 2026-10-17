# KitDesk: a document-first BA/QA demo

Publication derivative: only the local-checkpoint references below have been adjusted for public navigation. See [publication notes](PUBLICATION_NOTES.md); original decision, source, story and historical evaluation files are preserved.

A member wants to borrow a drill. Reserving it should not require a desk approval, but confirming a reservation is not the same as handing over the drill. Later, receiving it back is not the same as declaring it safe or available again. KitDesk uses that small journey to demonstrate discovery, connected requirements and honest test design.

**This is a fictional local document playground, not an implemented product.** Interviews, workshop dialogue, staged observations and scenario data are invented. Actual user role-play decisions are recorded separately. There is no provisioned application, test environment or membership integration, and no business approval or outcome metric should be invented to make the demo sound finished.

## Five-minute walkthrough

1. **Minute 1 — show the problem and its authority.** Open [project context](project-context/PROJECT.md), then [the expansion source guide](sources/expansion-01/README.md). Explain: “The original notes proposed staff approval. Recorded user decisions replaced that with immediate confirmation. The new interviews are synthetic discovery material, not customer research.”
2. **Minute 2 — show one concrete contract.** Open [KD-ST-001 v2](artifacts/stories/KD-ST-001-book-available-equipment.md). Point to AC-01/02: verified active membership, an available physical item, immediate confirmation/reservation and no pending stage. Same-item bookings need at least 30 minutes between them in either request order; exactly 30 is allowed on gap grounds. Training checks are excluded. AC-03/04/08 distinguish inactive, unverifiable and unavailable outcomes; AC-05/06 protect ownership and borrower details.
3. **Minute 3 — tell the wider journey.** Open the [lending lifecycle](artifacts/process-maps/Expansion_01_Lending_Lifecycle.md). Follow confirmed booking → actual handover/loan → receipt → separate condition assessment. Point out an unresolved exit, such as cancellation racing with handover or condition-to-availability policy. The two Mermaid diagrams were manually inspected, not rendered or stakeholder validated; their text and narrative are usable without a renderer.
4. **Minute 4 — demonstrate boundary reasoning, not a test run.** Open the [booking fixture guide](testing/data/booking-fixtures/README.md). Bell's reservation is minute 120–180; Ari starting at 209 leaves 29 minutes, while 210 leaves exactly 30. An earlier request ending at 90 also leaves 30. These are imaginary relative minutes, not approved calendar times. Show the [coverage matrix](testing/data/booking-fixtures/coverage.md) and [manual test design](testing/test-cases/KD-ST-001_Manual_Test_Design.md) to connect expectations to ACs and missing execution prerequisites.
5. **Minute 5 — show judgment and next work.** Open the [backlog index](artifacts/stories/EXPANDED_BACKLOG.md), then one linked candidate and its open questions. Use that final index for current story inventory and readiness; do not assume a count or a Ready state. Close with: “The artifacts make the questions and conditional behaviors reviewable. They do not prove the product works.” Choose one [focused exercise](EXERCISES.md#expansion-01-focused-routes) if there is time.

## What you can show

- **Discovery with provenance:** the [expansion synthesis](artifacts/discovery/Expansion_01_Discovery_Synthesis.md) and [source pack](sources/expansion-01/README.md) distinguish confirmed decisions, 22 author-defined provisional premises, 14 open questions and 6 conflicts. Those are source-register counts, not approvals or delivery results.
- **Connected behavior:** the [backlog index](artifacts/stories/EXPANDED_BACKLOG.md), [traceability](artifacts/requirements/Expansion_01_Traceability.md) and [process map](artifacts/process-maps/Expansion_01_Lending_Lifecycle.md) let a reviewer follow actors, record ownership, lifecycle and unanswered policy across artifacts. The index links canonical stories; this guide is not another story store.
- **Test-design reasoning:** the [baseline fixture pack](testing/data/booking-fixtures/README.md) has 8 invented personas, 6 physical items, 5 reusable baseline bookings and 28 independent scenarios: 24 contract-backed conditional designs and 4 exploratory/blocked prompts. Each scenario uses only its named baseline, not a shared seeded world. The pack covers KD-ST-001 v2, not the whole expansion lifecycle.
- **A bounded static check:** the retained [fixture-validation report](evaluation/expanded-demo-01/fixture-validation.md) records successful JSON parsing and 559 static consistency assertions with zero issues. It identifies the validated hashes and limits; it is not 559 application tests. The fixture guide's earlier “parser not run” author checklist is historical; the separate report records the later check.
- **One historical publication example:** the public [KitDesk repository](https://github.com/JustinS95/KitDesk), original [Issue #1](https://github.com/JustinS95/KitDesk/issues/1) and [Project 3](https://github.com/users/JustinS95/projects/3) were verified on 2026-10-17 in a checkpoint retained only in the original local workspace. The Issue was in Backlog at that verification. Issue creation, board reads and membership verification were exercised; explicit Project-add and Status mutations were not. The checkpoint is excluded from this public copy; this historical summary is not a fresh remote check or independently reproducible board-state proof.

## What not to claim

- No working application, executed booking/loan workflow, provisioned accounts, live membership dependency, security enforcement or concurrency result is demonstrated.
- No real interviews, workshops, stakeholder validation, accepted launch scope, quantified benefit or approved business policy comes from invented FX dialogue.
- Authored cases, expected results, static assertions and unchecked canonical ACs are not test passes or acceptance evidence. The manual design is a future execution aid, not an execution log.
- No statement here establishes that expanded local artifacts are committed, pushed, published as Issues or synchronized with GitHub. The one Issue's verified membership does not prove the explicit add mutation was exercised or explain who/what added it.
- Historical public visibility and board status may have changed. A new remote check or mutation requires its own scope and authorization; opening this guide does not authorize either.
- A polished candidate can be **well-formed under explicitly adopted fixture premises yet not implementation-ready**. Unresolved policy, dependency evidence and real environment/data prerequisites still matter; finishing a predecessor or writing more ACs does not remove them.

## Source authority: how to read apparent contradictions

Start with the question “Who actually decided this?” rather than “Which document is newest?”

| Material | Authority and correct use |
|---|---|
| [Initial UD-01–UD-04](artifacts/discovery/Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16) and [AC-trial UD-05–UD-08](artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md) | Actual user role-play decisions for this fictional scenario; take precedence over contradictory original approval/pending notes within their stated scope. They do not establish checkout recheck policy or permission to execute anything. |
| [Canonical KD-ST-001 v2](artifacts/stories/KD-ST-001-book-available-equipment.md) | Approved/applied booking refinement with remaining readiness limits. Preserve its existing version, AC identities, decisions and content; the expansion does not replace it. |
| [PROJECT.md v1 narrative](project-context/PROJECT.md) and [SRC-01–SRC-09](sources/INDEX.md) | Retained historical baseline, including contradictory proposals and older decisions. Useful for showing change and conflict; not authority to reintroduce staff approval over UD decisions. |
| [FX-SRC pack and FX-R register](sources/expansion-01/README.md) | Author-created synthetic evidence and review-pending extension premises. Explicitly adopting them supports conditional exercises, not a claim of user/stakeholder approval. Wishes, options and apparent invented consensus are not extra rules. |
| FX-Q/FX-C, synthesis, backlog, traceability and maps | Questions/conflicts and derived analysis remain traceable to their sources. More detailed prose, a diagram or a later scenario date does not silently resolve canonical open questions. Consult the final backlog index and individual stories for status. |
| [Booking fixtures](testing/data/booking-fixtures/README.md) and [static validation](evaluation/expanded-demo-01/fixture-validation.md) | Synthetic KD001-only examples and a bounded file-consistency check. Relative times and semantic membership outcomes are not product defaults, real accounts, adapters or integration evidence. |
| Local-only integration checkpoint; public [Issue #1](https://github.com/JustinS95/KitDesk/issues/1) | Original operational evidence is retained locally, not distributed here. A proposed operation manifest is not proof that every planned mutation ran. No live sync or expanded Issue publication follows. |

Three distinctions keep the demo honest:

1. **Booking ≠ loan.** A confirmed reservation is not physical possession. Handover creates the actual loan under explicitly established eligibility in the extension example.
2. **Receipt ≠ clearance ≠ availability.** Closing a returned loan does not settle damage assessment or bookability. The 30-minute booking gap is not a damaged-item clearance rule.
3. **Conditional design ≠ readiness ≠ execution.** Calendar/time-zone/DST choices, authoritative membership evidence and complete condition rules remain open in canonical booking. Extension cancellation, checkout, overdue and reviewer questions also stay visible rather than becoming invented defaults.

## Pick a practical next route

Use the concrete prompts in [EXERCISES.md](EXERCISES.md#expansion-01-focused-routes):

- **Discovery:** prioritize the next three consequential questions, not settled approval/training/gap questions.
- **Story/AC refinement:** propose clearer actor, outcome and denied/stale paths for one indexed extension candidate without silently editing canon.
- **Adversarial review:** trace cancellation, handover and receipt together; challenge ownership, duplicate actions and unsupported race winners.
- **Process mapping:** explain damaged receipt and separate assessment with explicit unresolved exits.
- **Test design:** bind selected 29/30/31-minute and ownership examples to canonical ACs, keeping setup and real interfaces blocked.

Choose one useful artifact, save it to the named local destination, and report what was actually checked. No exhaustive skill ritual, automatic publication, installation, data seeding or application/test execution is part of these routes. Preserve original sources, canonical KD-ST-001 and old trial observations rather than rewriting them to make the portfolio look cleaner.
