# Project Title

**Short project subtitle**

One-paragraph project description.

## How To Use This Template

1. Copy this template into a new repo for your project.
2. Update `project_config.yml` with your project metadata and links.
3. Replace `notebooks/index.html` with your final HTML notebook or dashboard export.
4. Optionally add small datasets to `data/processed/` and list them under `data.expected_files`.
5. Run the setup and checks:

```bash
python scripts/init_project.py
python scripts/validate_data.py
python scripts/publish_check.py
```

## Live Project

- HTML Notebook: 
- Portfolio Page: 
- Tableau Public: 

## Project Status

draft

## Why This Project Matters

Add project problem statement.

## Key Questions

- What question does this project answer?
- What decision does this analysis support?

## Audience

- sports analytics portfolio reviewers
- front office decision-makers
- coaching staff

## Project Outputs

- Primary deliverable: HTML notebook
- Notebook path: `notebooks/index.html`
- Report path: `docs/executive_summary.md`

## Data Sources

- Source Name
## Methodology Summary

See [`docs/methodology.md`](docs/methodology.md).

## Validation Summary

See [`docs/validation_report.md`](docs/validation_report.md).

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

- List next step.
