---
title: "Implementation of a CPU Controller for Dynamic Binary Translation"
collection: publications
category: manuscripts
permalink: /publication/MESA
excerpt: 'Developed programmable controller for exploiting instruction-level parallelism at the hardware level for undergraduate thesis. Controller developed as part of larger project in collaboration with the [Future Architecture and System Technology for Scalable Computing Lab (FAST) at UIUC](https://fast.ece.illinois.edu/) and the [Samsung Advanced Institute of Technology (SAIT)](https://www.sait.samsung.co.kr/saithome/main/main.do).'
date: 2025-05-14
venue: 'IDEALS at UIUC'
# slidesurl: 'http://academicpages.github.io/files/slides2.pdf'
paperurl: 'http://soumilsg.github.io/files/THESIS.pdf'
citation: 'TBD'
---
Developed programmable controller for exploiting instruction-level parallelism at the hardware level for undergraduate thesis. Controller developed as part of larger project in collaboration with the [Future Architecture and System Technology for Scalable Computing Lab (FAST) at UIUC](https://fast.ece.illinois.edu/) and the [Samsung Advanced Institute of Technology (SAIT)](https://www.sait.samsung.co.kr/saithome/main/main.do). 

**Abstract:**
As modern compute workloads grow more demanding, hardware accelerators integrated with CPUs are valuable for improving the execution speed and energy efficiency of highly parallelizable workloads. However, writing code to run on these accelerators generally requires specialized compilers or synthesis tools before execution. To address this, Wang et al. introduced the Microarchitecture Extensions for Spatial Architecture (MESA) controller, a hardware block that continuously monitors the CPU instruction stream and transparently offloads suitable traces to a configurable Coarse-Grained Reconfigurable Array (CGRA) for acceleration. However, the current MESA controller is constrained to a fixed mapping algorithm, hence limiting its adaptability to different CGRAs in commercial applications without costly redesigns per CGRA architecture. This thesis aims to extend the MESA controller’s capabilities by developing a programmable version capable of efficiently mapping workloads to a wide range of CGRAs. The enhanced controller will support a custom instruction set, allowing it to execute mapping algorithms tailored to the specific configuration of the CGRA. The revised MESA controller is implemented in SystemVerilog and verified through hardware and software simulation methods. The outcome of this thesis is a verified hardware design of a programmable version of the MESA controller as an IP that can be integrated into different System-on-Chip (SoC)s with varying CGRA designs.

**Index Terms —** Dynamic Binary Translation, MESA Controller, Coarse‑Grained Reconfigurable Arrays, Spatial Dataflow Graphs, Hardware Accelerators, Heterogeneous Systems, Instruction Set Architecture, RTL Design, RTL Verification,
Reconfigurable Computing, Parallel Programming, Computer Architecture