# Duodata Definitions

This directory contains the [Duodata](https://duodata.ai) metric definitions for this project. Duodata is an AI-powered metrics layer that establishes a single source of truth for KPIs, then projects them into your data stack (Snowflake, Databricks, BI tools, etc.) as version-controlled semantic models.

## Files

| File | Purpose |
|---|---|
| **config.yaml** | Governance settings: approval statuses, time periods, people (owners/stakeholders), and release milestones. |
| **sources.yaml** | Data sources that feed metric calculations. These correspond to your source systems (e.g., Salesforce)  |
| **dimensions.yaml** | Entities/attributes used to slice metrics -- entities like Company, Account Executive, and time periods. |
| **metrics.yaml** | Business metric definitions: the calculations, aggregations, granularity, and source mappings for each KPI. |
| **reports.yaml** | Report definitions that compose metrics and dimensions into specific analytical/semantic grouping (e.g. weekly flash, financials, headcount). |

## How they relate

```
sources  -->  dimensions  -->  metrics  -->  reports
                                  ^              |
                                  |   (sliced by)|
                                  +-dimensions---+
```

Sources supply data. Dimensions describe how to slice it. Metrics define what to measure. Reports assemble metrics and dimensions into consumable views. Config governs the lifecycle (status, ownership, releases) across all of the above.
