# website scraping software: How to Pick the Right Tool for Your Project, What Credits Really Cost, and Where ScraperAPI Fits In

Searching for website scraping software usually means one of two things: you have data to pull and no idea which tool won't waste your money, or you already have scraper code that keeps getting blocked. The answer differs depending on which camp you're in, but for developers the short version is this: an API-based scraper like ScraperAPI handles proxies, retries, JavaScript rendering and CAPTCHAs through a single endpoint, starts at **$49/month**, and you can test it free for 7 days with 5,000 credits and no credit card. For non-developers, a visual tool makes more sense — and I'll cover that too.

The catch with API-based scrapers is that the sticker price tells you very little. A "100,000 credits" plan sounds generous until you learn that a JavaScript-rendered request burns 10 credits and a Google search costs 25. That math decides whether a plan is cheap or expensive for you, so this article spends most of its space on it.

> **Quick pick**
> - Write code, scrape mostly normal sites → ScraperAPI Hobby, $49/mo, 100,000 credits, 20 concurrent threads
> - Need 1M+ credits or US/EU geotargeting → Startup at $149/mo
> - Want to test before paying anything → 7-day trial, 5,000 credits, no credit card
> - Can't code at all → a visual tool like Browse AI or Octoparse fits better (details below)
>
> 👉 [Start the free 7-day trial and see current plan prices](https://www.scraperapi.com/?fp_ref=coupons)

## The three types of website scraping software (and which one you actually need)

Most "best web scraping tools" roundups mix three fundamentally different products, which is why they're confusing. Before comparing anything, figure out which category your job falls into:

1. **Scraping APIs** — ScraperAPI, ScrapingBee, and similar services. You send an HTTP request with your target URL; the service rotates proxies, renders JavaScript when asked, solves CAPTCHAs, and returns HTML or parsed JSON. You write the logic, they handle the infrastructure.
2. **Visual no-code tools** — Browse AI, Octoparse, ParseHub, Clura. Point-and-click scrapers that run in a browser or desktop app. Octoparse runs around $75/month, ParseHub $149/month for paid tiers, and Clura has a free tier with 20 scrapes per day. Good for spreadsheets and monitoring, limited for large-scale or heavily protected sites.
3. **Full platforms** — Apify, Bright Data. Marketplaces of ready-made scrapers, proxy networks, and dedicated unlocker products. Most powerful, heaviest to learn. Bright Data's enterprise-grade infrastructure generally runs $500+/month.

ScraperAPI sits deliberately in category 1. One review summed it up well: "This is a single-purpose tool, and that's a feature." There's no marketplace to dig through and no eight-product suite to learn — you call one endpoint and get a page back.

## ScraperAPI plans: the complete current lineup

ScraperAPI currently shows nine options on its pricing page, from a 7-day trial to custom enterprise deals. Every paid plan includes JavaScript rendering, premium proxies, automatic JSON parsing, CAPTCHA and anti-bot detection, custom headers and sessions, desktop/mobile user agents, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee. Paying annually cuts every tier by 10%.

| Plan | Monthly price | Annual (per month) | API credits | Threads | Get started |
| --- | --- | --- | --- | --- | --- |
| Free trial | $0, 7 days | — | 5,000 | 5 | [Start free trial](https://www.scraperapi.com/?fp_ref=coupons) |
| Free plan | $0 | — | 1,000 | 5 | [Sign up free](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [Check Hobby plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [Check Startup plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [Check Business plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [Check Scaling plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [Check Professional plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [Check Advanced plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [Contact sales](https://www.scraperapi.com/?fp_ref=coupons) |

A few differences don't fit in the table:

- **Geotargeting**: Hobby and Startup are limited to US & EU. Country-level targeting across the full 70-country list unlocks at Business and up.
- **Analytics history**: Hobby and Startup keep only 30 days of dashboard data. Business and above get unlimited history.
- **Overage options**: auto-upgrade (credits run out → account moves to the next plan automatically, opt-in) is available from Hobby through Professional. Pay-as-you-go (keep scraping at a fixed per-credit rate up to a monthly cap you set) starts at Scaling.

Credits don't roll over between months, so spiky workloads — say, one big crawl per quarter — pay for idle months in between. Annual plans can renew early for a fresh batch of credits if you need to reset.

👉 [Compare every plan side by side on the pricing page](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Credits are not requests — the math most reviews skip

This is the part that actually determines your cost, and it's where most comparison articles stop at the credit count.

ScraperAPI's pricing FAQ puts the rates plainly: a standard page costs 1 credit, Amazon costs 5, Google and Bing cost 25, and LinkedIn costs 30. Sites behind Cloudflare, DataDome, or PerimeterX add 10 credits per request when the bypass succeeds. On top of that, your own parameters multiply the cost:

| Request type | Credits per request |
| --- | --- |
| Plain GET (static HTML) | 1 |
| JS rendering (`render=true`) | 10 |
| Premium proxies (`premium=true`) | 10 |
| Premium + rendering | 25 |
| Ultra-premium proxies | 30 |
| Ultra-premium + rendering | 75 |

Run the numbers and the picture changes fast. A Startup plan's 1,000,000 credits is a million plain requests — but only 100,000 with JS rendering, or about 13,000 ultra-premium rendered fetches. One review's blunt version: "a '1 million credit' plan buys far fewer pages than it sounds."

Two things soften this. First, the dashboard has a Domain Cost Estimator that tells you the exact credit cost for any URL before you commit, and you can set a `max_cost` cap per scrape so a single request can't blow past your limit. Second, ScraperAPI bills only successful requests per its docs — internally retried failures don't cost you anything.

> If you plan to scrape mostly Google, LinkedIn, or heavily protected e-commerce sites, do the multiplier math before choosing a plan. The cheapest and most expensive realistic workloads can differ by ten times in cost per page on the same dollar figure.

## Where ScraperAPI genuinely fits — and where it doesn't

Honest answer: ScraperAPI is a clean, cheap way to scrape sites that don't fight back hard, and the wrong tool for heavily defended targets.

Independent benchmarks put its overall success rate around **62–64%** — one measured 72.57%, another around 62.8–63.7% — which is slightly above the roughly 58–59% industry average, but well short of what dedicated unlocker products achieve (Bright Data's Web Unlocker measured 95–98% in the same comparisons, at a higher price and steeper learning curve). On Cloudflare and DataDome pages specifically, users report outright 500 errors. If most of your target list is protected sites, reviewers call that a dealbreaker, and the benchmark numbers back them up.

Speed has a similar split. Simple pages come back in seconds; hard domains can take up to 60 seconds, which is why the official docs recommend a 70-second client timeout. Independent tests on Amazon, Idealista, and Glassdoor recorded 20–40 seconds per request. For batch jobs that's fine — there's an async API where you submit jobs and collect results later — but for time-sensitive scraping it's a real limitation.

One billing quirk worth knowing before you commit: reviews report that ScraperAPI occasionally returns a CAPTCHA page or error page as a "successful" response and bills a credit for it. The support team will refund mistakenly billed credits when you flag them, but you should spot-check your responses rather than assume every billed request was clean.

What developers consistently praise: the integration takes minutes (cURL, Python, Node, PHP, Ruby, Java — a few lines each), the structured endpoints for Amazon, Google, Walmart, and eBay return parsed JSON so you skip parser maintenance entirely, and the docs are thorough. The recurring complaint is exactly what you'd expect after the section above: rendering and premium requests burn through credit budgets 10x faster than people budget for.

## When a no-code tool beats an API

If you can't code and don't want to learn, ScraperAPI isn't for you — its whole model assumes you're making HTTP requests. The visual alternatives trade power for accessibility:

- **Browse AI** positions itself as AI-powered extraction and monitoring; point it at a page and it builds a scraper.
- **Octoparse** (~$75/mo) and **ParseHub** (~$149/mo) handle visual workflows with pagination and scheduling.
- **Clura** runs inside Chrome and exports visible page data to structured spreadsheets; the free tier gives 20 scrapes per day.

These tools cap out on scale and anti-bot work. If you eventually need millions of pages per month or protected targets, you end up in API territory anyway.

## How ScraperAPI's pricing compares to the alternatives

For context on the market: Firecrawl's developer-oriented plans start at $19/month (Hobby) up to $399/month (Growth); Oxylabs pricing starts around $0.50 per 1,000 results; Bright Data's platform-level tools generally run $500+/month. ScraperAPI's $49 entry point is among the lower ones for a managed API that includes JS rendering and premium proxies on every tier.

The fair comparison isn't the monthly price, though — it's cost per actual page. On plain HTML, ScraperAPI works out to roughly $0.10–0.15 per 1,000 pages from the Startup tier up, which is cheap by any standard. Rendered and protected pages cost 10–30 times that, which is where the "expensive" reputation comes from. Neither number is wrong; they just describe different workloads.

## FAQ

**Is there a free version of ScraperAPI?**
Yes. There's a permanent free plan with 1,000 credits per month and 5 concurrent connections, plus a 7-day trial with 5,000 credits that requires no credit card. The free tier is enough to test the API, not to run a real workload.

**How many requests is 100,000 credits?**
It depends entirely on your targets and parameters: 100,000 plain static-page requests, about 10,000 with JavaScript rendering, roughly 4,000 Amazon product pages, or around 1,300 Google searches. Use the dashboard's Domain Cost Estimator on your actual URLs before committing to a plan.

**Can ScraperAPI get past Cloudflare?**
Not reliably. It adds 10 credits per request when the bypass succeeds on Cloudflare, DataDome, or PerimeterX sites, but independent benchmarks put overall success around 62–64%, and users report 500 errors on protected targets. If your workload is mostly protected pages, a dedicated unlocker product is the safer bet.

**What happens when I run out of credits?**
By default, scraping pauses until your credits renew. You can opt into auto-upgrade (from Hobby up), which moves you to the next plan automatically, or — from Scaling up — pay-as-you-go at a fixed per-credit rate up to a monthly cap you set. Exceeding your concurrency limit returns a 429 with no charge.

**Do I need to know how to code?**
For ScraperAPI, yes — basic HTTP requests at minimum. If you want scheduled, no-code workflows, its DataPipeline offers a low-code UI with webhook delivery, but you're still working with an API key and parameters. Pure no-code users should look at the visual tools mentioned earlier.

## Which plan should you actually pick

Match your workload to a tier instead of guessing from credit counts:

- **Just evaluating or running a small side project** → stay on the free plan or 7-day trial. 1,000 monthly credits is 1,000 static pages; enough to validate your targets before spending anything.
- **Personal projects or light monitoring on mostly static sites** → Hobby at $49/month ($44.10 annually) covers 100,000 credits, which is plenty for 1-credit workloads.
- **Production scraping at moderate volume, all in the US/EU** → Startup at $149/month. One million credits handles real projects, and the 50 threads keep batches moving.
- **Need country-level geotargeting, unlimited analytics history, or 3M+ credits** → Business at $299/month. This is the step where the geographic and reporting limits disappear.
- **Rendering-heavy workloads near a plan's edge** → watch the Startup-to-Business gap. If your estimated usage lands within 10–20% of a plan limit, remember there's no overage below Scaling — you'd jump from $149 to $299 for a slight overrun. Turning `max_cost` on and reserving rendering for pages that actually need it is usually cheaper than upgrading.
- **Mostly Cloudflare/DataDome targets, or need 95%+ success on hard sites** → ScraperAPI is the wrong fit; a dedicated unlocker will serve you better even at higher cost.

One last check before you buy: run two or three of your real target URLs through the Domain Cost Estimator with the exact parameters you plan to use. The number it shows — multiplied by your monthly volume — is your true cost. Everything else is marketing.

👉 [Test your targets free for 7 days on ScraperAPI](https://www.scraperapi.com/?fp_ref=coupons)
