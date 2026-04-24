# Standard Incidence


## Brief description

Template phenotype for identifying new cases of a disease within a defined time window

## Template note

The following parameters are specific for each disease of interest, and should be specified by the phenotyping algorithm that uses this template:

| Parameter               | Description                     |
|-------------------------|---------------------------------|
|  `disease_codelist` |   A list of SNOMED CT codes that identify a diagnosis event for the disease of interest     | 
|  `interval`         |   The period of time (in days) that must elapse between two diagnosis events for the second event to indicate a new case    |

The following parameters are also required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| `start_time_period` | The earliest date for which new cases are to be found |
| `end_time_period`   | The latest date for which new cases are to be found |

## Overview

The algorithm identifies the cohort of patients that have a diagnosis event indicating a new case of the disease of interest within the period defined by `start_time_period` and `end_time_period`

## Pseudocode

* Patients are included in the cohort if
        
    * (i) The patient record has at least one event from `disease_codelist` within the week of observation 
        
    * AND
        
    * (ii) The patient record has no events from `disease_codelist` in the period of `interval` days before that event