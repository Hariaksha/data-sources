# ACLED — Armed Conflict Location & Event Data

**Theme:** Conflict & Political Violence
**Source:** Armed Conflict Location & Event Data Project (ACLED)
**Geographic Coverage:** Global — 200+ countries and territories
**Time Coverage:** 1997 – present (Africa/Eastern Africa); 2010–2018 for most other regions;
see full [country/time-period coverage table](https://acleddata.com/methodology/countrytime-period-coverage)
**Unit of Observation:** Event (a single discrete incident with actors, location, date, and type)
**Spatial Granularity:** GPS coordinates (latitude/longitude) + Admin 1, Admin 2, Admin 3 levels
**Temporal Granularity:** Daily; updated weekly
**Format:** CSV (export tool, curated regional files), JSON (API)
**Access:** [ACLED Data Export Tool](https://acleddata.com/data-export-tool/) |
[Download Data Files](https://acleddata.com/conflict-data/download-data-files) — free with
registration at [acleddata.com/register](https://acleddata.com/register/)
**API:** [ACLED API Docs](https://apidocs.acleddata.com/) — available with free account
**License:** Non-commercial academic use; see
[Terms and Conditions](https://acleddata.com/terms-and-conditions)
**Indonesia Coverage:** January 2015 – present
**Last Verified:** April 2026

---

## Description

ACLED collects, codes, and publishes information on political violence events, demonstration
events, and other politically significant developments worldwide. Each event records the
type of incident, the actors involved, precise location, date, and reported fatalities.
Data are sourced from local, national, and international media and NGO reports in over 75
languages, coded by trained regional researchers, and published on a weekly basis.

ACLED is the primary event-level conflict dataset in political science and development
economics. It is especially useful for granular, sub-national analysis of conflict dynamics
over time.

---

## Event Taxonomy

ACLED records **6 event types** and **25 sub-event types**, grouped into 3 disorder categories:

| Disorder Type | Event Type | Example Sub-event Types |
|---------------|------------|-------------------------|
| Political violence | Battles | Armed clash, Government regains territory, Non-state actor overtakes territory |
| Political violence | Explosions/Remote violence | Air/drone strike, Suicide bomb, Shelling, IED/landmine, Grenade, Chemical weapon |
| Political violence | Violence against civilians | Attack, Sexual violence, Abduction/forced disappearance |
| Demonstrations | Protests | Peaceful protest, Protest with intervention |
| Political violence + Demonstrations | (Excessive force against protesters) | — |
| Demonstrations | Riots | Violent demonstration, Mob violence |
| Strategic developments | Strategic developments | Agreement, Arrests, Change to group/activity, Looting, HQ established, Non-violent transfer of territory |

---

## Key Variables

| Variable | Description | Notes |
|----------|-------------|-------|
| `event_id_cnty` | Unique alphanumeric event identifier | Stable across updates (e.g., `ETH9766`) |
| `event_date` | Date of event | `YYYY-MM-DD` format |
| `disorder_type` | High-level category | Political violence, Demonstrations, Strategic developments |
| `event_type` | Type of event | Battles, Protests, Riots, etc. |
| `sub_event_type` | Subcategory of event type | Armed clash, Peaceful protest, Air/drone strike, etc. |
| `actor1` / `actor2` | Primary actors involved | Named groups; actor1 is not necessarily the aggressor |
| `inter1` / `inter2` | Actor type codes | State forces, Rebel group, Militia, Civilians, etc. |
| `civilian_targeting` | Whether civilians were the primary target | `"Civilians targeted"` or blank |
| `country` | Country of event | — |
| `admin1` / `admin2` / `admin3` | Sub-national administrative levels | Province → District → Sub-district |
| `location` | Named place of event | — |
| `latitude` / `longitude` | GPS coordinates | EPSG:4326, 4 decimal places |
| `geo_precision` | Location precision code | 1 = exact, 3 = approximate |
| `fatalities` | Reported fatalities | Conservative estimate; 0 if unknown |
| `tags` | Additional structured tags | e.g., `women targeted: politicians; sexual violence` |
| `notes` | Free-text event description | — |
| `source` / `source_scale` | Sources used; geographic proximity of source | Local, national, international |

---

## Available Download Files

### Event Data (raw, event-level)
Downloadable by region via the [export tool](https://acleddata.com/data-export-tool/) or
[curated regional files](https://acleddata.com/conflict-data/download-data-files/event-data).
Regions include: Africa, Middle East, South Asia, Southeast Asia (incl. Indonesia),
East Asia, Europe, Latin America & Caribbean, North America, Oceania.

### Aggregated Data (pre-summarized, country-level)
Pre-built files available directly at
[acleddata.com/conflict-data/download-data-files/aggregated-data](https://acleddata.com/conflict-data/download-data-files/aggregated-data):

| File | Description | Frequency |
|------|-------------|-----------|
| Political violence events by country-year | Battles + explosions + violence against civilians | Annual |
| Political violence events by country-month-year | Same as above | Monthly |
| Demonstration events by country-year | Protests + riots | Annual |
| Events targeting civilians by country-year | All civilian-targeting events | Annual |
| Reported fatalities by country-year | All reported fatalities | Annual |
| Civilian fatalities from direct targeting by country-year | Fatalities from direct civilian targeting only | Annual |
| Aggregated Asia-Pacific data | Event, fatality, and exposure counts by week and Admin 1 | Weekly (updated Tuesdays) |

---

## Potential Research Questions

- How do wildfire events in Indonesia spatially and temporally overlap with ACLED conflict
  events at the sub-district level?
- Does conflict intensity (measured by fatalities or event counts) predict or follow
  environmental shocks like droughts or fires?
- Which actor types are most associated with violence against civilians in high-deforestation
  districts?
- Do protest events cluster around election cycles or economic shocks in Southeast Asia?
- How does the ACLED Conflict Index (a pre-aggregated summary score) rank countries for
  cross-national comparison?

---

## Merge Keys & Compatibility

- **Country-level:** merge via `iso3c` or `country` name with FSI, GPI, CCVI, HDI, EPI
- **Sub-national:** merge via `admin1` with NASA FIRMS wildfire detections using GADM
  administrative boundary shapefiles (match on province name or GADM `GID_1`)
- **Grid-cell:** aggregate events to 0.5° or 0.25° grid using `latitude`/`longitude`;
  merge with FIRMS active fire data or climate rasters
- **Temporal:** daily event dates align well with FIRMS daily fire detections for
  event-level temporal analysis

---

## Access Notes

1. Register for a free account at [acleddata.com/register](https://acleddata.com/register/)
2. Access the export tool at [acleddata.com/data-export-tool](https://acleddata.com/data-export-tool/)
   — filter by country, date range, event type, actor type
3. For Indonesia specifically: filter `country = "Indonesia"`, coverage begins January 2015
4. For API access, authenticate via
   [acleddata.com/reactivation/api-authentication](https://acleddata.com/reactivation/api-authentication)
5. Pre-aggregated files can be downloaded directly without the export tool from the
   [download data files page](https://acleddata.com/conflict-data/download-data-files)

---

## Known Limitations

- **Reporting bias:** events in remote areas or low-media-coverage regions are likely
  undercounted; coverage quality varies by country
- **Fatality precision:** the `fatalities` field records the most conservative estimate
  when sources conflict; treat as a lower bound
- **Indonesia coverage starts 2015:** limits pre-2015 historical analysis for Indonesian
  wildfire-conflict research
- **Event aggregation:** concurrent events by the same actors at the same location on
  the same day are merged into one record — raw event counts can understate intensity
- **Strategic developments:** collected less systematically than violence/demonstration
  events; not directly comparable across countries
- **Actor names:** generic names like `Protesters (Indonesia)` are used when specific
  group identities are unknown — limits actor-specific analysis

---

## References

- [ACLED Codebook](https://acleddata.com/methodology/acled-codebook) — full variable
  definitions, event type taxonomy, and actor coding rules
- [Country/Time-Period Coverage](https://acleddata.com/methodology/countrytime-period-coverage)
- [ACLED API Documentation](https://apidocs.acleddata.com/)
- [ACLED Knowledge Base](https://acleddata.com/conflict-data/knowledge-base)
- [ACLED Conflict Index](https://acleddata.com/series/acled-conflict-index) — pre-aggregated
  country-level conflict score (see also `catalog/conflict/acled-conflict-index.md`)