# Tree Equity Score

**Theme:** Climate & Environment / Urban Heat & Environmental Equity
**Source:** American Forests (501(c)(3) nonprofit, Washington, DC); tree canopy layer developed in partnership with Google (Environmental Insights Explorer)
**Coverage:** Every urban area in the United States (Tree Equity Score 2.0), plus Puerto Rico and the U.S. Virgin Islands; separate UK version launched November 2024; local "Analyzer" tools with property-level detail for 15+ specific cities/regions (Austin, Boston, Columbus, Dallas, DC, Detroit, Houston, Indianapolis, Lincoln Parish, Maricopa County, Rhode Island, Richmond, Toronto, Washington State)
**Unit of observation:** U.S. Census block group
**Temporal granularity:** Cross-sectional composite score, periodically recalculated as underlying inputs (canopy imagery, Census data, Landsat heat data) are refreshed — most recent major methodology update ("2.0") used 2022 Landsat imagery and the latest Census boundaries/demographics
**Format:** Interactive web map (National Explorer + city-specific Analyzers); bulk data download as Shapefile, GeoJSON, or CSV
**Access:** [https://www.treeequityscore.org](https://www.treeequityscore.org) — free, no registration; [Data Download](https://www.treeequityscore.org/methodology?tab=data-download) (per-state files)
**License:** Not explicitly published as a named open license (no CC/public-domain declaration found on the site) — the organization states "we believe data belongs to everyone" and offers free bulk download; verify specific reuse/redistribution terms directly with American Forests before republishing.
**Last verified:** July 2026

---

## What It Is

Tree Equity Score is a composite 0–100 index scoring every U.S. Census block group in urban areas on how well the benefits of urban tree canopy (shade, cooling, air quality) reach the people who need them most. Lower scores flag neighborhoods most in need of tree-planting investment. It was built to make the case — with data — that tree canopy is not evenly distributed, and that the gaps systematically track race and income.

The score combines: **tree canopy coverage** (AI-derived from satellite/aerial imagery via Google's Environmental Insights Explorer), **land surface temperature/heat disparity** (derived from Landsat imagery, averaging the five clearest and hottest summer days), and a set of **Census-derived priority indicators** — income, employment, race/ethnicity, building/population density, age, language, and a Health Index (from the CDC PLACES dataset: self-reported mental/physical health, asthma, coronary heart disease prevalence).

Version 2.0 (rolled out through 2024–2025) expanded coverage to every U.S. urban area (not just larger cities), added cross-municipal-boundary comparison, refined canopy targets for biome-specific contexts (e.g., grassland/desert-transition cities like Austin and Southern California), and replaced the need to look up Census Block Group IDs with plain address search.

---

## Key Variables

- **Tree Equity Score** (0–100 composite index) — the headline output
- Existing tree canopy % (block-group level)
- "Ideal" or target canopy % for that block group's biome/land-use context
- Priority index components: income, employment, race/ethnicity composition, population/building density, age (children and elderly), limited-English-speaking households
- Land surface temperature / heat disparity estimate
- Health Index (from CDC PLACES: asthma, coronary heart disease, self-reported health)

---

## Potential Research Questions

- Does Tree Equity Score correlate with independently measured heat exposure or health outcomes at the neighborhood level, beyond what's already built into the score's own heat/health inputs?
- How does canopy-equity patterning in U.S. cities compare with rooftop-albedo-based heat mitigation potential mapped by [Google Research's Heat Resilience project](google-heat-resilience.md) in the small number of cities both cover?
- Can Tree Equity Score's methodology (combining canopy, heat, and socioeconomic priority indicators) be adapted as a template for an analogous "wildfire risk equity" or "climate vulnerability equity" score outside the U.S.?
- Does tree-planting investment guided by Tree Equity Score in early-adopter cities (e.g., Austin, Detroit, DC) show measurable canopy or heat improvements in a before/after comparison using the same Landsat-based heat layer?

---

## Notes & Quirks

- **Not a longitudinal panel by default** — each release reflects the latest available canopy/Census/Landsat inputs at time of calculation; comparing scores across releases (e.g., 1.0 vs. 2.0) is not a clean apples-to-apples time series because methodology, canopy targets, and geographic coverage changed between versions.
- **Composite index, not a single measured quantity** — the 0–100 score bundles canopy gap, heat, and socioeconomic priority into one number; for research use, it's often more useful to pull the underlying component variables (canopy %, heat, demographic indicators) separately via the data download rather than treating the composite score itself as the outcome of interest.
- **License terms are unusually unclear for a public-data project** — unlike most entries in this catalog, no explicit CC/public-domain license was found; the "data belongs to everyone" framing is aspirational messaging, not a formal license grant. Confirm terms before redistributing derived datasets.
- **Local Analyzer tools ≠ National Explorer data** — the property-level "Analyzer" apps for specific cities/regions may use different or more granular underlying data than the block-group-level National Explorer/bulk download; don't assume identical methodology across the two products.
- **US-centric, with one international expansion** — a UK version exists, but as of last verification this is a separate product, not integrated into the same download/API.

---

## How to Access

1. Explore interactively (National Explorer or city-specific Analyzer): [https://www.treeequityscore.org/map](https://www.treeequityscore.org/map) and [https://www.treeequityscore.org/analyzer](https://www.treeequityscore.org/analyzer)
2. Download bulk data (Shapefile, GeoJSON, or CSV, by state): [https://www.treeequityscore.org/methodology?tab=data-download](https://www.treeequityscore.org/methodology?tab=data-download)
3. Read full methodology: [https://www.treeequityscore.org/methodology](https://www.treeequityscore.org/methodology)
4. Background on the 2.0 methodology update: [American Forests — "Ushering in the next generation: Tree Equity Score 2.0"](https://www.americanforests.org/article/ushering-in-the-next-generation-tree-equity-score-2-0/)
5. Data-driven story explainers: [https://www.treeequityscore.org/stories](https://www.treeequityscore.org/stories)
