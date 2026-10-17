# KitDesk project context

Status: fictional baseline for practice, version 1. No application has been implemented.

## Historical baseline and current authority

The version 1 narrative below is retained as historical context, including its original staff-approval proposal. It is not the current booking policy where later **actual user role-play decisions** explicitly supersede it. Read [UD-01–UD-04](../artifacts/discovery/Discovery_Summary_KitDesk_20261016.md#user-role-play-decisions--2026-10-16), [UD-05–UD-08](../artifacts/discovery/Booking_Decisions_AC_Trial_20261016.md) and the unchanged canonical [KD-ST-001 v2](../artifacts/stories/KD-ST-001-book-available-equipment.md).

Current confirmed booking behavior is immediate confirmation and reservation without staff approval or a pending stage. Active membership suffices for membership/training eligibility; training checks are excluded. Reservations of the same physical item must not overlap and need at least 30 minutes between them in either request order, including exactly 30 minutes. Inactive or unverifiable membership, or an unavailable interval, prevents the new booking with an explanation. Own-record and borrower-privacy boundaries apply. Booking is not actual handover or a loan; the gap does not clear damaged equipment.

The [Expansion 01 pack](../sources/expansion-01/README.md) adds **invented interviews and author-defined, review-pending premises**, not new user or stakeholder approval. Its detail cannot settle canonical date/time, membership-dependency or equipment-condition questions. See the [source index](../sources/INDEX.md), [expansion synthesis](../artifacts/discovery/Expansion_01_Discovery_Synthesis.md) and [backlog index](../artifacts/stories/EXPANDED_BACKLOG.md) for provenance and current candidate/readiness status, not an assumed Ready count. No application or provisioned test environment is established.

## Problem and desired outcomes

Northstar Community Workshop currently coordinates equipment loans using a shared spreadsheet and email. Members cannot reliably tell whether a tool is available, and desk staff spend time reconciling requests and overdue loans.

The proposed first release should let members discover equipment and request bookings, while staff manage approvals, handover and return. Success measures are not yet agreed; do not invent quantified targets.

## Scope envelope

In scope for discovery: equipment availability, booking requests, approval/rejection, member cancellation, checkout, return, overdue visibility, and notifications. These are candidate capabilities, not complete approved requirements.

Explicitly excluded from this scenario's first release: payments/fines, purchasing, multi-workshop inventory transfers, recurring bookings, and public self-registration. Existing membership records are assumed to be available, but the integration mechanism and actual test environment are not established.

## Actors and decision ownership

| Fictional actor/person | Context | Decision responsibility in the scenario |
|---|---|---|
| Member | Borrows equipment | May describe needs; not policy authority |
| Desk coordinator / Maya Chen | Handles lending operations | Booking and checkout policy owner |
| Workshop manager / Leon Patel | Sponsor | Release scope and business outcomes |
| Membership administrator / Aisha Reed | Manages membership information | Membership eligibility and personal-data visibility |
| Technical lead / Sam Ortiz | Advises delivery | Engineering conventions, not unilateral business policy |

Names are role-play characters, not actual users. No email addresses, account identities, assignees or mention identifiers are configured. Ask the user to role-play the appropriate owner when resolving a decision. Do not claim a character approved a new decision without that response.

## Vocabulary

- **Equipment item:** an individually lendable tool or kit, not a product category.
- **Booking request:** a member's request to use one item over a requested interval.
- **Loan:** the actual handover-to-return record. A booking and a loan are not interchangeable.
- **Desk coordinator:** operational staff role; not automatically an administrator.
- **Overdue:** a business concept whose exact clock, time zone and threshold remain open.

## Evidence conventions

Source IDs and locators are in `../sources/INDEX.md`. Preserve the difference between current practice, proposed future behavior, recorded decisions and open questions. No blanket newest-source-wins policy applies. The source pack intentionally disagrees in places. A design control is not evidence that a permission has been approved.

Use stable local story labels such as `KD-ST-001` if needed; these are not remote work-item IDs. No UUID registry, hierarchy schema, story-point scale or ADO process has been adopted. Do not add these merely because a skill supports them.

## Artifact destinations

All paths are relative to this playground root. These are playground storage conventions, not a new configuration schema for the skill library.

| Artifact | Destination |
|---|---|
| Intake, scope, questions and decision log | `artifacts/discovery/` |
| Meeting summaries | `artifacts/meeting-summaries/` |
| Synthesized requirements and BRDs | `artifacts/requirements/` |
| Canonical stories, criteria and optional task drafts | `artifacts/stories/` |
| Process maps | `artifacts/process-maps/` |
| Design analysis | `artifacts/design-briefs/` |
| Gap, consistency and estimate reviews | `artifacts/reviews/` |
| Draft stakeholder emails | `artifacts/communications/` |
| Draft release notes | `artifacts/release-notes/` |
| Test cases, plans and authored automation | Matching subfolder under `testing/` |
| Actual test run evidence | `testing/evidence/<unique-run-id>/` |
| Approved integration plans/manifests/results | `integrations/<unique-operation-id>/` |
| Skill trial observations | `evaluation/<unique-exercise-id>/` |

Keep original inputs in `sources/`. Do not duplicate canonical stories under requirements. Local relative links and source locators are sufficient; no registry service is needed. Preserve existing outputs; use a new descriptive exercise filename on collision unless an update was explicitly requested.
