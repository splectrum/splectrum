---
target: jules-tenbos/splectrum
source: splectrum/spl1
created: 2025-07-30T05:07:00.000Z
description: Task created from splectrum/spl1 issue #044 - Data Layer Refactor
---

---
type: feature
github_id: 2
title: "Data Layer Refactor"
state: "open"
milestone: "unassigned"
labels: "["documentation","enhancement","Refactor"]"
priority: medium
estimated_effort: TBD
github_updated_at: "2025-07-10T11:15:39Z"
local_updated_at: "2025-07-30T03:49:43.184Z"
---

The data layer needs better specification for its initial operations and requires the consolidation of spl/blob and spl/data.
A new API will be created and the existing one deprecated.
The new API will implement its functionality starting from a strict data layer record definition which contains all the additional metadata to fully describe the data payload and the way it should be treated.