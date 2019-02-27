---
title: Test Report
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_diagnostic_report.html
summary: "National Pathology FHIR Message Profile -  Test Report"
---
## The Test Report for a Haemotology or Chemical Biology Test ##

## Mapping for Diagnostic Report ##

How to populate the Specimen instance to conform to the profiles below:

|**Level 1**|[DiagnosticReport Resource](http://hl7.org/fhir/stu3/diagnosticreport.html)|**Level 2**|[CareConnect-DiagnosticReport-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1/_history/1.1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_diagnostic_report_all.html)**|


|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and Mapping for National Pathology Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  **DiagnosticReport** | ​ |  |  | **A Diagnostic report - a combination of request information, atomic results, images, interpretation, as well as formatted reports<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - identifier | 0..* | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier "Identifier") | Business identifier for report |
|  - basedOn | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | What was requested<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-ProcedureRequest-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1  "CareConnect-ProcedureRequest-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|  - status | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | registered : partial : preliminary : final +<br/>Binding (required): The status of the diagnostic report as a whole. [Diagnostic-Report-Status]( http://hl7.org/fhir/stu3/valueset-diagnostic-report-status.html ) |
|  - category | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Service category<br/>Binding (preferred): Codes for diagnostic service sections. [CareConnect-ClinicalDisciplines](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ClinicalDisciplines-1 )<br/><font color='red'>Clinical Discipline</font> |
|  - code | 1..1 | Mandatory | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Name/Code for this diagnostic report<br/>Binding (preferred): Codes that describe Diagnostic Reports. [Report Codes]( http://hl7.org/fhir/stu3/valueset-report-codes.html )<br/><font color='red'>Test Report Name</font> |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | The subject of the report - usually, but not always, the patient<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Patient-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1  "CareConnect-Patient-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|  - - issued | 1..1 | Mandatory | [Instant](http://hl7.org/fhir/stu3/datatypes.html#instant "Instant") | DateTime this version was released <font color="red">The date and time on which the test report was issued by the performer to the requester.</font> |
|  - performer | 0..* | Optional | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html "BackboneElement") | Participants in producing the report |
|   | 1..1 | Mandatory | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1 if a Practitioner is also recorded.'</font> |
|   | 1..1 | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font> |
|  - specimen | 0..* | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimens this report is based on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..* | Optional | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |
|  - result | 0..* | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Observations - simple, or complex nested groups<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..* | Optional | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observation-1'</font> |
|  - conclusion | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Clinical Interpretation of test results <br/><font color='red'>Human readable clinical summary relating to the test report.</font> |
|  - codedDiagnosis | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Codes for the conclusion<br/>Binding (preferred): A SNOMED Coded finding for the test report. [CareConnect-Finding-Code](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-FindingCode-1 ) <font color="red">Finding Code</font> |
|   - - coding | 0..* | Required | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |