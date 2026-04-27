
# (aaa) Smoking Status

## Brief description

Determination of smoking status at a specified date.

## Overview

This phenotype determines the smoking status of an individual patient at a particular date based on their most recent recorded observation up to that date.

## Input

| Parameter                 | Description/Value/Identifer                            |
|---------------------------|----------------------------------------------|
| `patient_record`     | A single patient's longitudinal record (_provided at execution time_)       
| `status_date`             | Date at which the status is to be determined (_specified at runtime_) |
| `active_smoker_codelist`  | RSC-C2065                                    |
| `ex_smoker_codelist`      | RSC-C2066                                    |
| `non_smoker_codelist`     | RSC-C2067                                    |

## Output

* **Type:** attribute
* **Description:**
  Smoking status at the specified date (SMOKER / EX-SMOKER / NON-SMOKER / UNKNOWN).

## Pseudocode

A composite codelist `all_smoker_status_codelist` is defined as the union of `active_smoker_codelist`, `ex_smoker_codelist` and `non_smoker_codelist`.


* Let `most_recent_status` be the most recent event in `patient_record` with a code from `all_smoker_status_codelist` on or before `status_date`.

* If such an event exists:

  * If the code is in `active_smoker_codelist` -> return **SMOKER**
  * If the code is in `ex_smoker_codelist` -> return **EX-SMOKER**
  * If the code is in `non_smoker_codelist` -> return **NON-SMOKER**

* Otherwise:

  * Return **UNKNOWN**

## Notes on use

* Applying this phenotype across a collection of patients can produce:
  * distributions of smoking status
  * cohorts (for example, current smokers)
  * patient-level variables (for example, patient is a smoker)
