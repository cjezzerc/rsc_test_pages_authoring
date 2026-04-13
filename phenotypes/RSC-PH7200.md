# RSC – Influenza Like Illness

## Brief description

Identification of new cases of Influenza Like Illness for the RCGP RSC weekly report of Respiratory and Communicable Diseases for England.

## Overview

The algorithm identifies the cohort of patients that have a new diagnosis event for Influenza Like Illness within the week of observation.

The data for the [RSC Weekly report](https://www.rcgp.org.uk/representing-you/research-at-rcgp/research-surveillance-centre/public-health-data) are counts of numbers of patients in the cohort, stratified by age and region.

## Pseudocode

The cohort is identified using the template phenotype T:RSC-PH1 with parameters

| Parameter               | Description     |
|-------------------------|-----------------|
|  _**disease-codelist**_ |   RSC-C7199     | 
|  _**interval**_         |   28 days       |

See the _**disease-codelist**_ for further information on the definition of this disease.