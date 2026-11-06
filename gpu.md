---
title: GPU computing
description: Run array computations on the GPU through WebGPU, portably on Windows, Linux, and macOS with no CUDA dependency. gpuArray and gather, overloaded operators and functions, and single-precision device arrays.
---

# GPU computing

**Move an array to the GPU, and your expressions run on the device.**

Nelson's **gpu_engine** module runs array computations on the GPU through **WebGPU** (Dawn).
The same code runs on Windows, Linux, and macOS, over Vulkan, Metal, or Direct3D 12, with no
proprietary CUDA dependency and no vendor lock-in.

## `gpuArray` and `gather`

Move data to the device with `gpuArray`, compute, and bring the result back with `gather`:

```matlab
A = single(rand(1000));
G = gpuArray(A);                 % copy the array to the device
R = gather(G .* G + sqrt(G));    % compute on the GPU, copy the result back
class(G)                         % gpuArray
```

Operators and many functions are overloaded, so expressions on a `gpuArray` run on the
device and keep their result device-resident until you `gather` it.

## Use the GPU when it is available

`canUseGPU` lets you write code that uses the GPU when present and falls back to the CPU
otherwise:

```matlab
if canUseGPU()
  A = gpuArray(single(rand(1000)));
else
  A = single(rand(1000));
end
```

It returns `false` on a machine without a supported Vulkan, Metal, or Direct3D 12 backend.

## Inspect the device

`gpuDevice` returns a description of the selected device, and `gpuDeviceCount` reports how
many compatible devices are present:

```matlab
>> d = gpuDevice()

d =

  struct with fields:

            Index: 1
             Name: 'Intel(R) UHD Graphics 770'
           Vendor: 'intel'
     Architecture: 'gen-12lp'
          Backend: 'D3D12'
    MaxBufferSize: 2.1475e+09
```

## What runs on the device

- The **operators** and the **element-wise maths** functions, including the rounding,
  hyperbolic, and inverse-trigonometric ones.
- **Reductions and scans**: `sum`, `prod`, `mean`, `var`, `std`, `cumsum`, `cumprod`,
  `sort`, and `find`.
- Complex-part extraction, and the shape and predicate functions.
- **Device constructors**: `zeros`, `ones`, `rand`, and `randn` through the `'gpuArray'` and
  `'like'` forms, for example `zeros(sz, 'gpuArray')` or `zeros(sz, 'like', G)`.

Call `gpuArrayFunctions` for the exact, always-current list.

## Precision and supported types

- Device arrays are stored in **single precision**: WebGPU has no double compute type yet,
  so a `double` input is downcast to `single`. Results match the equivalent CPU computation
  to single-precision accuracy.
- **Real, logical, and complex** data are supported. Sparse inputs are not.
- The small integer classes (`int8`, `uint8`, `int16`, `uint16`, `int32`, `uint32`) are
  preserved with saturating arithmetic, and `gather` returns the original class. The 64-bit
  integer classes are not supported.

---

Read the reference for
[`gpuArray`](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/gpu_engine/gpuArray.html),
[`gather`](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/gpu_engine/gather.html),
[`canUseGPU`](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/gpu_engine/canUseGPU.html),
[`gpuDevice`](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/gpu_engine/gpuDevice.html),
and [`gpuArrayFunctions`](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/gpu_engine/gpuArrayFunctions.html).

[Back to home](index.html)
