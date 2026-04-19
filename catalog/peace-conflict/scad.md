# Social Conflict Analysis Database (SCAD)

**Theme:** Peace & Conflict / Political Stability
**Source:** Climate Change and African Political Stability (CCAPS) Program, Strauss Center for International Security and Law, University of Texas at Austin (in collaboration with University of North Texas and University of Denver)
**Geographic Coverage:** All of Africa (47+ countries) + Mexico, Central America, and the Caribbean (countries with population > 1 million)
**Time Coverage:** 1990–2017
**Unit of Observation:** Social conflict event
**Format:** Downloadable CSV (two files: Africa, Latin America); companion SCAD-OPs CSV
**Access:** [strausscenter.org/ccaps-research-areas/social-conflict/database](https://www.strausscenter.org/ccaps-research-areas/social-conflict/database/) |
[Download SCAD–Africa (CSV)](https://www.strausscenter.org/wp-content/uploads/SCAD2018Africa_Final.csv.zip) |
[Download SCAD–Latin America (CSV)](https://www.strausscenter.org/wp-content/uploads/SCAD2018LatinAmerica_Final.csv.zip) |
[Codebook](https://www.strausscenter.org/wp-content/uploads/SCAD_33_Codebook.pdf)
**License:** Free to access
**Last Verified:** April 2026

---

## Description

Event-level database of social conflicts — including protests, riots, strikes,
inter-communal violence, government violence against civilians, and intra-government
violence — drawn from Associated Press (AP) and Agence France Presse (AFP) wire reports.
SCAD is designed to capture forms of social and political unrest not systematically tracked
in traditional conflict datasets (e.g., UCDP, ACLED), with a focus on low-intensity,
sub-civil-war events. Contains nearly 20,000 events across Africa, Mexico, Central America,
and the Caribbean. Each event is georeferenced with latitude/longitude and coded for actors,
targets, issues of contention, magnitude, deaths, and government response. A companion
dataset, **SCAD-OPs** (Organizational Properties), provides actor/target domain classifications
for a subset of countries (Egypt, South Africa, Nigeria, Kenya, Haiti, Dominican Republic,
Mexico) for the 1990–2016 period. Widely used in climate-conflict and political stability
research, especially in the CCAPS framework linking climate vulnerability to social unrest.

## Key Variables

| Variable | Description |
|----------|-------------|
| `eventid` | Unique event identifier |
| `startdate` / `enddate` | Start and end dates of the event |
| `etype` | Event type (1=protest, 2=riot, 3=strike, 4=inter-communal conflict, 5=govt violence against civilians, 6=other, 10=intra-govt violence) |
| `country` / `countryname` | Country ISO code and name |
| `elocal` | Sub-national location(s) of the event |
| `latitude` / `longitude` | Geocoordinates of the event location |
| `actor1` / `actor2` | Principal actor(s) involved |
| `target1` / `target2` | Principal target(s) of the event |
| `issue` | Primary issue of contention (e.g., economic, political, ethnic, religious) |
| `issue2` | Secondary issue of contention |
| `deaths` | Estimated number of deaths (-99 = unknown, -77/-88 = imprecise) |
| `repression` | Whether government repression occurred (0/1) |
| `cgovtarget` / `rgovtarget` | Central/regional government as target (0/1) |
| `size` | Estimated number of participants |
| `notes` | Free-text description of the event from source articles |

**SCAD-OPs Additional Variables**

| Variable | Description |
|----------|-------------|
| `domain` | Functional domain of actor/target (01=Central Govt, 02=Regional Govt, etc.) |
| `orgid` | Unique organizational identifier for tracking group activity over time |

## Potential Research Questions

- Does climate variability (e.g., drought, rainfall anomalies) increase the incidence of
  social conflict events in Africa, and through what pathways?
- How does the type of social conflict (protest vs. inter-communal violence) vary by
  country governance quality or regime type?
- Do elections systematically predict spikes in riot or protest activity in sub-Saharan Africa?

## Merge Keys & Compatibility

- Merge with **ACLED** via country + date for a comprehensive low-to-high-intensity conflict
  panel; SCAD complements ACLED by capturing sub-civil-war social unrest
- Merge with **CCVI** (Climate Change Vulnerability Index) or **PDSI/SPEI** drought indices
  via country + year for climate-conflict analyses
- Merge with **Fragile States Index** or **Freedom House** via `iso3c` + year for
  governance-conflict interaction models
- Link with **World Bank WDI** via country + year for socioeconomic correlates of unrest
- Geocoordinates (`latitude`/`longitude`) enable spatial joins with gridded climate,
  land use, or nighttime lights data for sub-national analyses
