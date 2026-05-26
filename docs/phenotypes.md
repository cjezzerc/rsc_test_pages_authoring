# Phenotypes

## The scope of a phenotype in this repository

A phenotype in this repository is a computable, implementation-independent definition of how to derive a clinically meaningful event, state, or attribute from **a single patient’s longitudinal primary care record**.

They may identify incident events such as acute infections, prescribing events, or vaccinations; determine condition status at a given date for persistent or resolvable conditions; or derive condition independent patient attributes such as smoking status or BMI category. 

As our phenotypes are specified to operate at the level of a single patient, they do not cover the extra layers of execution and analysis that are required for certain applications:

| Application | Extra execution and analysis |
| ---- | ---- |
| Cohort definition | Apply phenotype across population of subjects and select on basis of phenotpye result |
| Incidence, Prevalence  | Apply phenotype across population of subjects and derive suitable aggregate statistics |
| Covariates | Apply phenotype across population of patients and annotate each subject with the derived value |

Some definitions of phenotype take these extra aspects as part of the definition, either implicitly or explicitly.

## Pseudocode

Definitions are written in semi-formal pseudocode: they are intended to be precise enough to be implemented in software, but independent of any specific data model, coding system, query language, or programming language.

When phenotype definitions refer to events, patient data are assumed to be represented as one or more event tables. Each event is assumed to carry a single SNOMED CT code, interpreted as positive evidence for the concept represented by that code.

For some concepts, events are also assumed to include one associated value (and, where relevant, a unit of measurement). For example, this applies to 60621009 |Body mass index|.

## Template phenotypes

Many phenotypes for different conditions follow shared logical patterns and differ only in parameters such as the codelist used to specify the condition. 

To support this, the repository defines "general purpose" template phenotypes. 

For example, RSC-PH5 is defined as 

* use template RSC-PH1
* with codelist RSC-C7199
* and with an interval of 28 days.

Whereas RSC-PH9
is defined as 

* use template RSC-PH1
* with codelist RSC-C7204
* and with an interval of 28 days.
