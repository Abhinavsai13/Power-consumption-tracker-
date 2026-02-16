⚡ Power Consumption Tracker
IoT-Based Smart Energy Monitoring System using ESP32

Real-Time Voltage, Current & Power Monitoring with Cloud Analytics

📌 Overview

This project presents the design and implementation of an IoT-enabled Smart Energy Monitoring System using the ESP32 microcontroller.

The system measures real-time electrical parameters such as:

RMS Voltage (V)

RMS Current (A)

Active Power (W)

Energy Consumption (Wh / kWh)

The measured data is transmitted via WiFi to the Blynk IoT Cloud Platform, enabling remote monitoring through a mobile and web dashboard.

This project integrates:

Embedded Systems

Power Electronics

Analog Signal Processing

IoT Cloud Communication

Real-Time Data Monitoring

🛠 Hardware Components
Component	Description
ESP32 Dev Board	WiFi-enabled 32-bit microcontroller
ACS712	Hall-effect based current sensor
ZMPT101B	AC voltage sensing module with isolation
Relay Module (Optional)	Overload cut-off protection
16x2 LCD (Optional)	Local real-time display
External Power Adapter	5V supply for ESP32
🔌 Pin Configuration
Module	ESP32 Pin
ACS712 OUT	GPIO 34
ZMPT101B OUT	GPIO 35
VCC	5V
GND	GND

⚠ Only ADC pins (GPIO 32–39) are used for analog sensing.

⚙️ Key Features

✅ Real-time Voltage Monitoring
✅ Real-time Current Monitoring
✅ Power Calculation (Watts)
✅ Energy Consumption Tracking (Wh / kWh)
✅ WiFi-based Cloud Dashboard
✅ Historical Data Visualization
✅ Expandable Overload Protection
✅ Modular and Scalable Architecture

☁ Cloud Integration

Platform Used: Blynk IoT

Cloud Capabilities

Live voltage, current & power graphs

Historical data logging

Remote monitoring via mobile app

Alert notifications

Expandable to smart billing system

🧮 Working Principle
1️⃣ Current Measurement

The ACS712 sensor uses Hall-effect sensing to measure AC current flowing through the load. It outputs a proportional analog voltage signal.

2️⃣ Voltage Measurement

The ZMPT101B module uses transformer isolation to safely measure AC mains voltage and provides a scaled analog output.

3️⃣ Signal Processing

The ESP32 performs:

12-bit ADC sampling

Signal scaling and calibration

RMS approximation

Power computation

4️⃣ Power Calculation
𝑃
=
𝑉
×
𝐼
P=V×I

Where:

P → Power (Watts)

V → Voltage (Volts)

I → Current (Amperes)

5️⃣ Energy Calculation
𝐸
𝑛
𝑒
𝑟
𝑔
𝑦
(
𝑊
ℎ
)
=
𝑃
𝑜
𝑤
𝑒
𝑟
×
𝑇
𝑖
𝑚
𝑒
Energy(Wh)=Power×Time

The system continuously accumulates energy usage over time.

🔬 Calibration Procedure

Proper calibration ensures measurement accuracy.

Voltage Calibration

Measure mains voltage using a multimeter.

Adjust ZMPT101B potentiometer.

Fine-tune voltageCalibration factor in code.

Current Calibration

Measure load current using clamp meter.

Adjust currentCalibration in firmware.

Compare readings until matched.

📊 Example Output
Parameter	Sample Value
Voltage	230 V
Current	0.45 A
Power	103 W
Energy	0.12 kWh
