# Posh Events Scraper: Posh Scraper API for Python & Node.js (2026)

Scrape posh.vip events by city, keyword or organizer: dates, venues, ticket prices, tickets sold and organizer emails. No login needed. Export JSON, CSV, Excel.

**[▶ Try the Posh Events Scraper free on Scrapely](https://scrape.ly/store/echofield/posh-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Posh data with the [Posh Events Scraper](https://scrape.ly/store/echofield/posh-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the posh scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Posh scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/posh-scraper) or from your code with the SDK.
- **Structured posh data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $5.10 per 1,000 event or organizer results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Posh changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Posh data can you extract?

Scrape posh.vip events by city, keyword or organizer: dates, venues, ticket prices, tickets sold and organizer emails. No login needed. Export JSON, CSV, Excel.

| Output field |
|---|
| `coverUrl` |
| `eventTitle` |
| `startDateTime` |
| `timezone` |
| `venueName` |
| `city` |
| `stateCode` |
| `lowestPrice` |
| `lowestTotalPrice` |
| `highestPrice` |
| `totalTicketsSold` |
| `attendingCount` |
| `organizerName` |
| `contactEmail` |
| `eventUrl` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/posh-scraper').call({"locations": ["Miami"], "maxEvents": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["RESIDENTIAL"], "scrapelyProxyCountry": "US"}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/posh-scraper').call(run_input={ "locations": [ "Miami" ], "maxEvents": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "RESIDENTIAL" ], "scrapelyProxyCountry": "US" } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~posh-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "locations": [
    "Miami"
  ],
  "maxEvents": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "RESIDENTIAL"
    ],
    "scrapelyProxyCountry": "US"
  }
}
```

See every input option on the [Posh Events Scraper page](https://scrape.ly/store/echofield/posh-scraper).

## Pricing

**$5.10 per 1,000 event or organizer results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/posh-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Posh with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Posh with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a posh scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~posh-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Posh legal?** This scraper collects publicly available data. Check Posh's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** posh events scraper, posh scraper, posh scraper api, posh scraper python, posh scraper node.js,
scrape posh, posh data extraction, posh crawler, posh api, export posh data to csv, posh-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/posh-scraper).
