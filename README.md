# PubMed Scraper — MCP Server

Search PubMed — the U.S. National Library of Medicine's biomedical literature index — from your AI agent or MCP client, through NCBI's official E-utilities. Literature checks, evidence scans, and citation gathering, returned as structured records.

This repo is the MCP listing for the [PubMed Scraper](https://apify.com/magnova/pubmed-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--pubmed-scraper** — Search PubMed by term with an optional published-since window and only-new monitoring mode. Returns structured article records: title, authors, journal, publication date, abstract where available, and PMID / DOI identifiers.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/pubmed-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "pubmed-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/pubmed-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "pubmed-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/pubmed-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/pubmed-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.002 per article fetched — $2 per 1,000 articles**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/pubmed-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/pubmed-scraper

*Article records come from PubMed via NCBI's official E-utilities.*
