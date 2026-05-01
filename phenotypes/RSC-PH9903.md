
# Diabetes Type 2

## Brief Description

Identification of Diabetes Type 2 status of subject

## Overview

This phenotype determines Type 2 diabetes status at a specified index date in primary care records using curated SNOMED CT codelists for positive and negative disease-status events. For each patient, the most recent qualifying event on or before the index date defines status: a positive code indicates case status, while a negative code indicates non-case status. If no qualifying event exists, status defaults to non-case. Aggregated outputs support prevalence estimation, risk adjustment, and cohort derivation for epidemiological analyses.

## Template usage

This phenotype applies template phenotype T:RSC-PH4.

See the template for details of the algorithm.

The template requires these parameters to be specified:

| Parameter            | Value                                   |
|----------------------|-----------------------------------------|
| `patient_record`     | _To be provided on execution_           |   
| `status_date`        | _To be specified on execution_          |
| `positive_codelist`  | RSC-C2048                             |
| `negative_codelist`  | RSC-C7230                              |

## Pseudocode

See template

## Notes on use

See template

## Disease notes

See the codelists for further information on the definition of this condition.


