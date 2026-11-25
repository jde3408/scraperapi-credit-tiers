# Free Web Scraping API: What 1,000 Credits Really Buy, Do You Need a Card, and When ScraperAPI's $49 Plan Starts to Make Sense (All 7 Tiers Compared)

ScraperAPI's free plan gives you **1,000 API credits per month** with a maximum of **5 concurrent connections**, and the first seven days after signup come with **5,000 credits** so you can test at a larger scale. Neither step asks for a credit card. The number that decides everything else is the per-request price: a standard page costs 1 credit, a JavaScript-rendered request costs 10, and premium proxies plus rendering costs 25. Your standing monthly allowance is therefore 100 rendered pages, not 1,000.

Paid plans start at **$49/month** for Hobby, which carries 100,000 credits and 20 threads. If your project needs more than a hundred rendered pages a month, you are already past the free tier, and the useful question becomes which of the seven paid tiers you actually need. Below: every plan with verified pricing, the credit arithmetic done for you, the limits that only appear in the billing docs, and how the free tiers at Geekflare, Context.dev and Webfetch compare.

> **Most small teams either stay on the free plan or go straight to Hobby at $49/month** (100,000 credits, 20 threads). The free plan is for evaluation and static-page jobs; the 7-day 5,000-credit trial is where you find out whether your targets need rendering. 👉 [Check ScraperAPI's current plans and free-tier limits](https://scraperapi.com/pricing?fp_ref=coupons)

## All ScraperAPI plans, verified

Annual billing is exactly 10% off monthly across every tier, so the yearly column shows the effective monthly rate.

| Plan | Credits / month | Concurrent threads | Price | Start here |
| --- | --- | --- | --- | --- |
| Free | 1,000 | 5 | $0 | [Create a free account](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Hobby | 100,000 | 20 | **$49/mo**, or $44.10/mo billed yearly | [See the Hobby plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Startup | 1,000,000 | 50 | **$149/mo**, or $134.10/mo billed yearly | [See the Startup plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Business | 3,000,000 | 100 | **$299/mo**, or $269.10/mo billed yearly | [See the Business plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Scaling (most popular) | 5,000,000 | 200 | **$475/mo**, or $427.50/mo billed yearly | [See the Scaling plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Professional | 10,500,000 | 300 | **$975/mo**, or $877.50/mo billed yearly | [See the Professional plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | 21,500,000 | 500 | **$1,975/mo**, or $1,777.50/mo billed yearly | [See the Advanced plan](https://scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | 22,000,000+ | 500+ | Custom quote | [Request Enterprise pricing](https://scraperapi.com/pricing?fp_ref=coupons) |

The tiers differ in more than volume, and two of these differences bite before you expect them to.

| Plan | Geotargeting | Analytics history | Pay-as-you-go | Support |
| --- | --- | --- | --- | --- |
| Hobby | US and EU only | Up to 30 days | No | Standard |
| Startup | US and EU only | Up to 30 days | No | Standard |
| Business | Country-level, global | Unlimited | No | Standard |
| Scaling | Country-level, global | Unlimited | Yes | Standard |
| Professional | Country-level, global | Unlimited | Yes | Priority support |
| Advanced | Country-level, global | Unlimited | Yes | Priority routing |
| Enterprise | Country-level, global | Unlimited | Yes | Dedicated team, Slack |

Country-level targeting starts at Business ($299/month). Hobby and Startup are limited to US and EU exits, which matters if your data is priced or worded differently per market. Selection and routing themselves cost nothing extra; it is the plan gate that bites.

## What a credit buys, request by request

| Request type | Credits per request |
| --- | --- |
| Standard page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google and Bing, including subdomains | 25 |
| LinkedIn | 30 |
| JavaScript rendering (`render=true`) | 10 |
| Premium proxies (`premium=true`) | 10 |
| Screenshot (`screenshot=true`) | 10 |
| Premium proxies plus JavaScript rendering | 25 |
| Anti-bot bypass (Cloudflare, DataDome, PerimeterX, Akamai) | +10 on top of the base cost |
| Ultra premium (`ultra_premium=true`, paid plans only) | 30 |
| Ultra premium plus rendering (paid plans only) | 75 |
| Geotargeting, sessions, device type, output format, auto parsing | No extra cost |

Run the free plan's 1,000 credits through that table and the "1,000 free pages" claim falls apart in a useful way:

- **1,000** plain static pages
- **200** Amazon or Walmart pages at 5 credits
- **100** rendered pages at 10 credits
- **40** pages through premium proxies with rendering at 25 credits
- **33** LinkedIn profile or company pages at 30 credits
- **about 90** pages behind Cloudflare once the automatic bypass surcharge lands (1 + 10)

The bypass surcharge is the one that surprises people, because you do not opt into it. ScraperAPI applies it when its own logic decides the target needs bypassing, not when you set a parameter. A job that looks like 1,000 pages on paper can bill as 90.

Two habits keep this predictable. Every response carries the actual cost in the `sa-credit-cost` header, and the Domain Cost Estimator in the dashboard prices any URL before you send a request. You can also set `max_cost` per scrape so a single call cannot run past your ceiling.

Hauling this into paid territory: Hobby's 100,000 credits work out to **$0.49 per 1,000 standard pages** or **$4.90 per 1,000 rendered pages**. 👉 [Start with the 7-day, 5,000-credit trial before paying for anything](https://www.scraperapi.com/signup?fp_ref=coupons)

## Free-tier limits that never make the headline

**Five concurrent connections** is the hard ceiling on the free plan, against 20 on Hobby and 500 on Advanced. Exceed it and you get a 429 telling you to bring concurrency back inside the limit. The request is turned away rather than queued, and you are not charged for it.

**Credits reset on your monthly renewal date and unused credits are lost.** Nothing carries forward, so a quiet month on the free plan is a quiet month, not a saved budget.

**Ultra premium requests are paid-plan only.** That is the 30-credit and 75-credit rows in the table above; on the free plan they are simply unavailable.

**The trial is 7 days, not 30.** You get 5,000 credits in that window, which is five times the monthly allowance and enough to profile a real target list. After day seven you drop to 1,000 credits a month with 5 threads.

**Refunds are 7 days, no questions asked,** and you can cancel from the dashboard at any time without a cancellation charge. On paid tiers, running out of credits pauses scraping by default. Auto-upgrade, which moves you up a tier when credits exhaust, is opt-in and available on Hobby through Professional; pay-as-you-go at a fixed per-credit rate, with a spending cap you set, is available from Scaling upward. The spending cap is a limit, not a prepayment, and the account will not exceed it unless you change the setting.

## How the free tiers compare elsewhere

| Provider | Free allowance | Card required | JS rendering cost | Cheapest paid tier |
| --- | --- | --- | --- | --- |
| ScraperAPI | 1,000 credits/mo, plus 5,000 for the first 7 days | No | 10 credits/request | $49/mo for 100,000 credits |
| Geekflare | 500 credits/mo, 1 req/s, 7-day logs | No | Included in 1 credit | $19/mo for 10,000 credits |
| Context.dev | 1,000 credits/mo | No | Included; 1 credit per standard scrape | $19/mo for 7,500 credits |
| Webfetch | 1,000 on signup, then 250/mo, bankable to 1,000 | No | 5 credits/request | $11.99/mo for 75,000 credits |

The pricing models are genuinely different, and the difference decides small projects. Geekflare charges 1 credit per request whether or not it renders JavaScript, with CAPTCHA solving and anti-bot bypass included; routing through a proxy adds 4 credits and its AI extraction adds 6. Failed requests cost nothing there, and its Growth tier at $69/month for 100,000 credits works out to about $0.69 per 1,000 pages by its own arithmetic, or $58/month billed yearly.

Context.dev puts every request through a real browser at 1 credit, which means its 1,000 monthly free credits are 1,000 rendered pages rather than 100. It also handles PDFs, returns Markdown, HTML, screenshots or schema-defined JSON in one call, and accepts batches of up to 100,000 URLs per job.

Webfetch uses a five-step ladder of 1, 5, 10, 25 and 75 credits for raw, rendered, premium proxy, premium plus rendering, and stealth pool requests, and climbs it automatically only when the target refuses. It states that failed fetches are never billed, caps downloads at 5MB through the stealth pool and 25MB elsewhere, and blocks banks, payment processors and some government sites outright with a 403 that costs nothing. Its free allowance keeps refilling at 250 credits a month after the first 1,000 rather than expiring as a trial.

Read against ScraperAPI, the honest summary is this: ScraperAPI's free tier is the most generous one-time allowance here (5,000 credits in week one) but the stingiest steady-state allowance for rendered work, since rendering costs 10 credits where two competitors charge 1. Its paid ladder runs far higher than anyone else's, to 22 million credits and 500 threads, and country-level geotargeting from $299 a month is a real differentiator for multi-market data.

## Which plan fits which job

**A one-off script pulling a few hundred static pages.** Free plan, 1,000 credits a month, no card. You will not exhaust it and you do not need support.

**A recurring monitor on pages that need JavaScript.** 1,000 free credits is roughly 100 rendered checks a month, about three a day. Hobby at $49 buys 10,000 rendered pages, which is 330 a day. If you only need a few hundred rendered pages monthly and nothing else, Geekflare's 500-credit free tier covers it at 1 credit per render.

**Feeding a RAG pipeline or vector store.** Output format costs nothing extra on ScraperAPI, so Markdown, HTML, JSON or text all pull from the same credit. Token bills are the other half of this decision: one provider measured Markdown output at 15.2% of the HTML's size across 8 documentation, blog and index pages on October 20, 2026, which is the difference between a corpus you can afford to embed and one you cannot. If your corpus is mostly PDFs and large batches, Context.dev's 100,000-URL jobs are built for that shape of work.

**Multi-market pricing or content monitoring.** Country-level geotargeting starts at Business, **$299/month** for 3,000,000 credits and 100 threads. Nothing below it routes outside the US and EU.

**Sustained volume past 5 million credits.** Scaling at **$475/month** is the first tier with pay-as-you-go, so a spike does not force a plan change. Professional at $975 adds priority support and 300 threads; Advanced at $1,975 adds priority routing and 500 threads.

## Questions that come up before signing up

**Do I need a credit card for the free plan?** No. The 7-day, 5,000-credit trial and the 1,000-credit monthly plan both start without payment details.

**How many credits does JavaScript rendering cost?** 10 per request on ScraperAPI. Rendering plus premium proxies is 25. Compare that with providers that fold rendering into a single credit before you assume the free tiers are equivalent.

**What happens when credits run out mid-month?** Scraping pauses until renewal. Auto-upgrade is opt-in on Hobby through Professional and moves you up a tier automatically; pay-as-you-go with a monthly cap you set is available from Scaling upward. Neither happens unless you turn it on.

**Can I get Markdown only?** Yes, and output format carries no credit surcharge. Auto parsing and structured output are also listed as free of charge.

**Is there a refund?** Seven days, no questions asked, on top of the seven-day trial.

**Do unused credits roll over?** No. They reset at each renewal date.

## Before you enter a card

Two things are worth confirming with support rather than assuming. First, whether a failed request still consumes credits: ScraperAPI's plans and billing documentation do not spell this out, while Geekflare and Webfetch both state explicitly that failures are not billed. If your targets are flaky or heavily protected, that policy can move your effective cost more than the plan price does.

Second, check that auto-upgrade is off if a surprise tier change would bother you. It is opt-in, but it is the mechanism that turns a 100,000-credit month into a 1,000,000-credit bill.

The decision itself is narrow. Under 1,000 static pages a month, or under roughly 100 rendered ones: stay on the free plan. Past that, Hobby at **$49/month** covers 10,000 rendered pages and 20 threads, and annual billing takes 10% off if you already know you are staying. Country-level targeting or pay-as-you-go moves you to Business or Scaling and no lower.

👉 [Compare all seven ScraperAPI tiers and pick the one that matches your monthly page count](https://scraperapi.com/pricing?fp_ref=coupons)
