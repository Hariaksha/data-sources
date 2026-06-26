# Climate Protest Tracker

**Theme:** Climate / Conflict / Governance
**Coverage:** Global, 2022–present
**Unit of observation:** Protest event
**Temporal granularity:** Event-level (start date recorded by day)
**Format:** Interactive web tracker / table
**Access:** [https://carnegieendowment.org/features/climate-protest-tracker](https://carnegieendowment.org/features/climate-protest-tracker) — free / no registration required
**License:** Not clearly stated on the tracker page; verify Carnegie Endowment terms before redistribution
**Last verified:** June 2026

***

## Key Variables

| Variable | Description |
|----------|-------------|
| `country` | Country listed for the protest event |
| `protest_name` | Event title used by the tracker |
| `start_date` | Protest start date |
| `peak_size` | Reported or estimated peak number of participants |
| `protest_target` | Main issue area or sector targeted by the protest |
| `protest_objective` | Free-text description of the protest's demands or purpose |

***

## Potential Research Questions

- How have climate-related protest events changed across countries since 2022?
- Which protest targets, such as fossil fuels, mining, or climate adaptation, generate the largest mobilizations?
- Do climate protests cluster around major policy moments, disasters, or international summits?
- How often do protests oppose extractive or energy infrastructure versus demand stronger climate action?
- Can climate protest activity be linked to conflict dynamics, emissions profiles, or environmental governance outcomes?

***

## Notes & Quirks

- The tracker describes itself as a “one-stop source” for following global trends in climate policy protests since 2022.
- The page currently displays 465 results.
- The table supports filtering by size, year, protest objective, and protest target.
- Protest targets visible in the tracker include categories such as Fossil Fuels and Emissions, Mining and Mineral Resources, Climate Adaptation, and Agriculture.
- Some rows use prefixes like `+United States` or `+Multiple`, which suggests grouped, multi-location, or coordinated events that may need additional cleaning before country-level analysis.
- `peak_size` is not fully standardized: entries include exact counts, approximations such as `~300,000`, and threshold values such as `>200`.
- `protest_objective` is a rich free-text field and may be useful for qualitative coding, topic modeling, or supervised text classification.
- The tracker page does not clearly advertise a bulk download option, so collection may require manual extraction or web scraping.

***

## How to Access

1. Visit [https://carnegieendowment.org/features/climate-protest-tracker](https://carnegieendowment.org/features/climate-protest-tracker).
2. Use the on-page search bar and filters for Size, Year, Protest Objective, and Protest Target.
3. Extract the visible table manually or scrape the web page to create a structured dataset for analysis.
4. Preserve the original text fields, especially `protest_objective`, before building coded variables.

***

## Suggested Uses

- Cross-national analysis of climate mobilization.
- Event-level protest coding for climate-conflict or climate-politics research.
- Building a merged dataset with country-year indicators such as emissions, democracy, energy dependence, or disaster exposure.
- Creating a hand-coded typology of protest demands, targets, and repertoires.
