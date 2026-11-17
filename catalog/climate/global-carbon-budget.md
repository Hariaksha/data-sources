# Global Carbon Budget (GCB)

**Theme:** Climate / Carbon Emissions and Sinks
**Source:** Global Carbon Project; the Global Carbon Budget Office is led by Pierre Friedlingstein (University of Exeter), with 100+ contributors from 70 organizations in 18 countries
**Coverage:** Global and national (country-year); historical series with projections for the current year. Gridded maps for selected periods
**Unit of observation:** World-year (global budget), country-year (national fossil and land-use change emissions), grid cell (gridded fluxes)
**Temporal granularity:** Annual; a new edition comes out each year at the UN climate summit (COP). GCB 2026 released November 2026
**Format:** Excel (global and national data), netCDF (gridded data), PDF dataset descriptions, figures, and slides
**Access:** [https://globalcarbonbudget.org](https://globalcarbonbudget.org) · [2026 data hub](https://globalcarbonbudget.org/data-hub/the-latest-gcb-data-2026/) · [Zenodo archive](https://doi.org/10.5281/zenodo.23723209) — free, no registration
**License:** Free to use under the GCB fair use statements: cite Friedlingstein et al. (2026, *ESSD*), add the requested acknowledgement, and for ocean data also cite the original model and data products. Offering co-authorship to the contributing groups is encouraged if the data is central to a paper
**Last verified:** November 2026

---

## What It Is

The Global Carbon Budget is the scientific community's main annual estimate of the global CO₂ budget: how much CO₂ human activity emits, and where it goes. It has been published every year since 2006 and is written up as a peer-reviewed paper in *Earth System Science Data* (Friedlingstein et al.).

The budget balances sources against where the carbon ends up:

| Sources | Where it goes |
|---------|---------------|
| Fossil CO₂ emissions (coal, oil, gas, cement, flaring) | Growth of CO₂ in the atmosphere |
| Emissions from land-use change (deforestation, other land conversion, minus regrowth) | Ocean sink (absorbed by the ocean) |
| | Land sink (absorbed by vegetation and soils) |

Whatever doesn't balance is reported as the **budget imbalance**, a measure of what the estimates fail to explain.

---

## Datasets (2026 Data Hub)

| File | Contents |
|------|----------|
| Global Carbon Budget v2026 (xlsx) | Annual global sources, sinks, and imbalance |
| National fossil carbon emissions v2026 (xlsx) | Fossil CO₂ emissions by country and year |
| National land use change carbon emissions v2026 (xlsx) | Land-use change emissions by country and year |
| Gridded fossil and land-use emissions (netCDF) | Average for 2016–2025 |
| Gridded ocean and land carbon fluxes (netCDF) | Model and data-product estimates, average for 2016–2025, including responses to rising CO₂ and changing climate |
| Land carbon flux, two-method comparison (netCDF) | Gridded, 1990–2025 |
| Surface fCO₂ and air–sea CO₂ flux (external) | Gridded by longitude, latitude, and time |

Check the dataset descriptions file for each series' start year and units.

---

## 2026 Findings

- Fossil CO₂ emissions are projected to fall 0.4% in 2026, to 38.2 billion tonnes. Oil emissions fall 1.9%, which the authors attribute partly to the energy shock from the Iran conflict.
- Total CO₂ emissions, including land-use change, are projected at 43.3 billion tonnes, up from 42.8.
- The remaining carbon budget for 1.5°C is about 150 billion tonnes, under four years of current emissions.
- By country: China −0.9%, US −1.3%, EU −1.5%, Japan −1%, India +4.4%.
- The land sink recovered after weakening sharply during the 2023–24 El Niño. The authors expect the strong 2026 El Niño to have a significant impact in the coming year.

---

## Key Variables

- Year, country
- Fossil CO₂ emissions (territorial; consumption-based estimates may be included; check the national file)
- Land-use change emissions
- Atmospheric CO₂ growth, ocean sink, land sink, budget imbalance
- Uncertainty ranges (reported in the paper)

Units are often in carbon (GtC or MtC), not CO₂. Multiply by 3.664 to convert carbon to CO₂.

---

## Potential Research Questions

- How large are Indonesia's land-use change emissions in severe fire years (e.g., 2015, 2019, 2023) compared with normal years, and how do they compare with fire emission estimates from [NASA FIRMS](wildfire-detections.md)-based inventories such as GFED?
- Do countries' net-zero targets ([Net Zero Tracker](net-zero-tracker.md)) predict later changes in their actual fossil emissions?
- Did conflicts and energy shocks (e.g., Russia–Ukraine in 2022, the Iran conflict in 2026) lower emissions temporarily, and did emissions rebound?
- Do El Niño years weaken the land sink in a way that can be linked to tropical fire seasons?

---

## Notes & Quirks

- **Estimates are revised every year.** Each edition updates the whole historical series, and current-year numbers are projections from partial-year data. Record the version you use and don't mix editions. The 2026 files are labeled v0.1, so corrections may follow.
- **Land-use change is much less certain than fossil emissions.** National land-use estimates come from models and carry large uncertainty; check the paper's uncertainty tables before using them as a precise outcome.
- **Country-year only, apart from averaged grids.** No subnational yearly series, so it can't separate provinces or individual fire events. Most gridded files are 10-year averages, not yearly maps.
- **Carbon versus CO₂.** Files are often in units of carbon. Mixing them up gives errors of about 3.7 times.
- **CO₂ only.** It doesn't cover methane or other greenhouse gases; the Global Carbon Project publishes separate methane and nitrous oxide budgets.
- **Different from official national inventories.** Land-use emissions are defined differently than in countries' UN climate reports, so the two often disagree, especially for forest-rich countries such as Indonesia and Brazil.

---

## How to Access

1. Download the data: [https://globalcarbonbudget.org/data-hub/the-latest-gcb-data-2026/](https://globalcarbonbudget.org/data-hub/the-latest-gcb-data-2026/)
2. Earlier editions (2022–2025) and the full report, slides, figures, and country charts: [https://globalcarbonbudget.org/gcb-2026/](https://globalcarbonbudget.org/gcb-2026/)
3. Zenodo archive: [https://doi.org/10.5281/zenodo.23723209](https://doi.org/10.5281/zenodo.23723209)
4. Browse emissions by country in the [Global Carbon Atlas](https://globalcarbonatlas.org)
5. Cite: Friedlingstein et al. (2026). Global Carbon Budget 2026. *Earth System Science Data*. Follow the [fair use statements](https://globalcarbonbudget.org/data-hub/the-latest-gcb-data-2026/) for acknowledgements.
