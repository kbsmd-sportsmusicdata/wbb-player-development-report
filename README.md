# Lulu Twidale Development Report

**A California player-development notebook tracking role growth, scoring efficiency, and playmaking progression from 2023-24 through 2025-26.**

This project packages a notebook-style player development report for Lulu Twidale's first three California seasons. It combines season-level production, California-scoped play-by-play profile history, on/off context, recent form, and lineup evidence to show how her role, efficiency, and decision-making evolved from reserve guard to high-minute creator.

## How To Use This Repo

1. Start with `notebooks/index.html` to read the full development story in notebook form.
2. Use the evidence tables in `data/processed/` to inspect season history, shot profile, on/off context, recent form, and lineup context behind the notebook.
3. Regenerate the docs and rerun the checks after any data or wording update:

```bash
python scripts/init_project.py
python scripts/validate_data.py
python scripts/publish_check.py
```

## Live Project

- HTML Notebook: https://kbsmd-sportsmusicdata.github.io/wbb-player-development-report/
- Portfolio Page: Not published yet
- Tableau Public: Not used for this project

## Project Status

published

## Why This Project Matters

Player development reports often flatten growth into one headline. This repo separates Lulu Twidale's role growth, efficiency changes, shot-profile evolution, and on-court context so reviewers can see what improved, what held steady, and what still needs caution.

## Key Questions

- How did Lulu Twidale's role change from her first California season through 2025-26?
- Where did the biggest gains show up: efficiency, playmaking, shot mix, or lineup impact?
- Which parts of the development story are strongest enough to trust, and which parts still need context or caution?

## Audience

- player development and coaching staff
- basketball operations and scouting reviewers
- sports analytics portfolio reviewers

## Project Outputs

- Primary deliverable: HTML notebook
- Notebook path: `notebooks/index.html`
- Report path: `docs/executive_summary.md`

## Data Sources

- Lulu season history
- California play-by-play profile history
- California player on/off
- Lulu recent form 2026
- Lulu regular lineup summary

## Methodology Summary

See [`docs/methodology.md`](docs/methodology.md).

## Validation Summary

See [`docs/validation_report.md`](docs/validation_report.md). Current warnings mostly reflect expected missing context fields, including unavailable 2023-24 on/off coverage and season-specific play-by-play sparsity, rather than broken files.

## Data Dictionary

See [`docs/data_dictionary.md`](docs/data_dictionary.md).

## Repo Structure

```text
/data
/docs
/notebooks
/reports
/scripts
/sql
/templates
```

## How To Run

```bash
pip install -r requirements.txt
python scripts/generate_docs.py
python scripts/validate_data.py
python scripts/generate_readme.py
```

## Next Steps

- Review whether a simplified dashboard companion would add value or whether the notebook should remain the only public surface.
- Reuse the same template workflow for another player or team development report.
- Decide whether to add branch protection on main after the repo settles.
