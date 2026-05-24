# Project Handoff: Lulu Twidale Development Report

## Current Status

in-progress

## Project Purpose

This project packages a notebook-style player development report for Lulu Twidale's first three California seasons. It combines season-level production, California-scoped play-by-play profile history, on/off context, recent form, and lineup evidence to show how her role, efficiency, and decision-making evolved from reserve guard to high-minute creator.

## Key Deliverables

- Primary deliverable: HTML notebook
- Notebook: `notebooks/index.html`
- Executive summary: `docs/executive_summary.md`
- Methodology: `docs/methodology.md`
- Data dictionary: `docs/data_dictionary.md`
- Validation report: `docs/validation_report.md`

## Important Scripts

- `scripts/init_project.py`
- `scripts/generate_docs.py`
- `scripts/generate_readme.py`
- `scripts/validate_data.py`
- `scripts/publish_check.py`

## Known Limitations

- 2023-24 regular-season on/off is unavailable because the raw play-by-play snapshot lacks substitution events.
- This repo ships reviewable evidence tables, not the full wbb-bis pipeline or raw play-by-play archive.
- On/off and lineup context are California-scoped and should be read as team-context evidence rather than a complete player-isolation model.

## Next Steps

- Publish the notebook through GitHub Pages and backfill the live URL into this config.
- Decide whether the public repo should also include a simplified dashboard export or remain notebook-first.
- Apply the same repo workflow to another player or team development report once this project is live.

## Deployment Notes

GitHub Pages should deploy `notebooks/index.html` through the workflow in `.github/workflows/deploy_pages.yml`.
