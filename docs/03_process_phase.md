# Phase 3: Process
## Data Cleaning, Filtering, and Integration

---

## Objective

The purpose of the Process phase is to clean, validate, filter, and integrate the FDA FAERS Q2 2025 data to ensure it is accurate, consistent, and ready for analysis.

This phase focuses on preparing reliable analytical datasets without altering the original raw data.

---

## Data Processing Environment

- Tool Used: Microsoft Excel (Mac) with Power Query
- Data Format: ASCII text files (dollar-sign delimited)
- Raw Data Location: data/raw/
- Processed Data Location: data/processed/

Power Query was used to handle large files, apply transformations consistently, and document each processing step.

---

## Files Processed

The following FAERS Q2 2025 files were processed:

- DEMO25Q2.txt (Demographics)
- DRUG25Q2.txt (Drug and supplement information)
- REAC25Q2.txt (Adverse reactions)
- OUTC25Q2.txt (Patient outcomes)

Other files (INDI, RPSR, THER) remain available for future expansion but were not required for the primary analytical questions.

---

## Step 1: Import Raw Data

- Imported ASCII text files into Excel using Power Query
- Set delimiter to `$` (dollar sign)
- Verified correct column alignment using FAERS documentation (ASC_NTS)
- Confirmed PRIMARYID presence in all imported files
- Loaded DEMO as a reference table
- Loaded DRUG, REAC, and OUTC as transformed queries

Raw data files were not modified or overwritten.

---

## Step 2: Filter for Relevant Records

### DRUG File Filtering
- Filtered ROLE_COD to include only:
  - PS (Primary Suspect)
- Excluded:
  - SS (Secondary Suspect)
  - C (Concomitant)
  - I (Interacting)

This ensures analysis focuses only on supplements identified as the primary suspected cause of the adverse event.

---

## Step 3: Standardize and Validate Key Fields

### Supplement Name Cleaning (DRUGNAME)
- Converted text to uppercase
- Trimmed leading and trailing spaces
- Removed obvious formatting inconsistencies
- Identified naming variations for the same product

Full name normalization is documented but not aggressively merged to preserve reporting transparency.

---

## Step 4: Validate Identifiers

- Verified PRIMARYID consistency across DEMO, DRUG, REAC, and OUTC
- Checked for null or invalid PRIMARYID values
- Retained only records with a valid PRIMARYID

PRIMARYID was used as the sole join key across datasets.

---

## Step 5: Join Datasets

Using Power Query:

- DRUG joined to DEMO on PRIMARYID (inner join)
- REAC joined the DRUG-DEMO dataset on PRIMARYID (left join)
- OUTC joined on PRIMARYID to capture severity indicators

This structure allows:
- Multiple reactions per supplement
- Multiple outcomes per case
- One-to-many relationships without duplication errors

---

## Step 6: Handle Missing and Duplicate Data

### Missing Values
- Records with missing AGE or SEX were retained for overall counts
- Demographic analysis excludes records with missing demographic fields
- OUTC records are optional and analyzed only when present

### Duplicate Records
- Duplicate PRIMARYID rows retained where they represent valid multiple reactions or outcomes
- No artificial de-duplication applied beyond FAERS versioning

All exclusions and inclusions are documented.

---

## Step 7: Create Processed Outputs

The following datasets were generated:

- demo_cleaned.csv  
  Cleaned demographic data with validated identifiers

- drug_cleaned.csv  
  Filtered primary suspect supplements with standardized names

- reac_cleaned.csv  
  Reaction-level data linked to supplements

- merged_analysis.csv  
  Integrated dataset combining demographics, supplements, reactions, and outcomes

These files serve as the foundation for analytical calculations and visualization.

---

## Data Integrity Checks

- Row counts verified before and after joins
- Spot checks performed on randomly selected PRIMARYID values
- Aggregated counts validated against raw totals
- Transformation steps reviewed for reproducibility

No raw data was deleted or overwritten during processing.

---

## Output of Process Phase

After the Process phase:

- Data is clean, structured, and analysis-ready
- All datasets are consistently linked via PRIMARYID
- Supplement records are limited to primary suspects
- Known data limitations are preserved and documented
- A reliable foundation exists for analytical insights

---

Phase Status: Complete  
Next Phase: Analyze
