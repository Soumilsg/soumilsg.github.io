---
title: "Custom UNIX Operating System"
date: 2023-12-06
order: 3
layout: single
excerpt: >-
  Wrote my own operating system with interactive shell from scratch using C and x86 assembly. Wrote single-core kernel for 32-bit hardware with paging-only virtual memory system, writable file system, software context switching, terminal switching, and hardware interrupts and exception handling. Developed device drivers for keyboard, mouse, and real-time clock.

github: https://github.com/Soumilsg/Unix-Operating-System
---

Wrote my own operating system with interactive shell from scratch using C and x86 assembly. Wrote single-core kernel for 32-bit hardware with paging-only virtual memory system, writable file system, software context switching, terminal switching, and hardware interrupts and exception handling. Developed device drivers for keyboard, mouse, and real-time clock.

* Engineered a protected, single-core UNIX-like kernel from the ground up in C and x86 Assembly, targeting 32-bit hardware. Bootstrapped CPU/memory, implemented paging-only virtual memory with per-process page tables, and designed a read-only file-system interface akin to modern Linux.
* Built a preemptive multitasking layer: wrote a round-robin scheduler, software context-switching logic, and manual terminal-switch support to run up to eight user processes concurrently.
* Handled all hardware faults and asynchronous events by wiring up the interrupt descriptor table (IDT), writing handlers for maskable interrupts and exceptions, and integrating a kernel-side heap allocator for dynamic memory needs.
* Developed low-level device drivers for PS/2 keyboard, mouse, and real-time clock (RTC), exposing them via system-call abstractions.
* Delivered an interactive userland shell, implementing system calls for process control, file I/O and memory management—and used advanced GDB techniques under QEMU emulation to iteratively debug and validate system-level behavior.