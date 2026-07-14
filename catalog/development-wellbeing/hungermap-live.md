# HungerMap LIVE

**Theme:** Development & Wellbeing / Food Security & Early Warning
**Source:** World Food Programme (WFP), Hunger Monitoring Unit (formerly mVAM — mobile Vulnerability Analysis and Mapping)
**Coverage:** ~94 countries monitored globally; near real-time (CATI phone survey) monitoring active in 50+ countries, with a focus on 16 designated "Hunger Hotspot" countries
**Unit of observation:** Country / sub-national region (admin-1); some layers are event-level (conflict, hazards)
**Temporal granularity:** Near-daily updates (rolling 28/30-day survey window, ~2–4 day processing lag); historical time series available via API/HDX dumps
**Format:** Interactive web map (hungermap.wfp.org) + public REST API (JSON/GeoJSON) + per-country CSV/JSON data dumps on HDX
**Access:** [https://hungermap.wfp.org](https://hungermap.wfp.org) (map) · [https://api.hungermapdata.org](https://api.hungermapdata.org) (API) · [https://data.humdata.org](https://data.humdata.org/organization/wfp) (HDX country datasets)
**License:** WFP / HDX open data terms (attribution required; verify per-dataset terms on HDX, as some layers reuse third-party sources like ACLED and IPC with their own licenses)
**Last verified:** July 2026

---

## What It Is

HungerMap LIVE is WFP's global hunger-monitoring and early-warning platform, launched January 2020 and expanded rapidly during COVID-19. It fuses WFP's own near-real-time household food security surveys with dozens of secondary data streams (climate, conflict, markets, currency/inflation, nutrition) into a single near-daily picture of food insecurity, plus ~1-month-ahead machine-learning forecasts. It's built and maintained by WFP's Hunger Monitoring Unit (the successor to the mVAM program) together with WFP Innovation.

The core household-level input comes from continuous computer-assisted telephone interviewing (CATI) via call centers: respondents are surveyed on a rolling basis so that each daily update reflects a snapshot of the preceding 28–30 calendar days (spread evenly across that window), processed through automated statistical engines with a 2–4 day quality-control lag.

---

## Key Indicators

- **Prevalence of insufficient food consumption** — derived from the Food Consumption Score (FCS), a standard WFP indicator combining dietary diversity and frequency.
- **Prevalence of crisis-or-above food-based coping** — derived from the reduced Coping Strategies Index (rCSI), capturing households' use of crisis-level coping behaviors (e.g., skipping meals, selling assets).
- **90-day change** in both of the above, used to flag deteriorating vs. improving situations.
- **IPC (Integrated Food Security Phase Classification)** population estimates by phase (including Phase 4/5 — Emergency/Catastrophe).
- **Conflict events** (via ACLED integration) — event type, location, count.
- **Hazard data** (via PDC — Pacific Disaster Center) — hazard type, severity, location, timestamps.
- **Macroeconomic indicators** — currency exchange rates, inflation, staple food prices/import dependency.
- **Nutrition layer** (developed with Gates Foundation support) — micronutrient intake adequacy, used to flag "hidden hunger" from vitamin/mineral deficiencies.
- **Climate/weather layers** feeding the risk model (rainfall, vegetation, etc. — specific variables not itemized publicly).

---

## API Access (undocumented but public, no key required as of last verification)

| Endpoint | Returns |
|----------|---------|
| `api.hungermapdata.org/v2/adm0/{country_id}/countryData.json` | Population, FCS, rCSI, import dependency, related news |
| `api.hungermapdata.org/v2/adm0/{country_id}/adm1data.json` | Sub-national (admin-1) data + GeoJSON geometry |
| `api.hungermapdata.org/v2/iso3/{iso3}/countryIso3Data.json` | Nutrition metrics, currency/inflation series, trade data |
| `api.hungermapdata.org/v2/acled.geojson` | Conflict events (type, region, count, lat/lon) |
| `api.hungermapdata.org/v2/ipc.json` | IPC population-affected figures by phase |
| `api.hungermapdata.org/v2/pdc.json` | Hazard events (type, severity, coordinates, timestamps) |
| `static.hungermapdata.org/insight-reports/latest/country.json` | Links to per-country summary PDF reports |
| `static.hungermapdata.org/insight-reports/latest/global-summary.pdf` | Global insights/trends PDF |

Numeric `country_id` values are internal to WFP (not ISO3) — a lookup table needs to be built from the map or scraped country list before querying the `adm0`/`adm1` endpoints. The `iso3` endpoint accepts standard ISO3 codes directly.

**HDX mirror:** country-specific CSV/JSON dumps of the same underlying data ("HungerMap data for [country]") are also published on the Humanitarian Data Exchange, e.g. [Ukraine](https://data.humdata.org/dataset/wfp-hungermap-data-for-ukr), [Chad](https://data.humdata.org/dataset/wfp-hungermap-data-for-tcd), [Mozambique](https://data.humdata.org/dataset/wfp-hungermap-data-for-moz) — search `data.humdata.org` for "wfp-hungermap-data-for-{iso3}".

---

## Potential Research Questions

- Do spikes in conflict events (ACLED layer) precede measurable increases in the prevalence of insufficient food consumption at a sub-national level, and with what lag?
- How well do HungerMap's ~1-month-ahead ML forecasts perform against realized food-insecurity outcomes in conflict-affected vs. stable regions?
- Can the rCSI/FCS time series be used as a high-frequency proxy for local economic distress, comparable to the [Marketplace Activity Index](marketplace-activity-index.md), in wildfire- or conflict-affected areas?
- How does the nutrition ("hidden hunger") layer correlate with climate shocks (drought, flooding) recorded in the hazard/PDC layer?
- Are IPC phase classifications and HungerMap's own near-real-time prevalence estimates consistent, or does the near-real-time layer lead/lag the periodic IPC assessments?

---

## Notes & Quirks

- **The public API is undocumented and unofficial** — endpoints above were reverse-engineered from the web map's own network requests (per WFP's own internal chatbot docs) rather than published as a stable, versioned API. Treat field names/structure as subject to change without notice.
- **Country IDs are non-standard for the `adm0`/`adm1` endpoints** — you need WFP's internal numeric ID, not ISO3, for those specific endpoints (the `iso3` endpoint is the exception).
- **Rolling 28/30-day window, not a point-in-time snapshot** — each "daily" figure blends survey responses collected over the preceding month, so day-to-day movements are smoothed and lag real-time conditions by design.
- **CATI phone-survey coverage is uneven** — near-real-time monitoring is only active in a subset (50+) of the ~94 countries with any HungerMap presence; some countries show data from lower-frequency sources (IPC, secondary data) only.
- **Multiple third-party layers reused within the platform** (ACLED conflict data, IPC classifications, PDC hazards) — each carries its own underlying license/attribution requirements distinct from WFP's own data.
- **HDX country dumps may lag the live API** — cross-check dates if you need the most current figures vs. a stable archival snapshot.

---

## How to Access

1. Browse the interactive map: [https://hungermap.wfp.org](https://hungermap.wfp.org)
2. Query the live API directly (see endpoint table above) — e.g. `https://api.hungermapdata.org/v2/iso3/ETH/countryIso3Data.json`
3. Download country-level historical dumps via HDX: search "HungerMap data for [country]" at [https://data.humdata.org](https://data.humdata.org/organization/wfp)
4. Read global/regional PDF summary reports: [https://static.hungermapdata.org/insight-reports/latest/global-summary.pdf](https://static.hungermapdata.org/insight-reports/latest/global-summary.pdf)
5. Background/project description: [WFP Innovation — HungerMap LIVE](https://innovation.wfp.org/project/hungermap-live)
