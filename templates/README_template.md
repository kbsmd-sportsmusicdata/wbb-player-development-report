# {{ project.title }}

**{{ project.subtitle }}**

{{ project.description }}

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

- HTML Notebook: {{ links.github_pages or "Pending GitHub Pages deployment" }}
- Portfolio Page: {{ links.portfolio_page or "Not published yet" }}
- Tableau Public: {{ links.tableau_public or "Not used for this project" }}

## Project Status

{{ project.status }}

## Why This Project Matters

Player development reports often flatten growth into one headline. This repo separates Lulu Twidale's role growth, efficiency changes, shot-profile evolution, and on-court context so reviewers can see what improved, what held steady, and what still needs caution.

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

{% for step in notes.next_steps %}
- {{ step }}
{% endfor %}
