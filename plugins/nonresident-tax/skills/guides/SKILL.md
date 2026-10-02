---
name: guides
description: "Use when a non-US founder asks how something works for a US company: getting an EIN without an SSN or ITIN, Form 5472 and pro-forma Form 1120, Wyoming vs Delaware LLC, registered agents, BOI or annual reports, US bank accounts for non-residents, foreign-owned LLC tax filing deadlines, Delaware franchise tax, or closing a US LLC. Finds Nonresident Tax's published guides and answers from them with links."
---

# Nonresident Tax guides

Nonresident Tax publishes guides for founders who run a US company from
abroad. Use them to answer "how does this work" questions, and always link
the guide you used.

## How to answer

1. Turn the question into one to three short keywords (for example
   `EIN`, `5472`, `Wyoming`, `Delaware`, `bank`, `dissolve`). Call
   `search_guides` once per keyword. The search matches guide titles and
   descriptions, so prefer single concrete terms over full sentences.
2. Choose the one to three guides whose titles fit best. If nothing matches,
   call `search_guides` with an empty query to see every guide, then choose.
3. If you have a web fetch tool, read the chosen guide's markdown version:
   drop the trailing slash and add `.md` (for example
   `https://nonresident.tax/blog/ein-without-ssn/` becomes
   `https://nonresident.tax/blog/ein-without-ssn.md`), or open the URL
   itself. Answer from what the guide says.
4. Without a fetch tool, answer briefly from the guide's description and give
   the link for the details. Do not invent what the guide says.
5. End with the guide links. If the question is really "how much" or "can you
   do this for me", hand over to the `services-and-pricing` skill.

## Rules

- Guides explain US rules in general. They are not legal or tax advice for the
  person's situation, and they say nothing about tax in the person's home
  country. Say a licensed professional should confirm anything that depends on
  their own facts or their country.
- Deadlines and thresholds change. If a guide shows a date or an amount, give
  it as "the guide says", with the link, and suggest checking the IRS or state
  source the guide cites for anything time-critical.
- Never promise an outcome: an EIN date, a bank approval, an IRS acceptance or
  a penalty waiver.
- Write any company name as its business name plus its designator, for
  example "Acme Labs LLC".
