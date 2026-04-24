# **New cases of condition [T]

## Brief description

Template phenotype for identifying new cases for a specified condition.


## Overview

The phenotype identifies new cases by applying a minimum interval between events.

## Input


- Patient longitudinal record
  

| Parameter                | Description                                                                               |
|--------------------------|-------------------------------------------------------------------------------------------|
| `observation_window` | Timeframe within which new cases are to be identified                                     |
| `condition_codelist` | SNOMED CT codes identifying diagnosis events for the specific condition |
| `interval`           | Minimum number of days between two diagnosis events for the latter to indicate a new case |



## Output

* **Type:** events
* **Description:**
  A list of diagnosis events for the condition of interest that are considered to indicate new cases within the observation window.

## Pseudocode

For a given patient:

* Let `candidate_events` be all events with codes from `condition_codelist` within `observation_window`.

* For each event in `candidate_events`:

  * The event is considered to define a new case if:

    * There are no prior events from `condition_codelist` in the `interval` days before this event.

* Return the list of all such events.

## Notes on use

* Applying this phenotype across patients can produce:
  * event counts (incidence)
  * patient-level variables (for example, at least one event in list)
  * cohorts (for example, patients with at least one event)

## markdown authoring issues

* use of events in abstract sense to denote a new case, and in concrete sense of a record in the EPR is muddled and needs fixing
* lots of repetition (plus template notes can go if have (Template phenotype) in title)
  
## Template note

Section will be removed

