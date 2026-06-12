# Acute Laryngitis

## Brief description

Identification of new cases of acute laryngitis.

## Overview

This phenotype identifies new cases of acute laryngitis in primary care records using a curated SNOMED CT codelist. An interval rule (with a default value of 28 days) reduces double-counting from follow-up consultations during the same illness period. Applied across populations, the phenotype supports incidence estimation, cohort construction, and derivation of a patient-level variable for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH1.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |
| `observation_window` | _To be specified on execution_          |
| `condition_codelist` | RSC-C7197                               |
| `interval`           | _Specifiable on execution_ (default=28 days) |




## Condition notes

See the `condition_codelist` for further information on the definition of this condition.

## Data Visualisation Flavour

Acute
