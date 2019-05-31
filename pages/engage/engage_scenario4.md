---
title: Scenarios 4 
keywords:  test
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: engage_scenario4.html
summary: "– Multiple Test Requests, Multiple Samples"
---




**Description**

John Reardon, a 44 year old man, attends Heath Park GP surgery for a health check. Blood tests are requested by the practice nurse, Alison Thompson, for full blood count, electrolytes, liver function, cholesterol and glycated haemoglobin (i.e. HbA1c (IFCC)). 
The test requests are sent electronically using an order comms system to the pathology laboratory based in Greentown General Hospital. Alison takes three blood samples and sends them to the laboratory.

The samples are received by the laboratory, checked and matched with the test requests. The details are recorded on the Laboratory Information Management System (LIMS).

The tests are performed, and the results are authorised for release. The following test results (and reference ranges) are sent electronically from the LIMS to the GP practice system:


|----------------------|-----------------|-----------------|
|**Full Blood Count**|
|Haemoglobin|	142 g/L	|(115 to 150)
|White Blood Count|	5.7 10^9/L	|(3.5 to 11.0)
|Platelets|	206 10^9/L	|(140 to 400)
|Haematocrit (PCV)|	0.427 Ratio	|(0.36 to 0.46)
|Red Blood Count	|4.57 10^12/L	|(3.80 to 5.00)
|Mean Cell Volume|	93.4 fL	|(80.0 to 99.0)
|Mean Cell Haemoglobin|	31.1 pg	|(27.5 to 32.5)
|Mean Cell Haemoglobin Conc.|	333 g/L	|(310 to 350)
|Neutrophils|	2.76 10^9/L	|(1.70 to 8.00)
|Lymphocytes	|2.12 10^9/L	|(1.00 to 4.00)
|Monocytes|	0.48 10^9/L	|(0.20 to 0.80)
|Eosinophils|	0.29 10^9/L	|(0.04 to 0.40)
|Basophils|	0.06 10^9/L	|(0.02 to 0.10)
|Nucleated RBCs	|0.0010^9/L	||
|Red Cell Distribution Width	|^13 %	|(11.6 to 13.9)
|Mean Platelet Volume|	^10.6 fL	|(7.1 to 10.7)

<table style="width:100%">
  <tr>
    <th colspan="3">Electrolytes and Creatinine Profile</th>
  </tr>
  <tr>
    <td style="width:33%">Sodium</td>
    <td style="width:33%">140 mmol/L</td> 
    <td style="width:33%">(133 to 146)</td>
  </tr>
  <tr>
    <td style="width:33%">Potassium</td>
    <td style="width:33%">5.0 mmol/L</td> 
    <td style="width:33%">(3.5 to 5.3)</td>
  </tr>
   <tr>
    <td style="width:33%">Chloride</td>
    <td style="width:33%">103 mmol/L</td> 
    <td style="width:33%">(95 to 108)</td>
  </tr>
   <tr>
    <td style="width:33%">Creatinine</td>
    <td style="width:33%">76 umol/L</td> 
    <td style="width:33%">(48 to 128)</td>
  </tr>
   <tr>
    <td style="width:33%">EGFR</td>
    <td style="width:33%">>90 mL/min/1.73m*</td> 
    <td style="width:33%"></td>
  </tr>
  <tr>
    <td colspan="3">Comments: The EGFR quoted above must be multiplied by 1.2 if the patient is of Afro-Caribbean origin.</td>
  </tr>
</table>

|----------------------|-----------------|-----------------|
|**Liver function tests**||
|Total Bilirubin|	13 umol/L|	(0 to 21)|
|Alkaline Phosphatase|	83 IU/L|	(30 to 130)|
|Alanine Transaminase|	27 IU/L	|(0 to 40)|

|----------------------|-----------------|-----------------|
|Cholesterol|7.7 mmol/L||

|----------------------|-----------------|-----------------|
|HbA1c (IFCC)|45 mmol/mol|(18 to 41)|

## Named participants ##

- Patient: John Reardon  – FHIR Resource:  [Patient](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1)
- Requesting HCP: Alison Thompson   – FHIR Resource:  [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)
- Specimen Collecting HCP: Alison Thompson  – FHIR Resource: [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)

## Named Organisations ##

- Requesting Organisation: Heath Park Surgery   – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Specimen Collecting Organisation: Heath Park Surgery  – FHIR Resource: [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Performing Organisation: Greentown General Hospital (Blood Sciences)  – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)

## Required Tests ##

- Electrolytes – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Liver function – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Cholesterol  – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Full blood count  – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Glycated haemoglobin – FHIR Resource:  [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)

## Specimen(s) ##

- Blood x 3 – FHIR Resource: [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1)

## Test Report ##

- FHIR Resource: [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)

## Test Results ##

- FHIR Resource: [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)