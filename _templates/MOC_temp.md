---
title: {{title}}
draft: false
tags:
- example-tag
---
*up::* [[Home]]
*tags::* #map
# {{title}}

## Data View
%%everything that has a reference to this MOC%%
```dataview
table
WHERE contains(file.outlinks, this.file.link) AND contains(file.path, "/") AND !contains(file.path,"_templates")
```