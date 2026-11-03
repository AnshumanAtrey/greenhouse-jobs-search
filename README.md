# Greenhouse Jobs Scraper & API - All Companies, Last 24 Hours

Greenhouse jobs scraper and API: search every company's job board on Greenhouse (boards.greenhouse.io and job-boards.greenhouse.io) at once, live, and get each job's title, company, location, remote or onsite, job type, salary range, first-published date, deadline and link, newest first. Turn on full details for the description, the department, the company's reference number and pay as numbers.

Use it as a Greenhouse jobs API with no Greenhouse API key, a Greenhouse job board scraper or a daily job feed from the Apify Console, the Apify API, Python, JavaScript, n8n, Make or an AI agent, and export JSON, CSV or Excel. It is the `site:boards.greenhouse.io` Google dork done at the source, with the fields a search result cannot give you. Available as an [Apify Actor](https://apify.com/anshumanatrey/greenhouse-jobs-search). $0.0018 per job, $0.0019 with full details, $0.01 per run start at the default memory, no login, no API key.

## What does it do?

- **Searches 8,357 Greenhouse job boards of 8,317 companies at once.** On 2026-11-02 they held 216,033 open jobs at 7,201 companies, at employers such as SpaceX, Anduril, Databricks, Stripe, Anthropic, Cloudflare, Datadog, Coinbase, GitLab, Airbnb, Reddit and Figma.
- **Pay on the plain row.** When a company publishes pay, 22% of the jobs, it comes with every row at no extra price, every pay zone included.
- **One keyword is enough.** Type a job title and press Start. Leave the form empty for the newest jobs of every kind.
- **Newest first, read live.** Every job comes from Greenhouse at the moment of your run, sorted by the date the company first published it.
- **Filters that take what people type.** London, Germany, EMEA, Remote, contract, last 24 hours, or a pasted Google dork such as `site:boards.greenhouse.io intext:engineer`.
- **Checks job links.** Paste links, including the career pages of companies on the list with `?gh_jid=`, and each comes back open, closed or not found.

## How is it different from other Greenhouse scrapers?

- **Every company, read live.** Greenhouse publishes no list of its customers, so a live reader normally needs a board name or link from you, and most actors that search every company read a stored copy. This one carries a list of 8,357 boards built from public job APIs, Common Crawl, the Wayback Machine and GitHub lists, and reads all of them at the moment of your run. Of the 13 most used actors that cover Greenhouse (the table below), 4 need board names, links or a curated preset list, 8 search a stored copy, and one other reads live: yugenox/ats-jobs-search, across Greenhouse, Lever and Ashby.
- **The real posting date.** Greenhouse keeps two dates for a job: when it was first published and when it was last edited, and most jobs are edited long after they go up. In the 24 hours before 14:25 UTC on 2026-11-02, 952 jobs were first published, while 6,692 carried an edit from that day, so a last-24-hours filter on the edit date lists five to seven times the jobs that are really new (5.6 times in a sample of 2,000 boards at 18:29 UTC the same day). This actor uses the first-published date, the one Greenhouse's own board pages use for their New tag (1,482 of 1,482 jobs checked).
- **Every pay range.** Companies that pay by place publish one range per zone or country, and the row keeps all of them, in each currency (1,986 jobs show more than one).
- **Links from anywhere on Greenhouse.** Old and new board addresses, the EU boards, embed links, the API's own links and the career pages of companies on the list with `?gh_jid=` all read as the same job.
- **You pay for what you get.** One charge per delivered row, plus the run start, and a spending limit stops the run cleanly with the jobs it paid for.

## When should I use it?

- **Job seekers and job boards:** new jobs by title, country and date across thousands of tech companies, with pay where it is published, on a daily schedule.
- **Recruiters and sourcing teams:** see who is hiring for a role right now, anywhere on Greenhouse, and at what pay.
- **Sales and market research:** companies hiring for a function, by country and date, as a buying signal, and a list of the companies that hire through Greenhouse.
- **Data teams and AI agents:** one clean, stable feed of Greenhouse jobs through the API or MCP.

## How much does it cost to scrape Greenhouse jobs?

Pay per event: $1.80 per 1,000 jobs, or $1.90 per 1,000 with full details, plus $0.01 per run at the default 1 GB of memory. Apify's free $5 monthly credit covers about 2,600 jobs in runs of 100. Platform usage is included, and there is no monthly fee.

| Event | Price | When it is charged |
|---|---|---|
| Job | $0.0018 | One saved job, and one checked link that is closed or not found |
| Job with details | $0.0019 | One saved job with full details on |
| Run start | $0.01 per GB of memory | Charged by Apify when a run starts: once up to 1 GB and once more for each extra GB, so $0.01 at the default 1 GB |

On paid Apify plans the job prices are 10% less on Scale ($0.00162 and $0.00171) and 20% less on Business and above ($0.00144 and $0.00152); the run start stays $0.01 per GB. The Store page shows that Business price, from $1.44 per 1,000 jobs, and leaves the run start out.

| Run (Free and Starter price, default memory) | Cost |
|---|---|
| 100 newest jobs | $0.19 |
| 100 jobs with full details | $0.20 |
| 1,000 jobs | $1.81 |
| Every open Anthropic job, 677 on 2026-11-02 | $1.23 |
| Every job on the list, 216,033 on 2026-11-02 | $388.87 |

Why a run start: Greenhouse has no search, so every search reads all 8,357 job boards whatever it finds, and the run start pays for that read. Number of jobs (`maxJobs`) and the run start set the most a run can cost, and a run stops at its spending limit with a message saying so.

## How does the price compare with other Greenhouse scrapers?

Every actor on the Apify Store that names Greenhouse in its title, slug or description and had 60 or more users in the last 30 days, found by searching the Store for 13 Greenhouse terms and 33 job terms on 2026-11-02 (4,956 actors read), ordered by users. Free-plan prices from each actor's current pricing.

| Actor | Users, 30 days | Per job | Start fee | Input |
|---|---|---|---|---|
| fantastic-jobs/career-site-job-listing-api | 1,632 | $0.012 | $0.01 | Keyword, from its own database of 58 ATS |
| fantastic-jobs/career-site-job-listing-feed | 282 | $0.0025 | $0.10 | The same database as a feed |
| fantastic-jobs/greenhouse-jobs-api | 156 | $0.002 | none | Keyword, from its own database of Greenhouse jobs |
| hirebase/job-search | 137 | $0.005 | $0.001 | Keyword, from its own database of 20+ ATS |
| jobo.world/ats-jobs-api | 134 | $0.004 | $0.00005 | Keyword, from its own database of 75+ ATS |
| bovi/greenhouse-lever-ashby-job-scraper | 100 | $0.0015 | $0.00005 | Company names or preset lists |
| factpipe/ats-jobs-feed | 98 | $0.003, $0.005 from 2026-11-06 | none | Keyword, from its feed of 19,000+ companies |
| yugenox/ats-jobs-search | 86 | $0.002 | none | Keyword across Greenhouse, Lever and Ashby boards, live |
| memo23/career-site-ats-jobs-api | 81 | $0.004 | $0.03 | Board links or company names, live |
| bytepulselabs/greenhouse-job-scraper | 70 | $0.002 | none | Board links |
| glitchbound/ats-jobs-scraper | 63 | $0.003 | $0.00005 | Company names or domains |
| jobspipe/jobspipe-job-search | 61 | $0.00196 | none | Keyword, from its daily index of 30+ job boards |
| jtpalms/ats-jobs-index | 60 | $0.003 | $0.00005 | Keyword, from its index refreshed twice a day |
| This actor | new | $0.0018, $0.0019 with details | $0.01 per GB, $0.01 at 1 GB | One keyword, all 8,357 boards, live |

Where others are cheaper: bovi costs $0.0015 a job, and a little less on paid plans, when you already know the companies or use its curated preset lists. fantastic-jobs/greenhouse-jobs-api, yugenox/ats-jobs-search and bytepulselabs/greenhouse-job-scraper cost $0.002 a job with no start fee, so on the free plan they cost less than this actor for runs under 50 jobs (under 100 with full details): 10 jobs cost $0.02 there and $0.028 here. On paid plans several drop below this actor's $0.00162 on Scale and $0.00144 on Business: fantastic-jobs/greenhouse-jobs-api costs $0.0012 on both, bytepulselabs/greenhouse-job-scraper $0.0016 and $0.0014 (and $0.0018 on Starter, the same per job as here, with no start fee), jobo.world/ats-jobs-api $0.0013 on Business, and fantastic-jobs/career-site-job-listing-feed $0.0012 and $0.0008 plus a $0.001 start fee. Where others do more: the database actors add fields extracted by AI and LinkedIn company data, and the multi-ATS ones cover many platforms in one run.

## Which inputs does it take?

Nothing is required. Type a job title and press Start, or press Start with the form empty.

| Field | What it does |
|---|---|
| Job titles to find (`searchTerms`) | One per line. A job matches when its title has every word: frontend also finds Front-End. A pasted Google dork or Greenhouse link works too |
| Where the job is (`location`) | A city, state, country or region: London, Germany, EMEA, LatAm, TX. Worldwide finds jobs open everywhere, and Remote asks for remote jobs |
| Remote or onsite (`workType`) | remote, hybrid or onsite, from the company's own job fields, else from Remote, Hybrid or On-site in the location, or Remote or Hybrid in the title |
| Posted in the last (`postedWithin`) | 24 hours, 3 days, 7 days, 30 days, any time, or your own period such as 48 hours |
| Number of jobs (`maxJobs`) | How many, newest first: 100 by default, 0 for every match |
| Full details (`includeDetails`) | Adds the description as text and HTML, the department, the reference number and pay as numbers with its currency |
| Leave out words (`excludeTerms`) | Drops jobs whose title has these words, such as senior or intern |
| Job type (`employmentType`) | full-time, part-time, contract, intern or temporary, where the company states it |
| Match descriptions (`searchDescriptions`) | Finds your words in the description too, not only the title |
| Only these companies (`companies`) | A name (Stripe), the name in the address (stripe) or a Greenhouse link. Empty searches everyone |
| Job links to check (`jobUrls`) | Paste job links to check whether they are still open, instead of searching |

Example input:

```json
{
  "searchTerms": ["software engineer"],
  "location": ["London", "Germany"],
  "postedWithin": "7 days",
  "maxJobs": 100
}
```

## What does the output look like?

One row per job, newest first. These rows are from the example run of the deployed build (1.0.1) at the default 1 GB on 2026-11-03, run j96er5Rmn9tfQUkCt: software engineer across every board, 8,784 jobs at 1,554 companies, the 100 newest saved in 185 s.

| Job title (`title`) | Company name (`company`) | Main location (`location`) | Remote or onsite (`workType`) | Pay summary (`salary`) | Posted on (`postedAt`) |
|---|---|---|---|---|---|
| Staff Software Engineer, Fullstack (Card Experiences) | Affirm | Remote Canada | remote |  | 2026-11-03 |
| Senior Software Quality Assurance Engineer and Tester | Accenture Federal Services | Augusta, GA | onsite | USD 89,000 - 170,200 | 2026-11-02 |
| Staff Software Engineer, Tech Foundations | Airbnb | United States | remote | USD 212,000 - 265,000 | 2026-11-02 |
| Senior Software Engineer in Test, Android | Okta | Toronto, Ontario, Canada |  | CAD 118,000 - 162,000 | 2026-11-02 |
| Software Engineer, Compute | Vercel | Hybrid - San Francisco | hybrid |  | 2026-11-02 |

One row as JSON:

```json
{
  "title": "Staff Software Engineer, Tech Foundations",
  "company": "Airbnb",
  "location": "United States",
  "otherLocations": [],
  "workType": "remote",
  "employmentType": null,
  "department": null,
  "salary": "USD 212,000 - 265,000",
  "postedAt": "2026-11-02T19:03:07Z",
  "expiresAt": null,
  "jobUrl": "https://careers.airbnb.com/positions/8334372?gh_jid=8334372",
  "applyUrl": "https://careers.airbnb.com/positions/8334372?gh_jid=8334372",
  "status": "open",
  "platform": "greenhouse",
  "companySlug": "airbnb",
  "companyWebsite": "https://careers.airbnb.com",
  "jobId": "8334372",
  "checkedAt": "2026-11-03T09:02:52+00:00"
}
```

Full details fill `department` and add `description`, `descriptionHtml`, `reference`, `salaryMin`, `salaryMax` and `salaryCurrency`. A checked link that is closed or not found comes back with its `status`, company and link, and the other fields empty. A run also writes an `OUTPUT` record: how many job boards were read, how many jobs matched and were saved, the boards that could not be read, and any notes on how your input was read.

## How fast is it?

About 3 minutes at the default 1 GB of memory, and under 2 minutes at 2 GB. On the deployed build (1.0.1) on 2026-11-03, the empty form took 216 s at 1 GB (run bHR94LfwZ6KKoD9gc) and a search for software engineer 185 s (run j96er5Rmn9tfQUkCt); at 2 GB the same search took 119 s (run YSm3LERZBfd6xSvio), with a run start of $0.02 instead of $0.01. Greenhouse has no search, paging or order, so every search reads all 8,357 boards, one call each, and a keyword takes about as long as the empty form. Naming companies or checking links reads only those boards. Matching descriptions downloads every description, so it is slower.

## Common questions

### Which posting date does it use?

The moment the company first published the job. Greenhouse also keeps the time of the last edit, which moves whenever a job is touched: on 2026-11-02, 70% of open jobs had been edited more than a week after they went up. This actor sorts and filters by the first-published date, the date Greenhouse's own board pages use for their New tag, so last 24 hours means new jobs, not old ones that were edited.

### Why does a keyword search take as long as an empty form?

Greenhouse's job board API answers with every open job of one board, with no search, paging or order. So every search reads all 8,357 boards, one call each, and matches your words itself. Naming companies in Only these companies reads only those boards, which is much faster.

### Why does United States miss some US jobs?

Greenhouse keeps a job's location as the text the company typed, with no country field. On 2026-11-02, 59,614 jobs (28%) gave a US city and state code, such as Austin, TX, and no country, and United States found only 47 of them. Add the city or the state code to the places you type: TX also finds Texas. Two-letter codes that are also countries, such as CA, IN and GA, find both the state and the country (Canada, India, Gabon).

### Why do some jobs show several pay ranges?

Companies that pay by location publish one range per zone or country, and the row keeps all of them, joined with a semicolon: EUR 70,000 - 110,000; EUR 85,000 - 110,000; PLN 250,000 - 480,000 is one real row. Greenhouse stores amounts and a currency with no period, and hourly and yearly pay both occur, so read the amount with the job. With full details on, `salaryMin` and `salaryMax` are the lowest and highest amounts in the first range's currency.

### How does it find every company?

Greenhouse has no public list of its customers, so the list is built the way the `site:boards.greenhouse.io` dork works, from the web's own memory: freehire's public job API, Common Crawl's index, the Wayback Machine, and public company and job lists on GitHub gave 15,747 candidate names, and 23,941 names from other job platforms' company lists were tried as well. 32,663 of the 39,688 were checked live with Greenhouse's API; the other 7,025 guessed names were refused while Greenhouse blocked the address, and 54 of them checked later were all missing. 8,357 boards answered on 2026-11-02, 7,233 of them with open jobs, after 21 sandbox and test boards were left out. An estimate from how often the sources overlap puts the hiring boards on Greenhouse at 8,477 or more, so the list holds at most about 85% of them. To search a company that is not on the list, paste its link or type its name into Only these companies.

### Does it need a login or an API key?

No. Greenhouse's Job Board API is public: it serves what each company's job board shows any visitor. Greenhouse's other APIs need a customer's own key and read only that customer's data. You need only an Apify account.

### Does it work on Apify's free plan?

Yes. Apify's free $5 monthly credit pays for about 2,600 jobs in runs of 100, at $0.19 a run with the run start.

### How often should I run it?

Once a day keeps a feed fresh: set Posted in the last (`postedWithin`) to 24 hours and Number of jobs (`maxJobs`) to 0 to get every job first published that day, 952 in the 24 hours before 14:25 UTC on 2026-11-02, about $1.72 a run. Set the run up under Schedules in Apify Console, and match rows on `jobId` to skip jobs you already have.

### How do I get every job of one company?

Type its name in Only these companies (`companies`), such as Anthropic, or paste its Greenhouse link, and set Number of jobs (`maxJobs`) to 0. Only that board is read, so the run is much faster than a search of every board: every open Anthropic job, 677 on 2026-11-02, comes to $1.23.

### How do I check a list of job links?

Paste the links into Job links to check (`jobUrls`), one per line, instead of searching. Links on boards.greenhouse.io, job-boards.greenhouse.io, the EU boards, embed links and the career pages of companies on the list with `?gh_jid=` all work. Each link comes back as one row, open with the job's fields, or closed or not found with its link, so 10 links come to $0.028 with the run start.

### How do I call it from the API, Python, JavaScript, n8n or an AI agent?

Each way uses your Apify token (Apify Console, Settings, API & Integrations) and takes the input as JSON, with the field names above.

**API.** One call runs the actor and returns its rows. Apify stops that wait after 300 seconds: a search of every board takes about 3 minutes, inside the limit, but for every job (`maxJobs` 0) or a description search, use a client below, which waits until the run ends.

```bash
curl -X POST "https://api.apify.com/v2/acts/anshumanatrey~greenhouse-jobs-search/run-sync-get-dataset-items" \
  -H "Authorization: Bearer <YOUR_APIFY_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{"searchTerms": ["software engineer"]}'
```

**Python** (`pip install apify-client`):

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("anshumanatrey/greenhouse-jobs-search").call(run_input={"searchTerms": ["software engineer"]})
for row in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(row["title"], row["company"], row["location"], row["salary"], row["jobUrl"])
```

**JavaScript** (`npm install apify-client`):

```js
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: '<YOUR_APIFY_TOKEN>' });
const run = await client.actor('anshumanatrey/greenhouse-jobs-search').call({ searchTerms: ['software engineer'] });
const { items } = await client.dataset(run.defaultDatasetId).listItems();
for (const row of items) console.log(row.title, row.company, row.location, row.salary, row.jobUrl);
```

**n8n and Make.** In n8n, add the Apify node, pick Run an Actor and get dataset, choose this actor and paste the input JSON: the rows come out as n8n items. In Make, the Apify app's Run an Actor and Get Dataset Items modules do the same.

**AI agents (MCP).** Add `https://mcp.apify.com?tools=anshumanatrey/greenhouse-jobs-search` to your MCP client and sign in with Apify, or send `Authorization: Bearer <YOUR_APIFY_TOKEN>`. The agent gets this actor as a tool and sees every input field by its JSON key.

