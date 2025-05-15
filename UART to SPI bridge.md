---
tags:
  - school-project
  - FPGA
  - hardware
  - digital-design
  - electronics
language: en
programming-language: vhdl
layout: project
title: "UART-to-SPI Bridge"
permalink: /projects/uart-to-spi-bridge
---

The **UART-to-SPI Bridge** project focused on developing a communication interface to convert 4-byte UART data packets into a 32-bit SPI frame. The design was implemented on the Digilent Basys 3 FPGA board, showcasing skills in VHDL, digital communication protocols, and modular system design.

## Objectives

1. **UART Receiver**:
   - Develop a UART interface to receive 4 successive 1-byte packets from a PC via the board's USB-UART bridge.
   - The payload for each UART frame was set to 1 byte, with freely chosen baud rate and parity settings.

2. **SPI Transmitter**:
   - Implement an SPI interface operating in *SPI Mode 0*.
   - Each SPI frame transmitted a 32-bit payload via GPIO pins of the FPGA.

3. **Packet Merger**:
   - Design a controller to:
     - Track the number of received UART packets.
     - Merge 4 UART packets into a single 32-bit frame.
     - Trigger SPI transmission once the frame was complete.

4. **System Integration**:

   - Combine the UART receiver, SPI transmitter, and packet merger into a single system.
   - Test and verify the functionality on the target FPGA.

## System Description

- The UART interface connected the FPGA to a PC, allowing data transmission through a terminal or script.
- The SPI interface transmitted the combined 32-bit frame to an external SPI device via GPIO pins.
- The controller ensured proper synchronization and conversion of data between protocols.

This project provided hands-on experience in interfacing communication protocols, modular design, and FPGA implementation, forming a robust bridge between UART and SPI systems.

---

*Project supervisor*: Sammy Verslype  
*Completion date*: September 2023  