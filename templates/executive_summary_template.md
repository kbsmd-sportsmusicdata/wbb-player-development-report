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

Add short explanation of how this project supports decisions.

## Top Findings

1. Add finding.
2. Add finding.
3. Add finding.

## Recommended Use Cases

{% for use_case in project_context.use_cases %}
- {{ use_case }}
{% endfor %}

## Limitations

{% for limitation in notes.limitations %}
- {{ limitation }}
{% endfor %}
