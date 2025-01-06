---
tags:
  - school-project
  - group-work
  - mechatronics
  - programming
  - embedded-systems
  - software
  - iot
  - hardware
  - electronics
programming-language: python
layout: page
title: "Smart (IoT) Bridge"
permalink: /projects/smart-iot-bridge
---

The **Smart (IoT) Bridge** was a group project completed with four other students as part of my studies. The project aimed to enhance the structural monitoring of bridges using IoT technology. Our solution involved measuring various physical parameters—such as vibrations, strain, and load—to detect potential structural issues early.

## Project Components

1. **Proof of Concept**: 
    - We created a scaled model of a truss bridge to test sensor placements and data accuracy, initially designing components in *Solid Edge*. Though we faced challenges with construction materials and equipment availability, we adapted by using an existing bridge model for testing.

2. **Hardware**: 
    - A *Raspberry Pi 3 Model B+* served as the project’s main microcontroller, collecting and processing sensor data.
    - A *Qwiic Scale* ADC converted analog sensor data into digital format for easier handling by the Raspberry Pi.
  
3. **Software & Data Processing**:
    - Developed in *Python* with multithreading, the software processed sensor data and included functions for zero-point adjustment, calibration, and force calculation.
    - **Sensors**, such as strain gauges, were configured in a Wheatstone bridge setup to measure strain effectively. This setup also included temperature compensation to maintain accuracy.

4. **Communication**: 
    - Data was transmitted using various network protocols, including WiFi and *LoRaWAN*, chosen for its low power consumption and long-range capability—ideal for IoT applications.

5. **Web Interface**:
    - A website was created for real-time data visualization using *Grafana* and *InfluxDB*, providing a user-friendly dashboard to display stress levels, alerts, and historical data trends.
    - The site includes a demonstration video, a project description, and acknowledgments for supporting companies.

The **Smart IoT Bridge** project was an invaluable experience in applying IoT and sensor technology to real-world engineering challenges, aiming to contribute to safer infrastructure monitoring.

---

*Project team*: Thorsten Mahieu, Kilian Bryon, Guillaume Mertens, Korneel Zutterman, Emile Serreyn  
*Time range*: September - December 2020

Back to [projects](projects.md)

