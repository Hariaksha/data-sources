# Pandemic Backsliding Project (PanDem)

**Theme:** Governance & Civil Liberties / Democratic Backsliding
**Source:** Varieties of Democracy (V-Dem) Institute, University of Gothenburg (PIs: Amanda B. Edgell, Jean Lachapelle, Anna Lührmann, Seraphine F. Maerz)
**Geographic Coverage:** Global (144 countries)
**Time Coverage:** March 11, 2020 – June 30, 2021 (5 quarterly coding periods)
**Unit of Observation:** Country-quarter (time-series format) or country (cross-sectional format)
**Format:** Downloadable XLSX (two formats: time-series and cross-sectional); R script for index construction
**Access:** [v-dem.net/pandem.html](https://v-dem.net/pandem.html) |
[Time-Series dataset (XLSX)](https://github.com/vdeminstitute/pandem/blob/master/datasets/pandem_TS_v6.1.xlsx) |
[Cross-Sectional dataset (XLSX)](https://github.com/vdeminstitute/pandem/blob/master/datasets/pandem_CS_v6.1.xlsx) |
[Codebook (PDF)](https://github.com/vdeminstitute/pandem/blob/master/codebook/pandem_codebook.pdf) |
[GitHub repository](https://github.com/vdeminstitute/pandem)
**License:** Free to access
**Last Verified:** April 2026

---

## Description

Tracks the democratic quality of state responses to the COVID-19 pandemic across
144 countries from March 2020 to June 2021, grounded in the International Covenant
on Civil and Political Rights (ICCPR) and practice-based theories of democratic
emergency governance. Coding based on official government sources, academic databases,
IGO documents, and trusted media, with one trained research assistant per country and
principal investigator review. Produces two composite indices: (1) the **Pandemic
Violations of Democratic Standards Index (PanDem)** — the extent to which emergency
responses violated democratic norms across seven violation types (0 = no violations,
1 = severe violations); and (2) the **Pandemic Backsliding Index (PanBack)** — the risk
that pandemic emergency responses are eroding democratic institutions, weighted by a
country's pre-pandemic Liberal Democracy Index (LDI) score to capture vulnerability in
"grey zone" regimes (electoral autocracies and electoral democracies). Available in
time-series (country × quarter) and cross-sectional (country-level max/average) formats.
Current version: V6.1. Published in *Social Science and Medicine* (2021).
Relevant to research on democratic backsliding, crisis governance, and the political
economy of emergency powers.

## Key Variables

| Variable | Description |
|----------|-------------|
| `country_name` / `iso3` / `cowcode` | Country identifiers |
| `period` | Coding period (Q1 2020–Q2 2021, 5 periods) |
| `pandem` | Pandemic Violations of Democratic Standards Index (0–1; higher = more violations) |
| `panback` | Pandemic Backsliding Index (0–1; risk of democratic erosion, weighted by pre-pandemic LDI) |
| `discrim` | Type 1: Discriminatory enforcement of emergency measures (0–3) |
| `ndrights` | Type 2: Derogation of non-derogable rights under ICCPR (0–1) |
| `abusive` | Type 3: Abusive enforcement of emergency measures (0–3) |
| `nolimit` | Type 4: No time limit on emergency measures (0–3) |
| `legalchal` | Type 5: Limitations on legislative oversight and challenge (0–3) |
| `disinfo` | Type 6: Official disinformation campaigns (0–3) |
| `media` | Type 7: Restrictions on media freedom (0–3) |
| `emlaw` | Type of legal instrument used to declare emergency (1–7 categorical) |
| `v2x_liberal` | V-Dem Liberal Democracy Index in 2019 (baseline pre-pandemic democracy score) |

## Potential Research Questions

- Do countries with weaker pre-pandemic democratic institutions (lower LDI) show
  systematically higher PanBack scores, suggesting emergency power abuse?
- Which violation types (media, legislature, non-derogable rights) are most predictive
  of longer-term democratic erosion post-pandemic?
- Does the type of legal instrument used to declare a public health emergency correlate
  with the severity of rights violations?

## Merge Keys & Compatibility

- Merge with **V-Dem Dataset** via `country_name` / `cowcode` + year for
  pre- and post-pandemic democracy trend analysis using LDI, Electoral Democracy
  Index, or other V-Dem indicators
- Merge with **Freedom House** or **Democracy Index** via `iso3` + year for
  cross-validation of backsliding scores
- Merge with **Fragile States Index** via country + year to examine how state
  fragility moderates the democracy-crisis response relationship
- Combine with **Oxford COVID-19 Government Response Tracker (OxCGRT)** via
  country + date for joint analysis of stringency and democratic quality of
  emergency measures
- Link with **Climate Litigation Database** or **CCLW** via country + year to
  examine whether pandemic-era democratic erosion weakened climate governance capacity
