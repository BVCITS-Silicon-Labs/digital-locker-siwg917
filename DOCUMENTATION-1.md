# Smart Digital Locker using SiWG917

## 1. Abstract
The Smart Digital Locker is an embedded security system designed to provide controlled and secure access to a locker using PIN-based authentication. The project is developed using the Silicon Labs SiWG917 development platform, Embedded C, and Simplicity Studio. The system accepts user input through physical buttons and verifies the entered PIN against a predefined password. If the entered PIN is correct, access is granted; otherwise access is denied and the remaining attempts can be displayed through UART. The project demonstrates GPIO/button interfacing, authentication, UART communication, and real-time embedded control.

## 2. Introduction
The Smart Digital Locker provides an electronic alternative to a traditional key-based locker. The SiWG917 acts as the main controller and processes button input, PIN verification, access-control logic, and UART status messages.

## 3. Objectives
- Implement PIN-based locker authentication.
- Interface the SiWG917 with onboard buttons.
- Verify the entered PIN.
- Grant or deny access based on authentication.
- Track incorrect attempts.
- Display system status through UART.
- Demonstrate a practical embedded security application.

## 4. Problem Statement
Traditional lockers depend on physical keys that may be lost or misplaced. This project implements a simple electronic locker using PIN authentication to provide controlled access without relying on a mechanical key.

## 5. Proposed System
The user enters a PIN through the available buttons. The controller compares the entered PIN with the stored PIN. A correct PIN results in access being granted, while an incorrect PIN results in access being denied. A configurable maximum-attempt mechanism can be used to lock the system after repeated failures.

## 6. Hardware Requirements
- Silicon Labs SiWG917 development board
- Onboard push buttons
- USB cable
- PC/laptop
- UART connection
- Optional LED, buzzer, servo/solenoid lock

## 7. Software Requirements
- Simplicity Studio
- Silicon Labs WiSeConnect SDK
- Embedded C
- UART terminal
- VS Code (optional)

## 8. System Flow
```text
System Start
     |
     v
Initialize Hardware
     |
     v
Enter PIN
     |
     v
Verify PIN
   /     \
Correct  Incorrect
  |          |
  v          v
Access     Attempts++
Granted       |
  |           v
  v       Check Limit
Unlock        |
          +---+---+
          |       |
        Limit   Not Limit
          |       |
          v       v
       Lockout  Try Again
```

## 9. Button Interface
The onboard buttons provide user input. Button functions are assigned by the application logic and are handled through the Silicon Labs button/GPIO interface.

## 10. PIN Authentication
A predefined PIN is stored by the application. The entered PIN is compared with the stored value. For example:

```text
Correct PIN:
PIN CORRECT
ACCESS GRANTED
LOCKER UNLOCKED
```

For an incorrect PIN:

```text
PIN INCORRECT
ACCESS DENIED
Attempts Remaining: 2
```

## 11. UART Output
Example startup output:

```text
====================================
        SMART DIGITAL LOCKER
====================================

System Started Successfully

Enter PIN:
```

## 12. Software Architecture
```text
Application
   |
   +-- System Initialization
   +-- Button Initialization
   +-- PIN Input
   +-- PIN Verification
   +-- Attempt Management
   +-- Locker Control
   +-- UART Status Output
```

## 13. Program Flow
1. Start the system.
2. Initialize required hardware and UART.
3. Initialize buttons.
4. Display the locker interface.
5. Accept PIN input.
6. Compare the entered PIN with the stored PIN.
7. Grant access if the PIN is correct.
8. Deny access and increment the attempt counter if incorrect.
9. Lock the system when the configured attempt limit is reached.

## 14. Testing
| Test Case | Input | Expected Result |
|---|---|---|
| 1 | Reset board | Startup message displayed |
| 2 | Correct PIN | Access granted |
| 3 | Incorrect PIN | Access denied |
| 4 | Repeated incorrect PIN | Attempt counter increases |
| 5 | Maximum failed attempts | Lockout |
| 6 | Button press | Input detected |
| 7 | UART terminal | Status messages displayed |

## 15. Advantages
- Simple PIN-based authentication.
- No physical key required for normal operation.
- Easy to prototype on the SiWG917 board.
- Real-time button input and status feedback.
- Can be extended with additional security hardware.

## 16. Applications
- Personal lockers
- Smart cabinets
- Office storage
- Laboratory equipment access
- School and college lockers
- Restricted-access equipment

## 17. Limitations
- Basic PIN authentication is not sufficient for high-security applications.
- Physical buttons provide limited input capability.
- A complete locker requires additional locking hardware.
- Production systems require secure credential storage and tamper protection.

## 18. Future Enhancements
- OLED/LCD display
- Keypad PIN entry
- Servo or solenoid lock
- Buzzer and status LEDs
- RFID authentication
- Fingerprint authentication
- Wi-Fi/mobile application control
- Cloud monitoring
- Secure credential storage
- Tamper detection

## 19. Conclusion
The Smart Digital Locker demonstrates how the Silicon Labs SiWG917 platform can be used to build a basic electronic access-control system. The combination of button input, PIN verification, UART communication, and embedded control logic provides a functional prototype that can be extended with stronger authentication, physical locking hardware, and wireless connectivity.

## 20. Project Information
- **Project Name:** Smart Digital Locker
- **Repository:** `smart-digital-locker-si91x`
- **Platform:** Silicon Labs SiWG917
- **Language:** Embedded C
- **IDE:** Simplicity Studio
- **SDK:** WiSeConnect SDK
- **Interfaces:** GPIO / Buttons / UART
- **Project Type:** Embedded Security System
