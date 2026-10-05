# Terminal-Bench-Science

**Theme:** Research Tools / AI Agent Evaluation
**Source:** Stanford, the Laude Institute, and the Harbor framework team (science extension of Terminal-Bench)
**Coverage:** 70 expert-written tasks across five scientific domains (version 0.1); no social science or economics tasks
**Unit of observation:** Task (one research workflow run by an agent in a terminal environment)
**Temporal granularity:** Versioned releases — v0.1 released August 27, 2026; v0.2 in development
**Format:** Task repository on GitHub (run with the Harbor CLI); public leaderboards
**Access:** [https://www.terminal-bench-science.ai](https://www.terminal-bench-science.ai) · [GitHub](https://github.com/harbor-framework/terminal-bench-science) · DOI: [10.5281/zenodo.22110253](https://doi.org/10.5281/zenodo.22110253)
**License:** See the GitHub repository; the maintainers ask that benchmark data never be included in AI training corpora
**Last verified:** October 2026

---

## What It Is

Terminal-Bench-Science measures how well AI agents can complete real computational research tasks from the command line. Each task gives an agent a computing environment and instructions drawn from an actual research workflow, such as a data-analysis pipeline, simulation setup, numerical solver, model fit, instrument-data processing, or image and signal analysis. Automated tests check whether the agent's result is correct.

It extends [Terminal-Bench](https://www.tbench.ai), a coding-agent benchmark used by major AI labs, into the natural sciences. Tasks are contributed by researchers through an open GitHub process and pass domain, technical, and final ("bar-raiser") review.

---

## Task Domains (v0.1)

| Domain | Tasks | Subfields |
|--------|-------|-----------|
| Life sciences | 19 | Biology, medicine and health, neuroscience, ecology and evolution |
| Physical sciences | 17 | Astronomy and cosmology, physics, materials science, chemistry |
| Mathematical sciences | 17 | Applied mathematics, operations research, formal mathematics, statistics |
| Engineering sciences | 9 | Mechanical and aerospace, electrical and computer, chemical and process, civil and structural |
| Earth sciences | 8 | Geoscience, atmosphere and climate, ocean and marine, environment and sustainability |

---

## Scoring and Results

- Each agent attempts each task in **three independent trials**; the score is the **resolution rate** (share of tasks solved).
- **At launch (August 2026):** Claude Opus 5 with Claude Code 30.0%, GPT-5.6 Sol with Codex 22.4%, Claude Fable 5 with Claude Code 21.4%.
- **Later third-party leaderboards** ([Snorkel](https://snorkel.ai/leaderboard/terminal-bench-science/), [Vals](https://www.vals.ai/benchmarks/terminal-bench-science)) report higher scores for newer models, e.g. GPT-6 Astra about 60% and Claude Opus 5.5 about 54%.
- Scores depend on the agent harness (Claude Code, Codex, etc.) as well as the model, so compare results only within one leaderboard.

---

## Potential Uses

- Judging how much to trust AI agents for computational steps in your own research, keeping in mind that it doesn't test social-science or econometric workflows
- Contributing a task from your own work: Earth sciences is the smallest domain (8 tasks). A candidate would be a verifiable climate-data workflow, e.g., combining [NASA FIRMS](../catalog/climate/wildfire-detections.md) fire detections with [ERA5 wind](../catalog/climate/era5-wind.md) data and checking a computed result
- Making the case for a social-science track: a benchmark task built on [ACLED](../catalog/peace-conflict/acled.md) plus a difference-in-differences analysis would cover ground this benchmark currently misses

---

## Notes & Quirks

- **Natural sciences only.** No economics, political science, or other social-science tasks in v0.1, so scores say little about agent performance on conflict or econometrics pipelines.
- **Small and early.** 70 tasks at version 0.1; per-domain samples are small (8 Earth-science tasks), so domain-level scores are noisy.
- **Leaderboards differ.** The official launch results and third-party leaderboards use different harnesses and dates; don't mix numbers across them.
- **Training contamination.** The maintainers ask that task content not be used for AI training, which matters if you contribute or repost tasks.
- **Contribution rounds have deadlines.** The v0.2 deadline was October 5, 2026; check the site for the next round.

---

## How to Access

1. Overview, leaderboard, and task hub: [https://www.terminal-bench-science.ai](https://www.terminal-bench-science.ai)
2. Release announcement (v0.1): [https://www.terminal-bench-science.ai/announcement](https://www.terminal-bench-science.ai/announcement)
3. Code and tasks: [https://github.com/harbor-framework/terminal-bench-science](https://github.com/harbor-framework/terminal-bench-science)
4. Contribute a task: propose through the site's task form, build following the contribution guidelines, then pass automated checks and expert review
5. Cite: DOI [10.5281/zenodo.22110253](https://doi.org/10.5281/zenodo.22110253)
