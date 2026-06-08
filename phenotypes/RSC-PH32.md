# Measurements [T]

## Brief description

Template phenotype for identifying measurement events for a specified quantity

## Overview

This template phenotype identifies measurement events for a specified quantity from longitudinal primary care records using a SNOMED CT codelist.  The phenotype returns a list of events per patient. Applied across populations, it supports estimation of monitoring rates, cohort construction, and derivation of patient-level variables for downstream analysis.

## Input

| Parameter              | Description                                                                                        |
|------------------------|----------------------------------------------------------------------------------------------------|
| `patient_record`       | A single patient's longitudinal record                                                             |
| `observation_window`   | Timeframe within which events are to be identified                                                 |
| `measurement_codelist` | SNOMED CT codes identifying measurement of the specific quantity |

## Output

* **Type:** events
* **Description:**
  A list of measurement events **WHAT IS RETURNED?DATE?INITIATING EVENT?** for the specified quantity within the observation window.

## Pseudocode

* Let `candidate_events` be all events in `patient_record` with codes from `measurement_codelist` within `observation_window`.
* Return the list of all events including the associated recorded value.

## Notes on use

* Applying this phenotype across a collection of patients can produce:
  * counts of subjects for whom measurements have been made
  * patient-level variables (for example, patient has had the quantity measured at least once)
  * cohorts (for example, all patients with at least one measurement of the specified quantity)

## Template note

Section will be removed

## Data Visualisation Flavour

Template
