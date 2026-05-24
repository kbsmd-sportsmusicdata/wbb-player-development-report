# Methodology: {{ project.title }}

## Data Sources

{% for source in methodology.data_sources %}
### {{ source.name }}

- URL: {{ source.url }}
- Notes: {{ source.notes }}
{% endfor %}

## Cleaning Steps

{% for step in methodology.cleaning_steps %}
- {{ step }}
{% endfor %}

## Feature Engineering

{% for item in methodology.feature_engineering %}
- {{ item }}
{% endfor %}

## Metrics

### Primary Metrics

{% for metric in metrics.primary_metrics %}
- **{{ metric.name }}**: {{ metric.definition }}
  - Interpretation: {{ metric.interpretation }}
{% endfor %}

### Derived Metrics

{% for metric in metrics.derived_metrics %}
- **{{ metric.name }}**: {{ metric.formula }}
  - Interpretation: {{ metric.interpretation }}
{% endfor %}

## Modeling Approach

{{ methodology.modeling_approach }}

## Selection Logic

This repo keeps the public package narrow on purpose. The notebook is the primary deliverable, and the shipped evidence tables were chosen to match the notebook's actual sections rather than to replicate the full internal workflow.

The file choices map directly to the report structure:

- `lulu_season_history_2024_2026.csv` supports the development-arc and season-over-season production view.
- `california_pbp_profile_history_2024_2026.csv` supports shot profile, creation style, and percentile context.
- `california_player_onoff_2025_2026.csv` supports the on/off and team-context section.
- `lulu_recent_form_2026.csv` supports the current-season trend and consistency read.
- `lulu_regular_lineup_summary.csv` gives a compact lineup layer without shipping the full stint table.

## Evidence Precedence

The report uses a simple evidence hierarchy:

1. The notebook is the public-facing narrative layer.
2. The CSV files in `data/processed/` are the reviewable evidence layer for the main claims in that notebook.
3. The broader `wbb-bis` workspace remains the upstream source environment, but it is intentionally not copied wholesale into this repo.

## Coverage Choices And Limitations

This project preserves one important availability caveat rather than smoothing it away: 2023-24 regular-season on/off is not shown because the raw play-by-play snapshot lacks substitution events for lineup reconstruction.

That means some validation warnings are expected. Missing shot-distance context in early seasons and missing quarter-level on/off detail in later summaries are part of the underlying source coverage, not signs that the exported evidence tables are broken.

## Validation Checks

{% for check in methodology.validation_checks %}
- {{ check }}
{% endfor %}

## Reproducibility Notes

This project uses a config-driven documentation workflow. Update `project_config.yml`, then regenerate docs using:

```bash
python scripts/generate_docs.py
python scripts/generate_readme.py
```