### Am I charged for closed jobs?

A search returns open jobs only. A pasted link that turns out closed or not found is one Job row, because it was checked and answered.

### Is it legal to use?

It reads public job postings. You are responsible for how you use the data, including each site's terms and the privacy laws that apply to you.

## Limitations

- Locations are free text with no country field: 28% of jobs give only a US city and state, which a United States filter misses (see above).
- Work type and job type exist only when a company states them: in its own job fields, or for work type in the location (Remote, Hybrid, On-site) or the title (Remote, Hybrid). On 2026-11-02, 18.9% of jobs had a work type and 18.0% a job type, and a filter on either leaves out the rest.
- Pay is on 22% of jobs, has no period, and several zones are joined in one text.
- The department comes with full details, a checked link or a description search; the reference number and the description come only with full details, which reads each saved job once more.
- Greenhouse answers a closed job and a job ID that never existed the same way, so both come back closed.
- Company career-site links (`?gh_jid=`) are read for the 990 companies on the list whose jobs link to their own site; other career sites and grnh.se short links are not.
- Every search reads every board, so a keyword takes about as long as the empty form, and every run pays the run start.
- Greenhouse blocks an address that makes too many calls for a while. If it refuses the run's address, the run waits up to 3 minutes per board for the block to lift, says in its message how many boards could not be read and lists them in the `OUTPUT` record; when no board could be read, the run fails with that reason.
- A job a company posts twice at the same place is delivered once (7,477 such copies on 2026-11-02).
- 45 boards are named as a company's internal or referral-only board (Coupang Internal, Referrals Only), meant for its own staff or for referred candidates: their 1,203 jobs on 2026-11-02 come back like any other.
- Titles and descriptions come in the company's own language, most of them (95%) in English.
- The list of boards was built on 2026-11-02. A company that joined later is searched only when you name it.

