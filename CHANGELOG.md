# Changelog

## v1.0.0

First public release of the SimOptions connector: a remote, read-only MCP server for finding and comparing travel eSIM plans.

Server URL: `https://simoptions.com/api/connector` (streamable HTTP, no sign-in).

Tools (all read-only, no sign-in):

- `destinations_search`: find the countries and regions SimOptions sells eSIMs for.
- `plans_find`: plans for one or more destinations, filtered by days and data, with local-currency prices and plan and checkout links.
- `plans_get`: full detail of one plan.
- `devices_check`: check whether a phone is eSIM-compatible.
- `guides_setup`: eSIM installation and activation help. <!-- guides_setup: confirm -->

Install in Claude Code from the marketplace:

```bash
claude plugin marketplace add MWS-HK-SimOptions/public-connector
claude plugin install simoptions@simoptions
```

Or add the server URL directly:

```bash
claude mcp add --transport http simoptions https://simoptions.com/api/connector
```
