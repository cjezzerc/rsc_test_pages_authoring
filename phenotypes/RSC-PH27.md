# Respiratory Syncytial Virus (RSV) Vaccination

## Brief description

Identification of respiratory syncytial virus (RSV) vaccination events.

## Overview

This phenotype identifies RSV vaccination-related events in primary care records using curated codelists for RSV vaccination and RSV vaccine products. Applied across populations, the phenotype supports vaccine uptake surveillance, cohort construction, and derivation of patient-level variables for downstream analysis.

Events that occur on the same day are treated as a single events. 

## Template usage

This phenotype applies template phenotype T:RSC-PH31.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `drug_codelist`      | `rsv_vaccination_combined`              |
| same_day_filter      | True                                |

`rsv_vaccination_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C7529 |
| RSC-C7654 |

## Pseudocode

See template

## Notes on use

See template

## Product scope

See the `drug_codelist` for further information on the products included.

## Data Visualisation Flavour

Meds
