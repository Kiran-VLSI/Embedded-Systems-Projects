 📌 UART Communication Between Two Arduinos

## 📖 Project Overview
This project demonstrates how two **Arduino Uno** boards can communicate with each other using the **UART (Universal Asynchronous Receiver/Transmitter)** protocol.  
It forms the foundation for more advanced projects such as **robot control**, **home automation**, and **multi-device communication**.

- **Arduino 1 (Transmitter):** Sends serial data (numbers, characters, or sensor values).  
- **Arduino 2 (Receiver):** Receives data and displays it on the Serial Monitor (or LCD).  

---

## 🛠️ Components Required
- 2 × Arduino Uno  
- Jumper wires (Male-to-Male)  
- 2 × USB cables (for uploading code and Serial Monitor)  
- (Optional) 16x2 LCD with I2C module for display  

---

## 🔌 Circuit Connections
| Arduino 1 | Arduino 2 |
|-----------|-----------|
| TX (11)   | RX (10)   |
| RX (10)   | TX (11)   |
| GND       | GND       |

⚠️ Always connect the **GNDs together** to complete the communication circuit.

---

## 💻 Arduino Code

### 🔹 Arduino 1 (Transmitter)
```cpp
#include <SoftwareSerial.h>

// SoftwareSerial on pins 10 (RX), 11 (TX)
SoftwareSerial mySerial(10, 11);

void setup() {
  Serial.begin(9600);     // Debugging on Serial Monitor
  mySerial.begin(9600);   // Start UART communication
  Serial.println("Transmitter Ready");
}

void loop() {
  mySerial.println("Hello from Arduino 1");  // Send data
  Serial.println("Message Sent");
  delay(1000);  // Send every second
}
````

---

### 🔹 Arduino 2 (Receiver)

```cpp
#include <SoftwareSerial.h>

// SoftwareSerial on pins 10 (RX), 11 (TX)
SoftwareSerial mySerial(10, 11);

void setup() {
  Serial.begin(9600);     // Debugging on Serial Monitor
  mySerial.begin(9600);   // Start UART communication
  Serial.println("Receiver Ready");
}

void loop() {
  if (mySerial.available()) {
    String received = mySerial.readStringUntil('\n');
    Serial.print("Received: ");
    Serial.println(received);
  }
}
```

---

## 📊 Expected Output

* **Transmitter Arduino (Serial Monitor):**

  ```
  Transmitter Ready
  Message Sent
  Message Sent
  ...
  ```

* **Receiver Arduino (Serial Monitor):**

  ```
  Receiver Ready
  Received: Hello from Arduino 1
  Received: Hello from Arduino 1
  ...
  ```
---

## 🚀 Future Extensions

* 🔹 Robot control using UART (Master Arduino sends commands, Slave Arduino drives motors via L298N).
* 🔹 Multi-sensor network (multiple Arduinos send data to one central Arduino).
* 🔹 Wireless UART communication using HC-05 Bluetooth module.

---

## ✅ Key Learning Outcomes

* Understanding **UART serial communication** between two microcontrollers.
* Hands-on with **SoftwareSerial library** in Arduino.
* Building a base for **multi-Arduino communication projects**.

---

