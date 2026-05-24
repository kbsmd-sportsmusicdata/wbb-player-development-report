# Data Dictionary: {{ project.title }}

## Overview

This document defines key fields used in the project datasets.

## Field Definitions

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| example_field | string | Example description | Source name | Not applicable | Replace with actual field |

## Primary Metrics

{% for metric in metrics.primary_metrics %}
### {{ metric.name }}

- Definition: {{ metric.definition }}
- Interpretation: {{ metric.interpretation }}
{% endfor %}

## Derived Metrics

{% for metric in metrics.derived_metrics %}
### {{ metric.name }}

- Formula: {{ metric.formula }}
- Interpretation: {{ metric.interpretation }}
{% endfor %}
