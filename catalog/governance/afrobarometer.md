# Afrobarometer

**Theme:** Governance / Public Opinion & Survey Data (cross-cutting: democracy, economy, safety/security, environment)
**Source:** Afrobarometer — pan-African, nonpartisan research network (coordinated by a network of African survey/research institutions; not a single-country or single-university project)
**Coverage:** 39 African countries (as of Round 9); country coverage has expanded across rounds — Round 1 (1999–2001): 7→12 countries; Round 2 (2002–2004): 16; Round 3 (2005–2006): 18; Round 4 (2008): 20; Round 5 (2011–2013): 34; Round 6 (2014–2015): 36; Round 7 (2016–2018): 34; Round 8 (2019–2021): 34; Round 9: 39 — each round covers roughly 75% of the African continent's population
**Unit of observation:** Individual survey respondent (adult citizen), aggregatable to national and sub-national (region/urban-rural) level
**Temporal granularity:** Survey "rounds" (waves) conducted roughly every 2–3 years since 1999; not continuous/real-time
**Format:** Online Data Analysis (ODA) web tool (cross-tab builder, custom charts/tables, multi-format export); downloadable merged datasets with codebooks; questionnaires, sampling info, and survey manuals also published
**Access:** [https://www.afrobarometer.org/online-data-analysis/](https://www.afrobarometer.org/online-data-analysis/) (ODA tool) · [https://www.afrobarometer.org/data/](https://www.afrobarometer.org/data/) (downloadable merged datasets) · also mirrored via [World Bank Microdata Library](https://microdata.worldbank.org/collections/afrobarometer), [ICPSR](https://www.icpsr.umich.edu/web/ICPSR/series/162), and [DataFirst (UCT)](https://www.datafirst.uct.ac.za/)
**License:** Free to download and analyze without charge; donations appreciated but not required. No explicit named open-data license (e.g., CC) found — treat as free-to-use-with-attribution and verify specific redistribution terms if needed.
**Last verified:** July 2026

---

## What It Is

Afrobarometer is the leading pan-African public-opinion survey network, running face-to-face (tablet-assisted) interviews with randomly selected, nationally representative samples of 1,200–2,400 adult citizens per country per round, yielding a margin of error of roughly ±2–3 percentage points at 95% confidence. Interviews are conducted in the respondent's language of choice by locally trained teams, and typically take about an hour. Its slogan — "Let the people have a say" — reflects its mission to measure African citizens' own views and experiences of governance, the economy, and daily life, independent of government or donor framing.

The **Online Data Analysis (ODA)** tool is the main public interface: it lets users search by country, question, and round; build cross-tabulations by demographic variables (gender, age, education, urban/rural, etc.); track trends over time; and export custom tables/charts. Full merged datasets and codebooks are also downloadable directly, and mirrored on major data repositories (World Bank Microdata Library, ICPSR, DataFirst).

---

## Topics Covered

The questionnaire spans nine major thematic areas:

- Democracy, freedom, and citizen engagement
- Economy, poverty, and development
- Energy and infrastructure
- Environment and climate
- Health, education, and social services
- Identity, society, and gender
- Institutions, leadership, and governance
- Regional and global relations
- Safety and security

---

## Potential Research Questions

- Do citizen-reported perceptions of safety/security (Afrobarometer) track independently coded conflict-event intensity from [ACLED](../peace-conflict/acled.md) or [GDELT](../peace-conflict/gdelt.md) in the same countries and time windows?
- How do Afrobarometer's environment/climate perception questions compare to objective climate-vulnerability measures like the [Climate Conflict Vulnerability Index](../peace-conflict/climate-conflict-vulnerability-index.md)?
- Does trust in institutions/governance (Afrobarometer) predict — or respond to — changes in [Fragile States Index](fragile-states-index.md) or [Freedom House](freedom-house.md) scores over the same rounds?
- Can survey-measured economic hardship perceptions be cross-validated against independent economic-activity proxies such as the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md) or [HungerMap LIVE](../development-wellbeing/hungermap-live.md) in overlapping African countries?
- How has citizen trust in democratic institutions evolved across rounds in countries that experienced coups, conflict, or contested elections during the survey period?

---

## Notes & Quirks

- **Round-based, not continuous.** Data arrives in discrete waves every 2–3 years, not a continuous time series — treat comparisons across rounds as panel-like repeated cross-sections (same countries, generally different individual respondents), not a true individual-level panel.
- **Country coverage is not constant across rounds** — the country list has grown substantially since 1999 (7 → 39), so a full 1999–present time series only exists for the smallest, earliest-included set of countries; check per-round country lists before assuming continuity.
- **Individual-level microdata, but survey-weighted** — national/sub-national aggregates require applying the provided survey weights; naive unweighted aggregation will misrepresent urban/rural and regional population shares.
- **Interview mode has evolved** (from paper to electronic tablets) — check round-specific methodology notes if working across many rounds, since data-collection mode can introduce measurement differences.
- **No single hosting institution** — Afrobarometer is a distributed network of national partner institutions coordinated centrally; this generally doesn't affect data access but explains why mirrors exist on multiple third-party repositories (World Bank, ICPSR, DataFirst) in addition to the main site.

---

## How to Access

1. Explore and build custom cross-tabs interactively: [https://www.afrobarometer.org/online-data-analysis/](https://www.afrobarometer.org/online-data-analysis/)
2. Download full merged datasets + codebooks by round: [https://www.afrobarometer.org/data/](https://www.afrobarometer.org/data/)
3. Read survey methodology, sampling details, and questionnaires: [https://www.afrobarometer.org/surveys-and-methods/](https://www.afrobarometer.org/surveys-and-methods/)
4. Alternative access via established data repositories: [World Bank Microdata Library](https://microdata.worldbank.org/collections/afrobarometer), [ICPSR](https://www.icpsr.umich.edu/web/ICPSR/series/162), [DataFirst (UCT)](https://www.datafirst.uct.ac.za/)
5. Read published analysis (dispatches, flagship reports, scorecards): [https://www.afrobarometer.org](https://www.afrobarometer.org)
