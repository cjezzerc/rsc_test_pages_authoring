# Lower Respiratory Tract Infection (LRTI)

## Brief description

Identification of new cases of lower respiratory tract infection (LRTI). (**partial definition**!!)

## Overview

This phenotype identifies new cases of lower respiratory tract infection (LRTI) in primary care records using a curated composite SNOMED CT definition spanning acute bronchitis and acute pneumonia code groups. Within the specified observation window, a qualifying event is counted as a new case only if no prior qualifying event occurred in the preceding 28 days. This interval rule reduces double-counting from follow-up consultations during the same illness period. This implementation is a partial operational definition of LRTI. Aggregated outputs support incidence estimation, surveillance, and cohort derivation for epidemiological analyses.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `lrti_combined`                         |
| `interval`           | 28 days                                 |

`lrti_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C7211 |
| RSC-C7205 |

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.
