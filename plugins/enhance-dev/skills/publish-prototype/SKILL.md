---
name: publish-prototype
description: Publish a local product build to an Enhance canvas and visually verify the complete prototype. Use when a user asks to publish, attach, refresh, preview, or validate a prototype from a build folder.
---

# Publish a prototype

Use the installed interface: MCP tool contracts or CLI command help. A complete contract returned by search is ready to invoke; describe only when the contract is missing. No second interface is required. For canvas changes use `canvas_edit` / `canvas edit --edits`, preserve selection links, and reuse versions returned by successful writes. Render after a meaningful visual change.

1. Read the target canvas and current prototype state before changing anything.
2. Ask for the intended local build directory if the person has not selected one. Never guess a directory or publish an unrelated working tree.
3. Preflight the complete folder, then publish and attach it to the intended canvas. Reuse a mutation token only when retrying the identical input after an ambiguous outcome.
4. Open the published prototype through Enhance, exercise every specified state and interaction, and render representative desktop and mobile states.
5. Inspect the rendered pixels for clipping, overflow, missing assets, broken routes, console failures, and visual drift. A successful upload is not completion.
6. Correct actionable failures, republish, and repeat the inspection. Report the public result and any explicit unresolved limitation.

Follow remediation returned by MCP. Keep credentials, signed URLs, local paths, and customer content out of the response.
