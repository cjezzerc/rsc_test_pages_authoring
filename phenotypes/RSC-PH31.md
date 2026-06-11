# Prescription or administration of drug/vaccine [T]

## Brief description

Template phenotype for identifying  prescription or administration events for a specifield drug or vaccine 

## Overview

This template phenotype identifies prescription or administration events for a specified drug or vaccine from longitudinal primary care records using a SNOMED CT codelist. The administration of a vaccine may be identified with either a code recording the administering of the vaccine or an entry in the prescription table for the vaccine itself. The phenotype returns a list of events per patient. Applied across populations, it supports estimation of prescribing rates or vaccine coverage, cohort construction, and derivation of a patient-level variable for downstream analysis.
It is possible to filter the results so that the recording of two (or more) events on one day only counts as one prescription event. With this filtering, the recording of, for instance, a vaccine prescription and its administration on the same day only counts as one vaccination event. Filtering is achieved by setting same_day_filter=True

## Input

| Parameter            | Description                                                                                        |
|----------------------|----------------------------------------------------------------------------------------------------|
| `patient_record`     | A single patient's longitudinal record                                                             |
| `observation_window` | Timeframe within which events are to be identified                                                 |
| `drug_issue_codelist`      | SNOMED CT codes identifying prescription or administration events for the specific drug or vaccine |
| same_day_filter      | If true then events on the same day are treated as one event (default=False)                       |

## Output

* **Description:**
  A list of prescription or administration events including the date for the specified drug or vaccine within the observation window.

## Pseudocode

* Let `candidate_events` be all events in `patient_record` with codes from `drug_issue_codelist` within `observation_window`.
* For each event in `candidate_events`:
  * The event is considered to define a separate event if:
    * same_day_filter is false, or there are no prior events from `drug_issue_codelist` on the same day as the event.
* Return the list of all such events.

## Notes on use

* Applying this phenotype across a collection of patients can produce:
  * counts of prescriptions or vaccinations
  * patient-level variables (for example, patient has been prescribed the specified drug at least once)
  * cohorts (for example, all patients with at least one prescription for the specified drug)

## Template note

Section will be removed

## Data Visualisation Flavour

Template
