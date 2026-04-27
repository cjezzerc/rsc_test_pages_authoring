# Acute Respiratory Infection (ARI)

## Brief description

Identification of new cases of acute respiratory infection (ARI). (**partial definition**!!)

## Overview

This phenotype identifies new cases of acute respiratory infection for an individual patient within a specified observation window.

ARI encompasses lower respiratory tract infections (LRTI) and exacerbations of chronic lung disease (ECLD).

## Template usage

This phenotype applies template phenotype **T:RSC-PH1**.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `ari_combined`                          |
| `interval`           | 28 days                                 |

`ari_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C7211 |
| RSC-C7205 |
| RSC-C7215 |
| RSC-C7199 |

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.
