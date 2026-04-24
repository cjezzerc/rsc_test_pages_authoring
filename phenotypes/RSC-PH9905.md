
# ** Chronic Obstructive Pulmonary Disease (COPD)

## Brief description

Identification of COPD status at a specified date.

## Overview

This phenotype determines whether an individual patient has COPD at a given date based on prior diagnosis events.

## Markdown authoring issues

Not sure about the explicit 0,1 business 

## Input

- Patient longitudinal record
- `status_date`

## Output

- **Type:** state
- **Description:**
  COPD status at the specified date (1 = COPD, 0 = no COPD).

## Parameters

| Parameter | Description |
|---|---|
| `status_date` | Date at which status is determined |

## Codelists

| Name in algorithm | RSC Codelist |
|---|---|
| `copd` | RSC-C2133 |

## Pseudocode

For a given patient:

* If the patient has at least one event from `copd` with a date on or before `status_date`:

  * Return **1 (COPD)**

* Otherwise:

  * Return **0 (no COPD)**

## Notes on use

- Applying across patients yields:
  - COPD prevalence at a given date
  - COPD cohorts (patients with status = 1)

## Assumptions

- COPD is treated as a **persistent condition** (once diagnosed, remains present).
