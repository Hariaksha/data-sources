# data-sources

# 🗂️ Research Data Catalog

> A personal index of datasets I use or expect to use across research projects in environmental economics, conflict studies, climate policy, and development. This repository does **not** store raw data files — it catalogs what I have, where to get it, what it contains, and what questions it can help answer.

---

## Purpose

Across research on topics like wildfire-conflict dynamics in Indonesia, climate commitments, and survey-based welfare measures, I accumulate data from many different sources. This catalog solves a recurring problem: *knowing what data I already have access to when scoping a new project.*

Each dataset entry answers four questions:

1. **What is it?** — Coverage, grain, format, update frequency
2. **How do I get it?** — Access link, registration requirements, license
3. **What's inside?** — Key variables worth knowing about
4. **What can I do with it?** — Example research questions it can help answer

---

## Repository Structure

## 🗂️ Repository Structure

- `data-catalog/`
  - `README.md` — master index & quick-reference table
  - `catalog/` — one `.md` file per dataset
    - `conflict/` → `acled.md`, ...
    - `climate/` → `nasa-wildfire-firms.md`, `net-zero-tracker.md`, ...
    - `surveys/` → `gallup-world-poll.md`, ...
  - `data/` — small samples & derived files only (< 5 MB)
  - `scripts/` — download, API fetch, and cleaning scripts

> **Note on data storage:** Raw files (`.csv`, `.dta`, `.xlsx`) are intentionally **not** committed here unless tiny. Large files are excluded via `.gitignore`. The value of this repo is the metadata, not the data itself.

---

## Dataset Index

### 🔴 Conflict & Political Violence

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| ACLED | Global, 1997–present | Event-level, daily | No | [→ catalog/conflict/acled.md](catalog/conflict/acled.md) |

---

### 🌿 Climate & Environment

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| NASA FIRMS Wildfire Detections | Global, 2000–present | Daily pixel (375m–1km) | Sample | [→ catalog/climate/nasa-wildfire-firms.md](catalog/climate/nasa-wildfire-firms.md) |
| Net Zero Tracker | Global | Organization-level, annual | No | [→ catalog/climate/net-zero-tracker.md](catalog/climate/net-zero-tracker.md) |

---

### 📊 Surveys & Public Opinion

| Dataset | Coverage | Grain | Stored | Link |
|---------|----------|-------|--------|------|
| Gallup World Poll | Global, 2005–present | Individual respondent | No | [→ catalog/surveys/gallup-world-poll.md](catalog/surveys/gallup-world-poll.md) |

---

## Dataset Card Template

Every file in `catalog/` follows this format. Copy it when adding a new source.

```markdown
# [Dataset Name]

**Theme:** [e.g. Conflict / Climate / Surveys / Trade / Health]
**Coverage:** [Geographic scope + time range]
**Unit of observation:** [Event / Individual / Country-year / Pixel / etc.]
**Temporal granularity:** [Daily / Monthly / Annual / etc.]
**Format:** [CSV / API / Shapefile / etc.]
**Access:** [URL] — [free / registration required / subscription]
**License:** [e.g. CC BY, non-commercial academic, restricted]
**Last verified:** [Month Year]

***

## Key Variables

| Variable | Description |
|----------|-------------|
| `var_name` | What it measures |

***

## Potential Research Questions

- Question 1
- Question 2

***

## Notes & Quirks

Any gotchas, merge keys, coordinate systems, or known data quality issues.

***

## How to Access

Step-by-step instructions or a link to a script in `scripts/`.
```

---

## Thematic Areas

This catalog covers data relevant to the following research areas:

- **Environmental economics** — pollution, natural disasters, resource use, firm behavior
- **Conflict & peace studies** — armed conflict events, protest, state repression
- **Climate policy** — net zero commitments, NDCs, carbon markets
- **Surveys & welfare** — self-reported wellbeing, preferences, political attitudes
- **Geospatial** — satellite-derived environmental and demographic data

---

## Adding a New Dataset

1. Copy the template above into a new `.md` file under the appropriate `catalog/[theme]/` subfolder
2. Fill in all fields — leave nothing blank (write *Unknown* if unsure)
3. Add a row to the Dataset Index table in this README
4. If you have a fetch/download script, add it to `scripts/` with a matching name

---

## Notes

- Maintained by [Hariaksha Gunda](https://github.com/Hariaksha)
- For personal research use; links and access instructions reflect availability as of the dates noted in each card
- Dataset availability, licensing, and access requirements may change — always verify before use in a project
