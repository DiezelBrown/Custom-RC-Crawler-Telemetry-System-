# RC Crawler Telemetry Platform
**Project Status:** ✅ Completed — Fully Operational
> Custom 1/10-scale RC crawler integrating a custom KiCad PCB, ESP32 firmware, real-time sensor acquisition, Bluetooth Low Energy (BLE), and a Flutter mobile telemetry dashboard.

<table>
  <tr>
    <th>Custom RC Crawler</th>
    <th>Live Telemetry Dashboard</th>
  </tr>
  <tr>
    <td><img src="photos/rc_crawler_completed%20(1).jpg" width="400"></td>
    <td><img src="photos/app_dashboard.png" width="400"></td>
  </tr>
</table>





## Overview

The **RC Crawler Telemetry Platform** is a complete embedded system designed to collect and display real-time vehicle data during operation.

An **ESP32 integrated with a custom-designed KiCad PCB** collects battery voltage, motor temperature, wheel RPM, and vehicle orientation. The firmware processes the sensor data, calculates vehicle speed, and transmits telemetry over **Bluetooth Low Energy (BLE)** to a custom **Flutter/Dart mobile application**.

The project covers the complete engineering workflow from **mechanical fabrication and PCB design to embedded firmware, mobile development, hardware debugging, and real-world vehicle testing**.

---

## Problem

Hobby-scale RC vehicles provide limited visibility into important operating data such as temperature, battery voltage, speed, and vehicle orientation.

I built this platform to provide **real-time onboard diagnostics through a wireless mobile dashboard**.

---

## Project Highlights

- Designed and assembled a **custom KiCad PCB**
- Developed modular **C++ firmware** for the ESP32
- Integrated **BNO055, DS18B20, Hall-effect, and voltage sensors**
- Implemented real-time **RPM and vehicle-speed calculations**
- Developed wireless telemetry using **Bluetooth Low Energy (BLE)**
- Built a custom **Flutter/Dart mobile dashboard**
- Fabricated a custom **MIG-welded steel chassis**
- Validated the complete system through **real-world ground testing**

---

## System Architecture

```text
Battery Voltage ─┐
Motor Temp ──────┤
Wheel RPM ───────┼──> ESP32 + Custom PCB ──> BLE ──> Flutter Dashboard
Pitch / Roll ────┘
```

---

## Live Telemetry

| Measurement | Sensor / Method |
| --- | --- |
| Battery Voltage | Voltage Sensor |
| Motor Temperature | DS18B20 |
| Wheel RPM | Hall-Effect Sensor |
| Vehicle Speed | Calculated from Wheel RPM |
| Pitch & Roll | BNO055 IMU |
| Wireless Telemetry | ESP32 BLE |

---

## 🎥 Demo Videos

### Ground Test — Full System

Real-world vehicle test demonstrating the **custom PCB, ESP32 firmware, onboard sensors, BLE telemetry, and Flutter dashboard** operating together on the crawler.

**[▶ Watch Ground Test](Videos/ground_test_demo.MOV)**

### Lifted-Wheel Telemetry Test

Controlled drivetrain test demonstrating live **RPM, calculated speed, battery voltage, motor temperature, pitch, and roll telemetry**.

**Maximum Calculated Unloaded Wheel Speed: 17.28 mph**

**[▶ Watch Lifted-Wheel Test](Videos/lifted_wheel_telemetry_test.MOV)**

> **Note:** 17.28 mph represents unloaded calculated wheel speed, not verified ground speed.

---

## Engineering Challenge

During vehicle integration, the ESP32 began **overheating and eventually stopped communicating**. After replacing the ESP32, the same failure occurred again.

I systematically isolated the problem using a digital multimeter by:

- Measuring power rails throughout the custom PCB
- Correcting the buck converter output to a regulated **5.0 V**
- Checking continuity and resistance between the ESP32 **3.3 V rail and ground**
- Testing the PCB independently from the ESP32
- Isolating and testing the battery-voltage sensing circuit

Testing revealed that the PCB's original **two-resistor voltage divider was not reducing the battery-sense voltage correctly**, allowing excessive voltage to reach the ESP32.

I replaced the original voltage-divider implementation with the external voltage-sensor module used during the project's prototype stage. The module safely scales the battery voltage before the signal reaches the ESP32 ADC.

After implementing the fix, I restored and validated the complete telemetry system.

**Result:** Identified a repeated hardware failure, isolated the faulty subsystem, modified the circuit, and restored full system operation through measurement-driven troubleshooting.

---

## Tech Stack

**Embedded:** C++, ESP32, PlatformIO, Arduino Framework  

**Wireless:** Bluetooth Low Energy (BLE)  

**Sensors:** BNO055, DS18B20, Hall-effect sensor, voltage sensing  

**PCB:** KiCad, schematic capture, PCB layout, soldering  

**Mobile:** Flutter, Dart  

**Mechanical:** MIG welding, custom steel chassis fabrication  

**Tools:** Git, GitHub, VS Code, digital multimeter

---

## Repository Structure

```text
├── firmware/       # ESP32 C++ firmware
├── hardware/       # KiCad PCB files, BOM, pinout & wiring
├── mobile_app/     # Flutter/Dart telemetry application
├── docs/           # Development & testing documentation
├── photos/         # Build and system photos
├── Videos/         # Demonstration videos
└── README.md
```

---

## Project Outcome

Successfully **designed, fabricated, programmed, debugged, and tested** a complete embedded telemetry platform capable of collecting, processing, transmitting, and displaying real-time vehicle data during operation.
