# Smart Pill Dispenser

A user-friendly device designed to help individuals manage their medication schedules. The dispenser uses Bluetooth connectivity to interact with an Android app, allowing users to set medication timings and receive reminders.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Hardware Components](#hardware-components)
4. [Software Components](#software-components)
5. [System Overview](#system-overview)
6. [Setup Instructions](#setup-instructions)
7. [Usage](#usage)
8. [Code Explanation](#code-explanation)
9. [Screenshots](#screenshots)
10. [Future Improvements](#future-improvements)

---

## Introduction

Managing medications can be challenging for individuals with complex schedules or multiple prescriptions. This **Smart Pill Dispenser** simplifies the process by automatically dispensing pills at pre-set timings and notifying users through a connected Android app.

---

## Features

* **Automatic Dispensing**: Dispenses pills at specific times of the day (morning, afternoon, and night).
* **Bluetooth Integration**: Allows users to set schedules via an Android app.
* **Visual and Audio Alerts**: LCD display shows reminders, and a buzzer provides audio notifications.
* **Compact Design**: Built with an Arduino Nano for portability.

---

## Hardware Components

| Component                  | Purpose                                     |
| -------------------------- | ------------------------------------------- |
| **Arduino Nano**           | Main microcontroller.                       |
| **HC-05 Bluetooth Module** | Enables communication with the Android app. |
| **Servo Motor (180°)**     | Controls the dispensing mechanism.          |
| **16x2 I2C LCD**           | Displays medication timings and alerts.     |
| **Buzzer**                 | Provides audio notifications.               |
| **RTC DS3231**             | Keeps track of real-time schedules.         |
| **Buck Converter**         | Powers the system using a DC adapter.       |

---

## Software Components

| Component          | Description                            |
| ------------------ | -------------------------------------- |
| **Arduino IDE**    | Used for programming the Arduino Nano. |
| **Android Studio** | Used for developing the Android app.   |

---

## System Overview

This system consists of two main parts:

1. **Hardware**: A dispensing unit controlled by an Arduino Nano.
2. **Software**: An Android app to configure and manage schedules.

The device operates as follows:

1. The user sets the schedule (morning, afternoon, night) using the Android app.
2. At the scheduled time, the dispenser:

   * Rotates the servo motor to dispense pills.
   * Plays a buzzer sound for a few seconds.
   * Updates the LCD display to show a reminder.

---

## Setup Instructions

### Hardware Assembly

1. **Connect the Components**:

   * Attach the HC-05 Bluetooth module to the Arduino Nano.
   * Connect the servo motor to the servo pin.
   * Wire the RTC DS3231 and LCD using the I2C interface.
   * Add the buzzer to the designated pin.

2. **Power Supply**:

   * Use a DC adapter with a buck converter to provide stable power to the system.

### Software Setup

1. Install **Arduino IDE**:

   * Install the required libraries: `Servo`, `Wire`, `LiquidCrystal_I2C`, `RTClib`, and `SoftwareSerial`.
   * Upload the provided Arduino code to the Nano.

2. Install the Android App:

   * Build the app in **Android Studio** and install it on your smartphone.
   * Pair the phone with the HC-05 module.

---

## Usage

### Setting Timings

1. Open the Android app and connect to the dispenser via Bluetooth.
2. Set the desired timings for morning, afternoon, and night.
3. Save the schedule.

### Receiving Alerts

* At the scheduled time:

  * The servo motor rotates to dispense pills.
  * A buzzer sounds, and the LCD displays the reminder.

---

## Code Explanation

### Arduino Code Overview

```cpp
#include <Servo.h>
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <RTClib.h>
#include <SoftwareSerial.h>
```
**Key Functions**:

* **`updateDisplay()`**: Updates the LCD with the current time and schedule.
* **`checkReminders()`**: Checks if it's time to dispense medication.
* **`triggerReminder()`**: Activates the servo motor and buzzer.

---

## Screenshots

### 1. Device Setup



### 2. Android App Interface



### 3. LCD Display



---

## Future Improvements
* Add a sensor to detect low pill levels.
* Include multiple compartments for different medications.
* Enable remote monitoring through a cloud-connected app.
---
