---
tags:
  - school-project
  - mechatronics
  - labview
  - programming
  - electronics

programming-language: labview
layout: page
title: "BJT Curve Tracer in LabVIEW"
permalink: projects/curve-tracer-for-bjt/
---
{::comment} # BJT Curve Tracer in LabVIEW {:/comment}

The **BJT Curve Tracer** was initially a collaborative project for the "Mechatronics lab" course but ultimately became a solo endeavor since my team mates gave up on the major. This project involved developing a LabVIEW program to analyze the input and output characteristics of Bipolar Junction Transistors (BJTs) by generating characteristic curves, including the input ($$V_{BE}$$ vs. $$I_B$$) and output ($$V_{CE}$$ vs. $$I_C$$) curves.

## Project Overview

1. **Objective**:
    - To automate the measurement of key BJT characteristics, allowing users to control input values (e.g., base and collector voltages) and visualize the resulting curves.

2. **Circuit Design**:
    - The setup included a **voltage-controlled current source** connected to the BJT, enabling precise control over the base current.
    - Key instruments:
      - *HMC8012 multimeters* for voltage and current measurements
      - *HMC8043 triple output power supply* for controlling both V1 (base current source) and V2 (collector-emitter voltage)

3. **LabVIEW Programming**:
    - Developed a LabVIEW application with a structured UI for setting parameters such as current steps, voltage sweeps, and measurement range.
    - Programmed to save all measurement data to a `.csv` file with relevant settings for easy data retrieval and comparison.
    - A graphical interface allowed real-time visualization of the measured curves and parameter adjustment, supporting both input and output characteristic curves.

4. **Functionality**:
    - The program supports automated adjustments of base and collector currents in specified steps, captures data in real-time, and plots the curves dynamically.
    - Additional features include safe program stopping and easy retrieval of previous measurement data for analysis and comparison.

This project served as an extensive application of LabVIEW for circuit analysis, requiring in-depth knowledge of both BJT characteristics and LabVIEW's graphical programming capabilities.


This project was less fun but it greatly improved my skills to work independently and modularly.

---

*Project supervisor*: Jan Poelaert

*Completion date*: September 2022

Back to [school projects](school projects.md)
