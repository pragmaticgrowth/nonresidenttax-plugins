# Nonresident Tax plugin for Claude

Nonresident Tax helps founders who live outside the United States form and
run a US company: LLC or C-Corp formation in Wyoming or Delaware, EIN,
registered agent, a US business address with mail scanning, federal tax
filing (Form 5472 with pro-forma Form 1120 and related returns), state annual
filings, bookkeeping and dissolution.

This plugin lets Claude answer questions about those services from the
company's own published pages, find the right guide, and, after you sign in,
tell you where your own orders stand. It works in claude.ai, the Claude
desktop and mobile apps, Cowork and Claude Code.

## What it does

| Part                         | What you can ask                                                                                      |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- |
| `services-and-pricing` skill | "What does Nonresident Tax offer?", "How much is Form 5472 filing?", "What is in the formation plan?" |
| `guides` skill               | "Do I need an SSN to get an EIN?", "Wyoming or Delaware for a non-resident?", "What is Form 5472?"    |
| `my-account` skill           | "Where is my order?", "Which services do I have active?", "When does my plan renew?" (needs sign-in)  |
| `/pricing <service>` command | The published page and price for one service, with its source link                                    |
| `/my-orders` command         | Your orders, their status, and your active services (needs sign-in)                                   |

Every answer about a price comes from the live service page on
nonresident.tax and links to it. The plugin itself stores no prices, so it
never drifts from the website.

## The connector it uses

The plugin declares one remote MCP server, `nonresident-tax`, at
`https://nonresident.tax/mcp`. It is operated by Nonresident Tax. Every tool
on it is read-only: nothing can be ordered, paid, signed, uploaded or changed
through it.

| Tool                   | Sign-in needed | What it reads                                               |
| ---------------------- | -------------- | ----------------------------------------------------------- |
| `list_services`        | No             | The list of services published on nonresident.tax           |
| `get_service_info`     | No             | One service page as markdown, including the price it states |
| `search_guides`        | No             | Guide titles and links that match a keyword                 |
| `list_my_orders`       | Yes            | Your own orders: type, status, package and date             |
| `get_services_summary` | Yes            | Your own active plans and renewal dates                     |

The public tools work without an account. To use the two account tools, open
the plugin's **Connectors** tab, choose **Nonresident Tax**, and sign in with
your Nonresident Tax customer account. Sign-in happens on
`https://app.nonresident.tax`, which asks you to approve Claude by name. The
approval lets Claude call the connector's tools as you, and every one of those
tools is read-only. You can revoke that access at any time by disconnecting
the connector.

## Data and privacy

- The plugin contains no code, hooks or scripts. It is Markdown instructions
  for Claude, the connector address above, and the listing icon.
- Claude sends tool calls only to `https://nonresident.tax/mcp`. Sign-in uses
  standard OAuth with PKCE on `https://app.nonresident.tax`. Nothing is sent
  to any other service.
- The account tools return only the signed-in customer's own records. The
  plugin stores nothing and keeps no history of its own. The MCP server keeps
  routine request logs (time, path, status, errors) for troubleshooting, for
  under 30 days; it does not store tool results.
- Claude never asks you for a password, SSN, ITIN or bank details. Payments,
  document uploads and signatures happen only in your dashboard at
  `https://app.nonresident.tax`.
- How Nonresident Tax handles personal data is in the
  [Privacy Policy](https://nonresident.tax/privacy-policy/).

## Important

Nonresident Tax is not a law firm and not a CPA firm, and nothing Claude says
through this plugin is legal or tax advice. Questions about tax in your own
country of residence need a licensed professional there. Formation does not
guarantee a bank account, and no timeline or government approval is
guaranteed.

## Support

- Email: support@nonresident.tax
- Contact form: https://nonresident.tax/contact-us/
- Customer dashboard: https://app.nonresident.tax

## License

Proprietary. See [LICENSE](LICENSE).
