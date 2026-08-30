# Google Research — Heat Resilience (Rooftop Albedo)

**Theme:** Climate & Environment / Urban Heat Mitigation
**Source:** Google Research
**Coverage:** ~50 cities across 14 countries/regions — Argentina, Australia, Brazil (broadest coverage, 16 cities), Greece, India, Indonesia, Kenya, Mexico, Nigeria, Pakistan, South Africa, Spain, United Kingdom, United States
**Unit of observation:** Individual building (albedo value associated with building centroid/rooftop footprint)
**Temporal granularity:** Initial release is a single snapshot; the project states an intent to provide "periodic refreshes... subject to imagery availability" but no fixed schedule as of last verification
**Format:** Interactive Earth Engine App (pan/zoom, neighborhood aggregation, building-level inspection); bulk downloads as zipped, GIS-compatible files organized by country, with accompanying README documentation
**Access:** [https://sites.research.google/gr/heat-resilience/](https://sites.research.google/gr/heat-resilience/)
**License:** Google-derived albedo data requires attribution to Google; the alternate dataset built on Overture Maps building outlines requires additional attribution (Microsoft, USGS, and other Overture data contributors) under a mix of CC BY 4.0 and Open Database License (ODbL) terms depending on the underlying source
**Last verified:** July 2026

---

## What It Is

This Google Research project uses machine learning models on very-high-resolution satellite and aerial imagery to estimate **rooftop albedo** — the fraction of solar energy a surface reflects back into the atmosphere, on a 0–1 scale — for individual buildings across roughly 50 cities worldwide. Dark, heat-absorbing roofs typically measure 0.05–0.15 albedo; reflective "cool roofs" reach 0.60–0.85. The goal is to give city planners building-level data to target cool-roof retrofit programs, since replacing dark roofing material is one of the more cost-effective urban heat mitigation interventions, and historically under-invested neighborhoods often have the least reflective roofing and the highest heat exposure.

Two dataset variants are published for each covered city: one built on **Google's proprietary building outlines**, and one built on the **open-source Overture Maps** building footprint dataset — useful if you need a fully open-license geometry source to pair with the albedo values.

---

## Key Variables

- Building-level albedo (0–1 scale, per building centroid/footprint)
- Neighborhood-aggregated average reflectivity
- Building geometry/geospatial coordinates (via Google outlines or Overture Maps footprints)

---

## Geographic Coverage Note (Indonesia)

Indonesia is among the 14 covered countries, which is directly relevant given this catalog's focus on Indonesia wildfire-conflict dynamics — worth checking which specific Indonesian city/cities are included and whether coverage overlaps with areas of research interest before assuming applicability.

---

## Potential Research Questions

- Do low-albedo (heat-retaining) building concentrations spatially align with the lowest [Tree Equity Score](tree-equity-score.md) block groups in the small number of U.S. cities both datasets cover, suggesting compounding (rather than offsetting) heat burdens?
- In the Indonesian city/cities covered, does rooftop albedo correlate with informal settlement density, income, or proximity to industrial/urban heat sources?
- Could building-level albedo serve as a proxy for construction material/informality in rapid-urbanization contexts, complementary to methods like the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md)'s satellite-based detection approach?
- How much modeled temperature reduction would result from a hypothetical cool-roof retrofit program targeting the lowest-albedo buildings in a given city, and how does that compare to tree-canopy-based interventions (Tree Equity Score) in cost-effectiveness?

---

## Notes & Quirks

- **Snapshot, not yet a true time series** — only an initial release exists as of last verification; "periodic refreshes" are aspirational and imagery-availability-dependent, so don't assume a usable multi-year panel exists yet.
- **Two license regimes depending on which building-outline variant you use** — the Google-outlines version requires only Google attribution; the Overture-based version carries additional attribution obligations (Microsoft, USGS, and other contributors) and mixed CC BY 4.0 / ODbL terms. Check per-file documentation before redistributing.
- **Rooftop albedo only — not tree canopy or full thermal modeling.** This is a narrower, complementary dataset to something like Tree Equity Score: it measures one specific heat-mitigation lever (roof reflectivity) rather than a composite heat-vulnerability score.
- **Coverage is a curated ~50-city sample, not systematic global coverage** — cities were evidently selected for programmatic/partnership reasons (Brazil is disproportionately represented with 16 cities), not via a representative sampling design across all 14 countries.
- **Building-level granularity means large file sizes** for city-wide bulk downloads — plan accordingly if working with dense, high-rise urban cores.

---

## How to Access

1. Explore interactively via the Earth Engine App: [https://sites.research.google/gr/heat-resilience/](https://sites.research.google/gr/heat-resilience/)
2. Download zipped, GIS-ready data by country (includes README documentation) from the same project page
3. Choose between the Google building-outline dataset or the Overture Maps-based variant depending on your licensing/geometry needs
