---
title: Component Selection Example
---

## Examples



# Component Selection

## Overview

The purpose of this component selection assignment is to research and compare different electrical and electromechanical components for my subsystem of Team 101's Automatic Pet Food Dispenser.

My subsystem includes an optical slot sensor, op-amp filter circuit, MOSFET, motor, H-bridge motor driver, and power regulation circuitry. Each major component will be evaluated based on electrical specifications, compatibility, cost, ease of implementation, and suitability for the overall design.

The system uses the PIC18F57Q43 Curiosity Nano microcontroller. The control circuitry will use regulated 5V power where appropriate, while the motor will use a separate power supply based on its voltage and current requirements.

---

## 1. Optical Slot Sensor

**Subsystem: Position and Rotation Detection**

The optical slot sensor will be used to detect movement or rotation within the dispensing mechanism. Its output will be processed by the signal conditioning circuit before being sent to the microcontroller.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Manufacturer: [Name] <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] <br> - [Advantage 3] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Manufacturer: [Name] <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Manufacturer: [Name] <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Explain why this component is the best choice based on operating voltage, detection accuracy, mechanical compatibility, price, and ease of integration.]

---

## 2. Op-Amp / Signal Conditioning Circuit

**Subsystem: Sensor Signal Processing**

The op-amp circuit will condition the optical sensor output before it reaches the PIC18F57Q43 microcontroller.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Compare operating voltage, input/output voltage range, accuracy, current consumption, and compatibility with the optical sensor.]

---

## 3. MOSFET

**Subsystem: Motor Power Switching**

The MOSFET will be used for controlling power to the motor or other required load within the subsystem.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Explain your selection using gate-drive compatibility, drain-source voltage, continuous current rating, on-resistance, and thermal performance.]

---

## 4. DC Motor

**Subsystem: Dispensing Mechanism**

The motor will provide the mechanical motion required to move the dispensing mechanism and release pet food.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Compare motor torque, operating voltage, speed, current consumption, physical size, and ability to operate the food dispensing mechanism.]

---

## 5. H-Bridge Motor Driver

**Subsystem: Motor Control**

The H-bridge motor driver will allow the microcontroller to control the motor's direction and operation.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Explain the selection based on motor voltage, motor stall current, control logic compatibility, efficiency, and available protection features.]

---

## 6. Linear Voltage Regulator

**Subsystem: Power Regulation**

A linear voltage regulator will provide a stable 5V supply for compatible components within the subsystem. The motor will use a separate power source where required.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Compare input voltage range, output current capability, dropout voltage, heat dissipation, package, and cost.]

---

## 7. External Power Supply

**Subsystem: Power Distribution**

The power supply must provide sufficient voltage and current for the electrical components and dispensing motor.

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 1](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 2: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 2](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |
| **Option 3: [Part Number]** <br> Price: $[Price] <br> [Product Link](URL) <br> ![Option 3](IMAGE_URL) | - [Advantage 1] <br> - [Advantage 2] | - [Disadvantage 1] <br> - [Disadvantage 2] |

**Final Selection:** [Selected Part Number]

**Rationale:** [Explain why the selected power supply meets voltage and current requirements with sufficient safety margin.]

---

## Conclusion

The final component selections will be based on electrical compatibility, performance, cost, availability, ease of PCB integration, and the mechanical requirements of the Automatic Pet Food Dispenser.

All selected commercial components will have manufacturer datasheets and verified product links to support future schematic design, PCB layout, and power budget calculations.


### Style 1

> This is the example found in the assignment, uses more html

*Table 1: Example component selection*

**External Clock Module**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> XC1259TR-ND surface mount crystal<br>$1/each<br>[link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)                 | \* Inexpensive[^1]<br>\* Compatible with PSoC<br>\* Meets surface mount constraint of project                                               | \* Requires external components and support circuitry for interface<br>\* Needs special PCB layout. |
| ![](image3.png)<br>\* Option 2. <br>\* CTX936TR-ND surface mount oscillator <br>\* $1/each <br>\* [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940) | \* Outputs a square wave <br>\* Stable over operating temperature <br> \* Direct interface with PSoC (no external circuitry required) range | * More expensive <br>\* Slow shipping speed                                                         |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.

### Style 2

> Also acceptable, more markdown friendly

**External Clock Module**

1. XC1259TR-ND surface mount crystal

    ![](image1.png)

    * $1/each
    * [link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Compatible with PSoC                      | Needs special PCB layout.                                        |
    | Meets surface mount constraint of project |

1. CTX936TR-ND surface mount oscillator

    ![](image3.png)

    * $1/each
    * [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940)

    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Outputs a square wave                                             | More expensive      |
    | Stable over operating temperature                                 | Slow shipping speed |
    | Direct interface with PSoC (no external circuitry required) range |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.
