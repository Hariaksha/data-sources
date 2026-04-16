# NASA FIRMS — Fire Information for Resource Management System

**Theme:** Climate & Environment
**Source:** NASA LANCE (Land, Atmosphere Near real-time Capability for EOS) / FIRMS
**Geographic Coverage:** Global
**Time Coverage:** MODIS: November 2000 – present | VIIRS S-NPP: January 2012 – present |
VIIRS NOAA-20 (J1): January 2020 – present | VIIRS NOAA-21 (J2): February 2023 – present
**Unit of Observation:** Active fire detection pixel
**Spatial Granularity:** MODIS: ~1 km pixel | VIIRS: ~375 m pixel
**Temporal Granularity:** Daily (near real-time, updated within ~3 hours of satellite overpass)
**Format:** CSV, SHP (shapefile), KML, JSON (web services)
**Access:** [FIRMS Archive Download](https://firms.modaps.eosdis.nasa.gov/download/) |
[Web Services / API](https://firms.modaps.eosdis.nasa.gov/web-services/) — free with
NASA Earthdata account at [urs.earthdata.nasa.gov](https://urs.earthdata.nasa.gov/users/new)
**Indonesia Data Downloaded:** November 2000 – February 2026 (all four sensors)
**License:** Public domain (NASA)
**Last Verified:** April 2026

---

## Description

FIRMS distributes near real-time and archived active fire detections derived from two
satellite sensor families: MODIS (aboard Terra and Aqua satellites) and VIIRS (aboard
Suomi NPP, NOAA-20/J1, and NOAA-21/J2). Each detection represents a ~375m–1km pixel
identified as containing an active fire during a satellite overpass. FIRMS is the standard
data source for satellite-derived wildfire and burning activity in environmental research.

All four sensors have been downloaded for Indonesia (2000–2026) and are stored locally.
VIIRS (375m) offers finer spatial resolution than MODIS (1km) and is preferred for
sub-district-level analysis. MODIS provides the longest time series (2000–present).

---

## Sensor Comparison

| Sensor | Satellite | Resolution | Coverage Start | Best Use |
|--------|-----------|------------|----------------|----------|
| MODIS C6.1 | Terra + Aqua | ~1 km | Nov 2000 | Long time series, pre-2012 analysis |
| VIIRS S-NPP C2 | Suomi NPP | ~375 m | Jan 2012 | Higher spatial precision post-2012 |
| VIIRS J1 C2 | NOAA-20 | ~375 m | Jan 2020 | Best current precision (pair with S-NPP) |
| VIIRS J2 C2 | NOAA-21 | ~375 m | Feb 2023 | Most recent addition; supplements J1 |

For most research on Indonesia post-2012, **VIIRS S-NPP C2** is the recommended primary
sensor; MODIS C6.1 is preferred for the 2000–2011 period or for comparability with older
literature.

---

## Key Variables

| Variable | Description | Notes |
|----------|-------------|-------|
| `latitude` / `longitude` | Center of fire detection pixel | EPSG:4326 |
| `acq_date` | Date of detection | `YYYY-MM-DD` |
| `acq_time` | UTC time of satellite overpass | `HHMM` |
| `satellite` | Satellite identifier | `Terra`, `Aqua`, `N`, `N20`, `N21` |
| `instrument` | Sensor name | `MODIS` or `VIIRS` |
| `confidence` | Detection confidence | MODIS: `low/nominal/high`; VIIRS: 0–100 numeric |
| `frp` | Fire Radiative Power (MW) | Proxy for fire intensity/energy output |
| `bright_t31` | Brightness temperature (K), band 31 | MODIS only; indicator of fire heat |
| `bright_ti4` / `bright_ti5` | Brightness temperature (K), I4/I5 bands | VIIRS only |
| `daynight` | Day (`D`) or night (`N`) detection | Night detections tend to be more reliable |
| `type` | Presumed fire type | 0=vegetation, 1=volcano, 2=static source, 3=offshore |
| `version` | Collection version | C6.1 (MODIS) or C2 (VIIRS) |

---

## Potential Research Questions

- Do wildfire detections (FRP, pixel count) spatially overlap with ACLED conflict events
  at the sub-district level in Indonesia?
- Does fire intensity (FRP) predict conflict onset, or vice versa?
- What are the seasonal and interannual patterns of fire activity across Indonesian provinces,
  and how do they relate to El Niño/ENSO cycles?
- Do high-fire years correlate with increased displacement or protest events (ACLED)?
- How does burning activity in peatland concession areas compare to non-concession areas?

---

## Merge Keys & Compatibility

- **Sub-national spatial merge:** aggregate detections to Admin 1/2 using GADM shapefiles
  (`GID_1`, `GID_2`); match on province/district to ACLED `admin1`/`admin2`
- **Grid-cell merge:** aggregate to 0.25° or 0.5° grid; merge with climate rasters
  (precipitation, temperature, NDVI)
- **Temporal merge:** `acq_date` aligns directly with ACLED `event_date` for
  event-level temporal analysis (daily resolution)
- **Water stress merge:** spatial merge with UCI WRVM vulnerability raster via lat/lon

---

## Access Notes

1. Register at [NASA Earthdata](https://urs.earthdata.nasa.gov/users/new) (free)
2. Submit an archive download request at
   [firms.modaps.eosdis.nasa.gov/download](https://firms.modaps.eosdis.nasa.gov/download/)
   — select sensor, area of interest (Indonesia), and date range
3. For API/web service access:
   [firms.modaps.eosdis.nasa.gov/web-services](https://firms.modaps.eosdis.nasa.gov/web-services/)
4. Near real-time active fire data (last 24h/48h/7 days) as SHP/TXT/KML:
   [firms.modaps.eosdis.nasa.gov/active_fire](https://firms.modaps.eosdis.nasa.gov/active_fire/)

---

## Known Limitations

- **Commission errors:** water bodies, gas flares, industrial heat sources, and volcanic
  activity can trigger false detections — filter using `type` variable
- **Cloud obscuration:** dense smoke and cloud cover prevent detection; fire activity is
  systematically undercounted during cloudy periods (common in Indonesia's wet season)
- **1 km MODIS pixels** may aggregate multiple small fires into one detection or miss
  small fires entirely — VIIRS 375m is preferred for sub-district analysis
- **Temporal gaps:** satellite revisit time means a fire must persist to overpass time to
  be detected; intermittent fires may be missed
- **Confidence thresholds:** for research, filter to `confidence >= nominal` (MODIS) or
  `confidence >= 30` (VIIRS) to reduce false positives

---

## References

- [VIIRS Active Fire User Guide](https://viirsland.gsfc.nasa.gov/PDF/VIIRS_activefire_User_Guide.pdf)
- [MODIS Active Fire User Guide C6.1](https://cdn.earthdata.nasa.gov/conduit/upload/10575/MODIS_C6_Fire_User_Guide_B.pdf)
- [FIRMS FAQ](https://www.earthdata.nasa.gov/data/tools/firms/faq)
- [FIRMS Web Services Documentation](https://firms.modaps.eosdis.nasa.gov/web-services/)
- [Acknowledgements & Citation](https://www.earthdata.nasa.gov/data/projects/lance#ed-firms-citation)