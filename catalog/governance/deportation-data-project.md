# Deportation Data Project

**Theme:** Governance / Immigration Enforcement Transparency
**Source:** Deportation Data Project — joint initiative of UC Berkeley (School of Law) and UCLA (Political Science); co-directed by Graeme Blair (UCLA), David Hausman (Berkeley Law), and Amber Qureshi (FOIA litigation counsel); funded by the Russell Sage Foundation, an anonymous foundation, the California Center for Population Research at UCLA, and the Society of Hellman Fellows Fund at Berkeley
**Coverage:** United States — individual-level federal immigration enforcement records, October 1, 2007–present (varies by agency/table); EOIR court case records extend back to the 1970s for some fields
**Unit of observation:** Individual-level record — a single arrest, detainer, detention stay, encounter, removal, court case, or benefit application (anonymized)
**Temporal granularity:** Event/record-level with dates; ICE data updated on a rolling basis (most recent release as of last verification: through August 6, 2026); EOIR updated monthly by the agency
**Format:** Individual-level microdata files (CSV/Parquet), agency-original files, codebooks, and reposted agency reports
**Access:** [https://deportationdata.org](https://deportationdata.org) — free, no registration; [Data repository](https://deportationdata.org/data.html) · [Data guide/FAQ](https://deportationdata.org/guide.html) · [Documentation](https://deportationdata.org/docs.html)
**License:** CC-0 (no rights reserved — full public domain dedication)
**Last verified:** July 2026

---

## What It Is

The Deportation Data Project collects, processes, and reposts individual-level U.S. government immigration enforcement datasets, obtained primarily through Freedom of Information Act (FOIA) litigation (led by co-director Amber Qureshi's firm), supplemented by datasets the government has released proactively or in response to others' FOIA requests. The project explicitly builds on and credits the Transactional Records Access Clearinghouse (TRAC), which first obtained access to many of these datasets.

Unlike aggregate summary statistics published by agencies themselves, this project posts **row-level microdata** — each record represents a single person's encounter, arrest, detention stay, court case, or benefit application — making it suited to researchers and analysts who want to run their own aggregations rather than rely on agency-published summaries. The project writes its own documentation and codebooks for each dataset (including known limitations and how each was obtained) and also reposts the agencies' own documentation where available.

---

## Datasets Available

| Agency | Dataset(s) | Notes |
|--------|-----------|-------|
| **ICE** (Immigration and Customs Enforcement) | Arrests, detainer requests, detentions, encounters, removals; detention management data; detention facility stints (collapsed to stay-level); detention facilities and field offices | Processed version includes possible-duplicate flags and standardized date fields; original (as-released) ICE files also posted, including older releases and non-current tables like ICE Air flight data |
| **CBP** (Customs and Border Protection) | Border Patrol arrest data; Office of Field Operations "inadmissible arrivals" data (most frequently asylum seekers at ports of entry) | Sourced from CBP's own FOIA library |
| **EOIR** (Executive Office for Immigration Review — the immigration courts, DOJ) | Every immigration court case: scheduling, case type, charges, applications for relief, appeals | Agency posts monthly to its own FOIA Library, originally compelled by a TRAC FOIA request; DDP reposts with a processed codebook alongside the original |
| **USCIS** (U.S. Citizenship and Immigration Services) | DACA applications (Form I-821D), Temporary Protected Status applications (Form I-821) | Individual-level application data obtained via *Mukherjee v. ICE* litigation; processed version has standardized field names and concatenated multi-part files into a single Parquet per form |
| **EOUSA** (Executive Office for United States Attorneys) | LIONS national caseload data — federal prosecutions of immigration-law violations | Covers all U.S. Attorney's office prosecutions, not immigration-specific offices only |
| **Agency reports** | Reposted PDF/summary reports from OHSS, ICE, CBP, and EOIR that draw on the same underlying microdata | Centralizes reports that are otherwise scattered across individual agency websites |

Prebuilt analysis tools are also provided for common tasks: ICE arrests, detention stays, arrests joined with detention stays, detention facility stints, immigration court case exploration, and DACA/TPS application exploration.

---

## Potential Research Questions

- How have ICE arrest and detention volumes shifted geographically and over time relative to policy changes (e.g., administration transitions, enforcement priority memos)?
- Do CBP border-arrest and inadmissible-arrival trends correlate with conditions captured elsewhere in this catalog, e.g. [ACLED](../peace-conflict/acled.md) conflict events or climate-driven displacement pressure in origin countries?
- Are immigration court case outcomes (EOIR) associated with detention duration or facility, and does this vary systematically by geography?
- How do detention facility-level stint durations compare across ICE field offices, and do disparities align with documented facility conditions or capacity reports?
- Could USCIS DACA/TPS application microdata be used to study downstream effects of status changes on local economic indicators (e.g., cross-referenced against [USAFacts](usafacts.md) county-level economic data)?

---

## Notes & Quirks

- **Individual-level, not pre-aggregated.** This is a deliberate design choice — the project expects users to have their own data-analysis capacity, since records aren't rolled up into summary tables. Expect to do your own cleaning/aggregation; codebooks document known duplicate-record flags and standardization steps already applied to the "processed" versions.
- **"Processed" vs. "original" files exist for most agencies** — processed versions have standardized date fields, possible-duplicate indicators, and (for USCIS) concatenated/standardized field names; original files are the as-released agency format, useful if you need to independently verify processing decisions.
- **Coverage start dates vary by agency/table** — ICE/CBP individual-level data generally starts October 1, 2007; EOIR case records can go back to the 1970s for some fields, but the bulk of usable records are far more recent. Always check the per-dataset documentation for exact coverage.
- **Data obtained via active FOIA litigation** — some tables may lag or be incomplete pending ongoing legal processes; the project posts frequent updates (e.g., an August 21, 2026 release brought ICE data through August 6, 2026) so check the site for the latest release before treating any local copy as current.
- **Anonymized, but still individual-level** — handle with the same care as other sensitive individual-level administrative data even though direct identifiers are removed; the project material is intended for use by journalists, researchers, lawyers, and policymakers.
- **CC-0 license** — genuinely public domain, no attribution technically required (though good practice to cite the project and underlying agency source as documented on each dataset's page).

---

## How to Access

1. Browse the data repository and download files directly: [https://deportationdata.org/data.html](https://deportationdata.org/data.html)
2. Read the data guide / FAQ before analysis: [https://deportationdata.org/guide.html](https://deportationdata.org/guide.html) (also published as a standalone guide: [Hausman, "U.S. Immigration Enforcement Data: A Short Guide," California Law Review](https://www.californialawreview.org/online/immigration-enforcement-guide))
3. Consult per-agency codebooks and documentation: [https://deportationdata.org/docs.html](https://deportationdata.org/docs.html)
4. Use prebuilt analysis tools (arrests, detention stays, court cases, DACA/TPS): linked from the site's Tools section
5. Background on the project and team: [https://deportationdata.org/about.html](https://deportationdata.org/about.html)
