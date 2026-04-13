
# Diabetes Type 2

## Overview

The intention of the algorithm is to identify the Diabetes Type 2 status of each patient in a dataset at a specified date.

The algorithm creates a table containing a standard code for each patient based on the most recent observation regarding Diabetes Type 2.

**OR** is this just an in or out of cohort thing? Is this an example where might want more than one phenotype or is that overkill? Are these phenotypes really here to put context on a codelist so precise use case is not too important **??????????**

**THIS** is very essentially the same logic as smoker status so there could be a template method perhaps, but would have to specify what the output status was for each input codelist **?????**

**OR** does this make a case for a "cohort with exit condition" template phenotype **???????**

## Pseudocode

The following parameter is required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| _**status-date**_ | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  _**diabetes-t2**_  | RSC-C2048                   |
|  _**diabetes-t2-resolved**_   	 | RSC-C7230                   |

A composite code list _**all-statuses-codelist**_ is created as the union of the codelists in the table above.

* A results table is initialised with columns of "patient-id" and "computed-current-status"
* For each patient

    * _**patient-id**_ = Pseudonymised patient identifer

    * _**most-recent-status**_ = The most recent event for that patient with a code from _**all-statuses-codelist**_ with an observation date up to and including the _**status-date**_
    * If 
        * such an event can be found then _**computed-current-status**_ is calculated according to the following table

          | Codelist that _**most-recent-status**_ is a member of | _**computed-current-status**_                | 
          |--------------------------------|-----------------------------|
          |  _**diabetes-t2**_  | DIABETES-T2       |
          |  _**diabetes-resolved-t2**_ 	   | DIABETES-T2-RESOLVED    |

        * otherwise _**computed-current-status**_ is set to DIABETES-T2-NEVER-RECORDED
    * The tuple (_**patient-id**_, _**computed-current-status**_) is added as a row to the results table