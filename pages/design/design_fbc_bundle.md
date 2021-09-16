---
title: Examples
keywords: bundle, ITK, tests, battery
tags: [bundle,fhir,profiles, batery, fbc]
sidebar: overview_sidebar
permalink: design_fbc_bundle.html
summary: "National Pathology FHIR Message Full Blood Count Bundle Example"
---

The following example contains a Full Blood Count (FBC) test that is comprised of several component tests peformed on the same specimen. These tests combined form the FBC. The FBC payload is sent as an ITK bundle. This example covers the battery used in Scenario 4.

<script src="https://gist.github.com/IOPS-DEV/f83e4a2f805af0cea5ea2f91f2f68dca.js"></script>

{% include custom/fhir.codegrid.html
relfilepath="ITK-Pathology-FBC-Bundle-Example-1.xml"
title="Full Blood Count Bundle"
type="xml" %}
