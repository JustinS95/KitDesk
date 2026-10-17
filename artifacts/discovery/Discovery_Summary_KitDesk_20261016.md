# Discovery summary — KitDesk

Date: 2026-10-16. Status: **intake complete for a provisional story handoff; detailed rules remain open**.

Purpose: first discovery-intake skill trial, establishing a sourced baseline before drafting member-request and desk-decision stories. Audience: user role-playing the fictional decision owners. This is scenario discovery, not evidence of a working application.

## Evidence and coverage

Read in full: project-context/PROJECT.md v1 and discovery sources SRC-01–SRC-04 v1. Paths below are relative to the playground root.

| Source | Path | Relevant coverage |
|---|---|---|
| Project context v1 | `project-context/PROJECT.md` | Scope envelope, actors, glossary, ownership and artifact destinations |
| SRC-01 v1 | `sources/discovery/project-brief.md` | B01–B04: problem, candidate release scope, exclusions and undecided reminders |
| SRC-02 v1 | `sources/discovery/discovery-transcript.md` | T01–T08: current work, recorded decisions, policy proposals and actions |
| SRC-03 v1 | `sources/discovery/stakeholder-email.md` | E01–E03: later change proposals, not superseding approvals |
| SRC-04 v1 | `sources/discovery/current-process.md` | P01–P03: described manual process and exceptions; not observed production behavior |

The source index was read for navigation. SRC-05–SRC-09, design visuals, engineering implementation, live board data and application behavior were not reviewed for this intake. No blanket source-precedence rule is assumed.

## Business context and outcome

Members request tools through email; coordinators reconcile a spreadsheet and can promise the same item twice (SRC-01 B01; SRC-04 P01). The intended outcome is a consistent booking-to-return workflow with member visibility into their own requests and loans and staff control of lending (SRC-01 B02). Success thresholds are not agreed; reduced duplication and coordinator effort are candidate measurement areas, not quantified targets (SRC-02 T08).

Affected actors: members, desk coordinators, workshop manager and membership administrator. Technical advice does not confer business-policy authority (project context, Actors and decision ownership).

## Scope and boundaries

- Candidate first-release capabilities: browse equipment, request an interval, staff decisions, handover, return and overdue visibility (SRC-01 B02). Cancellation and notifications are also within discovery, not fully approved behavior (project context, Scope envelope; SRC-02 T04/T07).
- Confirmed scenario exclusions: payments/fines, purchasing, transfers between workshops, recurring bookings and public self-registration (project context, Scope envelope; SRC-01 B03).
- Existing membership is the intended basis for access; actual integration availability is not established (project context; SRC-01 B03). Current manual membership checks are not proof of a future automated policy (SRC-04 P02).
- **Revised proposed first story slice:** active member requests available equipment; booking immediately confirms and reserves the equipment for the requested interval, with no separate pending stage; member sees the outcome (UD-01, UD-04). This replaces the original staff-decision slice, not unrelated release capabilities.

## Decisions, proposals and supported needs

| Ref | Classification | Interpretation and evidence |
|---|---|---|
| DI-01 | Original decision superseded by user role-play decision UD-01 | Staff approval for launch was agreed by Leon (SRC-02 T02); automatic confirmation was proposed in SRC-03 E01. The user has now selected automatic confirmation in this exercise; retain the original sources as historical evidence, not current approval policy. |
| DI-02 | Recorded scenario decision | Members see their own bookings; availability must not expose other members' names/contact details. Coordinators need the borrower's contact details for collection, not a general directory (Aisha and Leon, SRC-02 T03). |
| DI-03 | Expressed operational rule; details incomplete | Maya says overlapping bookings for one physical item cannot be approved. Back-to-back handling and inspection buffers remain unresolved (SRC-02 T05). No duration, buffer or boundary semantics inferred. |
| DI-04 | Supported need | Rejected members need to know why (Maya, SRC-02 T02). Approval/rejection must be visible in the portal (Leon, SRC-02 T07). No email channel or exact wording is approved. |
| DI-05 | Conflicting proposals, no confirmed policy | Maya first proposes pending-only member cancellation and desk contact after approval (SRC-02 T04); later proposes approved-booking cancellation until collection (SRC-03 E02). Neither resolves concurrent handover. |
| DI-06 | Supported operational need; damaged-return branch incomplete | Staff record handover/return; members must not record their own returns (Maya, SRC-02 T06). Current damaged tools are set aside, but the future availability lifecycle and clearance permissions are unresolved (SRC-02 T06; SRC-04 P03). |
| DI-07 | Proposals, not approved release scope | Daily reminder emails and weekly overdue exports are suggestions (SRC-03 E03). Portal decision visibility is distinct from email delivery (SRC-02 T07). |

### User role-play decisions — 2026-10-16

Provenance: user's numbered response to this trial's three questions: “1. allow automatic confirmation / 2. hold the equipment / 3. active membership, and no”. These are exercise decisions supplied by the user, not claims of actual approvals from fictional people.

