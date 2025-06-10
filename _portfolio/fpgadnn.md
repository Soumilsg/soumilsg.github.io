---
title: "FPGA-Accelerated DNNs"
date: 2025-05-14
order: 5
layout: single
excerpt: >-
  Engineered a hardware-accelerated LeNet-5–inspired DNN on an AMD PYNQ-Z2 FPGA using Xilinx Vivado HLS and the ScaleHLS co-design framework, fully pipelining convolution, activation, and pooling stages with AXI-DMA and MicroBlaze integration to sustain high-throughput traffic-sign classification.
  
github: https://github.com/Soumilsg/DNNs_On_FPGA
---

Engineered a hardware-accelerated LeNet-5–inspired DNN on an AMD PYNQ-Z2 FPGA using Xilinx Vivado HLS and the ScaleHLS co-design framework, fully pipelining convolution, activation, and pooling stages with AXI-DMA and MicroBlaze integration to sustain high-throughput traffic-sign classification.
Automated weight and bias loading via Python, and benchmarked end-to-end inference throughput and energy efficiency against a YOLO-v8 model on Raspberry Pi + Edge TPU, achieving real-time (≈63 fps) recognition within strict FPGA resource constraints.