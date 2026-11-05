# AlphaOSINT Jobs MCP

Six remote MCP servers that give an AI agent live job-market data. Each one is an [Apify](https://apify.com) Actor exposed through Apify's hosted MCP endpoint, so there is nothing to run locally: add the URL, sign in to Apify, and the tools appear.

| Server | What it returns | Endpoint |
|---|---|---|
| LinkedIn Jobs | Public LinkedIn listings by keyword and location: title, company, seniority, employment type, posting date, applicant count, salary when shown, full description | `https://mcp.apify.com/?tools=johnvc/linkedin-jobs-api` |
| Google Jobs | Google Jobs results for a query and location, with qualifications, benefits and direct apply links | `https://mcp.apify.com/?tools=johnvc/Google-Jobs-Scraper` |
| Wellfound | Startup jobs from Wellfound with salary and equity ranges parsed | `https://mcp.apify.com/?tools=johnvc/wellfound-jobs-api` |
| Ashby boards | Every opening on a company's Ashby job board, including published salary data | `https://mcp.apify.com/?tools=johnvc/ashby-job-board-scraper` |
| SAP SuccessFactors | Jobs from SuccessFactors public career sites | `https://mcp.apify.com/?tools=johnvc/sap-successfactors-jobs-api` |
| isolved / ApplicantPro | Jobs from isolved and ApplicantPro career sites, with tenant discovery | `https://mcp.apify.com/?tools=johnvc/isolved-jobs-api` |

You pay Apify per result on your own account (fractions of a cent per job for most of these; the Google Jobs server charges per page of 10). The free plan includes $5 of monthly credit. Token: [console.apify.com/settings/integrations](https://console.apify.com/settings/integrations).

## Install

### Gemini CLI

```bash
gemini extensions install https://github.com/johnisanerd/alphaosint-jobs-mcp
```

Gemini asks for your Apify API token once and stores it as a setting.

### Claude Code

One line per server you want, for example:

```bash
claude mcp add --transport http linkedin-jobs "https://mcp.apify.com/?tools=johnvc/linkedin-jobs-api"
```

Then `/mcp` to sign in to Apify. Or clone this repo and run Claude Code inside it: the `.mcp.json` here registers all six.

### Cursor

Open this repo in Cursor, or copy `.mcp.json` into your project. Cursor picks up the servers and handles the Apify sign-in.

### VS Code

Add to `.vscode/mcp.json`:

```json
{ "servers": { "linkedin-jobs": { "type": "http", "url": "https://mcp.apify.com/?tools=johnvc/linkedin-jobs-api" } } }
```

### Any other MCP client

Use the endpoint from the table as a Streamable HTTP server. Apify's MCP endpoint supports OAuth, or send `Authorization: Bearer <your Apify token>`.

## Try it

- "Find 20 remote machine learning engineer jobs posted this week on LinkedIn and list the ones that state a salary."
- "What data analyst roles are on Google Jobs in Austin right now, and which companies post the most?"
- "Pull every open role on Anthropic's Ashby board and group them by team."

## Notes

- Each server exposes the Actor's input schema as the tool's parameters, so the agent can set keywords, locations, time windows and result caps itself. Set a cap when you want to bound spend.
- Results are the Actor's dataset rows as JSON.
- The Actors are built and maintained by [AlphaOSINT](https://alphaosint.com) and published on Apify as `johnvc`. Issues and questions: [this repo's issue tracker](https://github.com/johnisanerd/alphaosint-jobs-mcp/issues).

MIT License.
