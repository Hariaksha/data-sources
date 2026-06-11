# SCP-HAT – Sustainable Consumption and Production Hotspot Analysis Tool

**Theme:** Environmental Economics / Sustainable Consumption & Production / Climate / Development  
**Coverage:** 164 countries; 1990–2024 (updated via economic proxies in v3.0); global supply chains traced through multi-regional input-output analysis  
**Unit of observation:** Country / Economic sector (97-sector disaggregation for most countries; 26-sector for limited-data countries) / Year  
**Temporal granularity:** Annual, 1990–2024  
**Format:** Interactive web tool with downloadable data (CSV); National Data, Sectoral Data, and Trade Data tabs; custom selection or full dataset export  
**Access:** https://scp-hat.org and https://scp-hat.org/data-download/ — free, no registration required  
**License:** Open source data to the extent possible; data sources governed by respective providers (GLORIA, World Bank, UN IRP); cite the tool and technical documentation when used in research  
**Last verified:** June 2026

---

## Background

SCP-HAT is an online application developed under the **UN Environment Programme (UNEP) Life Cycle Initiative** and maintained in collaboration with FAO and the Global Life Cycle Assessment Platform. It uses **Environmentally Extended Multi-Regional Input-Output (EE-MRIO) analysis** combined with **Life Cycle Impact Assessment (LCIA)** — specifically the ReCiPe method — to estimate environmental pressures and impacts across global supply chains for nearly all countries in the world[web:7][web:10]. Version 3.0 (2024) extends coverage through 2024 and incorporates methodological refinements documented in the technical documentation[web:12].

---

## Key Variables

### Environmental Pressure Indicators (physical flows)

| Indicator | Description |
|-----------|-------------|
| Raw material use | Total domestic and imported material extraction (tonnes) |
| Land use | Agricultural and non-agricultural land area used in production/consumption |
| Primary energy | Total primary energy consumption (TJ) |
| Blue water consumption | Freshwater withdrawal and consumption in production processes |

### Environmental Impact Indicators (damage-based, via ReCiPe LCIA)

| Indicator | Description |
|-----------|-------------|
| Mineral depletion | Depletion of metal and mineral resources |
| Fossil fuel depletion | Depletion of oil, gas, and coal resources |
| Climate change (short-term) | Near-term GHG impact in CO₂-equivalent |
| Climate change (long-term) | Long-run warming potential in CO₂-equivalent |
| Potential species loss | Biodiversity loss from land use (species·year) |
| Air pollution (human health) | Health impacts from particulate matter and precursor emissions |
| Water scarcity | Freshwater stress accounting for regional scarcity weights |
| Marine eutrophication | Nitrogen loading to marine systems |

### Socioeconomic Indicators

Includes GDP, employment, economic value added, and Human Development Index (HDI), sourced from the World Bank Group[web:20].

---

## Two Analytical Perspectives

A defining methodological feature of SCP-HAT is that every indicator can be viewed from two perspectives[web:10][web:20]:

- **Domestic production perspective:** Environmental pressures and impacts are allocated to the country where they physically occur (territorial accounting — comparable to national GHG inventory logic)
- **Consumption footprint perspective:** Pressures and impacts are traced through global supply chains and allocated to the country of final consumption, including all upstream emissions and resource use occurring abroad

This dual-perspective framework makes SCP-HAT uniquely well-suited for distinguishing *where* environmental burdens are generated from *who* is driving them through consumption patterns.

---

## Modules

| Module | Target User | Function |
|--------|-------------|----------|
| **Module 1: Country Profile** | Policymakers, NGOs, general public | Country-level environmental performance across 7 environmental categories in policy context |
| **Module 2: SCP Hotspots** | Policy advisors and researchers | Wide range of SCP indicators at country and sector level; hotspot identification; trend and comparative analysis |
| **Module 3: National Data System** | Statisticians and technical experts | Upload national data to receive customized, country-specific results |

---

## Data Download Options

