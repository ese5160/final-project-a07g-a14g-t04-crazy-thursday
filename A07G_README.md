# a07g-exploring-the-CLI

* Team Number: 4
* Team Name: Crazy Thursday
* Team Members: Zheyu Li, Zhuozi Xie
* GitHub Repository URL: https://github.com/ese5160/final-project-a07g-a14g-t04-crazy-thursday.git
* Description of test hardware: (development boards, sensors, actuators, laptop + OS, etc)

## 1. Software Architecture

### 1.1 HRS

#### 1.1.1 Overview

The device includes an infrared sensor and a limit switch that cross-verifies that a cell phone has been placed in it, which activates a locking mechanism actuated by an electromagnet.The user can set the timer through mobile phone using WiFi connection. An emergency release button on the bottom of the device allows unlocking in urgent cases. For user interaction, a LCD screen on the surface should be used to display remaining time and a buzzer which can play music is used for indicating the time up. The device should balance the accesibility and energy consumption.

#### 1.1.2 Definitions, Abbreviations

IR sensor: infrared sensor

#### 1.1.3 Functionality

HRS 01 – Project shall be based on SAM W25 microcontroller (WiFi supported).

HRS 02 – An IR sensor(via I2C) shall be used for phone detection. The sensor shall be able to accurately detect distances in the range of 1-10cm.

HRS 03 – An 5V DC electromagnet with at least 2.5kg holding force shall be used to support the lock mechanism.

HRS 04 – An LCD display shall be used for user interface. The display shall communicate with the microcontroller via SPI.

HRS 05 – A passive buzzer that releases sounds of different frequencies shall be used.

HRS 06 - A Li-Ion battery (3.7V nominal voltage) Shall be used as the power supply of the whole system.

HRS 07 - A limit switch shall be used with IR sensor to cross validate that the cell phone is placed in the box

HRS 08 - A 6-DOF IMU supporting I2C connection shall be used to detect whether the box has been moved or not，>10Hz sample rate is enough.

### 1.2 SRS

#### 1.2.1 Overview

The Pandora's Box is a box that follow the scheduled study plan on the app, or set manually by user through cell phone, to lock phone and open after time out. Using a timed lock mechanism, it securely stores your phone, encouraging focus and productivity.

An electromagnet work as the locker of the box, prevent violent opening. A Infrared sensor with a limit switch check is the phone really in the box instead a empty box. There is also a LCD screen on the top of the box, which shows the time remaning for current study session.  An emergency button locate at the buttom of the box used to release lock in urgent conditions. A buzzer is in the box to help inform the user for study begin and end. There is an app, communicate through WIFI, that your can build you study plan and goals or use to set study time manually.

#### 1.2.2 Users

This project is for students seeking to build better learning habits, which could force them to focus on study without any disturb from phone.

#### 1.2.3 Functionality

SRS 01 – The IR sensor and limit switch shall continuously detect the presence of objects inside the box when the time is set and before the box is closed(in Prepare Stage).

SRS 02 - The Device shall receive commands from mobile phones using WiFi.

SRS 03 - The box shall support setting study time using mobile phone (based on WiFi connection).

SRS 04 - The electromagnet shall be controlled according to the status of IR sensor, limit switch and emergency release button.

SRS 05 - The buzzer should play sound to inform the user to study when reaching the scheduled study time.

SRS 06 - The buzzer should play sound to inform the user to rest when the setting time period end.

SRS 07 - IMU's reading should determine the LCD on/off based on the box gesture during lock state.

### 1.3 Block Diagram (task division)

### 1.4 State machine diagrams

![State machine](State_machine.png)

## 2. Understanding the Starter Code

### 2.1 What does “InitializeSerialConsole()” do? In said function, what is “cbufRx” and “cbufTx”? What type of data structure is it?

### 2.2 How are “cbufRx” and “cbufTx” initialized? Where is the library that defines them (please list the *C file they come from).

### 2.3 Where are the character arrays where the RX and TX characters are being stored at the end? Please mention their name and size. Tip: Please note cBufRx and cBufTx are structures.

### 2.4 Where are the interrupts for UART character received and UART character sent defined?

### 2.5 What are the callback functions that are called when:

a. A character is received? (RX)
b. A character has been sent? (TX)

### 2.6 Explain what is being done on each of these two callbacks and how they relate to the cbufRx and cbufTx buffers.

### 2.7 Draw a diagram that explains the program flow for UART receive – starting with the user typing a character and ending with how that characters ends up in the circular buffer “cbufRx”. Please make reference to specific functions in the starter code.

### 2.8 Draw a diagram that explains the program flow for the UART transmission – starting from a string added by the program to the circular buffer “cbufTx” and ending on characters being shown on the screen of a PC (On Teraterm, for example). Please make reference to specific functions in the starter code.

### 2.9 What is done on the function “startStasks()” in main.c? How many threads are started?
