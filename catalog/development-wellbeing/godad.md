# GODAD — Geocoded Official Development Assistance Dataset

**Theme:** Development & Wellbeing / Foreign Aid (subnational)
**Source:** Bomprezzi, Dreher, Fuchs, Hailer, Kammerlander, Kaplan, Marchesi, Masi, Robert & Unfried — research team centered at the University of Göttingen
**Coverage:** Aid recipients worldwide. Donors: 18 European donors and the United States (1973–2020), World Bank (1995–2023), China (2000–2021), India (2007–2014)
**Unit of observation:** Project-location (project-level file); ADM1-year and ADM2-year (aggregated files)
**Temporal granularity:** Annual (commitment, disbursement, start and closing years)
**Format:** Stata (`.dta`) and CSV — `GODAD_projectlevel`, `GODAD_adm1`, `GODAD_adm2`
**Access:** [https://godad.uni-goettingen.de](https://godad.uni-goettingen.de) · [Codebook (v1.0, July 2025)](https://godad.uni-goettingen.de/uploads/GODAD_codebook.pdf)
**License:** No explicit license stated in the codebook; the authors ask users to cite GODAD *and* each original source (OECD CRS, AidData, AFD, etc.)
**Last verified:** October 2026

---

## What It Is

GODAD locates official development assistance projects within recipient countries, so aid can be analyzed at the region (ADM1) or district (ADM2) level rather than only country-year. It combines several sources into one harmonized dataset:

- **European donors and the US:** OECD Creditor Reporting System (CRS) project records, geolocated by the GODAD team using natural language processing on project titles and descriptions (Bomprezzi et al. 2024). French projects also draw on Agence Française de Développement data, and some locations come from recipient-country Aid Information Management Systems (AidData 2016, 2017).
- **World Bank:** AidData (2017), IATI (2023), and Kersting & Kilby (2021)
- **China:** AidData's Chinese development finance data (Dreher et al. 2022; Custer et al. 2023; Goodman et al. 2024)
- **India:** Asmus et al. (2025)

Administrative boundaries follow **GADM 3.6**, so `gid_1` / `gid_2` codes can be matched to GADM shapefiles. Amounts are given in constant 2014 USD (deflated with DAC deflators) and in current USD.

**Cite as:** Bomprezzi, P., Dreher, A., Fuchs, A., Hailer, T., Kammerlander, A., Kaplan, L.C., Marchesi, S., Masi, T., Robert, C. & Unfried, K. (2025). *Wedded to Prosperity? Informal Influence and Regional Favoritism.* CESifo Working Paper No. 10969.

---

## Key Variables

**Project-level file**
- `project_id`, `project_location_id`, `donor`
- `gid_0/1/2`, `name_0/1/2` — GADM country, ADM1, ADM2
- `latitude`, `longitude`
- `startyear`, `closingyear`, `paymentyear`
- `title`, `description` — useful for text-based classification (e.g., identifying disaster or forestry projects)
- `sector_codes`, `sector_categories`, `sector_name` — OECD 3-digit sectors
- `financial_type`, `flow_class` — grant, loan, other official flows
- `comm`, `disb` — commitments and disbursements (constant 2014 USD); `_nominal` versions in current USD; separate IBRD/IDA amounts for the World Bank
- `location_count`, `comm_loc_evensplit`, `disb_loc_evensplit` — project value split evenly across its locations
- `precision_code`, `precision_crs` — how precisely each location is known
- `data_source`, `coordinates_source`

**ADM1/ADM2-year files**
- `{donor}_{type}_{sector}` — aid totals by donor (AUT, BEL, CHE, DEN, ESP, FIN, FRA, GER, GRE, ICE, IRE, ITA, LUX, NED, NOR, POR, SWE, UK, USA), type (commitments or disbursements, constant or current USD), and sector (economic infrastructure, social infrastructure, production, other)
- `projectscount_{donor}_{sector}` — number of projects
- Separate totals for India, China, and the World Bank

---

## Potential Research Questions

- Does aid flowing to Indonesian districts affect local conflict ([ACLED](../peace-conflict/acled.md), from 2015) or fire activity ([NASA FIRMS](../climate/wildfire-detections.md))? Forestry, environment, and disaster-relief projects can be identified from sector codes and project descriptions.
- Do donors reallocate aid within a country toward or away from conflict-affected districts after violence breaks out?
- Is Chinese development finance associated with different local conflict patterns than Western aid in the same countries?
- Do regions connected to political leaders receive more aid (regional favoritism), and does that targeting change local unrest?

---

## Notes & Quirks

- **Aid placement is endogenous.** Donors target poor, unstable, or politically favored places, so naive correlations between aid and conflict are uninformative. Credible designs in this literature use instruments (e.g., donor-side budget shocks interacted with a region's prior probability of receiving aid), discontinuities, or within-project timing.
- **Location values are an even split.** `*_loc_evensplit` divides a project's total equally among its locations; actual spending per location is unknown. Multi-location projects can therefore misstate local intensity.
- **Precision varies.** Some projects are known to an exact site, others only to a region or the whole country. Filter on `precision_code` / `precision_crs` before using ADM2-level data.
- **NLP geocoding for CRS data.** Locations for European and US aid were inferred from text, so coverage and accuracy depend on how detailed the project descriptions are.
- **Donor coverage periods differ** (e.g., India only 2007–2014; China only 2000–2021). Check which donors are in your window before comparing.
- **Disbursements can be negative** (refunds or ineligible expenditures recorded as negative flows).
- **GADM 3.6 boundaries** may not match the boundaries used by other datasets (e.g., ACLED's admin units, or Indonesia's district splits after redistricting). A spatial join on coordinates is often safer than merging on names.

---

## How to Access

1. Go to [https://godad.uni-goettingen.de](https://godad.uni-goettingen.de) and download the project-level and ADM1/ADM2 files
2. Read the [codebook](https://godad.uni-goettingen.de/uploads/GODAD_codebook.pdf) for variable definitions, precision codes, and sources
3. Match `gid_1` / `gid_2` to [GADM 3.6](https://gadm.org) shapefiles for mapping or spatial joins
4. See papers using the data on the GODAD site (e.g., Dreher, Pan, Schneider & Tang 2025 on aid and elections)
