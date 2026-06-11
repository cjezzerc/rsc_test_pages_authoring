# Statins Prescribed

## Brief description

Identification of statin prescribing events.

## Overview

This phenotype identifies prescribing events for statins in primary care records using curated medication codelists. Applied across populations, the phenotype supports prescribing surveillance, cohort construction, and derivation of patient-level variables for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH31.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `drug_codelist` | `statins_combined`                      |

`statins_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C5268 |
| RSC-C6211 |



## Product scope

See the `drug_codelist` for further information on the products included.

## Data Visualisation Flavour

Meds
