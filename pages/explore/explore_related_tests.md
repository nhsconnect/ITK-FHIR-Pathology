---
title: Related Tests
keywords: test
tags: [test,fhir]
sidebar: overview_sidebar
permalink: explore_related_tests.html
summary: "Related Tests in National Pathology"
---

## Related Tests ##

Related tests in National Pathology messages.

### Reporting different types of test result ###

Individual test results are reported in the value[x] element of an Observation resource. 
In FHIR, the value[x] construct allows a choice of datatype to be returned, appropriate to the datatype of the result.

| Value types           | FHIR datatype guidance    |
---
| valueQuantity         | [Quantity](https://hl7.org/fhir/r4/datatypes.html#Quantity)                   |
| valueCodeableConcept  | [CodeableConcept](https://hl7.org/fhir/r4/datatypes.html#CodeableConcept)     |
| valueString           | [string](https://hl7.org/fhir/r4/datatypes.html#string)                       |
| valueBoolean          | [boolean](https://hl7.org/fhir/r4/datatypes.html#boolean)                     |
| valueInteger          | [integer](https://hl7.org/fhir/r4/datatypes.html#integer)                     |
| valueRange            | [Range](https://hl7.org/fhir/r4/datatypes.html#Range)                         |
| valueRatio            | [Ratio](https://hl7.org/fhir/r4/datatypes.html#Ratio)                         |
| valueSampledData      | [SampledData](https://hl7.org/fhir/r4/datatypes.html#SampledData)             |
| valueTime             | [time](https://hl7.org/fhir/r4/datatypes.html#time)                           |
| valueDateTime         | [dateTime](https://hl7.org/fhir/r4/datatypes.html#dateTime)                   |
| valuePeriod           | [Period](https://hl7.org/fhir/r4/datatypes.html#Period)                       |

### Reporting coded values using Read Codes ###




### Reporting qualified reference ranges ###




