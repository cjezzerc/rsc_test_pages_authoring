# Acute Bronchitis

## Brief description

Identification of new cases of acute bronchitis.

## Overview

This phenotype identifies new cases of acute bronchitis in primary care records using a curated SNOMED CT codelist for acute bronchitis. Within the specified observation window, a qualifying event is counted as a new case only if no prior qualifying event occurred in the preceding 28 days. This interval rule reduces double-counting from follow-up consultations during the same illness period. Aggregated outputs support incidence estimation, surveillance, and cohort derivation for epidemiological analyses.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |   
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | RSC-C7211                               |
| `interval`           | 28 days                                 |


## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the `condition_codelist` for further information on the definition of this condition.
