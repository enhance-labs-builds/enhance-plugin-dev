# Canvas HTML exchange, version 1

This reference describes the canvas MCP HTML exchange. It is generated from the runtime's checked source and is also available as the MCP resource enhance://canvas/html/1. Tool schemas remain authoritative for arguments and returned outcomes. The broader CLI has its own command help.

## Read and retain identity

Preserve the complete canvas, page or selection reference. Use canvas_read with its editable view and an explicit existing root. An editable read is complete or fails with a narrower-scope remedy; an outline is a different, paginated view. The returned snapshot token binds the scope and observed revision. Submit that exact token and reference with the complete edited root.

Retained containers use div; retained text uses span containing plain text. Each retained element keeps data-enhance-id and data-enhance-name. These IDs identify existing objects; never invent, duplicate or copy them into a new object. You may edit the name. Preserve the original root identity. Existing rich-text formatting is reconciled by the text owner; do not add nested markup to retained text.

Locked and unsupported objects appear as empty opaque placeholders with data-enhance-opaque="true". Keep them unchanged, including their identity and name. Their hidden descendants are not missing content. The native structural tools remain responsible for moves, duplication and removal, including lock and scope checks.

Example returned root (illustrative IDs; use the actual returned IDs):

```html
<div data-enhance-id="frame" data-enhance-name="Settings" style="width:360px"><span data-enhance-id="title" data-enhance-name="Title" style="font-size:24px">Account settings</span><div data-enhance-id="reference" data-enhance-name="Reference" data-enhance-opaque="true"></div></div>
```

## Edit existing content and add new content

Retained elements accept only data-enhance-id, data-enhance-name, data-enhance-opaque and style. Use ordinary inline CSS declarations, with no duplicate property, !important or at-rule. Keep unrelated authored styles. The native style owner validates changes and preserves properties not represented by this projection.

Add a populated new subtree without retained identity or opaque markers. New content goes through the same safe HTML compiler as canvas_insert_html, receives fresh identities. Prefer concrete inline CSS and explicit dimensions for each meaningful group. Do not include scripts, event handlers, embedded executable documents or executable URLs. Available content becomes editable even when fidelity is incomplete. Available assets are retained; unavailable assets do not prevent insertion. Importing an asset does not place it.

Example complete update changing the title and adding a notice:

```html
<div data-enhance-id="frame" data-enhance-name="Settings" style="width:360px"><span data-enhance-id="title" data-enhance-name="Title" style="font-size:24px">Your account</span><div style="width:320px;height:64px;padding:16px;background:#f4f4f5"><span style="font-size:16px">Your changes are saved.</span></div><div data-enhance-id="reference" data-enhance-name="Reference" data-enhance-opaque="true"></div></div>
```

A new subtree cannot contain retained IDs or opaque placeholders in version 1. Insert a container and use canvas_arrange to move retained objects into it. New fragments are compiled independently; do not rely on inherited parent measurements or styles. Use explicit child dimensions and styles, then inspect the committed rendering. For a separate screen, prefer canvas_insert_html at an explicit parent and observed baseVersion.

## Deletion, commitment and recovery

Omission is not implicit deletion. Declare intentional omitted subtrees in removeNodeIds, or call canvas_remove with explicit roots. Locked content prevents the whole invalid edit. A no-op creates no revision. A pending preparation is not a commit: follow operation_status and its continuation until the outcome states whether the canvas changed.

Reuse identical arguments and the same clientToken after an uncertain response. A conflict requires a fresh scoped read and deliberate replan. Do not issue a fresh token merely to bypass the conflict or an unknown outcome. Keep the returned revision and identity mappings. Render the affected root at that revision and inspect its pixels; successful compilation alone is not visual verification.

## Completeness

Submit the complete intended edit. There is no node, source-length or operation-count ceiling. Unsupported optional visual features use the compiler's available representation. Identity, scope, lock and revision checks still govern retained objects and canonical writes.
