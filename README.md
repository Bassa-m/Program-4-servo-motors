# Program 4 servo motors

## Project Overview
The goal of this task is to program 4 servo motors connected to an Arduino Uno to perform two consecutive movements in order:
1. **First Movement:** Once the simulation starts, all 4 motors move together back and forth (Sweep mode) continuously for exactly 2 seconds.
2. **Second Movement:** After the 2 seconds finish, all motors immediately stop and hold their position at a 90-degree angle.

---

## Components Used
* Arduino Uno R3
* 4x Micro Servo Motors
* Jumper Wires

---

## Wiring & Connections
* **Signal Wires (Yellow):** Connected to digital pins 9, 10, 11, and 12 in order:
  - Servo 1 -> Pin 9
  - Servo 2 -> Pin 10
  - Servo 3 -> Pin 11
  - Servo 4 -> Pin 12
* **Power Wires (Red):** All combined and connected together to the **5V** pin on the Arduino.
* **Ground Wires (Black):** All combined and connected together to the **GND** pin on the Arduino to complete the circuit.

---

## Code Logic
To make the timing precise and ensure all 4 motors move smoothly at the same time, I avoided using the traditional `delay()` function because it freezes the processor. Instead, I used `millis()` to track the real-time execution.

I organized the code into two separate functions for cleaner structure:
* `runSweepMovement()`: Controls the back-and-forth movement during the first 2 seconds.
* `fixAt90Degrees()`: Stops all motors and holds them firmly at 90 degrees after the time is up.
*
