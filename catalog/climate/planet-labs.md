# Planet Labs (Planet)

**Theme:** Satellite Imagery / Earth Observation Infrastructure
**Source:** Planet Labs PBC (commercial Earth-observation company; public benefit corporation)
**Coverage:** Global — PlanetScope images the entire land surface daily; SkySat provides high-resolution tasked imagery anywhere on demand; NICFI basemaps cover the tropics (30°N–30°S)
**Unit of observation:** Raster imagery scene/tile (pixel-level reflectance); not tabular/entity data
**Temporal granularity:** PlanetScope: near-daily (median ~30-hour revisit); SkySat: up to 10 revisits/day when tasked; NICFI tropical basemaps: monthly mosaic composites
**Format:** Analytic/surface-reflectance GeoTIFF via API, Planet Explorer (web viewer), QGIS/ArcGIS plugins, Google Earth Engine (for NICFI)
**Access:** [https://www.planet.com](https://www.planet.com) (commercial); free tropical basemaps via [NICFI](https://www.planet.com/nicfi/) for eligible non-commercial use; free/discounted academic access often available through university GIS/library programs and NASA's Commercial Smallsat Data Acquisition (CSDA) program
**License:** Commercial — imagery use is governed by a Master Content/End User License Agreement; NICFI basemaps are free but restricted to non-commercial tropical-forest-related use; academic access via CSDA/university programs carries its own research-use restrictions (no redistribution of raw imagery)
**Last verified:** July 2026

---

## What It Is

Planet Labs operates the largest commercial constellation of Earth-imaging satellites, built around three product lines:

- **PlanetScope** — a constellation of ~130+ small "Dove" satellites imaging the entire land surface of Earth roughly daily at 3m/pixel resolution. Originally 4-band (RGB + NIR), later Dove satellites (2020+) add red edge, green I, coastal blue, and yellow bands (8-band). This is the imagery underlying methods like the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md)'s periodic-market detection approach.
- **SkySat** — a smaller high-resolution constellation (sub-meter, ~0.5–0.8m GSD) capable of tasked, on-demand revisits up to 10x/day for a specific location, in Blue/Green/Red/NIR/Panchromatic bands.
- **NICFI Satellite Data Program basemaps** — monthly, analysis-ready, ~4.78m-resolution mosaics of the world's tropics (30°N–30°S), funded by Norway's International Climate & Forests Initiative and made freely available for non-commercial tropical-forest-related research and policy use.

Planet also offers derived/value-added products: **Planetary Variables** (analytic feeds like soil water content, land surface temperature, crop biomass proxies), **SuperRes** (AI-enhanced resolution), change-detection tools, and — as of the resource that prompted this entry — an **agentic geospatial AI assistant** (private beta as of mid-2026) that lets researchers query, compare, and generate reports from Planet imagery via a map-based chat interface, including a "Deep Research" mode producing PDF reports with transparent reasoning logs. The beta is free during testing but currently limited to imagery up to 30 days old, with some capabilities reserved for future paid tiers.

---

## Key Products / Access Tiers

| Product | Resolution | Frequency | Cost | Best for |
|---------|-----------|-----------|------|----------|
| PlanetScope | 3m | ~Daily | Commercial (academic/CSDA discounts available) | High-frequency change detection, activity monitoring |
| SkySat | 0.5–0.8m | Up to 10x/day (tasked) | Commercial, tasking fee | Fine-grained verification, VHR spot imagery |
| NICFI Tropical Basemaps | ~4.78m | Monthly mosaic | Free (non-commercial, tropics only) | Forest monitoring, land-use change, policy transparency |
| Planetary Variables | Varies by variable | Varies | Commercial | Soil moisture, biomass, land surface temperature time series |
| Agentic Geospatial AI (beta) | N/A (uses above imagery) | Imagery up to 30 days old | Free during beta | Rapid exploratory geospatial research via chat interface |

---

## Potential Research Questions

- Could PlanetScope's daily revisit be used to extend or replicate the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md) methodology to other regions, e.g. Indonesia, for wildfire-conflict-adjacent economic monitoring?
- Do NICFI tropical basemaps show measurable land-use/deforestation signals that precede or follow [ACLED](../peace-conflict/acled.md)-coded conflict events or [NASA FIRMS](wildfire-detections.md) wildfire detections in the same areas?
- Can SkySat tasking be used for rapid post-event verification (e.g., confirming market/infrastructure damage identified via lower-resolution PlanetScope screening)?
- How well does the new agentic AI "Deep Research" mode's automated change-detection compare to manually validated methods like the Marketplace Activity Index's VHR-based manual confirmation step?
- Could Planetary Variables (soil water content, land surface temperature) serve as a higher-frequency covariate for climate-conflict vulnerability modeling, complementing the [Climate Conflict Vulnerability Index](../peace-conflict/climate-conflict-vulnerability-index.md)?

---

## Notes & Quirks

- **Raw imagery is not freely redistributable** — even where access is free or discounted (NICFI, CSDA, university programs), the underlying license agreements generally prohibit sharing raw imagery outside the approved use case/institution. This is the same constraint noted in the Marketplace Activity Index entry: only *derived* datasets/code, not the imagery itself, can typically be shared publicly.
- **NICFI is tropics-only and non-commercial** — restricted to the 30°N–30°S band and to forest/land-use/policy-relevant research; not a general-purpose free imagery source outside that scope and geography.
- **Academic access varies by institution** — many universities (Yale, UC San Diego, University of Minnesota, Berkeley, etc.) have negotiated their own Planet access agreements for affiliates; check your institution's GIS/library services before assuming you need a paid account.
- **NASA CSDA program** is a separate free-to-researcher route (via NASA Earthdata) for U.S.-government-funded research, providing access to archived PlanetScope/RapidEye data and a limited SkySat allocation — distinct from both NICFI and university-negotiated access.
- **The agentic AI assistant is in private beta** (as of the resource that prompted this entry, mid-2026) — feature set, pricing, and data currency (currently capped at ~30-day-old imagery) are likely to change; treat current capabilities as provisional.
- **Sensor-generation changes affect long time series** — as noted in the Marketplace Activity Index paper, PlanetScope's satellite generations have different spectral response functions; harmonization is needed when building activity/change measures that span a sensor transition (~2020–2021).

---

## How to Access

1. Commercial/general access and product overview: [https://www.planet.com/products/](https://www.planet.com/products/)
2. Free tropical basemaps (NICFI), including QGIS/ArcGIS/Earth Engine integration: [https://www.planet.com/nicfi/](https://www.planet.com/nicfi/) — also browsable directly in [Google Earth Engine's NICFI catalog](https://developers.google.com/earth-engine/datasets/publisher/planet-nicfi)
3. Free/discounted access for U.S.-funded research via NASA's Commercial Smallsat Data Acquisition program: [https://www.earthdata.nasa.gov/about/csda/vendor-planet](https://www.earthdata.nasa.gov/about/csda/vendor-planet)
4. Check your university's library/GIS services for an existing institutional Planet agreement before purchasing directly.
5. Try the agentic geospatial AI beta (as introduced in the resource prompting this entry): [https://www.planet.com/ai-resources/accelerate-research-with-agentic-geospatial-ai/](https://www.planet.com/ai-resources/accelerate-research-with-agentic-geospatial-ai/)
