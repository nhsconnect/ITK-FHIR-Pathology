---
title: Test Request Summary
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_procedure_request.html
summary: "National Pathology FHIR Message Profiles"
---

## Test Request Summary Overview for a Haemotology or Chemical Biology Test ##

Information from the original request that is returned with the test report.
This has two purposes. 
- 1) To assist in linking the report to the original request; 
- 2) Give context to the test report where the receiving HCP is different to the requesting HCP and does not have access to the original request.

## Mapping for Procedure Request ##

How to populate the Procedure Request instance to conform to the profiles below:

|**Level 1**|[Procedure Request Resource](http://hl7.org/fhir/stu3/procedurerequest.html)|**Level 2**|[CareConnect-ProcedureRequest-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)|**Level 3**|None|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| --- | --- | --- | --- | --- |
|  ProcedureRequest | ​ |  |  | **A request for a procedure or diagnostic to be performed<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - id | 0..1 | Required | Id | Logical id of this artifact<br/><font color="red">Must contain a UUID to identify the instance of a procedureRequest</font> |
|  - meta | 0..1 | Required | Meta | Metadata about the resource<br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1'</font> |
|  - identifier | 0..* | Optional | Identifier | Identifiers assigned to this order |
|  - - system | 1..1 | Mandatory | Uri | The namespace for the identifier value<br/><font color="red">MUST contain the value 'https://tools.ietf.org/html/rfc4122'.</font> |
|  - - value | 1..1 | Mandatory | String | The value that is unique<br/><font color="red">MUST contain a UUID</font> |
|  - status | 1..1 | Mandatory | Code | draft : active : suspended : completed : entered-in-error : cancelled<br/>Binding (required): The status of a procedure or diagnostic order. [RequestStatus](http://hl7.org/fhir/stu3/valueset-request-status.html)<br/><font color="red">MUST contain the value 'active'.</font> |
|  - intent | 1..1 | Mandatory | Code | proposal : plan : order +<br/>Binding (required): The kind of procedure or diagnostic request [RequestIntent](http://hl7.org/fhir/stu3/valueset-request-intent.html)<br/><font color="red">MUST contain the value 'order'.</font> |
|  - code | 1..1 | Required | CodeableConcept | What is being requested/ordered<br/>Binding (example): Codes identifying names of simple observations. <font color="Red">The tests requested by the requesting HCP.</font>|
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual the service is ordered for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | <font color="red">This MUST be to the Organization resource profiled as CareConnect-Patient-1</font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - requester | 0..1 | Mandatory | BackboneElement | Who/what is requesting procedure or diagnostic |
|  - - agent | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual making the request<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [Practitioner](http://hl7.org/fhir/stu3/StructureDefinition/Practitioner "Practitioner") | <font color="red">Requesting Healthcare Professional</font> |
|  - - - reference | 1..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - performer | 0..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Requested perfomer<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color="red">This MUST be to the Organization resource profiled as CareConnect-Practitioner-1</font> |
|   |  | Mandatory | [CareConnect-Organisation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organisation-1 "CareConnect-Organisation-1") | <font color="red">This MUST be to the Organization resource profiled as CareConnect-Organisation-1</font> |
|  - - reference | 1..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - reasonCode | 0..* | Required | CodeableConcept | Explanation/Justification for test<br/>Binding (example): Diagnosis or problem codes justifying the reason for requesting the procedure or diagnostic investigation. [Procedure Reason Codes](http://hl7.org/fhir/stu3/valueset-procedure-reason.html)<br/><font color="red">A structured and coded explanation from the requesting HCP containing an explanation on why the test has been requested and any contextual information they considered relevant. Use FHIR default value set</font><br/> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept<br/><font color="red">A human readable explanation from the requesting HCP containing an explanation on why the test has been requested and any contextual information they considered relevant.</font> |
|  - reasonReference | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Explanation/Justification for test<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided. <font color="Red">The clinical code of conditions the patient has that are supplied by the requesting HCP due to their relevance to the test request.</font> |
|   |  | Required | [CareConnect-Condition-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1 "CareConnect-Condition-1") | <font color="red">This MUST be to the Organization resource profiled as CareConnect-Condition-1</font> |
|  - - reference | 0..1 | Required | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|- note	|0..*|	Required	|Annotation	|Comments <font color="red">Clinical information provided by the requesting HCP/Organisation</font> |
|- - text|	1..1	|Required|	String	|The annotation - text content <font color="red">E.G. Patient always feels tired</font>|

## Test Request Summary Example ##

<script src="https://gist.github.com/IOPS-DEV/992fa4b3ac83b375286e75834082602a.js"></script>
