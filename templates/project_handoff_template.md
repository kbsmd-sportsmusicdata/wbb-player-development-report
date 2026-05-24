# Project Handoff: {{ project.title }}

## Current Status

{{ project.status }}

## Project Purpose

{{ project.description }}

## Key Deliverables

- Primary deliverable: {{ outputs.primary_deliverable }}
- Notebook: `{{ outputs.notebook_path }}`
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

{% for limitation in notes.limitations %}
- {{ limitation }}
{% endfor %}

## Next Steps

{% for step in notes.next_steps %}
- {{ step }}
{% endfor %}

## Deployment Notes

GitHub Pages should deploy `notebooks/index.html` through the workflow in `.github/workflows/deploy_pages.yml`.
