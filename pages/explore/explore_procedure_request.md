---
title: Test Request Summary
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_procedure_request.html
summary: "National Pathology FHIR Message Profiles"
---

## The Test Request Summary for a Haemotology or Chemical Biology Test ##

## Mapping for Procedure Request ##

How to populate the Procedure Request instance to conform to the profiles below:

|**Level 1**|[DiagnosticReport Resource](http://hl7.org/fhir/stu3/procedurerequest.html)|**Level 2**|[CareConnect-ProcedureRequest-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1/_history/1.1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_procedure_request_all.html)**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| --- | --- | --- | --- | --- |
|  ProcedureRequest | ​ |  |  | **A request for a procedure or diagnostic to be performed<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - id | 0..1 | Mandatory | Id | Logical id of this artifact |
|  - meta | 0..1 | Mandatory | Meta | Metadata about the resource |
|  - identifier | 1..1 | Mandatory | Identifier | Identifiers assigned to this order |
|  - status | 1..1 | Mandatory | Code | draft : active : suspended : completed : entered-in-error : cancelled<br/>Binding (required): The status of a procedure or diagnostic order. [RequestStatus](http://hl7.org/fhir/stu3/valueset-request-status.html) <font color="red">MUST use Active</font>|
|  - code | 1..1 | Mandatory | CodeableConcept | What is being requested/ordered<br/>Binding (example): Codes for tests/services that can be performed by procedure or diagnostic services. For laboratory, LOINC is (preferred)[http://hl7.org/fhir/STU3/terminologies.html#preferred] and a valueset using LOINC Order codes is available [here](valueset-diagnostic-requests.html). [Procedure Codes (SNOMED CT)](http://hl7.org/fhir/stu3/valueset-procedure-code.html)<br/><font color="red">Requested Tests</font> |
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual the service is ordered for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Patient-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1  "CareConnect-Patient-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|  - requester | 0..1 | Mandatory | BackboneElement | Who/what is requesting procedure or diagnostic |
|  - - agent | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual making the request<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font><br/><font color="Red">Requesting HCP</font> |
|   |  | Mandatory | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1'</font><br/><font color="Red">Requesting Organisation</font> |
|  - performer | 0..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Requested perfomer<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font><br/><font color="Red">Performing HCP</font> |
|  - reasonCode | 0..* | Required | CodeableConcept | Explanation/Justification for test<br/>Binding (example): Diagnosis or problem codes justifying the reason for requesting the procedure or diagnostic investigation. [Procedure Reason Codes](http://hl7.org/fhir/stu3/valueset-procedure-reason.html)<br/><font color="red">Request Raseon Code</font> |
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Required | String | Plain text representation of the concept<br/><font color="red">Request Information Text</font> |
|  - reasonReference | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Explanation/Justification for test<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Condition-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1  "CareConnect-Condition-1 ") | <font color="red">***Need to agree a description for this element. - Condition code***</font><br/> |
|   |  | Required | [CareConnect-Observation-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observationt-1  "CareConnect-Observation-1 ") |  |
|  - supportingInfo | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Additional clinical information<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | <font color-"red">A set of pre-requisite information prior to the test taking place. This may be coded or human readable inforamtion</font> |