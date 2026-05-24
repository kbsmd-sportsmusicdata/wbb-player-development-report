# Methodology: Lulu Twidale Development Report

## Data Sources

### Lulu season history

- URL: 
- Notes: Season-level player production table spanning 2023-24 through 2025-26.
### California play-by-play profile history

- URL: 
- Notes: California-scoped play-by-play summary used for shot mix, creation, and style context.
### California player on/off

- URL: 
- Notes: Regular-season on/off evidence for seasons where substitution events were available in raw play-by-play.
### Lulu recent form 2026

- URL: 
- Notes: Game-level 2025-26 trend table used for recent-form and context framing.
### Lulu regular lineup summary

- URL: 
- Notes: Compact lineup evidence used to identify the most common California groupings around Twidale.

## Cleaning Steps

- Aligned Lulu Twidale and Lulu Laditan-Twidale naming so all three seasons resolve to one player profile.
- Kept the notebook scoped to California seasons only, rather than mixing in broader player-history contexts.
- Limited on/off analysis to seasons with substitution events in raw play-by-play and preserved the 2023-24 availability note explicitly.
- Selected only the notebook-facing evidence tables needed to review development arc, shot profile, on/off, recent form, and lineup context.

## Feature Engineering

- Tracked season-over-season changes in minutes, points per 40, assists per 40, and true shooting percentage.
- Derived shot-share and creator-style context from California play-by-play profile history.
- Used position percentiles and development labels to frame the report as a staff-brief development read rather than a raw stat dump.

## Metrics

### Primary Metrics

- **Points per 40**: Points scored normalized to 40 minutes at the season level.
  - Interpretation: Higher values indicate stronger scoring volume independent of raw minutes.
- **True Shooting Percentage**: Scoring efficiency measure that combines two-point, three-point, and free-throw scoring.
  - Interpretation: Higher values indicate more efficient scoring conversion.
- **Assists per 40**: Assists normalized to 40 minutes at the season level.
  - Interpretation: Higher values indicate stronger playmaking volume within role.
- **On-Court Net Rating**: California's points scored minus points allowed per 100 possessions with Twidale on the floor.
  - Interpretation: Higher values indicate stronger team performance in her on-court minutes.

### Derived Metrics

- **Usage Proxy**: Project-level usage proxy from season-level offensive load indicators.
  - Interpretation: Higher values indicate a larger offensive burden.
- **Shot Mix Share**: Paint, midrange, three-point, and free-throw shot shares from play-by-play profile history.
  - Interpretation: Shows whether the scoring profile is becoming more balanced, more perimeter-heavy, or more rim-oriented.
- **Development Status**: Notebook-level developmental label combining trend, efficiency, and year-over-year context.
  - Interpretation: Summarizes whether the current season reads as stable, breakout, stalled, or mixed.

## Modeling Approach

Not applicable. This project is a descriptive player-development and context report, not a predictive model.

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

- Row count check
- Missing value check
- Duplicate check
- Schema check

## Reproducibility Notes

This project uses a config-driven documentation workflow. Update `project_config.yml`, then regenerate docs using:

```bash
python scripts/generate_docs.py
python scripts/generate_readme.py
```
