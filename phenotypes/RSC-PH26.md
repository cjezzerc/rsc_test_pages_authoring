# Statins Prescribed

## Brief description

Identification of statin prescribing events.

## Overview

This phenotype identifies prescribing events for statins in primary care records using curated medication codelists. Within the specified observation window, a qualifying event is counted as a new event only if no prior qualifying event occurred in the preceding 0 days (that is, no de-duplication interval is applied). Applied across populations, the phenotype supports prescribing surveillance, cohort construction, and derivation of patient-level variables for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `statins_combined`                      |
| `interval`           | 0 days                                  |

`statins_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C5268 |
| RSC-C6211 |

## Pseudocode

See template

## Notes on use

See template

## Condition notes

See the codelists for further information on the definition of this condition.