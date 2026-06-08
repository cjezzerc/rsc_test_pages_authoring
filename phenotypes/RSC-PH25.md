# Amoxicillin Prescribed

## Brief description

Identification of amoxicillin prescribing events.

## Overview

This phenotype identifies prescribing events for amoxicillin in primary care records using a curated medication codelist. Within the specified observation window, a qualifying event is counted as a new event only if no prior qualifying event occurred in the preceding 0 days (that is, no de-duplication interval is applied). Applied across populations, the phenotype supports prescribing surveillance, cohort construction, and derivation of patient-level variables for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | RSC-C5129                               |
| `interval`           | 0 days                                  |


## Pseudocode

See template

## Notes on use

See template

## Condition notes

See the `condition_codelist` for further information on the definition of this condition.

## Data Visualisation Flavour

Meds
