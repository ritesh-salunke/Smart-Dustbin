# Automated Wet/Dry Waste Sorting Smart Dustbin 🗑️♻️

An Arduino-based smart sorting dustbin that automatically classifies and segregates waste into two separate compartments (Wet and Dry) using a moisture sensor and a motorized tilting platform.

## Description

This project automates waste segregation at the source. Instead of a traditional lid, the top of the dustbin consists of a resting platform. When a user places trash on this platform, the system triggers a sorting sequence:
1. **Detection:** A PIR Motion Sensor detects the user's hand placing the trash.
2. **Classification:** A Soil Moisture Sensor embedded in the platform evaluates the waste to determine if it is "Wet" or "Dry".
3. **Segregation:** A Servo Motor tilts the platform left or right, dropping the waste into the corresponding Wet or Dry compartment below.

---

## Features

* **Auto-Sorting Mechanism:** Motorized flap that routes garbage into two distinct bins.
* **Moisture-Based Classification:** Instantly detects the water content of the waste.
* **Touchless Trigger:** Uses a PIR motion sensor to initiate the scanning and sorting process once the user steps away.
* **Serial Monitoring:** Real-time moisture data and sorting logs via the Arduino Serial Monitor.

---

## Hardware Components

* 1x Arduino Uno R3
* 1x PIR Motion Sensor
* 1x Soil Moisture Sensor
* 1x Servo Motor (MG995 recommended for torque to hold and drop waste)
* Jumper Wires
* 1x Breadboard
* Power Supply

---

## Circuit Connections

| Component | Pin | Arduino Uno Pin |
| :--- | :--- | :--- |
| **PIR Sensor** | VCC | 5V |
| | OUT | Digital Pin 2 |
| | GND | GND |
| **Moisture Sensor**| VCC | 5V |
| | A0 (Analog Out) | Analog Pin A0 |
| | GND | GND |
| **Servo Motor** | VCC (Red) | 5V |
| | Signal (Yellow/Orange)| Digital Pin 9 |
| | GND (Brown/Black) | GND |

> **Note on Servo Power:** Because the servo must hold the weight of the garbage on the platform, it is highly recommended to power the servo with an external 5V power supply rather than the Arduino to prevent the board from resetting. Connect the ground (GND) of the external power supply to the Arduino GND.

---

## How to Use

1. Upload the `Smart_Dustbin.ino` code to your Arduino Uno.
2. Open the Serial Monitor (9600 baud).
3. Place waste on the center platform. The PIR sensor will detect your movement.
4. Remove your hand. The system waits 2 seconds for the waste to settle.
5. The moisture sensor reads the data.
6. The servo tilts to **0° for Wet Waste** or **180° for Dry Waste**, dropping the trash into the correct bin, then returns to the **90° neutral position**.
