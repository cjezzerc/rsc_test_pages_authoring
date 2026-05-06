# BMI Categorisation

## Brief description

Categorisation of BMI at a specified date using either categorical BMI codes or numeric BMI observations.

## Overview

This phenotype assigns BMI category at a specified date using the most recent eligible BMI-related record between the start of the observation period and the specified date. It integrates two recording modalities in routine care data: categorical BMI status codes and coded numeric BMI observations. The selected record is mapped to harmonised BMI bands (<20, 20 to <25, 25 to <30, 30 to <40, >=40), with UNKNOWN returned when no qualifying record exists. Applied across populations, the phenotype supports descriptive epidemiology, cohort construction, and derivation of patient-level variables for downstream analysis.

## Input

| Parameter                 | Description/Value/Identifier                            |
|---------------------------|----------------------------------------------|
| `patient_record`          | A single patient's longitudinal record (_provided at execution time_) |
| `status_date`             | Date at which BMI category is to be determined (_specified at runtime_) |
| `start_observation_period`| Earliest date at which observations are still to be considered relevant |
| `bmi_lt20_codelist`       | RSC-C???? |
| `bmi_20_24.9_codelist`    | RSC-C1502 |
| `bmi_25_29.9_codelist`    | RSC-C1504 |
| `bmi_30_39.9_codelist`    | RSC-C1503 |
| `bmi_ge40_codelist`       | RSC-C1505 |
| `bmi_obs_entity_codelist` | RSC-C5022 |

## Output

* **Type:** attribute
* **Description:**
  BMI category at the specified date (BMI_LT20 / BMI_20_24_9 / BMI_25_29_9 / BMI_30_39_9 / BMI_GE40 / UNKNOWN).

## Pseudocode

A composite codelist `all_bmi_status_codelist` is defined as the union of:

* `bmi_lt20_codelist`
* `bmi_20_24.9_codelist`
* `bmi_25_29.9_codelist`
* `bmi_30_39.9_codelist`
* `bmi_ge40_codelist`
* `bmi_obs_entity_codelist`

* Let `most_recent_bmi` be the most recent event in `patient_record` with a code from `all_bmi_status_codelist` and an observation date in the inclusive interval `start_observation_period` to `status_date`.

* If no such event exists:

  * Return **UNKNOWN**

* Otherwise, if the event code is in `bmi_obs_entity_codelist`:

  * Let `bmi_value` be the numeric value associated with the event
  * If `bmi_value < 20` -> return **BMI_LT20**
  * If `20 <= bmi_value < 25` -> return **BMI_20_24_9**
  * If `25 <= bmi_value < 30` -> return **BMI_25_29_9**
  * If `30 <= bmi_value < 40` -> return **BMI_30_39_9**
  * If `bmi_value >= 40` -> return **BMI_GE40**

* Otherwise,

  * If the event code is in `bmi_lt20_codelist` -> return **BMI_LT20**
  * If the event code is in `bmi_20_24.9_codelist` -> return **BMI_20_24_9**
  * If the event code is in `bmi_25_29.9_codelist` -> return **BMI_25_29_9**
  * If the event code is in `bmi_30_39.9_codelist` -> return **BMI_30_39_9**
  * If the event code is in `bmi_ge40_codelist` -> return **BMI_GE40**

## Notes on use

* Applying this phenotype across a collection of patients can produce:
  * BMI category distributions
  * cohorts (for example, BMI_GE40)
  * patient-level variables (for example, patient is severly obese)
