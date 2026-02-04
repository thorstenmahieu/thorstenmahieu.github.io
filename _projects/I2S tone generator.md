---
tags:
  - school-project
  - FPGA
  - digital-design
  - hardware
  - electronics
  - solo-project

layout: project
title: "I2S Tone generator"
size: small
rating: 2.5/5
start-date: 2022-11
permalink: projects/i2s-tone-generator/
---

This project involved designing and implementing a digital tone generator capable of producing sine and triangle waveforms. The tones are delivered via an **I2S interface** to an audio codec, which converts the digital signals into analog audio. The assignment emphasized working within the audible frequency range and integrating components into an FPGA-based system using VHDL.

## Objectives

1. **System Design**:
   - Create a digital tone generator to produce sine and triangle waveforms at a self-chosen frequency.
   - Support user input for selecting or mixing waveforms.

2. **I2S Transmitter**:
   - Implement an Inter-IC Sound (I2S) interface to send digital audio to an audio codec for playback.
   - Synchronize data transmission using:
     - **BCLK** (Bit-Clock): 64x the LRCLK frequency.
     - **LRCLK** (Left-Right-Clock): Operating at 48 kHz.

3. **Clock Management**:
   - Provide a master clock (12.288 MHz) to the audio codec for internal DSP operations.
   - Architect clock signal sources and ensure proper synchronization.

4. **Integration**:
   - Combine the tone generator, I2S transmitter, and clock modules into a unified system.
   - Verify and debug the design on an FPGA platform.

## System Architecture

- The FPGA acted as the **master device**, generating tone samples, clocks, and control signals.
- The audio codec functioned as the **slave device**, processing and converting digital signals to analog output.

This project demonstrated the integration of digital signal generation and serial audio communication using FPGA, emphasizing precision timing and modular design principles.

---

*Project supervisor*: Sammy Verslype  
*Completion date*: September 2023  
