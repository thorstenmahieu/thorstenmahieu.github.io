---
tags:
  - school-project
  - DSP
  - embedded-systems
  - programming
  - C

programming-language: C
layout: project
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


## Future Improvements

1. Add **delay effects** or additional audio processing features.
2. Optimize the implementation to reduce noise and enhance audio quality.
3. Explore implementation on FPGA platforms for comparison.

## Conclusion

The tremolo effect was successfully implemented, functioning as intended with real-time audio processing. Although some noise was present, the project demonstrated effective simulation, design adaptation, and embedded implementation. Extensions like delay were not realized due to time constraints, but the project provided valuable insights into DSP audio processing.

---

*Project supervisor*: Sammy Verslype  
*Time range*: November - December 2023  
