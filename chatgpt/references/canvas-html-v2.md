# Canvas HTML exchange, version 2

This reference describes the canvas MCP HTML exchange. It is generated from the runtime's checked source and is also available as the MCP resource enhance://canvas/html/2. Tool schemas remain authoritative for arguments and returned outcomes. The broader CLI has its own command help.

## Read and retain identity

Preserve the complete canvas, page or selection reference. Use canvas_read with its editable view and an explicit existing root. An editable read is complete or fails with a narrower-scope remedy; an outline is a different, paginated view. The returned snapshot token binds the scope and observed revision. Submit that exact token and reference with the complete edited root.

Each layer's element carries the CSS the editor paints for it: its fills, border, radius, shadows, filters, background blur, opacity, blend and isolation, under the CSS authored on it. Frames, groups, rectangles, ellipses, images and the root are div elements. An image's source is its background-image, painted once; a written background-image URL, background-size (100% 100%, cover, contain or auto) or background-position changes its source, fit or position. Vectors, polygons, stars and Boolean groups are an svg element holding one path, whose d, fill-rule and fill are the layer's path and its one solid fill. Text is a span; rich text holds one span per run, each marked with data-enhance-run and its place, and carrying that run's CSS. Each retained element keeps data-enhance-id and data-enhance-name. These IDs identify existing objects; never invent, duplicate or copy them into a new object. You may edit the name. Preserve the original root identity.

A border or outline that the editor draws on its own element appears as a child element with data-enhance-paint="border" or "outline" and that element's CSS; the layer's own element then has none of that CSS. On that element you may change mix-blend-mode, the blend of its one paint, and, for a dashed stroke, the stroke-dasharray and stroke-linecap inside its mask-image, which set the dash pattern and cap; the rest of it follows the border or outline. A mask group's element carries the CSS mask made from its mask source (an alpha, luminance or outline mask); the mask source stays a child.

Locked layers are read with their CSS and data-enhance-locked="true"; every change to them is refused. Screens, recordings and prototypes are sealed: empty opaque placeholders with data-enhance-opaque="true", their pixels coming from a recorded page, a recording or a running build. Layer kinds without an HTML form yet are sealed the same way. The read gives each sealed layer's reason in sealedReasons. Keep opaque placeholders unchanged, including their identity and name. Their hidden descendants are not missing content. The native structural tools remain responsible for moves, duplication and removal, including lock and scope checks.

Example returned root (illustrative IDs; use the actual returned IDs):

```html
<div data-enhance-id="frame" data-enhance-name="Settings" style="width:360px"><span data-enhance-id="title" data-enhance-name="Title" style="font-size:24px">Account settings</span><div data-enhance-id="reference" data-enhance-name="Reference" data-enhance-opaque="true"></div></div>
```

## Edit existing content and add new content

Retained elements accept only data-enhance-id, data-enhance-name, data-enhance-opaque, data-enhance-locked and style; an svg element also keeps its viewBox and preserveAspectRatio. Use ordinary inline CSS declarations, with no duplicate property, !important or at-rule. Keep unrelated CSS unchanged; only what you change is written.

Writing a CSS property that a native setting paints replaces that setting: the setting is cleared and the layer keeps your CSS. Writing a mask group's mask CSS makes it an ordinary group with that CSS, and its former mask source paints as an ordinary child. Writing a path's d makes the layer a vector with that path; a Boolean group gives up its operands. A run span's words, color and CSS change only that run; a run has no blend of its own, so set mix-blend-mode on the text layer. On a paint element only mix-blend-mode changes, as that paint's blend; change the rest through the layer's border or outline CSS.

Add a populated new subtree without retained identity or opaque markers. New content goes through the same safe HTML compiler as canvas_insert_html, receives fresh identities. Prefer concrete inline CSS and explicit dimensions for each meaningful group. Do not include scripts, event handlers, embedded executable documents or executable URLs. Available content becomes editable even when fidelity is incomplete. Available assets are retained; unavailable assets do not prevent insertion. Importing an asset does not place it.

Example complete update changing the title and adding a notice:

```html
<div data-enhance-id="frame" data-enhance-name="Settings" style="width:360px"><span data-enhance-id="title" data-enhance-name="Title" style="font-size:24px">Your account</span><div style="width:320px;height:64px;padding:16px;background:#f4f4f5"><span style="font-size:16px">Your changes are saved.</span></div><div data-enhance-id="reference" data-enhance-name="Reference" data-enhance-opaque="true"></div></div>
```

A new subtree cannot contain retained IDs or opaque placeholders. Insert a container and use canvas_arrange to move retained objects into it. New fragments are compiled independently; do not rely on inherited parent measurements or styles. Use explicit child dimensions and styles, then inspect the committed rendering. For a separate screen, prefer canvas_insert_html at an explicit parent and observed baseVersion.

## Deletion, commitment and recovery

Omission is not implicit deletion. Declare intentional omitted subtrees in removeNodeIds, or call canvas_remove with explicit roots. Locked content prevents the whole invalid edit. A no-op creates no revision. A pending preparation is not a commit: follow operation_status and its continuation until the outcome states whether the canvas changed.

Reuse identical arguments and the same clientToken after an uncertain response. A conflict requires a fresh scoped read and deliberate replan. Do not issue a fresh token merely to bypass the conflict or an unknown outcome. Keep the returned revision and identity mappings. Render the affected root at that revision and inspect its pixels; successful compilation alone is not visual verification.

## Completeness

Submit the complete intended edit. There is no node, source-length or operation-count ceiling. Unsupported optional visual features use the compiler's available representation. Identity, scope, lock and revision checks still govern retained objects and canonical writes.
