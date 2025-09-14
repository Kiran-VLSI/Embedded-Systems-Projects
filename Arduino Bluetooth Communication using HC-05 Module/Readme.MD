 Arduino Bluetooth Communication using HC-05 Module

## Project Overview
This project demonstrates **serial communication between Arduino and a Bluetooth device** using the **HC-05 module**.  
The Arduino receives data from a mobile app or another Bluetooth device, processes it, and echoes it back.

---

## Components Required
- Arduino Uno  
- HC-05 Bluetooth Module  
- Jumper wires  
- USB cable for Arduino programming  

---

## Circuit Diagram / Connections

| HC-05 Pin | Arduino Pin | Notes                |
|-----------|-------------|--------------------|
| VCC       | 5V          | Power supply        |
| GND       | GND         | Ground              |
| TXD       | RX (Pin 10) | Arduino SoftwareSerial RX |
| RXD       | TX (Pin 11) | Arduino SoftwareSerial TX |
| EN / KEY  | Not connected | Optional for AT mode |

---

## Code Example

```cpp
#include <SoftwareSerial.h>

SoftwareSerial BTSerial(10, 11); // RX, TX pins for Bluetooth
String incomingData;

void setup() {
  Serial.begin(9600);
  BTSerial.begin(9600);
  Serial.println("HC-05 Bluetooth Module Ready");
}

void loop() {
  if (BTSerial.available()) {
    incomingData = BTSerial.readString();
    Serial.print("Received from BT: ");
    Serial.println(incomingData);

    // Echo back the received data
    BTSerial.print("Echo: ");
    BTSerial.println(incomingData);
  }
}
````

---

## How it Works

1. The **Arduino communicates** with the HC-05 module over **SoftwareSerial** on pins 10 and 11.
2. When the Bluetooth device sends data, Arduino **reads the incoming string** and prints it to the Serial Monitor.
3. Arduino **echoes back the received data** to the sending device for confirmation.
4. The project can be extended to **control LEDs, motors, or other peripherals** based on the received data.

---

## Key Features

* Wireless communication using HC-05 Bluetooth module
* Real-time serial data reading and echo
* Can control peripherals like LEDs, motors, or robots
* Expandable to more advanced Bluetooth projects

---

## Applications

* Bluetooth-controlled robots
* Wireless sensor data transmission
* Home automation and IoT projects

---

```
