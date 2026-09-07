# India Air Pollution — Environmental Risk Intelligence

## From Pollution Measurement to Evidence-Based Intervention Priorities

A data analytics and Power BI project analyzing India's historical air pollution monitoring data to identify pollution patterns, geographic hotspots, contextual risk factors, historical changes, evidence strength, and practical intervention priorities.

The project follows a six-stage analytical narrative:

**What → Where → Context → Change → Confidence → Action**

---

## Project Overview

Air pollution is a complex environmental challenge with substantial variation across locations, pollutants, seasons, and monitoring contexts. This project transforms historical air-quality monitoring records into an interactive environmental risk intelligence solution using Python, data preparation, exploratory analysis, and Power BI.

The objective is not only to describe pollution levels, but to build a structured analytical story that moves from national-level situational awareness toward evidence-based intervention priorities.

---

## Project Objectives

- Understand the overall distribution of major air pollutants across India.
- Identify states and locations associated with higher pollution concentrations.
- Examine pollution patterns across monitoring-area types and seasons.
- Analyze historical pollution patterns and changes over time.
- Evaluate data completeness and evidence strength before making decisions.
- Translate analytical findings into a practical prioritization and action framework.
- Build an interactive Power BI dashboard narrative for decision-oriented analysis.

---

## Dataset

The project uses the India Air Quality dataset and a processed analytical dataset created during the data preparation stage.

### Processed Dataset Scale

| Metric | Value |
|---|---:|
| Records | 432,396 |
| Columns | 21 |
| Locations | 301 |
| States | 34 |
| Coverage | 1987–2015 |
| Overall Completeness | 86.1% |

### Main Pollutants

- SO2 — Sulfur Dioxide
- NO2 — Nitrogen Dioxide
- RSPM — Respirable Suspended Particulate Matter
- SPM — Suspended Particulate Matter
- PM2.5 — Particulate Matter 2.5

SO2, NO2, RSPM, and SPM form the primary long-coverage pollution story. PM2.5 is treated as a supporting indicator because its historical coverage is more limited.

---

## Data Preparation and Cleaning

The analytical dataset was prepared using Python and Pandas.

Key preparation steps included:

1. Loading and inspecting the source dataset.
2. Checking dataset shape, data types, duplicates, and missing values.
3. Removing duplicate records.
4. Handling missing categorical values for agency and monitoring type.
5. Removing records where all major pollutant measurements were unavailable.
6. Filling missing locations using state-level information where appropriate.
7. Handling missing monitoring-station information using location-level information where appropriate.
8. Imputing missing SO2, NO2, and RSPM values using state-and-location-level medians.
9. Converting and validating date information.
10. Removing records where a valid date could not be established.
11. Converting station-code values to a validated numeric representation.
12. Performing descriptive statistics and pollutant-level data validation.
13. Checking negative and zero pollutant values.
14. Performing IQR-based outlier analysis.
15. Creating analytical fields for year, month, month name, quarter, season, decade, pollutant categories, and pollutant availability.

---

## Analytical Guardrails

The project applies several analytical principles to avoid overstating what the data can support.

### Concentration vs. Count

Pollutant concentrations are analyzed using averages and related descriptive measures. Concentrations are not summed because summing concentration measurements across records would not represent a meaningful pollution intensity measure.

### Unknown Values

Unknown or unavailable categorical values are retained when they cannot be reliably inferred rather than being assigned unsupported values.

### Station Codes

`stn_code` is not used for station-level metrics unless its meaning and validity are explicitly established.

### Causal Interpretation

The dashboards identify patterns and associations. They do not claim that a particular monitoring-area type directly causes higher pollution.

### Data Completeness

Pollution levels are interpreted together with measurement completeness. Stronger evidence supports stronger conclusions, while weaker coverage requires additional validation and caution.

---

## Evidence Strength

