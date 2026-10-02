---
name: design-on-canvas
description: Create or revise editable product designs on an Enhance canvas using the product's real screens, components, tokens, and visual language. Use for mocks, screen exploration, and canvas design iteration.
---

# Design on the canvas

Use the installed canvas MCP tools and their returned contracts. The CLI is a separate, broader interface; use its command help when that is the person's chosen interface. MCP work does not require installing or invoking the CLI.

Preserve the complete canvas, page or selection link. Its scope stays authoritative even when the browser's current selection changes. Use `canvas_find` only to resolve an unknown destination. Read the bounded outline with `canvas_read` to locate relevant objects; follow continuations or narrow the root when descendants are omitted. Inspect source or resource views when the task needs captured context, existing styles, images or fonts. Reuse the product's actual visual language.

For new content, insert a complete populated screen or meaningful group with `canvas_insert_html` at an explicit destination and observed revision. An empty canvas needs no pre-render. Publish each populated screen before preparing the next so the person can steer. Prefer concrete inline layout, editable text and useful groups; the HTML compiler reports unsupported content. Use `asset_import` when an authorized image or font needs importing, then use its ready resource reference in the design. Importing a resource does not place it on the canvas.

The versioned HTML reference is the MCP resource `enhance://canvas/html/1` and the package’s `references/canvas-html-v1.md`. Consult it when composing or reconciling HTML; the essential constraints are also in the tool descriptions.

For existing content, obtain a complete editable root with `canvas_read`. Edit its returned HTML and submit it with the original snapshot token through `canvas_update_html`. Preserve retained identity, names and opaque placeholders; new populated subtrees have no retained identity markers. Omission is not implicit deletion: declare intended removals, or use `canvas_remove` for explicit subtree deletion. Use `canvas_arrange` and `canvas_duplicate` for their structural operations rather than rebuilding objects. Keep locked and unsupported content intact.

A pending preparation is not a committed edit. Follow its `operation_status` and returned continuation until the receipt describes the committed objects and revision. Reuse the exact arguments and client token after an uncertain outcome. A conflict requires a fresh scoped read and deliberate replan, not a new token on the same stale edit.

Render the affected content at the committed revision with `canvas_render`, collect pending pixels, and inspect them for hierarchy, typography, alignment, clipping and overflow. Correct a concrete discrepancy and render again. Report what exists, what was visually inspected and any remaining limitation; a successful write alone is not visual verification.
