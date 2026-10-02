---
name: respond-to-feedback
description: Act on clear Enhance canvas and prototype feedback, implement the underlying change, republish when needed, and verify the result. Use when a user asks to address, resolve, or work through review comments.
---

# Respond to feedback

Use the installed canvas and feedback MCP contracts. Use the calling host's source/browser tools where needed; MCP work does not require installing a CLI. If the person chooses the CLI, its command help describes that interface.

Preserve the complete canvas, page or selection link. Use `feedback_read` to read unresolved threads in that scope, then read the needed message and anchor details. Follow every required continuation: a summary, truncated body or incomplete anchor is not the full feedback. Preserve wording, authorship and observed thread revisions. Read the referenced canvas objects and relevant source/prototype state rather than treating canvas proximity as an anchor.

Separate clear actions from ambiguous, conflicting, stale or already-satisfied feedback. Resolve intent from available evidence; ask only where the intended result remains material and uncertain. Locate the actual owner: editable canvas content, prototype source or both.

For canvas edits, read a complete editable root and use `canvas_update_html`, preserving identity and opaque content; use the structural tools when appropriate. For source edits, change the owning implementation and publish the selected build with `prototype_publish`. Retry uncertain writes with identical arguments and intent tokens. Follow returned operation continuations; a prepared plan or ready deployment alone does not prove the requested canvas change happened.

Render changed canvas content at its committed revision and inspect the pixels. Exercise changed prototype behavior through the host's browser. Check the outcome against the actual feedback, including clipping, missing assets and unrelated regressions.

Reply with concise completion evidence through `feedback_reply` when responding to the thread is part of the request. Resolve through `feedback_set_resolved` only after the requested outcome is implemented and verified. Use the observed thread revision: a new reply or moved anchor requires reading again before deciding whether resolution is still appropriate. Keep ambiguous, incomplete or unverified items open and report their specific remaining work.
