---
title: Features
description: "What Nelson offers engineers and scientists: a fast array language, visual modelling, modern data types, graphics, and broad interoperability."
---

# Features

Nelson is a complete environment for numerical computing. It combines a fast array
language, a visual block-diagram modeller, a modern data-analysis toolkit,
publication-quality graphics, and bridges to the tools you already use. More than
**3,000 built-in functions** cover everything from a quick calculation to a full
simulation.

New to version 2.0? See [what's new in 2.0](whats-new.md).

---

## The language

- **A familiar array syntax**, with matrices, slicing, broadcasting, and vectorised
  operations, so that existing scripts run with few changes.
- **A fast bytecode engine**: your code runs on a compiled virtual machine with dedicated
  fast paths for real and complex scalars.
- **Object-oriented programming** with [`classdef`](overloading.md): value and handle
  classes, inheritance, properties, static methods, events, and enumerations.
- **Packages, imports, and argument validation** for structuring larger projects.
- [Operator and function overloading](overloading.md) for custom behaviour.
- [Modularity](modularity.md) and [external modules](external_module.md) for organising
  and extending functionality.

## Data types and analysis

- [Core data types](types.md): doubles, integers, logicals, strings, characters, and a
  flexible, extensible type system.
- [Advanced data structures](types.md): cell arrays, structs, and dictionaries.
- **Tables and timetables** for labelled, mixed-type data and real data wrangling.
- **datetime and duration** with sub-second precision, time zones, and time-aware plot axes.
- **categorical arrays** with grouped display and categorical plots.

## Scientific computing

- [2-D and 3-D plotting](plots.md): high-level commands for data visualisation. See the
  [plot gallery](plot_gallery.md).
- Linear algebra, full sparse-matrix support, and numerical solvers.
- [ODE solvers](ode.md): explicit, stiff, implicit, delay, and boundary-value problems with
  a familiar interface and an optional SUNDIALS backend.
- [Fast Fourier Transform](fftw.md) for frequency-domain analysis.
- [Control systems](control.md) and [SLICOT integration](slicot.md) for system modelling.
- Statistics and data-analysis functions.
- Image processing, and a NetCDF reader and writer.

## Visual modelling with NFlow

- [**NFlow**](nflow.md) lets you build block diagrams, simulate them, and generate
  standalone **C and Rust** that match the model to machine precision. It supports causal
  and acausal modelling, several solvers, scopes, dashboards, and FMI and FMU
  co-simulation. _(beta)_

## User interface and web

- [**Web desktop**](web-desktop.md): the command window, editor, debugger, variable
  editor, and figures running in your browser, with a WebAssembly build.
- [Interactive code editor](code_editor.md) with debugging.
- [UI controls](uicontrol.md) and the [QML engine](qml_engine.md) for modern interfaces.

## Programming and interoperability

- [Standalone applications](compiler.md): compile your programs into native executables that
  run without a Nelson installation and without a C or C++ toolchain.
- [Build C and C++ on the fly](build_c_cpp_on_fly.md) for integration with compiled
  languages.
- [C MEX API support](mex.md) and the [Nelson Engine API](mex_engine.md).
- [Foreign Function Interface (FFI)](ffi.md) for calling shared libraries.
- [Python integration](python.md) and a Julia interface.

## High-performance computing

- [GPU computing](gpu.md): run array computations on the GPU through WebGPU, portably and
  without a CUDA dependency.
- [Parallel computing](parallel.md) across multiple cores.
- [Message Passing Interface (MPI)](mpi.md) for distributed computing.

## Data handling and connectivity

- [HDF5 I/O](hdf5.md) and [MAT-file I/O](matio.md) for interoperable data files that other
  array-computing tools can read.
- [JSON support](json.md) for parsing and generating JSON.
- [COM interface](com_interface.md) on Windows, and [RESTful web services](rest.md).

## Other capabilities

- [Audio processing](audio.md), [Unicode support](charset.md),
  [validator functions](validators.md), and [interprocess communication](ipc.md).

---

[Back to home](index.html)
