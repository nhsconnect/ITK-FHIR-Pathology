---
title: Scenarios 5 
keywords:  test
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: engage_scenario5.html
summary: "Split Test Request, Different Sample Types"
---

{% include warning.html content="This **temporary** site is provided to assist with the development of the **Alpha** Specification and is being updated regularly. It is advised not to develop against these specifications until a formal announcement has been made." %}

**Description**

Susan Allen is a 25 year old woman with type 1 diabetes. Susan is seen for a review in a diabetes clinic at her local hospital, Oldhampton Royal Infirmary. The diabetes nurse, Mike Black, requests blood and urine tests: full blood count, electrolytes, glycated haemoglobin, cholesterol and triglycerides and urine albumin and urine for microbiology (Microscopy, Culture and Sensitivity – MC&S). Mike takes blood samples and sends them to the pathology laboratory based in the hospital. 

The patient is given a paper request form for the urine samples. The following day she takes the samples and request form to her GP surgery, Newgate GP Practice. The samples are sent from the GP surgery to the laboratory. 

The samples are received by the laboratory, checked and matched with the test requests. The details are recorded on the Laboratory Information Management System (LIMS).

The tests are performed, and the results are authorised for release. The following test results (and reference ranges) are sent electronically from the LIMS to the hospital’s EPR system:

|----------------------|-----------------|-----------------|
|**Full Blood Count**|
|Haemoglobin|	134 g/L	|(115 to 150)
|White Blood Count|	6.1 10^9/L	|(3.5 to 11.0)
|Platelets|	143 10^9/L	|(140 to 400)
|Haematocrit (PCV)|	0.372 Ratio	|(0.36 to 0.46)
|Red Blood Count	|4.23 10^12/L	|(3.80 to 5.00)
|Mean Cell Volume|	87.9 fL	|(80.0 to 99.0)
|Mean Cell Haemoglobin|	31.7 pg	|(27.5 to 32.5)
|Mean Cell Haemoglobin Conc.|	360 g/L	|(310 to 350)
|Neutrophils|	4.02 10^9/L	|(1.70 to 8.00)
|Lymphocytes	|1.45 10^9/L	|(1.00 to 4.00)
|Monocytes|	0.56 10^9/L	|(0.20 to 0.80)
|Eosinophils|	0.06 10^9/L	|(0.04 to 0.40)
|Basophils|	0.03 10^9/L	|(0.02 to 0.10)
|Nucleated RBCs	|0.0010^9/L	||
|Red Cell Distribution Width	|^14 %	|(11.6 to 13.9)
|Mean Platelet Volume|	^13.0 fL	|(7.1 to 10.7)

<table style="width:100%">
  <tr>
    <th colspan="3">Electrolytes and Creatinine Profile</th>
  </tr>
  <tr>
    <td style="width:33%">Sodium</td>
    <td style="width:33%">143 mmol/L</td> 
    <td style="width:33%">(133 to 146)</td>
  </tr>
  <tr>
    <td style="width:33%">Potassium</td>
    <td style="width:33%">4.5 mmol/L</td> 
    <td style="width:33%">(3.5 to 5.3)</td>
  </tr>
   <tr>
    <td style="width:33%">Chloride</td>
    <td style="width:33%">107 mmol/L</td> 
    <td style="width:33%">(95 to 108)</td>
  </tr>
   <tr>
    <td style="width:33%">Creatinine</td>
    <td style="width:33%">58 umol/L</td> 
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
|Acute Kidney Injury|0|

|----------------------|-----------------|-----------------|
|**Glycated haemoglobin**
|HbA1c (IFCC)|45 mmol/mol|(18 to 41)|

|----------------------|-----------------|-----------------|
|**Liver function tests**||
|Total Bilirubin|	13 umol/L|	(0 to 21)|
|Alkaline Phosphatase|	83 IU/L|	(30 to 130)|
|Alanine Transaminase|	27 IU/L	|(0 to 40)|

|----------------------|-----------------|-----------------|
|**Cholesterol and Triglycerides**
|Cholesterol|7.7 mmol/L||
|Triglycerides	|6.9 mmol/L|	(0 to 1.7)
|HDL Cholesterol|	0.8 mmol/L	
|TC/HDL ratio|	9.6	|(0 to 5)
|Non-HDL Cholesterol|	6.9 mmol/L	|


|----------------------|-----------------|-----------------|
|**Urine Albumin and Urine**
|Urine Creatinine	|4.2 mmol/L	|
|Urine Albumin|	<3 mg/L|	(3 to 20)
|Albumin/creatinine ratio|	Not applicable	



## Named participants ##

- Patient: Patient: Susan Allen – FHIR Resource: [Patient](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1)
- Requesting HCP: Mike Black  – FHIR Resource:  [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)
- Specimen Collecting HCP: Mike Black  – FHIR Resource: [Practitioner](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1)

## Named Organisations ##

- Requesting Organisation: Oldhampton Royal Infirmary (Diabetes Clinic) – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Specimen Collecting Organisation: Newgate GP Practice  – FHIR Resource: [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)
- Performing Organisation: Oldhampton Royal Infirmary (Blood Sciences)  – FHIR Resource:  [Organization](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1)

## Condition ##

- Hypertension – FHIR Resource:  [Condition](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1)

## Required Tests ##

- Glycated haemoglobin – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Full blood count – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Electrolytes – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Cholesterol – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Triglycerides – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
 -Urine albumin – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)
- Urine MC&S – FHIR Resource: [ProcedureRequest](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1)

## Specimen(s) ##

- Blood – FHIR Resource: [Specimen](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1)

## Test Report ##

- FHIR Resource: [DiagnosticReport](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1)

## Test Results ##

- FHIR Resource: [Observation](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1)