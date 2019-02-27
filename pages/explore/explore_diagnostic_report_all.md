---
title: Test Report
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_diagnostic_report_all.html
summary: "National Pathology FHIR Message Profiles"
---

## The Test Report for a Haemotology or Chemical Biology Test ##

## Mapping for Diagnostic Report ##

How to populate the Specimen instance to conform to the profiles below:

|**Level 1**|[DiagnosticReport Resource](http://hl7.org/fhir/stu3/diagnosticreport.html)|**Level 2**|[CareConnect-DiagnosticReport-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1/_history/1.1)|**Level 3**|None|

|**[View Used FHIR Elements](explore_diagnosticreport.html)**|    |**View All FHIR Elements**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and Mapping for National Pathology Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  **DiagnosticReport** | ​ |  |  | **A Diagnostic report - a combination of request information, atomic results, images, interpretation, as well as formatted reports<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - id | 0..1 | Not Used | [Id](http://hl7.org/fhir/stu3/datatypes.html#id "Id") | Logical id of this artifact |
|  - meta | 0..1 | Not Used | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta "Meta") | Metadata about the resource |
|  - implicitRules | 0..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | A set of rules under which this content was created |
|  - language | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Language of the resource content<br/>Binding (extensible): A human language. [Common Languages](http://hl7.org/fhir/stu3/valueset-languages.html) |
|  - text | 0..1 | Not Used | [Narrative](http://hl7.org/fhir/stu3/narrative.html#Narrative "Narrative") | Text summary of the resource, for human interpretation |
|  - contained | 0..* | Not Used | [Resource](http://hl7.org/fhir/stu3/resource.html "Resource") | Contained, inline Resources |
|  - modifierExtension | 0..* | Not Used | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension "Extension") | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open |
|  - identifier | 0..* | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier "Identifier") | Business identifier for report |
|  - - use | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | usual : official : temp : secondary (If known)<br/> Binding (required): Identifies the purpose for this identifier, if known. [IdentifierUse](http://hl7.org/fhir/stu3/valueset-identifier-use.html) |
|  - - type | 0..1 | Not Used | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Description of identifier<br/> Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. [Identifier Type Codes](http://hl7.org/fhir/stu3/valueset-identifier-type.html) |
|  - - - coding | 0..* | Not Used | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |
|  - - - - system | 0..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system |
|  - - - - version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Version of the system - if relevant |
|  - - - - code | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |
|  - - - - userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean "Boolean") | If this coding was chosen directly by the user |
|  - - - text | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept |
|  - - system | 1..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | The namespace for the identifier value |
|  - - value | 1..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | The value that is unique |
|  - - period | 0..1 | Not Used | [Period](http://hl7.org/fhir/stu3/datatypes.html#period "Period") | Time period when id is/was valid for use<br/> Constraint (per-1): If present, start SHALL have a lower value than end |
|  - - - start | 0..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime "dateTime") | Starting time with inclusive boundary |
|  - - - end | 0..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime "dateTime") | End time with inclusive boundary, if not ongoing |
|  - - assigner | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Organization that issued id (may be just text)<br/> Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  - basedOn | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | What was requested<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-ProcedureRequest-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1  "CareConnect-ProcedureRequest-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|  - status | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | registered : partial : preliminary : final +<br/>Binding (required): The status of the diagnostic report as a whole. [Diagnostic-Report-Status]( http://hl7.org/fhir/stu3/valueset-diagnostic-report-status.html ) |
|  - category | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Service category<br/>Binding (preferred): Codes for diagnostic service sections. [CareConnect-ClinicalDisciplines](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ClinicalDisciplines-1 )<br/><font color='red'>Clinical Discipline</font> |
|  - code | 1..1 | Mandatory | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Name/Code for this diagnostic report<br/>Binding (preferred): Codes that describe Diagnostic Reports. [Report Codes]( http://hl7.org/fhir/stu3/valueset-report-codes.html )<br/><font color='red'>Test Report Name</font> |
|  - - coding | 0..* | Not Used | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Version of the system - if relevant |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean "Boolean") | If this coding was chosen directly by the user |
|  - - text | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | The subject of the report - usually, but not always, the patient<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Patient-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1  "CareConnect-Patient-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|   |  | Not Used | [Group](http://hl7.org/fhir/stu3/group.html "Group") |  |
|   |  | Not Used | [Device](http://hl7.org/fhir/stu3/device.html "Device") |  |
|   |  | Not Used | [CareConnect-Location-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Location-1  "CareConnect-Location-1 ") |  |
|  - context | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Health care event when test ordered<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..1 | Not Used | [CareConnect-Encounter-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Encounter-1 "CareConnect-Encounter-1 ") |  |
|   | 0..1 | Not Used | [EpisodeOfCare ](http://hl7.org/fhir/stu3/episodeofcare.html  "EpisodeOfCare ") |  |
|   -effective[x] | 1..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#dateTime "dateTime") | Clinically relevant time/time-period for report |
|   | 1..1 | Not Used | [Period](http://hl7.org/fhir/stu3/datatypes.html#Period "Period") |  |
|  - - issued | 1..1 | Mandatory | [Instant](http://hl7.org/fhir/stu3/datatypes.html#instant "Instant") | DateTime this version was released <font color="red">The date and time on which the test report was issued by the performer to the requester.</font> |
|  - performer | 0..* | Optional | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html "BackboneElement") | Participants in producing the report |
|   - - modifierExtension | 0..* | Not Used | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|  - - role | 0..1 | Not Used | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Type of performer<br/>Binding (example): Indicate a role of diagnostic report performer [Performer Role]( http://hl7.org/fhir/stu3/valueset-performer-role.html ) |
|   - - actor | 1..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Practitioner or Organization participant<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 1..1 | Mandatory | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1 if a Practitioner is also recorded.'</font> |
|   | 1..1 | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font> |
|  - specimen | 0..* | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimens this report is based on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..* | Optional | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |
|  - result | 0..* | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Observations - simple, or complex nested groups<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..* | Optional | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observation-1'</font> |
|  - imagingStudy | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Reference to full details of imaging associated with the diagnostic report<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | 0..* | Not Used | [ImagingStudy](http://hl7.org/fhir/stu3/imagingstudy.html "ImagingStudy") |  |
|   | 0..* | Not Used | [ImagingManifest](http://hl7.org/fhir/stu3/ImagingManifest.html "ImagingManifest") |  |
|   - image | 0..* | Not Used | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html "BackboneElement") | Key images associated with this report |
|  - - modifierExtension | 0..* | Not Used | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|  - - comment | 0..1 | Not Used | String | Comment about the image (e.g. explanation) |
|  - - link | 1..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Reference to the image source<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Media](http://hl7.org/fhir/stu3/media.html "Media") |  |
|  - conclusion | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Clinical Interpretation of test results <br/><font color='red'>Human readable clinical summary relating to the test report.</font> |
|  - codedDiagnosis | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Codes for the conclusion<br/>Binding (preferred): A SNOMED Coded finding for the test report. [CareConnect-Finding-Code](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-FindingCode-1 ) <font color="red">Finding Code</font> |
|   - - coding | 0..* | Required | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Version of the system - if relevant |
|  - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean "Boolean") | If this coding was chosen directly by the user |
|  - - - text | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept |
|  - presentedForm | 0..* | Not Used | [Attachment](http://hl7.org/fhir/stu3/datatypes.html#attachment "Attachment") | Entire report as issued<br/>Constraint (att-1): It the Attachment has data, it SHALL have a contentType |
|  - - contentType | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Mime type of the content, with charset etc.<br/>Binding (required): The mime type of an attachment. Any valid mime type is allowed. ( http://www.rfc-editor.org/bcp/bcp13.txt ) |
|  - - language | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Human language of the content (BCP-47)<br/>Binding (extensible): A human language. ( http://hl7.org/fhir/stu3/valueset-languages.html ) |
|  - - data | 0..1 | Not Used | [base64Binary](http://hl7.org/fhir/stu3/datatypes.html#base64binary "base64Binary") | Data inline, base64ed |
|  - - url | 0..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Uri where the data can be found |
|  - - size | 0..1 | Not Used | [unsignedInt](http://hl7.org/fhir/stu3/datatypes.html#unsignedint "unsignedInt") | Number of bytes of content (if url provided) |
|  - - hash | 0..1 | Not Used | [base64Binary](http://hl7.org/fhir/stu3/datatypes.html#base64binary "base64Binary") | Hash of the data (sha-1, base64ed) |
|  - - title | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Label to display in place of the data |
|  - - creation | 0..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime "dateTime") | Date attachment was first created |
