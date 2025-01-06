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
  - FPGA
  - electronics
  - analog-design
  - digital-design
programming-language: dart, sql, vhdl
layout: page
title: "Remote-Controlled, Sensor-Equipped Omnidirectional Vehicle"
permalink: projects/remote-controlled-vehicle/
---
{::comment} # Remote-Controlled, Sensor-Equipped Omnidirectional Vehicle {:/comment}

This group project involved designing a remote-controlled vehicle equipped with sensors for obstacle detection and data recording. The system was implemented using a Raspberry Pi, FPGA board, and analog electronics, with a mobile app for wireless control.

## Objectives

1. Enable remote control of the vehicle via a smartphone or tablet app, supporting movements in all directions.
2. Integrate an ultrasonic sensor for obstacle detection, triggering the vehicle to stop when close to an object.
3. Log distance measurements in a SQL database on the Raspberry Pi.
4. Design modular hardware and software components for seamless integration and functionality.

## System Components

### **Control Application** (Karel Debedts)
- Developed using **Flutter** to provide a user-friendly interface for controlling the vehicle.

### **Raspberry Pi (Thorsten Mahieu)**
- **Hardware**: Raspberry Pi 3B+ served as the central controller.
  - Configured via SSH and VNC for headless operation.
- **Database**:
  - Installed and configured **MariaDB** to log distance measurements.
  - Created a table with a primary key, measurement values, and timestamps.
- **UART Communication**:
  - Configured PL011 UART for reliable GPIO communication, reassigning ports to bypass the default mini-UART.

### **FPGA (Timon Callens)**
- Managed **UART**, **PWM**, and sensor processing for real-time motor and sensor control.

### **Ultrasonic Sensor**
- Integrated for obstacle detection with analog filtering to ensure accurate measurements.

## System Workflow

1. The control app sends commands to the Raspberry Pi via WiFi.
2. The Raspberry Pi logs data in a database and communicates with the FPGA using UART.
3. The FPGA drives the vehicle motors and processes input from the ultrasonic sensor.
4. The vehicle stops automatically when the sensor detects an obstacle within a set threshold.

## Conclusion

This project demonstrated effective teamwork and the integration of software, digital, and analog systems to create a functional and interactive remote-controlled vehicle.

---

*Project team*: Thorsten Mahieu, Karel Debedts, Timon Callens

*Time range*: September - December 2022

Back to [projects](projects.md)