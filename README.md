# AC-Energy-Meter-with-PZEM-004T-ESP32-WebServer
In this project, we will create an IoT-based AC Energy Meter using the ESP32 microcontroller and the PZEM-004T module, a high-precision AC power monitoring solution.


PZEM-004T Multifunction AC Digital Meter
The PZEM-004T is a compact, single-phase AC power monitoring module designed to measure electrical parameters such as voltage (80–260V), current (up to 100A via external CT), active power, energy consumption (kWh), frequency, and power factor.
![image](https://github.com/user-attachments/assets/49ec5d0f-bdb4-4bf8-9212-0f19904b75e6)

PZEM-004T V3.0
Fig: PZEM-004T V3.0
It communicates via Modbus-RTU protocol over TTL serial (), making it easy to interface with microcontrollers like Arduino or ESP32. With built-in galvanic isolation and a non-invasive current transformer, it prioritizes safety. It is widely used in IoT applications, smart metering, and home automation projects.

The PZEM-004T is an energy monitoring module that communicates via UART (RS485) and has the following pin configuration:

Pinout of PZEM-004T V3.0
![image](https://github.com/user-attachments/assets/ab94f836-698d-4ad6-8132-105a265bcebd)


1. Power & Measurement Pins:

L (Live) & N (Neutral): Connect to AC mains for voltage measurement and module power.
CT+ & CT-: Connect to the current transformer (CT) for current measurement.
2. Communication Pins (TTL Serial or RS485):

5V: Power supply for the module (external 5V required).
GND: Ground reference for communication.
TX (Transmit): Sends data to the microcontroller.
RX (Receive): Receives data from the microcontroller.

Module TTL Interface Note: This module’s TTL interface is passive and requires an external 5V power supply. All four pins (5V, RX, TX, GND) must be connected for proper communication. Operating temperature range: -20°C to +60°C.


![image](https://github.com/user-attachments/assets/345af93b-ecd8-4096-b1b1-7ee73bba8dd9)

Power Indicator Light: Shows that the module is powered and operational.
Pulse Indicator Light: It blinks based on active energy measurement. The higher blinking rate indicates higher power consumption.
TX Communication Light: Blinks when the module transmits data via RS485.
RX Communication Light: Blinks when the module receives data from the master device (e.g., Arduino, ESP32).

Circuit Diagram & Connections
![image](https://github.com/user-attachments/assets/cc71001d-75c6-4fdb-aaea-cba12d38ccdd)

Connect the PZEM-004T’s 5V and GND to ESP32’s 5V and GND for power. Link TX (PZEM) → RX2 (ESP32 pin 16) and RX (PZEM) → TX (ESP32 pin 17) for serial communication.

Wire the live (L) and neutral (N) of your AC supply (120V/220V) to the PZEM’s AC input terminals (labeled “L” and “N”).

For Open CT (split-core): Clamp the CT around the live wire of the AC circuit you want to monitor (do NOT clamp neutral).
For Close CT (solid-core): Disconnect the circuit, thread the live wire through the CT’s core, and reconnect.


PZEM-004T Arduino Library. 
https://github.com/mandulaj/PZEM-004T-v30


