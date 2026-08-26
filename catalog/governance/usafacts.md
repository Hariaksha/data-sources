# USAFacts

**Theme:** Governance / Government Data Transparency (cross-cutting: economy, crime, spending, health, immigration, education, defense, environment, population)
**Source:** USAFacts — nonpartisan nonprofit founded by Steve Ballmer (former Microsoft CEO); privately funded, no external donor contributions
**Coverage:** United States — all 50 states, 3,000+ counties, 90,000+ government entities; aggregates 70+ official government data sources
**Unit of observation:** Varies by topic — national, state, and county-level statistics; some indicators down to school-district or agency level
**Temporal granularity:** Varies by underlying source (annual, quarterly, or monthly); site content updated on a rolling basis as new government releases land
**Format:** Web hub pages (topic overviews, "Data Guides," fact cards, interactive visualizations) with underlying data downloadable in CSV; each statistic links back to its original government source
**Access:** [https://usafacts.org](https://usafacts.org) — free, no registration; per-topic hubs: [Economy](https://usafacts.org/economy/), [Crime](https://usafacts.org/crime/), [Government Spending](https://usafacts.org/government-spending/), [Health](https://usafacts.org/health/), [Immigration](https://usafacts.org/immigration/), [Education](https://usafacts.org/education/), [Defense & Security](https://usafacts.org/defense-and-security/), [Environment](https://usafacts.org/environment/), [Population](https://usafacts.org/population/)
**License:** CC BY-SA 4.0 (attribution required for reuse)
**Last verified:** July 2026

---

## What It Is

USAFacts is a nonpartisan data organization whose mission is to make U.S. government statistics accessible without spin or political framing — "just the facts." Rather than collecting original data, it aggregates and standardizes numbers already published by 70+ federal, state, and local government sources (Census Bureau, BLS, BEA, CDC, FBI/DOJ, DHS, Treasury, Department of Education, EPA/NOAA, etc.), reconciling inconsistent definitions and formats and surfacing figures buried in footnotes, PDFs, and appendix tables that most people skip. Every statistic on the site links back to its original government source via a "source" button, making it a useful discovery/triangulation layer on top of primary agency data rather than a primary source in itself.

The site is organized into nine cross-cutting topic hubs (linked above), each structured similarly: a topical overview, "Data Guides" for deeper self-paced explainers, an "Insights" section of fact-based short answers to common questions, and a section explaining the relevant government agencies. It also publishes recurring flagship reports, including an annual **"Government 10-K"** (framing U.S. government finances the way a public company's 10-K filing would) and an **"America in Facts"** annual report for Congress.

---

## Topic Hubs Covered

| Hub | Example content |
|-----|-----------------|
| [Economy](https://usafacts.org/economy/) | Jobs/unemployment, inflation, cost of living, housing, taxes, trade/exports-imports |
| [Crime](https://usafacts.org/crime/) | Violent/property crime rates, policing, incarceration |
| [Government Spending](https://usafacts.org/government-spending/) | Federal/state budgets, deficit, entitlement spending, the "Government 10-K" |
| [Health](https://usafacts.org/health/) | Public health statistics, insurance coverage, mortality, disease prevalence |
| [Immigration](https://usafacts.org/immigration/) | Immigration flows, enforcement, demographic composition |
| [Education](https://usafacts.org/education/) | Enrollment, funding, outcomes, school-level statistics |
| [Defense & Security](https://usafacts.org/defense-and-security/) | Military spending, personnel, homeland security |
| [Environment](https://usafacts.org/environment/) | Climate trends, fire risk, flood data, natural disasters |
| [Population](https://usafacts.org/population/) | Demographics, migration, census-derived statistics |

---

## Potential Research Questions

- Do county-level economic distress indicators (unemployment, cost of living) from USAFacts correlate with the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md)-style informal-economy proxies in analogous data-scarce contexts abroad?
- How does USAFacts' environment/fire-risk data compare to [NASA FIRMS wildfire detections](../climate/wildfire-detections.md) for cross-validating U.S. wildfire trend narratives?
- Can USAFacts' government spending and crime datasets serve as a clean U.S. baseline/comparison case against [Fragile States Index](fragile-states-index.md) or [Global Peace Index](../peace-conflict/global-peace-index.md) components that use analogous indicators internationally?
- Does immigration hub data show measurable relationships with regional economic indicators tracked elsewhere on the site (jobs, housing)?

---

## Notes & Quirks

- **Not a primary data source — a curation/standardization layer.** USAFacts re-publishes and reconciles numbers already released by government agencies; for citation-grade work, verify against the original agency source linked from each statistic rather than citing USAFacts alone.
- **Topic hub pages are navigational, not data tables.** The nine hub URLs listed above function as landing pages linking out to "Data Guides," "Insights" articles, and agency explainers — they don't display raw datasets or bulk-downloadable tables directly; drill into individual articles/metrics for the underlying CSV download links.
- **No public API as of last verification** — a 2018 statement referenced API plans, but no current public API was found; CSV download is the primary structured-access route.
- **US-only.** Despite covering topics (environment, defense, immigration) that have obvious international analogs elsewhere in this catalog, USAFacts itself has no non-U.S. coverage.
- **CC BY-SA 4.0 license applies to USAFacts' own content/visualizations**, not necessarily to the underlying government data it sources from (which is typically public domain, but confirm per-source).

---

## How to Access

1. Browse topic hubs: [https://usafacts.org](https://usafacts.org) (see per-topic links above)
2. Download underlying data in CSV from individual articles/metric pages (look for the "Download data" or source-attribution links)
3. Explore USAFacts' code/data projects on GitHub: [https://github.com/USAFacts](https://github.com/USAFacts)
4. Read methodology and organizational background: [https://usafacts.org/about-usafacts/](https://usafacts.org/about-usafacts/)
5. See the full list of underlying government data sources: [https://usafacts.org/data-sources/](https://usafacts.org/data-sources/)
