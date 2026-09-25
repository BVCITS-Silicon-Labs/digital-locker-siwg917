# digital-locker-siwg917
Smart Digital Locker using Silicon Labs SiWG917, featuring secure PIN-based access control, button input, lock/unlock functionality, and real-time status display using embedded C and Simplicity Studio.
# 🔐 Smart Digital Locker using SiWG917

## 📌 Project Overview

The **Smart Digital Locker** is an embedded security project developed using the **Silicon Labs SiWG917** platform. It provides secure locker access using a PIN entered through physical buttons and displays system status through UART.

The project demonstrates embedded GPIO/button handling, PIN authentication, access control, and basic security features using Embedded C and Simplicity Studio.

## 🎯 Objectives

- Provide secure access using a PIN.
- Read user input through onboard buttons.
- Verify the entered PIN.
- Grant or deny locker access.
- Limit incorrect password attempts.
- Display locker status and messages through UART.

## 🛠️ Hardware Requirements

- Silicon Labs SiWG917 development board
- Onboard push buttons
- USB cable
- PC/Laptop
- Optional LED, buzzer, or electronic locking mechanism

## 💻 Software Requirements

- Simplicity Studio
- WiSeConnect SDK
- Embedded C
- UART Terminal
- VS Code (optional)

## 🔑 Features

- PIN-based authentication
- Access granted/denied system
- Incorrect-attempt limitation
- Button-based PIN entry
- UART status messages
- Locker lock/unlock control
- Embedded real-time operation

## 🔄 System Operation

```text
        SYSTEM START
              │
              ▼
     INITIALIZE HARDWARE
              │
              ▼
          ENTER PIN
              │
              ▼
        VERIFY PIN
          /       \
     Correct     Incorrect
        │            │
        ▼            ▼
 ACCESS GRANTED   ATTEMPT++
        │            │
        ▼            ▼
LOCKER UNLOCKED  LIMIT CHECK
                     │
                ┌────┴────┐
                │         │
             Reached   Not Reached
                │         │
                ▼         ▼
             LOCKOUT   TRY AGAIN
====================================
        SMART DIGITAL LOCKER
====================================
Software Requirements
Simplicity Studio
Silicon Labs WiSeConnect SDK
Embedded C
VS Code (optional)
UART terminal software
Hardware Platform
Silicon Labs SiWG917
The SiWG917 development platform is used as the main controller for the project.
The controller is responsible for:
Reading button inputs.
Processing user input.
Verifying the PIN.
Managing authentication attempts.
Controlling the locker state.
Sending status information through UART.
Button Interface
The onboard buttons are used to provide user input.
Example configuration:
BTN0 → User Input
BTN1 → User Input
The exact button function can be assigned according to the application logic.
The project uses the Silicon Labs button driver to initialize and process button events
PIN Authentication
The system uses a predefined PIN for authentication.
Example:
Stored PIN = 1234
The user enters the PIN using the available input buttons.
The system compares the entered PIN with the stored PIN.
Correct PIN
PIN CORRECT
ACCESS GRANTED
LOCKER UNLOCKED
Incorrect PIN
PIN INCORRECT
ACCESS DENIED
Attempts Remaining: 2

System Started Successfully

Enter PIN:
****

PIN CORRECT
ACCESS GRANTED
LOCKER UNLOCKED
PIN INCORRECT
ACCESS DENIED
Attempts Remaining: 2
