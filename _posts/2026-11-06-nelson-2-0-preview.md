---
title: "Nelson 2.0 is available as a preview"
date: 2026-11-06 10:00:00 +0100
description: A faster engine, object-oriented programming, visual modelling, and a web desktop.
image: /images/v2/ripple_turbo.png
---

![A shaded 3-D surface rendered by Nelson, coloured with the turbo colormap]({{ '/images/v2/ripple_turbo.png' | relative_url }})

Nelson 2.0 is now available as a preview. It is a major release, both inside and out.

On the inside, your code runs on a new bytecode virtual machine with dedicated fast paths
for real and complex scalars, so existing scripts run noticeably faster while producing the
same results.

On the outside, the release adds full object-oriented programming with `classdef`, visual
modelling with [NFlow]({{ '/nflow.html' | relative_url }}), a browser-based
[web desktop]({{ '/web-desktop.html' | relative_url }}), and a modern data-analysis toolkit
with tables, timetables, datetime, duration, and categorical arrays.

See [what's new in 2.0]({{ '/whats-new.html' | relative_url }}) for the full list, or
[download Nelson](https://github.com/nelson-lang/nelson/releases) to try it.
