
# RSC - Ischaemic Heart Disease

## Brief description

Identification of subjects with Ischaemic Heart Disease

## Overview

The intention of the algorithm is to identify subjects with Ischaemic Heart Disease at a specified date.

## Pseudocode

The following parameter is required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| `status_date` | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  `ischaemic_heart_disease` | RSC-C3160                  |

* Patients are included in the cohort if
        
    * (i) The patient has at least one event from `ischaemic_heart_disease` at a date up to and including `status_date`

