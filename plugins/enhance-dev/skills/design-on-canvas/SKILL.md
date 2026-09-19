---
name: design-on-canvas
description: Create or revise editable product designs on an Enhance canvas using the product's real screens, components, tokens, and visual language. Use for mocks, screen exploration, and canvas design iteration.
---

# Design on the canvas

Use the installed interface. With MCP, `canvas_write_html`, `canvas_edit`, and `canvas_render` contain executable contracts; use them directly. With only the CLI, `enhance canvas guide` and command help provide the same workflow. For other capabilities, use a complete search result contract or describe the chosen capability when its contract is missing. No second interface is required.

1. Preserve the complete canvas or selection link. Its selected nodes and descendants are the scope; do not substitute all captures or the live browser selection. Reuse known ids, versions, and relevant product references. Read a targeted subtree only when needed information is missing. For an existing product, use its screens, components, styles, and tokens to preserve its visual language.
2. If starting state is unknown, use `capability_query` with `{"capability":"canvas.inspect","input":{"canvasId":"<UUID from the canvas URL>"}}`, or `canvas inspect`. When `nodeCount` is zero, the destination is `root`. Use the returned version to create a populated screen or meaningful group in one HTML write (`canvas_write_html`, or `canvas write-html --review none`). For multiple screens, publish the first populated screen before authoring the next, then publish each subsequent screen separately so the user can see and steer progress. Keep preparation to what that screen needs; do not prepare the whole screen set before the first write. Include content, hierarchy, and layout together. A blank canvas needs no pre-render; an empty shell is not a useful first design. Give important rows, cards, and buttons explicit dimensions; avoid relying on implicit stretch, margins, or inline badge backgrounds. Use block frames for badges. Omit `idPrefix` unless needed; a new import or replacement needs a fresh prefix.
3. For steering such as “change this text and make the card blue,” use one `canvas_edit` / `canvas edit --edits` batch. Keep semantic groups and editable objects; use flex, padding, and gap. Read missing ids rather than rebuilding the screen. Use the version returned by the latest successful read **or write**; reread after a conflict and recompute only the requested change.
4. Render the affected screen when the visual change is ready to review (`canvas_render` or `canvas render`). Inspect pixels for hierarchy, alignment, typography, contrast, overflow and clipping. Correct a concrete discrepancy and render again; avoid repeated inspection with no intervening change. Exercise interactions when a prototype exists.
5. Report what was designed and visually verified, including genuine unresolved ambiguity. A committed receipt proves the write; the inspected render proves the visual review.

A populated group can start with supported inline layout:

```html
<div layer-name="Tasks" style="display:flex;flex-direction:column;width:360px;padding:24px;gap:16px;background:#ffffff">
  <h1 style="font-size:24px;color:#172033">Today</h1>
  <p style="font-size:14px;color:#596579">Three tasks ready to start</p>
  <div layer-name="Task card" style="display:flex;flex-direction:column;padding:16px;gap:8px;background:#eef2ff">
    <h2 style="font-size:18px">Review the design</h2>
    <p style="font-size:14px">Product · Due today</p>
  </div>
</div>
```

Reuse a mutation token only for the identical input. Follow returned remediation. Keep credentials, signed URLs, and private content out of the response.
