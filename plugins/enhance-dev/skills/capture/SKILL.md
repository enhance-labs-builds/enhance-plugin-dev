---
name: capture
description: Put the screens a thread is changing onto an Enhance canvas as editable frames and return the link. Use when asked to capture, share or review screens, or to put work on a canvas. Also applies whenever a thread has changed how a screen looks: when that work is done, offer once, in one line, to put the changed screens on an Enhance canvas for review, and capture only on a yes.
---

# Capture screens to Enhance

Put each screen this thread is changing onto one Enhance canvas as an editable frame, and return the canvas link. The person should see their first screen within a couple of minutes and the whole set within five.

A capture is cheap and can be redone, so capture each page as soon as it is in the state you want, as it is, at whatever size it has. When a state needs data, such as an account or a finished step, make it yourself where the app runs, with its seed script or its own API, rather than asking the person. Place each page as soon as you capture it, and give the person the link with the first one. For a whole flow, walk it once and capture as you go.

## Tools

- `canvas_create` with a `title` of what this thread is changing makes the canvas and answers with its id and its link.
- `canvas_capture_page` puts one page on the canvas. Its description gives the two calls one capture takes. Read it before the first capture.
- `connection_status` says who is signed in. If nobody is, call `connection_connect`.
