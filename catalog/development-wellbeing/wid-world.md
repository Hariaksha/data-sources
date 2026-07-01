# WID.world — World Inequality Database

**Theme:** Development & Economics / Income & Wealth Inequality
**Source:** World Inequality Lab (WIL), hosted at Paris School of Economics; 100+ researchers across 70+ countries
**Coverage:** Global — 100+ countries and territories + regional aggregates; historical data for some countries dating to the 18th–19th century
**Unit of observation:** Country-year, disaggregated by income/wealth percentile group
**Temporal granularity:** Annual; coverage varies by country (some from 1800s, most from mid-20th century, through present)
**Format:** Interactive data browser; CSV bulk download; Stata package (`wid`); R package
**Access:** [https://wid.world/data/](https://wid.world/data/) — free, open access, no registration required
**License:** Open access
**Last verified:** June 2026

---

## What It Is

WID.world is the primary open-access repository for long-run distributional data on income and wealth. It combines national accounts, household surveys, and fiscal (tax) data to produce consistent series on who earns and owns what — across countries and over time. It is the data infrastructure behind the *World Inequality Report* and major work by Piketty, Saez, Zucman, Chancel, and collaborators.

WID uniquely goes beyond survey-based measures (which top-code the wealthy) by anchoring distributions to national accounts totals and using tax records where available.

---

## Key Variable Concepts

WID organizes data into five concept groups:

### Income
| Concept | Description |
|---------|-------------|
| `Pre-tax factor income` | Labor + capital income before taxes and transfers |
| `Pre-tax national income` | Factor income + pension income (most commonly used inequality series) |
| `Post-tax national income` | After all taxes and government transfers |
| `Fiscal income` | Income as reported on tax returns (narrower than national income) |

### Wealth
| Concept | Description |
|---------|-------------|
| `Net personal wealth` | Individual-level net assets (most granular wealth series) |
| `Net private wealth` | Household + non-profit sector net wealth |
| `Net public wealth` | Government net assets (assets minus liabilities) |
| `Book-value / market-value national wealth` | Total wealth at national level |
| `Tobin's Q` | Ratio of market to book value of corporations |

### National Accounts Aggregates
GDP, national income, labor share, capital share, public spending/revenue, current account, capital account, savings rates — useful for anchoring distributional series.

### Carbon Emissions (by income group)
| Concept | Description |
|---------|-------------|
| `Personal carbon footprint` | CO₂ emissions attributed to individuals, by income percentile |
| `National carbon footprint` | Total consumption-based national emissions |
| `National territorial emissions` | Production-based national emissions |
| `National net imports of carbon` | Embedded carbon in trade balance |

### Other
Population, employed population, PPP and market exchange rates (LCU per USD/EUR/CNY), inequality transparency index, Gini coefficient, Top10/Bottom50 ratio.

---

## Distributional Disaggregation

All income and wealth concepts can be sliced by:

**Percentile groups:**
- Key groups: Bottom 50%, Middle 40%, Top 10%, Next 9%, Top 1%
- Fine-grained: P0P10 through P90P100 in decile steps; custom percentile ranges also available
- Summary statistics: Gini index, Top10/Bottom50 ratio, Pareto coefficient

**Population unit:**
- Equal-split adults (default — most comparable across countries)
- Individuals
- Tax units
- Employed population
- Female / Male (gender-disaggregated series)

**Age groups:** All ages, adults, children, 20–39, 40–59, 60+, 65+, 80+

---

## Geographic Coverage

~200 countries and territories + regional aggregates including:
- East Asia, Europe, Latin America, MENA, North America & Oceania, Russia & Central Asia, South & Southeast Asia, Sub-Saharan Africa
- Available in both MER (market exchange rates) and PPP (purchasing power parity) versions for cross-country comparison
- Historical entities included (e.g., USSR, Yugoslavia, Czechoslovakia, German Democratic Republic)

---

## Variable Naming Convention

WID uses a structured code system. Variable names combine:
- **Concept prefix** (e.g., `s` = share, `a` = average, `t` = threshold, `g` = Gini)
- **Income/wealth type** (e.g., `ptinc` = pre-tax national income, `hweal` = personal wealth)
- **Numeric suffix** (unit/age code)
- **Population suffix** (e.g., `j` = tax unit, `i` = individual, `p` = equal-split adult)

Example: `sptinc992j` = share of pre-tax national income, tax units
Full code dictionary: [https://wid.world/codes-dictionary/](https://wid.world/codes-dictionary/)

---

## Key Merge Variables

| Variable | Description |
|----------|-------------|
| `country` | ISO 2-letter country code (or WID region code) |
| `year` | Calendar year |
| `percentile` | Percentile range (e.g., `p99p100` = top 1%; `p0p50` = bottom 50%) |
| `variable` | WID variable code (e.g., `sptinc992j`) |

---

## Potential Research Questions

- How has the income share of the bottom 50% vs. top 1% evolved within and across countries since 1980?
- What explains cross-country variation in wealth concentration, and how does public wealth offset private inequality?
- Is there a relationship between carbon footprint inequality and income inequality across countries?
- How do pre-tax and post-tax inequality series diverge, and what does this imply about redistribution effectiveness?
- How does gender wealth inequality vary across countries and over time?
- Can long-run historical inequality series (pre-1950) explain contemporary development outcomes?

---

## Notes & Quirks

- **Pre-tax national income is the recommended baseline series** for cross-country inequality comparisons; fiscal income is narrower and less comparable.
- **Equal-split adults** is the recommended population unit for cross-country comparisons; tax units vary in definition across countries.
- **Coverage is uneven.** Rich countries have long, high-quality series (some to 1900 or earlier); many low-income countries have shorter or less reliable series. Always check country-level coverage before use.
- **PPP vs. MER matters.** For comparing levels across countries, use PPP; for finance and trade research, MER. Regional aggregates are provided in both.
- **Carbon data is a newer addition** and coverage is sparser than the income/wealth series.
- **Stata package:** `ssc install wid` — allows direct download of data into Stata with a simple `wid` command, specifying indicators, countries, and years. Far easier than manual CSV downloads for large queries.
- **R package:** `devtools::install_github("WIDworld/wid-r-tool")` — similar functionality.
- **Vintage differences:** WID series are revised as new data becomes available. Note the download date if replicating results.
- **WID ≠ World Inequality Report.** WID.world is the ongoing data portal; the *World Inequality Report* is a periodic flagship publication (most recent: 2026) that draws on but is separate from the database.

---

## How to Access

**Interactive browser:**
1. Go to [https://wid.world/data/](https://wid.world/data/)
2. Select indicators, countries/regions, years, variable type, and population unit
3. Click "Download" for a CSV of your selection, or "Download full dataset" for the complete database

**Stata (recommended for research use):**
```stata
ssc install wid
wid, indicators(sptinc) areas(US FR DE) years(1980/2023) perc(p0p50 p90p100 p99p100) ages(992) pop(j)
```

**R:**
```r
devtools::install_github("WIDworld/wid-r-tool")
library(wid)
download_wid(indicators = "sptinc", areas = c("US","FR"), years = 1980:2023,
             perc = c("p0p50","p99p100"), ages = 992, pop = "j")
```

**Country and regional pages:** [https://wid.world/world/](https://wid.world/world/) — interactive charts by country with pre-built visualizations.

**Cite as:** World Inequality Database (WID.world), [https://wid.world](https://wid.world), accessed [Month Year].
