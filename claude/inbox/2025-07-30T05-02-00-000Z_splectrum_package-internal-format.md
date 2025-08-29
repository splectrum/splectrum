---
target: jules-tenbos/splectrum
source: splectrum/spl1
created: 2025-07-30T05:02:00.000Z
description: Task created from splectrum/spl1 issue #039 - Create Package Internal Format
---

---
type: feature
github_id: 7
title: "Create Package Internal Format"
state: "open"
milestone: "unassigned"
labels: "["enhancement"]"
priority: medium
estimated_effort: TBD
github_updated_at: "2025-07-10T11:15:40Z"
local_updated_at: "2025-07-30T03:49:43.179Z"
---

Module and data packages feature a map external format suitable for deployment management.
This data has to be broken down in an internal avro format - the native internal data structure.

I think it is possible to cover both functional and data (template) packages with the same avro schema.

Design the data and folder structures for both and put assets into place.
The Package API needs import and export methods into the internal native structure.
I don't think another specific interface is needed - the internal format can be dealt with using the Record API.