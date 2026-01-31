# FDA Supplement Adverse Events Analysis

## Project Overview

This project presents a large-scale healthcare data analysis of dietary supplement and herbal product adverse events using the FDA Adverse Event Reporting System (FAERS) database for April–June 2025 (Q2 2025).

The analysis focuses on identifying high-risk supplements, understanding side effect patterns, evaluating severity outcomes, and generating actionable safety insights using structured analytics methodology and Excel Power Query.

Data Period: April 1 – June 30, 2025
Focus: Dietary supplements and herbal products
Data Source: FDA FAERS Quarterly Data Extract (ASCII format)
Project Status: In Progress

---

## Objectives

1. Identify the top 10 dietary and herbal supplements with the highest number of adverse event reports
2. Determine the most frequently reported side effects
3. Analyze demographic patterns among reported adverse events
4. Calculate severity metrics, including hospitalization rates
5. Generate actionable recommendations for supplement safety monitoring

---

## Project Structure

```
fda-supplement-adverse-events-analysis/
│
├── README.md
├── SCOPE_OF_WORK.md
│
├── docs/
│   ├── 01_ask_phase.md
│   ├── 02_prepare_phase.md
│   ├── 03_process_phase.md
│   ├── 04_analyze_phase.md
│   ├── 05_share_phase.md
│   └── 06_act_phase.md
│
├── data/
│   ├── raw/
│   └── processed/
│
├── analysis/
│
└── visualizations/
```

---

## Understanding the Data

### FDA FAERS

The FDA Adverse Event Reporting System (FAERS) is a national database that contains adverse event and medication error reports submitted by healthcare professionals, pharmaceutical manufacturers, and consumers.

### Important Disclaimer

FAERS data represent reported associations and do not establish causation.

* Submission of a report does not confirm that the supplement caused the adverse event.
* Events may be related to underlying disease, concurrent medications, or chance.
* The analysis identifies reporting patterns and trends, not clinical causality.

---

## Data Structure

The FAERS Q2 2025 dataset consists of seven relational files linked using a common identifier.

| File | Description                 | Key       |
| ---- | --------------------------- | --------- |
| DEMO | Patient demographics        | PRIMARYID |
| DRUG | Supplement and drug details | PRIMARYID |
| REAC | Adverse reactions           | PRIMARYID |
| OUTC | Patient outcomes            | PRIMARYID |
| INDI | Indications                 | PRIMARYID |
| RPSR | Report source               | PRIMARYID |
| THER | Therapy start/end dates     | PRIMARYID |

PRIMARYID is the unique identifier linking all datasets.

---

## Methodology

This project follows a structured six-phase analytics framework:

1. Ask – Define business objectives, stakeholders, and analytical questions
2. Prepare – Understand data sources, structure, and quality considerations
3. Process – Clean, validate, filter, and merge datasets
4. Analyze – Perform statistical analysis and identify trends
5. Share – Create visualizations and communicate insights
6. Act – Develop recommendations and next-step strategies

---

## Tools and Technologies

* Microsoft Excel Power Query
* Excel Pivot Tables and Charts
* Healthcare data analytics techniques
* GitHub for documentation and version control

---

## Key Analytical Steps

* Filtered FDA FAERS datasets for primary suspect products
* Standardized supplement naming
* Cleaned missing and inconsistent values
* Merged multiple tables using PRIMARYID
* Aggregated adverse event counts by supplement
* Evaluated demographic and severity trends

---

## Preliminary Findings (Preview)

| Supplement | Adverse Event Reports |
| ---------- | --------------------- |
| DUPIXENT   | 35,357                |
| MOUNJARO   | 7,422                 |
| ZEPBOUND   | 7,358                 |
| CIMZIA     | 5,702                 |
| SKYRIZI    | 5,308                 |

These early results highlight products requiring enhanced post-market safety monitoring.

---

## Analytical Questions Addressed

1. Which dietary and herbal supplements had the highest adverse event reporting frequency?
2. What side effects were reported most frequently?
3. Which age groups experienced the most reported adverse events?
4. What percentage of cases resulted in hospitalization?
5. Which supplements warrant increased regulatory monitoring?

---

## Data Privacy and Compliance

* All FDA FAERS data is publicly available and de-identified.
* No personal patient identifiers are included.
* Analytical methods and transformations are fully documented.

---

## Author

Ellie
Healthcare Data Analyst
GitHub: httpshttps://github.com/morshediem-mm

---

## Disclaimer

This project is for educational and analytical portfolio purposes only.

FAERS data reflect reported associations and do not establish medical causation.
Healthcare decisions should always be guided by licensed medical professionals.

---

Last Updated: January 2026

---