All data downloadable at https://scp-hat.org/data-download/ via three tabs[web:3]:

- **National Data:** Filter by country, environmental and socioeconomic indicators, perspective (production/consumption), unit (total/per capita/per GDP), and year range
- **Sectoral Data:** Same filters with sector-level disaggregation (up to 97 sectors)
- **Trade Data:** Supply chain and trade flow breakdowns by country and sector

Export options include selected subsets or the full dataset in CSV format.

---

## Underlying Data Sources

| Data Type | Source |
|-----------|--------|
| Input-output tables | GLORIA (Global Resource Input Output Assessment) database |
| Environmental pressure data | UN Environment International Resource Panel (IRP) Global Material Flows Database |
| Life cycle impact assessment | ReCiPe LCIA method |
| Socioeconomic data | World Bank Group |

---

## Potential Research Questions

- How do consumption-based carbon and material footprints diverge from territorial production-based accounts across income levels and regions?
- Which sectors in low- and middle-income countries are the primary drivers of embodied environmental pressures in global supply chains?
- Can SCP-HAT's consumption footprint indicators serve as explanatory variables in panel regressions on climate policy stringency, trade exposure, or development outcomes?
- How do water scarcity and land use footprints correlate with conflict incidence or food insecurity across time and country?
- What role does imported environmental burden play in the SDG 12 (sustainable consumption and production) trajectories of specific regions?
- How have national production and consumption footprints evolved across 1990–2024 for Southeast Asian or Sub-Saharan African economies relative to global averages?

---

## Notes & Quirks

- SCP-HAT uses **EE-MRIO + LCIA** — a sophisticated methodology combining economic input-output tables with environmental satellite accounts[web:20]. Results are modelled estimates, not direct measurements.
- The **dual-perspective framework** (production vs. consumption) is the tool's most valuable feature for research; always be explicit about which perspective you are using, as results can differ substantially[web:10].
- **Sector disaggregation varies by country:** Most countries use a 97-sector table; countries with limited data availability use an aggregated 26-sector version[web:20]. Confirm sector coverage for your specific countries of interest.
- Version 3.0 (2024) extends data through 2024 but uses **economic proxies** for the most recent years rather than fully updated physical data — treat recent years with appropriate caution in longitudinal analyses[web:12].
- **Units are flexible:** The download interface allows switching between total values, per capita, and per GDP — always record and report which unit is used[web:3].
- **No spatial disaggregation below country level:** All data is national or sectoral, not subnational or georeferenced. Pair with spatial datasets (e.g., UNBL, NASA FIRMS, Strata) for subnational analysis.
- The tool is endorsed by the **NDC Partnership** and aligned with UNFCCC/SDG 12 reporting frameworks, giving it strong policy credibility for application work.
- For reproducible research: download data, record version (currently v3.0), access date, indicator names, perspective, and unit.

---

## How to Access

1. Navigate to https://scp-hat.org/data-download/
2. Select a tab: **National Data**, **Sectoral Data**, or **Trade Data**
3. Filter by countries, environmental indicators, socioeconomic indicators, perspective (production/consumption), unit (total/per capita/per GDP), and year range
4. Click **Export selection** for your filtered subset or **Export full dataset** for the complete database
5. For methodology and indicator definitions, see https://scp-hat.org/methods/ and the technical documentation (v3.0, May 2024)

---

## Related Datasets in This Catalog

- `development-wellbeing/human-development-index.md` — HDI is included as a socioeconomic variable in SCP-HAT; the two can be directly linked by country-year
- `climate/environmental-performance-index.md` — EPI and SCP-HAT both assess country-level environmental performance but use different methodological frameworks; useful for triangulation
- `development-wellbeing/world-inequality-report.md` — Consumption inequality and consumption footprint data are complementary dimensions of SDG 12 analysis
- `peace-conflict/strata-unep-fao.md` — Strata's land degradation and water stress layers align thematically with SCP-HAT's land use and water scarcity footprint indicators
