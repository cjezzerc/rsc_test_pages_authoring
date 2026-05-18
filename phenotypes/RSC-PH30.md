# Ischaemic Heart Disease

## Brief description

Identification of ischaemic heart disease status of subject

## Overview

This phenotype determines ischaemic heart disease status at a specified date in primary care records using a curated SNOMED CT codelist for positive disease evidence. For each patient, any qualifying event on or before the specified date classifies the patient as a case. Because no negative-status codelist is used, status is treated as persistent once recorded. Applied across populations, the phenotype supports prevalence estimation, cohort construction, and derivation of patient-level variables for downstream analysis.

## Template usage

This phenotype applies template phenotype T:RSC-PH4.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |   
| `status_date`        | _To be specified on execution_          |
| `positive_codelist`  | RSC-C3160                               |
| `negative_codelist`  | _not used_                              |

## Pseudocode

See template

## Notes on use

See template

## Condition notes

See the codelists for further information on the definition of this condition.

## Assumptions

Ischaemic heart disease is treated as a persistent condition (once diagnosed, remains present).