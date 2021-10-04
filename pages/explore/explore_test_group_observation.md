---
title: Test Group
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_test_group_observation.html
summary: "National Pathology FHIR Message Profiles"
---

## Test Group Overview ##

Contains data on a group of test results. In this case a group is considered any group of tests that have been defined as a group by the performing organisation. For example - Full Blood Count. The group may be a standard group defined nationally, a locally defined group or a non standard group of tests. It is populated by the performing organisation.
In the way we have defined test group it is a synonym for test battery, panel or profile (in a testing sense not FHIR).


## Mapping for Observation ##

How to populate the Observation instance to conform to the profiles below:

|**Level 1**|[Observation Resource](http://hl7.org/fhir/stu3/observation.html)|**Level 2**|[CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_observation_all.html#mapping-for-DiagnosticReport)**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  Observation | ​ |  |  | **Measurements and simple assertions<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (obs-7): If code is the same as a component code then the value element associated with the code SHALL NOT be present<br/>Constraint (obs-6): dataAbsentReason SHALL only be present if Observation.value[x] is not present** |
|  - id | 0..1 | Required | Id | Logical id of this artifact<br/><font color="red">MUST contain a unique identifier to identify the instance of an observation</font> |
|  - meta | 0..1 | Mandatory | Meta | Metadata about the resource<br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observtion-1'</font> |
|  - identifier | 0..* | Required | Identifier | Business Identifier for observation<br/><font color="red">A business level identifier for the test group. Produced by the performing organisation</font> |
|  - - system | 1..1 | Mandatory | Uri | The namespace for the identifier value<br/><font color="red">MUST contain a local identifier naming system</font> |
|  - - value | 1..1 | Mandatory | String | The value that is unique<br/><font color="red">MUST contain a unique identifier</font> |
|  - status | 1..1 | Mandatory | Code | registered : preliminary : final : amended +<br/>Binding (required): Codes providing the status of an observation. [ObservationStatus](http://hl7.org/fhir/stu3/valueset-observation-status.html) |
|  - code | 1..1 | Mandatory | CodeableConcept | Type of observation (code / type)<br/>Binding (example): Codes identifying names of simple observations. ( http://hl7.org/fhir/stu3/valueset-observation-codes.html )<br/><font color="red">The clinical code for the group of tests.</font> |
|  - - coding | 0..* | Mandatory | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Mandatory | Coding | Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK coding system describing a type of observation [CareConnect-ObservationType-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationType-1) |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system<br/><font color="red">A code that identifies the test result.</font> |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system<br/><font color="red"?SNOMED CT display name. This will be the name of the grpup test.</font> |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 0..1 | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who and/or what this is about<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Optional | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | <font color='red'>This MUST be to the Patient resource profiled as CareConnect-Patient-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - performer | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who is responsible for the observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided <font color="red">Reference to the resource for the Organization that carried out the tests. A practitioner resource may also be referenced here but only where an organization is reference is provided.</font>|
|   |  | Required | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>This MUST be to the Organization resource profiled as CareConnect-Organization-1 </font> |
|   |  | Required | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>This MUST be to the Practitioner resource profiled as CareConnect-Practitioner-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Organization or Practitioner resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - comment | 0..1 | Required | String | Comments about result<br/><font color="red">Notes that relate to the test group header that were written by the performing organization.</font> |
|  - specimen | 0..1 | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimen used for this observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Specimen resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - related | 0..* | Required | BackboneElement | Resource related to this observation<br/><font color="red">References to the results that make up this group.  The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observation-1'</font><br/> |
|  - - target | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Resource that is related to this one<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") |  |
|  - - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL<br/><font color="red">a reference to the Observtionresource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font><br/> |