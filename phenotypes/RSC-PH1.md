# RSC – C+RD – Weekly Report


## Brief description

Template phenotype used in creating the weekly RCGP RSC Communicable and Respiratory Disease Report for England.

## Template note

This is a template phenotype used in creating the weekly RCGP RSC Communicable and Respiratory Diseases for England report. The specific disease of interest is defined by specifying the codelist in the table below.

The following parameters are specific for each disease of interest, and should be specified by the phenotyping algorithm that uses this template.

| Parameter               | Description                     |
|-------------------------|---------------------------------|
|  _**disease-codelist**_ |   A list of SNOMED CT codes that identify a diagnosis event for the disease of interest     | 
|  _**interval**_         |   The period of time (in days) that must elapse between two diagnosis events for the second event to be considered a new event    |

## Overview

The algorithm identifies the cohort of patients that have a new diagnosis event for the disease of interest within the week of observation.

The data for the [RSC Weekly report](https://www.rcgp.org.uk/representing-you/research-at-rcgp/research-surveillance-centre/public-health-data) are counts of numbers of patients in the cohort, stratified by age and region.

## Pseudocode

* Patients are included in the cohort if
        
    * (i) The patient has at least one event from _**disease-codelist**_ within the week of observation 
        
    * AND
        
    * (ii) The patient has no events from _**disease-codelist**_ in the period of _**interval**_ days before that event