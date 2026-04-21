
# Dementia

## Brief description

Identification of subjects with Dementia

## Overview

The intention of the algorithm is to identify subjects with Dementia at a specified date.

## Pseudocode

The following parameter is required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| _**status-date**_ | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  _**dementia**_ | RSC-C2002                 |
|  _**dementia_meds**_ | RSC-C6371                 |

* Patients are included in the cohort if
        
    * (i) The patient has at least one event from _**dementia**_ or _**dementia_meds**_ at a date up to and including _**status-date**_

