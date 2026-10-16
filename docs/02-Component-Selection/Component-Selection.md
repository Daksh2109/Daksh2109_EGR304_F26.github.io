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

The optical slot sensor will detect movement of the dispensing mechanism in our Automatic Pet Food Dispenser. A rotating slotted wheel or mechanical flag will interrupt the infrared beam, allowing the system to track movement. The sensor output will be sent through the op-amp/filter circuit before reaching the PIC18F57Q43 Curiosity Nano.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: Vishay TCST1103** <br> **Price:** $1.48 each <br> **Slot Width:** 3.1 mm <br> **Output:** Phototransistor <br> [DigiKey Product](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST1103/2354847) <br> [Datasheet](https://www.vishay.com/en/product/83764/) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/034b6955-2ddf-4b54-9eee-952b0faeca31" /> | - Compatible with a 5V sensor circuit when properly biased. <br> - 3.1 mm slot provides room for a small encoder wheel or mechanical flag. <br> - Through-hole package is easier to solder during prototyping. <br> - Daylight-blocking filter helps reduce interference from ambient light. <br> - Lowest price among these three options. | - Requires an external resistor for the infrared emitter. <br> - Phototransistor output requires a pull-up or signal-conditioning circuit. <br> - Sensor must be aligned with the moving mechanism. |
| **Option 2: Vishay TCST2103** <br> **Price:** $1.84 each <br> **Slot Width:** 3.1 mm <br> **Output:** Phototransistor <br> [DigiKey Product](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST2103/2354849) <br> [Datasheet](https://www.vishay.com/docs/81147/tcst2103.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/eff78c40-5eaf-49e6-8b9d-b795b3b5b661" /> | - Supports operation in a 5V sensing circuit with appropriate resistors. <br> - Through-hole mounting is suitable for student PCB assembly. <br> - 3.1 mm slot supports mechanical interruption sensing. <br> - Phototransistor output is suitable for detecting movement and rotation. | - Larger physical package requires more mounting space. <br> - Higher price than the TCST1103. <br> - Requires additional circuitry to obtain a clean microcontroller input. |
| **Option 3: Aratas / Omron EE-SX1103** <br> **Price:** $1.75 each <br> **Slot Width:** 2 mm <br> **Output:** Phototransistor <br> [DigiKey Product](https://www.digikey.com/en/products/detail/aratas-formerly-omron-components/EE-SX1103/355306) <br> [Datasheet and Specifications](https://omronfs.omron.com/en_US/ecb/products/pdf/en-ee_sx1103.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/e6c08b4d-dd12-4694-a49f-ce9b461fd467" /> | - Compact design can save PCB space. <br> - Fast response time of approximately 10 microseconds. <br> - Through-hole mounting simplifies soldering. <br> - Suitable for precise detection using a narrow mechanical flag. | - Narrow 2 mm slot requires more accurate mechanical alignment. <br> - Less clearance for a thicker rotating disk. <br> - Requires external emitter and output circuitry. |

### Final Selection

**Selected Component: Option 1 – Vishay TCST1103**

**Manufacturer:** Vishay Semiconductor

**Part Number:** TCST1103

**Estimated Unit Cost:** $1.48

**Supplier:** DigiKey

**Rationale:**

The Vishay TCST1103 is the preferred optical slot sensor for our Automatic Pet Food Dispenser because it provides a good balance of performance, mechanical compatibility, ease of implementation, and cost. Its 3.1 mm sensing gap provides sufficient clearance for a thin slotted wheel or mechanical flag, while its through-hole package makes it easier to install and solder on our PCB.

The sensor uses an infrared emitter and phototransistor, making it suitable for detecting interruptions caused by movement of the dispensing mechanism. Its daylight-blocking filter also helps reduce interference from surrounding light.

Although the sensor requires external resistors and signal conditioning, our subsystem already includes an op-amp/filter circuit. This allows us to process the sensor output before sending it to the PIC18F57Q43 microcontroller.

Compared with the other options, the TCST1103 offers similar sensing functionality at a lower unit price. Therefore, it is the preferred choice, provided the final mechanical design fits within its sensing gap.

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
