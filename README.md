# IoT-Based-Stampede-Detection-System
An ESP32-based IoT crowd monitoring and stampede-risk assessment prototype using load sensing, vibration detection, sound analysis, and a real-time web dashboard with a Crowd Intensity Index (CII).
# IoT-Based Smart Stampede Detection and Crowd Monitoring System

## Overview

The **Smart Stampede Detection and Crowd Monitoring System** is an IoT-based prototype designed to monitor crowd conditions and identify patterns that may indicate potentially dangerous crowd movement.

The system uses an ESP32 microcontroller integrated with multiple sensors to collect crowd-related parameters, including load variations, vibration, and surrounding sound intensity.

A real-time web dashboard displays sensor readings, a Crowd Intensity Index (CII), and alert status to support continuous monitoring.

## Objectives

- Monitor crowd-related physical parameters using multiple sensors.
- Detect sudden variations in load, vibration, and sound.
- Calculate a Crowd Intensity Index (CII).
- Display sensor information through a real-time web dashboard.
- Develop a prototype for early identification of potentially unsafe crowd conditions.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller |
| HX711 | Load cell signal amplifier |
| Load Cells | Pressure/load measurement |
| ADXL345 | 3-axis acceleration and vibration sensing |
| INMP441 | Digital microphone for sound sensing |
| Wi-Fi | Wireless dashboard connectivity |
| RA-02 SX1278 LoRa | Planned long-range communication module |
| Raspberry Pi 4 | Planned receiver and monitoring unit |

## Software and Technologies

- Arduino IDE
- Embedded C/C++
- ESP32 Wi-Fi
- HTML, CSS and JavaScript
- WebServer library
- I2C and I2S communication protocols
- HX711 and ADXL345 libraries

## System Architecture

1. **Data Acquisition:** ESP32 collects readings from the connected sensors.
2. **Load Monitoring:** HX711 interfaces with load cells to obtain load-related readings.
3. **Vibration Monitoring:** ADXL345 measures acceleration along three axes.
4. **Sound Monitoring:** INMP441 captures digital audio samples and estimates sound intensity in dBFS.
5. **Data Processing:** The ESP32 processes sensor readings and calculates the Crowd Intensity Index.
6. **Visualization:** A web dashboard displays live readings, trends, and alert information.

## Crowd Intensity Index (CII)

The prototype uses a weighted scoring approach:

CII = 0.35P + 0.25V + 0.20S + 0.10dP + 0.10dV

Where:

- P = Normalized load-related parameter
- V = Normalized vibration parameter
- S = Normalized sound parameter
- dP = Change in normalized load parameter
- dV = Change in normalized vibration parameter

All parameters are normalized to a scale of 0–100 before calculating the index.

The current prototype uses experimental normalization and display thresholds. These values require further calibration and validation using real crowd data.

## Dashboard Features

- Live sensor readings
- Load-related parameter monitoring
- Three-axis accelerometer readings
- Sound intensity monitoring
- Crowd Intensity Index display
- Real-time CII trend graph
- Alert status visualization

The ESP32 hosts the dashboard through its built-in Wi-Fi web server. A laptop connected to the same Wi-Fi network can access it through a browser.

## Current Implementation Status

**Implemented:**
- ESP32-based sensor interfacing
- Load-related data acquisition
- Accelerometer-based vibration monitoring
- Microphone-based sound analysis
- Experimental CII calculation
- ESP32-hosted live web dashboard

**Planned / Future Improvements:**
- Integration of LoRa-based communication using RA-02 SX1278
- Raspberry Pi-based central monitoring station
- Multi-node crowd monitoring
- Sensor calibration and real-world testing
- Machine learning-based crowd-risk classification
- Improved alert mechanisms

## Important Prototype Limitations

- Load cell readings require proper bridge configuration and calibration.
- Simulated load values must not be interpreted as actual measured crowd weight.
- Microphone output in dBFS is not calibrated sound pressure level (dB SPL).
- The CII is an experimental prototype metric, not a scientifically validated stampede prediction model.
- This prototype is intended for demonstration and research, not as a certified public-safety system.

## Applications

- Crowd monitoring at public gatherings
- Event and festival monitoring
- Railway stations and transportation hubs
- Stadiums and public venues
- Smart-city safety research

## Future Scope

The system can be extended with multiple distributed sensor nodes communicating through LoRa. A Raspberry Pi can act as a central monitoring unit, collecting information from different nodes and displaying crowd conditions through a centralized dashboard. Machine learning techniques can further improve pattern recognition and risk classification.

## Contributors

Developed as an Electronics and Communication Engineering project.

## License

This project is available under the MIT License.
