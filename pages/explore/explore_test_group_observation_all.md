---
title: Test Group
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_test_group_observation_all.html
summary: "National Pathology FHIR Message Profiles"
---

## Mapping for Observation ##

How to populate the Observation instance to conform to the profiles below:

|**Level 1**|[Observation Resource](http://hl7.org/fhir/stu3/observation.html)|**Level 2**|[CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1/_history/1.1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_observation_all.html#mapping-for-DiagnosticReport)**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for XXX Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  Observation | ​ |  |  | **Measurements and simple assertions<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (obs-7): If code is the same as a component code then the value element associated with the code SHALL NOT be present<br/>Constraint (obs-6): dataAbsentReason SHALL only be present if Observation.value[x] is not present** |
|  - id | 0..1 | Select | Id | **Logical id of this artifact** |
|  - meta | 0..1 | Select | Meta | **Metadata about the resource** |
|  - implicitRules | 0..1 | Select | Uri | **A set of rules under which this content was created** |
|  - language | 0..1 | Select | Code | **Language of the resource content<br/>Binding (extensible): A human language. [Common Languages](http://hl7.org/fhir/stu3/valueset-languages.html)** |
|  - text | 0..1 | Select | Narrative | **Text summary of the resource, for human interpretation** |
|  - contained | 0..* | Select | Resource | **Contained, inline Resources** |
|  - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open** |
|  - identifier | 0..* | Select | Identifier | **Business Identifier for observation** |
|  - - use | 0..1 | Select | Code | **usual : official : temp : secondary (If known)<br/>Binding (required): Identifies the purpose for this identifier, if known. [IdentifierUse](http://hl7.org/fhir/stu3/valueset-identifier-use.html)** |
|  - - type | 0..1 | Select | CodeableConcept | **Description of identifier<br/>Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. [Identifier Type Codes](http://hl7.org/fhir/stu3/valueset-identifier-type.html)** |
|  - - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - - system | 1..1 | Select | Uri | **The namespace for the identifier value** |
|  - - value | 1..1 | Select | String | **The value that is unique** |
|  - - period | 0..1 | Select | Period | **Time period when id is/was valid for use<br/>Constraint (per-1): If present, start SHALL have a lower value than end** |
|  - - - start | 0..1 | Select | dateTime | **Starting time with inclusive boundary** |
|  - - - end | 0..1 | Select | dateTime | **End time with inclusive boundary, if not ongoing** |
|  - - assigner | 0..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Organization that issued id (may be just text)<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | **** |
|  - - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - basedOn | 0..* | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Fulfills plan, proposal or order.<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [CarePlan](http://hl7.org/fhir/stu3/StructureDefinition/CarePlan "CarePlan") | **** |
|   |  | Select | [DeviceRequest](http://hl7.org/fhir/stu3/StructureDefinition/DeviceRequest "DeviceRequest") | **** |
|   |  | Select | [ImmunizationRecommendation](http://hl7.org/fhir/stu3/StructureDefinition/ImmunizationRecommendation "ImmunizationRecommendation") | **** |
|   |  | Select | [NutritionOrder](http://hl7.org/fhir/stu3/StructureDefinition/NutritionOrder "NutritionOrder") | **** |
|   |  | Select | [ProcedureRequest](http://hl7.org/fhir/stu3/StructureDefinition/ProcedureRequest "ProcedureRequest") | **** |
|   |  | Select | [ReferralRequest](http://hl7.org/fhir/stu3/StructureDefinition/ReferralRequest "ReferralRequest") | **** |
|   |  | Select | [CareConnect-MedicationRequest-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-MedicationRequest-1 "CareConnect-MedicationRequest-1") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - status | 1..1 | Mandatory | Code | **registered : preliminary : final : amended +<br/>Binding (required): Codes providing the status of an observation. [ObservationStatus](http://hl7.org/fhir/stu3/valueset-observation-status.html)** |
|  - category | 0..* | Select | CodeableConcept | **Classification of type of observation<br/>Binding (preferred): Codes for high level observation categories. [Observation Category Codes](http://hl7.org/fhir/stu3/valueset-observation-category.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - code | 1..1 | Mandatory | CodeableConcept | **Type of observation (code / type)<br/>Binding (example): Codes identifying names of simple observations. [LOINC Codes](http://hl7.org/fhir/stu3/valueset-observation-codes.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open** |
|  - - coding (snomedCT) | 0..1 | Select | Coding | **Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK coding system describing a type of observation [CareConnect-ObservationType-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationType-1)** |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Select | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | **The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font>** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - subject | 0..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Who and/or what this is about<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [Group](http://hl7.org/fhir/stu3/StructureDefinition/Group "Group") | **** |
|   |  | Select | [Device](http://hl7.org/fhir/stu3/StructureDefinition/Device "Device") | **** |
|   |  | Select | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | **** |
|   |  | Select | [CareConnect-Location-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Location-1 "CareConnect-Location-1") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - context | 0..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Healthcare event during which this observation is made<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [EpisodeOfCare](http://hl7.org/fhir/stu3/StructureDefinition/EpisodeOfCare "EpisodeOfCare") | **** |
|   |  | Select | [CareConnect-Encounter-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Encounter-1 "CareConnect-Encounter-1") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - effective[x] | 0..1 | Select | dateTime | **Clinically relevant time/time-period for observation** |
|   |  | Select | Period | **** |
|  - issued | 0..1 | Select | Instant | **Date/Time this was made available** |
|  - performer | 0..* | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Who is responsible for the observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [RelatedPerson](http://hl7.org/fhir/stu3/StructureDefinition/RelatedPerson "RelatedPerson") | **** |
|   |  | Select | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | **** |
|   |  | Select | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | **** |
|   |  | Select | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - value[x] | 0..1 | Select | [Quantity](http://hl7.org/fhir/stu3/datatypes.html#quantity "Quantity") | **Actual result<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present** |
|   |  | Select | CodeableConcept | **** |
|   |  | Select | String | **** |
|   |  | Select | Boolean | **** |
|   |  | Select | [Range](http://hl7.org/fhir/stu3/datatypes.html#range "Range") | **** |
|   |  | Select | [Ratio](http://hl7.org/fhir/stu3/datatypes.html#ratio "Ratio") | **** |
|   |  | Select | [SampledData](http://hl7.org/fhir/stu3/datatypes.html#sampleddata "SampledData") | **** |
|   |  | Select | [Attachment](http://hl7.org/fhir/stu3/datatypes.html#attachment "Attachment") | **** |
|   |  | Select | [Time](http://hl7.org/fhir/stu3/datatypes.html#time "Time") | **** |
|   |  | Select | dateTime | **** |
|   |  | Select | Period | **** |
|  - dataAbsentReason | 0..1 | Select | CodeableConcept | **Why the result is missing<br/>Binding (extensible): Codes specifying why the result (Observation.value[x]) is missing. [Observation Value Absent Reason](http://hl7.org/fhir/stu3/valueset-observation-valueabsentreason.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - interpretation | 0..1 | Select | CodeableConcept | **High, low, normal, etc.<br/>Binding (extensible): Codes identifying interpretations of observations. [Observation Interpretation Codes](http://hl7.org/fhir/stu3/valueset-observation-interpretation.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - comment | 0..1 | Select | String | **Comments about result** |
|  - bodySite | 0..1 | Select | CodeableConcept | **Observed body part<br/>Binding (example): Codes describing anatomical locations. May include laterality. [SNOMED CT Body Structures](http://hl7.org/fhir/stu3/valueset-body-site.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open** |
|  - - coding (snomedCT) | 0..1 | Select | Coding | **Code defined by a terminology system** |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Select | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | **The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font>** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - method | 0..1 | Select | CodeableConcept | **How it was done<br/>Binding (example): Methods for simple observations. [Observation Methods](http://hl7.org/fhir/stu3/valueset-observation-methods.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open** |
|  - - coding (snomedCT) | 0..1 | Select | Coding | **Code defined by a terminology system<br/>Binding (preferred): A code from SNOMED Clinical Terminology UK [CareConnect-ObservationMethod-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationMethod-1)** |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Select | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | **The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font>** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - specimen | 0..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Specimen used for this observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [Specimen](http://hl7.org/fhir/stu3/StructureDefinition/Specimen "Specimen") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - device | 0..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **(Measurement) Device<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [Device](http://hl7.org/fhir/stu3/StructureDefinition/Device "Device") | **** |
|   |  | Select | [DeviceMetric](http://hl7.org/fhir/stu3/StructureDefinition/DeviceMetric "DeviceMetric") | **** |
|  - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - referenceRange | 0..* | Select | BackboneElement | **Provides guide for interpretation<br/>Constraint (obs-3): Must have at least a low or a high or text** |
|  - - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both** |
|  - - low | 0..1 | Select | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | **Low Range, if relevant<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity** |
|  - - - value | 0..1 | Select | Decimal | **Numerical value (with implicit precision)** |
|  - - - unit | 0..1 | Select | String | **Unit representation** |
|  - - - system | 0..1 | Select | Uri | **System that defines coded unit form** |
|  - - - code | 0..1 | Select | Code | **Coded form of the unit** |
|  - - high | 0..1 | Select | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | **High Range, if relevant<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity** |
|  - - - value | 0..1 | Select | Decimal | **Numerical value (with implicit precision)** |
|  - - - unit | 0..1 | Select | String | **Unit representation** |
|  - - - system | 0..1 | Select | Uri | **System that defines coded unit form** |
|  - - - code | 0..1 | Select | Code | **Coded form of the unit** |
|  - - type | 0..1 | Select | CodeableConcept | **Reference range qualifier<br/>Binding (extensible): Code for the meaning of a reference range. [Observation Reference Range Meaning Codes](http://hl7.org/fhir/stu3/valueset-referencerange-meaning.html)** |
|  - - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - - appliesTo | 0..* | Select | CodeableConcept | **Reference range population<br/>Binding (example): Codes identifying the population the reference range applies to. [Observation Reference Range Applies To Codes](http://hl7.org/fhir/stu3/valueset-referencerange-appliesto.html )** |
|  - - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - - age | 0..1 | Select | Range | **Applicable age range, if relevant<br/>Constraint (rng-2): If present, low SHALL have a lower value than high** |
|  - - - low | 0..1 | Select | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | **Low limit<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity** |
|  - - - - value | 0..1 | Select | Decimal | **Numerical value (with implicit precision)** |
|  - - - - unit | 0..1 | Select | String | **Unit representation** |
|  - - - - system | 0..1 | Select | Uri | **System that defines coded unit form** |
|  - - - - code | 0..1 | Select | Code | **Coded form of the unit** |
|  - - - high | 0..1 | Select | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | **High limit<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity** |
|  - - - - value | 0..1 | Select | Decimal | **Numerical value (with implicit precision)** |
|  - - - - unit | 0..1 | Select | String | **Unit representation** |
|  - - - - system | 0..1 | Select | Uri | **System that defines coded unit form** |
|  - - - - code | 0..1 | Select | Code | **Coded form of the unit** |
|  - - text | 0..1 | Select | String | **Text based reference range in an observation** |
|  - related | 0..* | Select | BackboneElement | **Resource related to this observation** |
|  - - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both** |
|  - - type | 0..1 | Select | Code | **has-member : derived-from : sequel-to : replaces : qualified-by : interfered-by<br/>Binding (required): Codes specifying how two observations are related. [ObservationRelationshipType](http://hl7.org/fhir/stu3/valueset-observation-relationshiptypes.html)** |
|  - - target | 1..1 | Select | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | **Resource that is related to this one<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided** |
|   |  | Select | [QuestionnaireResponse](http://hl7.org/fhir/stu3/StructureDefinition/QuestionnaireResponse "QuestionnaireResponse") | **** |
|   |  | Select | [Sequence](http://hl7.org/fhir/stu3/StructureDefinition/Sequence "Sequence") | **** |
|   |  | Select | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") | **** |
|  - - - reference | 0..1 | Select | String | **Literal reference, Relative, internal or absolute URL** |
|  - - - identifier | 0..1 | Select | Identifier | **Logical reference, when literal reference is not known** |
|  - - - display | 0..1 | Select | String | **Text alternative for the resource** |
|  - component | 0..* | Select | BackboneElement | **Component results** |
|  - - modifierExtension | 0..* | Select | Extension | **Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both** |
|  - - code | 1..1 | Select | CodeableConcept | **Type of component observation (code / type)<br/>Binding (example): Codes identifying names of simple observations. [LOINC Codes](http://hl7.org/fhir/stu3/valueset-observation-codes.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open** |
|  - - coding (snomedCT) | 0..1 | Select | Coding | **Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK coding system describing a type of observation [CareConnect-ObservationType-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationType-1)** |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Select | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | **The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>** |
|  - - - system | 1..1 | Select | Uri | **Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font>** |
|  - - - code | 1..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 1..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - value[x] | 0..1 | Select | [Quantity](http://hl7.org/fhir/stu3/datatypes.html#quantity "Quantity") | **Actual component result<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present** |
|   |  | Select | CodeableConcept | **** |
|   |  | Select | String | **** |
|   |  | Select | [Range](http://hl7.org/fhir/stu3/datatypes.html#range "Range") | **** |
|   |  | Select | [Ratio](http://hl7.org/fhir/stu3/datatypes.html#ratio "Ratio") | **** |
|   |  | Select | [SampledData](http://hl7.org/fhir/stu3/datatypes.html#sampleddata "SampledData") | **** |
|   |  | Select | [Attachment](http://hl7.org/fhir/stu3/datatypes.html#attachment "Attachment") | **** |
|   |  | Select | [Time](http://hl7.org/fhir/stu3/datatypes.html#time "Time") | **** |
|   |  | Select | dateTime | **** |
|   |  | Select | Period | **** |
|  - dataAbsentReason | 0..1 | Select | CodeableConcept | **Why the component result is missing<br/>Binding (extensible): Codes specifying why the result (Observation.value[x]) is missing. [Observation Value Absent Reason](http://hl7.org/fhir/stu3/valueset-observation-valueabsentreason.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - interpretation | 0..1 | Select | CodeableConcept | **High, low, normal, etc.<br/>Binding (extensible): Codes identifying interpretations of observations. [Observation Interpretation Codes](http://hl7.org/fhir/stu3/valueset-observation-interpretation.html)** |
|  - - coding | 0..* | Select | Coding | **Code defined by a terminology system** |
|  - - - system | 0..1 | Select | Uri | **Identity of the terminology system** |
|  - - - version | 0..1 | Select | String | **Version of the system - if relevant** |
|  - - - code | 0..1 | Select | Code | **Symbol in syntax defined by the system** |
|  - - - display | 0..1 | Select | String | **Representation defined by the system** |
|  - - - userSelected | 0..1 | Select | Boolean | **If this coding was chosen directly by the user** |
|  - - text | 0..1 | Select | String | **Plain text representation of the concept** |
|  - referenceRange | 0..* | Select | see Observation.referenceRange | **Provides guide for interpretation of component result** |