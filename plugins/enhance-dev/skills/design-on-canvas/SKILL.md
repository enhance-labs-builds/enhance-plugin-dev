---
name: design-on-canvas
description: Create or revise editable product designs on an Enhance canvas using the product's real screens, components, tokens, and visual language. Use for mocks, screen exploration, and canvas design iteration.
---

# Design on the canvas

Create or change editable screens on an Enhance canvas, look at what you made, and give the canvas link.

## Tools

- `canvas_create` with a `title` makes a canvas and answers with its id and its link.
- The description of `canvas_read` shows how to read what a canvas holds: its outline, or one screen as HTML.
- The description of `canvas_insert_html` shows how to add a screen as HTML, with an example. Read it before the first insert.
- Give a new top-level screen `"placement": {"kind": "auto"}` so Enhance puts it in free space, unless the person gave coordinates. Place the next screen of a sequence with `{"kind": "near", "anchorNodeId": "<the previous screen's id from its answer>", "side": "right"}`.
- The description of `canvas_edit` shows how to change text, styles, names and order on layers that are already there, and copy a layer, many in one call. Use it for any change to existing work.
- The description of `canvas_update_html` shows how to rebuild the inside of a layer. Use it only when the structure itself changes.
- The description of `asset_import` shows how to bring in an image or a font.
- The description of `canvas_render` shows how to get a picture of a screen.
- The description of `canvas_finish_working` shows how to say that you have finished, so your mark leaves the canvas.

## Start by looking

Read the canvas outline first: its screens, their widths, and what the person has selected.

A change to an existing screen keeps that screen's look. A new screen on a canvas that holds a product's screens follows those screens first: their fonts, sizes, colours, spacing and corner radii. The rules for the look below are for a screen with no product to follow.

## Tell the person your brief

Before the first write, tell the person your design brief in a few lines: the moods you considered and the one you chose, five or six colours with their roles, the type, and the direction in one line. Skip it only when the brief or the product already fixes the design.

- Moods: name three or four mood words, and choose one that is not the first that came to mind. Say in a few words why it fits better.
- Colours: picture a scene for that mood, and take each colour from an object in it. Pure white is the usual ground, and one strong colour carries the screen.
- Type: a display face and a text face, with their sizes.
- Direction: one line on the layout idea.

## Decide the look

- Few elements, each doing work. Make the thing that matters most much bigger than the rest; a page of equal cards has no first read.
- Pair heavy display type with light, small labels, as an editorial page does. Use three type sizes, far apart.
- Vary the spacing: tight inside a group, generous between groups. Prefer an asymmetric layout to a centred one when the content allows.
- Put content straight on the page. Add a card, border or shadow only to show grouping or something clickable, and leave out dated gradients and heavy shadows.
- Light mode unless asked. No text under 13px, and text under 16px at 4.5:1 contrast or more.
- A product screen should be clear at a glance. Brand and marketing work should impress, and can be playful. When the brief is vague, aim to impress.
- Real words and numbers of realistic length. SVG for icons, not emoji.
- Asked for several directions, change the layout or the idea, not only the colours, and keep the content the same.

## Fonts, units and sizes

- Use the canvas's fonts or import one; put an @font-face whose src is the path the import returned in each write that uses it, since the family name alone draws a fallback. If you cannot, use the closest, say so, and go on. Set font sizes and line heights in px, and letter spacing in em.
- Start a new screen at 1440 by 900 for desktop, 768 by 1024 for tablet or 390 by 844 for mobile, unless the brief or the product says otherwise; the height is only a starting point.
- A mobile screen starts with the status bar of the guide's `mobile-status-bar` topic, pasted as its first child; never draw one by hand.

## Write a group at a time

- Write one visual group per call, about 15 lines of HTML, so the screen grows in view.
- Write inline styles with flex, padding and gap, and a layer-name attribute on each element, since other name attributes are dropped; set the font family on each group, since a group does not take it from the layer it goes into. No margins, grids or tables.
- For repeated rows, write the container together with its first row, then copy that row with `canvas_edit` and change its text, rather than write the same HTML again. Read the copy's layers for their ids; never guess an id.
- In repeated rows, give icons, values and trailing actions a fixed width, and keep the slot when a row has nothing in it. After three similar rows, look at a picture and check that the slots line up down the page.
- To restructure, move layers with `canvas_edit`; never delete a layer and write it again.

## Look at what you made

After each section, get a picture of the screen, check it against the review list, and tell the person one line that starts with "Review:". Use scale 1 for layout; use 2 only to read small text. For more detail, get a picture of a smaller layer. The review list, in order:

1. Spacing: is it even where it should be even, tight in groups and generous between them?
2. Type: are there few sizes, far apart, and none under 13px?
3. Contrast: can all text be read against its ground, at 4.5:1 or more under 16px?
4. Alignment: do edges and repeated rows line up down the page?
5. Fit: is anything cut off or overflowing its frame?
6. Repetition: do repeated items match one another, with no stray one?
7. Is everything that was asked for there?

Fix what a picture shows with small edits, not by rebuilding the screen: starting again throws away work the person has watched, and content that overflows is never a reason to delete a frame. When a frame cuts its content off, set its height to fit its content with the style "height": "hug"; never guess a new fixed height. Then look again.

## When you have finished

When you have finished, call finish, naming the screens or none; if refused, go on. Then give the canvas link. Never show layer ids to the person; name screens and layers by what they are.
