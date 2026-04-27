# Exacerbation of Chronic Lung Disease (ECLD)

## Brief description

Identification of new cases of exacerbation of chronic lung disease (ECLD).

## Overview

This phenotype identifies new cases of exacerbation of chronic lung disease for an individual patient within a specified observation window.

ECLD encompasses exacerbations of asthma and exacerbations of COPD.

## Template usage

This phenotype applies template phenotype **T:RSC-PH1**.

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
