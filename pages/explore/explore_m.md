---
title: Template for explore. Replace with you page name
keywords:  messaging, bundles
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_m.html
summary: "Summary description"
---

{% include important.html content="The links below will refer to the StructureDefinition url applied to the FHIR profile, which are not yet active. For queries please refer to the Help and Support section." %} 

The following FHIR profiles are used to form the Your Message:

- [DM-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/DM-Bundle-1)
- [DM-MessageHeader-1](https://fhir.nhs.uk/STU3/StructureDefinition/DM-MessageHeader-1)
- [CareConnect-DM-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-DM-Organization-1)
- [DM-HealthcareService-1](https://fhir.nhs.uk/STU3/StructureDefinition/DM-HealthcareService-1)
- [CareConnect-DM-Patient-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-DM-Patient-1)
- [CareConnect-DM-Encounter-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-DM-Encounter-1)
- [CareConnect-DM-Location-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-DM-Location-1)
                                                                                                   
### Your message name data item mapping to FHIR profiles ###

The example message data items are fulfilled by elements within the FHIR resources listed below:

| DM Data Item            | FHIR resource element                                 | Mandatory/Required/Optional |
|--------------------------|-------------------------------------------------------|-----------------------------|
| Local Patient Identifier | CareConnect-DM-Patient-1.identifier (localIdentifier) | Mandatory                   |
| Town of Birth            | CareConnect-DM-Patient-1.birthPlace                  | Required                    |
| Country of Birth         | CareConnect-DM-Patient-1.birthPlace                  | Required                    |
| Communication Preference | CareConnect-DM-Patient-1.telecom.system              | Required                    |
| Patient email address    | CareConnect-DM-Patient-1.telecom.value               | Required                    |
| Ethnicity                | CareConnect-DM-Patient-1.ethnicCategory              | Required                    |
| Religion                 | CareConnect-DM-Patient-1.religiousAffiliation        | Required                    |
| Marital Status		   | CareConnect-DM-Patient-1.maritalStatus				   | Required					 |

