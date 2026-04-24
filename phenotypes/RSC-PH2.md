
# BMI categorisation

## Brief description

Categorisation of BMI based on categorical codes or numeric observations

## Overview

This algorithm provides a harmonised categorisation of the BMI for each patient, based on the latest observation within a particular time window. The algorithm allows for the observation being numerical in some cases (e.g. 24.3) and categorical in other cases (e.g. BMI <20), and also for a variety of equivalent categorical concepts being used.

The algorithm creates a table containing a standard code for each patient categorising BMI into bands of <20, 20-24.9, 25-29.9, 30-39.9 and 40+

?? Is this the cateogisation strategy intended? Are these the categories we want (e.g. could separate 30-39.9 into two categories Obese I and Obese II; or have a category of <16; hoever that leads to more ambiguities, e.g. is Obese Obese I or II ?)

## Pseudocode

The following parameters are required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| `start_observation_period` | The earliest date of observations to be considered |
| `end_observation_period`   | The latest date of observations to be considered   |

The following non overlapping codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
| `bmi_lt20_codelist`     |	RSC-C????   |
| `bmi_20_24.9_codelist`     |	RSC-C1502   |
| `bmi_25_29.9_codelist`	   |  RSC-C1504   |
| `bmi_30_39.9_codelist`	   |  RSC-C1503   |
| `bmi_ge40_codelist`	       |  RSC-C1505   |
| `bmi_obs_entity_codelist`  |  RSC-C5022  |

* A composite code list `all_bmi_status_codelist` is created as the union of the six codelists in the table.

* A results table is initialised with columns of "patient-id" and "computed-current-bmi-status"

* For each patient

    * `patient_id` = Pseudonymised patient identifer

    * `most_recent_bmi` = The most recent event for that patient with a code from `all_bmi_status_codelist`, and with an observation date in the inclusive period `start_observation_period` to  `end_observation_period`
    * if `most_recent_bmi` is from the codelist `bmi_obs_entity_codelist` then `bmi_value` is set to the numeric value associated with the event

    * `computed_current_bmi_status` is set according to the following table

      | `most_recent_bmi` concept is from ..| `bmi_value` |	computed-current-bmi-status  | SNOMED | OMOP | Term |
      |--|--|--|--|--|--|
      | `bmi_lt20_codelist`                 |	        | BMI_LT20     | 310252000 | 4147565 | Body mass index less than 20   |
      | `bmi_obs_entity_codelist`           |	<20	    | ""           | ""        | ""      | ""                             |
      | `bmi_20_24.9_codelist`              |	      	| BMI_20-24.9  | 412768003 | 4135421 | Body mass index 20-24 - normal |
      | `bmi_obs_entity_codelist`           |	20-24.9	| ""           | ""        | ""      | ""                             |
      | `bmi_25_29.9_codelist`	            |       	| BMI_25-29.9  | etc
      | `bmi_obs_entity_codelist`         	| 25-29.9	| ""           |
      | `bmi_30_39.9_codelist`	            |     	  | BMI_30-39.9  |
      | `bmi_obs_entity_codelist`           | 30-39.9 | ""           |
      | `bmi_ge40_codelist`	                |      	  | BMI_GE40     |
      | `bmi_obs_entity_codelist`           | >40     | ""           |
      | no event found from any codelist        |         | UNKNOWN      | 	261665006	| 4129922 | Unknown |


    * The tuple (`patient_id`, `computed_current_bmi_status`) is added as a row to the results table


