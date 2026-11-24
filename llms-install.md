# Installing AlphaOSINT Jobs MCP in Cline

These are remote MCP servers hosted by Apify. Nothing is installed or run locally.

1. Ask the user for an Apify API token. They can create one at https://console.apify.com/settings/integrations (the free plan includes $5 of monthly credit).
2. Add the servers the user wants to `cline_mcp_settings.json`. All six:

```json
{
  "mcpServers": {
    "linkedin-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/linkedin-jobs-api",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    },
    "google-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/Google-Jobs-Scraper",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    },
    "wellfound-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/wellfound-jobs-api",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    },
    "ashby-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/ashby-job-board-scraper",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    },
    "successfactors-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/sap-successfactors-jobs-api",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    },
    "isolved-jobs": {
      "type": "streamableHttp",
      "url": "https://mcp.apify.com/?tools=call-actor,fetch-actor-details,johnvc/isolved-jobs-api",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    }
  }
}
```

3. Replace `<APIFY_TOKEN>` with the user's token in each entry. If the user only wants some of the job sources, leave the others out.
4. Check the install by asking a server for a few results, for example LinkedIn jobs for "data analyst" in "Austin" with a small result cap. Each server's tool takes the Actor's input fields as parameters, so set a cap to bound spend.
