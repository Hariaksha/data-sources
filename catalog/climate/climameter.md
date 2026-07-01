# ClimaMeter

**Theme:** Climate & Environment / Extreme Event Attribution
**Source:** ClimaMeter consortium, hosted by Institut Pierre Simon Laplace (IPSL); funded by the European Union and CNRS
**Coverage:** Global; events from 2017–present
**Unit of observation:** Extreme weather event (individual episode)
**Temporal granularity:** Event-level (each report covers a specific date range); ClimaMonitor sub-tool provides daily analyses for Europe
**Format:** Web platform — event report pages (narrative + maps + gauges); no bulk download
**Access:** [https://www.climameter.org](https://www.climameter.org) — free, no registration required
**License:** CC BY-NC-ND 4.0 — free to share with attribution, non-commercial, no derivatives
**Last verified:** June 2026

---

## What It Is

ClimaMeter is a rapid extreme-event attribution framework. For any major extreme weather event, it produces a report answering: *how much did human-caused climate change alter the meteorological conditions behind this event?*

The approach is analogue-based — it identifies historical days with similar surface pressure patterns to the event of interest, splits the historical record into a "past" (weaker anthropogenic signal) and "present" (stronger signal) period, and compares temperature, precipitation, and wind conditions across those analogues. This makes it fast, transparent, and reproducible without relying on climate model simulations.

The methodology is peer-reviewed: Faranda et al. (2024), *Weather and Climate Dynamics* — [https://wcd.copernicus.org/articles/5/959/2024/](https://wcd.copernicus.org/articles/5/959/2024/)

---

## Hazard Types Covered

The **Hazard Database** ([/hazard-database](https://www.climameter.org/hazard-database)) archives all past event reports, organized into five categories:

| Hazard type | Examples |
|-------------|---------|
| **Heavy Precipitation** ☔ | Floods, tropical cyclones, atmospheric rivers, storms |
| **High Temperatures** 🌡 | Heatwaves (regional and global) |
| **Strong Winds** 🌬️ | Hurricanes, cyclones, extratropical storms, tornadoes |
| **Wildfires** 🔥 | Fire-weather conditions driving active wildfire events |
| **Low Temperatures** 🧊 | Cold spells, winter storms, snowstorms |

---

## Key Metrics in Each Event Report

Each event report contains the following outputs:

| Output | Description |
|--------|-------------|
| **Attribution gauge** | % attribution to human-induced climate change vs. natural variability (0–100 scale) |
| **Rarity gauge** | How exceptional the event was relative to the historical distribution (percentile-based; e.g., "Very Exceptional Meteorological Event" = >95th percentile in both past and present periods) |
| **Anomaly maps** | Surface pressure and temperature anomalies for the event relative to the full historical mean |
| **Change maps** | Difference in analogue conditions between "past" and "present" periods, for pressure, temperature, precipitation, and wind |
| **Quantitative Δ** | Reported changes in temperature (°C), precipitation (mm/day), and wind speed associated with present vs. past analogues |
| **Natural variability assessment** | Whether ENSO, AMO, or PDO phases explain any of the differences observed between past and present analogues |

---

## Data Sources Underlying the Methodology

| Period | Primary data | Variables | Spatial resolution |
|--------|-------------|-----------|-------------------|
| Before Dec 6, 2024 | MSWX reanalysis | Pressure, T2m, precipitation, wind speed | Native MSWX |
| Dec 6, 2024–present | ERA5 (CDS) + GFS forecasts | msl, t2m, tp, u10, v10 | 0.25° × 0.25°; resampled to 0.5° |

ERA5 historical coverage starts from 1950; GFS fills the gap for very recent days not yet in ERA5.

---

## ClimaMonitor (Daily Sub-Tool)

[ClimaMonitor](https://www.climameter.org/climamonitor) is a daily automated extension of ClimaMeter focused on Europe. It runs the same analogue framework each day on current European weather conditions to provide near-real-time attribution context, before a full event report is warranted.

---

## Potential Research Questions

- Does rapid event attribution systematically differ from model-based attribution in direction or magnitude, and under what conditions?
- How has the climate change signal in extreme event attribution evolved over the ClimaMeter record (2017–present)?
- Are certain hazard types (heatwaves vs. precipitation events vs. wind events) showing stronger or more consistent attribution signals over time?
- Can ClimaMeter attribution scores be used as a covariate in conflict or displacement event studies (e.g., linking extreme weather to social unrest)?
- How do attribution results for the same geographic region vary across seasons and event types?
- What is the relationship between event rarity scores and downstream socioeconomic impacts?

---

## Notes & Quirks

- **Not a downloadable dataset.** ClimaMeter publishes individual event reports as web pages, not structured data files. For quantitative use, you would need to manually extract figures from reports or contact the consortium.
- **Analogue method ≠ model-based attribution.** This approach uses observed historical reanalysis data rather than counterfactual climate model runs. It is faster but cannot fully isolate the forced response from internal variability.
- **Data source changed December 2024.** Reports before Dec 6, 2024 used MSWX reanalysis; later reports use ERA5 + GFS. Results are not directly comparable across this break without adjustment.
- **"Past" vs. "present" split is relative.** The historical record is divided into two equal halves, so the exact split date depends on the event date and the dataset used. This is not a fixed calendar threshold.
- **Natural variability flag.** When ENSO, AMO, or PDO phases significantly explain the past–present difference, the attribution gauge adjusts toward "natural variability." This is flagged in the report text.
- **Coverage is event-driven, not systematic.** Events are chosen based on newsworthiness and scientific interest — the database is not a complete census of all extreme events in the period.
- **ClimaMonitor is Europe-only** for daily analysis; individual event reports are global.

---

## How to Access

1. Browse all event reports by hazard type at: [https://www.climameter.org/hazard-database](https://www.climameter.org/hazard-database)
2. Access the interactive Event Dashboard at: [https://www.climameter.org/event-dashboard](https://www.climameter.org/event-dashboard)
3. Access daily European attribution via ClimaMonitor: [https://www.climameter.org/climamonitor](https://www.climameter.org/climamonitor)
4. For research collaboration or data access requests, contact via: [https://www.climameter.org/contact](https://www.climameter.org/contact)
5. Peer-reviewed papers using the framework are listed at: [https://www.climameter.org/peer-reviewed-research](https://www.climameter.org/peer-reviewed-research)

**Cite methodology as:** Faranda, D. et al. (2024). *Attributing Venice Acqua Alta events to a changing climate and evaluating the MOSE surge barriers*. Weather and Climate Dynamics. [https://wcd.copernicus.org/articles/5/959/2024/](https://wcd.copernicus.org/articles/5/959/2024/)
