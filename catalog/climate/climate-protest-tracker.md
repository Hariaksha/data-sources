# Carnegie Climate Protest Tracker

**Theme:** Conflict / Climate / Political Mobilization
**Coverage:** Global, January 2022–present
**Unit of observation:** Protest event
**Temporal granularity:** Event-level (daily start dates)
**Format:** Interactive web tracker (filterable table); no bulk download advertised
**Access:** [https://carnegieendowment.org/features/climate-protest-tracker](https://carnegieendowment.org/features/climate-protest-tracker) — free, no registration required
**License:** Carnegie Endowment for International Peace (non-commercial academic use implied; verify before publication)
**Last verified:** June 2026

***

## Key Variables

| Variable | Description |
|----------|-------------|
| `country` | Country where the protest occurred |
| `protest_name` | Descriptive name assigned to the event |
| `start_date` | Date the protest began (Month DD, YYYY) |
| `peak_size` | Estimated peak attendance (exact, approximate, or range notation, e.g., `>200`, `~300,000`) |
| `protest_target` | Category of entity or sector the protest opposed or addressed (see taxonomy below) |
| `protest_objective` | Full free-text description of what demonstrators demanded or sought |

### Protest Target Taxonomy (known values)

- Fossil Fuels and Emissions
- Mining and Mineral Resources
- Climate Adaptation
- Agriculture
- *Blank* (target not categorized)

***

## Potential Research Questions

- How has the frequency and geographic spread of climate protests changed since 2022?
- Which protest targets (fossil fuels, mining, adaptation) mobilize the largest crowds?
- Does protest activity cluster around international climate events (COP summits, Earth Day, Global Climate Strike)?
- Is there a relationship between a country's carbon intensity or fossil fuel dependence and the volume of domestic climate protests?
- How do anti-fossil fuel protests differ from anti-renewable protests (e.g., anti-wind, anti-solar) in size, geography, and stated objectives?
- Can protest event density serve as an instrument or control variable in climate-conflict or climate-governance studies?

***

## Notes & Quirks

- **Total events as of June 2026:** 465+ results displayed in the tracker.
- **Size notation is inconsistent:** Peak size uses a mix of exact numbers (`2,000`), approximations (`~300,000`), and inequality notation (`>200`, `>1,200`). Clean this column carefully before analysis — treat as ordinal or bin into size categories.
- **Multi-city events:** Some events span multiple cities or countries and are tagged with `+` or `Multiple` as the country. These require special handling for country-level aggregation.
- **Protest objective is free-text:** Rich qualitative detail, but not consistently coded. Useful for text analysis (NLP/topic modeling) or manual coding schemes.
- **No bulk download:** Data appears only as a web table; scraping will be required to build an analysis-ready dataset. Check Carnegie's terms before scraping.
- **Unit ambiguity:** Each row is an event, but "events" range from single-location rallies to coordinated nationwide actions on the same day — they are not always comparable in scale.
- **Coverage start is 2022:** Not suitable for trend analyses requiring pre-2022 baselines without merging with other sources (e.g., ACLED, Mass Mobilization Project).
- **Merge key considerations:** Country name and date are the natural join keys, but country spellings and event boundaries may not align cleanly with other datasets.

***

## How to Access

1. Navigate to [https://carnegieendowment.org/features/climate-protest-tracker](https://carnegieendowment.org/features/climate-protest-tracker).
2. Use the on-page filters (Size, Year, Protest Objective, Protest Target) to subset events.
3. To obtain a machine-readable dataset, scrape the HTML table — the tracker renders as a paginated or fully-loaded table depending on browser state. Use Python (`requests` + `BeautifulSoup` or `Playwright` for JavaScript-rendered content).
4. See `scripts/scrape-climate-protest-tracker.py` (if available) for a fetch script.

### Suggested Python scraping approach

```python
from playwright.sync_api import sync_playwright
import pandas as pd

with sync_playwright() as p:
    browser = p.chromium.launch()
    page = browser.new_page()
    page.goto("https://carnegieendowment.org/features/climate-protest-tracker")
    page.wait_for_selector("table")
    html = page.content()
    browser.close()

tables = pd.read_html(html)
df = tables[0]  # adjust index as needed
df.to_csv("data/climate-protest-tracker.csv", index=False)
```

***

## Related Datasets

- **ACLED** (`catalog/peace-conflict/acled.md`) — event-level conflict and protest data with broader thematic and temporal coverage; can be used to cross-validate or supplement.
- **Mass Mobilization Project** — covers anti-government protest 1990–present; complements climate-specific events.
- **Global Climate Strike data** (Fridays for Future) — specific to youth-led climate strikes, useful for cross-referencing large mobilization events.
