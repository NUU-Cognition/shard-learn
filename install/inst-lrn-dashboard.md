---
id: lrn-dashboard-001
tags:
  - "#dashboard"
  - "#lrn/dashboard"
---

# Learn

Educational content for teaching concepts.

## Active Reports

```dataview
TABLE status, date-created as "Created"
FROM "Mesh/Learn"
WHERE status = "active"
SORT date-created DESC
```

## Drafts

```dataview
TABLE status, date-created as "Created"
FROM "Mesh/Learn"
WHERE status = "draft"
SORT date-created DESC
```

## By Topic

```dataview
TABLE status
FROM "Mesh/Learn"
WHERE status != "archived"
SORT file.name ASC
```
