# Analysis

This folder documents the analytical steps, calculations, 
and logic used to answer the project questions.

## Excel Dashboard File
The full Excel workbook is available as a GitHub Release:
[Download Excel Dashboard](https://github.com/morshediem-mm/fda-supplement-adverse-events-analysis/releases)
## Analytical Steps Performed

### Step 1 — Data Import
Imported raw FDA FAERS Q2 2025 ASCII files into Excel
using the Text Import Wizard with $ delimiter

### Step 2 — Data Cleaning
- Removed duplicate records
- Standardized drug name formatting
- Handled missing values across all 4 tables

### Step 3 — Data Merging
Merged DEMO, DRUG, REAC, and OUTC tables using
PRIMARYID as the common key via Power Query

### Step 4 — PivotTable Analysis
Built 4 PivotTables:
- Top 20 Adverse Reactions by report count
- Top 20 Drugs by report count  
- Serious Outcomes distribution
- Adverse Reactions by Drug

### Step 5 — Key Calculations
- Serious % = Serious outcomes / Total reports = 44%
- Fatigue % = 13,908 / 393,131 = 3.5% of all reports
- Hospitalization count = 81,419 cases

### Step 6 — Dashboard
Built an interactive Excel dashboard with 2 slicers
connecting PivotCharts for dynamic filtering
