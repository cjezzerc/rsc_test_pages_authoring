
# Smoking Status

## Brief description

Determination of smoking status at a specified date.

## Overview

This phenotype determines smoking status at a specified date using the most recent smoking-related event recorded on or before that date. It applies curated SNOMED CT codelists representing current smoker, ex-smoker, and non-smoker states, and maps the latest qualifying code to a harmonised status category (SMOKER, EX-SMOKER, NON-SMOKER). Where no qualifying smoking-status record is available, status is UNKNOWN.

## Input

| Parameter                 | Description                                  |  Value                          |
|---------------------------|----------------------------------------------|---------------------------------|
| `patient_record`          | A single patient's longitudinal record       | _To be provided on execution_   |
| `status_date`             | Date at which the status is to be determined | _To be specified on execution_  |
| `start_date`              | Earliest date from which to search           | _To be specified on execution_  |
| `active_smoker_codelist`  | SNOMED CT codes identifying active smokers   | RSC-C2065                       |
| `ex_smoker_codelist`      | SNOMED CT codes identifying ex-smokers       | RSC-C2066                       | 
| `non_smoker_codelist`     | SNOMED CT codes identifying ex-smokers       | RSC-C2067                       |

## Output

* **Description:**
  Smoking status at the specified date (SMOKER / EX-SMOKER / NON-SMOKER / UNKNOWN).

## Pseudocode

* A composite codelist `all_smoker_status_codelist` is defined as the union of `active_smoker_codelist`, `ex_smoker_codelist` and `non_smoker_codelist`.

* Let `observation_window` be the period from `start_date` to `status_date` (inclusive)

* Let `most_recent_event` be the most recent event in `patient_record` within the `observation_window` with a code from `all_smoker_status_codelist`.

* If such an event exists:

  * If the code is in `active_smoker_codelist` -> return **SMOKER**
  * If the code is in `ex_smoker_codelist` -> return **EX-SMOKER**
  * If the code is in `non_smoker_codelist` -> return **NON-SMOKER**

* Otherwise:

  * Return **UNKNOWN**

## Notes on use

* Applying this phenotype to primary care records can produce:
  * distributions of smoking status
  * cohorts (for example, current smokers)
  * patient-level variables (for example, patient is a smoker)

## Data Visualisation Flavour

Categorisation
