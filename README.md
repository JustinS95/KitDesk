# KitDesk — document-first BA/QA demo

Publication-adjusted copy of the local fictional playground. Start with the [five-minute demo](DEMO_GUIDE.md); see [publication notes](PUBLICATION_NOTES.md) for excluded local recovery records, navigation adjustments and historical evidence limits. The reusable skill library is not included.

An isolated, fictional software-development project for hands-on skill trials. **This is a document playground, not a working application or connected Azure DevOps project.** Scenario people, organizations, interviews and data are invented; user role-play decisions and recorded integration observations are identified separately.

## The project: KitDesk

Northstar Community Workshop lends shared tools and equipment to members. KitDesk will replace its spreadsheet-and-email booking process with a member portal and a staff lending desk. It offers enough connected behavior to exercise discovery, stories, permissions, lifecycle, requirements, testing and release communication without an enterprise-sized domain.

## Start here

1. Read [project context](project-context/PROJECT.md) and the [source index](sources/INDEX.md).
2. Pick a prompt from [EXERCISES.md](EXERCISES.md). Start with discovery or meeting summarization.
3. Save new outputs in the designated artifact folder. Do not rewrite the source pack to resolve contradictions.
4. Record what the skill actually did in [evaluation/README.md](evaluation/README.md). Expected behavior is not an observed pass.

For a five-minute portfolio walkthrough, start with [DEMO_GUIDE.md](DEMO_GUIDE.md). The [Expansion 01 source pack](sources/expansion-01/README.md), [backlog index](artifacts/stories/EXPANDED_BACKLOG.md), [lending lifecycle](artifacts/process-maps/Expansion_01_Lending_Lifecycle.md) and [booking fixture guide](testing/data/booking-fixtures/README.md) support richer local exercises. Follow the index for individual story status; authored candidates are not automatically Ready.

The fictional scenario rules are test inputs, not actual organizational policies or authorization. New business decisions during an exercise need an explicit user response or a clearly labeled hypothetical decision. Do not silently convert an assumption into an approved rule.

## Layout

```text
kitdesk is represented by this playground root
├── project-context/       Project scope, glossary and fictional decision owners
├── sources/               Original fictional inputs; preserve as baselines
│   ├── discovery/         Brief, transcript, stakeholder email, current process
│   ├── design/            Text-only design export
│   ├── engineering/       Convention decision and integration proposal
│   ├── tracking/          Synthetic board snapshot (not a live ADO export)
│   ├── release/           Candidate change notes, not release approval
│   └── expansion-01/      Additional invented discovery; premises review pending
├── artifacts/             Outputs we will author during exercises
│   ├── discovery/
│   ├── meeting-summaries/
│   ├── requirements/
│   ├── stories/           Populated canonical local story store and backlog index
│   ├── process-maps/
│   ├── design-briefs/
│   ├── reviews/
│   ├── communications/
│   └── release-notes/
├── testing/
│   ├── test-cases/
│   ├── test-plans/
│   ├── automation/        Future authored tests; no framework installed
│   ├── data/              Synthetic data, not provisioned application records
│   └── evidence/          Future real run evidence; no seeded results
├── integrations/          Integration boundaries; operational recovery records stay local
└── evaluation/            Exercise observations and skill improvement candidates
```

## Boundaries and coverage

- This repository contains the publication-adjusted document snapshot, separate from the reusable skill library. Original documents retain historical local-only statements; their authoring-time scope is explained in [publication notes](PUBLICATION_NOTES.md). A file in this PR is not a published Issue, merged change, approved requirement or delivered feature.
- Original KD-ST-001 was published as [Issue #1](https://github.com/JustinS95/KitDesk/issues/1). Local-only recovery evidence recorded [Project 3](https://github.com/users/JustinS95/projects/3) membership in Backlog on 2026-10-17. That operational checkpoint is intentionally not distributed. Issue creation, board reads and membership verification were exercised; explicit Project-add and Status mutations were not. No live synchronization or current board-state claim is provided.
- Setting up the playground does not execute the skills' business workflows, create requirements, run application tests, or prove the skills work.
- Document-based exercises can start now. Design analysis can use the supplied **text-only export**, but cannot claim visual inspection or Figma access.
- Word conversion needs a real DOCX supplied later; there is no disguised Markdown-to-DOCX fixture.
- Playwright needs a real application, verified implementation details and an available framework before runnable tests can be authored honestly.
- ADO reads/writes need a separately chosen sandbox and permissions. Synthetic board data supports offline reasoning only; do not pass its IDs to remote tools.
- No sending emails, publishing, package installation, live integration, test execution, source deletion or skill-library edits are authorized by these exercise prompts.

## Suggested first request

> Use discovery-intake on the KitDesk playground. Read project-context/PROJECT.md and the discovery sources listed in sources/INDEX.md. Identify material conflicts and ask me the most important questions before writing stories. Save the intake in artifacts/discovery/.
