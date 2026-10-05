# Sustainable Development Report (SDG Index & Dashboards)

**Theme:** Development & Wellbeing / Sustainable Development Goals (all 17 SDGs)
**Source:** UN Sustainable Development Solutions Network (SDSN) and its SDG Transformation Center; published with Dublin University Press. Lead authors (2026): Sachs, Lafortune, Fuller & Iablonovski
**Coverage:** All 193 UN Member States assessed; 169 ranked in the 2026 SDG Index (Eritrea and Timor-Leste ranked for the first time). Annual editions since 2016; data explorer covers 2000–2026 for 108 trend indicators
**Unit of observation:** Country (indicator, goal, and overall index levels)
**Temporal granularity:** Annual report; backcasted country scores and rankings for 2015–2026 using consistent indicators and thresholds
**Format:** Interactive web dashboards (17 goal maps, country profiles, data explorer); downloadable Excel database, codebook, methodology papers, and report PDF
**Access:** [https://dashboards.sdgindex.org](https://dashboards.sdgindex.org) — free · Database and methodology: [SDG Transformation Center](https://sdgtransformationcenter.org/)
**License:** Free to download; no explicit open license stated on the site — cite SDSN and the original indicator sources
**Last verified:** October 2026

---

## What It Is

The Sustainable Development Report (SDR) tracks every UN member's progress on the 17 Sustainable Development Goals. It is not an official UN statistic: it's an independent assessment by SDSN that assembles indicators from official and unofficial sources (UN agencies, World Bank, OECD, NGOs, research groups) and scores them against targets.

It has three main products:

- **SDG Index:** an overall 0–100 score ("percent of the way to optimal performance"), averaging the 17 goals with equal weight. In 2026, Finland, Sweden, and Denmark rank first to third.
- **SDG Dashboards:** a color rating and trend arrow for each country on each goal and indicator.
- **International Spillover Index:** measures positive and negative effects a country has on other countries' ability to reach the SDGs (e.g., through trade, emissions embodied in imports, arms exports, tax havens).

The 2026 edition uses **123 indicators**: 101 used for all countries, plus 22 extra indicators for OECD members' dashboards. A smaller **SDG Headline Index** (one indicator per goal, 17 total) covers 146 countries, to reduce bias from missing data.

---

## The 17 Goals

| SDG | Goal |
|-----|------|
| 1 | No Poverty |
| 2 | Zero Hunger |
| 3 | Good Health and Well-being |
| 4 | Quality Education |
| 5 | Gender Equality |
| 6 | Clean Water and Sanitation |
| 7 | Affordable and Clean Energy |
| 8 | Decent Work and Economic Growth |
| 9 | Industry, Innovation and Infrastructure |
| 10 | Reduced Inequalities |
| 11 | Sustainable Cities and Communities |
| 12 | Responsible Consumption and Production |
| 13 | Climate Action |
| 14 | Life Below Water |
| 15 | Life on Land |
| 16 | Peace, Justice and Strong Institutions |
| 17 | Partnerships for the Goals |

Each goal has its own dashboard map, e.g. `https://dashboards.sdgindex.org/map/goals/SDG16/` (replace the number for other goals).

**Example — SDG 16** draws on 11 indicators: homicides, perceived safety, unsentenced detainees, prison population, access to and affordability of justice, Corruption Perceptions Index, press freedom, child labor, birth registration, arms exports, timeliness of court proceedings, and lawful expropriation. Most come from external datasets (Transparency International, Reporters Without Borders, UNODC, World Justice Project, SIPRI, UNICEF), several of which are cataloged separately here.

---

## Methodology

- **Normalization:** each indicator is rescaled to 0–100 between a lower bound (worst performance) and an upper bound (target or optimum). Upper bounds come from SDG targets, science-based targets, the average of top performers, or expert input.
- **Aggregation:** indicators are averaged within each goal, and the 17 goals are averaged with equal weight into the SDG Index.
- **Dashboard colors:** green (goal achieved), yellow, orange, and red (major challenges remain), plus grey where data is missing. Goal-level ratings are driven by the worst-performing indicators in that goal, so one bad indicator can turn a goal red.
- **Trend arrows:** whether a country is on track, moderately improving, stagnating, or decreasing, based on recent rates of change relative to what's needed to reach the target by 2030.
- **Inclusion:** countries with too much missing data are left out of the ranking (often conflict-affected or small states), though they still appear in the dashboards.
- **Review:** SDSN publishes methodology papers and held a public consultation on the 2026 indicators (April 17–27, 2026).

---

## Key Variables (Excel Database)

- Overall SDG Index score and rank
- Goal scores (17) and dashboard ratings and trends for each
- Indicator raw values, normalized scores, ratings, and trends (123 indicators)
- Spillover Index score
- Headline Index score
- Backcasted scores and ranks, 2015–2026

---

## Potential Research Questions

- Do conflict events ([ACLED](../peace-conflict/acled.md)) predict stagnation or decline in SDG scores, and on which goals (e.g., SDG 2 hunger, SDG 4 education, SDG 16 institutions)?
- How do Indonesia's SDG 13 (climate) and SDG 15 (life on land) scores relate to fire activity measured independently by [NASA FIRMS](../climate/wildfire-detections.md)?
- Are countries with large negative spillovers (e.g., embodied deforestation in imports) the main drivers of land-use pressure in producer countries like Indonesia?
- Does foreign aid ([GODAD](godad.md)) targeted at specific sectors line up with improvement on the corresponding goals?

---

## Notes & Quirks

- **Scores aren't comparable across editions.** Indicators and thresholds change each year. Use the backcasted 2015–2026 series in the current edition for any over-time comparison, not scores copied from older reports.
- **Mostly a repackaging of other datasets.** For research, the original indicator sources usually give longer series, finer detail, and clearer documentation. The SDR is most useful for screening countries and finding which indicators measure each goal.
- **Ratings depend on threshold choices.** Color ratings and "achieved" judgments reflect SDSN's chosen bounds and the worst-indicator rule, which can make goal ratings sensitive to a single indicator.
- **Missing data isn't random.** Fragile and conflict-affected countries are the most likely to be unranked or to have grey cells, which biases cross-country comparisons toward more stable states.
- **Country-level only** in the global edition. Regional and national editions exist (Europe since 2019, Arab region, small island developing states, and countries such as Brazil, India, Spain, and the United States), some with subnational data.
- **OECD extra indicators.** OECD countries are assessed on 22 more indicators than others, so their dashboards aren't directly comparable to non-OECD dashboards.

---

## How to Access

1. Browse dashboards, goal maps, and country profiles: [https://dashboards.sdgindex.org](https://dashboards.sdgindex.org)
2. Download the Excel database, codebook, and report PDF from the same site's downloads section
3. Methodology papers and the full database: [SDG Transformation Center](https://sdgtransformationcenter.org/)
4. 2026 methodology chapter: [Part 2 — The SDG Index and Dashboards](https://dashboards.sdgindex.org/chapters/part-2-the-sdg-index-and-dashboards/)
5. Regional editions, e.g. [Europe SDR 2026](https://eu-dashboards.sdgindex.org/downloads/)
