# 🔌 Arduino & Embedded Systems Projects

This repository contains multiple **Arduino and Embedded Systems** projects implemented using various sensors, communication protocols, and actuators. Each project folder includes the **code, circuit diagrams, and documentation**.

---

## 📂 Project List

### 1️⃣ [Arduino Bluetooth Communication using HC-05](./Arduino%20Bluetooth%20Communication%20using%20HC-05)  
- Uses **HC-05 Bluetooth Module** to establish wireless communication with Arduino.  
- Control devices or send/receive data via a smartphone or PC.  

---

### 2️⃣ [Arduino Temperature & Humidity Monitor with LCD & Buzzer](./Arduino%20Temperature%20%26%20Humidity%20Monitor%20with%20LCD%20%26%20Buzzer)  
- Measures **temperature & humidity** using a **DHT22 sensor**.  
- Displays values on a **16x2 I2C LCD display**.  
- **Buzzer alert** if temperature goes below 20°C or above 40°C.  

---

### 3️⃣ [I2C Protocol Implementation using Arduino UNO and 16x2 LCD](./I2C%20Protocol%20Implementation%20using%20Arduino%20UNO%20and%2016x2%20LCD)  
- Demonstrates **I2C communication protocol**.  
- Arduino communicates with an **I2C-based 16x2 LCD**.  
- Displays sensor values and messages efficiently using only 2 wires (SDA & SCL).  

---

### 4️⃣ [Robot using Arduino Uno and L298N Motor Driver](./Robot%20using%20Arduino%20Uno%20and%20L298N%20Motor%20Driver)  
- **4-wheel robot** built using **Arduino UNO** and **L298N Motor Driver**.  
- Controlled using **IR sensors** for **line-following functionality**.  
- Can be extended with **Bluetooth (HC-05)** for wireless control.

---

### 5️⃣ [UART Communication Between Two Arduinos](./UART%20Communication%20Between%20Two%20Arduinos)  
- Demonstrates **UART communication** using **TX/RX pins**.  
- **Arduino 1 (Transmitter):** Sends numbers/strings continuously.  
- **Arduino 2 (Receiver):** Receives and displays data on the **Serial Monitor** (or LCD).  
- Foundation for advanced projects like **robot control over UART**.  

---

## 🛠️ Tools & Technologies
- **Arduino IDE** / Wokwi Online Simulator  
- **Embedded C / Arduino C**  
- **Communication Protocols:** I2C, UART, Bluetooth (HC-05)  
- **Actuators & Sensors:** Motors, IR Sensors, DHT22, LCD Display, Buzzer  

---

## 🚀 How to Run
1. Open the Arduino code (`.ino`) in **Arduino IDE**.  
2. Select the correct **board (Arduino UNO)** and **port**.  
3. Upload the code to your Arduino board.  
4. Connect hardware as per the circuit diagrams in each project folder.  

---

## 📌 Future Enhancements
- Add **IoT integration (ESP8266/ESP32 + MQTT)**.  
- Mobile app-based control using **MIT App Inventor**.  
- Data logging using **SD Card Module**.  

---

## 👨‍💻 Author
Chandrakiran G 

---
