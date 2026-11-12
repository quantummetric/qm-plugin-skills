---
name: getting-started
description: Orient to a Quantum Metric connection before answering questions about Quantum Metric data. Use at the start of any Quantum Metric session, when a query returns no data or an error, or when a tool reports an authorization problem.
---

# Getting started with Quantum Metric

Quantum Metric tools run as the signed-in user, with that user's role, permissions, workspace and timezone. The server keeps no state between calls.

## 1. Confirm the context

Call `get_context` first. Tell the user which subscription, workspace and timezone the session is using, in one line, before presenting any numbers.

## 2. Choose the workspace and timezone

- The session starts in the user's current workspace and profile timezone.
- To use a different workspace, call `list_workspaces`, find its ID, and pass that ID as `workspace` on every later call. The workspace applies per call.
- To use a different timezone, pass `timezone` on the tools that accept it.

## 3. Read the server's own guidance

Before building a query, call `search_skills` with the user's topic. Load what it returns with `get_skill` and `load_skill_resource`, and follow it. The server's guidance is the source of truth for query construction, so do not restate it from memory.

## 4. Know the limits

- Quantum Metric tools read and act on data the subscription already collects.
- Requests are for targeted questions. For bulk data movement, point the user to the Quantum Metric API.
- Analytics queries are limited to 120 seconds.
- A tool ignores parameters it does not define. Check the parameter name against the tool definition.

## 5. Fix common problems

| Symptom | What to do |
|---|---|
| Connected, but no tools appear | Restart the client, then confirm the server URL. |
| 401: access token expired, rejected or no longer valid | Sign in to Quantum Metric again from the client. |
| 403 "Session expired or unauthorized" on every call | The subscription is one the signed-in account cannot access. Check the subscription name and sign in with the account that belongs to it. |
| "You do not have access to this feature" on specific tools | The user's role does not include that feature. Ask a Quantum Metric admin to review the role. |
| "Error: no workspace set" | Call `list_workspaces` and pass a workspace ID as `workspace`. |
| Query times out | Narrow the time range, add filters, or run a saved query. |
| Query returns no data | Check the workspace, the time range and the event name. |
