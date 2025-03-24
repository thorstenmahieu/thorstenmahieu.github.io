---
tags:
  - school-project
  - FPGA
  - hardware
  - digital-design
programming-language: vhdl
layout: page
title: "Binary to (hexa)decimal BCD converter"
permalink: projects/binary-to-hexa-decimal-converter/
---

In this project, I developed a **binary-to-(hexa)decimal BCD converter** using **VHDL** and **Vivado**, implemented on a Digilent Basys 3 FPGA board. The system accepts a binary input through the board’s switches and displays the converted (hexa)decimal output on the 4-digit 7-segment LEDs.  

A button allows the user to toggle between **decimal** and **hexadecimal** modes. The conversion involves encoding the binary input into a **binary-coded decimal (BCD)** format, compatible with either common cathode or common anode configurations.  

To ensure robust functionality, an **overflow signal** is triggered if the input exceeds the representable range for the selected mode (commonly encountered in decimal mode).

This project highlights the integration of digital design concepts and hardware programming to create a functional and user-interactive FPGA-based application.

<img src="/assets/hexadecimal.jpg" alt="photo of the board with cafe" width="screen-width" >
    > A picture of the FPGA board with the hex number "CAFE" on it (51966 in decimal), showcasing it works.
---
*Project supervisor*: Sammy Verslype

*Completion date*: June 2023

Back to [projects](projects.md)
