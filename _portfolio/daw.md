---
title: "Digital Audio Workstation (DAW) with Audio Processor on FPGA"
date: 2023-05-14
order: 6
layout: single
excerpt: >-
  Created functional Digital Audio Workstation (DAW) with ability to apply audio affects to sound files and mix and record multiple tracks together. Implemented DAW using Intel Quartus on Intel MAX10 Series FPGA.
  
paperurl: 'http://soumilsg.github.io/files/385.pdf'
---

* End-to-end FPGA Digital Audio Workstation: implemented a stand-alone DAW on an Intel MAX 10 development board that records, plays back, edits, mixes and outputs stereo audio in real time, taking keyboard input and rendering a VGA user interface.
* Custom I²S / I²C audio pipeline: hand-wrote SystemVerilog modules for an SGTL5000 codec interface—HDL I²S \_tx/\_rx shifters with 32-bit stereo framing and LRCLK/SCLK/MCLK domain handling, plus Platform-Designer I²C IP to program codec registers from Nios II C code.
* Clock-domain architecture: synchronized 50 MHz FPGA fabric with 44.1 kHz audio clocks; generated derived clocks (50 MHz÷16) and designed dual FIFO buffers to cross domains between the high-latency SDRAM bridge and the real-time I²S stream.
* On-board audio library in SDRAM: removed Nios II access to the 64 MB SDRAM, instantiated an External-Bus-to-Avalon bridge, and authored a read/write macro-function to fetch 24-bit PCM samples (two 16-bit words per address) and to cache live recordings.
* Audio effects engine:  • Programmable gain via arithmetic left/right bit-shifts (±2 – ±6 dB) with switch-selectable direction/magnitude; Three-level low-pass EQ (FIR-style convolution) for “under-water” effects;  • Stereo track mixer that time-multiplexes the single-ported SDRAM bridge to sum multiple tracks sample-accurately.
* Finite-State Machine DAW controller: sequenced recording, library playback, per-track processing, and final mixdown states; multiplexed I²S sources/destinations and asserted effect-enable lines according to the current mode.
* Keyboard, LEDs, 7-segment & VGA UI: captured USB-keyboard scan codes through MAX3421E SPI stack, displayed hex keycodes, track status LEDs, and real-time level meters/menus on 640×480 VGA generated in hardware.
* Embedded-software integration: wrote SGTL5000 C driver and DAW control routines in Eclipse, linked into on-chip memory, then merged the ELF into the Quartus SOF to eliminate separate JTAG downloads and speed iteration.
* Data-preparation tool-chain: used Audacity to export 16-bit PCM .wav tracks, HxD to verify endianness and address offsets, and a Python script to convert audio blobs to Intel-hex for mass SDRAM initialization.
* Verification & debugging: leveraged SignalTap II logic-analyzer probes to trace bridge timing, FIFO fill levels, and I²S bit-streams; employed Terasic System-Builder GUI and compute-sanitizer-style tests to validate SDRAM reads/writes.
* Result: achieved glitch-free 44.1 kHz stereo playback/recording, real-time gain/EQ control, and seamless mixing of up to four 8-second tracks stored entirely in SDRAM, all controlled from a single keyboard with live VGA feedback.
