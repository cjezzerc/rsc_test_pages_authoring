# Influenza Like Illness (ILI)

## Brief description

Identification of new cases of influenza like illness (ILI).

## Overview

Influenza Like Illness (ILI)
This phenotype identifies new cases of influenza-like illness (ILI) in primary care records using a curated SNOMED CT codelist. Within the specified observation window, a qualifying event is counted as a new case only if no prior qualifying event occurred in the preceding 28 days. This interval rule reduces double-counting from follow-up consultations during the same illness period. Applied across populations, the phenotype supports incidence estimation, cohort construction, and derivation of a patient-level variable for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |   
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | RSC-C7199                               |
| `interval`           | 28 days                                 |




## Condition notes

See the `condition_codelist` for further information on the definition of this condition.

## Data Visualisation Flavour

Acute
