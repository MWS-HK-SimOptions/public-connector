# SimOptions connector

SimOptions public connector for ChatGPT and Claude: find and compare travel eSIM plans, check phone compatibility, and get a checkout link.

[SimOptions](https://simoptions.com) is a travel eSIM store run by MWS HK Limited. This connector is a remote MCP server that lets an AI assistant answer travel eSIM questions with live SimOptions data: which destinations are covered, which plans fit a trip, what a plan includes, and whether a phone supports eSIM.

- **Server URL:** `https://simoptions.com/api/connector/`
- **Transport:** streamable HTTP
- **Access:** read-only, no sign-in, no API key

This repository holds only the public listing files for the connector. The server itself is not in this repository.

## Tools

All tools are read-only and work without signing in.

| Tool | What it does |
| --- | --- |
| `destinations_search` | Finds the countries and regions SimOptions sells eSIMs for. |
| `plans_find` | Lists plans for one or more destinations (multi-country trips), filtered by days and data, with prices in local currency, networks, 5G, calls/SMS, top-up support, and links to the plan page and checkout. |
| `devices_check` | Checks whether a phone is eSIM-compatible. |

## Connect

### Claude Code

Add the server directly:

```bash
claude mcp add --transport http simoptions https://simoptions.com/api/connector/
```

Or install it as a plugin from this repository's marketplace:

```bash
claude plugin marketplace add MWS-HK-SimOptions/public-connector
claude plugin install simoptions@simoptions
```

### Claude.ai and the Claude apps

Open **Customize > Connectors**, add a custom connector, and enter `https://simoptions.com/api/connector/`. No sign-in is needed. On Team and Enterprise plans, an Owner adds custom connectors for the organization.

<!-- TODO: once the connector is listed in Anthropic's directory (https://claude.ai/directory), add the directory link here. -->

### ChatGPT

Go to [ChatGPT Plugins](https://chatgpt.com/plugins), select the plus button, then **Add custom MCP server**. Enter `https://simoptions.com/api/connector/` as the server URL, choose no authentication, and select **Create as a plugin**. Custom MCP servers depend on your account and workspace settings.

<!-- TODO: once the plugin is published in the ChatGPT plugin directory, add the directory link here. -->

### Other MCP clients

Point any client that supports streamable HTTP at `https://simoptions.com/api/connector/`. No headers or credentials are required.

## Example prompts

- "Find an eSIM for 10 days in Japan with at least 10 GB."
- "Compare eSIM plans for a trip to France, Italy and Spain."
- "Does the iPhone 13 support eSIM?"

## Privacy, terms and support

- Privacy policy: https://simoptions.com/privacy-cookie-policy/
- Terms: https://simoptions.com/general-conditions-of-services/
- Support: contact@simoptions.com or https://simoptions.com/contact-us/

SimOptions is operated by MWS HK Limited.
