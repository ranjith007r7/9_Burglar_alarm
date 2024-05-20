# 9_Burglar_alarm
A simple Burglar alarm

# Burglar Alarm System

## Overview

This project implements a burglar alarm system using an Arduino, a ultrasonic distance sensor (NewPing), a passive infrared (PIR) motion sensor, a buzzer, and a 16x2 LCD screen. The system detects intruders based on proximity detected by the ultrasonic sensor or motion detected by the PIR sensor. When an intruder is detected, the buzzer sounds an alarm, and a message is displayed on the LCD screen.

## Components

- Arduino board (e.g., Uno, Mega)
- Ultrasonic distance sensor (NewPing)
- Passive infrared (PIR) motion sensor
- Buzzer
- 16x2 LCD screen with I2C interface
- Breadboard and jumper wires

## Circuit Diagram

1. **Ultrasonic Sensor**
   - Connect the trig pin of the ultrasonic sensor to digital pin 7 on the Arduino.
   - Connect the echo pin of the ultrasonic sensor to digital pin 8 on the Arduino.
   - Connect VCC and GND of the ultrasonic sensor to 5V and GND on the Arduino, respectively.

2. **PIR Motion Sensor**
   - Connect the output pin of the PIR sensor to digital pin 12 on the Arduino.
   - Connect VCC and GND of the PIR sensor to 5V and GND on the Arduino, respectively.

3. **Buzzer**
   - Connect the positive (+) pin of the buzzer to digital pin 10 on the Arduino.
   - Connect the negative (-) pin of the buzzer to GND on the Arduino.

4. **LCD Screen**
   - Connect the SDA pin of the LCD screen to A4 on the Arduino.
   - Connect the SCL pin of the LCD screen to A5 on the Arduino.
   - Connect VCC and GND of the LCD screen to 5V and GND on the Arduino, respectively.

## Code Explanation

### Libraries

- `NewPing.h`: For interfacing with the ultrasonic distance sensor.
- `LiquidCrystal_I2C.h`: For controlling the LCD screen using I2C communication.

### Variables

- `sonar`: NewPing object for interfacing with the ultrasonic sensor.
- `buzzerPin`: The pin connected to the buzzer.
- `pirPin`: The pin connected to the PIR motion sensor.
- `distThresh`: Threshold distance for triggering the alarm.

### Setup

- The pins connected to the buzzer and PIR sensor are set as OUTPUT and INPUT, respectively.
- The LCD screen is initialized.

### Loop

- The distance is measured by the ultrasonic sensor.
- If the distance is less than the threshold distance or motion is detected by the PIR sensor, an intruder is detected.
- The buzzer sounds an alarm, and a message is displayed on the LCD screen.
- If no intruder is detected, the buzzer is turned off, and a message indicating no intruder is displayed on the LCD screen.

## Usage Instructions

1. Assemble the circuit as per the circuit diagram.
2. Upload the provided code to the Arduino board.
3. Observe the behavior of the system:
   - When an intruder is detected, the buzzer sounds an alarm, and a message is displayed on the LCD screen.
   - When no intruder is detected, the system remains silent, and a message indicating no intruder is displayed on the LCD screen.

## Example Output

- When an intruder is detected, the LCD screen will display "Intruder Detected", and the buzzer will sound an alarm.
- When no intruder is detected, the LCD screen will display "NO Intruder", and the buzzer will remain silent.

This project provides a basic burglar alarm system that can be further expanded with additional features such as SMS alerts or remote monitoring.

---


