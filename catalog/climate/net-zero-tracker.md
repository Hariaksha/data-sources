# Net Zero Tracker

**Theme:** Climate Policy / Corporate & National Net Zero Commitments
**Source:** Joint initiative of Energy & Climate Intelligence Unit (ECIU), Data-Driven EnviroLab (University of North Carolina-Chapel Hill), NewClimate Institute, and Oxford Net Zero (University of Oxford); philanthropically funded (IKEA Foundation, European Climate Foundation, ClimateWorks Foundation)
**Coverage:** ~4,190 entities — all UNFCCC party countries/territories, every region in the 25 largest emitting nations, all cities with 500,000+ inhabitants, the 2,000 largest publicly listed companies (Forbes Global 2000), and the 100 largest privately-owned companies
**Unit of observation:** Entity (nation, sub-national region, city, or company) and its net zero (or equivalent) target
**Temporal granularity:** Target-level data reflects the date each entity was last analysed (not the pledge announcement date); includes a time-series view ("Net Zero Targets Over Time") tracking growth in target adoption over time for both nations and companies
**Format:** Interactive web Data Explorer with filters; downloadable dataset from the homepage; also a natural-language chat interface (ChatNetZero.ai)
**Access:** [https://zerotracker.net/data-explorer](https://zerotracker.net/data-explorer) — free, no registration required for browsing; full dataset downloadable from the site homepage or by emailing updates@zerotracker.net
**License:** Not explicitly stated as an open data license — the Terms of Use page asserts general site/IP ownership without addressing data reuse/redistribution terms explicitly. Verify directly with the team (updates@zerotracker.net) before redistributing derived data.
**Last verified:** July 2026

---

## What It Is

Net Zero Tracker is billed as "the definitive global resource for collating, assessing and presenting the scale and quality of net zero pledges." It emerged in response to the proliferation of net zero pledges following the 2018 IPCC Special Report on 1.5°C, aiming to distinguish substantive commitments from rhetorical ones by scoring pledge *robustness*, not just existence.

The Data Explorer lets you filter and compare entities across type (nation/region/city/company), and — notably for time-series use — includes a **"Net Zero Targets Over Time"** view showing the cumulative growth of net zero target adoption among nations and companies since pledges began proliferating post-2018/2021 (COP26). This is genuinely historical/time-series data, not just a current snapshot, though the underlying entity-level records themselves reflect the date of last analysis rather than a continuous panel.

---

## Key Variables

| Variable | Description |
|----------|--------------|
| Entity type | Nation, region, city, or company |
| Target name | e.g., "net zero," "carbon neutral," "climate neutral," "carbon negative" |
| Target year | Year the entity has committed to reach its target |
| Legal/policy status | Whether the target is enshrined in law, policy document, or is a pledge only |
| Scope coverage | For companies: Scope 1/2/3 coverage; for nations/cities: CO₂-only vs. multi-gas coverage |
| Interim targets | Whether shorter-term milestones exist en route to the net zero year |
| Plan quality ("traffic light") | Robustness scoring based on a codebook (e.g., detailed plan completeness, annual reporting mechanism, offset-use conditions, Scope 3 disclosure) |
| Analysis date | Date the entity's record was last reviewed/updated (used in place of announcement date) |
| GHG emissions / GDP / revenue (context fields) | National emissions from ClimateWatch CAIT (2021 vintage); GDP from World Bank (countries) or Kummu et al. 2024 (regions/cities); company revenue/employees from Forbes Global 2000, Fortune, Eqvista, and company filings |

---

## Methodology Notes

- Target and plan-quality data are compiled from **publicly available sources** — entity websites, official documentation, press releases, and news articles — supplemented by web-scraping for Tier 1 (highest-scrutiny) entities at regular intervals.
- Coding undergoes **double-checking by secondary coders**, with prior versions reporting ~94% intercoder reliability; major actor updates receive additional spot checks.
- Because coverage depends on **publicly available, often English-language sources**, there are acknowledged gaps for entities that publish primarily in other languages, plus structural coverage gaps: smaller cities, non-top-25-emitter regions, and privately-held companies outside the top 100 are excluded entirely.

---

## Potential Research Questions

- Has the *rate* of net zero pledge adoption (from the "Targets Over Time" series) plateaued, accelerated, or reversed since COP26 / COP28, and does this differ between nations and companies?
- Does higher plan-quality ("traffic light") scoring correlate with actual subsequent emissions trajectories, or is it decoupled from real-world performance?
- How does national net zero target robustness relate to a country's [Environmental Performance Index](environmental-performance-index.md) or [Global Sustainable Competitiveness Index](global-sustainable-competitiveness-index.md) ranking?
- Are climate litigation cases (see [Climate Litigation Database](climate-litigation.md)) more frequent against entities with weaker (lower-quality) net zero pledges?
- Do companies headquartered in countries with strong national net zero legislation set more robust corporate targets than peers in countries with weaker/pledge-only commitments?

---

## Notes & Quirks

- **"Time series" here means pledge-adoption-over-time, not a continuous re-scored panel** — the Data Explorer's historical view tracks when entities *first* set/adopted targets, not a quarterly/annual re-assessment of the same entities' scores over time. Entity-level target and plan-quality records reflect the most recent analysis date, so constructing a true longitudinal panel of scoring changes for a given entity would require your own periodic snapshots (or a data request to the team for historical versions).
- **License is unclear** — unlike most datasets in this catalog, Net Zero Tracker's Terms of Use page does not explicitly grant an open data license for downloaded data. Confirm reuse/redistribution terms directly with updates@zerotracker.net before using in publications requiring clear licensing.
- **Underlying context data (GDP, emissions, revenue) has mixed vintages** — e.g., national GHG emissions sourced from a 2021-vintage ClimateWatch CAIT extract — check currency before combining with more recent macro data.
- **"Target year" ≠ commitment strength** — always cross-reference the plan-quality/traffic-light fields; an ambitious target year with a weak or absent implementation plan is common and is exactly the distinction this dataset is designed to surface.
- **A conversational query interface exists** (ChatNetZero.ai) as an alternative to the structured Data Explorer, useful for quick lookups but not a substitute for the underlying structured data when doing systematic analysis.

---

## How to Access

1. Explore and filter entity-level data interactively: [https://zerotracker.net/data-explorer](https://zerotracker.net/data-explorer)
2. Download the full current dataset from the homepage: [https://zerotracker.net](https://zerotracker.net)
3. Read the full methodology and codebook: [https://zerotracker.net/methodology](https://zerotracker.net/methodology)
4. Query via natural-language chat interface: [ChatNetZero.ai](https://chatnetzero.ai)
5. For data corrections, historical extracts, or licensing questions, contact: updates@zerotracker.net (data issues) or hello@zerotracker.net (general inquiries)
