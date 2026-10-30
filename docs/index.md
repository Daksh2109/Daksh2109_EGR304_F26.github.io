---
title: Welcome
tags:
- tag1
- tag2
---
<center>
<font size= "6">Daksh Raghav Preetha Datasheet</font><br>
as part of<br>
<font size= "8"> Automatic Pet Food Dispenser </font><br>
for<br>
<font size= "5"> Team 101 </font><br>

**Submission: October, 30, 2026**
</center>

## Introduction

This individual datasheet documents the design and development of the motor-control subsystem for an Automatic Pet Food Dispenser created as part of EGR 304. The purpose of this project is to develop a system capable of dispensing pet food automatically using electronic controls and a motor-driven mechanism.

My individual responsibility focuses on controlling the DC motor responsible for dispensing food, providing the required power to the control circuitry, and establishing an electrical interface with the other subsystem. This datasheet includes the component selection, Bill of Materials (BOM), circuit schematic, and power budget used to support the design.

### Project Summary

* The Automatic Pet Food Dispenser is designed to provide a convenient and reliable way to dispense food for pets without requiring manual operation every time.     The system combines electronic controls, a motor-driven dispensing mechanism, and coordinated communication between subsystems to release food when requested.

* The overall design uses a microcontroller-based control system to coordinate the dispensing process. When a dispensing request is generated, the motor-control     subsystem receives a digital signal and activates the DC motor to operate the food-dispensing mechanism.

* The project aims to create a functional, affordable, and reliable prototype while maintaining a design that can be tested, assembled, and improved throughout      the engineering development process.

* My subsystem contributes to the overall project by providing the electrical motor-control and power-regulation functions needed to operate the dispensing          mechanism. [team report.](https://egr304-2026-f-101.github.io/)


### My Contribution

My responsibility for the Automatic Pet Food Dispenser project is the design and development of the **Motor-Control and Power-Regulation Subsystem**.

The subsystem uses a PIC18F57Q43 Curiosity Nano microcontroller to control a FIT0492-B 12V DC gearmotor through a DRV8874 H-bridge motor driver. The H-bridge allows the microcontroller to control motor operation electronically.

A 12V DC power supply provides power to the motor driver and motor, while an L7805CV linear voltage regulator converts the 12V supply to 5V for the microcontroller and supporting circuitry.

The subsystem also includes a manual pushbutton for local activation, an LED for debugging, and an 8-pin header interface for connecting to the other subsystem.

The interface allows the motor-control subsystem to receive a digital dispensing request and operate the motor for the required dispensing cycle.

My individual design responsibilities include:

- Selecting the motor, H-bridge driver, voltage regulator, and power supply.
- Designing the motor-control and power-regulation schematic using KiCad.
- Establishing the digital interface between the motor-control subsystem and the other subsystem.
- Creating the Bill of Materials and identifying component suppliers.
- Calculating the electrical power requirements and safety margins.
- Preparing the design for prototyping, testing, and eventual PCB implementation.

The following sections document the engineering decisions and calculations supporting my subsystem.

### Component Selection

The [Component Selection](02-Component-Selection/Component-Selection.md) section explains the selection of the motor, H-bridge motor driver, voltage regulator, and power supply based on their electrical specifications and suitability for the dispensing mechanism.

### Bill of Materials (BOM)

The [Bill of Materials](03-BOM/BOM.md) section lists the components required to construct the motor-control subsystem, including quantities, manufacturers, supplier information, and estimated costs.

### Schematic

The [Schematic](04-Schematic/schematic.md) section contains the KiCad electrical schematic for the subsystem, including the microcontroller, motor driver, power regulation, input interface, and supporting components.

### Power Budget

The [Power Budget](05-Power-Budget/Power-Budget.md) section calculates the electrical current and power requirements of the subsystem, evaluates the selected power supply, and includes safety margins for reliable operation.
