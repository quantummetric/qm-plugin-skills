---
name: data-analysis
description: Answer questions about funnels, conversion, errors, friction, traffic and trends using Quantum Metric. Use for any request that needs a number, a breakdown, a drop-off or a comparison from Quantum Metric data.
---

# Analyzing Quantum Metric data

Work in this order. Each step prevents a plausible but wrong answer.

## 1. Orient

If `getting-started` has not run in this conversation, run it first. The workspace, time range and timezone must be known before any number is reported.

## 2. Reuse what already exists

Before building a new query, look for a definition that already answers the question:

- `list_saved_queries` for saved queries
- `list_funnels` for funnels
- `list_dashboards`, then `get_dashboard` and `execute_dashboard_card` for dashboard cards
- `list_concepts` and `get_concept` for business concepts configured in the subscription

When a match exists, run it with `run_saved_query`, `run_funnel` or `execute_dashboard_card` instead of rebuilding it.

## 3. Resolve names to real objects

- Pages: `discover_page_candidates` turns a page name into an analytics filter.
- Events: `list_events`, `get_event` and `search_event_values`.
- Metrics and dimensions: `catalog_metrics` and `catalog_summary`.

Never guess an event name, page name or metric name. Use the values the tools return.

## 4. Run the analysis

- Ad-hoc questions: `run_query`.
- Funnel drop-off: `run_funnel` and `analyze_funnel_dropoff`.
- Use explicit dates. State the time range in the answer.

## 5. Verify before answering

Check that what ran matches what was asked:

- The right measure: count, rate, unique sessions or unique users.
- The right population: the filters, segment and workspace that applied.
- The right period and timezone.

If the question and the query differ, fix the query and run it again.

## 6. Report

- Report only numbers returned by a tool. Do not estimate, extrapolate or combine results from different populations.
- Say when a result is empty or limited.
- Include the links the tools return for dashboards, sessions and replays.
- To explain a number, hand off to `session-review` with example sessions.
