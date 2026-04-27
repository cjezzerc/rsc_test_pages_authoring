# Condition status [T]

## Brief description

Template phenotype for identifying the status of subject for a specified condition at a certain date

## Overview

This phenotype determines the status of an individual patient at a particular date based on their most recent relevant recorded observation up to that date. 

## Input

| Parameter                | Description                                                                                  |
|--------------------------|---------------------------------------------------------------------------------------------------|
| `patient_record`     | A single patient's longitudinal record                                                                |
| `status_date` | Date at which the status is to be determined                                                                 |
| `positive_codelist` | SNOMED CT codes indicating presence of the specific condition                                          |
| `negative_codelist` | SNOMED CT codes indicating absence (including recovery from) the specific condition (_optional_)       |


## Output

* **Type:** state
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

* Applying this phenotype across a collection of patients can produce:
  * case counts (prevalence)
  * patient-level variables (patient does or does not have the condition)
  * cohorts (all patients with the condition)
  
  
## Template note

Section will be removed

