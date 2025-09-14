Robot using Arduino Uno and L298N Motor Driver

## Project Overview
This project implements a **Line Follower Robot** using **Arduino Uno**, an **L298N motor driver module**, and **IR sensors**.  
The robot can detect and follow a black line on a white surface (or vice versa) using two IR sensors.

---

## Components Required
- Arduino Uno  
- L298N Motor Driver Module  
- 4 DC Motors with chassis  
- 2 IR Sensors (Left & Right)  
- 7V–12V Battery Pack (18650 or Li-ion)  
- Switch  
- Jumper wires  

---

## Circuit Diagram
![Line Follower Robot Circuit](circuit_diagram.jpg)

**Connections:**
- **IR Sensors → Arduino**  
  - Left IR Sensor → Digital Pin 2  
  - Right IR Sensor → Digital Pin 3  
  - VCC → 5V, GND → GND  

- **Motor Driver (L298N) → Arduino**  
  - IN1 → Pin 8  
  - IN2 → Pin 9  
  - IN3 → Pin 10  
  - IN4 → Pin 11  

- **Motor Driver → Motors**  
  - Motor A → Left-side motors  
  - Motor B → Right-side motors  

- **Motor Driver Power**  
  - VCC → 7V–12V Battery +  
  - GND → Battery - and Arduino GND  
  - 5V → Arduino 5V  

---

## Code Example

```cpp
int leftSensor = 2;
int rightSensor = 3;
int in1 = 8;
int in2 = 9;
int in3 = 10;
int in4 = 11;

void setup() {
  pinMode(leftSensor, INPUT);
  pinMode(rightSensor, INPUT);
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);
}

void loop() {
  int left = digitalRead(leftSensor);
  int right = digitalRead(rightSensor);

  if (left == 0 && right == 0) {
    // Move Forward
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW);
  }
  else if (left == 1 && right == 0) {
    // Turn Right
    digitalWrite(in1, LOW);
    digitalWrite(in2, HIGH);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW);
  }
  else if (left == 0 && right == 1) {
    // Turn Left
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, LOW);
    digitalWrite(in4, HIGH);
  }
  else {
    // Stop (both sensors see white)
    digitalWrite(in1, LOW);
    digitalWrite(in2, LOW);
    digitalWrite(in3, LOW);
    digitalWrite(in4, LOW);
  }
}
````

---

## How it Works

1. IR sensors detect black/white surfaces.
2. Arduino reads sensor values.
3. Based on conditions:

   * Both LOW → Move forward
   * Left HIGH, Right LOW → Turn right
   * Left LOW, Right HIGH → Turn left
   * Both HIGH → Stop
4. L298N motor driver drives the motors accordingly.

---

## Applications

* Autonomous line-following robots
* Smart car navigation
* Industrial AGVs (Automated Guided Vehicles)

---
