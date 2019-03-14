---
title: Test Result (Single)
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_test_result_observation.html
summary: "National Pathology FHIR Message Profiles"
---

## Overview ##

Contains data on clinical test performed on patient where there are multiple values. This information may or may not be linked to a test report or a test group. It is populated by the performing organisation. The majority of test results will contain a single value however there are tests with multiple values (for example blood pressure). As a general rule - where there are multiple values that can potentially have an independent clinical interpretation they are considered as multiple test results each with their own value (For example: Full Blood Count) - where there are multiple values which can only be interpreted together they are considered as a single test result with multiple values (For example: Glucose Absorption Test) 

## Mapping for Observation ##

How to populate the Observation instance to conform to the profiles below:

|**Level 1**|[Observation Resource](http://hl7.org/fhir/stu3/observation.html)|**Level 2**|[CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1/_history/1.1)|**Level 3**|None|

|**View Used FHIR Elements**|    |**[View All FHIR Elements](explore_observation_all.html#mapping-for-diagnosticreport)**|

|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  Observation | ​ |  |  | **Measurements and simple assertions<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (obs-7): If code is the same as a component code then the value element associated with the code SHALL NOT be present<br/>Constraint (obs-6): dataAbsentReason SHALL only be present if Observation.value[x] is not present** |
|  - id | 0..1 | Required | Id | Logical id of this artifact<br/><font color="red">Must contain a UUID to identify the instance of a observation</font> |
|  - meta | 0..1 | Mandatory | Meta | Metadata about the resource<br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observtion-1'</font> |
|  - identifier | 0..* | Mandatory | Identifier | Business Identifier for observation |
|  - - system | 1..1 | Mandatory | Uri | The namespace for the identifier value<br/><font color="red">MUST contain the value 'https://tools.ietf.org/html/rfc4122'.</font> |
|  - - value | 1..1 | Mandatory | String | The value that is unique<br/><font color="red">MUST contain a UUID</font> |
|  - status | 1..1 | Mandatory | Code | registered : preliminary : final : amended +<br/>Binding (required): Codes providing the status of an observation. [ObservationStatus](http://hl7.org/fhir/stu3/valueset-observation-status.html) |
|  - category | 0..* | Required | CodeableConcept | Classification of type of observation<br/>Binding (preferred): Codes for high level observation categories. [Observation Category Codes](http://hl7.org/fhir/stu3/valueset-observation-category.html)<br/><font color="red">The general type of test result.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - code | 1..1 | Mandatory | CodeableConcept | Type of observation (code / type)<br/>Binding (example): Codes identifying names of simple observations. ( http://hl7.org/fhir/stu3/valueset-observation-codes.html ) |
|  - - coding | 0..* | Mandatory | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Mandatory | Coding | Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK coding system describing a type of observation [CareConnect-ObservationType-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationType-1) |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system<br/><font color="red>A code that identifies the test result.</font> |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system<br/><font color="red"?SNOMED CT display name. This will be the name of the test that took place</font> |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 0..1 | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who and/or what this is about<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Optional | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | <font color='red'>his MUST be to the Patient resource profiled as CareConnect-Patient-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - effective[x] | 0..1 | Required | dateTime | Clinically relevant time/time-period for observation<br/><font color="red">The date and time on which the test was performed.</font> |
|  - issued | 0..1 | Required | Instant | Date/Time this was made available<br/><font color="red">Test Result Issued Date and Time</font> |
|  - performer | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who is responsible for the observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided. <font color="red">Reference to the person and/or organisation that authored the test report.</font> |
|   |  | Required | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>his MUST be to the Organization resource profiled as CareConnect-Organization-1 </font> |
|   |  | Required | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>his MUST be to the Practitioner resource profiled as CareConnect-Practitioner-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Organization or Practitioner resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - value[x] | 0..1 | Required | [Quantity ( CareConnect-ApproximateQuantity-1 )](http://hl7.org/fhir/stu3/datatypes.html#quantity "Quantity") | Actual result<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>|
|  - - extension (valueApproximation)|	0..1|	Required	|Extension	|"Value Approximation Constraint (ext-1): Must have either extensions or value[x], not both URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ValueApproximation-1"|
|  - - value.quantity.value | 0..1 | Mandatory | [Decimal](http://hl7.org/fhir/stu3/datatypes.html#decimal "Decimal") | Numerical value (with implicit precision) |
|  - - value.quantity.comparator | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | < : <= : >= : > - how to understand the value<br/>Binding (required): How the Quantity should be understood and represented. (http://hl7.org/fhir/stu3/valueset-quantity-comparator.html )<br/><font color="red">A comparator that may used to indicate whether the actual value is greater or less than the stated value.</font> |
|  - - value.quantity.unit | 0..1 | Required | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Unit representation<br/><font color="red">A human readable form of the unit of measure associated with a test result value.</font> |
|  - - value.quantity.code | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Coded form of the unit<br/><font color="red">The UCUM code that identifies the unit of measure associated with a test result value.</font> |
|  - dataAbsentReason | 0..1 | Required | CodeableConcept | Why the result is missing<br/>Binding (extensible): Codes specifying why the result (Observation.value[x]) is missing. [Observation Value Absent Reason](http://hl7.org/fhir/stu3/valueset-observation-valueabsentreason.html)<br/><font color="red">The reason why a test result is missing.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - interpretation | 0..1 | Required | CodeableConcept | High, low, normal, etc.<br/>Binding (extensible): Codes identifying interpretations of observations. [Observation Interpretation Codes](http://hl7.org/fhir/stu3/valueset-observation-interpretation.html)<br/><font color="red">Simple coded interpretation of the results. It is provided by the performing HCP. For example - out of range, high, low.</font><font color="red">Use FHIR Value Set for standard interpretation codes and https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ExtendedInterpretationCode-1 for additional codes</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - comment | 0..1 | Required | String | Comments about result<br/><font color="red">Human readable clinical summary relating to a test result. It is provided by the performing HCP</font> |
|  - bodySite | 0..1 | Required | CodeableConcept | Observed body part<br/>Binding (example): Codes describing anatomical locations. May include laterality. [SNOMED CT Body Structures](http://hl7.org/fhir/stu3/valueset-body-site.html) |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Required | Coding | Code defined by a terminology system |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Required | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - method | 0..1 | Required | CodeableConcept | How it was done<br/>Binding (example): Methods for simple observations. [Observation Methods](http://hl7.org/fhir/stu3/valueset-observation-methods.html)<br/><font color="red">The method of testing/observation that was used.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Required | Coding | Code defined by a terminology system<br/>Binding (preferred): A code from SNOMED Clinical Terminology UK [CareConnect-ObservationMethod-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationMethod-1) |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Required | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - specimen | 0..1 | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimen used for this observation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Specimen resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - referenceRange | 0..* | Required | BackboneElement | Provides guide for interpretation<br/>Constraint (obs-3): Must have at least a low or a high or text |
|  - - low | 0..1 | Required | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | Low Range, if relevant<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity |
|  - - - value | 0..1 | Required | Decimal | Numerical value (with implicit precision) |
|  - - - unit | 0..1 | Required | String | Unit representation |
|  - - - system | 0..1 | Required | Uri | System that defines coded unit form |
|  - - - code | 0..1 | Required | Code | Coded form of the unit |
|  - - high | 0..1 | Required | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | High Range, if relevant<br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity |
|  - - - value | 0..1 | Required | Decimal | Numerical value (with implicit precision) |
|  - - - unit | 0..1 | Required | String | Unit representation |
|  - - - system | 0..1 | Required | Uri | System that defines coded unit form |
|  - - - code | 0..1 | Required | Code | Coded form of the unit |
|  - - text | 0..1 | Required | String | Text based reference range in an observation<br/><font color="red">Recomend to use text to describe reference range (i.e. male/female etc)</font> |
|  - related | 0..* | Required | BackboneElement | Resource related to this observation<br/><font color="red">Multi-purpose data item:</font><br/><font color="red">1. Report Filing. Reference to information recorded by the receiving health care professional when they review the test results.</font><br/><font color="red">2. Reference to the test group header observation if the result is part of a test group.</font> |
|  - - target | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Resource that is related to this one<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") |  |
|  - - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL<br/><font color="red">a reference to the Observtionresource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font><br/> |

## Test (Single) Result Example(s) ##

<script src="https://gist.github.com/IOPS-DEV/bdac374abdb996d0527e9cb44b2a0b33.js"></script>