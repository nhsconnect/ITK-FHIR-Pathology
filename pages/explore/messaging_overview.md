---
title: Messaging Architecture Overview
keywords:  messaging
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore.html
summary: "Overview of the Messaging Architecture section"
---

{% include warning.html content="This **temporary** site is provided to assist with the development of the **Alpha** and is being updated regularly. It is advised not to develop against these specifications until a formal announcement has been made." %}


## Using the message pages ##

Within this message section of the implementation guide, the audience are presented with each business entity that form part of a National Pathology diagnostic test. The business entities are:

- Test Request Summary - This business entity is used to capture details from the requestor and uses the [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1) FHIR resource.
- Test Report - This business entity is used to capture details regarding all the tests performed by the performing organisation and uses the [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1) FHIR resource.
- Specimen - This business entity is used to capture specimen (sample) details and uses the [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1) FHIR resource.
- Test Group - This business entity is used to capture groups of test results. These can be a battery of tests or a single test, or a combination of all of these entities. Use the [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) FHIR resource.
- Test Result - This business entity is used to capture details for a single test result and uses the [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1).


Within each business entity message, the audience is presented with a tabular view that provides low level details on how each FHIR element is used to construct a data record to support the requirements for that business entity. The table is made up of 5 columns:

**Name**

The FHIR data element name used by HL7 FHIR

**Card.**

The cardinality assigned to this FHIR data element. This may differ to the FHIR base value if the resource uses is a CareConnect version.

**Business Conformance**

This indicates what the business has requested the value be set to. Consists of Mandatory, Required and Optional (MRO). This may conflict with the FHIR cardinality e.g 0..1 in FHIR MAY be Mandatory within the business.

**Type**

FHIR data type used with this element. This MAY inlcuded reference to FHIR profiles.

**Description, Constraints and Mapping for Implementation**

Supporting information for the data item which is made up of FHIR default description, which always remains in place and unchanged, and additional narrative added to support the business requirement. Any additional supporting information is highlighted in <font color="Red">Red font</font> to distinguish it from the default FHIR descriptions.


The table provides a clear guidance to allow implementers to rapidly build a structured National Pathology diagnostic test message.

## Bundle Diagram ##

The following diagram provides a visual indication to assist implementers with understanding which resources are included within a National Pathology ITK bundle, and how these resources are related. The diagram is interactive and upon click on each resource, this will redirect the user to the specific National Pathology page which provides data item level implementation guidance.

{% include custom/bundle_diagram.svg %}