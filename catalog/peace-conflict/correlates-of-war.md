# Correlates of War (COW)

**Theme:** Conflict & International Relations (interstate war, state capabilities)
**Source:** Correlates of War Project, founded in 1963 by J. David Singer at the University of Michigan
**Coverage:** Global, 1816–present (end years vary by dataset; several stop well before the present)
**Unit of observation:** Country-year, dyad-year, war, or dispute (no subnational or event-level data)
**Temporal granularity:** Annual; datasets updated irregularly, often years apart
**Format:** CSV and Stata files with codebooks, by dataset
**Access:** [https://correlatesofwar.org/data-sets/](https://correlatesofwar.org/data-sets/) — free, no registration; much of it is also bundled in the R package [`peacesciencer`](https://search.r-project.org/CRAN/refmans/peacesciencer/html/cow_nmc.html)
**License:** Free for research use with citation; check each dataset's documentation for its citation and terms
**Last verified:** October 2026

---

## What It Is

COW is the foundational collection of datasets for the quantitative study of war and international relations. It began in the 1960s to find the "correlates" of interstate war, and its definitions of states, wars, and disputes became standards in the field. Its datasets are mainly at the country-year or country-pair (dyad) level and are most useful for international and country-level analysis.

---

## Main Datasets

| Dataset | Contents | Coverage |
|---------|----------|----------|
| **State System Membership** | Which entities count as states, and when | 1816– |
| **War Data** (interstate, intrastate v5.1, extrastate, non-state) | Wars with at least **1,000 battle deaths** | 1816– |
| **Militarized Interstate Disputes (MIDs)** v5 | Threats, displays, and uses of force between states | 1816–**2014** |
| **MID Locations** v2.1 | Where disputes occurred | 1816–2010 |
| **National Material Capabilities (NMC)** v7 | Military spending, military personnel, energy use, iron and steel production, urban population, total population; feeds the **CINC** power score | 1816–**2022** |
| **Formal Alliances** | Defense pacts, neutrality, non-aggression, and entente agreements | 1816– |
| **Diplomatic Exchange**, **Intergovernmental Organizations**, **Trade** | Diplomatic ties, IGO memberships, bilateral trade | Various |
| **Territorial Change**, **Direct/Colonial Contiguity**, **World Religion** | Border changes, shared borders, religious composition | Various |

---

## Key Variables

- `ccode` — **COW country code**, used as the country identifier across many political science datasets (including Voeten's UN General Assembly voting data)
- `stateabb` — three-letter state abbreviation
- `year`
- NMC: `milex`, `milper`, `irst`, `pec`, `tpop`, `upop`, `cinc`
- War and MID data: start and end dates, participants, side, fatality level, hostility level, outcome

---

## Potential Research Questions

- Do changes in a state's material capabilities (CINC) predict its likelihood of entering militarized disputes or wars?
- Are country-level controls from COW (capabilities, alliances, contiguity) needed when estimating cross-country effects of climate shocks on conflict?
- Do alliance ties shape how countries vote on UN General Assembly resolutions targeting an ally?

---

## Notes & Quirks

- **No subnational data.** COW is country- or dyad-year only, so it's of little direct use for district-level conflict or wildfire analysis. Use [UCDP GED](ucdp.md) or [ACLED](acled.md) for that.
- **High war threshold.** Wars require 1,000 battle deaths, so COW misses most low-intensity violence. UCDP's 25-death threshold captures far more conflicts; the two aren't interchangeable.
- **Slow updates.** MIDs end in 2014, and other series lag by years. Check end dates before building a recent panel.
- **Main value is as a merging key and control source.** COW country codes link many datasets, and NMC/CINC and alliance data are standard country-level controls. Watch for mismatches between COW codes and ISO3 codes (e.g., Germany, Serbia, and Yemen across historical boundary changes).
- **Interstate focus.** The project's core is war between states; its intrastate and non-state war data is less detailed than UCDP's.

---

## How to Access

1. Browse and download datasets: [https://correlatesofwar.org/data-sets/](https://correlatesofwar.org/data-sets/)
2. NMC v7 (capabilities and CINC): [https://correlatesofwar.org/data-sets/national-material-capabilities/](https://correlatesofwar.org/data-sets/national-material-capabilities/)
3. In R, load and merge COW data with [`peacesciencer`](https://search.r-project.org/CRAN/refmans/peacesciencer/html/cow_nmc.html)
4. Cite the article listed in each dataset's codebook
