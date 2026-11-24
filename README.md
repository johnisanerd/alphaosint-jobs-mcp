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

### One click

Each button adds one server and carries only its URL. Your client opens Apify's sign-in on first use, so no token is ever put in a link.

| Server | Cursor | VS Code | Kiro | Replit |
|---|---|---|---|---|
| LinkedIn Jobs | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=linkedin-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9saW5rZWRpbi1qb2JzLWFwaSJ9) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=linkedin-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Flinkedin-jobs-api%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=linkedin-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Flinkedin-jobs-api%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgTGlua2VkSW4gSm9icyIsImJhc2VVcmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9saW5rZWRpbi1qb2JzLWFwaSJ9) |
| Google Jobs | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=google-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9Hb29nbGUtSm9icy1TY3JhcGVyIn0%3D) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=google-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2FGoogle-Jobs-Scraper%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=google-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2FGoogle-Jobs-Scraper%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgR29vZ2xlIEpvYnMiLCJiYXNlVXJsIjoiaHR0cHM6Ly9tY3AuYXBpZnkuY29tLz90b29scz1qb2hudmMvR29vZ2xlLUpvYnMtU2NyYXBlciJ9) |
| Wellfound | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=wellfound-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy93ZWxsZm91bmQtam9icy1hcGkifQ%3D%3D) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=wellfound-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fwellfound-jobs-api%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=wellfound-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fwellfound-jobs-api%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgV2VsbGZvdW5kIiwiYmFzZVVybCI6Imh0dHBzOi8vbWNwLmFwaWZ5LmNvbS8%2FdG9vbHM9am9obnZjL3dlbGxmb3VuZC1qb2JzLWFwaSJ9) |
| Ashby boards | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=ashby-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9hc2hieS1qb2ItYm9hcmQtc2NyYXBlciJ9) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=ashby-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fashby-job-board-scraper%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=ashby-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fashby-job-board-scraper%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgQXNoYnkgYm9hcmRzIiwiYmFzZVVybCI6Imh0dHBzOi8vbWNwLmFwaWZ5LmNvbS8%2FdG9vbHM9am9obnZjL2FzaGJ5LWpvYi1ib2FyZC1zY3JhcGVyIn0%3D) |
| SAP SuccessFactors | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=successfactors-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9zYXAtc3VjY2Vzc2ZhY3RvcnMtam9icy1hcGkifQ%3D%3D) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=successfactors-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fsap-successfactors-jobs-api%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=successfactors-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fsap-successfactors-jobs-api%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgU0FQIFN1Y2Nlc3NGYWN0b3JzIiwiYmFzZVVybCI6Imh0dHBzOi8vbWNwLmFwaWZ5LmNvbS8%2FdG9vbHM9am9obnZjL3NhcC1zdWNjZXNzZmFjdG9ycy1qb2JzLWFwaSJ9) |
| isolved / ApplicantPro | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=isolved-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9pc29sdmVkLWpvYnMtYXBpIn0%3D) | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=isolved-jobs&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fisolved-jobs-api%22%7D) | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=isolved-jobs&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fisolved-jobs-api%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D) | [![Add to Replit](https://replit.com/badge?caption=Add%20to%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFscGhhT1NJTlQgaXNvbHZlZCAvIEFwcGxpY2FudFBybyIsImJhc2VVcmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9pc29sdmVkLWpvYnMtYXBpIn0%3D) |

<details>
<summary>LM Studio and Goose (copy the link into your browser's address bar)</summary>

LM Studio:

```
lmstudio://add_mcp?name=linkedin-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9saW5rZWRpbi1qb2JzLWFwaSJ9
lmstudio://add_mcp?name=google-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9Hb29nbGUtSm9icy1TY3JhcGVyIn0%3D
lmstudio://add_mcp?name=wellfound-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy93ZWxsZm91bmQtam9icy1hcGkifQ%3D%3D
lmstudio://add_mcp?name=ashby-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9hc2hieS1qb2ItYm9hcmQtc2NyYXBlciJ9
lmstudio://add_mcp?name=successfactors-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9zYXAtc3VjY2Vzc2ZhY3RvcnMtam9icy1hcGkifQ%3D%3D
lmstudio://add_mcp?name=isolved-jobs&config=eyJ1cmwiOiJodHRwczovL21jcC5hcGlmeS5jb20vP3Rvb2xzPWpvaG52Yy9pc29sdmVkLWpvYnMtYXBpIn0%3D
```

Goose:

```
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Flinkedin-jobs-api&type=streamable_http&id=linkedin-jobs&name=AlphaOSINT%20LinkedIn%20Jobs
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2FGoogle-Jobs-Scraper&type=streamable_http&id=google-jobs&name=AlphaOSINT%20Google%20Jobs
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fwellfound-jobs-api&type=streamable_http&id=wellfound-jobs&name=AlphaOSINT%20Wellfound
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fashby-job-board-scraper&type=streamable_http&id=ashby-jobs&name=AlphaOSINT%20Ashby%20boards
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fsap-successfactors-jobs-api&type=streamable_http&id=successfactors-jobs&name=AlphaOSINT%20SAP%20SuccessFactors
goose://extension?url=https%3A%2F%2Fmcp.apify.com%2F%3Ftools%3Djohnvc%2Fisolved-jobs-api&type=streamable_http&id=isolved-jobs&name=AlphaOSINT%20isolved%20/%20ApplicantPro
```

</details>

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

## For agents that pay with a wallet (x402)

Apify also sells runs of these Actors to agents that pay in USDC, with no Apify account. Both routes are operated by Apify:

- **Prepaid token.** `GET https://agi.apify.com/protocols/x402/prepaid-tokens?amount=1&currency=usd` answers with an x402 payment challenge. Pay it and the retry returns a Bearer token worth that amount, which works on every endpoint in the table above and on Apify's REST API.
- **Pay per run.** `POST https://agi.apify.com/api-proxy/actors/johnvc~linkedin-jobs-api/runs?amount=1&currency=usd` with the Actor input as the JSON body answers `402` with a `payment-required` header (x402 v2, USDC on Base; `amount` is a ceiling, not the price). After payment the call returns a receipt, and `GET https://agi.apify.com/api-proxy/runs/{receipt}` returns the results. Swap in any Actor from the table, written as `johnvc~<actor-name>`.

Amounts, networks and limits are Apify's and can change: see [Apify's agent payments docs](https://docs.apify.com/agents/payments).

## Try it

- "Find 20 remote machine learning engineer jobs posted this week on LinkedIn and list the ones that state a salary."
- "What data analyst roles are on Google Jobs in Austin right now, and which companies post the most?"
- "Pull every open role on Anthropic's Ashby board and group them by team."

## Notes

- Each server exposes the Actor's input schema as the tool's parameters, so the agent can set keywords, locations, time windows and result caps itself. Set a cap when you want to bound spend.
- Results are the Actor's dataset rows as JSON.
- The Actors are built and maintained by [AlphaOSINT](https://alphaosint.com) and published on Apify as `johnvc`. Issues and questions: [this repo's issue tracker](https://github.com/johnisanerd/alphaosint-jobs-mcp/issues).

MIT License.
