---
tags:
  - group-work
  - school-project
  - embedded-systems
  - IoT
  - programming
programming-language: C
layout: project
title: "Time-Synchronized Embedded Device"
rating: 2/5
permalink: /projects/time-synchronized-embedded-device
---

This project focused on developing a **time-synchronized embedded device** for IoT-based environmental monitoring. Using a LoRa network, a gateway and sensor node communicated wirelessly to collect temperature data efficiently while adhering to real-time constraints.

## Objectives

1. Implement a gateway to transmit beacons and receive temperature data from a sensor node.
2. Develop a sensing device to synchronize with the gateway, collect calibrated temperature data, and log it in a database.
3. Optimize energy consumption with low-power and ultra-low-power modes.

## Features

### Gateway
- Transmits 20 beacons at random intervals (2-10 seconds) with synchronization info.
- Receives acknowledgments (acks) containing temperature data from the sensor.
- Displays statistics on beacons sent and acks received.

### Sensor Node
- **Synchronization**:
  - Logs wake-up times and temperature data in EEPROM upon receiving a beacon.
  - Sends calibrated temperature as acknowledgment to the gateway.
- **Power Efficiency**:
  - Enters sleep mode between transmissions and ultra-low-power mode after 20 beacons.
- **Commands via Serial Port**:
  - Retrieve the latest or all recorded data, and enable low-power mode.

## Challenges
- **Temperature Measurement**: ADC returned incorrect values when integrated into the full system.
- **Ultra-Low-Power Mode**: Difficulties reactivating the sensor from this state.
- **Real-Time Constraints**: Limited by time and resources, requiring improvements in task separation and scheduling.

## Conclusion
The project successfully enabled communication between the gateway and sensor node while implementing key database operations and low-power modes. Despite challenges with temperature measurement and ultra-low-power transitions, the system demonstrated essential IoT functionalities and provided a foundation for future enhancements.

---

*Project team*: Thorsten Mahieu, Cédric Chau  
*Time range*: November 2023 - December 2023  