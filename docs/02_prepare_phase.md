# Phase 2: Prepare
## Understanding Data Sources and Structure

---

## Objective

The purpose of the Prepare phase is to understand the structure, content, and limitations of the FDA FAERS dataset and to determine how it can be used to answer the analytical questions defined in Phase 1.

This phase focuses on data sourcing, file relationships, key variables, and data quality considerations before any cleaning or transformation begins.

---

## Data Source Overview

Source: FDA Adverse Event Reporting System (FAERS)  
Release: Quarterly Data Extract (QDE)  
Time Period: April 1 – June 30, 2025 (Q2 2025)  
Format: ASCII text files (dollar-sign delimited)  
Access: Publicly available FDA dataset  

The FAERS database contains spontaneous adverse event reports submitted by healthcare professionals, manufacturers, and consumers related to drugs and dietary supplements. Submission of a report indicates a reported association and does not establish causality.

---

## Dataset Structure

The Q2 2025 FAERS release consists of seven relational files linked using a common case identifier: PRIMARYID.

File Name | Description | Primary Purpose | Approximate Size
DEMO | Patient demographics and administrative data | Demographic patterns | ~500K records
DRUG | Drug and supplement product details | Identify reported supplements | ~99.5 MB
REAC | Adverse reactions (MedDRA coded) | Reaction frequency | Large
OUTC | Patient outcomes | Severity indicators | Variable
INDI | Indications for product use | Usage context | ~40 MB
RPSR | Report source | Reporting context | Small
THER | Therapy start and end dates | Temporal relationship | ~13.8 MB

PRIMARYID is the unique identifier linking all related records. A single PRIMARYID may correspond to multiple drugs, reactions, outcomes, and indications.

---

## Scope Definition

Included in Scope:
- Reports involving dietary supplements and herbal products
- FAERS reports from Q2 2025 only
- Products listed as Primary Suspect (ROLE_COD = "PS")
- Records with a valid PRIMARYID

Excluded from Scope:
- Prescription drugs are not classified as dietary supplements
- Reports outside the Q2 2025 time window
- Records with missing or invalid PRIMARYID
- Secondary suspect, concomitant, or interacting drugs unless explicitly noted

---

## Key Variables of Interest

Variable | File | Purpose | Notes
PRIMARYID | All | Join key linking all files | Unique case identifier
DRUGNAME | DRUG | Identify supplements | Requires name standardization
ROLE_COD | DRUG | Filter for primary suspect products | PS = Primary Suspect
PT | REAC | Reaction frequency analysis | MedDRA standardized coding
OUTC_COD | OUTC | Severity assessment | HO = Hospitalization
AGE | DEMO | Demographic analysis | Requires unit normalization
AGE_UNIT | DEMO | Age unit | YR = years, DY = days
SEX | DEMO | Gender distribution | M/F codes
EVENT_DT | DEMO | Event timing | Adverse event date

These variables directly support the analytical questions defined in Phase 1.

---

## Mapping Data to Analytical Questions

Question | Required Files | Key Fields | Join Method
Q1: Most frequently reported supplements | DRUG, DEMO | DRUGNAME, PRIMARYID, ROLE_COD | Join via PRIMARYID; filter PS
Q2: Most common adverse reactions | REAC, DEMO | PT, PRIMARYID | Join via PRIMARYID; count PT
Q3: Demographic patterns | DEMO | AGE, SEX, PRIMARYID | Aggregate by age and sex
Q4: Hospitalization rate | OUTC, DRUG, DEMO | OUTC_COD, DRUGNAME | Join via PRIMARYID; filter HO
Q5: Monitoring priorities | All files | Frequency and severity metrics | Combine Q1–Q4 outputs

---

## Data Quality Considerations

Known Limitations:
- Reporting is voluntary and subject to reporting bias
- Not all fields are populated for every record
- Duplicate submissions may exist for the same event
- Supplement names are inconsistently reported
- Some demographic and outcome fields contain missing values
- Accuracy depends on reporter type and completeness of submission

Validation Approach:
- Assess completeness of critical fields
- Identify and manage duplicate PRIMARYID entries
- Standardize supplement names during processing
- Document exclusions and data quality issues

---

## Key Assumptions

- All seven files are complete and unmodified from the FDA source
- PRIMARYID functions as a reliable join key for case-level analysis
- MedDRA coding is consistently applied across reports
- Data is sufficiently de-identified to protect patient privacy
- Reported associations reflect genuine observations, with known limitations

---

## Data Organization Plan

- Raw data stored in data/raw/ without modification
- Processed datasets stored in data/processed/
- Analytical work stored in analysis/ (Excel workbooks and outputs)
- No transformations performed during the Prepare phase
- All processing decisions are documented in subsequent phases

---

## Deliverables of the Prepare Phase

- Clear understanding of FAERS data structure and relationships
- Identification of relevant files and variables per analytical question
- Defined scope and inclusion criteria
- Documented data quality considerations and assumptions
- Readiness to proceed to the Process phase

---

Phase Status: Complete  
Next Phase: Process
