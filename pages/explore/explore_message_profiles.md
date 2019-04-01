---
title: Message Profiles
keywords: message, profiles
tags: [message,fhir,profiles]
sidebar: overview_sidebar
permalink: explore_message_profiles.html
summary: "National Pathology FHIR Message Profiles"
---


## National Pathology FHIR Message Bundle ##

The FHIR message bundle is a collection of FHIR Resource Profiles that have been designed to support the requiements for National Pathology messaging (Haemotology and Chemical Biochemistry).

The message bundle consits of the following FHIR Resource Profiles.

- [CareConnect-ProcedureRequest-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-ProcedureRequest-1) - An NHS Digital Profile that contains the details of the originating procedure requested, for example a GP Practice.

- [CareConnect-DiagnosticReport-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1) - An NHS Digital Profile that contains the test report summary data from the test report. 

- [CareConnect-Specimen-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Specimen-1) - An NHS Digital Profile to capture the specifics of each sample tested by a pathology laboraratory 

- [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) - A CareConnect Profile for an observation. The Observation Resource is used to record the output from a group of tests and the output from a single test.

