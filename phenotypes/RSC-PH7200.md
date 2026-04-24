# **Influenza Like Illness (ILI)

## Brief description

Identification of new episodes of Influenza Like Illness (ILI).

## Overview

This phenotype identifies **new ILI episodes** for an individual patient within a specified observation window.

## Input

- Patient longitudinal record
- Observation window (for example, week of observation)

## Output

- **Type:** events
- **Description:**
  A list of ILI episodes (dates) occurring within the observation window.

## Pseudocode

This phenotype applies template phenotype **T:RSC-PH1** with parameters:

| Parameter | Value |
|---|---|
| `disease_codelist` | RSC-C7199 |
| `interval` | 28 days |

## Notes on use

- Applying across patients yields:
  - ILI incidence (number of events)
  - an ILI cohort (patients with at least one event in the period)
  - patient-level variables (for example, any ILI in week)

## Disease notes

See the `disease_codelist` for further information on the definition of this disease.