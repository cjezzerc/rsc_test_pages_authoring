# Pulse Rate

## Brief description

Extraction of pulse rate measurements.

## Overview

Pulse Rate
This phenotype defines pulse rate measurement events in primary care records using a curated SNOMED CT codelist for pulse rate observations. It is intended for use in identifying measurement-based coded events and associated numeric values within a specified observation window.

## Template usage

This phenotype applies template phenotype T:RSC-PH32.

The template requires these parameters to be specified:

| Parameter             | Value                                   |
|-----------------------|-----------------------------------------|
| `patient_record`      | _To be provided on execution_           |
| `observation_window`  | _To be specified on execution_          |
| `measurement_codelist`| RSC-C7485                               |

## Condition notes

See the `measurement_codelist` for further information on the definition of this measurement.

## Data Visualisation Flavour

Measurement
