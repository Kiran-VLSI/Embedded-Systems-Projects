# I2C Protocol Implementation using Arduino Uno and 16x2 LCD Display

## Project Overview
This project demonstrates the **I2C communication protocol** between an Arduino Uno and a **16x2 LCD display**.  
The goal is to simplify LCD interfacing by using the **I2C module**, reducing the number of GPIO pins required.

---

## Components Required
- Arduino Uno  
- 16x2 LCD Display with I2C module (PCF8574 or similar)  
- Jumper wires  
- Breadboard (optional)  
- USB cable for Arduino programming  

---

## Circuit Diagram / Connections
| LCD Pin | I2C Module Pin | Arduino Uno Pin |
|---------|----------------|----------------|
| GND     | GND            | GND            |
| VCC     | VCC            | 5V             |
| SDA     | SDA            | A4             |
| SCL     | SCL            | A5             |

**Note:**  
- SDA → Analog Pin 4  
- SCL → Analog Pin 5  

## How it Works

1. The **I2C protocol** allows communication with the LCD using **only 2 pins (SDA & SCL)**.
2. Arduino sends commands/data over the I2C bus to control the LCD.
3. The LCD displays the text sent from the Arduino code.
4. The library **LiquidCrystal\_I2C** simplifies communication and command handling.

---

## Key Features

* Minimal pin usage with I2C (vs 6-7 pins in parallel mode)
* Backlight control
* Easy text updates
* Can be expanded to display sensor readings dynamically

---

## Applications

* Display sensor values (temperature, humidity, distance, etc.)
* Arduino-based user interface projects
* Embedded systems learning for I2C communication

---

