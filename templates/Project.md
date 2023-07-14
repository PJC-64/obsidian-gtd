---
start_date: <% tp.file.creation_date("YYYY-MM-DD") %>
end_date: <!-- Change Me -->
due_date: <!-- Change Me --> 
updated: 2023-02-06T17:18:36+00:00
---

# Project



## General

<!--
	**Add a 'state' under Title, with double-colon to make it a tag.***
	Valid state values:
		#project/active
		#project/done
		#project/archived
-->


### Summary

<!-- Project Summary -->

### Notes 

<!-- Notes about this project and/or general progress that is project-wide rather than tied to an individual action. -->

## Actions Status

### Active

```dataviewjs
const path = require("path")
require(path.resolve(dv.app.vault.adapter.basePath, "000 - Meta/30 - Scripts/dv-script/project-action-active.js"))(dv)
```

### Pending | Available

```dataviewjs
const path = require("path")
require(path.resolve(dv.app.vault.adapter.basePath, "000 - Meta/30 - Scripts/dv-script/project-action-pending-available.js"))(dv)
```

### Completed

```dataviewjs
const path = require("path")
require(path.resolve(dv.app.vault.adapter.basePath, "000 - Meta/30 - Scripts/dv-script/project-action-completed.js"))(dv)
```
