# Nonresident Tax plugins for Claude

The `nonresident-tax` marketplace. It holds one plugin, **nonresident-tax**,
for founders who live outside the United States and run, or want to start, a
US company with [Nonresident Tax](https://nonresident.tax). In Claude it
answers questions about Nonresident Tax services from the company's own
published pages, searches its guides, and, after you sign in, shows where
your own orders stand. Everything it does is read-only.

## Install

In claude.ai or the Claude apps, add **Nonresident Tax** from the plugin
directory, or open **Customize → Plugins → Add → Add marketplace**, enter
`pragmaticgrowth/nonresidenttax-plugins`, and install **nonresident-tax**.

In Claude Code:

```bash
claude plugin marketplace add pragmaticgrowth/nonresidenttax-plugins
claude plugin install nonresident-tax@nonresident-tax
```

To see your own orders, open the plugin's **Connectors** tab, choose
**Nonresident Tax**, and sign in with your customer account at
app.nonresident.tax.

See [plugins/nonresident-tax/README.md](plugins/nonresident-tax/README.md) for
what the plugin does, the one connector it uses, and what data it sends.

This repository is published from Nonresident Tax's private monorepo; the
`plugins/nonresident-tax/` folder is overwritten on every release, so changes
made here directly are lost. Questions: support@nonresident.tax.

## License

Proprietary. See [LICENSE](LICENSE).
