---
title: Business Identifiers
keywords: identifiers
tags: [identifiers,fhir]
sidebar: overview_sidebar
permalink: explore_business_identifiers.html
summary: "Business Identifiers used in National Pathology"
---

## Business Identifiers ##

Resources in National Pathology messages SHOULD be sent with appropriate Business Identifiers.
The National Pathology messaging specification uses the DiagnosticReport, ProcedureRequest, Specimen, Observation resources. These all SHOULD carry business identifiers to allow meaningful search and identification and linking to clinical context.

Business identifiers will consist of:
a Naming System which identifies the identifier namespace
an identifier string, which uniquely identifies the resource within that namespace

There is a preference hierarchy for business identifiers. In order:

### National Identifiers ###
    Existing identifier naming systems for Pathology resources are the HL7 OID identifiers for the PMIP project
    These identifiers COULD be used, but are not recommended.
    
| 2.16.840.1.113883.2.1.4.5.1  | NHS PMIP Specimen Identifier by Requester  | Identifiers of specimens as used by requesters in the UK National Health Service PMIP project  | National Health Service (UK) |
| 2.16.840.1.113883.2.1.4.5.2  | NHS PMIP Specimen Numbers  | Number (or other specific recognisable identifier) used within the Pathology Messaging Implementation Project (PMIP), and other similar messaging projects, to identify specimens.  | NHS UK GP2GP Project |
| 2.16.840.1.113883.2.1.4.5.3  | NHS PMIP Request Numbers  | Number (or other specific recognisable identifier) used within the Pathology Messaging Implementation Project (PMIP), and other similar messaging projects, to identify requests and referrals.  | NHS UK GP2GP Project |
| 2.16.840.1.113883.2.1.4.5.4  | NHS PMIP Request Identifier by Service Provider  | Identifiers of investigation requests as used by service providers in the UK National Health Service PMIP project  | National Health Service (UK) |
| 2.16.840.1.113883.2.1.4.5.5  | NHS PMIP Report Numbers  | Number (or other specific recognisable identifier) used within the Pathology Messaging Implementation Project (PMIP), and other similar messaging projects, to identify reports.  | NHS UK GP2GP Project |

Proposal: Recommend investigation of provision of national Pathology business identifiers at a UK Core, or NHS Digital (England) level.

### Local Identifiers ###
    Where using a local business identifier, vendors and implementers SHOULD register a unique Naming System with HL7 UK.
    Within the Naming System, for each resource, implementers must generate an identifier string which uniquely identifies the resource within that namespace.
    
    Recommend: Use of properly registered local business identifier naming systems is the current recommended approach

### No Business Identifier available ###
    Where no business identifier is available, caution must taken when presenting Test Report resources out of the overall Pathology message context. Where identification of a component resource is only by logical id cross reference, there is a significant risk of loss of clinical context