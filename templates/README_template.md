# {{ project.title }}

**{{ project.subtitle }}**

{{ project.description }}

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

- HTML Notebook: {{ links.github_pages }}
- Portfolio Page: {{ links.portfolio_page }}
- Tableau Public: {{ links.tableau_public }}

## Project Status

{{ project.status }}

## Why This Project Matters

{{ project_context.problem_statement | default("Add project problem statement.") }}

## Key Questions

{% for question in project_context.key_questions %}
- {{ question }}
{% endfor %}

## Audience

{% for item in project_context.audience %}
- {{ item }}
{% endfor %}

## Project Outputs

- Primary deliverable: {{ outputs.primary_deliverable }}
- Notebook path: `{{ outputs.notebook_path }}`
- Report path: `{{ outputs.report_path }}`

## Data Sources

{% for source in methodology.data_sources %}
- {{ source.name }}{% if source.url %}: {{ source.url }}{% endif %}
{% endfor %}

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

{% for step in notes.next_steps %}
- {{ step }}
{% endfor %}
