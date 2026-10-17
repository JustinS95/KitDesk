# FX-SRC-07 — Synthetic membership dependency readiness brief

Version 1. Scenario date: 2026-10-26. **Fictional analysis prompt and invented role-play statements; no system queried, account provisioned or integration verified.** This brief adds no API contract or eligibility rule. [Authority](README.md#authority-and-baseline).

## I01 — What is already settled at booking

UD-03/06 make verified active membership sufficient for membership/training eligibility at booking; training checks are excluded. UD-07/08 distinguish inactive from unable-to-verify, require explanation and prevent a confirmed booking/reservation for either. Those decisions do not specify the source mechanics. The [canonical story v2](../../artifacts/stories/KD-ST-001-book-available-equipment.md) also preserves unavailable-interval and simultaneous-conflict outcomes. Do not weaken them because a dependency is missing.

Historical [SRC-07](../engineering/membership-integration.md) is an unapproved technical proposal without verified interfaces, mapping or freshness. A board label or plausible endpoint would not establish that the proposed dependency is usable. This pack supplies neither endpoint nor sample credentials/payloads.

## I02 — Invented dependency discussion

Aisha: “Our membership record may describe a person, but you still need evidence that the portal's member is that person and that the status is current enough. I haven't given you a status list to convert into active/inactive.”

Sam: “For a conditional booking example we can explicitly assume active membership was verified. That lets us reason about the available-interval outcome. It does not prove we can obtain that verification in a running environment.”

Maya: “If the lookup can't answer, please don't call that person inactive. But I also don't want the staff screen inventing permission to waive it.”

These quotes are invented perspectives consistent with the user decisions, not evidence of a discovered system. No synthetic status vocabulary, stale-cache rule, fallback, timeout or identity mapping is adopted. FX-Q04 remains open.

## I03 — Booking and collection are different policy points

Invented Aisha: “I lean toward checking again when equipment leaves, because membership could have changed.”

Invented Maya: “If a confirmed member arrives and the lookup is down, a mandatory recheck could stop collection. I need an explicit policy, not a technical default.”

This is FX-C04. Neither position is chosen. Booking active membership does not silently answer checkout eligibility, and UD automatic confirmation does not authorize a staff override. FX-R07's successful handover path is conditional on collection eligibility established outside this unresolved branch. A draft may cover the established-eligible path, but cannot claim complete handover AC while FX-Q05 remains.

## I04 — Evidence needed before readiness

| Needed evidence | Current evidence in this pack | Consequence / owner to role-play |
|---|---|---|
| Authoritative membership source and meaning of states | Existing-membership premise; no verified source contract | FX-Q04: Aisha with Sam; cannot implement mapping from names alone |
| Linking authenticated member to correct membership record | None | FX-Q04: Aisha with Sam; no guessed identifier or account joins |
| Freshness/verification boundaries and unavailable outcomes | User booking outcomes known; mechanics absent | FX-Q04: preserve AC-08, do not invent cache lifetime or failure fallback |
| Collection recheck and inactive/unverifiable collection outcomes | Conflicting fictional preferences in I03 | FX-Q05: Aisha + Maya; no blanket go/no-go rule |
| Testable environment and authorized isolated data | None established by this source expansion | Dependency verification would require separate authorization and setup |

An exercise can derive readiness questions, a dependency risk, conditional AC and proposed contract examples. It cannot label the dependency delivered, mark a story ready, or execute tests. No remote work-item closure is evidence of membership capability here.

## I05 — Fixture isolation and scope discipline

This brief intentionally allocates no membership-record IDs or login identities. It does not modify the separate `FX-BKG-*` QA fixtures, infer real accounts from synthetic members, or map local source labels to remote issues. No production data, contact details, credentials or secret references are included. Staff access to collection contact details remains task-scoped and does not imply access to full membership records. No public self-registration, training integration or eligibility override is introduced.
