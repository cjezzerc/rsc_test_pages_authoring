
# Diabetes Type 2

## Brief Decription

Identification of subjects with Diabetes Type 2

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
| `status_date` | The date at which the status is to determined |

The following codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
|  `diabetes_t2`  | RSC-C2048                   |
|  `diabetes_t2_resolved`   	 | RSC-C7230                   |

A composite code list `all_statuses_codelist` is created as the union of the codelists in the table above.

* A results table is initialised with columns of "patient-id" and "computed-current-status"
* For each patient

    * `patient_id` = Pseudonymised patient identifer

    * `most_recent_status` = The most recent event for that patient with a code from `all_statuses_codelist` with an observation date up to and including the `status_date`
    * If 
        * such an event can be found then `computed_current_status` is calculated according to the following table

          | Codelist that `most_recent_status` is a member of | `computed_current_status`                | 
          |--------------------------------|-----------------------------|
          |  `diabetes_t2`  | DIABETES-T2       |
          |  `diabetes_resolved_t2` 	   | DIABETES-T2-RESOLVED    |

        * otherwise `computed_current_status` is set to DIABETES-T2-NEVER-RECORDED
    * The tuple (`patient_id`, `computed_current_status`) is added as a row to the results table