# World Bank Data360

**Theme:** Development & Wellbeing / Multi-Topic Development Indicators
**Source:** World Bank Group (successor to the World Bank Open Data portal and ProsperityData360; consolidates World Development Indicators and partner data)
**Coverage:** 200+ economies; ~300 million data points, which the World Bank says is about 40× what the old Open Data portal held. Time span varies by indicator (many WDI series start in 1960)
**Unit of observation:** Country-year for most indicators; some series are sub-annual or broken down by sex, age, or urban/rural
**Temporal granularity:** Mostly annual; varies by dataset
**Format:** Web portal (search, custom reports, charts), REST API (JSON), bulk downloads (via WDI), and an official MCP server for AI agents
**Access:** [https://data360.worldbank.org](https://data360.worldbank.org) — free, no registration; merged into [https://data.worldbank.org](https://data.worldbank.org) as the primary open data site
**API:** [https://data360.worldbank.org/en/api](https://data360.worldbank.org/en/api) — no API key required (base: `https://data360api.worldbank.org/data360/`)
**License:** CC BY 4.0 unless a dataset is labeled otherwise. Some third-party datasets need the original provider's permission for reuse
**Last verified:** September 2026

---

## What It Is

Data360 is the World Bank's consolidated development-data platform, built as the successor to its Open Data portal. It pulls together curated datasets and indicators from across the World Bank Group and partner organizations into one searchable interface with shared metadata standards (under the WBG Policy on Development Data Quality). It builds on the earlier ProsperityData360 platform and folds in the **World Development Indicators (WDI)**. It is being merged into data.worldbank.org in stages, and parts of it are still labeled beta.

Content is organized around five focus areas: **Digital, Infrastructure, People, Planet, and Prosperity**.

The [Atlas of Global Development](world-bank-atlas-global-development.md), cataloged separately, is a narrative/visual product built on top of Data360.

---

## Key Datasets (by Database ID)

| Database ID | Contents |
|-------------|----------|
| `WB_WDI` | World Development Indicators, the World Bank's flagship country-year indicator set (population, GDP, poverty, health, education, environment, etc.) |
| `WB_POVERTY` | Poverty and inequality measures |
| `WB_SSGD` | Subnational/spatially disaggregated development data |
| `IPC_IPC` | Integrated Food Security Phase Classification (partner data) |

Indicator IDs are prefixed with the database ID, e.g. `WB_WDI_SP_POP_TOTL` = WDI total population. Countries use ISO3 codes (`REF_AREA=IDN`), and disaggregation dimensions include `SEX`, `AGE`, and `URBANISATION` (with `_T` = total).

---

## API Access

Example (verified working, no key needed): Indonesia's total population, 2020–2022:

```
https://data360api.worldbank.org/data360/data?DATABASE_ID=WB_WDI&INDICATOR=WB_WDI_SP_POP_TOTL&REF_AREA=IDN&timePeriodFrom=2020&timePeriodTo=2022
```

Returns JSON with `OBS_VALUE`, `TIME_PERIOD`, `REF_AREA`, unit, and disaggregation fields in an SDMX-style structure.

**MCP server:** The World Bank publishes an official [Data360 MCP server](https://worldbank.github.io/data360-mcp/) that lets Claude and other AI clients search indicators, fetch time series, check country coverage, compare/rank countries, and generate Vega-Lite charts straight from Data360. Remote endpoint: `https://maimcpext.worldbank.org/ext/data360/mcp` (use the `mcp-remote` wrapper for Claude Desktop). Load the `data360://system-prompt` resource into the agent's context for reliable tool use.

---

## Potential Research Questions

- Can WDI indicators (forest area, agricultural land, rural population, GDP per capita) serve as country-year controls in an Indonesia wildfire-conflict panel alongside [ACLED](../peace-conflict/acled.md) and [NASA FIRMS](../climate/wildfire-detections.md)?
- Do sub-national (`WB_SSGD`) development indicators explain variation in conflict or fire exposure within countries better than national aggregates?
- How do IPC food-insecurity phases in Data360 line up with near-real-time food security estimates from [HungerMap LIVE](hungermap-live.md)?
- Do Data360 poverty and inequality series track the distributional estimates in [WID.world](wid-world.md) for the same countries and years?

---

## Notes & Quirks

- **Beta and mid-migration.** Data360 is still being merged into data.worldbank.org in stages. URLs, API parameters, and dataset IDs may change; the older Indicators API (`api.worldbank.org/v2`) and DataBank still exist alongside it.
- **Indicator IDs differ from classic WDI codes.** Classic WDI codes like `SP.POP.TOTL` become `WB_WDI_SP_POP_TOTL` in Data360 (database prefix, underscores instead of dots). Scripts written for the old API need updating.
- **License is mostly but not entirely CC BY 4.0.** Third-party/partner datasets can carry their own terms; check each dataset's metadata before redistributing.
- **Not all indicators cover all countries or years.** Coverage is uneven, especially for small states, conflict-affected countries, and recent years. The MCP server's coverage-check tool (or a quick API query) helps before building a panel.
- **Bulk downloads still route through WDI** rather than a single Data360 bulk export.

---

## How to Access

1. Search and browse: [https://data360.worldbank.org](https://data360.worldbank.org) (also reachable via [https://data.worldbank.org](https://data.worldbank.org))
2. Query programmatically: [Data360 API](https://data360.worldbank.org/en/api) (base URL `https://data360api.worldbank.org/data360/`)
3. Connect an AI assistant via the official [Data360 MCP server](https://worldbank.github.io/data360-mcp/)
4. Bulk-download WDI: via the World Development Indicators portal / [DataBank](https://databank.worldbank.org)
5. About the platform and licensing: [https://data360.worldbank.org/en/about](https://data360.worldbank.org/en/about) · [World Bank data licensing](https://datacatalog.worldbank.org/public-licenses)
