---
title: Test Request Summary
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_procedure_request_all.html
summary: "National Pathology FHIR Message Profiles"
---

## Test Request Summary Overview for a Haemotology or Chemical Biology Test ##

Information from the original request that is returned with the test report.
This has two purposes. 
- 1.) To assist in linking the report to the original request; 
- 2.) Give context to the test report where the receiving HCP is different to the requesting HCP and does not have access to the original request.

## Mapping for Procedure Request ##

The test request summary is used to capture the details about the test that has been requested by a healthcare organisation 

How to populate the Procedure Request instance to conform to the profiles below:

|**Level 1**|[ProcedureRequest Resource](http://hl7.org/fhir/stu3/procedurerequest.html)|**Level 2**|[CareConnect-ProcedureRequest-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1/_history/1.1)|**Level 3**|None|

|**[View Used FHIR Elements](explore_procedure_request.html)**|    |**View All FHIR Elements**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| --- | --- | --- | --- | --- |
|  ProcedureRequest | ​ |  |  | **A request for a procedure or diagnostic to be performed<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |
|  - id | 0..1 | Mandatory | Id | Logical id of this artifact |
|  - meta | 0..1 | Mandatory | Meta | Metadata about the resource |
|  - implicitRules | 0..1 | Not Used | Uri | A set of rules under which this content was created |
|  - language | 0..1 | Not Used | Code | Language of the resource content<br/>Binding (extensible): A human language. [Common Languages](http://hl7.org/fhir/stu3/valueset-languages.html) |
|  - text | 0..1 | Not Used | Narrative | Text summary of the resource, for human interpretation |
|  - contained | 0..* | Not Used | Resource | Contained, inline Resources |
|  - modifierExtension | 0..* | Not Used | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open |
|  - identifier | 1..1 | Mandatory | Identifier | Identifiers assigned to this order |
|  - - use | 0..1 | Not Used | Code | usual : official : temp : secondary (If known)<br/>Binding (required): Identifies the purpose for this identifier, if known. [IdentifierUse](http://hl7.org/fhir/stu3/valueset-identifier-use.html) |
|  - - type | 0..1 | Not Used | CodeableConcept | Description of identifier<br/>Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. [Identifier Type Codes](http://hl7.org/fhir/stu3/valueset-identifier-type.html) |
|  - - - coding | 0..* | Not Used | Coding | Code defined by a terminology system |
|  - - - - system | 0..1 | Not Used | Uri | Identity of the terminology system |
|  - - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - - code | 0..1 | Not Used | Code | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Not Used | String | Representation defined by the system |
|  - - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - - text | 0..1 | Not Used | String | Plain text representation of the concept |
|  - - system | 0..1 | Not Used | Uri | The namespace for the identifier value |
|  - - value | 0..1 | Not Used | String | The value that is unique |
|  - - period | 0..1 | Not Used | Period | Time period when id is/was valid for use<br/>Constraint (per-1): If present, start SHALL have a lower value than end |
|  - - - start | 0..1 | Not Used | dateTime | Starting time with inclusive boundary |
|  - - - end | 0..1 | Not Used | dateTime | End time with inclusive boundary, if not ongoing |
|  - - assigner | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Organization that issued id (may be just text)<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Organization](http://hl7.org/fhir/stu3/StructureDefinition/Organization "Organization") |  |
|  - - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - definition | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Protocol or definition<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [ActivityDefinition](http://hl7.org/fhir/stu3/StructureDefinition/ActivityDefinition "ActivityDefinition") |  |
|   |  | Not Used | [PlanDefinition](http://hl7.org/fhir/stu3/StructureDefinition/PlanDefinition "PlanDefinition") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - basedOn | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | What request fulfills<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Resource](http://hl7.org/fhir/stu3/StructureDefinition/Resource "Resource") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - - replaces | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | What request replaces<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Resource](http://hl7.org/fhir/stu3/StructureDefinition/Resource "Resource") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - requisition | 0..1 | Not Used | Identifier | Composite Request ID |
|  - - use | 0..1 | Not Used | Code | usual : official : temp : secondary (If known)<br/>Binding (required): Identifies the purpose for this identifier, if known. [IdentifierUse](http://hl7.org/fhir/stu3/valueset-identifier-use.html) |
|  - - type | 0..1 | Not Used | CodeableConcept | Description of identifier<br/>Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. [Identifier Type Codes](http://hl7.org/fhir/stu3/valueset-identifier-type.html) |
|  - - - coding | 0..* | Not Used | Coding | Code defined by a terminology system |
|  - - - - system | 0..1 | Not Used | Uri | Identity of the terminology system |
|  - - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - - code | 0..1 | Not Used | Code | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Not Used | String | Representation defined by the system |
|  - - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - - text | 0..1 | Not Used | String | Plain text representation of the concept |
|  - - system | 0..1 | Not Used | Uri | The namespace for the identifier value |
|  - - value | 0..1 | Not Used | String | The value that is unique |
|  - - period | 0..1 | Not Used | Period | Time period when id is/was valid for use<br/>Constraint (per-1): If present, start SHALL have a lower value than end |
|  - - - start | 0..1 | Not Used | dateTime | Starting time with inclusive boundary |
|  - - - end | 0..1 | Not Used | dateTime | End time with inclusive boundary, if not ongoing |
|  - - assigner | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Organization that issued id (may be just text)<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Organization](http://hl7.org/fhir/stu3/StructureDefinition/Organization "Organization") |  |
|  - - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - status | 1..1 | Mandatory | Code | draft : active : suspended : completed : entered-in-error : cancelled<br/>Binding (required): The status of a procedure or diagnostic order. [RequestStatus](http://hl7.org/fhir/stu3/valueset-request-status.html)<br/><font color="red">MUST use Active</font> |
|  - intent | 1..1 | Not Used | Code |  |
|  - priority | 0..1 | Not Used | Code | routine : urgent : asap : stat<br/>Binding (required): Identifies the level of importance to be assigned to actioning the request [RequestPriority](http://hl7.org/fhir/stu3/valueset-request-priority.html) |
|  - doNotPerform | 0..1 | Not Used | Boolean | True if procedure should not be performed<br/>Default Value: false |
|  - category | 0..* | Not Used | CodeableConcept | Classification of procedure<br/>Binding (example): Classification of the procedure [Procedure Category Codes (SNOMED CT)](http://hl7.org/fhir/stu3/valueset-procedure-category.html) |
|  - - coding | 0..* | Not Used | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Not Used | Uri | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - code | 0..1 | Not Used | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Not Used | String | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - text | 0..1 | Not Used | String | Plain text representation of the concept |
|  - code | 1..1 | Mandatory | CodeableConcept | What is being requested/ordered<br/>Binding (example): Codes for tests/services that can be performed by procedure or diagnostic services. For laboratory, LOINC is (preferred)[http://hl7.org/fhir/STU3/terminologies.html#preferred] and a valueset using LOINC Order codes is available [here](valueset-diagnostic-requests.html). [Procedure Codes (SNOMED CT)](http://hl7.org/fhir/stu3/valueset-procedure-code.html)<br/><font color="red">Requested Tests</font> |
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual the service is ordered for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Patient-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1  "CareConnect-Patient-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ProcedueRequest-1'</font> |
|   |  | Not Used | [Group](http://hl7.org/fhir/stu3/StructureDefinition/Group "Group") |  |
|   |  | Not Used | [Location](http://hl7.org/fhir/stu3/StructureDefinition/Location "Location") |  |
|   |  | Not Used | [Device](http://hl7.org/fhir/stu3/StructureDefinition/Device "Device") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - context | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Encounter or Episode during which request was created<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Encounter](http://hl7.org/fhir/stu3/StructureDefinition/Encounter "Encounter") |  |
|   |  | Not Used | [EpisodeOfCare](http://hl7.org/fhir/stu3/StructureDefinition/EpisodeOfCare "EpisodeOfCare") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - occurrence[x] | 0..1 | Not Used | dateTime | When procedure should occur |
|   |  | Not Used | Period |  |
|   |  | Not Used | [Timing](http://hl7.org/fhir/stu3/datatypes.html#timing "Timing") |  |
|  - asNeeded[x] | 0..1 | Not Used | Boolean | Preconditions for procedure or diagnostic<br/>Binding (example): A coded concept identifying the pre-condition that should hold prior to performing a procedure. For example "pain", "on flare-up", etc. [SNOMED CT Medication As Needed Reason Codes](http://hl7.org/fhir/stu3/valueset-medication-as-needed-reason.html) |
|   |  | Not Used | CodeableConcept |  |
|  - authoredOn | 0..1 | Not Used | dateTime | Date request signed |
|  - requester | 0..1 | Mandatory | BackboneElement | Who/what is requesting procedure or diagnostic |
|  - - modifierExtension | 0..* | Not Used | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|  - - agent | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual making the request<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Device](http://hl7.org/fhir/stu3/StructureDefinition/Device "Device") |  |
|   |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font><br/><font color="Red">Requesting HCP</font> |
|   |  | Mandatory | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1'</font><br/><font color="Red">Requesting Organisation</font> |
|  - - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - - onBehalfOf | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Organization agent is acting for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Organization](http://hl7.org/fhir/stu3/StructureDefinition/Organization "Organization") |  |
|  - - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - performerType | 0..1 | Not Used | CodeableConcept | Performer role<br/>Binding (example): Indicates specific responsibility of an individual within the care team, such as "Primary physician", "Team coordinator", "Caregiver", etc. [Participant Roles](http://hl7.org/fhir/stu3/valueset-participant-role.html) |
|  - - coding | 0..* | Not Used | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Not Used | Uri | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - code | 0..1 | Not Used | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Not Used | String | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - text | 0..1 | Not Used | String | Plain text representation of the concept |
|  - performer | 0..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Requested perfomer<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Practitioner-1'</font><br/><font color="Red">Performing HCP</font> |
|   |  | Not Used | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Organization-1'</font><br/><font color="Red">Performing Organisation</font> |
|   |  | Not Used | [Patient](http://hl7.org/fhir/stu3/StructureDefinition/Patient "Patient") |  |
|   |  | Not Used | [Device](http://hl7.org/fhir/stu3/StructureDefinition/Device "Device") |  |
|   |  | Not Used | [RelatedPerson](http://hl7.org/fhir/stu3/StructureDefinition/RelatedPerson "RelatedPerson") |  |
|   |  | Not Used | [HealthcareService](http://hl7.org/fhir/stu3/StructureDefinition/HealthcareService "HealthcareService") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - reasonCode | 0..* | Required | CodeableConcept | Explanation/Justification for test<br/>Binding (example): Diagnosis or problem codes justifying the reason for requesting the procedure or diagnostic investigation. [Procedure Reason Codes](http://hl7.org/fhir/stu3/valueset-procedure-reason.html)<br/><font color="red">Request Raseon Code</font> |
|  - - coding | 0..* | Optional | Coding | Code defined by a terminology system |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - text | 0..1 | Required | String | Plain text representation of the concept<br/><font color="red">Request Information Text</font> |
|  - reasonReference | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Explanation/Justification for test<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Condition-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1  "CareConnect-Condition-1 ") | <font color="red">***Need to agree a description for this element. - Condition code***</font><br/> |
|   |  | Required | [CareConnect-Observation-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observationt-1  "CareConnect-Observation-1 ") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - supportingInfo | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Additional clinical information<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | <font color-"red">A set of pre-requisite information prior to the test taking place. This may be coded or human readable inforamtion</font> |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - specimen | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Procedure Samples<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Specimen](http://hl7.org/fhir/stu3/StructureDefinition/Specimen "Specimen") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |
|  - bodySite | 0..* | Not Used | CodeableConcept | Location on Body<br/>Binding (example): Codes describing anatomical locations. May include laterality. [SNOMED CT Body Structures](http://hl7.org/fhir/stu3/valueset-body-site.html) |
|  - - coding | 0..* | Not Used | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Not Used | Uri | Identity of the terminology system |
|  - - - version | 0..1 | Not Used | String | Version of the system - if relevant |
|  - - - code | 0..1 | Not Used | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Not Used | String | Representation defined by the system |
|  - - - userSelected | 0..1 | Not Used | Boolean | If this coding was chosen directly by the user |
|  - - text | 0..1 | Not Used | String | Plain text representation of the concept |
|  - note | 0..* | Not Used | Annotation | Comments |
|  - - author[x] | 0..1 | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Individual responsible for the annotation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Practitioner](http://hl7.org/fhir/stu3/StructureDefinition/Practitioner "Practitioner") |  |
|   |  | Not Used | [Patient](http://hl7.org/fhir/stu3/StructureDefinition/Patient "Patient") |  |
|   |  | Not Used | [RelatedPerson](http://hl7.org/fhir/stu3/StructureDefinition/RelatedPerson "RelatedPerson") |  |
|   |  | Not Used | String |  |
|  - - time | 0..1 | Not Used | dateTime | When the annotation was made |
|  - - text | 1..1 | Not Used | String | The annotation - text content |
|  - relevantHistory | 0..* | Not Used | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Request provenance<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Not Used | [Provenance](http://hl7.org/fhir/stu3/StructureDefinition/Provenance "Provenance") |  |
|  - - reference | 0..1 | Not Used | String | Literal reference, Relative, internal or absolute URL |
|  - - identifier | 0..1 | Not Used | Identifier | Logical reference, when literal reference is not known |
|  - - display | 0..1 | Not Used | String | Text alternative for the resource |


