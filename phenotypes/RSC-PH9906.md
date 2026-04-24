
# Dementia

## Brief description

Identification of subjects with Dementia

## Overview

The intention of the algorithm is to identify subjects with Dementia at a specified date.

## Pseudocode

The following parameter is required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| `status_date` | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  `dementia` | RSC-C2002                 |
|  `dementia_meds` | RSC-C6371                 |

* Patients are included in the cohort if
        
    * (i) The patient has at least one event from `dementia` or `dementia_meds` at a date up to and including `status_date`

