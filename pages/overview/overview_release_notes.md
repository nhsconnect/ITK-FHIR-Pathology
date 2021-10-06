---
title: Release Notes
keywords: development, versioning
tags: [development]
sidebar: overview_sidebar
permalink: overview_release_notes.html
summary: Summary release notes of the versions released in FHIR National Pathology Implementation Guide
---

{% include important.html content="This site is under active development by NHS Digital and is intended to provide all the technical resources you need to successfully develop the FHIR National Pathology. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." %}

## 1.2.0-beta ##


Update to Implementation Guidance in support of clarifications sought during proof of concept implementations.

### Status updated to Beta

- Implementation Guidance Maturity Level updated from Experimental to Beta.  The change reflects the increased maturity of the Implementation Guidance following the recent Proof of Concept testing and also use of the STU3 Pathology profiles as part of the National Integration EDIFACT/FHIR Adaptor.

### Default Value for DiagnosticReport.code = 721981007

 - guidance added on DiagnosticReport mapping page.



**Added pages for guidance on:**

#### Business Identifiers

- Guidance added regarding use of identifiers within National Pathology messaging payloads. Examples updates to align with guidance.

#### Reporting Values

- Guidance added on Observation.value[x] choice of datatype.
- Guidance added on units and [UCUM](http://unitsofmeasure.org).
- Guidance added on use of Extension-CareConnect-ValueApproximation-1 to mark approximations.
- Guidance added on qualified reference ranges (<x, >x).
        
#### Related Tests

- Guidance on use of Observation.related.type to record Observation cross-referencing.

### Specimen resource data mapping

- clarified and corrected some mapping issues to align with the CareConnect-Specimen-1 profile.

## 1.1.0-experimental ##

Test Report uses additional elements provided by the CareConnect-DiagnosticReport-1 profile to support the priority of a test and the date and time a test was requested. 

- CareConnect-DiagnosticReport-1.priority - The urgency of the test
- CareConnect-DiagnosticReport-1.authoredOn - The date and time of the test request

**Additional changes**

- The 'note' element has been updated with new narrative to describe its usage.

- Specimen page has been updated to remove a typo.

- CareConnect-Specimen-1.note element has been updated with new narrative to describe its usage.

- General housekeeping applied across the implementation guide.
  
## 1.0.0-experimental ##

- Project initialization
- Draft Implementation guide added
- National Pathology FHIR assets added

## CareConnect Level 2 Profiles ##

- CareConnect-ProcedureRequest-1 
- CareConnect-DiagnosticReport-1 
- CareConnect-Specimen-1 
- CareConnect-Observation
- CareConnect-Patient-1
- CareConnect-Organization-1
- CareConnect-Practitioner-1

## FHIR Value Sets ##

ValueSet-CareConnect-InterpretationCode-1
ValueSet-CareConnect-ReportCodeSnCT
ValueSet-CareConnect-FindingCode-1
ValueSet-CareConnect-SpecimenBodySite-1
ValueSet-CareConnect-SpecimenType-1

## FHIR CodeSystems ##

CodeSystem-CareConnect-InterpretationCode-1


## FHIR Data Type ##

CareConnect-Quantity-1

## FHIR Extensions ##

Extension-CareConnect-ValueApproximation-1
Extension-CareConnect-FastingStatus-1


