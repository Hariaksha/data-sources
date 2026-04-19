# Democratic Space Barometer (DemSpaces)

**Theme:** Governance & Democratic Backsliding / Forecasting
**Source:** Varieties of Democracy (V-Dem) Institute, University of Gothenburg (Andreas Beger / Basil Analytics, Richard K. Morgan, Laura Maxwell); conceptual framework adapted from the International Republican Institute (IRI) Closing Space Barometer
**Geographic Coverage:** Global (169 countries)
**Time Coverage:** Historical data: 1970–2020 (V-Dem); Forecasts: 2-year rolling window (latest: 2022–2023)
**Unit of Observation:** Country × space × forecast window (opening or closing event probability)
**Format:** Interactive dashboard (R Shiny); downloadable forecast CSVs and archived data via GitHub
**Access:** [v-dem.net/demspace](https://v-dem.net/demspace) |
[GitHub repository](https://github.com/vdeminstitute/demspaces) |
[Forecast archive](https://github.com/vdeminstitute/demspaces/tree/main/archive)
**License:** Free to access
**Last Verified:** April 2026

---

## Description

A probabilistic forecasting tool that estimates the likelihood a country will experience
a significant **opening event** (shift toward more democratic governance) or **closing event**
(shift toward more autocratic governance) across six dimensions of democratic space within
a two-year window. Built on a historical country-year panel from 1970–2020 using V-Dem
indices, the barometer trains 12 random forest classification models — one opening and one
closing model per space — to produce country-level risk scores. Outcome events are defined
as year-to-year changes in each underlying V-Dem index that exceed empirically derived
space-specific thresholds. Opening and closing probabilities are non-mutually exclusive:
a country can simultaneously face high risk of both (indicating a "crossroads" moment).
Developed as a DRG (Democracy, Human Rights, and Governance) assistance planning tool in
collaboration with USAID-affiliated partners. Forecasts have been updated annually since
2019 (v9) and are archived through v15. Current forecast cycle: 2022–2023.
Relevant to research on democratic backsliding, autocratization, civil society space, and
governance risk forecasting.

## Key Variables

**Six Democratic Spaces (each measured with a V-Dem index, 0–1 scale):**

| Space | Dimension | Underlying V-Dem Index |
|-------|-----------|------------------------|
| Associational | Civil society autonomy and participation | Core Civil Society Index (`v2xcs_ccsi`) |
| Economic | Public sector corruption | Public Corruption Index (`v2x_pubcorr`) |
| Electoral | Citizens' check on government via elections | Vertical Accountability Index (`v2x_veracc`) |
| Governing | Legislative and judicial checks on executive | Horizontal Accountability Index (`v2x_horacc`) |
| Individual | Personal freedoms, rule of law, property rights | Equality Before the Law and Individual Liberty Index (`v2x_egal`) |
| Informational | Media freedom, press censorship, expression | Freedom of Expression and Alt. Info Index (`v2x_freexp_altinf`) |

**Forecast Output Variables (per country × space):**

| Variable | Description |
|----------|-------------|
| `pr_closing` | Estimated probability of ≥1 closing event in the 2-year window |
| `pr_opening` | Estimated probability of ≥1 opening event in the 2-year window |
| `pr_neither` | Estimated probability of no opening or closing event |
| `country_name` / `gwcode` | Country identifier (Gleditsch-Ward code) |
| `year` | Forecast base year |
| `space` | Democratic space dimension (associational, economic, electoral, governing, individual, informational) |

## Potential Research Questions

- Which democratic spaces show the highest forecast closing risk in a given region,
  and do these precede actual democratic erosion events in subsequent years?
- How does the accuracy of random forest closing event forecasts compare across
  space types and regime categories (electoral democracy vs. electoral autocracy)?
- Can DemSpaces closing probabilities be used as leading indicators of climate
  policy rollback or reduced environmental governance capacity?

## Merge Keys & Compatibility

- Merge with **V-Dem Dataset** via `gwcode` / `country_name` + year to combine
  forecasts with any of the 500+ V-Dem indicators for covariate analysis
- Merge with **PanDem / PanBack** via `country_name` + year to examine whether
  pandemic-era democratic violations predict DemSpaces closing risk
- Merge with **Freedom House** or **ERT Dataset** via country + year for
  cross-validation of opening/closing event classifications
- Merge with **Climate Litigation Database** or **CCLW** via country + year
  to examine whether democratic space closures reduce climate law adoption or
  litigation activity
- Merge with **Fragile States Index** via `iso3c` + year for joint fragility-
  backsliding risk analysis
