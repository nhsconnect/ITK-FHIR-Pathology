---
title: Scenarios 1 
keywords:  test
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: engage_scenario1.html
summary: "Single Test Request, Single Test Result"
---

{% include warning.html content="This **temporary** site is provided to assist with the development of the **Alpha** Your Project Here Specification and is being updated regularly. It is advised not to develop against these specifications until a formal announcement has been made." %}

**Description**

Michael Kay, a 58 year old man, attends an appointment at an oncology outpatient clinic at Lingfield Royal Infirmary. The consultant, Dr Ibrahim Khan, gives Michael a blood test form for a prostate-specific antigen (PSA) test and asks him to attend the hospital’s phlebotomy clinic.
On the same day, Michael attends the phlebotomy clinic and hands in the blood test form. A blood sample is taken by one of the clinic phlebotomists, Juan Garcia, and sent to the laboratory based in the hospital.
The sample is received by the laboratory, checked and matched with the test request. The details are recorded on the Laboratory Information Management System (LIMS). 
The test is performed, and the results are authorised for release. The following test results (and reference ranges) are sent electronically from the LIMS to the hospital’s Electronic Patient Record (EPR) system and the GP system at Michael’s GP surgery:

|-------------------------|--------|--------|
|Prostate Specific Antigen|5.9 ug/L|(0 to 4)|

## Named participants ##

- Patient: Michael Kay – FHIR Resource: [Patient](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1)
- Requesting HCP: Dr Ibrahim Khan – FHIR Resource: [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)
- Specimen Collecting HCP: Juan Garcia – FHIR Resource: [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)

## Named Organisations ##

- Requesting Organisation: Lingfield Royal Infirmary (Oncology) – FHIR Resource: [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Specimen Collecting Organisation: Lingfield Royal Infirmary (Oncology) – FHIR Resource: [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Performing Organisation: Lingfield Royal Infirmary (Blood Sciences) – FHIR Resource: [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)

## Condition ##

- Prostate cancer – FHIR Resource: [Condition](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1)

## Required Tests ##

- PSA – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)

## Specimen(s) ##

- Blood – FHIR Resource: [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1)

## Test Report ##

- FHIR Resource: [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)

## Test Results ##

- FHIR Resource: [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)




