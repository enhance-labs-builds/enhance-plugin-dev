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
- The description of `canvas_edit` shows how to change text, styles, names and order on layers that are already there, and copy a layer, many in one call. Use it for any change to existing work.
- The description of `canvas_update_html` shows how to rebuild the inside of a layer. Use it only when the structure itself changes.
- The description of `asset_import` shows how to bring in an image or a font.
- The description of `canvas_render` shows how to get a picture of a screen.

## Decide the look before the markup

A change to an existing screen keeps that screen's look. A new screen on a canvas that holds a product's screens takes their fonts, sizes, colours, spacing and corner radii. With no product to follow:

- White background, near-black text and one accent colour, used for the main action and little else, unless the brief asks otherwise.
- Three type sizes, far apart: one large, one body, one small. No text under 13px, and body text at 4.5:1 contrast or more.
- Make the thing that matters most much bigger than the rest. A page of equal cards has no first read.
- Put content straight on the page and separate it with space: tight inside a group, generous between groups. Add a card, border or shadow only to show grouping or something clickable.
- Real words and numbers of realistic length. SVG for icons, not emoji.
- In repeated rows, give icons, values and trailing actions a fixed width, and keep the slot when a row has nothing in it.
- Asked for several directions, change the layout or the idea, not only the accent colour, and keep the content the same.

## Look at what you made

After each screen, and after any change a person would notice, get a picture and check, in this order:

1. Is everything that was asked for there, and readable?
2. Is anything cut off or overflowing its frame? Fix the frame's size or the content's wrapping; do not shrink the text.
3. Do repeated rows line up down the page?
4. Is the first thing you notice the thing that matters most?
5. Is spacing even where it should be even?

Fix what you see with `canvas_edit`, not by rebuilding the screen, then look again.
