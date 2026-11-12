---
name: session-review
description: Investigate one Quantum Metric session, or a small set of sessions, to explain what a user experienced. Use for a bug report, a complaint, a replay link or a session ID, and to find evidence behind a number.
---

# Reviewing Quantum Metric sessions

Sessions explain a number. They do not produce one.

## 1. Orient

If `getting-started` has not run in this conversation, run it first.

## 2. Start with the summary

Call `get_session_summary` with the session ID or URL. It gives the overall journey, errors and friction. For a user rather than a session, call `get_user_summary`.

## 3. Go deeper only where the summary points

- `get_session_hits` for the page-level and event-level detail around a moment.
- `get_replay_screenshot` to see the screen at a moment.
- `get_session_replay_urls` for replay links to share.

Read long session detail inside a `session-reader` subagent when the client supports subagents, and return only the answer to the main conversation.

## 4. Report what the session shows

- Describe the sequence of events and the point where the experience broke.
- Quote errors and values exactly as the tools return them.
- If a tool call fails or the data is unavailable, say so. Do not reconstruct events.
- Include the replay link for every session discussed.

## 5. Look across sessions

For a pattern, review three to five sessions from the affected group. Report what they have in common and how many were reviewed. Run `data-analysis` to size the pattern across all sessions.
