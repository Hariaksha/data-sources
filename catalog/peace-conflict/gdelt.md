# GDELT — Global Database of Events, Language, and Tone

**Theme:** Conflict & Political Violence / Global Event Monitoring
**Source:** The GDELT Project (open-source initiative; supported in part by Google Jigsaw / Google Cloud)
**Geographic Coverage:** Global — nearly every country, monitoring news media in 100+ languages
**Time Coverage:** Events Database: January 1, 1979–present (GDELT 1.0 back-file); real-time GDELT 2.0 stream since February 2015. Global Knowledge Graph (GKG): 2015–present (with a 1979–2013 GKG 1.0 back-file)
**Unit of Observation:** Event (a single coded interaction between two actors, e.g. "Country A's military threatens Country B") for the Events Database; document/article-level entity, theme, and tone extraction for the GKG
**Spatial Granularity:** Geocoded to country, admin1, city, or landmark level where identifiable in source text
**Temporal Granularity:** GDELT 2.0 updates every 15 minutes; GDELT 1.0 (legacy) updated daily
**Format:** Flat CSV/TSV files (daily/15-min exports), Google BigQuery public dataset, GDELT Analysis Service (web UI), GDELT DOC API (article search)
**Access:** [https://www.gdeltproject.org/data.html](https://www.gdeltproject.org/data.html) (raw files) · BigQuery public dataset `gdelt-bq.gdeltv2` · [https://analysis.gdeltproject.org](https://analysis.gdeltproject.org) (no-code analysis tool)
**License:** Free for unlimited academic, commercial, or governmental use — no fee, no registration required; attribution to the GDELT Project and a link back requested
**Last verified:** July 2026

---

## What It Is

GDELT monitors the world's broadcast, print, and online news media in real time (in over 100 languages), automatically identifying and coding events, people, organizations, locations, themes, emotions, and narratives as they happen. It's built and maintained by an independent open-data initiative (with Google Jigsaw/Cloud infrastructure support) and describes itself as the largest open database of human society, spanning a quarter-billion+ coded event records.

GDELT has three main components:

1. **Events Database** — event-level records coded using the CAMEO taxonomy (see below), covering interactions between "actors" (countries, organizations, ethnic/religious groups, etc.) — e.g., protests, military actions, diplomatic statements, aid, violence.
2. **Global Knowledge Graph (GKG)** — a much richer per-article layer extracting themes, named entities (people, organizations, locations), emotional/tone dimensions, and thousands of dictionary-based sentiment/topic scores (GCAM) from the full text of monitored news coverage.
3. **GDELT Television/Visual layers** (e.g., the Television Explorer, and image-based analysis of TV news and other visual media) — a more specialized add-on not typically needed for standard event-data research.

---

## Key Variables

**Events Database (selected fields):**
- `GLOBALEVENTID`, `SQLDATE` / date fields — unique event ID and date
- `Actor1CountryCode`, `Actor2CountryCode` (and role/type codes) — the parties involved
- `EventCode`, `EventBaseCode`, `EventRootCode` — CAMEO taxonomy codes describing the interaction type (e.g., protest, use of force, appeal, cooperation)
- `QuadClass` — coarse classification into Verbal Cooperation / Material Cooperation / Verbal Conflict / Material Conflict
- `GoldsteinScale` — a −10 to +10 scale of the event's theoretical impact on stability
- `AvgTone` — average sentiment/tone of all coverage mentioning the event
- `ActionGeo_*` fields — geocoded location (country, admin1, lat/lon)
- `SOURCEURL` — link to the originating news article

**Global Knowledge Graph (selected fields):**
- `V2Themes` — thematic tags (e.g., disaster, humanitarian aid, protest)
- `V2Locations`, `V2Persons`, `V2Organizations` — entity extraction
- `V2Tone` — a multi-dimensional tone/affect vector (not just single-value sentiment)
- `GCAM` — Global Content Analysis Measures, thousands of soft counts from multiple sentiment/topic dictionaries
- `SourceCommonName`, `DocumentIdentifier` — sourcing metadata

---

## CAMEO Event Taxonomy

Events are coded using **CAMEO** (Conflict and Mediation Event Observations), a hierarchical scheme with root categories (e.g., 01 Make Statement, 14 Protest, 19 Fight, 20 Use Unconventional Mass Violence) that subdivide into 300+ specific event types. GDELT uses CAMEO v1.1b3. Actor country codes in CAMEO fields differ from the FIPS country codes used in geographic (`*Geo*`) fields — a common source of merge errors when combining the two.

Full codebooks: [GDELT Event Database Codebook v2.0](http://data.gdeltproject.org/documentation/GDELT-Event_Codebook-V2.0.pdf) and [GKG Codebook](https://www.gdeltproject.org/data.html).

---

## Potential Research Questions

- Do spikes in GDELT-coded protest/conflict events (CAMEO root codes 14, 17–20) in Indonesia precede or follow periods of elevated wildfire activity detected in [NASA FIRMS](../climate/wildfire-detections.md)?
- How does `GoldsteinScale`/`AvgTone` trend around known conflict events compare to [ACLED](acled.md)'s independently coded event severity, as a cross-validation check?
- Can GKG theme tags (e.g., disaster, drought, displacement) be used to build a high-frequency media-attention index for climate-conflict linkages, complementary to the [Climate Conflict Vulnerability Index](climate-conflict-vulnerability-index.md)?
- Does media tone (`AvgTone`/`V2Tone`) around rural economic disruption events correlate with independently measured activity drops in the [Marketplace Activity Index](../development-wellbeing/marketplace-activity-index.md)?
- How well do near-real-time (15-minute) GDELT event spikes serve as an early-warning signal relative to slower-moving sources like [HungerMap LIVE](../development-wellbeing/hungermap-live.md)?

---

## Notes & Quirks

- **Automated NLP coding, not human-verified** — events are extracted and coded by automated natural language processing across huge volumes of global media, so individual event records can be noisy, duplicated (the same real-world event reported by many outlets becomes many event records), or miscoded. Aggregate/trend-level analysis is generally more reliable than treating individual event records as ground truth.
- **CAMEO actor codes ≠ FIPS geo codes** — a frequent source of join bugs; check which code system a given field uses before merging on country.
- **GDELT 1.0 vs 2.0** — 2.0 (Feb 2015–present) added the 15-minute update cadence, expanded language coverage, and the richer GKG/tone fields; the 1.0 back-file (1979–2015) is coarser and daily-only. Don't assume schema compatibility across the two without checking field-level documentation.
- **BigQuery is usually the most practical access path** for anything beyond small date ranges — the raw flat-file exports are voluminous (15-minute files since 2015) and better suited to targeted/streaming use cases than bulk historical analysis.
- **Duplicate/near-duplicate events are common** for high-media-coverage events (e.g., major conflicts), since GDELT codes an event separately for each qualifying article that mentions it — deduplication strategy matters for event-count-based analyses.
- **No paywall or registration required**, unlike ACLED's academic-use terms — a practical advantage when open redistribution of derived results matters.

---

## How to Access

1. Query the full historical dataset via Google BigQuery public dataset: `gdelt-bq.gdeltv2.events` and `gdelt-bq.gdeltv2.gkg` (free tier covers most research-scale queries)
2. Download raw CSV/TSV export files directly: [https://www.gdeltproject.org/data.html](https://www.gdeltproject.org/data.html)
3. No-code exploration and visualization: [https://analysis.gdeltproject.org](https://analysis.gdeltproject.org)
4. Search/browse individual articles: [GDELT DOC 2.0 API](https://blog.gdeltproject.org/gdelt-doc-2-0-api-debuts/)
5. Full documentation and codebooks: [https://www.gdeltproject.org/data.html](https://www.gdeltproject.org/data.html)
