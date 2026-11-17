# Changelog

## v1.0.1

Plans now link only to their landing page on simoptions.com, where they are bought.

- `plans_find`: each plan's one link is `pageUrl`, its landing page. The `checkoutUrl` field is removed.
- Bouygues Telecom plans link to the Europe page.

## v1.0.0

First public release of the SimOptions connector: a remote, read-only MCP server for finding and comparing travel eSIM plans.

Server URL: `https://simoptions.com/api/connector/` (streamable HTTP, no sign-in).

Tools (all read-only, no sign-in):

- `destinations_search`: find the countries and regions SimOptions sells eSIMs for.
- `plans_find`: plans for one or more destinations, filtered by days and data, with local-currency prices and plan and checkout links.
- `devices_check`: check whether a phone is eSIM-compatible.

Install in Claude Code from the marketplace:

```bash
claude plugin marketplace add MWS-HK-SimOptions/public-connector
claude plugin install simoptions@simoptions
```

Or add the server URL directly:

```bash
claude mcp add --transport http simoptions https://simoptions.com/api/connector/
```
