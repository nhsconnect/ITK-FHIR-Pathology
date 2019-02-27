---
title: Test Report Filing
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_test_filing_observation.html
summary: "National Pathology FHIR Message Profiles"
---


|  Name | Card. | Conformance | Type | **Description, Constraints and Mapping for XXX Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  DiagnosticReport | ​ |  |  | **A Diagnostic report - a combination of request information, atomic results, images, interpretation, as well as formatted reports<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - id | 0..1 | Select | Id | **Logical id of this artifact** |
|  - meta | 0..1 | Select | Meta | **Metadata about the resource** |
|  - implicitRules | 0..1 | Select | Uri | **A set of rules under which this content was created** |
|  - language | 0..1 | Select | Code | **Language of the resource content<br/>Binding (extensible): A human language. [Common Languages](http://hl7.org/fhir/stu3/valueset-languages.html)** |
|  - text | 0..1 | Select | Narrative | **Text summary of the resource, for human interpretation** |
|  - contained | 0..* | Select | Resource | **Contained, inline Resources** |
|  - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open** |
|  - identifier | 0..* | Select | Identifier | **Business identifier for report** |
|  - basedOn | 0..* | Select | Reference | **What was requested<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | CareConnect-ProcedureRequest-1 | **** |
|  - status | 1..1 | Select | Code | **registered : partial : preliminary : final +<br/>Binding (required): The status of the diagnostic report as a whole. [Diagnostic-Report-Status]( http://hl7.org/fhir/stu3/valueset-diagnostic-report-status.html )** |
|  - category | 0..1 | Select | CodeableConcept | **Service category<br/>Binding (preferred): Codes for diagnostic service sections. [CareConnect-ClinicalDisciplines](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ClinicalDisciplines-1 )** |
|  - code | 1..1 | Select | CodeableConcept | **Name/Code for this diagnostic report<br/>Binding (preferred): Codes that describe Diagnostic Reports. [Report Codes]( http://hl7.org/fhir/stu3/valueset-report-codes.html )** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - subject | 1..1 | Select | Reference | **The subject of the report - usually, but not always, the patient<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | Group | **** |
|   |  | Select | Device | **** |
|   |  | Select | Location  | **** |
|   |  | Select | CareConnect-Patient-1 | **** |
|  - context | 0..1 | Select | Reference | **Health care event when test ordered<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | CareConnect-Encounter-1 | **** |
|   |  | Select | EpisodeOfCare | **** |
|   -effective[x] | 1..1 | Select | dateTime | Period | **Clinically relevant time/time-period for report** |
|  - - issued | 0..1 | Select | Instant | **DateTime this version was released** |
|  - performer | 0..* | Select | BackboneElement | **Participants in producing the report** |
|   - - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both** |
|  - - role | 0..1 | Select | CodeableConcept | **Type of performer<br/>Binding (example): Indicate a role of diagnostic report performer [Performer Role]( http://hl7.org/fhir/stu3/valueset-performer-role.html )** |
|   - - actor | 1..1 | Select | Reference | **Practitioner or Organization participant<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | CareConnect-Organization-1 | **** |
|   |  | Select | CareConnect-Practitioner-1 | **** |
|  - specimen | 0..* | Select | Reference | **Specimens this report is based on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | CareConnect-Specimen-1 | **** |
|  - result | 0..* | Select | Reference | **Observations - simple, or complex nested groups<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select |  CareConnect-Observation-1 | **** |
|  - imagingStudy | 0..* | Select | Reference | **Reference to full details of imaging associated with the diagnostic report<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | ImagingStudy | **** |
|   |  | Select | ImagingManifest | **** |
|   - image | 0..* | Select | BackboneElement | **Key images associated with this report** |
|  - - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both** |
|  - - comment | 0..1 | Select | String | **Comment about the image (e.g. explanation)** |
|  - - link | 1..1 | Select | Reference | **Reference to the image source<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | Media | **** |
|   |  | Select | Media | **** |
|  - conclusion | 0..1 | Select | String | **Clinical Interpretation of test results** |
|  - codedDiagnosis | 0..1 | Select | CodeableConcept | **Codes for the conclusion<br/>Binding (required): A SNOMED Coded finding for the test report. [CareConnect-Finding-Code](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-FindingCode-1 )** |
|   - - coding | 0..* | Select | Coding | **Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open** |
|  - - coding (snomedCT) | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - presentedForm | 0..* | Select | Attachment | **Entire report as issued<br/>Constraint (att-1): It the Attachment has data, it SHALL have a contentType** |
