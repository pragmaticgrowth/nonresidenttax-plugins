---
description: Show a Nonresident Tax service's published page and price, with its source link
argument-hint: "<service, for example company formation, federal tax, accounting, dissolution>"
---

Use the `services-and-pricing` skill to answer: what does Nonresident Tax charge for $ARGUMENTS, and what does it include?

Rules for this command:

- If $ARGUMENTS is empty, call `list_services`, show each service's name and one-line description, ask which one, and stop.
- Otherwise call `list_services`, match $ARGUMENTS to one service `name`, then call `get_service_info` with that exact name.
- Quote prices only as the page states them, with the billing period and what is included. Say state fees are separate and checkout shows the final amount.
- End with the source link the tool returned and `https://app.nonresident.tax` to get started.
