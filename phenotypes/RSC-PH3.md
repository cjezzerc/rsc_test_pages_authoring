
# (aaa) Smoking Status

## Brief description

Determination of smoking status at a specified date.

## Overview

This phenotype determines the smoking status of an individual patient based on their most recent recorded observation.

## Input

- Patient longitudinal record
- `status_date`

## Output

- **Type:** attribute
- **Description:**
  Smoking status at the specified date (SMOKER / EX-SMOKER / NON-SMOKER / UNKNOWN).

## Parameters

| Parameter | Description |
|---|---|
| `status_date` | Date at which status is determined |

## Codelists

| Name in algorithm | RSC Codelist |
|---|---|
| `active_smoker_codelist` | RSC-C2065 |
| `ex_smoker_codelist` | RSC-C2066 |
| `non_smoker_codelist` | RSC-C2067 |

A composite codelist `all_smoker_status_codelist` is defined as the union of `active_smoker_codelist`, `ex_smoker_codelist` and `non_smoker_codelist`.

## Pseudocode

For a given patient:

* Let `most_recent_status` be the most recent event with a code from `all_smoker_status_codelist` on or before `status_date`.

* If such an event exists:

  * If the code is in `active_smoker_codelist` -> return **SMOKER**
  * If the code is in `ex_smoker_codelist` -> return **EX-SMOKER**
  * If the code is in `non_smoker_codelist` -> return **NON-SMOKER**

* Otherwise:

  * Return **UNKNOWN**

## Notes on use

- Applying across patients yields:
  - distributions of smoking status
  - cohorts (for example, current smokers)
  - covariates for analysis
