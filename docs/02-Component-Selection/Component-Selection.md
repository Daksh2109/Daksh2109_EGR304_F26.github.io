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

**Subsystem: Optical Sensor Signal Conditioning**

The op-amp circuit processes the signal from the optical slot sensor before it reaches the PIC18F57Q43 Curiosity Nano microcontroller. The circuit is designed to operate from the regulated 5V supply provided by the LM7805 voltage regulator.

The selected op-amp must support single-supply operation, provide sufficient input and output voltage range, consume minimal power, and be compatible with the existing KiCad schematic.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: Microchip MCP6004-I/P** <br> **Manufacturer:** Microchip Technology <br> **Supply Voltage:** 1.8V–6.0V <br> **Amplifiers:** 4 <br> **Bandwidth:** 1 MHz <br> **Package:** 14-PDIP <br> **Price:** $0.60 each <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=MCP6004-I%2FP) <br> [Manufacturer Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/45b579ef-60c2-48f7-a296-1ed65109689b" /> | - Compatible with our regulated 5V power supply. <br> - Rail-to-rail input and output operation. <br> - Four op-amps allow multiple signal-conditioning stages. <br> - Low power consumption. <br> - Through-hole package simplifies soldering and prototyping. <br> - Already used in our previous KiCad schematic. | - Lower bandwidth than some alternative op-amps. <br> - Requires external resistors and capacitors for filtering. <br> - Not designed to replace a dedicated comparator for high-speed switching. |
| **Option 2: Texas Instruments LM324N** <br> **Manufacturer:** Texas Instruments <br> **Supply Voltage:** 3V–30V <br> **Amplifiers:** 4 <br> **Bandwidth:** Approximately 1.2 MHz <br> **Package:** 14-PDIP <br> **Price:** Check current DigiKey unit price <br> [DigiKey Product](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627) <br> [Manufacturer Datasheet](https://www.ti.com/lit/ds/symlink/lm224.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792052005401) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/e8016907-cbc0-4492-ac35-a2977d17f060" /> | - Supports 5V single-supply operation. <br> - Four op-amps in one IC. <br> - Through-hole package is easy to assemble. <br> - Widely used for basic analog signal conditioning. <br> - Can operate over a broad supply-voltage range. | - Output cannot swing fully to the positive supply rail. <br> - Input common-mode range does not extend to the positive supply rail. <br> - Less suitable than a rail-to-rail amplifier for signals near 5V. <br> - Would require changing the op-amp selected in our existing schematic. |
| **Option 3: Texas Instruments TLV9004IPWR** <br> **Manufacturer:** Texas Instruments <br> **Supply Voltage:** 1.8V–5.5V <br> **Amplifiers:** 4 <br> **Bandwidth:** 1 MHz <br> **Package:** 14-TSSOP <br> **Price:** Check current DigiKey unit price <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=TLV9004IPWR) <br> [Manufacturer Datasheet](https://www.ti.com/lit/ds/symlink/tlv9004.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792113554109&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Ftlv9004) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/81eaba8c-a17c-4ddb-9dfd-cbe8e715be81" /> | - Compatible with regulated 5V operation. <br> - Rail-to-rail input and output. <br> - Four amplifiers provide flexibility for filtering. <br> - Low power consumption. <br> - Compact package saves PCB space. | - Surface-mount package is harder to solder manually. <br> - Smaller pins require more careful PCB layout. <br> - Would require updating our existing KiCad schematic and footprint. <br> - Offers limited practical benefit over the MCP6004 for this application. |

### Final Selection

**Selected Component: Option 1 – Microchip MCP6004-I/P**

**Manufacturer:** Microchip Technology

**Part Number:** MCP6004-I/P

**Operating Voltage:** 1.8V–6.0V

**Planned Supply Voltage:** 5V DC

**Number of Amplifiers:** 4

**Package:** 14-PDIP (Through-Hole)

**Supplier:** DigiKey

**Rationale:**

The Microchip MCP6004-I/P is selected for the Automatic Pet Food Dispenser because it provides the necessary signal-conditioning capabilities while remaining compatible with our existing electrical design.

The MCP6004 supports single-supply operation from 1.8V to 6.0V, allowing it to operate from the regulated 5V output of our LM7805 voltage regulator. Its rail-to-rail input and output capability makes it suitable for processing sensor signals over a wide portion of the available supply-voltage range.

The IC contains four independent operational amplifiers, allowing multiple signal-conditioning stages to be implemented without requiring additional amplifier ICs. Its 1 MHz bandwidth is sufficient for the relatively slow sensing signals expected from the pet food dispensing mechanism.

Another major advantage is that the MCP6004 is already included in our previous KiCad schematic. Selecting this component allows us to reuse our existing circuit design and reduces the changes needed for the upcoming schematic and PCB assignments.

Compared with the LM324N, the MCP6004 provides better rail-to-rail signal handling. Compared with the TLV9004, its through-hole package is easier to solder and integrate during prototyping.

Therefore, the **MCP6004-I/P is the preferred op-amp** because it offers reliable 5V operation, low power consumption, sufficient performance, and the greatest compatibility with our existing design.

The sensor-conditioning circuit will be modified as necessary to accommodate the selected optical slot sensor. The output voltage will also be checked against the PIC18F57Q43 Curiosity Nano's ADC input limits before the final schematic is completed.

---


## 3. MOSFET / Power Switching

**Subsystem: Motor Power Switching and Control**

The MOSFET is responsible for electronically switching power to an electrical load within the Automatic Pet Food Dispenser. It must be compatible with the selected power supply, motor control circuitry, and PIC18F57Q43 Curiosity Nano microcontroller.

The MOSFET selection is based on drain-source voltage, current capacity, gate-drive requirements, on-resistance, cost, ease of PCB integration, and compatibility with our existing circuit design.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: Alpha & Omega Semiconductor AOTF2618L** <br> **Manufacturer:** Alpha & Omega Semiconductor <br> **Drain-Source Voltage:** 60V <br> **Drain Current:** 7A (Ta), 22A (Tc) <br> **Package:** TO-220F <br> **Price:** Check current DigiKey unit price <br> [DigiKey Product](https://www.digikey.com/en/products/detail/alpha-omega-semiconductor-inc/AOTF2618L/785-1442-5-ND/3603382) <br> [Manufacturer Datasheet](https://www.aosmd.com/res/datasheets/AOTF2618L.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/b62ad8f1-6c7f-46a7-b0d7-7bf65eb742b4" /> | - 60V drain-source rating provides substantial headroom for a low-voltage switching circuit. <br> - Rated for 7A at ambient temperature and 22A at the specified case temperature. <br> - Through-hole package simplifies PCB assembly and soldering. <br> - Insulated TO-220F package is useful for mounting. <br> - Already used in our previous KiCad assignment, reducing redesign work. | - Larger package occupies more PCB space. <br> - Full current rating depends on thermal conditions. <br> - Direct operation from 3.3V microcontroller GPIO is not guaranteed. <br> - Gate-drive requirements must be checked before schematic implementation. |
| **Option 2: Infineon IRLZ44NPBF** <br> **Manufacturer:** Infineon Technologies <br> **Drain-Source Voltage:** 55V <br> **Drain Current:** 47A (case-temperature rated) <br> **Package:** TO-220 <br> **Price:** Approximately $1.80 each; verify current price <br> [DigiKey Product](https://www.digikey.com/en/products/detail/infineon-technologies/IRLZ44NPBF/811808) <br> [Manufacturer Datasheet](https://www.infineon.com/assets/row/public/documents/24/49/infineon-irlz44n-datasheet-en.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/19316dfc-1c78-4f6a-8233-8d33da67ba4a" /> | - Logic-level N-channel MOSFET. <br> - Low on-resistance helps reduce power loss. <br> - High current rating provides electrical headroom. <br> - Through-hole package is easy to solder. <br> - Suitable for many low-voltage power-switching applications. | - Higher current capacity than our application may require. <br> - TO-220 package occupies significant PCB space. <br> - Gate-drive performance must still be checked at the actual control voltage. <br> - Would require changing the MOSFET used in our existing schematic. |
| **Option 3: STMicroelectronics STP55NF06L** <br> **Manufacturer:** STMicroelectronics <br> **Drain-Source Voltage:** 60V <br> **Drain Current:** 55A (case-temperature rated) <br> **Package:** TO-220 <br> **Price:** Approximately $2.88 each; verify current price <br> [DigiKey Product](https://www.digikey.com/en/products/detail/stmicroelectronics/STP55NF06L/1039551) <br> [Manufacturer Datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/49/c5/a8/71/93/60/4f/86/CD00002690.pdf/files/CD00002690.pdf/jcr:content/translations/en.CD00002690.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/90598517-4ed2-4955-98b8-0cb5dc47c106" /> | - 60V drain-source rating is suitable for low-voltage motor applications. <br> - High current capability. <br> - Designed for low-voltage gate-drive applications. <br> - Low on-resistance helps reduce heat generation. <br> - Through-hole package simplifies prototyping. | - Higher estimated price than the other alternatives. <br> - Large package requires more PCB space. <br> - High current rating is unnecessary for many small motors. <br> - Would require replacing our existing MOSFET selection. |

### Final Selection

**Selected Component: Option 1 – Alpha & Omega Semiconductor AOTF2618L**

**Manufacturer:** Alpha & Omega Semiconductor Inc.

**Manufacturer Part Number:** AOTF2618L

**DigiKey Part Number:** 785-1442-5-ND

**MOSFET Type:** N-Channel

**Drain-Source Voltage:** 60V

**Continuous Drain Current:** 7A (Ta), 22A (Tc), under specified conditions

**Package:** TO-220F (Through-Hole)

**Supplier:** DigiKey


### Rationale

The Alpha & Omega Semiconductor AOTF2618L is selected as the preferred MOSFET for our Automatic Pet Food Dispenser because it offers appropriate voltage and current ratings for consideration in the subsystem's power-switching circuitry.

The MOSFET has a maximum drain-source voltage of 60V and continuous drain-current ratings of 7A at ambient temperature and 22A at the specified case temperature. These ratings provide sufficient potential headroom for the low-voltage loads being considered, subject to verification of the actual current and thermal requirements.

Its TO-220F through-hole package makes it easier to solder and incorporate into our PCB compared with smaller surface-mount components. The insulated package can also simplify certain mounting arrangements.

Another major advantage is that the AOTF2618L was already used in our previous KiCad assignment. Reusing this component will reduce schematic modifications and allow us to build upon our existing design.

Compared with the IRLZ44NPBF and STP55NF06L, the AOTF2618L provides the greatest compatibility with our existing KiCad work. Although the alternatives offer higher rated current capacities, these ratings may not provide a meaningful advantage for our relatively small dispensing mechanism.

Therefore, the **AOTF2618L is our preferred MOSFET**, pending verification of its gate-drive voltage, switching losses, and compatibility with the selected motor and driver.

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
