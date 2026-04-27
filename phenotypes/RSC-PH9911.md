# Lower Respiratory Tract Infection (LRTI)

## Brief description

Identification of new cases of lower respiratory tract infection (LRTI).

## Overview

This phenotype identifies new cases of lower respiratory tract infection for an individual patient within a specified observation window.

LRTI encompasses acute bronchitis and acute pneumonia.

## Template usage

This phenotype applies template phenotype **T:RSC-PH1**.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `lrti_combined`                         |
| `interval`           | 28 days                                 |

`lrti_combined` is the union of the codesets RSC-C7211 and RSC-C7205

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.
