---
name: publish-prototype
description: Publish a selected product build to an Enhance canvas and visually verify its prototype. Use for publishing, attaching, refreshing or validating a local build folder or an authorized uploaded build artifact.
---

# Publish a prototype

Use the installed `prototype_publish` contract. Local and hosted input acquisition differ; the native publication and canvas attachment lifecycle is the same. MCP work does not require a separate CLI. When the person chooses the CLI, use its command help.

Preserve the complete target canvas or page link and read its current outline and prototype state. Reuse the observed revision and the intended existing prototype when refreshing it. Do not silently create a second prototype to avoid an attachment conflict.

Acquire exactly the build the person selected. A local runtime accepts a build directory that the calling host can access. A hosted runtime accepts an authorized file reference when its listed contract provides that capability; use the host's supported artifact selection or upload flow. A local path is not a hosted artifact. If the input has not been selected, ask for it. If transfer is unavailable, explain the missing capability without pretending a server can read the person's computer.

Publish with a fresh intent token. Retry an uncertain result with identical arguments and the same token. Follow `operation_status` and the returned continuation for pending ingestion or attachment. Deployment readiness and canvas attachment are distinct: recover an attachment conflict against the current canvas using the ready deployment, rather than uploading the build again. Report the actual outcome if either stage remains incomplete.

Open the published prototype through Enhance, exercise the requested routes, states and interactions using the calling host's browser capabilities, and inspect representative viewport pixels. Check missing assets, navigation, console failures, overflow and visual drift. A ready deployment is not proof that interactions were exercised. Fix defects in the owning source, build again and republish when that work is within the request; otherwise describe the specific remaining defect.

Finish with the authorized prototype/canvas link and what was verified. Do not include credentials or temporary signed transfer URLs.
