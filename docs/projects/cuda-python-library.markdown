---
layout: page
title: CUDA Accelerated Python Library
permalink: /projects/cuda-python-library/
hide_in_nav: true
---

## CUDA Accelerated Python Library

[View on GitHub](https://github.com/batu2244/CUDA-Accelerated-Python-Library)

This project implements and benchmarks GPU-accelerated versions of two foundational computational operations - matrix multiplication and image convolution - comparing performance across CPU and GPU implementations at varying problem scales.

**Implementations**

For matrix multiplication, four versions were built: a CPU baseline in C, a naïve CUDA kernel that assigns one thread per output element, an optimized CUDA kernel using shared memory tiling (tile width of 16) to dramatically reduce global memory access overhead, and calls to the cuBLAS library for reference-level GPU performance. For image convolution, CPU and CUDA variants were implemented supporting multiple filter types (edge detection, sharpening, and Gaussian blur) at configurable filter sizes (3×3, 5×5, and 7×7). All implementations are compiled into Python-callable shared libraries, making them usable directly from Jupyter notebooks.

**Hardware & Stack**

The project targets an NVIDIA Tesla T4 GPU (Compute Capability 7.5) and is written in C and CUDA, with Python used for orchestration and benchmarking. Benchmarks were run across matrix sizes from 512 to 2048 and across varying image dimensions.

**Results**

GPU implementations scale significantly better than the CPU baseline as problem size grows. The tiled CUDA kernel outperforms the naïve CUDA version by reducing redundant global memory reads. cuBLAS achieves the highest throughput overall. For smaller inputs, GPU initialization overhead is noticeable, but it becomes negligible at larger scales - confirming that GPU acceleration is most valuable for computationally heavy workloads.
