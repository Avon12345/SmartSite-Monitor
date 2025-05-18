# SmartSite-Monitor
 Low-Power ESP32-Based Environmental Sensor Node for Industrial Deployment


Problem Statement

Remote or temporary industrial sites (construction, offshore prep, etc.) often lack persistent environmental monitoring. Existing solutions are expensive, power-hungry, or not fit for ad-hoc deployment. This project builds a modular, low-cost, battery-powered sensor system to track environmental conditions and send data over Wi-Fi.

Objectives

Build a battery powered enviromental sensing device using ESP32 WROVER
Collect temperature, humidity and vibration data via I2C/SPI Sensors.
Transmit readings via MQTT over Wi-Fi to a central dashboard
Modular C++ firmware with sensor abstraction
Logging and fault detection (e.g. retry loops, Wi-Fi fallback)
Optimise for low power consumption using deep sleep and wake-on timer.
Move from breadboard to custom PCB.
Document design process and decisions for technical review.

Firmware Structure

Modular C++ Design using sensor driver classes
Use of FreeRTOS tasks
JSON Packaging of data
Sleep cycle with wake-on-timer
Error handling and reconnection logic

Communication

MQTT protocol over Wi-Fi
Configurable server endpoint
JSON payload

Power Budget & Strategy

Sleep between samples
Active time target. <500ms
Use esp_deep_sleep_start() between cycles
Estimate battery life per sample interval

Testing Plan

Unit tests for sensor modules (desktop simulation where possible)
Manual integration test on breadboard
Logging power consumption and sensor noise
MQTT connectivity tests in low signal conditions

Phase Plan

1. Breadboard with basic temp sensor + serial log
2. Add vibration sensor + Wi-Fi comms
3. Full sensor set + deep sleep + JSON output
4. Custom PCB design + test + battery integration
5. Enclosure, docs, polish, web dashboard (TBD)

Deliverables 

Firmware (C++)
Hardware Schematic (KiCAD)
PCB Design Files (Gerbers + BOM)
Technical write-up: design trade-offs, power analysis, lessons learned
Demnstration video.

