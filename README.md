# data-sources

# 🗂️ Research Data Catalog

> A personal index of datasets I use or expect to use across research projects in environmental economics, conflict studies, climate policy, and development. This repository does **not** store raw data files — it catalogs what I have, where to get it, what it contains, and what questions it can help answer.

---

## Purpose

Across research on topics like wildfire-conflict dynamics in Indonesia, climate commitments, and survey-based welfare measures, I accumulate data from many different sources. This catalog solves a recurring problem: *knowing what data I already have access to when scoping a new project.*

Each dataset entry answers four questions:

1. **What is it?** — Coverage, grain, format, update frequency
2. **How do I get it?** — Access link, registration requirements, license
3. **What's inside?** — Key variables worth knowing about
4. **What can I do with it?** — Example research questions it can help answer

---

## 🗂️ Repository Structure

- `README.md` — master index & quick-reference table
- `catalog/` — one `.md` file per dataset
  - `peace-conflict/` → `acled.md`, `acled-conflict-index.md`, `global-peace-index.md`, `global-terrorism-index.md`, `organized-crime-index.md`, `global-militarization-index.md`, `climate-conflict-vulnerability-index.md`, `ecosystems-for-peace-nbs-catalog.md`, `scad.md`, `gdelt.md`
  - `climate/` → `wildfire-detections.md`, `era5-wind.md`, `project-cosmos.md`, `climameter.md`, `environmental-performance-index.md`, `global-sustainable-competitiveness-index.md`, `climate-litigation.md`, `climate-protest-tracker.md`, `climate-transparency-platform.md`, `disaster-dollar-database.md`, `noaa_billion_dollar_disasters.md`, `scp-hat.md`, `un-biodiversity-lab.md`, `water-resource-vulnerability.md`, `global-marine-fisheries-catch-1950-2014.md`, `net-zero-tracker.md`
  - `governance/` → `fragile-states-index.md`, `state-resilience-index.md`, `corruption-perceptions-index.md`, `global-corruption-barometer.md`, `freedom-house.md`, `democracy-index.md`, `press-freedom-index.md`, `academic-freedom-index.md`, `demspaces.md`, `pandem.md`, `informea.md`, `silencing-science/silencing-science-tracker.md`
  - `development-wellbeing/` → `human-development-index.md`, `wid-world.md`, `multidimensional-poverty-index.md`, `gender-development-index.md`, `social-institutions-gender-index.md`, `world-inequality-report.md`, `global-health-security-index.md`, `happiness-world-report.md`, `good-country-index.md`, `world-giving-index.md`, `formal-bilateral-influence-capacityindex.md`, `wealth-migration.md`, `world-bank-atlas-global-development.md`, `demscore.md`, `marketplace-activity-index.md`, `hungermap-live.md`
  - `infrastructure/` → `poweroutage-us.md`, `hot-osm-hdx.md`
  - `reference/` — language and country reference files

> **Note on data storage:** Raw files (`.csv`, `.dta`, `.xlsx`) are intentionally **not** committed here unless tiny. Large files are excluded via `.gitignore`. The value of this repo is the metadata, not the data itself.
> **Note on data storage:** Raw files (`.csv`, `.dta`, `.xlsx`) are intentionally **not** committed here unless tiny. Large files are excluded via `.gitignore`. The value of this repo is the metadata, not the data itself.

---

## Dataset Index

### 🔴 Peace & Conflict

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| ACLED | Global, 1997–present | Event-level, daily | No | [→](catalog/peace-conflict/acled.md) |
| ACLED Conflict Index | Global, recent | Country | No | [→](catalog/peace-conflict/acled-conflict-index.md) |
| Global Peace Index | Global, 2008–present | Country-year | No | [→](catalog/peace-conflict/global-peace-index.md) |
| Global Terrorism Index | Global, 2000–present | Country-year | No | [→](catalog/peace-conflict/global-terrorism-index.md) |
| Organized Crime Index | Global (193 countries), 2021/2023 | Country | No | [→](catalog/peace-conflict/organized-crime-index.md) |
| Global Militarization Index | Global, annual | Country-year | No | [→](catalog/peace-conflict/global-militarization-index.md) |
| Climate Conflict Vulnerability Index | Global, cross-sectional | Country | No | [→](catalog/peace-conflict/climate-conflict-vulnerability-index.md) |
| Ecosystems for Peace – NbS Catalog | Global, 2024–present | Project/intervention | No | [→](catalog/peace-conflict/ecosystems-for-peace-nbs-catalog.md) |
| SCAD (Social Conflict Analysis Database) | Africa + LAC, 1990–2017 | Event-level | No | [→](catalog/peace-conflict/scad.md) |
| GDELT (Global Database of Events, Language, and Tone) | Global, 1979–present (real-time since 2015) | Event-level | No | [→](catalog/peace-conflict/gdelt.md) |

