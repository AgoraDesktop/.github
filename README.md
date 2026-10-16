# The Agora Desktop Environment

**→ [agoradesktop.github.io](https://agoradesktop.github.io)** — project site ·
**[design record](https://github.com/AgoraDesktop/Agora)** — what Agora is and how the repositories
are organised

Agora is an installable desktop environment for Linux and the BSDs — the Cocoa stack, a Mac-like
desktop, and its applications — written in Objective-C and built from source.

It is a project to develop a fully-fledged desktop environment familiar to Mac users, but not directly
a clone of any version of Mac OS X, with an incremental development strategy.

**Status: design.** The component repositories exist; no Agora-written code yet.

## Agora and GNUstep

We use forked versions of the GNUstep libraries because our goals require changes which we would not
want to ask the main GNUstep project to adopt. We will continue to import code from upstream as it is
integrated.

We envision the relationship between Agora and GNUstep as being analogous to that between XFCE and
GTK+, or KDE and Qt — we are a consumer of the libraries first and foremost, and thus our changes
should not necessarily be considered for upstream inclusion.

---

*Apple's names — "Cocoa", "Core Graphics", "AppKit" — describe the surface being duplicated. They
are not Agora's product names, and no Apple marks or assets ship.*
