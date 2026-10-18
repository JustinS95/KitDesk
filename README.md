# KitDesk — a BA/QA portfolio

Northstar Community Workshop lends tools and equipment to members. Its spreadsheet-and-email process makes reservations, physical handovers and returns hard to distinguish. KitDesk explores a member booking portal and a staff lending desk through discovery, explicit decisions, connected stories and test design.

**This is a fictional, document-first portfolio, not an implemented application.** People, interviews and data are invented; approved scenario decisions are separate from original evidence. Ready means requirements-ready, not delivered software or executed test evidence.

## Start with the story

Take the [five-minute walkthrough](DEMO_GUIDE.md), or follow the chain:

1. **Discover:** [project context](project-context/PROJECT.md), [original source index](sources/INDEX.md) and [discovery synthesis](artifacts/discovery/Expansion_01_Discovery_Synthesis.md).
2. **Decide:** [approved DD-01–08 checkpoint](artifacts/discovery/Demo_Readiness_Decisions_20261018.md) — time, membership, item qualification, handover, privacy and due facts.
3. **Specify:** [canonical story index](artifacts/stories/EXPANDED_BACKLOG.md), [booking story](artifacts/stories/KD-ST-001-book-available-equipment.md) and [source → decision → AC traceability](artifacts/requirements/Expansion_01_Traceability.md).
4. **Track:** the public [KitDesk repository](https://github.com/JustinS95/KitDesk) and [GitHub Project board](https://github.com/users/JustinS95/projects/3).

## Board snapshot

Verified **2026-10-18T14:28:46Z**: seven Ready, five Backlog. These are historical observations, not a guarantee of live status. The seven Ready Issue bodies were updated to the approved requirements; the five deferred Issues were unchanged.

| Status | Stories / public Issues |
|---|---|
| Ready | [KD-ST-001](https://github.com/JustinS95/KitDesk/issues/1), [KD-ST-002](https://github.com/JustinS95/KitDesk/issues/3), [KD-ST-003](https://github.com/JustinS95/KitDesk/issues/4), [KD-ST-005](https://github.com/JustinS95/KitDesk/issues/6), [KD-ST-006](https://github.com/JustinS95/KitDesk/issues/7), [KD-ST-007](https://github.com/JustinS95/KitDesk/issues/8), [KD-ST-008](https://github.com/JustinS95/KitDesk/issues/9) |
| Backlog | [KD-ST-004](https://github.com/JustinS95/KitDesk/issues/5), [KD-ST-009](https://github.com/JustinS95/KitDesk/issues/10), [KD-ST-010](https://github.com/JustinS95/KitDesk/issues/11), [KD-ST-011](https://github.com/JustinS95/KitDesk/issues/12), [KD-ST-012](https://github.com/JustinS95/KitDesk/issues/13) |

**Publication boundary:** the latest canonical repository documents and `team.yaml` changes are pending publication. Updated public Issue bodies do not mean the matching repository files have been published or are automatically synchronized.

## How to read the evidence

- **Original sources** preserve conflicting proposals; they show what needed discovery, not settled policy.
- **Approved decisions and canonical stories** define the bounded fictional requirements. The checkpoint records their authority; its earlier board/publication notes are historical, superseded by the snapshot above.
- **Future engineering** must supply authentication, membership and condition data, access enforcement and once-only transitions. Cancellation, receipt/assessment, overdue classification and problem-report service still have unresolved Backlog scope.

For test-design examples and their version limits, see the [walkthrough](DEMO_GUIDE.md#test-design-evidence).

## Configuration example

[team.yaml](team.yaml) is a minimal example connecting the KitDesk project name, GitHub repository, user Project 3 and canonical `artifacts/stories` registry. It is configuration context, not an operational roster or a promise of live synchronization.
