
# Codelists

A codelist in this repository is a list of codes that are needed to execute the logic of a particular phenotype, along with associated codelist metadata.

Other terms used for codelists are value sets, subsets, and code sets.

The page for each codelist in the repository has three sections

| Section | Contents |
|--|--|
| About this codelist | This is information such as notes on how and why the codelist was constructed, and also details of the SNOMED release that the logical definition was last revised for, and against which the expansion was made |
| Logical Definition |The logical definition is a definition of the desired membership of a codelist that makes use of the hierarchical nature of a code system like SNOMED CT.|
| Expansion |The expansion is the explicit list of codes produced by applying the rules in the logical definition against a specific SNOMED CT release. In practical terms, the list of codes can be equated with the "expansion".|

"logical definition" and "expansion" are standard terms from HL7/FHIR terminology practice.

The expansion is also sometimes known as the extensional definition, or the flat list.

The logical definition is also sometimes known as the intensional definition, or more loosely the "ECL definition".

At present, all codelists in this repository are SNOMED CT codelists.

The logical definition is used by the authors of the codelist, but can also be useful to codelist users as it often expresses important information about the codelist authors' intentions.

## Curation

The codelists in this repository are focused on **analysing** health records rather than specifying pick lists of codes for **entry** into health records. As such they contain inactive codes. They also sometimes include codes that should not have been entered into records, but where experience shows that such codes are encountered in records. As such these lists must **never** be used as the sole basis of codelists for data entry.

The curation of the codelists is also focused on primary care and therefore the lists may not be so appropriate for analysing secondary or tertiary care records.

The RSC codelists are curated by a team of GPs with terminology expertise, using an in-house tooling workflow for initial construction and maintenance across SNOMED CT releases.

For local RSC users, the RSC codelist numbering is aligned with identifiers in the in-house system. For example, RSC-C7199 corresponds to TADDS variable 7199.

## Logical Definition

The logical definitions in this repository follow a standard pattern of clauses of these forms

1. include A and all its descendants
1. include concept B (but not its descendants)
1. exclude C and all its descendants
1. exclude concept D (but not its descendants)

Sometimes (in this repository and elsewhere) a logical definition consists of only type (2) clauses from the list above, i.e. it is simply a list of individual concepts. In this case the distinction between the logical definition and the expansion blurs.

## <a id="Expansion"></a>Expansion

The SNOMED CT release against which the expansion is made is stated.

The expansions can be downloaded using a button in the expansion section, or on the codelist index page.

We advise that for long term access relevant codelists should be reproduced as supplementary information in any publications.

### EMIS namespace codes

The codelists presented here contain some codes from the EMIS namespace. For the majority of records in the RSC dataset, EMIS namespace codes are mapped to UK release SNOMED codes using tables provided by EMIS as part of the data provisioning process. There remain a small number of codes that are not mapped by such a process and these remain as codes of the form (1-8 digits)-100006-(3 digits), 

e.g. 2010031000006100 | Acute infective exacerbation of asthma |

Expansions of logical definitions are supplemented using information provided by EMIS, that links many of the EMIS namespace codes into the SNOMED UK release hierarchy. For certain EMIS namespace concepts it is necessary to add explicit clauses to include single concepts in the logical definition.

### Inactive concepts

Codelists are supplemented with data from the NHS England History Substitution Table.

## Use of codelists in phenotypes

Non-template phenotype definitions reference specific codelists as algorithm parameters.

The same codelist can be reused in more than one phenotype. For example, RSC-C7221 appears in both the ECLD phenotype (RSC-PH19) and the ARI phenotype (RSC-PH20) as part of their combined condition codelists.

A single phenotype may also use multiple codelists. For example RSC-PH27 uses both RSC-C7529 and RSC-C7654.
