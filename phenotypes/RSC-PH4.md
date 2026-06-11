# Binary condition status [T]

## Brief description

Template phenotype for identifying the status of subject for a specified condition at a certain date

## Overview

This template phenotype identifies cases of a chronic condition at a specified date in the primary care record using curated SNOMED CT codelists for positive evidence of the condition and, where available, negative evidence such as resolution or explicit absence. Status is assigned from the latest qualifying code (positive = 1, negative = 0), with a default of 0 when no qualifying event exists. Applied across populations, the phenotype supports prevalence estimation, cohort construction, and derivation of a patient-level variable for downstream analysis.

## Input

| Parameter                | Description                                                                                  |
|--------------------------|---------------------------------------------------------------------------------------------------|
| `patient_record`     | A single patient's longitudinal record                                                                |
| `status_date` | Date at which the status is to be determined                                                                 |
| `positive_codelist` | SNOMED CT codes identifying diagnosis events for the specific condition                                          |
| `negative_codelist` | SNOMED CT codes indicating absence (including recovery from or remission of) the specific condition (_optional_)       |


## Output

* **Description:**
  Status for specified condition at the specified date (1 = has the condition, 0 = does not have the condition).

## Pseudocode

* A composite codelist `composite_codelist` is defined as the union of `positive_codelist`, and `negative_codelist`.


* Let `most_recent_status` be the most recent event in `patient_record` with a code from `composite_codelist` on or before `status_date`.

* If such an event exists:

  * If the code is in `positive_codelist` -> return 1
  * If the code is in `negative_codelist` -> return 0

* Otherwise:

  * Return 0

## Notes on use

* Applying this phenotype to primary care records can produce:
  * case counts and prevalence
  * patient-level variables (patient does or does not have the condition)
  * cohorts (all patients with the condition)
  
  
## Template note

Section will be removed


## Data Visualisation Flavour

Template
