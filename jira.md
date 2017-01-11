# JIRA Cheet Sheet

## Filters

### Custom Filters

By `Add gadget` on dashboard and add following filters, we are able to cascading gadget by ticket status.

The advantage is that it would make tickets work like a pipeline, so that every ticket status change would push it into next stage.

```
assignee = currentUser() AND status in ("To Do") ORDER BY updated DESC
assignee = currentUser() AND status in ("In Progress") ORDER BY updated DESC
assignee = currentUser() AND status in ("Ready For QA") ORDER BY updated DESC
assignee = currentUser() AND status in ("Ready For PO") ORDER BY updated DESC
assignee = currentUser() AND status in ("Deployed") ORDER BY updated DESC
```
