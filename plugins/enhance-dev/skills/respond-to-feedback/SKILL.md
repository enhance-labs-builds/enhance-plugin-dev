---
name: respond-to-feedback
description: Act on clear Enhance canvas and prototype feedback, implement the underlying change, republish when needed, and verify the result. Use when a user asks to address, resolve, or work through review comments.
---

# Respond to feedback

Use the installed interface: MCP tool contracts or CLI command help. A complete contract returned by search is ready to invoke; describe only when the contract is missing. No second interface is required. For canvas changes use `canvas_edit` / `canvas edit --edits`, preserve selection links, and reuse versions returned by successful writes. Render after a meaningful visual change.

1. Read the canvas, unresolved attention comments, related selections, and current prototype state. Preserve comment wording and authorship.
2. Separate clear actions from ambiguous, conflicting, stale, or already-satisfied feedback. Ask the person only where the intended result cannot safely be inferred.
3. For each clear action, locate the actual owner: editable canvas content, prototype source, or both. Make the smallest complete change in the existing design and code conventions.
4. If source changed, republish the caller-selected build. If canvas content changed, render the affected screen.
5. Compare structure and pixels against the feedback. Exercise the changed interaction, inspect for clipping and regressions, and iterate until it is right.
6. Resolve only comments whose requested outcome is implemented and verified. Leave every ambiguous or incomplete item open and report it precisely.

Never mark feedback complete merely because a mutation succeeded. Follow MCP remediation and never expose credentials, signed URLs, local paths, or private content.
