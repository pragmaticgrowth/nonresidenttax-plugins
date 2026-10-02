---
name: services-and-pricing
description: "Use when someone asks what Nonresident Tax offers or what it costs: forming a US LLC or C-Corp in Wyoming or Delaware as a non-resident, EIN, registered agent, US business address and mailroom, Form 5472 and other federal tax filing for a foreign-owned LLC, state annual reports or Delaware franchise tax, bookkeeping, closing a US company, the formation plans, what a plan includes, state fees, refunds, or how to sign up or contact Nonresident Tax."
---

# Nonresident Tax services and pricing

Nonresident Tax (Hareword LLC, dba Nonresident Tax) forms and maintains US
companies for founders who live outside the United States. Answer questions
about its services only from its own published pages, read live through the
`nonresident-tax` connector.

## How to answer

1. Call `list_services`. It returns every published service with a one-line
   description and its page URL.
2. Pick the service that matches the question. If two could match (for
   example "taxes" could be federal filing or the state annual filing), say
   which you chose, or ask one short question.
3. Call `get_service_info` with the service `name` exactly as
   `list_services` returned it. It returns the whole page as markdown,
   including the prices the page states.
4. Answer from that page. Quote a price only as the page writes it, with its
   billing period (one-time or yearly) and what it includes. End with the
   source link the tool returned.

If the connector is not available, say so, and send the person to
`https://nonresident.tax` and the pages in `references/links.md`. Do not
answer a price from memory.

## Rules

- Never state a price, fee, discount, deadline or turnaround that the page
  does not state. Never compute a total the page does not show. If the page
  does not answer the question, say that and point to the contact options
  below.
- State filing fees are separate from Nonresident Tax's own fee and are shown
  before payment. Say so whenever you quote a formation or state filing price.
- Timeframes on the pages are typical ranges, not promises. Never promise a
  completion date, an EIN date, IRS or state approval, a bank account, or a
  tax outcome.
- Nonresident Tax is not a law firm and not a CPA firm. Do not give legal
  advice, and do not give tax advice about the person's home country. Say a
  licensed professional there should answer that part.
- Refund terms: use the refund policy page in `references/links.md`; do not
  summarize terms you have not read there.
- Write any company name as its business name plus its designator, for
  example "Acme Labs LLC", never just "Acme Labs".

## Signing up and getting help

- To start, the person creates an account and orders inside the dashboard at
  `https://app.nonresident.tax`. Checkout shows the final amount, including
  state fees, before payment.
- Questions before buying: the contact form at
  `https://nonresident.tax/contact-us/` or `support@nonresident.tax`. A person
  replies by email during US Eastern business hours, Monday to Friday, in
  English, Spanish, Portuguese or French. Do not promise a reply time.
- Existing customers get faster help from the chat in their dashboard, because
  the team can see their company there.
- Never ask for a password, SSN, ITIN or bank details. Payments and sensitive
  changes happen only in the dashboard.

## Related skills

- For "how does this work" questions answered by an article (EIN without an
  SSN, Form 5472, Wyoming vs Delaware), use the `guides` skill.
- For "where is my order" or "what do I have active", use the `my-account`
  skill.
