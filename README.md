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

System Started Successfully

Enter PIN:
****

PIN CORRECT
ACCESS GRANTED
LOCKER UNLOCKED
PIN INCORRECT
ACCESS DENIED
Attempts Remaining: 2
