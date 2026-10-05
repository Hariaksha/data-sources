# UCDP — Uppsala Conflict Data Program

**Theme:** Conflict & Political Violence (organized lethal violence)
**Source:** Uppsala Conflict Data Program, Department of Peace and Conflict Research, Uppsala University (Sweden); the Armed Conflict Dataset is produced jointly with the Peace Research Institute Oslo (PRIO)
**Coverage:** Global. Armed Conflict Dataset 1946–present; most other datasets, including the Georeferenced Event Dataset (GED), 1989–present
**Unit of observation:** Conflict-year, dyad-year, or actor-year (aggregate datasets); individual event (GED)
**Spatial granularity:** GED events geocoded to the village/town level where possible, with precision codes
**Temporal granularity:** Annual releases (GED v26.1 latest); monthly Candidate Events releases with about a one-month lag (v26.0.X)
**Format:** CSV and Excel downloads, codebooks, and a REST API
**Access:** [UCDP Download Center](https://ucdp.uu.se/downloads/) · [API](https://ucdp.uu.se/apidocs/) · [UCDP Conflict Encyclopedia](https://ucdp.uu.se) — free, no registration
**License:** CC BY 4.0 (cite the dataset-specific article listed in each codebook)
**Last verified:** October 2026

---

## What It Is

UCDP is the standard source for data on organized lethal violence worldwide. Its core definition: an **armed conflict** is a contested incompatibility over government or territory in which armed force between two organized parties, at least one of them a government, causes **at least 25 battle-related deaths in a calendar year**. A conflict with 1,000 or more deaths in a year is classed as a **war**.

UCDP distinguishes three types of organized violence:

| Type | Definition |
|------|------------|
| **State-based** | A government fights another state or an organized armed group |
| **Non-state** | Organized groups fight each other, with no government party (includes organized communal violence) |
| **One-sided** | A government or formally organized group deliberately kills civilians |

---

## Main Datasets

| Dataset | Unit | Coverage | Notes |
|---------|------|----------|-------|
| UCDP/PRIO Armed Conflict Dataset | Conflict-year | 1946– | The long-run country/conflict panel |
| Dyadic Dataset | Dyad-year | 1946– | Government vs. specific rebel group |
| Battle-Related Deaths Dataset | Conflict/dyad-year | 1989– | Low, best, and high death estimates |
| Non-State Conflict Dataset | Conflict-year | 1989– | Organized communal and militia violence |
| One-Sided Violence Dataset | Actor-year | 1989– | Violence against civilians |
| **Georeferenced Event Dataset (GED)** | Event (day, location) | 1989– | Most disaggregated; v26.1 |
| **Candidate Events Dataset** | Event | Recent months | Monthly, unvetted; most events later enter GED |
| Peace Agreements, Conflict Termination, External Support, Actor datasets | Various | Various | Context and covariates |

---

## Key Variables (GED)

- `id`, `relid` — event identifiers
- `type_of_violence` — 1 state-based, 2 non-state, 3 one-sided
- `conflict_new_id`, `dyad_new_id`, `side_a`, `side_b` — conflict, dyad, and actors
- `date_start`, `date_end`, `date_prec` — dates and date precision
- `latitude`, `longitude`, `where_prec` — location and location precision (exact place up to country-level only)
- `adm_1`, `adm_2`, `country`, `region`
- `priogrid_gid` — PRIO-GRID cell ID (0.5° grid), for spatial panels
- `deaths_a`, `deaths_b`, `deaths_civilians`, `deaths_unknown`
- `best`, `low`, `high` — best, lower, and upper fatality estimates
- `source_article`, `number_of_sources` — sourcing

---

## Indonesia Coverage

GED covers Indonesia from **1989**, compared with 2015 for [ACLED](acled.md). That spans the Aceh insurgency, East Timor, communal violence in Maluku and Central Sulawesi (Poso), and Papua. It also covers the 1997–98 and 2015 fire crises, giving a much longer pre-period for wildfire-conflict designs that pair GED with [NASA FIRMS](../climate/wildfire-detections.md) (2000–) and [ERA5](../climate/era5-wind.md).

---

## Potential Research Questions

- Are severe fire seasons in Indonesia followed by more organized violence, and does the effect differ between state-based and non-state (communal) violence?
- Does combining GED (1989–, lethal only) with ACLED (2015–, including protests and riots) show whether fire shocks shift conflict from non-lethal to lethal forms?
- Using the longer GED pre-period, did conflict decline in African diamond-producing areas after the Kimberley Process (2003)?
- How quickly do conflicts terminate after peace agreements, and does foreign aid ([GODAD](../development-wellbeing/godad.md)) to affected regions change recurrence?

---

## Notes & Quirks

- **Lethal violence only.** Events without deaths (most protests and riots, non-lethal repression) are excluded. Use ACLED or [SCAD](scad.md) for non-lethal social conflict.
- **Inclusion threshold.** GED includes an event only if its conflict, dyad, or actor crossed 25 deaths in some year. Small or one-off clashes below that level are missing, which undercounts low-intensity violence.
- **Fatality uncertainty.** Use `best` by default, and check robustness with `low` and `high`.
- **Location precision varies.** Filter on `where_prec` before subnational analysis; low-precision events are often assigned to a region or country centroid and can create false spatial clusters.
- **Candidate Events aren't final.** Monthly data is unvetted and some events change or drop out at the annual GED release. Don't mix candidate and final data without noting it.
- **Versions change.** Each annual release can revise earlier years; record the version you use (e.g., GED 26.1).
- **Different definitions from ACLED and COW.** UCDP's 25-death threshold and organized-actor requirement differ from ACLED's event coding and [Correlates of War](correlates-of-war.md)'s 1,000-death war threshold. Counts aren't interchangeable.

---

## How to Access

1. Download datasets and codebooks: [https://ucdp.uu.se/downloads/](https://ucdp.uu.se/downloads/)
2. Query programmatically: [UCDP API](https://ucdp.uu.se/apidocs/)
3. Browse conflicts by country and actor: [UCDP Conflict Encyclopedia](https://ucdp.uu.se)
4. Older versions for replication: [historical versions](https://ucdp.uu.se/downloads/olddw.html)
5. Cite the article named in each dataset's codebook (e.g., Sundberg & Melander 2013 for GED)
