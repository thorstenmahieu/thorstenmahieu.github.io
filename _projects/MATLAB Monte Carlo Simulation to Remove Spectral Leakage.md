---
tags:
  - school-project
  - data-science
  - artificial-intelligence
  - programming
  - solo-project
programming-language: MATLAB
rating: 2/5 
layout: project
title: "MATLAB Monte Carlo Simulation to Remove Spectral Leakage"
permalink: projects/spectral-leakage-removal/
---


This project focused on addressing **spectral leakage**, a common issue in digital signal processing (DSP) when signals are not sampled coherently. Spectral leakage spreads the amplitude of frequency components into adjacent frequencies, making it challenging to determine the correct frequencies, amplitudes, and phases in the signal. A MATLAB-based solution was developed to implement both iterative and non-iterative algorithms for leakage removal.

## Objectives

1. Analyze the causes and effects of spectral leakage during discrete Fourier transformations (DFTs).
2. Implement a **non-iterative algorithm** to estimate frequency components with reduced spectral leakage.
3. Explore and partially implement an **iterative algorithm** for enhanced accuracy.
4. Validate the algorithms using a Monte Carlo simulation.

## Methodology

### Theoretical Background
- Spectral leakage occurs when sampled signals do not have an integer multiple of their fundamental period.
- Truncation errors and non-coherent sampling lead to misinterpretation of frequency components.
- Solutions like applying windows (e.g., Hamming, Hann) are common but insufficient for complete removal of leakage.

### Algorithm Implementation
- **Non-Iterative Algorithm**:
  - Identifies frequency components using asymptotic behavior in the FFT spectrum.
  - Estimates amplitudes and phases of components through analytical formulas.
- **Iterative Algorithm** (partially implemented):
  - Removes the influence of overlapping frequency components iteratively.
  - Refines estimations of frequency, amplitude, and phase through multiple iterations.

### Monte Carlo Simulation
- Tested the algorithm with varying signal lengths and frequencies (20 Hz to 5 kHz).
- Simulated signals with up to three frequency components to evaluate the algorithm’s robustness.

## Results

- The **non-iterative algorithm** effectively reduced spectral leakage and provided better results than traditional windowing techniques. However, it struggled when frequency components were closely spaced.
- The **iterative algorithm**, though incomplete, showed potential for distinguishing closely spaced frequencies with greater accuracy.

## Conclusion

This project demonstrated the importance of advanced spectral leakage removal techniques in DSP. While the non-iterative algorithm provided significant improvements, the iterative approach is expected to deliver superior results once fully implemented. Future work could focus on optimizing the iterative algorithm and applying it to real-world DSP applications.

---

*Time range*: October - November 2023  
 