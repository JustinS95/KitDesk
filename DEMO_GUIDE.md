# KitDesk in five minutes

A member wants to borrow a drill. Confirming a reservation is not handing over the drill; receiving it back is not declaring it safe to lend again. This portfolio follows that small journey from conflicting discovery notes to explicit requirements and a public board.

## The walkthrough

1. **Minute 1 — find the problem.** Open the [project context](project-context/PROJECT.md) and [discovery synthesis](artifacts/discovery/Expansion_01_Discovery_Synthesis.md). The original notes proposed staff approval; approved scenario decisions replaced it with immediate confirmation. The retained fictional sources show the conflict, not real customer research.
2. **Minute 2 — show a decision becoming a contract.** Compare [DD-01–08](artifacts/discovery/Demo_Readiness_Decisions_20261018.md) with [KD-ST-001 v3](artifacts/stories/KD-ST-001-book-available-equipment.md). Its twelve AC preserve immediate reservation and the exact 30-minute gap, then add London/DST validation, current membership, fail-closed item qualification and scoped access. Use [traceability](artifacts/requirements/Expansion_01_Traceability.md) to follow the reasoning rather than treating a longer story as proof of completeness.
3. **Minute 3 — follow the physical handover.** Open [KD-ST-006](artifacts/stories/KD-ST-006-record-handover.md), then [own loans KD-ST-007](artifacts/stories/KD-ST-007-view-own-loans.md). Card and asset must match during the collection interval; the first completed transition wins, with one loan and an explicit booking-end due fact. Booking ≠ possession; receipt ≠ clearance; due ≠ overdue classification.
4. **Minute 4 — inspect a test boundary.** In the [booking fixture guide](testing/data/booking-fixtures/README.md), Bell's reservation occupies relative minutes 120–180. Ari starting at 209 leaves 29 minutes; 210 leaves exactly 30. A request ending at 90 also leaves 30 before Bell's start. Compare the [coverage matrix](testing/data/booking-fixtures/coverage.md) and [manual test design](testing/test-cases/KD-ST-001_Manual_Test_Design.md). These are boundary examples, not approved calendar times or a shared provisioned world.
5. **Minute 5 — show scope judgment on the board.** Open the [canonical backlog](artifacts/stories/EXPANDED_BACKLOG.md) and [public Project](https://github.com/users/JustinS95/projects/3). Follow the booking contract to [Issue #1](https://github.com/JustinS95/KitDesk/issues/1) and handover to [Issue #7](https://github.com/JustinS95/KitDesk/issues/7). Explain why seven stories are Ready while cancellation, receipt, condition assessment, overdue classification and problem reporting remain Backlog—not silently completed dependencies.

## Public snapshot versus repository publication

At **2026-10-18T14:28:46Z**, seven Issue bodies had been updated and their Project Status verified Ready; five deferred Issues remained unchanged in Backlog. The [README snapshot](README.md#board-snapshot) lists all twelve exact story/Issue mappings. This is retained verification, not a fresh live check.

The [public repository](https://github.com/JustinS95/KitDesk) and public Issues are distinct surfaces: the latest local canonical documents and `team.yaml` changes are still pending repository publication. Earlier all-twelve-Backlog and stale-Ready-body statements in linked artifacts describe an older checkpoint, not this later verified board result.

## Test-design evidence

The existing fixtures and manual test design cover **KD-ST-001 v2**, not v3's twelve AC or the new DD decisions. They have **never been executed against an application** and have not been updated for the DD supplement. They remain useful historical examples, not current full-contract coverage.

The optional [fixture static-validation report](evaluation/expanded-demo-01/fixture-validation.md) records JSON parsing and 559 file-consistency assertions with zero issues for its identified inputs. Those are static checks, not 559 application tests. Its later check supersedes the fixture guide's earlier “parser not run” note only for that bounded validation.

## Read the artifacts in context

| Layer | What it establishes |
|---|---|
| [Original source pack](sources/expansion-01/README.md) | Invented discovery evidence and original open premises; preserve contradictions to show how decisions changed the requirements. |
| [Approved checkpoint](artifacts/discovery/Demo_Readiness_Decisions_20261018.md) + [canonical stories](artifacts/stories/EXPANDED_BACKLOG.md) | Adopted fictional rules and scoped AC. Historical questions and publication notes remain dated context, not new blockers or current remote status. |
| Engineering and validation still to come | Real adapters/accounts or explicit fakes, qualification facts, authentication/access enforcement, atomic transitions and DD-aligned tests. Requirements readiness does not supply these implementations. |

The [original lifecycle map](artifacts/process-maps/Expansion_01_Lending_Lifecycle.md) is secondary historical reasoning, not the current oracle for DD-resolved qualification, race or due rules. For current open scope, use the [question disposition](artifacts/discovery/Expansion_01_Discovery_Synthesis.md#current-question-disposition--2026-10-18) and five deferred stories in the canonical backlog.
