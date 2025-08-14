Heater Control System (ESP32 + DHT22)
Wokwi Project Link: https://wokwi.com/projects/439006205751180289
Project Overview
This project implements a temperature-based heater controller on an ESP32 using a
DHT22 sensor. It uses a state machine to manage heating behavior and includes bonus
features for BLE advertising, LED feedback, and FreeRTOS-based periodic operations.
Features
- State Machine with: Idle, Heating, Stabilizing, Target Reached, Overheat
- Continuous temperature reading from DHT22 sensor
- Heater control via relay (GPIO 5)
- Serial logging of temperature and state
- BLE advertising of current heating state
- LED visual feedback (GPIO 2) – solid ON while heating, blinking in overheat
- FreeRTOS task for periodic temperature checks (1s interval)
Hardware / Wiring (Wokwi Simulation)
Components:
- ESP32 DevKit V1
- DHT22 Temperature Sensor
- Relay Module
- LED for visual feedback
- 10k pull-up resistor for DHT22
Component ESP32 Pin
DHT22 VCC 3V3
DHT22 GND GND
DHT22 DATA GPIO 4
Relay VCC 3V3
Relay GND GND
Relay IN GPIO 5
LED Anode (+) GPIO 2
LED Cathode (-) GND
Libraries Required
- DHT sensor library (by Adafruit)
- Adafruit Unified Sensor
- BLE (built into ESP32 Arduino core)
How to Run (Wokwi)
- Open the Wokwi project link or import the provided sketch.ino and diagram.json into a
new ESP32 project.
- Install the required libraries.
- Click Run.
- Open the Serial Monitor (baud: 115200) to view temperature readings and state
transitions.
- Observe LED behavior: Solid ON = Heating, Blinking = Overheat, OFF = Idle / Target
Reached / Stabilizing.
Configuration
Temperature thresholds can be adjusted in sketch.ino: targetTemp = 30.0 // target
temperature (°C) overheatTemp = 40.0 // overheat cutoff (°C) stabilizingRange = 1.0 // ±
range before target
Future Improvements
- Additional overheat sensor for hardware redundancy
- Multiple heating profiles selectable via BLE or physical buttons
- PID temperature control for smoother stability
- Cloud dashboard integration for logging
Repository Contents
- sketch.ino - Main ESP32 Arduino code
- diagram.json - Wokwi wiring configuration
- README.md - Project documentation
- Design_Document.pdf - Part-1 system design
- block_diagram.png - Clean block diagram image
