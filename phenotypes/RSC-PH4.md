# Standard Incidence


## Brief description

Template phenotype for identifying new cases of a disease within a defined time window

## Template note

The following parameters are specific for each disease of interest, and should be specified by the phenotyping algorithm that uses this template:

| Parameter               | Description                     |
|-------------------------|---------------------------------|
|  _**disease-codelist**_ |   A list of SNOMED CT codes that identify a diagnosis event for the disease of interest     | 
|  _**interval**_         |   The period of time (in days) that must elapse between two diagnosis events for the second event to indicate a new case    |

The following parameters are also required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| _**start-time-period**_ | The earliest date for which new cases are to be found |
| _**end-time-period**_   | The latest date for which new cases are to be found |

## Overview

The algorithm identifies the cohort of patients that have a diagnosis event indicating a new case of the disease of interest within the period defined by _**start-time-period**_ and _**end-time-period**_

## Pseudocode

* Patients are included in the cohort if
        
    * (i) The patient record has at least one event from _**disease-codelist**_ within the week of observation 
        
    * AND
        
    * (ii) The patient record has no events from _**disease-codelist**_ in the period of _**interval**_ days before that event