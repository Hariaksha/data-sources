# Marketplace Activity Index (MAI)

**Theme:** Development & Wellbeing / Remote-Sensed Economic Activity
**Source:** von Carnap, T., Asiyabi, R.M., Dingus, P. & Tompsett, A. (University of Oslo; Stanford Center on Food Security and the Environment; Stockholm School of Economics / Mistra Center for Sustainable Markets; University of Edinburgh; Beijer Institute / Stockholm University)
**Coverage:** Ethiopia (1,776 mapped markets, nationwide outside Addis Ababa), 2017–2024; validation samples in Kenya, Malawi, and Mozambique
**Unit of observation:** Marketplace (point/polygon) — weekly-to-daily activity readings per market
**Temporal granularity:** Up to weekly (activity measure derived from ~30-hour median satellite revisit interval); market maps are static/cross-sectional
**Format:** Interactive web dashboard (hex-grid map) with per-market data visualization; raw data downloadable for analysis; underlying code and derived datasets on GitHub
**Access:** [https://market-activity.net](https://market-activity.net) (dashboard) · [https://github.com/pauldingus/MAI-replication-package](https://github.com/pauldingus/MAI-replication-package) (code + derived data) · Code archive: [https://doi.org/10.5281/zenodo.18867787](https://doi.org/10.5281/zenodo.18867787)
**License:** CC BY-NC-ND 4.0 (paper); underlying PlanetScope satellite imagery itself is *not* redistributable (accessed under an academic research user agreement) — only derived datasets/code are shared
**Last verified:** July 2026

---

## What It Is

The Marketplace Activity Index (MAI) is a dataset — and the underlying method — for detecting rural periodic (weekly) marketplaces from freely/commercially available satellite imagery and tracking their activity over time, without requiring any prior information about market locations. It's introduced in:

> von Carnap, T., Asiyabi, R.M., Dingus, P. & Tompsett, A. (2026). *Using satellite imagery to map rural marketplaces and monitor their activity at high frequency.* **Nature Communications**. https://doi.org/10.1038/s41467-026-72865-z (Received 8 Aug 2025; Accepted 20 Apr 2026; Published 9 May 2026; Open Access, unedited early-access manuscript at time of review)

Periodic markets — weekly gatherings of buyers and sellers — are the main visible manifestation of rural trade in much of the low- and middle-income world, but because they are informal and dispersed, systematic maps and attendance records essentially don't exist. This paper fills that gap using purely remote-sensing methods, producing (1) a map of market **locations** and (2) a **panel of activity** at each market at up-to-weekly frequency.

The public-facing dashboard at market-activity.net lets users browse detected market locations (aggregated into a hex grid at low zoom, individual markets at high zoom), open multiple market panes to compare activity, and download raw per-market activity data.

---

## Methodology (from the paper)

**Core intuition:** marketplaces look visibly different on market days vs. non-market days (crowds, colorful temporary stalls), but this difference is subtle in the lower-resolution, high-frequency imagery needed for continuous monitoring. The method isolates the *periodic* (day-of-week-specific) component of this appearance change from other sources of image variation (vegetation, ploughing, clouds).

1. **Imagery:** PlanetScope RGB surface-reflectance imagery (~3.1m resolution, median 30-hour revisit), June 2017–September 2024; screening also uses lower-resolution/frequency Sentinel-2 imagery for computational efficiency.
2. **Reference composites:** for each image, a "non-market-day" reference composite is built from temporally nearby images (±6 weeks), deliberately excluding the same day-of-week, using an interval-mean (40th–60th percentile) rather than a plain median to reduce residual misalignment noise.
3. **Difference signal:** each image is differenced against its reference composite; differences are summarized per pixel by multiplying (a) max absolute difference across R/G/B bands (brightness) with (b) max absolute difference across two polar/angular colour descriptors (colour), then averaged by day-of-week.
4. **Candidate-location screening (Ethiopia):** rather than screening the whole country, candidate locations are restricted to areas within 300m of OSM roads or built-up areas (Global Human Settlement Layer), excluding Addis Ababa — narrowing the search to 4.5% of Ethiopia's landmass. Sentinel-2 is used as a cheap first-pass filter (screens 0.093% of Ethiopia's landmass at the PlanetScope stage, across 4,562 candidate locations), followed by manual visual confirmation against very-high-resolution (VHR) basemap imagery.
5. **Market delineation:** contiguous areas of elevated periodic signal above empirically chosen thresholds are extracted (discarding <50m²); a "fringe" ring (area with fluctuating, as opposed to core/constant, activity) defines the effective market area used for the activity measure.
6. **Activity index construction:** raw per-image activity readings are de-meaned relative to non-market-day values and rescaled so that, within a chosen reference year, 0 = average non-market-day level and 100 = average market-day level (a penalized smoothing spline is fit across market-day observations within each year to interpolate/re-reference). This makes the index comparable across markets and over time. A separate harmonization step corrects for a change in satellite sensor generation around 2020–2021.

**Validation:** using independent secondary market-listing datasets from Kenya (60 markets), Malawi (31 markets), and Mozambique (48 markets), the method achieves >90% precision and <10% false-positive rate across a broad range of signal-strength thresholds. In Ethiopia, 1,776 markets were detected (vs. 421 listed in OpenStreetMap, 2,627 in a 2007 government census of unclear/likely-inaccurate quality); 69.7% of Ethiopia's population lives within 10km of a detected market. 63% of detected markets show no measurable night-light emissions at all, underscoring why nightlights (the standard remote-sensing economic-activity proxy) miss this kind of activity.

