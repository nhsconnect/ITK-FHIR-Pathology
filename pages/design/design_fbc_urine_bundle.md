---
title: Examples
keywords: bundle, ITK, tests, battery
tags: [bundle,fhir,profiles, batery, fbc]
sidebar: overview_sidebar
permalink: design_fbc_urine_bundle.html
summary: "National Pathology FHIR Message Full Blood Count and 24hr Protien Test (Urine) Bundle Example"
---

The following example contains two tests on two specimens. A Full Blood Count (FBC) test that comprises of several component tests peformed on the same venous blood specimen. These tests combined form the FBC and are part of a group test (battery/panel/profile). 

An additional 24 hour urine protein output test is also included. Both tests are part of the same Diagnostic Report and are inlcuded within the same payload, which is sent as an ITK bundle. 

This example takes elements from Scenario 5.

<script src="https://gist.github.com/IOPS-DEV/9b232a3cb28e8d7bf79b5fb568a97e91.js"></script>