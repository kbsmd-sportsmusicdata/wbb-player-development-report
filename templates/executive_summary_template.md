# Executive Summary: {{ project.title }}

## Project Objective

{{ project.description }}

## Intended Audience

{% for item in project_context.audience %}
- {{ item }}
{% endfor %}

## Key Questions

{% for question in project_context.key_questions %}
- {{ question }}
{% endfor %}

## Decision-Support Value

This project supports player-development review by separating role growth from shot-quality changes and team-context impact. For staff or scouting readers, it helps answer whether Twidale's breakout was driven mostly by volume, better efficiency, improved creation, stronger lineup fit, or some combination of the four.

## Top Findings

1. Twidale's California role expanded sharply, moving from a 16.3-minute reserve profile in 2023-24 to a 36.2-minute high-usage creator by 2025-26.
2. Her efficiency jumped most dramatically in 2024-25, and while 2025-26 was a slightly less efficient season, the larger workload still paired with stronger playmaking volume and a higher-assist role.
3. The notebook's development read is strongest when it combines season history with California-scoped on/off and recent-form context, while still acknowledging that 2023-24 lineup/on-off reconstruction is unavailable.

## Recommended Use Cases

{% for use_case in project_context.use_cases %}
- {{ use_case }}
{% endfor %}

## Limitations

{% for limitation in notes.limitations %}
- {{ limitation }}
{% endfor %}
