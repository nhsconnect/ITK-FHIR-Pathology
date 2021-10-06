---
title: Related Tests
keywords: test
tags: [test,fhir]
sidebar: overview_sidebar
permalink: explore_related_tests.html
summary: "Related Tests in National Pathology"
---

## Related Tests ##

Related tests in National Pathology messages.

The .related element within the Observation resource allows cross-referencing of individual test results within a National Pathology message payload.

The type of cross-reference is described using the required HL7 codesystem [codesystem-observation-relationshiptypes](http://hl7.org/fhir/stu3/codesystem-observation-relationshiptypes.html).

This codesystem has possible values: has-member \| derived-from \| sequel-to \| replaces \| qualified-by \| interfered-by

Thus:
```
<related>
    <type value="has-member" />
    <target>
        <reference value="urn:uuid:dacb177a-9501-4dcc-8b22-b941791ae0db"/>
    </target>
</related>
```

Examples within this document with test panel payloads illustrate usage of the 'has-member' relation


### Related types ###
* has-member is used for test batteries, panels or sets of measurements. For example, a FBC (full blood count) would have members capturing Red blood cell count, Total white cell count, Mean corpuscular haemoglobin concentration, etc.

* derived-from is used to reference observations or measurements that allow the determination of another i.e. from which this observation value is derived. These might be inputs to a calculation or simply supporting evidence. For example constituent observations contributing to a NEWS2 or APGAR score.

Other related observation types are defined as per the HL7 codesystem [codesystem-observation-relationshiptypes](http://hl7.org/fhir/stu3/codesystem-observation-relationshiptypes.html).