**Detectability criteria (defines what MAI can and cannot capture):** a market must (i) occur periodically (1–3 days/week), (ii) take place at least partly outdoors with a footprint ≥50m², (iii) be observable for enough of 2017–2024 to distinguish signal from noise, and (iv) operate around 10:30–10:45am local time (the typical satellite overpass time). Daily/permanent urban markets, night markets, fully covered markets, and markets in persistently cloudy regions are not detected.

---

## Key Findings Demonstrated in the Paper

- **Seasonality:** market activity tracks the agricultural calendar — a one-SD decrease in growing-season rainfall is associated with a 4.2-index-point decrease in subsequent harvest-season market activity (~24% of the typical seasonal swing between average and lean-season activity).
- **COVID-19:** a sharp, unseasonal drop in market activity is visible in April 2020 coinciding with Ethiopia's COVID restrictions.
- **Conflict:** using geo-referenced conflict-event data, periods of elevated conflict (e.g., the Tigray war from November 2020) generally coincide with lower market activity; effects vary substantially by administrative zone (up to ~30 index points in some zones — larger than typical seasonal swings).
- **Statistical power:** a year-on-year 4-index-point difference is detectable at 80% power with just 6 markets; a month-on-month difference of the same size requires ~60 markets.

---

## Key Variables (Dashboard / Derived Data)

- Market location (point/polygon outline of detected market extent, incl. "fringe" boundary)
- Market day(s) of operation (day-of-week)
- Activity index value per available image/date (0 = typical non-market-day level, 100 = typical market-day level in reference year)
- Signal strength / detection threshold at which the market was identified
- Administrative zone / region (for Ethiopia, down to admin-1/zone level used in regional aggregations)

---

## Potential Research Questions

- How does market activity respond to conflict shocks in near-real time, relative to lagged administrative or survey-based indicators — useful as a high-frequency proxy for local economic disruption in conflict studies (e.g., Indonesia-style wildfire-conflict work, if the method were extended/replicated elsewhere).
- Can changes in market activity serve as an early-warning signal for humanitarian crises, complementing systems like FEWS NET?
- How does the elasticity of market activity to rainfall/weather shocks vary across agro-climatic zones with unimodal vs. bimodal rainfall regimes?
- Does market activity decline around conflict events predict subsequent displacement, food insecurity, or other conflict-adjacent outcomes?
- How well would this method transfer to other countries/regions (e.g., Indonesia) given only satellite imagery and OSM/built-up-area data as inputs?

---

## Notes & Quirks

- **Raw satellite imagery is not redistributable** — the authors accessed PlanetScope imagery under an academic research-use agreement. Only the code and *derived* datasets (market outlines, activity index values) are public via GitHub/Zenodo. Reproducing the pipeline elsewhere requires your own PlanetScope access.
- **Not a global product yet.** Full validation coverage is Ethiopia (comprehensive, 2017–2024) plus small ground-truth samples in Kenya, Malawi, and Mozambique used only to validate detection accuracy, not to produce full activity panels there.
- **The public website is a JavaScript single-page app** (React) — content is not server-rendered, so it must be crawled/interacted with in a browser (or via its client bundle) rather than scraped from static HTML.
- **The index has no natural unit** — values are only meaningful relative to a market's own reference-year rescaling (0 = non-market-day baseline, 100 = market-day average in a chosen reference year, typically 2018). Cross-market level comparisons require care; the authors recommend comparing signs of changes or within-market/within-group comparisons rather than raw magnitudes across heterogeneous markets.
- **Sensor-generation break ~2020–2021**: PlanetScope's satellite generation changed, requiring a harmonization step; analyses using only pre-2020 or only post-2021 data don't need this adjustment.
- **Journal status at last check:** published as an "unedited"/early-access manuscript (Nature Communications, in press formatting) — page numbers/figure numbers may shift slightly upon final typesetting.

---

## How to Access

1. Browse the interactive dashboard (hex-grid map, per-market activity panels, comparison view): [https://market-activity.net](https://market-activity.net)
2. Download raw per-market activity data via the site's Data page (`/data`) — a Data Guide (`/data-guide`) and Data Request (`/data-request`) page are also available for details/bespoke requests.
3. Full code + derived datasets (Ethiopia market outlines, activity panel): [https://github.com/pauldingus/MAI-replication-package](https://github.com/pauldingus/MAI-replication-package)
4. Permanently archived code snapshot (version used in the published paper): [https://doi.org/10.5281/zenodo.18867787](https://doi.org/10.5281/zenodo.18867787)
5. Read the paper (Open Access, CC BY-NC-ND 4.0): [https://doi.org/10.1038/s41467-026-72865-z](https://doi.org/10.1038/s41467-026-72865-z)

**Cite as:** von Carnap, T., Asiyabi, R.M., Dingus, P. & Tompsett, A. (2026). Using satellite imagery to map rural marketplaces and monitor their activity at high frequency. *Nature Communications*. https://doi.org/10.1038/s41467-026-72865-z
