---
title: "NFlow and the web desktop arrive in 2.0"
date: 2026-11-06 09:00:00 +0100
description: Visual modelling with C and Rust code generation, plus the full desktop in your browser.
image: /images/v2/web_desktop.jpg
---

![The Nelson web desktop running in a browser]({{ '/images/v2/web_desktop.jpg' | relative_url }})

Two of the largest additions in Nelson 2.0 are NFlow and the web desktop.

[**NFlow**]({{ '/nflow.html' | relative_url }}) is a visual block-diagram editor and
simulator. You build a model from a palette of blocks, simulate it on a solver engine, and
then generate standalone **C and Rust** that build and run on their own and match the model
to machine precision. It ships as a beta.

[**The web desktop**]({{ '/web-desktop.html' | relative_url }}) brings the command window,
editor, debugger, variable editor, and figures to the browser, using the same engine, with
nothing to install. A separate WebAssembly build runs Nelson entirely client-side. It ships
as a preview.

You can read more in [what's new in 2.0]({{ '/whats-new.html' | relative_url }}).
