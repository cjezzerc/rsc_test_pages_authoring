# Upper Respiratory Tract Infection (URTI)

## Brief description

Identification of new cases of upper respiratory tract infection (URTI).

## Overview

This phenotype identifies new cases of upper respiratory tract infection (URTI) in primary care records using a combination of curated SNOMED CT codelists for defining conditions for URTI. An interval rule (with a default value of 28 days) reduces double-counting from follow-up consultations during the same illness period. This implementation is a partial operational definition of LRTI. Applied across populations, the phenotype supports incidence estimation, cohort construction, and derivation of a patient-level variable for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | `urti_combined`                         |
| `interval`           | _Specifiable on execution_ (default=14 days) |



| `urti_combined` is the union of the following codelists: |
|----------|
| RSC-C7208 |
| RSC-C7210 |
| RSC-C7206 |
| RSC-C7204 |
| RSC-C7197 |
| RSC-C7212 |



## Condition notes

See the codelists for further information on the definition of this condition.

## Data Visualisation Flavour

Acute
