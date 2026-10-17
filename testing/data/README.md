# Synthetic data

The CSV files contain invented identifiers and display values only. They do not establish validation rules, membership-policy enums, training grants, login access or provisioned application state. Do not expand them into real personal information.

`membership_label` and `condition_label` are sample descriptions, not approved state machines. Which sample cases are permitted must come from confirmed requirements. Dates and bookings should be created for a specific later test run only when the environment and policies are known.

## Booking scenario fixtures

[KD-ST-001 v2 booking fixtures](booking-fixtures/README.md) add an isolated portable JSON dataset and coverage guide: fictional personas/items, relative-minute booking scenarios and separately blocked policy prompts. These are semantic test-design examples, not application seed payloads, runnable tests or executed evidence; they do not change the CSV conventions above.
