# Booking decisions — acceptance-criteria trial

Date: 2026-10-16. Status: **scenario policies confirmed; refinement approved for application and applied to KD-ST-001 v2**.

This supplements the [initial intake](Discovery_Summary_KitDesk_20261016.md). Its training, inspection-gap and failure-feedback questions are now resolved to the extent stated below. Original sources and earlier trial records remain historical baselines, not updated policy documents.

| Ref | Confirmed scenario decision | Conversation evidence / limits |
|---|---|---|
| UD-05 | Require at least 30 minutes between bookings of the same physical item for inspection. | User: “let's add a 30 minute inspection gap”. Assistant clarified: a booking ending at 10:00 permits the next at 10:30, not earlier. Applies between earlier and later bookings, irrespective of request order. Does not establish opening hours, a time zone, inspection staff actions or damaged-item clearance. |
| UD-06 | Active membership is sufficient for membership/training eligibility in release one; training checks are excluded. | User: “2. yes and yes” to active membership being sufficient with training checks excluded, and preventing booking when membership cannot be verified. Item availability still applies; active membership does not override it. |
| UD-07 | If membership cannot be verified, prevent booking. | Same numbered response. No confirmed booking or reservation is created for that request. No pending booking or automatic retry is introduced. |
| UD-08 | Explain the applicable failure to the member and create no booking: active membership required, membership could not be verified, or requested interval unavailable. | User: “3. yes” to the three proposed failure outcomes. Preserve existing reservations when the requested interval is unavailable. Meaning is approved, not exact message copy. |

Still unresolved: time zone and daylight-saving interpretation, permitted date/time selections, complete equipment-condition availability rules, cancellation/release, checkout rechecks and staff overrides. Do not re-ask settled training, gap-duration or membership-unavailable questions as if no decision exists. No implementation, test execution or external action is authorized by these decisions.
