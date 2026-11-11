---
name: my-account
description: "Use when a Nonresident Tax customer asks about their own account: where their order or filing stands, what they have bought, which plans or services are active, when their plan renews, or what they need to do next. Reads their own records through the signed-in Nonresident Tax connector; read-only."
---

# My Nonresident Tax account

These tools read the signed-in customer's own records. They are read-only:
nothing can be ordered, paid, signed, uploaded or changed from here.

## Before the first call

The account tools need the customer to be signed in to the `nonresident-tax`
connector. If a call fails with an authorization error, or the connector is
not connected, tell the customer:

> Open this plugin's Connectors tab, choose Nonresident Tax, and sign in with
> your Nonresident Tax customer account. The sign-in page is on
> app.nonresident.tax and asks you to approve Claude. Every tool it unlocks
> is read-only.

Then stop until they say they are connected. Never ask for their password or
a code in the chat.

## How to answer

1. Call `list_my_orders`. Each order has an `id`, an `orderType`, a `status`,
   a `packageType` and a `createdAt` date. Orders come most recently updated
   first, not by order date.
2. If `truncated` is true, say only the most recent orders are shown and older
   ones exist.
3. For plans and renewals, call `get_services_summary`. Each entry in
   `activeSubscriptions` has a `plan` and a `currentPeriodEnd`: the date the
   current paid period ends and the plan renews, unless it was cancelled.
   When it has a `bookkeeping` list, each entry gives a `companyName`, the
   `openQuestions` waiting on the customer and the `connectionsNeedingAttention`
   (bank connections that need a new sign-in, are disconnecting, are revoked
   or have new accounts to add). Say that questions are answered, and
   connections reconnected, in the customer's Accounting section. Without a
   `bookkeeping` list, the customer has no bookkeeping set up.
4. For "what do I need to do next", call `list_my_next_actions`. Each entry in
   `actions` is one step waiting on the customer, with a `title`, the
   `companyId`, an `orderId` when it belongs to an order, sometimes a
   `waitingSince` date, and a `url`: the dashboard screen where they finish
   it. Give the title and read the `url` out exactly as returned; never build
   or change a link yourself. An empty list means nothing is waiting on them
   right now: every open order is with the Nonresident Tax team or done. If
   `truncated` is true, say more steps exist and the dashboard lists them all.
   Its bookkeeping steps are the same questions and connections
   `get_services_summary` counts, so the two always agree. If the call answers
   that next steps are temporarily unavailable, say so and suggest trying again
   in a few minutes or opening `https://app.nonresident.tax`.
5. Answer in plain words. Turn raw values into readable ones (`in_progress`
   becomes "in progress", `federal_tax` becomes "federal tax filing") and give
   dates as dates, for example "12 March 2027". Do not show internal ids,
   price ids or field names unless the customer asks for them.
6. When the customer has several orders, lead with the one they asked about,
   then list the rest briefly.

## What these tools do not show

- They do not show documents, messages from the team, tax deadlines for a
  specific return, prices or amounts due. `list_my_next_actions` names the
  steps for federal tax filings, state filings and bookkeeping only; other
  steps (company formation and SS-4 signing, a registered agent change, an
  EIN name correction, closing a company, onboarding, mail) are not in it yet.
  For those, and to upload or pay, send the customer to their dashboard at
  `https://app.nonresident.tax`, where every step and upload lives.
- `activePayments` lists internal price ids. Do not read them out; say "your
  dashboard's billing page lists every payment".
- If the records look wrong or a status has not moved for a long time, suggest
  the chat in the dashboard or `support@nonresident.tax`. Do not guess a
  reason or promise a date.

## Rules

- Write any company name as its business name plus its designator, for
  example "Acme Labs LLC", never just "Acme Labs".
- Never ask for a password, SSN, ITIN or bank details. Payments, uploads and
  signatures happen only in the dashboard.
- Never promise a completion date, an IRS or state approval, a refund or a
  tax outcome.
- Nothing here is legal or tax advice.
