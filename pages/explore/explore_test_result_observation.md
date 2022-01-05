---
title: Test Result (Single)
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_test_result_observation.html
summary: "National Pathology FHIR Message Profiles"
---

## Overview ##

Contains data relating to a clinical test performed on a patient. This information may or may not be linked to a test report or a test group. It is populated by the performing organisation.

## Mapping for Observation ##

How to populate the Observation instance to conform to the profiles below:

|**Level 1**|[Observation Resource](http://hl7.org/fhir/stu3/observation.html)|**Level 2**|[CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)|**Level 3**|None|


|  **Name** | **Card.** | **Conformance** | **Type** | **Description, Constraints and mapping for National Pathology Implementation** |
| :--- | :--- | :--- | :--- | :--- |
|  Observation | ​ |  |  | **Measurements and simple assertions<br/><br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/><br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/><br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/><br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/><br/>Constraint (obs-7): If code is the same as a component code then the value element associated with the code SHALL NOT be present<br/><br/>Constraint (obs-6): dataAbsentReason SHALL only be present if Observation.value[x] is not present** |
|  - id | 0..1 | Required | Id | Logical id of this artifact<br/><br/><font color="red">MUST contain a unique identifier to identify the instance of a observation</font> |
|  - meta | 0..1 | Mandatory | Meta | Metadata about the resource<br/><br/><font color="red">The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Observtion-1'</font> |
|  - identifier | 0..* | Required | Identifier | Business Identifier for observation<br/><br/>Resources in National Pathology messages SHOULD be sent with appropriate Business Identifiers. A National identifier is preferred to a Local identifier, is preferred to No business identifer. |
|  - - system | 1..1 | Mandatory | Uri | The namespace for the identifier value<br/><br/><font color="red">MUST contain a local identifier naming system</font> |
|  - - value | 1..1 | Mandatory | String | The value that is unique<br/><br/><font color="red">MUST contain a unique identifier</font> |
|  - status | 1..1 | Mandatory | Code | registered : preliminary : final : amended +<br/><br/>Binding (required): Codes providing the status of an observation. [ObservationStatus](http://hl7.org/fhir/stu3/valueset-observation-status.html) |
|  - category | 0..* | Required | CodeableConcept | Classification of type of observation<br/><br/>Binding (preferred): Codes for high level observation categories. [Observation Category Codes](http://hl7.org/fhir/stu3/valueset-observation-category.html)<br/><br/><font color="red">The general type of test result.A default value of Laboratory should be used if a more specific value is not available e.g. pathology, microbiology etc.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - code | 1..1 | Mandatory | CodeableConcept | Type of observation (code / type)<br/><br/>While coded SNOMED CT values are preferred, if a translation or mapping to SNOMED is not available, reporting coded values using Read codes.<br/><br/>Binding (example): Codes identifying names of simple observations. ( http://hl7.org/fhir/stu3/valueset-observation-codes.html ) <font color="red">The clinical code that represents the name of the test result or test analyte.</font>|
|  - - coding | 0..* | Mandatory | Coding | Code defined by a terminology system<br/><br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Mandatory | Coding | Code defined by a terminology system<br/><br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK coding system describing a type of observation [CareConnect-ObservationType-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationType-1) |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/><br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/><br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><br/><font color='red'>If using SNOMED CT, the value attribute of the profile element MUST contain the value 'http://snomed.info/sct'<br/>If using a Read code, the value attribute of the profile element MUST contain the value 'http://read.info/readv2'<br/></font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system<br/><br/><font color="red">A code that identifies the test result.</font> |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system<br/><br/><font color="red">SNOMED CT display name. This will be the name of the test that took place</font> |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - subject | 0..1 | Optional | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who and/or what this is about<br/><br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Optional | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1 "CareConnect-Patient-1") | <font color='red'>This MUST be to the Patient resource profiled as CareConnect-Patient-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Patient resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - effective[x] | 0..1 | Required | dateTime | Clinically relevant time/time-period for observation<br/><br/><font color="red">The date and time on which the test was performed.</font> |
|  - issued | 0..1 | Required | Instant | Date/Time this was made available<br/><br/><font color="red">The date and time that the result was issued by the laboratory or other report provider</font> |
|  - performer | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Who is responsible for the observation<br/><br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided. <font color="red">Reference to the resource for the organisation and/or practitioner that performed the test.</font> |
|   |  | Required | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1 "CareConnect-Organization-1") | <font color='red'>This MUST be to the Organization resource profiled as CareConnect-Organization-1 </font> |
|   |  | Required | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1 "CareConnect-Practitioner-1") | <font color='red'>This MUST be to the Practitioner resource profiled as CareConnect-Practitioner-1 </font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Organization or Practitioner resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - value[x] | 0..1 | Required | [Quantity ( CareConnect-ApproximateQuantity-1 )](http://hl7.org/fhir/stu3/datatypes.html#quantity "Quantity") | Actual result<br/><br/>For numeric results this will typically be a valueQuantity<br/><br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/><br/>|
|  - - extension (valueApproximation)|	0..1|	Required	|Extension	| If using an approximation, Result values of Quantity datatype can be marked as approximations using the [Extension-CareConnect-ValueApproximation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ValueApproximation-1).<br/><br/>This extension SHOULD NOT be used when reporting exact values.<br/><br/>"Value Approximation Constraint (ext-1): Must have either extensions or value[x], not both. |
|  - - value.quantity.value | 0..1 | Mandatory | [Decimal](http://hl7.org/fhir/stu3/datatypes.html#decimal "Decimal") | Numerical value (with implicit precision) |
|  - - value.quantity.comparator | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | < : <= : >= : > - how to understand the value<br/><br/>Binding (required): How the Quantity should be understood and represented. (http://hl7.org/fhir/stu3/valueset-quantity-comparator.html )<br/><br/><font color="red">A comparator that may be used to indicate whether the actual value is greater or less than the stated value.</font> |
|  - - value.quantity.unit | 0..1 | Required | [String](http://hl7.org/fhir/stu3/datatypes.html#string "String") | Unit representation<br/><br/>When reporting Quantities, systems SHOULD report relevant units for the quantity value.<br/>
        - If a code for the unit is present, the system SHALL also be present<br/>
        - UCUM is the preferred system for reporting units<br/><font color="red">A human readable form of the unit of measure associated with a test result value.</font> |
|  - - value.quantity.system | 0..1 | Required | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri "Uri") | System from which the unit is taken<br/><br/><font color="red">When using the UCUM system - http://unitsofmeasure.org - that identifies the unit of measure associated with a test result value.</font> |
|  - - value.quantity.code | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code "Code") | Coded form of the unit<br/><br/><font color="red">The UCUM code that identifies the unit of measure associated with a test result value.</font> |
|  - dataAbsentReason | 0..1 | Required | CodeableConcept | Why the result is missing<br/><br/>Binding (extensible): Codes specifying why the result (Observation.value[x]) is missing. [Observation Value Absent Reason](http://hl7.org/fhir/stu3/valueset-observation-valueabsentreason.html)<br/><br/><font color="red">The reason why a test result is missing.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - interpretation | 0..1 | Required | CodeableConcept | High, low, normal, etc.<br/><br/>Binding (extensible): Codes identifying interpretations of observations. [Observation Interpretation Codes](http://hl7.org/fhir/stu3/valueset-observation-interpretation.html)<br/><br/><font color="red">Simple coded interpretation of the results. It is provided by the performing HCP. For example - out of range, high, low. </font><font color="red">Use FHIR Value Set for standard interpretation codes and https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ExtendedInterpretationCode-1 for additional codes</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system |
|  - - - system | 0..1 | Mandatory | Uri | Identity of the terminology system |
|  - - - code | 0..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 0..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - comment | 0..1 | Required | String | Comments about result<br/><br/><font color="red">A human readable clinical summary relating to a test result and/or additional notes provided by the laboratory e.g. the specimen has haemolysed or has leaked.</font> |
|  - bodySite | 0..1 | Required | CodeableConcept | Observed body part<br/><br/>Binding (example): Codes describing anatomical locations. May include laterality. [SNOMED CT Body Structures](http://hl7.org/fhir/stu3/valueset-body-site.html) |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system<br/><br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Required | Coding | Code defined by a terminology system |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Required | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/><br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/><br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - method | 0..1 | Required | CodeableConcept | How it was done<br/><br/>Binding (example): Methods for simple observations. [Observation Methods](http://hl7.org/fhir/stu3/valueset-observation-methods.html)<br/><br/><font color="red">The method of testing/observation that was used.</font> |
|  - - coding | 0..* | Required | Coding | Code defined by a terminology system<br/><br/>Slicing: Discriminator: code, Ordering: false, Rules: Open |
|  - - coding (snomedCT) | 0..1 | Required | Coding | Code defined by a terminology system<br/><br/>Binding (preferred): A code from SNOMED Clinical Terminology UK [CareConnect-ObservationMethod-1](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ObservationMethod-1) |
|  - - - extension (snomedCTDescriptionID) | 0..1 | Required | [Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid "Extension-coding-sctdescid") | The SNOMED CT Description ID for the display.<br/><br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/><br/> |
|  - - - system | 1..1 | Mandatory | Uri | Identity of the terminology system<br/><br/><font color='red'>The value attribute of the profile element MUST contain the value 'http://snomed.info/sct'</font> |
|  - - - code | 1..1 | Mandatory | Code | Symbol in syntax defined by the system |
|  - - - display | 1..1 | Mandatory | String | Representation defined by the system |
|  - - text | 0..1 | Optional | String | Plain text representation of the concept |
|  - specimen | 0..1 | Required | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Specimen used for this observation<br/><br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Required | [CareConnect-Specimen-1 ](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1 "CareConnect-Specimen-1 ") | <font color='red'>The value attribute of the profile element MUST contain the value 'https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-Specimen-1'</font> |
|  - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL <font color="red">a reference to the Specimen resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font> |
|  - referenceRange | 0..* | Required | BackboneElement | Provides guide for interpretation<br/><br/>Constraint (obs-3): Must have at least a low or a high or text |
|  - - low | 0..1 | Required | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | Low Range, if relevant.<br/><br/>Values with a low bound only are interpreted as greater than low bound.<br/><br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/><br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity |
|  - - - value | 0..1 | Required | Decimal | Numerical value (with implicit precision) |
|  - - - unit | 0..1 | Required | String | Unit representation |
|  - - - system | 0..1 | Required | Uri | System that defines coded unit form |
|  - - - code | 0..1 | Required | Code | Coded form of the unit |
|  - - high | 0..1 | Required | [Quantity ( SimpleQuantity )](http://hl7.org/fhir/stu3/StructureDefinition/SimpleQuantity "Quantity ( SimpleQuantity )") | High Range, if relevant<br/><br/>Values with a high bound only are interpreted as less than high bound.<br/><br/>Constraint (qty-3): If a code for the unit is present, the system SHALL also be present<br/><br/>Constraint (sqty-1): The comparator is not used on a SimpleQuantity |
|  - - - value | 0..1 | Required | Decimal | Numerical value (with implicit precision) |
|  - - - unit | 0..1 | Required | String | Unit representation |
|  - - - system | 0..1 | Required | Uri | System that defines coded unit form |
|  - - - code | 0..1 | Required | Code | Coded form of the unit |
|  - - text | 0..1 | Required | String | Text based reference range in an observation<br/><br/><font color="red">Recommend to use text to describe reference range (i.e. male/female etc)</font> |
|  - related | 0..* | Required | BackboneElement | Resource related to this observation<br/><br/>Where this Observation is calculated or derived from other results, .related SHALL list antecedent (or input) Test Result Observation resources<br/><br/> |
|  - - type | 0..1 | Required | Code | Where a Test Result is calculated or derived from other results, antecedent items SHALL be typed as 'derived-from'<br/><br/>[ has-member \| derived-from \| sequel-to \| replaces \| qualified-by \| interfered-by ]<br/><br/>Binding (required): Codes specifying how two observations are related. [ObservationRelationshipType](http://hl7.org/fhir/stu3/valueset-observation-relationshiptypes.html) |
|  - - target | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html "Reference") | Resource that is related to this one<br/><br/>logical identifier (.id element) of the antecedent item Observation resource<br/><br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1 "CareConnect-Observation-1") |  |
|  - - - reference | 0..1 | Mandatory | String | Literal reference, Relative, internal or absolute URL<br/><br/><font color="red">a reference to the Observtion resource instance in the message in the format of a UUID prefixed with 'urn:uuid:'.</font><br/><br/> |


Mandatory elements **MUST** be returned in National Pathology messages.
Required elements **SHOULD** be returned in National Pathology messages if the data is available.
Optional elements **MAY** be returned in National Pathology messages if the data is available

Elements in the base FHIR resource that are not listed **SHOULD NOT** be used in National Pathology messages.

## Test (Single) Result Example(s) ##

{% include custom/fhir.codegrid.html
relfilepath="NP-Observation-Result-Example-1.xml"
title="Observation Result Example"
type="xml" %}