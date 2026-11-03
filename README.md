# Smart Radar Equipment Health Monitoring System

### An IoT-Based Approach for Vibration and Thermal Condition Monitoring of Radar Equipment Enclosures

## 📌 Project Overview

The **Smart Radar Equipment Health Monitoring System** is an IoT-based embedded monitoring solution designed to monitor selected environmental and mechanical conditions around radar equipment enclosures.

Electronic equipment used in radar and defence applications may be exposed to abnormal vibration, temperature variations, and potentially hazardous conditions. Continuous monitoring of these parameters can help identify unusual operating conditions at an early stage.

This project uses an ESP32 microcontroller integrated with multiple sensors to monitor vibration, temperature, humidity, and gas/smoke-related readings. The collected sensor data is processed to identify abnormal conditions. Visual and audio indicators provide local alerts, while Telegram notifications and a monitoring dashboard enable remote observation.

The proposed system is intended as a **supplementary condition-monitoring solution** that can be adapted for equipment enclosures without requiring modifications to the primary radar control system.

## 🎯 Problem Statement

Radar equipment and associated electronic systems require reliable operating conditions. Excessive vibration, abnormal temperature variations, and smoke or gas-related conditions may indicate environmental or equipment-related issues.

Without additional monitoring, identifying these conditions may depend on periodic manual inspection or the availability of existing equipment diagnostics.

This project proposes a low-cost IoT-based monitoring system that continuously observes selected parameters and provides alerts when configured abnormal conditions are detected.

## 🎯 Project Objectives

* Monitor vibration and acceleration using an MPU6050 sensor.
* Measure temperature and humidity using a DHT22 sensor.
* Monitor gas/smoke-related sensor readings using an MQ-2 sensor.
* Process sensor readings using an ESP32 microcontroller.
* Provide local status indications using LEDs.
* Activate a buzzer when configured alert conditions are detected.
* Send remote notifications through a Telegram bot.
* Display monitoring information through a dashboard.
* Develop a low-cost supplementary monitoring prototype for electronic equipment enclosures.

## 🛠️ Hardware Components

| Component               | Purpose                               |
| ----------------------- | ------------------------------------- |
| ESP32 Development Board | Main controller and IoT communication |
| MPU6050                 | Vibration and acceleration monitoring |
| DHT22                   | Temperature and humidity measurement  |
| MQ-2 Gas Sensor         | Gas/smoke-related sensing             |
| Red LED                 | Abnormal-condition indication         |
| Green LED               | Normal-condition indication           |
| Buzzer                  | Audible warning                       |
| Connecting Wires        | Hardware interconnections             |
| Breadboard              | Prototype circuit assembly            |
| Power Supply            | Provides power to the system          |

## 💻 Software and Technologies

| Technology             | Application                                                              |
| ---------------------- | ------------------------------------------------------------------------ |
| ESP32                  | Embedded system controller                                               |
| MicroPython / Firmware | Sensor interfacing and system control (specify the actual firmware used) |
| Telegram Bot API       | Remote notifications                                                     |
| Dashboard              | Remote sensor-data visualization                                         |
| IoT Communication      | Data transmission and monitoring                                         |

## 🏗️ System Architecture

The system follows a sensor-to-controller-to-monitoring architecture.

**Overall Working Flow:**

```text
       RADAR EQUIPMENT ENCLOSURE
                  |
       +----------+----------+
       |          |          |
    MPU6050     DHT22      MQ-2
   Vibration  Temperature  Gas/Smoke
   Monitoring  & Humidity  Monitoring
       |          |          |
       +----------+----------+
                  |
             ESP32 MCU
                  |
       Sensor Data Processing
                  |
       Configured Condition Checks
                  |
       +----------+-----------+
       |          |           |
    Green LED   Red LED     Buzzer
       |          |           |
       +----------+-----------+
                  |
          Wi-Fi Communication
                  |
       +----------+-----------+
       |                      |
  Telegram Bot           Monitoring
  Notifications           Dashboard
```

## ⚙️ Working Principle

### 1. Vibration Monitoring

The MPU6050 accelerometer and gyroscope sensor measures acceleration and angular motion along its axes. These readings can be used to monitor vibration-related changes in the equipment enclosure.

Abnormal readings can be identified using configured limits or suitable signal-processing methods.

### 2. Temperature and Humidity Monitoring

The DHT22 sensor measures the surrounding temperature and relative humidity.

The ESP32 reads these values and checks whether the measured environmental conditions exceed the configured operating limits.

### 3. Gas and Smoke Monitoring

The MQ-2 sensor provides readings associated with certain combustible gases and smoke.

The sensor output is monitored to identify readings that cross the configured alert threshold. This provides an additional environmental warning mechanism.

### 4. Condition Processing

The ESP32 collects readings from the connected sensors and evaluates them against configured conditions.

Based on the monitoring results, the system determines whether the observed conditions are normal or require attention.

### 5. Alert Indication