---

### 🌿 Climate & Environment

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| NASA FIRMS Wildfire Detections | Global, 2000–present | Daily pixel (375m–1km) | Sample | [→](catalog/climate/wildfire-detections.md) |
| ERA5 Wind Data (ECMWF) | Global, 1940–present | Grid cell (0.25°), hourly | No | [→](catalog/climate/era5-wind.md) |
| Environmental Performance Index | Global (180 countries), 2002–present | Country | No | [→](catalog/climate/environmental-performance-index.md) |
| Global Sustainable Competitiveness Index | Global (180 countries), annual | Country-year | No | [→](catalog/climate/global-sustainable-competitiveness-index.md) |
| Climate Litigation Database | Global (198+ jurisdictions), 1986–present | Case-level | No | [→](catalog/climate/climate-litigation.md) |
| Climate Protest Tracker | Global, 2022–present | Event-level | No | [→](catalog/climate/climate-protest-tracker.md) |
| Climate Transparency Platform | Global, ongoing | Country/Project | No | [→](catalog/climate/climate-transparency-platform.md) |
| Disaster Dollar Database | US, 2003–present | Incident-level | No | [→](catalog/climate/disaster-dollar-database.md) |
| NOAA Billion-Dollar Disasters | US, 1980–2024 | Event-level | No | [→](catalog/climate/noaa_billion_dollar_disasters.md) |
| SCP-HAT | Global (164 countries), 1990–2024 | Country-sector-year | No | [→](catalog/climate/scp-hat.md) |
| UN Biodiversity Lab | Global, varies | Spatial layer/Country | No | [→](catalog/climate/un-biodiversity-lab.md) |
| Water Resource Vulnerability Monitor | Global (~166 countries), 2000–2023 | Country-year | No | [→](catalog/climate/water-resource-vulnerability.md) |
| Global Marine Fisheries Catch | Global, 1950–2014 | Cell-year-country-taxon | No | [→](catalog/climate/global-marine-fisheries-catch-1950-2014.md) |
| Project Cosmos (Carbon Brief) | Global, 1990–2025 | Publication / Author / Institution | No | [→](catalog/climate/project-cosmos.md) |
| ClimaMeter | Global, 2017–present | Extreme weather event | No | [→](catalog/climate/climameter.md) |
| Net Zero Tracker | Global (~4,190 entities: nations, regions, cities, companies) | Entity | No | [→](catalog/climate/net-zero-tracker.md) |

---

### 🏛️ Governance

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| Fragile States Index | Global (179 countries), 2005–present | Country-year | No | [→](catalog/governance/fragile-states-index.md) |
| State Resilience Index | Global, recent | Country | No | [→](catalog/governance/state-resilience-index.md) |
| Corruption Perceptions Index | Global, annual | Country-year | No | [→](catalog/governance/corruption-perceptions-index.md) |
| Global Corruption Barometer | Selected countries, periodic | Individual (survey) | No | [→](catalog/governance/global-corruption-barometer.md) |
| Freedom in the World (Freedom House) | Global (210 countries), 1972–present | Country-year | No | [→](catalog/governance/freedom-house.md) |
| Democracy Index (EIU) | Global (167 countries), 2006–present | Country-year | No | [→](catalog/governance/democracy-index.md) |
| World Press Freedom Index | Global (180 countries), 2002–present | Country-year | No | [→](catalog/governance/press-freedom-index.md) |
| Academic Freedom Index | Global, recent | Country | No | [→](catalog/governance/academic-freedom-index.md) |
| DemSpaces | Global (169 countries), 1970–2020 + forecasts | Country | No | [→](catalog/governance/demspaces.md) |
| Pandemic Backsliding Project (PanDem) | Global (144 countries), 2020–2021 | Country-quarter | No | [→](catalog/governance/pandem.md) |
| InforMEA | Global, 1971–present | Treaty/Country-year | No | [→](catalog/governance/informea.md) |
| Silencing Science Tracker | US, Nov 2016–present | Incident | Yes (CSV) | [→](catalog/governance/silencing-science/silencing-science-tracker.md) |

---

