# Embedded-Systems-Projects

This repository contains my embedded systems projects using **Arduino, Embedded C**, and various sensors & modules.  
It demonstrates hands-on implementation of **I2C & UART communication, motor control, sensor integration, and robotics**.

---

## **📂 Projects Overview**

### **Arduino Projects**
1. **Line Follower Robot**  
   - Components: Arduino Uno, L298N Motor Driver, IR Sensors, 4 DC Motors  
   - Description: Robot follows a black line on the floor using IR sensor input.  
   - Code: `Arduino/Line_Follower_Robot/Code/line_follower.ino`

2. **Bluetooth Controlled Robot**  
   - Components: Arduino Uno, L298N Motor Driver, HC-05 Bluetooth Module, 2 DC Motors  
   - Description: Control robot movements via Bluetooth from a mobile app.  
   - Code: `Arduino/Bluetooth_Controlled_Robot/Code/bluetooth_robot.ino`

3. **Sensor Integration**  
   - **I2C Sensor Example**: Reading temperature and motion sensors via I2C  
   - **UART Sensor Example**: Communicating with serial sensors  
   - Code: `Arduino/Sensor_Integration/`

---

### **Embedded C Projects**
1. **LED Blink**  
   - Platform: ATmega328P / STM32 (example)  
   - Description: Basic GPIO control using Embedded C  
   - Code: `Embedded_C/Microcontroller_Examples/LED_Blink/`

2. **UART Communication**  
   - Description: Sending & receiving data over UART protocol using Embedded C  
   - Code: `Embedded_C/Microcontroller_Examples/UART_Communication/`

---

## **📌 Key Skills Demonstrated**
- Embedded C programming & compilation  
- Arduino IDE programming  
- Sensor integration: IR, I2C, UART  
- Motor control & robotics using L298N driver  
- Bluetooth communication using HC-05  
- Basic line follower and obstacle avoidance robot design  

---

## **📁 Future Projects / Upgrades**
- Implement obstacle avoidance with ultrasonic sensors  
- Integrate OLED display with sensor data  
- Build an IoT-enabled robot with WiFi module (ESP8266/ESP32)  

---

## **📌 How to Run**
1. Install **Arduino IDE**  
2. Open the `.ino` file for the project  
3. Connect hardware according to the schematic  
4. Upload the code and test the project  

---

**Author:** Chandrakiran G   
**Email:** gchandrakiran97@gmail.com
