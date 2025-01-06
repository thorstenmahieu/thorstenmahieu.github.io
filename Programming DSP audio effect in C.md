---
tags:
  - school-project
  - DSP
  - embedded-systems
  - programming

programming-language: c
layout: page
title: "Programming DSP audio effect in C"
permalink: projects/dsp-audio-effect/
---
{::comment} # Tremolo Audio Effect {:/comment}

This project involved implementing an audio effect of my choosing for an embedded DSP system. I chose the **tremolo effect**. The tremolo effect modulates the amplitude of an audio signal using a sinusoidal waveform, creating a pulsing sound effect. The project was divided into two phases: simulation in MATLAB and implementation on a DSP board.

## Objectives

1. Simulate the effect in MATLAB to analyze its behavior in the time and frequency domains.
2. Implement the effect on a DSP board (TMS320C5515) to process real-time stereo audio.
3. Explore potential extensions, such as additional audio effects like delay.

## Features and Functionality

1. **MATLAB Simulation**:
   - Loaded audio files and determined sample rates using `audioread`.
   - Modulated the audio signal with a sinusoidal waveform, adjusting frequency (15 Hz) and modulation depth (0.5).
   - Visualized original and processed signals in the time domain and played them for comparison.

2. **DSP Implementation**:
   - Developed using **C** in Code Composer Studio.
   - Implemented real-time audio processing with:
     - Sample-by-sample loopback for stereo input and output.
     - Sinusoidal modulation using `generate_sinewave_1` from the DSP library.
   - Configured the audio codec and board clock for a 48 kHz sample rate.

3. **Tremolo Effect Processing**:
   - Calculated output samples for left and right channels:

     $$
     \text{output} = \text{input} + (\text{input} \times \text{modulation depth} \times \sin(2\pi f t))
     $$
   - Ensured balanced gain and normalized output to prevent clipping.

## Technology Stack

- **Simulation**:
  - MATLAB for initial design and analysis.
- **Implementation**:
  - DSP board: TMS320C5515.
  - Programming: C with DSP-specific libraries in Code Composer Studio.
  - Sinusoidal generation using fixed-point arithmetic for performance.

## Workflow and Tools

1. Simulated the effect in MATLAB to validate its performance.
2. Adapted the design for the DSP board, starting from basic loopback examples.
3. Integrated sinusoidal modulation and stereo audio processing into the DSP framework.

## Future Improvements

1. Add **delay effects** or additional audio processing features.
2. Optimize the implementation to reduce noise and enhance audio quality.
3. Explore implementation on FPGA platforms for comparison.

## Conclusion

The tremolo effect was successfully implemented, functioning as intended with real-time audio processing. Although some noise was present, the project demonstrated effective simulation, design adaptation, and embedded implementation. Extensions like delay were not realized due to time constraints, but the project provided valuable insights into DSP audio processing.

---

*Project supervisor*: Sammy Verslype  
*Time range*: November - December 2023

Back to [projects](projects.md)