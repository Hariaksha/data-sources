# PowerOutage.us

**Theme:** Infrastructure & Energy  
**Coverage:** United States (96%), Canada (95%), United Kingdom (89%) — real-time and historical  
**Unit of observation:** Utility-level outage counts, aggregated to county, state, and national level  
**Temporal granularity:** Near real-time (updates every few minutes); historical archive available  
**Format:** Web interface, REST API, embeddable maps, alert system  
**Access:** [https://poweroutage.us](https://poweroutage.us) — free public view; paid API/data products  
**License:** Proprietary — see [Terms of Use](https://poweroutage.us/legal/termsofuse)  
**Last verified:** June 2026

---

## What It Is

PowerOutage.us is a real-time power outage intelligence platform that aggregates customer-outage data from electric utilities across the US, Canada, and UK. It tracks how many customers are currently without power at the utility, county, and state level, and maintains a historical archive of outage events.

---

## Key Variables

| Variable | Description |
|----------|-------------|
| `customers_out` | Number of customers currently without power |
| `utility` | Reporting electric utility name |
| `state` / `county` | Geographic aggregation level |
| `timestamp` | Time of last data update (near real-time) |
| `percent_affected` | Share of utility's customers experiencing outage |
| `event_id` | Identifier for named major outage events |

---

## Potential Research Questions

- How do extreme weather events (hurricanes, ice storms, wildfires) translate into utility-level outage counts and durations?
- Is there spatial heterogeneity in outage frequency and recovery time across income or demographic groups?
- How do grid resilience outcomes correlate with utility ownership type (IOU vs. co-op vs. municipal)?
- Can near-real-time outage data serve as a proxy for disaster severity in conflict-climate research?
- What is the relationship between outage exposure and downstream welfare or economic outcomes?

---

## Data Products

| Product | Description | Access |
|---------|-------------|--------|
| Public Map | Live outage map by state, county, utility | Free — [poweroutage.us](https://poweroutage.us) |
| Live Outage REST API | Programmatic access to real-time outage counts | Paid — [API docs](https://poweroutage.us/use-our-data#api) |
| Historical Intelligence | Archive of past outage events | Paid — [details](https://poweroutage.us/use-our-data#historical-data) |
| Smart Alert System | Threshold-based outage notifications | Paid — [details](https://poweroutage.us/use-our-data#alerts) |
| Embeddable Maps | Live maps for third-party platforms | Paid — [details](https://poweroutage.us/use-our-data#maps) |
| Precision Reporting | Custom outage reports | Paid — [details](https://poweroutage.us/use-our-data#reporting) |

---

## Notes & Quirks

- Data is sourced by scraping or API-polling individual utility websites — coverage and update frequency vary by utility.
- The unit of observation is **customers out**, not households or individuals. One "customer" is typically one metered account (residential or commercial).
- Historical data is not freely available; access requires a paid subscription or data partnership agreement.
- Useful as a **proxy for disaster impact** in environmental economics and climate-conflict research, but should be cross-validated against NOAA storm event data or FEMA declarations.
- Coverage gaps exist for smaller rural cooperatives and municipal utilities that do not self-report outage data.
- Major named events are archived under [poweroutage.us/about/majorevents](https://poweroutage.us/about/majorevents) and may be a useful starting point for event-study designs.

---

## How to Access

1. **Free public data:** Browse [poweroutage.us](https://poweroutage.us) directly for current state/county/utility counts. No registration required.
2. **API access:** Apply for API credentials at [poweroutage.us/use-our-data](https://poweroutage.us/use-our-data). Pricing is usage-based.
3. **Historical data:** Contact PowerOutage.us directly through the data products page for historical archive licensing.
4. **Academic/research inquiries:** Check the [Research page](https://poweroutage.us/research) for any academic data-sharing programs.

---

## Related Datasets

- `catalog/climate/nasa-wildfire-firms.md` — cross-reference wildfire detections with outage events
- `catalog/conflict/acled.md` — potential linkage for infrastructure disruption in conflict contexts