---
name: apply-canvas-design
description: Implement an approved or edited Enhance canvas design in the owning product source, republish it, and verify source-to-design fidelity. Use for canvas-to-code or canvas-to-prototype handoff.
---

# Apply a canvas design

Use the installed canvas MCP contracts for product operations and the calling host's development tools for source changes. A hosted MCP does not provide access to a local repository. Use CLI command help only when the CLI is the person's chosen interface.

Preserve the complete page/selection reference. Read the selected design with `canvas_read`, including a complete editable root and relevant resource or captured-source evidence. Render its current revision with `canvas_render` and inspect the pixels. Relate those objects to the actual source owner and current prototype; nearby canvas objects are not evidence of a navigation flow or source mapping.

Identify the intended layout, typography, resource, responsive and interaction changes. Resolve material ambiguity using available context, asking only when the intended result cannot be inferred. Implement the change in the owning framework, component system and tokens. Keep retained source behavior and unrelated product state intact; a detached canvas artifact is not the implementation.

Build with the host's development tools and publish the selected output with `prototype_publish`: a local directory where supported, or an authorized transferred build artifact in a hosted profile. Follow its existing operation and attachment continuation. Retry uncertain publication with identical input and the same intent token; a changed build is a new intent.

Exercise every changed state and viewport in the published result. Compare structure and pixels against the approved design, including text, fonts, layout, clipping, assets and interactions. A screenshot does not prove a route or interaction was tested. Iterate on concrete discrepancies, then report the source changes, attached publication, visual evidence and any explicit remaining difference.
