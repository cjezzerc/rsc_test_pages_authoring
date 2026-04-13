
# RSC – Smoker Status

## Brief description

Identification of current smoker status

## Overview

The intention of the algorithm is to identify the smoker status of each patient in a dataset at a specified date.

The algorithm creates a table containing a standard code for each patient based on the most recent observation regarding smoker status.

## Pseudocode

The following parameter is required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| _**status-date**_ | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  _**active-smoker-codelist**_  | RSC-C2065                   |
|  _**ex-smoker-codelist**_   	 | RSC-C2066                   |
|  _**non-smoker-codelist**_ 	   | RSC-C2067                   | 

A composite code list _**all-smoker-status-codelist**_ is created as the union of _**active-smoker-codelist**_, _**ex-smoker-codelist**_ and  _**non-smoker-codelist**_  

* A results table is initialised with columns of "patient-id" and "computed-current-status"
* For each patient

    * _**patient-id**_ = Pseudonymised patient identifer

    * _**most-recent-status**_ = The most recent event for that patient with a code from _**all-smoker-status-codelist**_ with an observation date up to and including the _**status-date**_
    * If 
        * such an event can be found then _**computed-current-status**_ is calculated according to the following table

          | Codelist that _**most-recent-status**_ is a member of | _**computed-current-status**_                | 
          |--------------------------------|-----------------------------|
          |  _**active-smoker-codelist**_  | SMOKER       |
          |  _**ex-smoker-codelist**_ 	   | EX-SMOKER    |
          |  _**non-smoker-codelist**_ 	   | NON-SMOKER   | 

        * otherwise _**computed-current-status**_ is set to UNKNOWN
    * The tuple (_**patient-id**_, _**computed-current-status**_) is added as a row to the results table