| Pollutant | Completeness | Interpretation |
|---|---:|---|
| NO2 | 99.98% | Strong evidence |
| SO2 | 99.98% | Strong evidence |
| RSPM | 98.58% | Strong evidence |
| SPM | 45.83% | Limited evidence |
| PM2.5 | Limited historical coverage | Supporting indicator |

The overall dataset completeness is approximately **86.1%**.

The lower completeness of SPM is an important analytical limitation. Higher observed pollution levels in areas with weaker data coverage should trigger validation and caution rather than being treated as equally strong evidence.

---

# Power BI Dashboard Narrative

The project is organized into six dashboards. Each dashboard answers a specific decision question and advances the analytical story.

## Dashboard 1 — India Environmental Risk Overview

**Question:** What is happening?

**Purpose:** Situational Awareness

The first dashboard provides a national-level overview of India's historical air pollution monitoring landscape.

It establishes:

- Overall monitoring scale.
- Pollution concentration patterns.
- Geographic coverage.
- Pollutant-level overview.
- Seasonal patterns.
- High-level interactive filtering.

Users can explore the data by dimensions such as year, state, and season.

This dashboard is designed for orientation and situational awareness rather than detailed diagnosis.

---

## Dashboard 2 — Pollution Risk Landscape

**Question:** Where is the burden concentrated?

**Purpose:** Hotspot Detection

The second dashboard moves from **what** is happening to **where** pollution is concentrated.

It focuses on:

- State-level pollution rankings.
- Location-level pollution rankings.
- Geographic distribution of pollution.
- Identification of potential high-pollution areas.
- Transition from national overview to local investigation.

The location-level view creates a bridge toward the contextual analysis presented in Dashboard 3.

---

## Dashboard 3 — Industrial & Urban Risk Profile

**Question:** What context is associated with higher pollution?

**Purpose:** Risk Context

This dashboard examines pollution patterns across different monitoring-area types and contextual conditions.

The analysis compares:

- Industrial areas.
- Residential areas.
- Sensitive areas.
- State-level differences.
- Seasonal differences.
- Location-level patterns.
- Year-level patterns.

The dashboard supports hierarchical exploration through:

**State → Type → Season → Location → Year**

A decomposition-tree approach is used to explore combinations associated with higher pollution levels.

The analysis deliberately uses association-based language and does not interpret monitoring-area type as proof of causation.

---

## Dashboard 4 — Historical Pollution Risk & Escalation

**Question:** How is pollution changing?

**Purpose:** Threat Trajectory

The fourth dashboard introduces the time dimension to identify historical pollution patterns.

It examines:

- Long-term pollution patterns.
- State-level trajectories.
- Seasonal changes.
- Recurring high-intensity combinations.
- Historical concentration patterns across pollutants and locations.

The dashboard is intended to identify patterns that may warrant further investigation and monitoring.

Historical trend measures should be interpreted using appropriate averages and validated analytical definitions rather than summed concentration values.

---

## Dashboard 5 — Environmental Risk & Decision Security

**Question:** How strong is the evidence?

**Purpose:** Confidence and Uncertainty

The fifth dashboard evaluates whether the underlying data is sufficiently complete to support confident interpretation.

It focuses on:

- Overall data completeness.
- Pollutant-level completeness.
- Strong versus limited evidence.
- Areas where higher pollution coincides with weaker data coverage.
- Analytical uncertainty and decision caution.

This dashboard adds an important layer to the project: **a pollution finding is only as strong as the evidence supporting it.**

NO2, SO2, and RSPM provide strong historical evidence because of their high completeness. SPM requires greater caution because of its materially lower completeness.

---

## Dashboard 6 — Pollution Reduction Strategy & Action Plan

**Question:** What realistic interventions should be considered?

**Purpose:** Decision and Action

The final dashboard translates analytical findings into a structured intervention framework.

### 1. PRIORITIZE

Focus attention on high-pollution hotspots identified through the analysis.

### 2. VALIDATE

Check official action plans, local evidence, and other authoritative sources before selecting specific interventions.

### 3. TARGET

Select interventions that are appropriate for the local pollution context and monitoring-area characteristics.

