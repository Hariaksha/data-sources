# Project Cosmos (Carbon Brief)

**Theme:** Climate / Bibliometrics / Science of Science
**Coverage:** Global — all climate change research linked to IPCC reports (1990–present) and 22 climate-focused journals (through 31 December 2025)
**Unit of observation:** Publication / Author / Institution
**Temporal granularity:** Publication-level (year of publication); database updated annually at end of each calendar year
**Format:** Interactive web tool; not publicly downloadable (restricted access — see below)
**Access:** [https://interactive.carbonbrief.org/cosmos/index.html](https://interactive.carbonbrief.org/cosmos/index.html) — free to browse; data access requires a research proposal submitted to cosmos@carbonbrief.org
**License:** Not open source; Carbon Brief has deliberately restricted bulk access to prevent AI scraping. Interactive browsing is free. Research collaborations considered on request.
**Last verified:** June 2026

---

## What It Is

Project Cosmos is Carbon Brief's database of climate change research — billed as the largest and most complete mapping of climate science ever assembled. It contains **1,816,639 unique publications** connected by **40 million citation relationships**, built from IPCC reports (all six assessment cycles, 1990–2023) and 22 peer-reviewed climate-focused journals.

The database was constructed by extracting references from every major IPCC report ever published, tracing those citations outward through second-order references, identifying papers that cite the IPCC, and pulling all studies from 22 dedicated climate journals. It is stored in Neo4j (a graph database) to enable citation network analysis.

---

## Database Structure (Five Pillars)

| Pillar | Description | Unique publications |
|--------|-------------|-------------------|
| **I-REF** | Publications directly referenced in any IPCC report since 1990 | 106,782 |
| **I-SOR** | Second-order references — publications cited by I-REF works | 1,383,877 |
| **I-CITER** | Publications that themselves cite an IPCC report or chapter | 167,740 |
| **J-STUD** | All studies published in 22 dedicated climate journals through Dec 2025 | 51,804 |
| **J-REF** | Publications cited by J-STUD works | 641,917 |

---

## Key Variables

Each publication entry contains up to 30 metadata fields sourced via OpenAlex:

| Variable | Description |
|----------|-------------|
| `title` | Publication title |
| `doi` | Digital object identifier |
| `year` | Year of publication |
| `authors` | List of authors |
| `institution` | Author affiliations at time of publication |
| `openalex_id` | Unique ID assigned by OpenAlex |
| `topics` | Research topics (~4,500 topics in a 4-level hierarchy, auto-assigned by OpenAlex) |
| `abstract` | Full abstract text (enables keyword search and NLP) |
| `citation_score` | Number of times cited within the Cosmos database (excluding IPCC self-citations) |
| `h_index` | Author h-index from Google Scholar (authors only; covers all their publications, not just Cosmos entries) |
| `pillar` | Which of the five database pillars the publication belongs to |

---

## Cosmos 500 Rankings

Carbon Brief's initial published analysis includes three ranked lists (top 500 each), available interactively:

- **Most cited publications** — [/cosmos/data/publications/](https://interactive.carbonbrief.org/cosmos/data/publications/)
- **Most cited authors** (1.6m unique authors in database) — [/cosmos/data/authors/](https://interactive.carbonbrief.org/cosmos/data/authors/)
- **Most cited institutions** — [/cosmos/data/institutions/](https://interactive.carbonbrief.org/cosmos/data/institutions/)

All three rankings are also produced for the **IPCC-only subset** (the 107,000 I-REF publications directly cited by IPCC reports).

---

## Potential Research Questions

- Which climate science topics, journals, and institutions are most influential within IPCC-cited literature?
- How has citation density and topic emphasis shifted across IPCC assessment cycles (AR1–AR6)?
- Are there systematic gaps in IPCC-cited literature (geographic, topical, language)?
- Which authors or institutions are central nodes in the climate citation network?
- How does citation influence within Cosmos compare to broader bibliometric measures (h-index, Scopus)?
- What is the lag between publication and first IPCC citation, and how does it vary by topic?

---

## Notes & Quirks

- **Not open source.** Carbon Brief explicitly chose not to release the full database publicly due to AI scraping concerns. Interactive tools let you browse the Cosmos 500 rankings; full data requires a research partnership.
- **Citation scores are internal.** A publication's citation count reflects how often it is cited *within the Cosmos database*, not in broader academic literature — do not compare directly to Scopus or Web of Science counts.
- **IPCC reports excluded from rankings.** IPCC reports/chapters are omitted from citation score calculations and rankings because their internal cross-citations would dominate the rankings.
- **OpenAlex as backbone.** All metadata and institution affiliations are sourced from OpenAlex. Any coverage gaps or errors in OpenAlex propagate into Cosmos.
- **Language.** >97% of publications are in English; French and Spanish also present.
- **Temporal depth.** The oldest publication in the database dates to 1483. The practical research-relevant range is roughly 1950–2025.
- **Annual updates.** The database is updated at the end of each calendar year; journal coverage currently runs through 31 December 2025.
- **22 journals only.** Major multidisciplinary journals (Nature, Science) are excluded on the grounds that their climate-relevant articles are likely captured through IPCC citations. This means highly cited papers in those journals may be underrepresented if not IPCC-cited.

---

## How to Access

1. **Browse freely** at [https://interactive.carbonbrief.org/cosmos/index.html](https://interactive.carbonbrief.org/cosmos/index.html) — interactive maps, rankings, and individual author/publication/institution pages.
2. **For data access**, submit a research proposal to: **cosmos@carbonbrief.org**. Carbon Brief invites co-authored projects from academics, journalists, and analysts.
3. **Cite as:** Hickman, L. et al. *Introducing Project Cosmos: Carbon Brief's 'universe' of climate science* (Carbon Brief, 2026) https://interactive.carbonbrief.org/cosmos/index.html
