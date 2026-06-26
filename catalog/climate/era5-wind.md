# ERA5 Wind Data (ECMWF Reanalysis v5)

**Theme:** Climate & Environment / Atmospheric Science
**Source:** European Centre for Medium-Range Weather Forecasts (ECMWF), distributed via the Copernicus Climate Data Store (CDS)
**Coverage:** Global
**Time Coverage:** 1940–present (continuously updated with ~5-day lag)
**Unit of observation:** Grid cell (0.25° × 0.25°, ~28 km at the equator)
**Temporal granularity:** Hourly native resolution; monthly aggregations available as a separate product
**Format:** NetCDF or GRIB (selectable at download)
**Access:** [https://cds.climate.copernicus.eu](https://cds.climate.copernicus.eu) — free; registration required
**License:** [Copernicus License Agreement](https://cds.climate.copernicus.eu/disclaimer-privacy) — free for research, commercial, and operational use with attribution
**Last verified:** June 2026

---

## Key Variables

ERA5 contains hundreds of variables. For wind, the most relevant are:

### Surface / Near-surface wind (Single-level product)

| Variable | CDS name | Description |
|----------|----------|-------------|
| `u10` | `10m_u_component_of_wind` | Eastward (zonal) wind speed at 10 m above surface, m/s |
| `v10` | `10m_v_component_of_wind` | Northward (meridional) wind speed at 10 m above surface, m/s |
| `u100` | `100m_u_component_of_wind` | Eastward wind at 100 m (boundary layer) |
| `v100` | `100m_v_component_of_wind` | Northward wind at 100 m (boundary layer) |
| `fg10` | `10m_wind_gust_since_previous_post_processing` | Maximum 10 m wind gust in the hour |
| `i10fg` | `instantaneous_10m_wind_gust` | Instantaneous gust at 10 m |

**Wind speed** (not a native variable) is derived as: `ws = sqrt(u10² + v10²)`

**Wind direction** (meteorological convention, degrees from north) is derived as: `wd = (270 - degrees(atan2(v10, u10))) % 360`

### Pressure-level wind (Pressure-level product)

Available at standard pressure levels (e.g., 850 hPa, 500 hPa, 250 hPa) — useful for upper-atmosphere or transport pathway analysis.

| Variable | Description |
|----------|-------------|
| `u` | Eastward wind component at pressure level, m/s |
| `v` | Northward wind component at pressure level, m/s |

---

## CDS Product Names

When downloading via the Copernicus portal or CDS API, these are the two main datasets for wind:

| Use case | CDS dataset name |
|----------|-----------------|
| Surface winds (u10, v10, gusts) | `reanalysis-era5-single-levels` |
| Upper-atmosphere winds | `reanalysis-era5-pressure-levels` |
| Monthly means (surface) | `reanalysis-era5-single-levels-monthly-means` |
| Monthly means (pressure levels) | `reanalysis-era5-pressure-levels-monthly-means` |

---

## How to Access (Manual Download via Copernicus Portal)

1. Register for a free account at [https://cds.climate.copernicus.eu](https://cds.climate.copernicus.eu)
2. Navigate to the relevant dataset (e.g., *ERA5 hourly data on single levels from 1940 to present*)
3. Under the **Download data** tab, configure:
   - **Product type:** Reanalysis
   - **Variable(s):** e.g., `10m u-component of wind`, `10m v-component of wind`
   - **Year / Month / Day / Time:** Select the range you need
   - **Geographical area:** Default is global; use the bounding box tool to subset by region
   - **Format:** NetCDF (recommended for analysis in Python/R) or GRIB
4. Submit the request — large requests are queued and you receive an email when ready
5. Download the `.nc` or `.grib` file

**Note:** Large spatial or temporal extents can take hours to process. For heavy use, the [CDS API (Python)](https://cds.climate.copernicus.eu/how-to-api) with `cdsapi` is more efficient than manual downloads.

---

## Potential Research Questions

- How does surface wind speed and direction influence wildfire spread and smoke transport?
- Do wind anomalies predict shifts in conflict event locations via smoke/haze exposure effects?
- What are seasonal wind patterns over a region of interest, and how do they co-vary with fire activity?
- How does wind-driven fire spread interact with vegetation and land use to produce fire risk?
- Can upper-atmosphere wind patterns be used to trace aerosol or pollution transport across borders?

---

## Notes & Quirks

- **u/v components vs. wind speed/direction:** ERA5 natively stores the vector components (`u`, `v`), not scalar speed or direction. Always derive these as needed rather than downloading a pre-computed product.
- **Conventions:** `u10 > 0` = wind blowing eastward; `v10 > 0` = wind blowing northward. Meteorological wind direction (where wind *comes from*) is the opposite of the vector direction.
- **Temporal aggregation:** Native hourly data is large. For most research applications, daily means or monthly means are sufficient and much smaller. Pre-aggregated monthly means are available as a separate CDS product.
- **Land–sea mask:** ERA5 interpolates over coastlines. For coastal or island geographies (e.g., Indonesia), check whether grid cells are classified as land or ocean if that distinction matters.
- **Spatial resolution:** The standard download is 0.25° (~28 km). A lower-resolution 0.5° product (ERA5-Land for land variables; reduced grids) is also available.
- **ERA5-Land:** A related product with higher spatial resolution (0.1°, ~9 km) for land-surface variables — does not include wind, but useful for companion variables like temperature and precipitation.
- **Time zone:** All ERA5 timestamps are in UTC.
- **Version history:** ERA5 replaced ERA-Interim (discontinued 2019). Do not mix ERA-Interim and ERA5 data in the same analysis without careful consideration of the differences.