### 4. MONITOR

Reassess pollution levels after intervention to evaluate whether conditions improve.

### Governance Principle

Ambient pollution monitoring data can identify candidate intervention areas. Specific hotspot-level actions should be grounded in official local action plans, source-apportionment evidence, or other authoritative evidence.

---

# Analytical Narrative

The six dashboards form a single decision-oriented story:

| Stage | Dashboard | Key Question |
|---|---|---|
| What | India Environmental Risk Overview | What is happening? |
| Where | Pollution Risk Landscape | Where is the burden concentrated? |
| Context | Industrial & Urban Risk Profile | What context is associated with higher pollution? |
| Change | Historical Pollution Risk & Escalation | How is pollution changing? |
| Confidence | Environmental Risk & Decision Security | How strong is the evidence? |
| Action | Pollution Reduction Strategy & Action Plan | What realistic interventions should be considered? |

This structure prevents the dashboard from becoming a collection of disconnected charts and instead creates a progression from measurement to decision support.

---

## Tools and Technologies

### Data Analysis

- Python
- Pandas
- NumPy
- Jupyter Notebook

### Data Visualization and Business Intelligence

- Microsoft Power BI
- Power Query
- DAX

### Data Management

- CSV
- Git
- GitHub
- Git Large File Storage (Git LFS)

---

## Repository Structure

```text
india-air-pollution-analysis/
│
├── Data/
│   ├── Cleaned_data/
│   │   └── preprocessed_data.csv
│   │
│   └── raw/
│       └── archive (1).zip
│
├── Milestones/
│   ├── Milestone 1.docx
│   ├── Milestone 2.pptx
│   ├── Milestone 3.pdf.pptx
│   └── Milestone 4.pptx
│
├── Notebook/
│   └── india-air-quality-data.ipynb
│
├── PowerBi/
│   └── AirPollution.pbix
│
├── .gitattributes
└── README.md
```

The processed dataset is stored using **Git LFS** because of its file size.

---

## Project Workflow

```text
Raw Dataset
     |
     v
Data Inspection
     |
     v
Data Cleaning & Validation
     |
     v
Feature Engineering
     |
     v
Exploratory Data Analysis
     |
     v
Power BI Modeling
     |
     v
Six-Dashboard Narrative
     |
     v
Evidence Assessment
     |
     v
Intervention Prioritization
```

---

## Project Outcome

The project demonstrates how a large historical environmental dataset can be transformed into an analytical decision-support solution.

Rather than focusing only on pollution rankings, the project combines:

- Pollution intensity
- Geographic concentration
- Monitoring context
- Historical patterns
- Data completeness
- Evidence strength
- Intervention prioritization

The result is an environmental risk intelligence framework that moves from **measurement to interpretation and then toward action**, while maintaining clear analytical guardrails around data limitations and causal claims.

---

## Skills Demonstrated

- Data Cleaning and Preprocessing
- Exploratory Data Analysis
- Missing-Value Treatment
- Data Validation
- Outlier Analysis
- Feature Engineering
- Statistical Analysis
- SQL/Data Analytics concepts
- Power BI Dashboard Development
- Power Query
- DAX
- Interactive Data Visualization
- Data Storytelling
- Business/Decision Intelligence
- Evidence-Based Analysis
- Git and GitHub
- Git LFS

---

## Project Documentation

The repository contains milestone documentation covering the development and analytical progression of the project.

The Power BI workbook contains the complete interactive dashboard implementation, while the Jupyter Notebook documents the Python-based data preparation and analytical workflow.

---

## Team

**Team 3**

- **Rushikesh Shirwalkar**
- **Ajay Seepana**
- **Rakesh Bommala**


---

## Project Status

**Completed**

The project includes:

- Data preparation and validation
- Processed analytical dataset
- Exploratory analysis
- Power BI dashboard development
- Six-dashboard analytical narrative
- Evidence-strength assessment
- Intervention framework
- Milestone documentation

