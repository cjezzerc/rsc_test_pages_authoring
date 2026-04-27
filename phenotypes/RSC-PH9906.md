# Dementia

## Brief description

Identification of dementia status of subject

## Overview

This phenotype determines whether an individual patient has dementia at a given date based on prior diagnosis events.

## Template usage

This phenotype applies template phenotype T:RSC-PH4.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |   
| `status_date`        | _To be specified on execution_          |
| `positive_codelist`  | `dementia_combined`                     |
| `negative_codelist`  | _not used_                              |

`dementia_combined` is the union of the following codelists:

| Codelist |
|----------|
| RSC-C2002 |
| RSC-C6371 |

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.

## Assumptions

Dementia is treated as a **persistent condition** (once diagnosed, remains present).