---
description: List your Nonresident Tax orders, their status, and your active plans (needs sign-in)
---

Use the `my-account` skill to show the signed-in customer's orders and active plans.

Rules for this command:

- Read-only. Call `list_my_orders`, then `get_services_summary`.
- If the connector is not signed in, give the sign-in steps from the skill and stop.
- Answer in this shape: one line per order ("<order type>, <package if any>: <status>, ordered <date>"), newest first, then "Active plans:" with each plan and its renewal date. Say if the list is truncated.
- Finish with: next steps, uploads and payments are in the dashboard at https://app.nonresident.tax.
