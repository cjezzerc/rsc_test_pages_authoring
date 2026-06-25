# BMI Categorisation

## Brief description

Categorisation of body mass index (BMI) at a specified date using either categorical BMI codes or numeric BMI observations.

## Overview

This phenotype assigns BMI category at a specified date using the most recent eligible BMI-related record between the start of the observation period and the specified date. It integrates two recording modalities in routine care data: categorical BMI status codes and coded numeric BMI observations. The selected record is mapped to BMI bands of BMI_UNDERWEIGHT, BMI_NORMAL, BMI_OVERWEIGHT, BMI_OBESE and BMI_SEVERELY_OBESE , with UNKNOWN returned when no qualifying record exists. Applied across populations, the phenotype supports descriptive epidemiology, cohort construction, and derivation of a patient-level variable for downstream analysis.

## Input

| Parameter                 | Description                                                             | Value                          |
|---------------------------|-------------------------------------------------------------------------|--------------------------------|
| `patient_record`          | A single patient's longitudinal record                                  | _To be specified on execution_  |
| `status_date`             | Date at which BMI category is to be determined                          | _To be specified on execution_ |
| `start_observation_period`| Earliest date at which observations are still to be considered relevant | _To be specified on execution_ |
| `bmi_lt20_codelist`       | SNOMED CT codes indicating that the BMI is less than 20                 | RSC-C????                      |
| `bmi_20_24.9_codelist`    | SNOMED CT codes indicating that the BMI is in the range 20-24.9         | RSC-C1502                      |
| `bmi_25_29.9_codelist`    | SNOMED CT codes indicating that the BMI is in the range 25-29.9         | RSC-C1504                      |
| `bmi_30_39.9_codelist`    | SNOMED CT codes indicating that the BMI is in the range 30-39.9         | RSC-C1503                      |
| `bmi_ge40_codelist`       | SNOMED CT codes indicating that the BMI is greater than 40              | RSC-C1505                      |
| `bmi_obs_entity_codelist` | SNOMED CT codes indicating that a value has been recorded for BMI       | RSC-C5022                      |

## Output

* **Description:**
  BMI category at the specified date (BMI_LT20 / BMI_20_24_9 / BMI_25_29_9 / BMI_30_39_9 / BMI_GE40 / UNKNOWN).

## Pseudocode

* It is assumed that all BMI values are recorded (or categorised) rounded to one decimal place

* A composite codelist `all_bmi_status_codelist` is defined as the union of:

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
  * If `bmi_value < 18.5` -> return **BMI_UNDERWEIGHT**
  * If `18.5 <= bmi_value < 25` -> return **BMI_NORMAL**
  * If `25 <= bmi_value < 30` -> return **BMI_OVERWEIGHT**
  * If `30 <= bmi_value < 40` -> return **BMI_OBESE**
  * If `bmi_value >= 40` -> return **BMI_SEVERELY_OBESE**

* Otherwise,

  * If the event code is in `bmi_lt20_codelist` -> return **BMI_UNDERWEIGHT**
  * If the event code is in `bmi_20_24.9_codelist` -> return **BMI_NORMAL**
  * If the event code is in `bmi_25_29.9_codelist` -> return **BMI_OVERWEIGHT**
  * If the event code is in `bmi_30_39.9_codelist` -> return **BMI_OBESE**
  * If the event code is in `bmi_ge40_codelist` -> return **BMI_SEVERELY_OBESE**

## Notes on use

* Applying this phenotype across a collection of patients can produce:
  * BMI category distributions
  * cohorts (for example, BMI_GE40)
  * patient-level variables (for example, patient is severly obese)

* There is a small unavoidable inconsistency, in that the lower limit on BMI_NORMAL is 20 when using categorical codes, and 18.5 when using numerical values. This is due to the available BMI categorical codes in SNOMED not precisely aligning with the current NICE guidelines. The effect should be small as in practice the majority of recorded values are numerical, and categorical codes tend to be used in rarer circumstances where an estimate is made rather than a direct measurement. 

## Data Visualisation Flavour

Categorisation
