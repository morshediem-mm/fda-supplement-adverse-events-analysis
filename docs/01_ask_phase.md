# Phase 1: Ask

## Problem Statement
Adverse events associated with pharmaceutical drugs and biologics 
represent a significant patient safety concern. Healthcare professionals, 
regulators, and patients rely on systematic reporting to identify safety 
signals and monitor drug performance post-market.

This project examines FDA Adverse Event Reporting System (FAERS) data 
for Q2 2025 to identify reporting patterns associated with pharmaceutical 
products, including frequency of adverse reactions and indicators of 
severity such as hospitalization, death, and disability.

The analysis focuses on reported associations rather than clinical 
causation and aims to surface products and reactions that may warrant 
closer post-market safety monitoring.

---

## Project Objectives
The objective of this analysis is to use FDA FAERS Q2 2025 data to:

- Identify pharmaceutical drugs most frequently associated with 
  adverse event reports
- Determine the most commonly reported adverse reactions
- Evaluate serious outcome indicators including hospitalization, 
  death, life-threatening events, and disability
- Analyze the distribution of serious vs non-serious outcomes
- Support data-driven recommendations for post-market safety monitoring

---

## Scope of Analysis

- **Data Source**: FDA FAERS Quarterly Data Extract (ASCII format)
- **Time Period**: April 1 – June 30, 2025 (Q2 2025)
- **Product Focus**: Pharmaceutical drugs and biologics
- **Analysis Level**: Aggregate reporting patterns and severity indicators
- **Tools**: Microsoft Excel, Power Query, PivotTables

---

## Key Analytical Questions

1. Which pharmaceutical drugs are most frequently associated with 
   adverse event reports in Q2 2025?
2. What adverse reactions are reported most often across all products?
3. What proportion of reported events resulted in serious outcomes 
   such as hospitalization or death?
4. Which drugs show the highest concentration of specific reaction types?
5. Which products demonstrate patterns that may warrant increased 
   post-market safety monitoring?

---

## Stakeholders

- FDA regulatory and pharmacovigilance teams
- Healthcare professionals and clinicians
- Pharmaceutical manufacturers
- Patients and consumer advocacy groups
- Healthcare data analysts reviewing safety trends

---

## Key Findings Preview

| Metric | Value |
|--------|-------|
| Total Reports Analyzed | 393,131 |
| Top Reported Drug | INFLECTRA (30,160 reports) |
| Most Common Reaction | Fatigue (3.5% of all reports) |
| Serious Outcome Rate | 44% |
| Leading Serious Outcome | Hospitalization (81,419 cases) |

---

## Assumptions and Limitations

- FAERS data reflects **reported associations**, not confirmed causation
- Reports may include incomplete, duplicate, or biased submissions
- Adverse events may be influenced by concurrent medications or 
  underlying conditions
- A single case may involve multiple drugs and multiple reactions
- Findings are intended to identify trends, not establish 
  clinical conclusions

---

**Phase Status:** Complete
**Next Phase:** Prepare
