# Smart Dustbin using Arduino Uno 🗑️🤖

An Arduino-based smart dustbin featuring a touchless motion-activated lid and a moisture sensor for automatic wet/dry waste segregation.

## Description

This project is an automated, touchless Smart Dustbin built using an Arduino Uno. It is designed to improve hygiene and automate waste segregation at the source. 

The system relies on two main sensors:
* **PIR Motion Sensor:** Detects a person's presence and automatically opens the bin lid using a servo motor, allowing for a completely hands-free experience.
* **Soil Moisture Sensor:** Evaluates the waste deposited into the bin to classify it as either "Wet" or "Dry" waste, paving the way for easier recycling and automated waste management. 

---

## Features

* **Touchless Operation:** Opens automatically when a hand or object is waved in front of it.
* **Waste Classification:** Detects the moisture level of the waste to determine if it is wet or dry.
* **Auto-Closing:** The lid closes automatically after a set delay.
* **Serial Monitoring:** Outputs real-time moisture data and waste classification to the Arduino Serial Monitor.

---

## Hardware Components

To build this project, you will need the following components:

* 1x Arduino Uno R3
* 1x PIR Motion Sensor
* 1x Soil Moisture Sensor
* 1x Servo Motor (SG90 for small bins, MG995 for larger/heavier lids)
* Jumper Wires (Male-to-Male, Male-to-Female)
* 1x Breadboard
* Power Supply / Battery (for the Arduino)

---

## Circuit Connections

Make the connections between your components and the Arduino Uno as follows:

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

> **Note:** If your servo motor is jittery or drawing too much power, consider powering it with an external 5V power supply rather than directly from the Arduino 5V pin. Ensure all ground (GND) pins share a common connection.

---

## Software & Prerequisites

* **Arduino IDE:** You will need the [Arduino IDE](https://www.arduino.cc/en/software) installed on your computer to upload the code.
* **Servo Library:** The code utilizes the standard `<Servo.h>` library, which comes pre-installed with the Arduino IDE.

---

## Installation & Setup

1. **Clone the Repository:**
   Download or clone this repository to your local machine using:
   `git clone https://github.com/YourUsername/Smart-Dustbin.git`

2. **Assemble the Hardware:**
   Connect the PIR sensor, moisture sensor, and servo motor to the Arduino according to the circuit connections table above.

3. **Upload the Code:**
   * Open `Smart_Dustbin.ino` in the Arduino IDE.
   * Select your board (**Tools > Board > Arduino Uno**).
   * Select the correct port (**Tools > Port**).
   * Click the **Upload** button.

4. **Test the System:**
   * Open the **Serial Monitor** (set baud rate to 9600).
   * Wave your hand in front of the PIR sensor; the servo should actuate to open the lid.
   * Touch the moisture sensor with a damp cloth to see the moisture levels change on the Serial Monitor.

---

## Future Improvements

* Add an LCD/OLED display to visually indicate "Wet Waste" or "Dry Waste".
* Add an Ultrasonic Sensor to measure how full the bin is and alert the user when it needs to be emptied.
* Implement an ESP8266/ESP32 Wi-Fi module to send IoT alerts to a smartphone when the bin is full.

---

## License

This project is open-source and available under the [MIT License](LICENSE).
