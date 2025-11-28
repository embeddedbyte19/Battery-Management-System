# Battery-Management-System
STM32->BATTERY PACK->BMS

## 🔋 STM32 Battery Monitoring & Protection System

**Project Overview**
This project implements a smart battery monitoring and protection system using an STM32 microcontroller. It interfaces with a battery fuel gauge IC via I2C to continuously track critical battery parameters and provide structured diagnostic output over UART.
The system is designed for embedded battery-powered applications such as EV battery packs, energy storage systems, and industrial power modules where accurate monitoring and safety protection are essential.

**Core algorithms, register maps, and detailed implementation logic have been intentionally kept private for intellectual property protection.**

**Key Capabilities**
Real-time battery voltage and current monitoring
State of Charge (SOC) & State of Health (SOH) tracking
Individual cell voltage measurement
Multi-point temperature sensing
Battery protection threshold evaluation
UART-based diagnostic reporting
conversion of raw sensor data to human-readable values

**System Architecture**
Battery Pack
     ↓
Fuel Gauge IC (I2C)
     ↓
STM32 MCU (Data Processing)
     ↓
UART Output → Monitoring PC / Display System

## The firmware periodically reads data from the fuel gauge IC, processes it internally, applies protection logic, and transmits formatted frames for diagnostics and system-level integration.

**Measured Parameters**
Pack Voltage
Charge / Discharge Current
Remaining Capacity
Full Charge Capacity
Battery Cycle Count
Multiple Temperature Sensors
Individual Cell Voltages
Safety & Operational Status Flags

**Output Format**
Two main data frames are transmitted:
P1 Frame – Operational Status
Contains real-time battery runtime data including capacity, temperature, voltage, and health indicators.
P2 Frame – Protection Parameters
Contains protection and safety-related values such as thresholds and delay timers (conceptually exposed, internal calculations secured).

**Source Code Security**
For security and commercial reasons:
The core source code is private
Specific register access methods
Data flash interactions
Protection algorithms
Scaling logic
are not disclosed in this public repository.

**Hardware Platform**
STM32 Microcontroller
I2C-based Fuel Gauge IC
UART communication interface

Battery Pack (Multi-cell configuration)
