---
title: Scenarios 2 
keywords:  test
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: engage_scenario2.html
summary: "Single Test Profile Request, Multiple Test Results"
---

{% include warning.html content="This **temporary** site is provided to assist with the development of the **Alpha** Your Project Here Specification and is being updated regularly. It is advised not to develop against these specifications until a formal announcement has been made." %}

**Description**

Lisa Stanner, a 60 year old woman, attends Manor GP Practice for monitoring her hypertension. Lisa’s GP, Dr Jane Green, requests renal function tests (electrolytes and creatinine profile). The request is sent electronically using an order comms system (accessed via the GP practice system) to the pathology laboratory based in the local hospital, Midtown District Hospital.
Dr Green books an appointment with the practice nurse, Alice Jones. Lisa attends the appointment the following day where the blood sample is taken and sent to the laboratory.
The sample is received by the laboratory, checked and matched with the test request. The details are recorded on the Laboratory Information Management System (LIMS). 
The tests are performed, and the results are authorised for release. The following test results (and reference ranges) are sent electronically from the LIMS to the GP practice system:


<table style="width:100%">
  <tr>
    <th colspan="3">Electrolytes and Creatinine Profile</th>
  </tr>
  <tr>
    <td style="width:33%">Sodium</td>
    <td style="width:33%">142 mmol/L</td> 
    <td style="width:33%">(133 to 146)</td>
  </tr>
  <tr>
    <td style="width:33%">Potassium</td>
    <td style="width:33%">4.8 mmol/L</td> 
    <td style="width:33%">(3.5 to 5.3)</td>
  </tr>
   <tr>
    <td style="width:33%">Chloride</td>
    <td style="width:33%">105 mmol/L</td> 
    <td style="width:33%">(95 to 108)</td>
  </tr>
   <tr>
    <td style="width:33%">Creatinine</td>
    <td style="width:33%">64 umol/L</td> 
    <td style="width:33%">(48 to 128)</td>
  </tr>
   <tr>
    <td style="width:33%">EGFR</td>
    <td style="width:33%">87 mL/min/1.73m*</td> 
    <td style="width:33%"></td>
  </tr>
  <tr>
    <td colspan="3">Comments: The EGFR quoted above must be multiplied by 1.2 if the patient is of Afro-Caribbean origin.</td>
  </tr>
</table>



## Named participants ##

- Patient: Patient: Lisa Stanner – FHIR Resource: [Patient](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1)
- Requesting HCP: Dr Jane Green – FHIR Resource:  [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)
- Specimen Collecting HCP: Alice Jones – FHIR Resource: Practitioner

## Named Organisations ##

- Requesting Organisation: Manor GP Practice – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Specimen Collecting Organisation: Manor GP Practice – FHIR Resource: Organization
- Performing Organisation: Midtown District Hospital (Blood Sciences) – FHIR Resource:  Organization

## Condition ##

- Hypertension – FHIR Resource:  [Condition](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1)

## Required Tests ##

- Electrolytes and creatinine – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)

## Specimen(s) ##

- Blood – FHIR Resource: [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1)

## Test Report ##

- FHIR Resource: [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)

## Test Results ##

- FHIR Resource: [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)