## Who maintains it?

Built and maintained by **Anshuman Atrey** ([@AnshumanAtrey](https://github.com/AnshumanAtrey)), who publishes a portfolio of data and OSINT actors on Apify Store. For a feature request or a bug, message [LinkedIn](https://linkedin.com/in/anshumanatrey) (fastest), open an issue on the GitHub repo, or write through [atrey.dev](https://atrey.dev).

## Sibling actors

| Actor | What it searches |
|---|---|
| [Ashby Jobs Scraper](https://apify.com/anshumanatrey/ashby-jobs-search) | Jobs from every company on Ashby (jobs.ashbyhq.com), searched live |
| [Cornerstone Jobs Scraper](https://apify.com/anshumanatrey/cornerstone-jobs-search) | Jobs from every company on Cornerstone (csod.com), searched live |
| [Workday Jobs Scraper](https://apify.com/anshumanatrey/workday-job-search) | Jobs from every company on Workday (myworkdayjobs.com), searched live |
| [Deel Jobs Scraper](https://apify.com/anshumanatrey/deel-jobs-search) | Jobs from every company on Deel ATS (jobs.deel.com), with pay |
| [SmartRecruiters Jobs Scraper](https://apify.com/anshumanatrey/smartrecruiters-jobs-search) | Jobs from 2,900+ companies on SmartRecruiters, searched live |
| [Workable Jobs Scraper](https://apify.com/anshumanatrey/workable-job-search) | Jobs from every company on Workable, in one search |
| [Lever Jobs Scraper](https://apify.com/anshumanatrey/lever-jobs-search) | Jobs from 2,300+ companies on Lever (jobs.lever.co), searched live |

For the people behind a company: [LinkedIn Profile Finder](https://apify.com/anshumanatrey/linkedin-harvester) turns an email into a public LinkedIn profile.

## Documentation

- Apify Store: https://apify.com/anshumanatrey/greenhouse-jobs-search
- GitHub repo: https://github.com/AnshumanAtrey/greenhouse-jobs-search (MIT license, see [LICENSE](LICENSE))
- The engine behind it: https://github.com/AnshumanAtrey/ats-jobs-engine

## Last updated

2026-11-03 (version 1.0)
