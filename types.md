---
title: "Data types"
description: "In Nelson every value is an array, and a scalar is simply a 1x1 array. Numeric and logical"
---

# Data types

In Nelson every value is an array, and a scalar is simply a 1x1 array. Numeric and logical
types exist in any number of dimensions and in dense or sparse storage, and the
floating-point types can be real or complex. The pages below describe each type with short
examples.

## Numeric

- [double](types/double.md) - the default type: 64-bit floating point, real or complex,
  dense or sparse, from scalars to N-dimensional arrays.
- [single](types/single.md) - 32-bit floating point, with the same array shapes.
- [integer](types/integer.md) - signed and unsigned 8, 16, 32, and 64-bit integers, with
  saturating arithmetic.
- [sparse](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/sparse/sparse.html) -
  a compact storage form for mostly-zero `double` and `logical` matrices that keeps only the
  non-zero entries. It is a storage attribute rather than a separate class, so `class` still
  reports `double` or `logical`.

## Logical

- [logical](types/logical.md) - `true` and `false` values, dense or sparse, produced by
  comparisons and used to index and mask arrays.

## Text

- [character array](types/characters.md) - Unicode character arrays written in single quotes.
- [string array](types/string.md) - double-quoted string arrays, with per-element text
  operations and a `<missing>` value.

## Containers

- [cell array](types/data_structure.md) - containers that hold a value of any type and size
  in each element.
- [structure](types/data_structure.md) - named fields grouped into a record, including
  structure arrays.
- [dictionary](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/dictionary/dictionary.html) -
  maps with typed keys and values.
- [function handle](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/function_handle/anonymous_function.html) -
  a reference to a function, including anonymous functions such as `@(x) x.^2`.

## Tables and time series

- [table](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/table/1_create_convert_tables/table.html) -
  column-oriented data with named variables and mixed column types.
- [timetable](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/table/1_create_convert_tables/timetable.html) -
  a table whose rows are indexed by time.
- [datetime](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/time/1_create_date_time_arrays/datetime.html) -
  points in time.
- [duration](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/time/2_duration_calendar_duration/duration.html) -
  elapsed time in fixed units such as seconds, minutes, and hours.
- [calendarDuration](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/time/2_duration_calendar_duration/calendarDuration.html) -
  calendar spans such as months and days.
- [categorical](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/categorical/categorical.html) -
  labelled categories for discrete data.

## Objects and graphics

- [objects](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/interpreter/classdef.html) -
  user-defined classes written with `classdef`, with properties, methods, inheritance, and
  operator overloading (see also [Overloading](overloading.md)).
- [handle object](types/handle.md) - objects with reference semantics.
- [graphics object](types/graphics_object.md) - the figures, axes, and other handles that
  make up a plot.

[Back to features](features.md)
