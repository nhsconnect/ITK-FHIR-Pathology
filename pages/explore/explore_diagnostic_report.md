---
title: Test Report
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_diagnostic_report.html
summary: "National Pathology FHIR Message Profile -  Test Report"
---
## Test Report Overview for a Haematology or Chemical Pathology Test ##

Contains data on the report of tests performed on the patient and is populated with data from the performing organisation. The report may be a document, structured data or a combination of both. For unstructured reports there may or may not be additional structured data depending on what the GP practice decides should be coded into the clinical record. Each test report may contain multiple test batteries, test results and specimens.


## Mapping for Diagnostic Report ##

How to populate the Diagnostic Report instance to conform to the profiles below:

|**Level 1**|[DiagnosticReport Resource](http://hl7.org/fhir/stu3/DiagnosticReport.html)|**Level 2**|[CareConnect-DiagnosticReport-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_diagnostic_report_all.html)**|

|  **Name** | **Card.** | **Business Conformance** | **Type** | **Description, Constraints and Mapping for National Pathology Implementation** |  |  |  |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | --- | --- | --- | --- | --- | --- | --- |
|  **DiagnosticReport** | ​ |  |  | **A Diagnostic report - a combination of request information, atomic results, images, interpretation, as well as formatted reports<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |  |  |  |  |  |  |  |
|  - id | 0..1 | Optional | [Id](http://hl7.org/fhir/stu3/datatypes.html#id "Id") | Logical id of this artifact<br/><font color="red">MUST contain a unique identifier to identify the instance of a DiagnosticReport</font> |  |  |  |  |  |  |  |
|  - meta | 0..1 | Mandatory | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta "Meta") | Metadata about the resource<br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1'</font> |  |  |  |  |  |  |  |
|  - identifier | 0..* | Required | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier "Identifier") | Business identifier for report<br/><font color="red">A business level identifier for the test report. Produced by the performing organisation.</font> |  |  |  |  |  |  |  |
|  - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | The namespace for the identifier value<br/><font color="red">MUST contain a local identifier naming system</font> |  |  |  |  |  |  |  |
|  - - value | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | The value that is unique<br/><font color="red">MUST contain a unique identifier</font> |  |  |  |  |  |  |  |
|  - basedOn | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | What was requested<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided<br/><font color="red">Reference to the Test Request Summary.</font> |  |  |  |  |  |  |  |
|   |  | Required | [CareConnect-ProcedureRequest-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1  "CareConnect-ProcedureRequest-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |  |  |  |  |  |  |  |
|  - status | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | registered : partial : preliminary : final +<br/>Binding (required): The status of the diagnostic report as a whole. [Diagnostic-Report-Status]( http://hl7.org/fhir/stu3/valueset-diagnostic-report-status.html )<br/><font color="red">The status of the Test Report. MUST be set to 'partial' when the report is issued on an initial, interim or preliminary basis, for example because some of the requested tests have not yet completed. MUST be set to ‘final’ when the report is completed. MUST be set to ‘unknown’ when the status is unable to be determined.</font> |  |  |  |  |  |  |  |
|  <a href="#" data-toggle="tooltip" title="Clinical Discipline">- category</a>| 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Service category<br/>Binding (preferred): Codes for diagnostic service sections. ( http://hl7.org/fhir/stu3/valueset-diagnostic-service-sections.html ) |  |  |  |  |  |  |  |
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |  |  |  |  |  |  |  |
|  <a href="#" data-toggle="tooltip" title="Report Name">- code</a>| 1..1 | Mandatory | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Name/Code for this diagnostic report<br/>Binding (preferred): Codes that describe Diagnostic Reports. [Report Codes]( https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ReportCodeSnCT-1 )<br/><font color="red">FHIR suppliers SHOULD populate with the SNOMED ConceptID 721981007 for 'Diagnostic studies report'.</font> |  |  |  |  |  |  |  |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system<br/><font color="red">Fixed value="http://snomed.info/sct"</font> |  |  |  |  |  |  |  |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system <br/><font color="red">Fixed value="721981007"</font> |  |  |  |  |  |  |  |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system <br/><font color="red">Fixed value="Diagnostic studies report"</font> |  |  |  |  |  |  |  |
|  - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept<br/><font color="red">Where a SNOMED code does not meet the report name requirements a text alternative may be used</font> |  |  |  |  |  |  |  |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | The subject of the report - usually, but not always, the patient<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |  |  |  |  |  |  |  |
|   |  | Mandatory | [CareConnect-Patient-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1  "CareConnect-Patient-1 ") | <font color='red'>This MUST be to the Patient resource profiled as CareConnect-Patient-1 </font> |  |  |  |  |  |  |  |
|  - issued | 1..1 | Mandatory | [Instant](http://hl7.org/fhir/stu3/datatypes.html#instant "Instant") | DateTime this version was released <font color="red">The date and time on which the test report was issued by the performer to the requester.</font> |  |  |  |  |  |  |  |
|  - performer | 0..* | Required | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html "BackboneElement") | Participants in producing the report<br/><font color="red">Reference to the person and/or organisation that authored the test report.</font> |  |  |  |  |  |  |  |
|   - - actor | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Practitioner or Organization participant<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |  |  |  |  |  |  |  |
|   | 1..1 | Mandatory | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1 if a Practitioner is also recorded.'</font> |  |  |  |  |  |  |  |
|   | 1..1 | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font> |  |  |  |  |  |  |  |
|  - specimen | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimens this report is based on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |  |  |  |  |  |  |  |
|   | 0..* | Mandatory | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |  |  |  |  |  |  |  |
|  - result | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Observations - simple, or complex nested groups<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided <font color="red">Reference to the result(s) which are contained in the DiagnosticReport. This may contain references to standalone test results, test group headers (which then reference further results) or a mixture of both.</font>|  |  |  |  |  |  |  |
|   | 0..* | Mandatory | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observation-1'. Reference to the result(s)/result groups contained in the report</font> |  |  |  |  |  |  |  |
|  <a href="#" data-toggle="tooltip" title="Clinical Summary">- conclusion</a>| 0..1 | Required | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Clinical Interpretation of test results <br/><font color='red'>Human readable clinical summary relating to the test report. It is provided by the performing HCP.</font> |  |  |  |  |  |  |  |
|  <a href="#" data-toggle="tooltip" title="Finding Code">- codedDiagnosis</a>| 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Codes for the conclusion<br/>Binding (preferred): A SNOMED Coded finding for the test report. [CareConnect-Finding-Code](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-FindingCode-1 ) <br/><font color="red">A coded finding of the test report. Produced by the organisation that performed the tests.</font> |  |  |  |  |  |  |  |
|   - - coding | 0..* | Required | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |  |  |  |  |  |  |  |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |  |  |  |  |  |  |  |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |  |  |  |  |  |  |  |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |  |  |  |  |  |  |  |

## Examples ##

Basic example of a Diagnostic Report

{% include custom/fhir.codegrid.html
relfilepath="NP-Diagnostic-Report-Example-1.xml"
title="Diagnostic Report Example"
type="xml" %}
