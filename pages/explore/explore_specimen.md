---
title: Specimen
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_specimen.html
summary: "National Pathology FHIR Message Profiles"
---

## Mapping for Specimen ##

How to populate the Specimen instance to conform to the profiles below:

|**Level 1**|[Specimen Resource](http://hl7.org/fhir/stu3/specimen.html)|**Level 2**|[CareConnect-Specimen-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1/_history/1.1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_specimen_all.html#mapping-for-patient)**|

|  **Name** | **Card.** | **Business Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |  |  |  |  |  |  |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  Specimen | ​ |  |  | **Sample for analysis<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource** |  |  |  |  |  |  |  |  |  |  |
|  - id | 0..1 | Mandatory | [Id](http://hl7.org/fhir/stu3/datatypes.html#id "Id") | Logical id of this artifact<br/><font color="red">Must contain a UUID to identify the instance of a specimen</font> |  |  |  |  |  |  |  |  |  |  |
|  - meta | 0..1 | Mandatory | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta "Meta") | Metadata about the resource<br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |  |  |  |  |  |  |  |  |  |  |
|  - extension (fastingStatus) | 0..1 | Required | [Extension-CareConnect-FastingStatus-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-FastingStatus-1 "Extension-CareConnect-FastingStatus-1") | Fasting Status<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/><font color="red">Details of the fasting status of the patient at time of specimen collection</font> |  |  |  |  |  |  |  |  |  |  |
|  - identifier | 0..1 | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier "Identifier") | External Identifier<br/><font color="red">A business level identifier for the specimen supplied by the collecting/requesting organisation. eg. GP Practice</font> |  |  |  |  |  |  |  |  |  |  |
|  - accessionIdentifier | 0..1 | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier "Identifier") | Identifier assigned by the lab<br/><font color="red">A business level identifier for the specimen supplied by the performing organisation. eg. Lab performing the test.</font> |  |  |  |  |  |  |  |  |  |  |
|  - status | 0..1 | Required | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | available : unavailable : unsatisfactory : entered-in-error<br/>Binding (required): Codes providing the status/availability of a specimen. (http://hl7.org/fhir/stu3/valueset-specimen-status.html ) |  |  |  |  |  |  |  |  |  |  |
|  - type | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Kind of material that forms the specimen<br/>Binding (required): The type of the specimen. ( https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-SpecimenType-1 ) |  |  |  |  |  |  |  |  |  |  |
|  - - coding | 0..* | Required | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |  |  |  |  |  |  |  |  |  |  |
|  - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |  |  |  |  |  |  |  |  |  |  |
|  - - - code | 1..1 | Required | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system<br/><font color="red">Code MUST be from: <br/>(<105590001 :Substance (substance):(in which case method and site should also be populated)OR <br/><49755003 :Morphologically abnormal structure (morphologic abnormality):OR <br/>< 260787004 :Physical object (physical object))</font> |  |  |  |  |  |  |  |  |  |  |
|  - - - display | 1..1 | Required | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Representation defined by the system<br/><font color="red">MUST contain a SNOMED CT display name that matches to its equivalent SNOMED CT code</font> |  |  |  |  |  |  |  |  |  |  |
|  - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept |  |  |  |  |  |  |  |  |  |  |
|  - subject | 1..1 | Mandatory | Reference | Where the specimen came from. This may be from the patient(s) or from the environment or a device<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |  |  |  |  |  |  |  |  |  |  |
|   |  | Mandatory | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | <font color="red">This MUST be to the patient resource profiled as CareConnect-Patient-1</font> |  |  |  |  |  |  |  |  |  |  |
|  - receivedTime | 0..1 | Required | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime "dateTime") | The time when specimen was received for processing<br/><font color="red">The date and time on which the specimen was received for processing.</font> |  |  |  |  |  |  |  |  |  |  |
|  - collection | 0..1 | Mandatory | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html "BackboneElement") | Collection details |  |  |  |  |  |  |  |  |  |  |
|  - - collected[x] | 0..1 | Required | dateTime | Collection time<br/><font color="red">The date and time on which the specimen was collected.</font> |  |  |  |  |  |  |  |  |  |  |
|  - - quantity | 0..1 | Required | Quantity ( SimpleQuantity ) | The quantity of specimen collected<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity |  |  |  |  |  |  |  |  |  |  |
|  - - - value | 0..1 | Required | [Decimal](http://hl7.org/fhir/stu3/datatypes.html#decimal "Decimal") | Numerical value (with implicit precision)<br/><font color="red">Collected Specimen Quantity</font><br/> |  |  |  |  |  |  |  |  |  |  |
|  - - - unit | 0..1 | Required | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Unit representation<br/><font color="red">Collected Specimen Quantity Unit of Measure Text</font> |  |  |  |  |  |  |  |  |  |  |
|  - - - bodySite | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept "CodeableConcept") | Anatomical collection site<br/>Binding (required): Codes describing anatomical locations. May include laterality. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-SpecimenBodySite-1 ) |  |  |  |  |  |  |  |  |  |  |
|  - - - - coding | 0..* | Optional | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding "Coding") | Code defined by a terminology system |  |  |  |  |  |  |  |  |  |  |
|  - - - - - system | 1..1 | Required | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |  |  |  |  |  |  |  |  |  |  |
|  - - - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Symbol in syntax defined by the system<br/><font color="red">MUST be code from: < 442083009 : Anatomical or acquired body structure<br/>OR < 49755003 : Morphologically abnormal structure</font> |  |  |  |  |  |  |  |  |  |  |
|  - - - - - display | 1..1 | Mandatory | String | Representation defined by the system<br/><font color="red">MUST contain a SNOMED CT display name that matches to its equivalent SNOMED CT code</font> |  |  |  |  |  |  |  |  |  |  |
|  - - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Plain text representation of the concept |  |  |  |  |  |  |  |  |  |  |
|  - note | 0..1 | Optional | Annotation | Comments<br/><font color="red">Notes/comments relating to the specimen taken by the collection and/or performing organisation or HCP.</font> |  |  |  |  |  |  |  |  |  |  |
|  author[x] | 0..1 | Optional | String | Individual responsible for the annotation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |  |  |  |  |  |  |  |  |  |  |
|   |  | Required | Reference |  |  |  |  |  |  |  |  |  |  |  |
|   |  | Required | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color="red">This MUST be to the Practitioner resource profiled as CareConnect-Practitioner-1</font> |  |  |  |  |  |  |  |  |  |  |
|  time | 0..1 | Required | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime "dateTime") | When the annotation was made |  |  |  |  |  |  |  |  |  |  |
|  text | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | The annotation - text content |  |  |  |  |  |  |  |  |  |  |