# Agora

**An installable desktop environment for Linux and the BSDs — the Cocoa stack, a Mac-like desktop,
and its applications: written in Objective-C, built from source.**

**→ [agoradesktop.github.io](https://agoradesktop.github.io)**

---

Agora is three things that compose into one whole:

1. **The Cocoa stack** — Core Foundation, Foundation, Core Graphics, Core Text and the Application
   Kit, implemented in Objective-C. Behavioural and API compatibility is the goal: an Objective-C
   program written against the documented Cocoa surface builds and runs against Agora's stack.
2. **A Mac-like desktop** — a window server and shell whose behaviour matches Mac OS X's window
   management: client-side window chrome, a system-owned menu bar, a dock, a desktop with icons,
   sheets, and the drag-and-drop session.
3. **Applications** — a reference set (document, text, grid/formula, presentation, canvas, image)
   written against the stack, shipped as the desktop's content.

Everything is compiled from source with `clang`, on **Linux, FreeBSD, NetBSD and OpenBSD**.

## Status

**Design.** The component repositories exist; no Agora-written code yet.

**[The design record](https://github.com/AgoraDesktop/Agora)** is the top-level statement of what
Agora is and how its repositories are organised — read that first. It also carries the build
conventions: clang only, every library shared, no systemd, no vendored ICU or OpenSSL.

## The components

One component, one repository — Agora is a federation of small repositories, not a monolith.
Reusable libraries are `libagora-<domain>`; programs take a plain kebab-case name.

### The Cocoa stack

| repository | what it is |
|---|---|
| [`libagora-core`](https://github.com/AgoraDesktop/libagora-core) | Core Foundation — the C core: strings, collections, run loops |
| [`libagora-base`](https://github.com/AgoraDesktop/libagora-base) | Foundation — Objective-C collections, strings, dates, files, notifications |
| [`libagora-drawing`](https://github.com/AgoraDesktop/libagora-drawing) | Core Graphics — the 2D drawing and geometry model |
| [`libagora-text`](https://github.com/AgoraDesktop/libagora-text) | Core Text — text layout and fonts |
| [`libagora-app`](https://github.com/AgoraDesktop/libagora-app) | Application Kit (AppKit) — windows, views, controls, the menu model |

### Supporting libraries

| repository | what it is |
|---|---|
| [`libagora-objc`](https://github.com/AgoraDesktop/libagora-objc) | the Objective-C runtime (GNUstep libobjc2) — what Foundation and the desktop compile against |
| [`libagora-dispatch`](https://github.com/AgoraDesktop/libagora-dispatch) | libdispatch — Grand Central Dispatch and the blocks runtime |
| [`libagora-lcms2`](https://github.com/AgoraDesktop/libagora-lcms2) | little CMS — the colour-management engine Core Graphics uses for colour spaces and conversion |

### The desktop

| repository | what it is |
|---|---|
| [`window-server`](https://github.com/AgoraDesktop/window-server) | the Wayland compositor: outputs, seats, input routing, surface roles, layers |
| [`widget-zoo`](https://github.com/AgoraDesktop/widget-zoo) | a demonstration application: the view and control classes and the menu system |
| [`libagora-watch`](https://github.com/AgoraDesktop/libagora-watch) | the change stream — a path changed, and here is which way |
| [`libagora-iconservices`](https://github.com/AgoraDesktop/libagora-iconservices) | Icon Services — the icon an item or a type is drawn with |
| [`libagora-launchservices`](https://github.com/AgoraDesktop/libagora-launchservices) | Launch Services — the type model (UTIs), and what opens what |

### Assembly

| repository | what it is |
|---|---|
| [`release`](https://github.com/AgoraDesktop/release) | composes a whole desktop: every component pinned at an exact revision, plus the build that produces it |

---

*Apple's names — "Cocoa", "Core Graphics", "AppKit" — describe the surface being duplicated. They
are not Agora's product names, and no Apple marks or assets ship.*
