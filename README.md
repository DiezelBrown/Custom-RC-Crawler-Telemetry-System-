# RC Crawler Telemetry Platform
**Project Status:** 🚧 Active Development
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

The Embedded Vehicle Telemetry Platform is a custom-built 1/10-scale RC crawler that demonstrates embedded systems, PCB design, wireless telemetry, and real-time vehicle diagnostics. The system collects battery voltage, motor temperature, wheel speed, and vehicle orientation using onboard sensors and transmits the data to a Flutter mobile application over Bluetooth Low Energy (BLE). The project serves as a low-cost platform for embedded systems development, vehicle diagnostics, and robotics research

## Problem

Most hobby-scale robotic vehicles provide little visibility into system health during operation. Diagnosing issues such as battery voltage drop, motor overheating, excessive vehicle roll, or wheel slip often requires separate instruments or trial-and-error.

This project addresses that problem by providing a low-cost embedded telemetry platform capable of collecting and displaying real-time vehicle data through a Bluetooth-connected mobile application.

## Key Capabilities

- ✅ Custom-fabricated steel chassis
- ✅ ESP32 embedded telemetry platform
- ✅ Battery voltage monitoring
- ✅ Motor temperature monitoring
- ✅ Wheel RPM measurement
- ✅ Vehicle speed calculation
- ✅ BNO055 IMU (Pitch & Roll)
- ✅ Bluetooth Low Energy (BLE)
- ✅ Mobile application 
- 🔄  Custom KiCad PCB *(In Progress)*
- ⏳ Operator-assisted recovery mode

---

## Technologies

- C++
- ESP32
- PlatformIO
- Bluetooth Low Energy (BLE)
- Embedded Systems
- Sensor Integration
- I²C
- OneWire
- Hall Effect Sensor
- MIG Welding

---

## Current Telemetry

| Feature | Status |
|----------|--------|
| Battery Voltage | ✅ |
| Motor Temperature | ✅ |
| Wheel RPM | ✅ |
| Vehicle Speed | ✅ |
| Pitch | ✅ |
| Roll | ✅ |
| Bluetooth | ✅ |

---

## Repository Structure

```text
firmware/
├── ESP32 firmware

hardware/
├── BOM.md
├── HARDWARE.md
├── pinout.md
└── wiring.md

docs/
├── Development updates
└── Testing results

photos/
├── Build photos
└── Demonstrations
```

---

## Current Status

### Completed

- ✅ Steel chassis
- ✅ ESP32 firmware
- ✅ Battery voltage sensor
- ✅ DS18B20 temperature sensor
- ✅ Hall-effect RPM sensor
- ✅ BNO055 IMU
- ✅ Bluetooth Low Energy
- ✅  Mobile telemetry application
### In Progress

- 🔄Custom KiCad PCB

### Planned

- ⏳ Operator-assisted recovery mode
- ⏳ Data logging

---

## Future Goals

- Develop a cross-platform mobile application.
- Design a custom KiCad PCB.
- Implement Bluetooth-based operator controls.
- Develop an operator-assisted recovery mode.
