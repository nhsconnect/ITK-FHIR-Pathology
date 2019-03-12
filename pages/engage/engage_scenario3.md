---
title: Scenarios 3 
keywords:  test
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: engage_scenario3.html
summary: "Two Test Requests, Two Test Results"
---

{% include warning.html content="This **temporary** site is provided to assist with the development of the **Alpha** Your Project Here Specification and is being updated regularly. It is advised not to develop against these specifications until a formal announcement has been made." %}

**Description**

Sarah Smith, a community-based midwife at St John’s Infirmary, sees a 5 day old baby, Jane Archer, in a postnatal clinic. Jane is showing signs of jaundice. Sarah takes a blood sample from Jane and requests total bilirubin and conjugated bilirubin tests. 
The test requests are sent using a paper test request form to the laboratory based in St John’s. The blood sample is sent via specialist courier to the laboratory.

The sample is received by the laboratory, checked and matched with the test requests. The details are recorded on the Laboratory Information Management System (LIMS). 

The tests are performed, and the results are authorised for release. The following test results (and reference ranges) are phoned to the midwife and sent electronically from the LIMS to primary care and the EPR system within the hospital:

|----------------------|-----------------|-----------------|
|Total Bilirubin|	325 umol/L	|(0 to 21) |

|----------------------|-----------------|-----------------|
|Conjugated Bilirubin	|14 umol/L	|(0 to 5.1)|

Jane is admitted to the Special Care Baby Unit at the hospital for phototherapy.

## Named participants ##

- Patient: Jane Archer – FHIR Resource:  [Patient](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1)
- Requesting HCP: Sarah Smith  – FHIR Resource:  [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)
- Specimen Collecting HCP: Sarah Smith – FHIR Resource: Practitioner

## Named Organisations ##

- Requesting Organisation: St John’s Infirmary (Maternity Service)  – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Specimen Collecting Organisation: St John’s Infirmary (Maternity Service) – FHIR Resource: Organization
- Performing Organisation: St John’s Infirmary (Blood Sciences) – FHIR Resource:  Organization

## Condition ##

- Jaundice  – FHIR Resource:  [Condition](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1)

## Required Tests ##

- Total Bilirubin – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Conjugated Bilirubin  – FHIR Resource:  ProcedureRequest

## Specimen(s) ##

- Blood – FHIR Resource: [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1)

## Test Report ##

- FHIR Resource: [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)

## Test Results ##

- Total Bilirubin Result - FHIR Resource: [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)
- Conjugated Bilirubin Result - FHIR Resource: Observation



