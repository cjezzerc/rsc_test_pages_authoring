# Exacerbation of Chronic Lung Disease (ECLD)

## Brief description

Identification of new cases of exacerbation of chronic lung disease (ECLD). (**partial definition**!!)

## Overview

This phenotype identifies new cases of exacerbation of chronic lung disease (ECLD) in primary care records using a curated composite SNOMED CT definition that includes exacerbation codes for asthma and COPD. Within the specified observation window, a qualifying event is counted as a new case only if no prior qualifying event occurred in the preceding 28 days. This interval rule reduces double-counting from follow-up consultations during the same illness period. This implementation is a partial operational definition of ECLD. Aggregated outputs support incidence estimation, surveillance, and cohort derivation for epidemiological analyses.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `ecld_combined`                         |
| `interval`           | 28 days                                 |

`ecld_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C7215 |
| RSC-C7199 |

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.
