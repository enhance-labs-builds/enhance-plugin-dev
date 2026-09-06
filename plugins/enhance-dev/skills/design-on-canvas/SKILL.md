---
name: design-on-canvas
description: Create or revise editable product designs on an Enhance canvas using the product's real screens, components, tokens, and visual language. Use for mocks, screen exploration, and canvas design iteration.
---

# Design on the canvas

Use the live Enhance MCP catalogue for executable detail. Search for likely actions; scan the catalogue when the task is broad. Describe every selected capability before invoking it.

1. Preserve the scope of a pasted selection link: every `selection` parameter names a requested node, and only those nodes and their descendants are in scope. Inspect and edit those IDs; never substitute all captures or the live browser selection. With the CLI, retain the complete link as `--canvas` throughout the task. Read the brief, canvas structure, current prototype, relevant captured screens, reusable components, styles, and tokens. For an existing product, derive its language rather than substituting generic UI.
2. Identify the intended screen states, responsive variants, content, hierarchy, and interactions before authoring.
3. Create or edit native, semantic canvas objects. Reuse established components and tokens; keep meaningful grouping, names, layout, and editability.
4. Render the whole affected screen at representative viewport sizes. Inspect pixels as well as structure for hierarchy, alignment, typography, contrast, overflow, clipping, and empty or loading states.
5. Iterate on discrepancies and re-render. Exercise interactions where a prototype exists.
6. Report what was designed, the states verified, and any genuine ambiguity that still needs a decision.

Do not treat a successful write or an accessibility-tree match as visual verification. Follow MCP remediation; never expose credentials, local paths, signed URLs, or customer content.
