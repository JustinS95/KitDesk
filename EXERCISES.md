# Skill exercises

Use paths relative to this playground. Load each selected skill through the normal skill mechanism and follow its references. Prompts authorize the described local artifact only, not external action or automatic follow-on work.

The original sequence below is retained as a baseline exercise catalog. For current-state work, read the [authority clarification](project-context/PROJECT.md#historical-baseline-and-current-authority) first: booking is now automatic under UD decisions, so old approval prompts are historical comparisons, not authorization to recreate an approval story. Do not re-ask settled decisions or duplicate KD-ST-001. For the expanded bundle, use the [focused routes](#expansion-01-focused-routes).

## Suggested sequence

| Exercise | Skills | Try this request | Output destination / key observation |
|---|---|---|---|
| 01: Intake | discovery-intake | Read PROJECT.md and SRC-01 through SRC-04. Identify material unknowns and ask me the highest-impact questions before stories. Save a provisional intake. | `artifacts/discovery/`; does it retain conflicts instead of inventing rules? |
| 02: Meeting summary | writing-meeting-summaries | Summarize SRC-02 with decisions, proposals, actions and unresolved questions, citing T locators. | `artifacts/meeting-summaries/`; are owners and missing due dates honest? |
| 03: Slice scope | scope-decomposition | Propose independently valuable slices for KitDesk using the discovery sources. Do not assume architecture layers or a tracking hierarchy. | `artifacts/discovery/`; does it avoid frontend/backend pseudo-stories? |
| 04: Synthesize | synthesize-requirements | Reconcile SRC-01 through SRC-05 into traceable desired-state requirements. Keep disputed rules unresolved. | `artifacts/requirements/`; does it preserve provenance and decision status? |
| 05: BRD | writing-brds | Draft a KitDesk BRD from the source pack and any explicitly confirmed exercise decisions. Do not invent outcome metrics. | `artifacts/requirements/`; is it distinct from a copied backlog? |
| 06: Stories | writing-user-stories | Draft member request and desk approval stories using confirmed behavior; mark unresolved rules. Do not publish. | `artifacts/stories/`; actors, record scope and lifecycle must connect coherently |
| 07: Criteria | writing-acceptance-criteria; applying-project-conventions | Review the saved stories and SRC-06. Refine observable acceptance criteria without inventing field limits, endpoints or role policies. | Update selected canonical stories only after reading them; show remaining gaps |
| 08: Process | process-mapping | Map current-state request-to-return from SRC-04. Keep future recommendations separate. | `artifacts/process-maps/`; Mermaid branches must match source-supported exceptions |
| 09: Design | figma-design-analysis | Analyze SRC-05 as a supplied text-only export. Extract supported behavior candidates and gaps; do not claim Figma or visual inspection. | `artifacts/design-briefs/`; visible controls must not become approved permissions |
| 10: Consistency | adversarial-story-review | Review the saved request, approval, cancellation and return stories together, only if those stories exist. Check record scope and lifecycle. | `artifacts/reviews/`; don't fabricate missing stories to make the review possible |
| 11: Gaps | gap-analysis | Compare described current practice in SRC-04, intended behavior and actual saved story coverage. Distinguish missing coverage from unresolved intent. | `artifacts/reviews/`; no claim of verified current implementation |
| 12: Stakeholder follow-up | writing-client-emails | Draft a short email asking Leon and the policy owners to resolve approval, cancellation and reminder scope. | `artifacts/communications/`; draft only, no invented commitments or sending |
| 13: Test cases | writing-test-cases | Derive manual cases from a selected saved story and its approved criteria. Keep exploratory questions separate. | `testing/test-cases/`; traceable steps, negative/permission cases and honest prerequisites |
| 14: UAT plan | writing-test-plans | Draft a risk-based UAT plan for selected stories. Record missing environment, data, roles and entry gates. | `testing/test-plans/`; don't imply execution readiness |
| 15: Automation feasibility | writing-playwright-tests | Assess whether runnable automation can be authored from current inputs. If blocked, save only a prerequisite checklist; do not invent selectors or install anything. | `testing/automation/`; no app/framework should result in an explicit limitation |
| 16: Release draft | writing-release-notes | Use SRC-09 to draft candidate release notes, clearly distinguishing merged, done, demoed, planned and actually released. | `artifacts/release-notes/`; no shipped claims from ticket status |
| 17: Blockers | ado-board-blocker-analysis | Use SRC-08 for an explicitly offline analysis. Explain useful partial work and unknown dependencies. Propose no remote mutations. | `artifacts/reviews/`; blocked labels are not proof all work must stop |
| 18: Readiness | ado-ready-for-work-analysis | Propose readiness criteria for SRC-08, ask me to confirm them, then assess against the confirmed criteria and actual prerequisites. | `artifacts/reviews/`; a Done predecessor alone must not imply ready |
| 19: Estimates | ado-estimate | Assess SRC-08 offline for estimation prerequisites. Ask me for the team's scale/calibration before proposing numbers. | `artifacts/reviews/`; uncertainty and scope gaps must remain visible |
| 20: Team context | manage-project-team | Review project-context/PROJECT.md. Draft the missing team/ownership questions needed before assignment or mentions; do not resolve fictional people into real identities. | `artifacts/discovery/`; do not invent emails or cache identities |

The first exercise's `PROJECT.md` means `project-context/PROJECT.md`. Sources are listed in `sources/INDEX.md`. Outputs from earlier exercises become inputs only after they actually exist; drafts are not approvals.

## Skills needing extra material or explicit external authorization

| Skill | What must be supplied before a meaningful operational trial |
|---|---|
| convert-word-to-markdown | Real DOCX, approved destination and conversion capability; check losses honestly |
| ado-operations; fetch-ado-work-items | Exact real sandbox organization/project/scope and authorized read capabilities; SRC-08 is not a live export |
| ado-work-item-creation | Reviewed local items, exact process/hierarchy/target mappings and approval for the shown create/update batch |
| sync-stories-from-ado | Adopted canonical store, real stable mappings, complete scoped snapshots and two-sided baselines; do not fabricate these from SIM labels |
| comment-on-ado-item | Exact real target, approved comment and any verified mention identities; offline drafts can be practiced without posting |
| ado-move-board-item | Real board metadata, baseline revisions and explicit approval of exact moves; offline labels are insufficient |
| post-test-evidence | Actual retained test evidence and separately approved real uploads/comments/edits/moves; never publish synthetic passes |

## Meta-skills after a trial

- `using-ba-superpowers`: choose a route when the next artifact is unclear; no need to load every skill.
- `continuous-skill-improvement`: use actual observations, not the existence of this playground, to propose a reusable correction.
- `writing-ba-skills`: only after a separate request to revise a skill. Log improvement candidates in `evaluation/` without changing the live library automatically.

## Deliberate challenge areas

These are fixture design notes, **not a record of failures observed in the skills**: changed approval proposal, disputed cancellation, member-vs-staff privacy, damaged-return lifecycle, unspecified time/eligibility rules, dependency marked Done without availability, partial work despite Blocked, and release claims unsupported by delivery evidence. Catching these is a useful signal, not a complete proof of skill quality.

## Expansion 01: focused routes

Start with the [five-minute demo](DEMO_GUIDE.md), then choose **one** route below; no full skill chain is required. These exercises use [invented discovery sources](sources/expansion-01/README.md), not real research. UD decisions outrank contradictory historical notes; FX premises are review pending. Use the [backlog index](artifacts/stories/EXPANDED_BACKLOG.md) for actual story status, not an assumed count or Ready label. Retain original sources, KD-ST-001 v2 and earlier trial observations.

### Discovery: decide what to ask next

> Use discovery-intake. Read the Expansion 01 source guide, FX-SRC-04 and FX-SRC-07, and the current UD decision records. Compare them with artifacts/discovery/Expansion_01_Discovery_Synthesis.md. Select three questions whose answers most change cancellation, collection or condition scope. Cite the conflicting statements, identify the fictional role to ask, and explain useful work still possible. Save a new expansion follow-up in artifacts/discovery/; do not answer the questions yourself.

**Look for:** prioritization and preserved authority, not another invented workshop or a re-opened 30-minute/training decision. No stakeholder contact is authorized.

### Story/AC refinement: make one conditional slice clearer

> Use writing-acceptance-criteria. From artifacts/stories/EXPANDED_BACKLOG.md select one extension candidate concerning handover or return. Review its actor, record scope, successful outcome and refusal/stale/uncertain paths against the cited FX sources. Save a refinement proposal in artifacts/reviews/ without editing the canonical story. Separate source-backed criteria under explicit fixture premises from questions needing a user decision. Do not alter KD-ST-001 or add staff approval, training checks or automatic bookability after return.

**Look for:** observable outcomes without invented endpoints, role identifiers, timing defaults or business approval. A well-formed conditional candidate is not necessarily implementation-ready; applying a proposal is a separate action.

### Adversarial review: follow one item across records

> Use adversarial-story-review. Select connected cancellation, handover and return candidates from the backlog index, reading only the selected stories and their cited sources. Trace one member/item from confirmed reservation through actual loan and damaged receipt. Challenge ownership, duplicate actions, cancellation-versus-handover, reviewer authority and later reservations. Save a bounded review in artifacts/reviews/; label unresolved outcomes rather than choosing a race winner or overriding policy.

**Look for:** booking, loan and condition-case boundaries surviving direct/stale access; a returned loan is not a cleared or bookable item. This is document review, not a security or concurrency test.

### Process mapping: explain an exception without inventing policy

> Use process-mapping. Read artifacts/process-maps/Expansion_01_Lending_Lifecycle.md and FX-SRC-06/08. Create a small alternate-path map in a new artifacts/process-maps/ file for correct-item damaged receipt followed by condition review. Show who acts, which record changes, what remains unchanged, and unresolved exits. Preserve the existing map; label FX premises and distinguish manual syntax inspection from rendering or stakeholder validation.

**Look for:** actual receipt closing the loan separately from condition assessment, with no automatic availability, debt, email or clearance permission.

### Test design: turn a boundary into an honest future case

> Use writing-test-cases. Read canonical KD-ST-001 v2, testing/data/booking-fixtures/README.md, testing/data/booking-fixtures/coverage.md, and testing/test-cases/KD-ST-001_Manual_Test_Design.md. Design a focused supplement for the 29/30/31-minute boundaries in both request orders plus own/non-owner visibility. Bind selected FX-BKG scenario IDs to ACs, preserve isolated baselines, and list environment/authentication/navigation prerequisites without inventing them. Keep date/DST/condition explorations without an accepted expected outcome. Save a new file in testing/test-cases/; do not run tests, seed data or check off ACs.

**Look for:** design traceability and explicit blockers. The [fixture validation](evaluation/expanded-demo-01/fixture-validation.md) records JSON parsing and static consistency checks only, not passed app tests. Relative-minute data is not an approved calendar or a provisioned account set.

All routes authorize only the named local draft. No automatic publishing, synchronization, board changes, sending, installs or application/test execution follows.
