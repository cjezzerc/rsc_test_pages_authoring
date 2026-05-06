# Acute Respiratory Infection (ARI)

## Brief description

Identification of new cases of acute respiratory infection (ARI). (**partial definition**!!)

## Overview

This phenotype identifies new cases of acute respiratory infection (ARI) in primary care records using a combination of curated SNOMED CT codelists for defining conditions for [ARI](https://www.eurosurveillance.org/content/10.2807/1560-7917.ES.2024.29.35.2300682). Within the specified observation window, a qualifying event is counted as a new case only if no prior qualifying event occurred in the preceding 28 days. This interval rule reduces double-counting from follow-up consultations during the same illness period. This implementation is a partial operational definition of ARI. Applied across populations, the phenotype supports incidence estimation, cohort construction, and derivation of patient-level variables for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `ari_combined`                          |
| `interval`           | 28 days                                 |



| `ari_combined` is the union of the following codelists: |
|----------|
| RSC-C7211 |
| RSC-C7205 |
| RSC-C7215 |
| RSC-C7199 |

## Pseudocode

See template

## Notes on use

See template

## Condition notes

See the codelists for further information on the definition of this condition.
