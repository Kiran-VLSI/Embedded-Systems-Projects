 🌡️ Arduino Temperature & Humidity Monitor with Buzzer Alert

This project uses an **Arduino UNO**, **DHT22 sensor**, **I2C LCD display**, and a **Buzzer** to monitor temperature and humidity in real-time.  
If the temperature goes **below 20°C** or **above 40°C**, the buzzer will automatically turn ON.

---

## 📌 Components Required
- Arduino UNO
- DHT22 Temperature & Humidity Sensor
- 16x2 I2C LCD Display
- Buzzer
- Jumper wires
- Breadboard

---

## ⚡ Circuit Connections

- **DHT22 Sensor**
  - VCC → 5V
  - GND → GND
  - Data → D2

- **I2C LCD**
  - VCC → 5V
  - GND → GND
  - SDA → A4
  - SCL → A5

- **Buzzer**
  - + → D8
  - – → GND

---

## 🖥️ Code

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include "DHT.h"

#define DHTPIN 2
#define DHTTYPE DHT22
const int buzzerPin = 8;

DHT dht(DHTPIN, DHTTYPE);
LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup() {
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
  dht.begin();
  lcd.init();
  lcd.backlight();
}

void loop() {
  float temperatureC = dht.readTemperature();
  float humidity = dht.readHumidity();

  if (isnan(temperatureC) || isnan(humidity)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  Serial.print("Temp: ");
  Serial.print(temperatureC);
  Serial.print(" °C  Hum: ");
  Serial.print(humidity);
  Serial.println(" %");

  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Temp: ");
  lcd.print(temperatureC);
  lcd.print(" C");

  lcd.setCursor(0, 1);
  lcd.print("Hum: ");
  lcd.print(humidity);
  lcd.print(" %");

  if (temperatureC < 20 || temperatureC > 40) {
    digitalWrite(buzzerPin, HIGH);
  } else {
    digitalWrite(buzzerPin, LOW);
  }

  delay(2000);
}
````

---

## 🚀 Features

* Reads **Temperature & Humidity** using DHT22
* Displays values on **16x2 I2C LCD**
* Sends data to **Serial Monitor**
* Activates buzzer alarm when temperature is **out of safe range (20°C–40°C)**

---

## 🛠️ Future Enhancements

* Add **Bluetooth (HC-05)** module for wireless monitoring
* Add **data logging** to SD card
* Use a **relay** to control fan/heater automatically

---

## 📷 Simulation (Wokwi)

You can simulate this project online using **Wokwi Arduino Simulator**.
[👉 Try it on Wokwi]=https://wokwi.com/projects/441875695577859073

---
