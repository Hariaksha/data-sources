# InforMEA — UN Information Portal on Multilateral Environmental Agreements

**Theme:** Climate Policy / Environmental Governance / International Law
**Coverage:** Global — all UN member states and territories; treaties from 1971 (Ramsar) to present
**Unit of observation:** Treaty / Country-year / Party / Decision
**Temporal granularity:** Varies by content type — treaty entry-into-force dates (one-time), COP decisions (annual/biennial), national reports (periodic), e-learning courses (rolling)
**Format:** Web portal (browse + search); no bulk download API — structured per party and treaty page
**Access:** [https://www.informea.org/en](https://www.informea.org/en) — free, no registration required
**License:** UN public information; content attribution to respective MEA secretariats
**Last verified:** June 2026

---

## Key Variables

| Variable | Description |
|----------|-------------|
| Party / Country | Which countries have ratified each MEA; browseable at `informea.org/en/countries/{iso2}` |
| Treaty ratification status | Whether a party has signed, ratified, or acceded to each agreement |
| MEA focal points | Designated national contacts per treaty per country |
| COP decisions | Decisions adopted at each Conference of the Parties, searchable by treaty and keyword |
| National reports | Periodic national implementation reports submitted under each MEA |
| Ramsar sites | Protected wetland sites listed within each party's territory |
| World Heritage sites | UNESCO World Heritage sites listed within each party's territory |
| Action plans | National biodiversity strategies, drought action plans, and similar instruments |
| E-learning courses | Free online courses covering MEA implementation and environmental law |

---

## Thematic Coverage

InforMEA aggregates data from agreements across six environmental topic clusters:

| Topic Cluster | Example Agreements |
|---------------|--------------------|
| Biological Diversity | CBD, CITES, Ramsar, CMS |
| Chemicals and Waste | Basel, Rotterdam, Stockholm, Minamata |
| Climate and Atmosphere | UNFCCC, Kyoto Protocol, Paris Agreement, Montreal Protocol |
| Environmental Governance | Aarhus Convention, Escazú Agreement |
| Land and Agriculture | UNCCD |
| Marine and Freshwater | MARPOL, UNCLOS BBNJ Agreement, London Protocol |

---

## Potential Research Questions

- Which countries have ratified the Paris Agreement but not submitted updated NDCs — and how does this correlate with governance indicators?
- Does ratification of the Basel Convention on hazardous waste predict improvements in national environmental performance scores?
- How does MEA participation density (number of treaties ratified) vary across fragile states, and does it correlate with conflict incidence?
- Which parties to the UNCCD have submitted drought management plans, and are these more common in climate-vulnerable states?
- Can treaty ratification sequences serve as a proxy for "environmental state capacity" in cross-national panel models?
- How does focal-point designation (or absence) relate to treaty implementation quality in low-income countries?

---

## Notes & Quirks

- **No bulk data export**: InforMEA is a human-navigable portal, not a structured database. Data must be scraped or manually compiled; there is no API or downloadable CSV.
- **Party-level URLs are consistent**: Country pages follow the pattern `informea.org/en/countries/{iso2}` (e.g., `/en/countries/id` for Indonesia), making programmatic scraping straightforward.
- **Treaty coverage is uneven**: Older or smaller MEAs may have incomplete decision records or missing national reports.
- **Ratification ≠ implementation**: The portal records legal ratification dates and submitted reports, but does not evaluate compliance quality — pair with EPI or governance indices for implementation analysis.
- **E-learning platform is separate**: Courses are hosted at [elearning.informea.org](https://elearning.informea.org/), not the main portal.
- **Map disclaimer**: Boundary designations on the Parties map do not imply UN endorsement of disputed territories.
- **Good merge key**: ISO 2-letter country codes used in URLs align with most standard country-level datasets (World Bank, ACLED, UCDP).

---

## How to Access

1. **Browse by party**: Navigate to [https://www.informea.org/en/countries](https://www.informea.org/en/countries) and select a country, or go directly to `https://www.informea.org/en/countries/{iso2}`.
2. **Browse by treaty**: Go to [https://www.informea.org/en/treaties](https://www.informea.org/en/treaties) for a full treaty index.
3. **Browse by topic**: The homepage offers topic clusters (Biological Diversity, Climate and Atmosphere, etc.) as entry points.
4. **Search**: Full-text search at [https://www.informea.org/en](https://www.informea.org/en) covers treaties, parties, decisions, and cases.
5. **Scraping**: Country pages follow predictable URL patterns. A script that iterates over ISO-2 codes can systematically collect ratification data. See `scripts/` for a potential fetch script (to be added).

---

## Related Datasets in This Catalog

- [`catalog/climate/net-zero-tracker.md`](../climate/net-zero-tracker.md) — tracks net-zero pledges, many of which are tied to UNFCCC commitments visible on InforMEA
- [`catalog/climate/environmental-performance-index.md`](../climate/environmental-performance-index.md) — can be used alongside ratification data to assess implementation gaps
- [`catalog/governance/fragile-states-index.md`](../governance/fragile-states-index.md) — useful for examining MEA participation in fragile state contexts
- [`catalog/governance/corruption-perceptions-index.md`](../governance/corruption-perceptions-index.md) — pairs well for governance-MEA compliance analysis
