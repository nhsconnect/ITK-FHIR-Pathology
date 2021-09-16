---
title: Examples
keywords: bundle, ITK, tests, battery
tags: [bundle,fhir,profiles, batery, fbc]
sidebar: overview_sidebar
permalink: design_renal_bundle.html
summary: "National Pathology FHIR Message Full Blood Count Bundle Example"
---

The following example contains a Electrolyte and Creatinine tests comprises of several component tests peformed on the same specimen. These tests combined form a Electrolyte and Creatinine Profile. The payload is sent as an ITK bundle. This example is closely related to Scenario 2 in this Implemenation guide.

<script src="https://gist.github.com/IOPS-DEV/47f27c71bec859182cde2f9368deda77.js"></script>

{% include custom/fhir.codegrid.html
relfilepath="ITK-Renal-Test-Bundle-Example-1.xml"
title="Renal Test Bundle"
type="xml" %}
