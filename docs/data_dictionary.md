# Data Dictionary: Lulu Twidale Development Report

## Overview

This document defines key fields used in the project datasets.

## Included Files

- `data/processed/lulu_season_history_2024_2026.csv`: season-level production and percentile history across Lulu Twidale's three California seasons.
- `data/processed/california_pbp_profile_history_2024_2026.csv`: California-scoped play-by-play profile history with shot mix, creation, and style context.
- `data/processed/california_player_onoff_2025_2026.csv`: regular-season on/off summary for the seasons with substitution-event coverage.
- `data/processed/lulu_recent_form_2026.csv`: game-level 2025-26 performance log used for trend and consistency context.
- `data/processed/lulu_regular_lineup_summary.csv`: compact regular lineup evidence for the most common California groupings around Twidale.

## Key Fields By File

### lulu_season_history_2024_2026.csv

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| `season` | integer | Season end year used in the report. | Season history table | Not applicable | `2024` maps to `2023-24`, and so on. |
| `mpg` | float | Minutes per game. | Season history table | `minutes_total / games_played` | Used to track role growth. |
| `pts_per40` | float | Points per 40 minutes. | Season history table | `pts_total / minutes_total * 40` | Normalizes scoring across changing minutes. |
| `ts_pct` | float | True shooting percentage. | Season history table | Scoring efficiency formula across field goals and free throws | Central efficiency measure in the notebook. |
| `ast_per40` | float | Assists per 40 minutes. | Season history table | `ast_total / minutes_total * 40` | Used to show playmaking growth. |
| `usage_proxy` | float | Project-level usage proxy. | Season history table | Derived from offensive load indicators | Higher values indicate larger offensive burden. |

### california_pbp_profile_history_2024_2026.csv

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| `season` | integer | Season end year for the play-by-play profile row. | California PBP profile history | Not applicable | One row per season. |
| `three_share` | float | Share of shots taken from three-point range. | California PBP profile history | `three_fga / total_shots` style share derivation | Helps define the perimeter-heavy scoring profile. |
| `paint_share` | float | Share of shots taken at the rim or in the paint. | California PBP profile history | Derived from paint shot volume | Used with three-share to explain shot-diet balance. |
| `assisted_fg_rate` | float | Share of made field goals that were assisted. | California PBP profile history | `assisted_fgm / fg_made_total` | Helps separate off-ball finishing from self-creation. |
| `shot_creator_type` | string | Notebook-facing scoring/creation label. | Project-level derived classification | Derived from shot and creation context | Used for the report's style framing. |
| `playmaking_style` | string | Notebook-facing playmaking label. | Project-level derived classification | Derived from assist and creation context | Pairs with creator type in the shot-profile section. |

### california_player_onoff_2025_2026.csv

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| `season` | integer | Season end year for the on/off summary. | California player on/off table | Not applicable | Coverage begins in 2024-25 because 2023-24 substitutions are unavailable. |
| `on_off_rtg` | float | California offensive rating with Twidale on the floor. | California player on/off table | Points scored per 100 possessions | Used as the offensive side of the lineup context. |
| `on_def_rtg` | float | California defensive rating with Twidale on the floor. | California player on/off table | Points allowed per 100 possessions | Used to contextualize team results during her minutes. |
| `on_net_rtg` | float | Net rating with Twidale on the floor. | California player on/off table | `on_off_rtg - on_def_rtg` | Primary team-context impact field. |
| `close_net_rtg` | float | Net rating in close-game possessions. | California player on/off table | Close-game subset of on/off | Used when the report discusses tighter game states. |

### lulu_recent_form_2026.csv

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| `game_date` | string | Date of the game in the 2025-26 season log. | Recent-form game log | Not applicable | Supports trend visual ordering. |
| `points` | float | Points scored in the game. | Recent-form game log | Not applicable | Main single-game scoring output. |
| `assists` | float | Assists recorded in the game. | Recent-form game log | Not applicable | Helps track guard creation game to game. |
| `ts_pct_game` | float | Single-game true shooting percentage. | Recent-form game log | Per-game TS% formula | Used for efficiency trend context. |
| `game_score` | float | Single-game game score value. | Recent-form game log | Notebook source metric | Used in recent-form and consistency framing. |
| `game_score_L10` | float | Rolling last-10 game score context. | Recent-form game log | Rolling summary field | Useful for seeing current-season trend direction. |

### lulu_regular_lineup_summary.csv

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| `season` | integer | Season end year for the lineup grouping. | Regular lineup summary | Not applicable | Keeps lineup context season-specific. |
| `lineup_str` | string | Encoded player-identifier lineup string. | Regular lineup summary | Not applicable | Internal lineup key used by the source workflow. |
| `stints` | integer | Number of stints logged for the lineup. | Regular lineup summary | Not applicable | Helps identify which groups were most common. |
| `minutes` | float | Minutes played by the lineup. | Regular lineup summary | Aggregated stint minutes | High-minute groups are most useful for review. |
| `plus_minus` | float | Score differential while the lineup was on the floor. | Regular lineup summary | Not applicable | Basic outcome context for the lineup group. |
| `net_rtg` | float | Net rating for the lineup grouping. | Regular lineup summary | Possession-based rating calculation | Used as compact lineup-impact evidence. |

## Primary Metrics

### Points per 40

- Definition: Points scored normalized to 40 minutes at the season level.
- Interpretation: Higher values indicate stronger scoring volume independent of raw minutes.
### True Shooting Percentage

- Definition: Scoring efficiency measure that combines two-point, three-point, and free-throw scoring.
- Interpretation: Higher values indicate more efficient scoring conversion.
### Assists per 40

- Definition: Assists normalized to 40 minutes at the season level.
- Interpretation: Higher values indicate stronger playmaking volume within role.
### On-Court Net Rating

- Definition: California's points scored minus points allowed per 100 possessions with Twidale on the floor.
- Interpretation: Higher values indicate stronger team performance in her on-court minutes.

## Derived Metrics

### Usage Proxy

- Formula: Project-level usage proxy from season-level offensive load indicators.
- Interpretation: Higher values indicate a larger offensive burden.
### Shot Mix Share

- Formula: Paint, midrange, three-point, and free-throw shot shares from play-by-play profile history.
- Interpretation: Shows whether the scoring profile is becoming more balanced, more perimeter-heavy, or more rim-oriented.
### Development Status

- Formula: Notebook-level developmental label combining trend, efficiency, and year-over-year context.
- Interpretation: Summarizes whether the current season reads as stable, breakout, stalled, or mixed.
