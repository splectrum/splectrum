---
target: jules-tenbos/splectrum
source: splectrum/spl1
created: 2025-07-30T05:04:00.000Z
description: Task created from splectrum/spl1 issue #041 - Package API Filepath Root Folder Fix
---

---
type: bug
github_id: 5
title: "Amend spl/package API so the package filepaths do not contain root folder"
state: "open"
milestone: "unassigned"
labels: "["bug"]"
priority: high
estimated_effort: TBD
github_updated_at: "2025-07-10T11:15:39Z"
local_updated_at: "2025-07-30T03:49:43.182Z"
---

Currently when a package is created, it prefixes all file and folder paths with the root folder name.
This must be removed as it stops the package being deployed under a different name.
It is better to apply the constraint at the app level - i.e. a package manager app - and leave the core package free to create mix and match new apps.