### 📈 Development & Wellbeing

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| Human Development Index | Global (~193 countries), 1990–present | Country-year | No | [→](catalog/development-wellbeing/human-development-index.md) |
| Global Multidimensional Poverty Index | ~110 developing countries, annual | Country | No | [→](catalog/development-wellbeing/multidimensional-poverty-index.md) |
| Gender Development Index / GII | Global, annual | Country-year | No | [→](catalog/development-wellbeing/gender-development-index.md) |
| Social Institutions and Gender Index | Global (~180 countries), periodic | Country | No | [→](catalog/development-wellbeing/social-institutions-gender-index.md) |
| World Inequality Report 2026 | Global, historical–2025 | Country | No | [→](catalog/development-wellbeing/world-inequality-report.md) |
| Global Health Security Index | Global (195 countries), 2019/2021 | Country | No | [→](catalog/development-wellbeing/global-health-security-index.md) |
| World Happiness Report | Global (~150 countries), 2012–present | Country-year | No | [→](catalog/development-wellbeing/happiness-world-report.md) |
| Good Country Index | Global (163 countries), periodic | Country | No | [→](catalog/development-wellbeing/good-country-index.md) |
| World Giving Index | Global (~140 countries), annual | Country-year | No | [→](catalog/development-wellbeing/world-giving-index.md) |
| Formal Bilateral Influence Capacity Index | Global (dyadic), 1960–recent | Country-dyad-year | No | [→](catalog/development-wellbeing/formal-bilateral-influence-capacityindex.md) |
| Henley Private Wealth Migration Report | Global, annual | Country | No | [→](catalog/development-wellbeing/wealth-migration.md) |
| World Bank Atlas of Global Development | Global, varies | Mixed | No | [→](catalog/development-wellbeing/world-bank-atlas-global-development.md) |
| DEMSCORE | Global, various | Various | No | [→](catalog/development-wellbeing/demscore.md) |
| WID.world (World Inequality Database) | Global (100+ countries), 18th century–present | Country-year-percentile | No | [→](catalog/development-wellbeing/wid-world.md) |
| Marketplace Activity Index | Ethiopia (1,776 markets), 2017–2024; validation in Kenya/Malawi/Mozambique | Market-day/week | No | [→](catalog/development-wellbeing/marketplace-activity-index.md) |
| HungerMap LIVE | Global (~94 countries), near-daily since 2020 | Country / admin-1 | No | [→](catalog/development-wellbeing/hungermap-live.md) |

---

### 🔌 Infrastructure

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| PowerOutage.us | US/Canada/UK, real-time + historical | Utility/County | No | [→](catalog/infrastructure/poweroutage-us.md) |
| Humanitarian OpenStreetMap Team (HOT) — HDX Data | Global (249 countries/territories), rolling | Feature-level (road/building/POI) | No | [→](catalog/infrastructure/hot-osm-hdx.md) |

---

## Dataset Card Template

Every file in `catalog/` follows this format. Copy it when adding a new source.

```markdown
# [Dataset Name]

**Theme:** [e.g. Conflict / Climate / Surveys / Trade / Health]
**Coverage:** [Geographic scope + time range]
**Unit of observation:** [Event / Individual / Country-year / Pixel / etc.]
**Temporal granularity:** [Daily / Monthly / Annual / etc.]
**Format:** [CSV / API / Shapefile / etc.]
**Access:** [URL] — [free / registration required / subscription]
**License:** [e.g. CC BY, non-commercial academic, restricted]
**Last verified:** [Month Year]

***

## Key Variables

| Variable | Description |
|----------|-------------|
| `var_name` | What it measures |

***

## Potential Research Questions

- Question 1
- Question 2

***

## Notes & Quirks

Any gotchas, merge keys, coordinate systems, or known data quality issues.

***

## How to Access

Step-by-step instructions or a link to a script in `scripts/`.
```

---

## Thematic Areas

This catalog covers data relevant to the following research areas:

- **Environmental economics** — pollution, natural disasters, resource use, firm behavior
- **Conflict & peace studies** — armed conflict events, protest, state repression
- **Climate policy** — net zero commitments, NDCs, carbon markets
- **Surveys & welfare** — self-reported wellbeing, preferences, political attitudes
- **Geospatial** — satellite-derived environmental and demographic data

---

## Adding a New Dataset

1. Copy the template above into a new `.md` file under the appropriate `catalog/[theme]/` subfolder
2. Fill in all fields — leave nothing blank (write *Unknown* if unsure)
3. Add a row to the Dataset Index table in this README
4. If you have a fetch/download script, add it to `scripts/` with a matching name

---

## Notes

- Maintained by [Hariaksha Gunda](https://github.com/Hariaksha)
- For personal research use; links and access instructions reflect availability as of the dates noted in each card
- Dataset availability, licensing, and access requirements may change — always verify before use in a project
