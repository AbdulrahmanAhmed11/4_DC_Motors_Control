# 4_DC_Motors_Control
Arduino-based 4WD robotic movement routine controlled via L293D motor driver for automated timed navigation.

## 1. Description
This repository contains a complete simulation and code implementation for controlling a 4-Wheel Drive (4WD) robotic chassis. Utilizing an Arduino Uno and an L293D Motor Driver IC, the system is programmed to autonomously execute a specific time-based movement routine:
1. **Move Forward** for exactly 30 seconds.
2. **Move Backward** for exactly 1 minute.
3. **Alternate Turns:** Turn right for 15 seconds, then left for 15 seconds (repeating twice to complete 1 minute of alternating movement).

## 2. Hardware Components
- 1x Arduino Uno
- 1x L293D Motor Driver IC (H-Bridge)
- 4x DC Motors
- 1x 9V Battery (Dedicated power source for motors)
- 1x Breadboard
- Jumper Wires

## 3. Circuit Wiring Details
Proper power isolation is critical in this design to protect the microcontroller logic:
- **Power Isolation:** The Arduino provides a `5V` logic signal to the L293D (Pins 1, 9, and 16). The external `9V` battery is connected directly to Pin 8 (VCC2) of the L293D to handle the high current draw of the four DC motors. A common ground is established across the entire circuit.
- **Parallel Motor Connection:** The two left motors are wired in parallel to Output 1 & 2. The two right motors are wired in parallel to Output 3 & 4. This differential drive setup allows skid-steering navigation.
- **Control Pins:**
  - Left Motors (IN1, IN2) ➔ Arduino Pins `10`, `9`
  - Right Motors (IN3, IN4) ➔ Arduino Pins `6`, `5`

## 4. Circuit Diagram
Below is the correct wiring schematic implemented in TinkerCAD:

<img width="1650" height="849" alt="Circuit Diagram" src="https://github.com/user-attachments/assets/669ced68-8db7-429f-a115-601211672e75" />

## 5. TinkerCAD Live Simulation
You can view, inspect the circuit, and run the simulation directly through the following link:

🔗 **[Click Here to Open the TinkerCAD Project](https://www.tinkercad.com/things/8UCO1oiU0n5-4dcmotorscontrol/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits)**



## 6. Engineering Context
Configuring hardware components like H-bridge motor drivers for differential drive systems is a foundational skill in robotics. This movement routine serves as a core module for developing fully autonomous robotic platforms capable of precise environmental navigation, completed as part of the Smart Methods summer robotics intensive.
