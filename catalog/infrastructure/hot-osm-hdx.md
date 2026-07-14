# Humanitarian OpenStreetMap Team (HOT) — HDX Data

**Theme:** Infrastructure & Geospatial / Crowdsourced Mapping
**Source:** Humanitarian OpenStreetMap Team (HOT), published via the Humanitarian Data Exchange (HDX)
**Coverage:** Global — 249 countries and territories; ~2,600+ datasets (~4,000+ including historical), roughly 20% of all content on HDX
**Unit of observation:** Feature-level (individual road segment, building, point of interest) aggregated into per-country/region GIS layers
**Temporal granularity:** Rolling/continuous updates (exports regenerated on a regular automated cycle); no fixed historical time series, reflects current OSM state at each export
**Format:** GIS layers — Shapefile, GeoPackage, GeoJSON, KML, Flatgeobuf, CSV, MBTiles; also queryable/exportable on demand via the HOT Export Tool
**Access:** [https://data.humdata.org/organization/hot](https://data.humdata.org/organization/hot) (HDX org page) · [https://export.hotosm.org](https://export.hotosm.org) (custom export tool) · [https://www.hotosm.org](https://www.hotosm.org)
**License:** Open Database License (ODbL) — free to use/share/adapt with attribution to © OpenStreetMap contributors
**Last verified:** July 2026

---

## What It Is

HOT is the humanitarian arm of the OpenStreetMap (OSM) ecosystem — a nonprofit that coordinates crowdsourced mapping specifically for disaster response, humanitarian action, and community development. Rather than hosting its own separate database, HOT curates and regularly re-exports subsets of OpenStreetMap's crowdsourced data as clean, pre-packaged, per-country GIS layers on HDX, covering infrastructure categories most relevant to humanitarian operations: road networks, populated places, airports/railways/ports, education and health facilities, rivers/waterways, and buildings (including, in active-crisis contexts, mapped destroyed structures).

Since 2016, a "HOT Bot" integration automatically pushes fresh exports from HOT's own Export Tool to HDX on a recurring cycle, so users get ready-made country/region extracts without needing to configure a custom export themselves. In 2022 alone, HOT-attributed HDX exports were downloaded nearly 67,000 times by users in 194 countries.

---

## How the Underlying Data Is Collected

OSM (and by extension HOT's exports) is built from three main contribution channels:

1. **In-person mobile data collection** — volunteers and local mappers surveying specific infrastructure on the ground (often via OSM-compatible apps like OSMAnd, StreetComplete, or the Tasking Manager for organized mapathons).
2. **Remote sensing / digitization** — tracing features from satellite or drone/UAV imagery, frequently coordinated through the [HOT Tasking Manager](https://tasks.hotosm.org) during active disaster responses.
3. **Data imports** — bulk import of existing government or organizational datasets into OSM, following OSM's import guidelines.

Because it's crowdsourced, completeness and currency vary significantly by country and region — areas with active HOT mapathons (e.g., recent disaster/conflict zones) tend to be far more richly mapped than areas with little mapper activity.

---

## Key Data Categories

- Road networks (by class: primary, secondary, tracks, paths)
- Populated places / settlements
- Airports, railways, ports
- Health facilities
- Education facilities
- Rivers and waterways
- Buildings (including damage/destruction status in active-crisis exports)
- Points of interest relevant to humanitarian logistics (varies by country export)

---

## Potential Research Questions

- Does the density of HOT/OSM mapping activity itself correlate with conflict intensity or disaster occurrence (i.e., is more/less complete mapping a proxy for crisis attention)?
- Can pre- vs. post-crisis building/road datasets be used to estimate infrastructure damage in conflict or wildfire-affected areas (e.g., cross-referencing with [NASA FIRMS wildfire detections](../climate/wildfire-detections.md) or [ACLED](../peace-conflict/acled.md) conflict events)?
- How does road network completeness relate to market accessibility, complementing the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md)'s own road-proximity screening approach for Ethiopia?
- Are health/education facility layers reliable enough for accessibility analysis in data-scarce rural regions, or do they require ground-truthing?
- Could crowdsourced mapping intensity (contributor counts, edit frequency) serve as an indirect proxy for local civil society capacity or humanitarian presence?

---

## Notes & Quirks

- **Not a static or versioned dataset** — exports reflect whatever OSM's crowdsourced state is at the time of the last HOT Bot cycle. For reproducible research, download and archive a specific export rather than re-querying live, since the same country page will return different data at different times.
- **Coverage is uneven by design** — since it's crowdsourced and disaster/humanitarian-focused, recently mapped or actively mapathon'd regions (e.g., post-disaster response areas) can be far more complete than otherwise-similar regions with no recent mapping campaigns. Don't assume completeness gaps reflect ground truth (e.g., "no roads mapped" ≠ "no roads exist").
- **License is ODbL, not CC** — distinct share-alike-style obligations apply if you redistribute a derived database (not just individual extracts); attribution to OpenStreetMap contributors is required in all cases.
- **HOT Export Tool vs. HDX country pages** — the HDX org page gives pre-packaged, regularly refreshed exports; the [HOT Export Tool](https://export.hotosm.org) lets you draw a custom bounding box/feature selection and export on demand, useful for sub-national or cross-border areas of interest not aligned to HDX's per-country packaging.
- **Complementary to, not a replacement for, official statistics** — best used alongside authoritative sources (national mapping agencies, government census data) rather than as a sole source for facility counts or population estimates.

---

## How to Access

1. Browse and download pre-packaged per-country layers: [https://data.humdata.org/organization/hot](https://data.humdata.org/organization/hot)
2. Build a custom extract for a specific area/feature set: [https://export.hotosm.org](https://export.hotosm.org) (free OSM account required)
3. Contribute to or track active mapping campaigns: [https://tasks.hotosm.org](https://tasks.hotosm.org)
4. Background on HOT's HDX partnership: [Centre for Humanitarian Data — Humanitarian OpenStreetMap on HDX](https://centre.humdata.org/humanitarian-openstreetmap-on-hdx/)
5. Organization homepage: [https://www.hotosm.org](https://www.hotosm.org)
