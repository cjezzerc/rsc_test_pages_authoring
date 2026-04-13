
# BMI categorisation

## Overview

This algorithm provides a harmonised categorisation of the BMI for each patient, based on the latest observation within a particular time window. The algorithm allows for the observation being numerical in some cases (e.g. 24.3) and categorical in other cases (e.g. BMI <20), and also for a variety of equivalent categorical concepts being used.

The algorithm creates a table containing a standard code for each patient categorising BMI into bands of <20, 20-24.9, 25-29.9, 30-39.9 and 40+

?? Is this the cateogisation strategy intended? Are these the categories we want (e.g. could separate 30-39.9 into two categories Obese I and Obese II; or have a category of <16; hoever that leads to more ambiguities, e.g. is Obese Obese I or II ?)

## Pseudocode

The following parameters are required:

| Parameter         | Description                                   |
|-------------------|-----------------------------------------------|
| _**start-observation-period**_ | The earliest date of observations to be considered |
| _**end-observation-period**_   | The latest date of observations to be considered   |

The following non overlapping codelists are used

| codelist name in algorithm     | RSC Codelist                |
|--------------------------------|-----------------------------|
| _**bmi-lt20-codelist**_     |	RSC-C????   |
| _**bmi-20-24.9-codelist**_     |	RSC-C1502   |
| _**bmi-25-29.9-codelist**_	   |  RSC-C1504   |
| _**bmi-30-39.9-codelist**_	   |  RSC-C1503   |
| _**bmi-ge40-codelist**_	       |  RSC-C1505   |
| _**bmi-obs-entity-codelist**_  |  RSC-C5022  |

* A composite code list _**all-bmi-status-codelist**_ is created as the union of the six codelists in the table.

* A results table is initialised with columns of "patient-id" and "computed-current-bmi-status"

* For each patient

    * _**patient-id**_ = Pseudonymised patient identifer

    * _**most-recent-bmi**_ = The most recent event for that patient with a code from _**all-bmi-status-codelist**_, and with an observation date in the inclusive period _**start-observation-period**_ to  _**end-observation-period**_
    * if _**most_recent_bmi**_ is from the codelist _**bmi-obs-entity-codelist**_ then _**bmi_value**_ is set to the numeric value associated with the event

    * _**computed-current-bmi-status**_ is set according to the following table

      | _**most-recent-bmi**_ concept is from ..| _**bmi_value**_ |	computed-current-bmi-status  | SNOMED | OMOP | Term |
      |--|--|--|--|--|--|
      | _**bmi-lt20-codelist**_                 |	        | BMI_LT20     | 310252000 | 4147565 | Body mass index less than 20   |
      | _**bmi-obs-entity-codelist**_           |	<20	    | ""           | ""        | ""      | ""                             |
      | _**bmi-20-24.9-codelist**_              |	      	| BMI_20-24.9  | 412768003 | 4135421 | Body mass index 20-24 - normal |
      | _**bmi-obs-entity-codelist**_           |	20-24.9	| ""           | ""        | ""      | ""                             |
      | _**bmi-25-29.9-codelist**_	            |       	| BMI_25-29.9  | etc
      | _**bmi-obs-entity-codelist**_         	| 25-29.9	| ""           |
      | _**bmi-30-39.9-codelist**_	            |     	  | BMI_30-39.9  |
      | _**bmi-obs-entity-codelist**_           | 30-39.9 | ""           |
      | _**bmi-ge40-codelist**_	                |      	  | BMI_GE40     |
      | _**bmi-obs-entity-codelist**_           | >40     | ""           |
      | no event found from any codelist        |         | UNKNOWN      | 	261665006	| 4129922 | Unknown |


    * The tuple (_**patient-id**_, _**computed-current-bmi-status**_) is added as a row to the results table