The system uses local indicators to communicate its monitoring status:

* Green LED: Normal operating condition.
* Red LED: Abnormal condition detected.
* Buzzer: Audible warning when the configured alarm condition is triggered.

### 6. Remote Monitoring

The ESP32 uses Wi-Fi connectivity to communicate monitoring information.

Telegram notifications provide remote alerts, while the dashboard displays sensor readings and system status for easier observation.

## ⭐ Key Features

* Multi-sensor monitoring using ESP32.
* Vibration and acceleration measurement.
* Temperature and humidity monitoring.
* Gas/smoke-related environmental monitoring.
* Local visual and audible alerts.
* Remote Telegram notifications.
* Dashboard-based monitoring.
* Low-cost embedded IoT prototype.
* Potential for integration with equipment-enclosure monitoring applications.

## 📊 Applications

The proposed monitoring approach can be explored in:

* Radar equipment enclosures.
* Defence electronic equipment rooms.
* Industrial control panels.
* Communication equipment cabinets.
* Electronic instrumentation enclosures.
* Remote equipment monitoring systems.

## 🚀 Future Enhancements

The project can be further improved through:

1. **Advanced Vibration Analysis:** Implement vibration RMS, frequency-domain analysis, and more robust signal-processing techniques.
2. **Temperature Trend Analysis:** Analyse temperature variations over time to identify gradual changes.
3. **Intelligent Anomaly Detection:** Explore machine-learning-based anomaly detection using collected sensor data.
4. **Data Logging:** Store historical sensor readings for trend analysis and maintenance records.
5. **Multi-Level Alerts:** Introduce warning, critical, and emergency alert levels.
6. **Industrial-Grade Sensors:** Upgrade to more accurate and reliable sensors suitable for real equipment environments.
7. **Improved Communication:** Explore more reliable communication methods for remote monitoring applications.

## ⚠️ Project Limitations

* The MPU6050 provides motion and acceleration measurements; it does not independently identify the exact mechanical fault.
* The DHT22 measures local ambient temperature and humidity, not the internal temperature of individual electronic components.
* The MQ-2 is a general gas/smoke-related sensor and is not a certified fire-detection device.
* The system monitors selected external conditions and does not directly evaluate radar RF performance or internal electronic faults.
* Threshold-based alerts depend on proper sensor calibration and configuration.
* Remote monitoring through Telegram and the dashboard depends on network connectivity.

**Note:** This project is a prototype for supplementary equipment-condition monitoring. It is not a replacement for certified defence equipment diagnostics, safety systems, or existing radar monitoring mechanisms.

## 📁 Repository Structure

```text
Smart-Radar-Equipment-Health-Monitoring/
│
├── README.md
│
├── 01_Source_Code/
│   └── ESP32_Firmware.py
│
├── 02_Circuit_Diagrams/
│   └── Circuit_Diagram.png
│
├── 03_Project_Images/
│   ├── Hardware_Setup.jpg
│   └── Sensor_Connections.jpg
│
├── 04_Dashboard/
│   └── Dashboard_Files/
│
├── 05_Documentation/
│   └── Project_Report.pdf
│
└── 06_Presentation/
    └── Project_Presentation.pptx
```

*The filenames above are examples. Update this structure to match the files actually included in your repository.*

## 🔧 Installation and Setup

### Prerequisites

* ESP32 development board.
* Required sensors and electronic components.
* USB cable for programming the ESP32.
* Appropriate firmware development environment.
* Wi-Fi connection.
* Telegram bot credentials, if Telegram notifications are enabled.
* Dashboard software and its dependencies, if applicable.

### Setup Procedure

1. Clone or download this repository.
2. Assemble the hardware according to the circuit diagram.
3. Install the required firmware environment and libraries.
4. Configure the ESP32 sensor connections and GPIO pins according to the actual circuit.
5. Configure Wi-Fi credentials securely.
6. Configure Telegram bot credentials if remote notifications are enabled.
7. Upload the firmware to the ESP32.
8. Start the dashboard using the instructions provided in its source folder.
9. Power the hardware and verify sensor readings and alert functionality.

Refer to the source-code folder for the actual implementation and configuration instructions.

## 👨‍💻 Project Information

**Project Title:** Smart Radar Equipment Health Monitoring System

**Domain:** Embedded Systems | Internet of Things | Condition Monitoring

**Controller:** ESP32

**Project Type:** IoT-Based Embedded System Prototype

**Author:** Dharaneeswaran M.

**Department:** Electronics and Communication Engineering (ECE)

**Institution:** Kalasalingam Academy of Research and Education

## 📜 License

This project is intended for educational, learning, and research purposes.

Refer to the repository's LICENSE file for the applicable usage and distribution terms.

## ⭐ Acknowledgement

This project was developed as an academic engineering initiative to explore embedded systems, sensor integration, IoT communication, remote monitoring, and equipment-condition monitoring.

If you find this project useful, consider giving the repository a ⭐ on GitHub!
