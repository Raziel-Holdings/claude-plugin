# Raziel for Claude

Exact private-market and startup finance math inside Claude, from [Raziel](https://raziel.co), the alternative asset management platform for investors and founders.

Ask Claude things like "What's my XIRR on these three checks?", "How much will this SAFE convert into at a $12M pre?" or "Model dilution across a seed and Series A with a 10% pool top-up", and Claude runs the numbers with Raziel's tested calculators instead of estimating them.

## What's included

- **MCP server** (`https://raziel.co/mcp`): 25 calculators and 3 reference tools.
  - Returns: IRR, XIRR, MOIC, CAGR, TVPI/DPI, carried interest.
  - Startup equity: SAFE conversion, convertible notes, startup valuation, dilution, option pool, pro rata, liquidation preferences, secondary sales.
  - Tax dates: QSBS (Section 1202) and 83(b) and QSBS dates.
  - Real estate and planning: runway, cap rate, cash on cash, portfolio allocation.
  - Founder metrics: burn multiple, Rule of 40, LTV to CAC, CAC payback, net revenue retention.
  - Reference: search Raziel's guides, define private-market terms, and compare Raziel with other platforms.
  - Prompts: investor update, due diligence checklist, data room checklist.
- **Skill** (`raziel-calculators`): tells Claude when to use each calculator, the input conventions (money in USD, percentages as percent numbers, dates as YYYY-MM-DD) and to share the `calculator_url` link that comes with each result.

Every tool is read-only. Results are for education only, not tax, legal or investment advice.

## Install

In Claude Code:

```
/plugin marketplace add Raziel-Holdings/claude-plugin
/plugin install raziel@raziel
```

Or add only the MCP server: `claude mcp add --transport http raziel https://raziel.co/mcp`

## What the plugin sends and stores

- **What it sends:** when Claude calls a tool, the plugin sends that tool's inputs (the numbers, dates or search text Claude passes) to `https://raziel.co/mcp`.
- **What runs:** nothing runs on your computer. No hooks or scripts, and no local packages.
- **What is stored:** the server does pure math and lookups and stores nothing you send. Requests are rate limited per IP.
- **No accounts:** no API key or account is needed.

See the [privacy policy](https://raziel.co/legal/privacy-policy).

## Support

[raziel.co/contact](https://raziel.co/contact) or open an issue in this repository. Developer docs: [raziel.co/developers](https://raziel.co/developers).