| Ref | Decision | Scope and limits |
|---|---|---|
| UD-01 / Q01 | Allow automatic confirmation when equipment is available. | Supersedes mandatory desk approval for this scenario's launch booking flow. No manual fallback, exception approval or staff override is inferred. |
| UD-02 / Q02 | Equipment is held for the requested interval. | Initially answered in the context of a pending request; UD-04 clarifies that the reservation belongs to the immediately confirmed booking, not a separate pending hold. No expiry or release rule is inferred. |
| UD-03 / Q03 | Require active membership to request; do not recheck membership at approval. | “No” answers the approval-recheck question, not checkout rechecks, integration failure handling or all training questions. No training requirement is added without confirmation. |
| UD-04 / Q10 | An available request immediately becomes a confirmed booking that reserves the equipment; there is no separate pending stage. | Explicit user response “agreed” to this clarification. Supersedes pending-stage interpretations of UD-02. There is no later manual approval step at which to recheck membership; checkout policy remains open. |

UD-04 provenance: user's “agreed” response to the assistant's question recommending immediate confirmation/reservation with no pending stage. No rule is inferred from undocumented current practice. No quantitative business targets, field limits, time zone, technical interfaces or permission inheritance are assumed. Q01, Q02 and Q10 are resolved, as are the active-membership and approval-recheck portions of Q03. Training applicability remains unconfirmed. The questions below are retained as the original intake record; their current resolution status is recorded here.

## Prioritized questions for the first story slice

All open rules can remain unresolved in this provisional intake. “Blocking” below means blocking **finalization of the affected story/criteria**, not blocking the intake itself or all useful work.

| Ref | Question | Class and impact | Decision owner / evidence needed |
|---|---|---|---|
| Q01 | For launch, keep staff approval for every request, or approve Maya's proposed automatic confirmation when free? | Blocking: changes the core decision actor and request outcome (DI-01). | Leon for launch scope, with Maya on booking policy; explicit user role-play response. |
| Q02 | Does a pending request reserve its interval, or may other members submit overlapping requests for staff to choose between? | Blocking: changes request availability and competing-request behavior (SRC-02 T02/T05). | Maya, with Leon if scope changes; explicit policy response. |
| Q03 | What makes a member eligible to request equipment, and must eligibility be checked again at approval? | Blocking: changes who may request and what staff may approve (SRC-02 T05). | Aisha for eligibility rules, with Maya on approval flow; explicit rule, including whether training applies to the selected equipment scope. |

## Deferred questions, not defaulted rules

| Ref | Unknown | Classification for the first slice / later impact | Owner |
|---|---|---|---|
| Q04 | Cancellation permissions, cutoff and collision with handover (DI-05) | Nonblocking for the bounded first slice; blocking before cancellation stories are finalized. | Leon and Maya |
| Q05 | Exact interval interpretation, time zone and back-to-back inspection gap (DI-03) | Blocking before date/availability and approval-boundary criteria are implementation-ready; provisional story outlines can proceed without invented values. | Maya; time-zone owner to confirm |
| Q06 | Membership information unavailable, eligibility changes, checkout rechecks and overrides (SRC-02 T05; SRC-04 P02) | Failure behavior blocks final eligibility exception criteria; checkout/override rules can be deferred while outside the first slice. Current manual escalation is not an approved automated fallback. | Aisha and Maya; override authority to confirm |
| Q07 | Damaged-item availability, clearance authority and walk-in scope (SRC-02 T06; SRC-04 P02/P03) | Nonblocking for first slice; blocking for affected return/availability and walk-in branches. | Maya; Leon for scope |
| Q08 | Reminder/export inclusion, overdue definition and notification policy (SRC-01 B04; SRC-02 T07; SRC-03 E03) | Nonblocking for first slice; blocking before reminders, exports or overdue criteria are finalized. | Leon; operational timing with Maya |
| Q09 | Baseline and success targets (SRC-02 T08) | Nonblocking for provisional story outlines; needed before measurable business outcomes can be finalized. | Leon, supported by operational data from Maya |
| Q10 | With automatic confirmation, does an available request immediately become a confirmed booking that holds the equipment, or is there a separate pending-hold stage? | Resolved by UD-04: immediate confirmation and reservation; no separate pending stage. | User role-play confirmation; arose from UD-01 and UD-02 together. |

## Readiness and next action

The evidence and user decisions now support a provisional automatic-booking story draft and the recorded privacy boundaries. Further intake is not required merely to draft that outline. Interval boundaries, eligibility exceptions and equipment-training applicability must remain explicit unresolved details; the output must not be called implementation-ready or executable. The original desk-approval story must not be generated unchanged. Story authoring is the recommended next trial, not an action performed by this intake.

Source-stated follow-up actions remain unchanged: Maya brings damaged-return examples, Aisha proposes eligibility checks, Leon decides cancellation/reminder scope; no due dates are recorded (SRC-02 T08). These actions have not been completed merely by listing them here.

This intake and a separate skill-trial observation record were saved. No source files, stories, remote systems or reusable skills were changed, and no application tests were executed. The bounded discovery trial is complete for a provisional handoff; that does not certify the full skill library or resolve every product rule.
