---
title: "LeNet-5 in CUDA"
date: 2025-05-14
order: 4
layout: single
excerpt: >-
  Implemented a CUDA-accelerated version of the LeNet-5 convolutional neural network that runs on an NVIDIA A40 GPU cluster, fusing feature-map unrolling, tiled matrix multiplication, and output permutation into a single Tensor-Core-enabled kernel. Development, debugging, and tuning were driven with Nsight Systems, Nsight Compute, compute-sanitizer, and gprof to guarantee bit-exact correctness and maximize throughput.
  
---

Implemented a CUDA-accelerated version of the LeNet-5 convolutional neural network that runs on an NVIDIA A40 GPU cluster, fusing feature-map unrolling, tiled matrix multiplication, and output permutation into a single Tensor-Core-enabled kernel. Development, debugging, and tuning were driven with Nsight Systems, Nsight Compute, compute-sanitizer, and gprof to guarantee bit-exact correctness and maximize throughput.

* Engineered end-to-end CUDA kernels for LeNet-5 inference; combined unrolling + GEMM + permutation in one launch, eliminating global-memory round-trips and raising arithmetic intensity.
* Exploited Tensor Cores and warp-level MMA instructions, achieving ~15x speed-up over a cuDNN baseline on Fashion-MNIST while sustaining >90 % SM occupancy.
* Applied shared-memory tiling, register blocking, and kernel fusion to balance DRAM bandwidth with compute throughput, keeping GPU memory traffic low at batch size = 10 k.
* Profiled hot spots with Nsight Systems/Compute, iteratively resolving bank conflicts, uncoalesced loads, and warp divergence; validated memory safety via compute-sanitizer.
* Automated CI tests to compare CPU (gprof-instrumented) and GPU paths, ensuring deterministic outputs across seeds and full reproducibility of timing results.
* Packaged the model and driver scripts for multi-GPU execution under Slurm