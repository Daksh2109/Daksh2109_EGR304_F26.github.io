---
title: Component Selection 
---



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
| **Option 2: Texas Instruments LM324N** <br> **Manufacturer:** Texas Instruments <br> **Supply Voltage:** 3V–30V <br> **Amplifiers:** 4 <br> **Bandwidth:** Approximately 1.2 MHz <br> **Package:** 14-PDIP <br> **Price:** $0.58 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627) <br> [Manufacturer Datasheet](https://www.ti.com/lit/ds/symlink/lm224.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792052005401) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/e8016907-cbc0-4492-ac35-a2977d17f060" /> | - Supports 5V single-supply operation. <br> - Four op-amps in one IC. <br> - Through-hole package is easy to assemble. <br> - Widely used for basic analog signal conditioning. <br> - Can operate over a broad supply-voltage range. | - Output cannot swing fully to the positive supply rail. <br> - Input common-mode range does not extend to the positive supply rail. <br> - Less suitable than a rail-to-rail amplifier for signals near 5V. <br> - Would require changing the op-amp selected in our existing schematic. |
| **Option 3: Texas Instruments TLV9004IPWR** <br> **Manufacturer:** Texas Instruments <br> **Supply Voltage:** 1.8V–5.5V <br> **Amplifiers:** 4 <br> **Bandwidth:** 1 MHz <br> **Package:** 14-TSSOP <br> **Price:** $0.91 each <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=TLV9004IPWR) <br> [Manufacturer Datasheet](https://www.ti.com/lit/ds/symlink/tlv9004.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792113554109&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Ftlv9004) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/81eaba8c-a17c-4ddb-9dfd-cbe8e715be81" /> | - Compatible with regulated 5V operation. <br> - Rail-to-rail input and output. <br> - Four amplifiers provide flexibility for filtering. <br> - Low power consumption. <br> - Compact package saves PCB space. | - Surface-mount package is harder to solder manually. <br> - Smaller pins require more careful PCB layout. <br> - Would require updating our existing KiCad schematic and footprint. <br> - Offers limited practical benefit over the MCP6004 for this application. |

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
| **Option 1: Alpha & Omega Semiconductor AOTF2618L** <br> **Manufacturer:** Alpha & Omega Semiconductor <br> **Drain-Source Voltage:** 60V <br> **Drain Current:** 7A (Ta), 22A (Tc) <br> **Package:** TO-220F <br> **Price:** $1.90 per unit <br> [DigiKey Product](https://www.digikey.com/en/products/detail/alpha-omega-semiconductor-inc/AOTF2618L/785-1442-5-ND/3603382) <br> [Manufacturer Datasheet](https://www.aosmd.com/res/datasheets/AOTF2618L.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/b62ad8f1-6c7f-46a7-b0d7-7bf65eb742b4" /> | - 60V drain-source rating provides substantial headroom for a low-voltage switching circuit. <br> - Rated for 7A at ambient temperature and 22A at the specified case temperature. <br> - Through-hole package simplifies PCB assembly and soldering. <br> - Insulated TO-220F package is useful for mounting. <br> - Already used in our previous KiCad assignment, reducing redesign work. | - Larger package occupies more PCB space. <br> - Full current rating depends on thermal conditions. <br> - Direct operation from 3.3V microcontroller GPIO is not guaranteed. <br> - Gate-drive requirements must be checked before schematic implementation. |
| **Option 2: Infineon IRLZ44NPBF** <br> **Manufacturer:** Infineon Technologies <br> **Drain-Source Voltage:** 55V <br> **Drain Current:** 47A (case-temperature rated) <br> **Package:** TO-220 <br> **Price:** Approximately $1.80 each <br> [DigiKey Product](https://www.digikey.com/en/products/detail/infineon-technologies/IRLZ44NPBF/811808) <br> [Manufacturer Datasheet](https://www.infineon.com/assets/row/public/documents/24/49/infineon-irlz44n-datasheet-en.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/19316dfc-1c78-4f6a-8233-8d33da67ba4a" /> | - Logic-level N-channel MOSFET. <br> - Low on-resistance helps reduce power loss. <br> - High current rating provides electrical headroom. <br> - Through-hole package is easy to solder. <br> - Suitable for many low-voltage power-switching applications. | - Higher current capacity than our application may require. <br> - TO-220 package occupies significant PCB space. <br> - Gate-drive performance must still be checked at the actual control voltage. <br> - Would require changing the MOSFET used in our existing schematic. |
| **Option 3: STMicroelectronics STP55NF06L** <br> **Manufacturer:** STMicroelectronics <br> **Drain-Source Voltage:** 60V <br> **Drain Current:** 55A (case-temperature rated) <br> **Package:** TO-220 <br> **Price:** Approximately $3.05 each <br> [DigiKey Product](https://www.digikey.com/en/products/detail/stmicroelectronics/STP55NF06L/1039551) <br> [Manufacturer Datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/49/c5/a8/71/93/60/4f/86/CD00002690.pdf/files/CD00002690.pdf/jcr:content/translations/en.CD00002690.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/90598517-4ed2-4955-98b8-0cb5dc47c106" /> | - 60V drain-source rating is suitable for low-voltage motor applications. <br> - High current capability. <br> - Designed for low-voltage gate-drive applications. <br> - Low on-resistance helps reduce heat generation. <br> - Through-hole package simplifies prototyping. | - Higher estimated price than the other alternatives. <br> - Large package requires more PCB space. <br> - High current rating is unnecessary for many small motors. <br> - Would require replacing our existing MOSFET selection. |

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

**Subsystem: Food Dispensing Mechanism**

The DC motor provides the mechanical motion required to operate the Automatic Pet Food Dispenser. The motor will rotate the dispensing mechanism to release food in controlled amounts.

A 12V geared DC motor is preferred because it provides useful torque, a manageable rotational speed, and a larger mechanical structure suitable for moving the dispensing mechanism.

The motor selection is based on operating voltage, speed, torque, physical size, current requirements, cost, and compatibility with the motor driver.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: DFRobot FIT0492-B 12V Metal Gearmotor** <br> **Manufacturer:** DFRobot <br> **Part Number:** FIT0492-B <br> **Operating Voltage:** 12V <br> **No-Load Speed:** 100 RPM <br> **Rated Torque:** 686.5 mN·m (approximately 7 kg·cm) <br> **Gear Ratio:** 100:1 <br> **Motor Diameter:** 37 mm <br> **Output Shaft:** 6 mm <br> **Price:** $11.90 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-B/7087168) <br> [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/7153/FIT0492-B.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/358590ee-fbfc-4922-9748-174fbea285e8" /> | - 12V operation is compatible with our proposed power system. <br> - 100 RPM provides a reasonable speed for controlled dispensing. <br> - Metal gearbox provides increased output torque. <br> - Rated torque of approximately 7 kg·cm is suitable for consideration in a mechanical dispensing system. <br> - Larger 37 mm motor provides a more substantial mechanical design. <br> - 6 mm shaft allows connection to the dispensing mechanism. <br> - Lower price than many comparable geared motors. <br> - Available through DigiKey. | - Requires a separate motor driver capable of handling the motor current. <br> - Stall current must be verified before selecting the H-bridge. <br> - Larger motor requires more mounting space. <br> - Requires a suitable mounting bracket and shaft coupler. |
| **Option 2: DFRobot FIT0492-A 12V Metal Gearmotor** <br> **Manufacturer:** DFRobot <br> **Part Number:** FIT0492-A <br> **Operating Voltage:** 12V <br> **No-Load Speed:** 50 RPM <br> **Rated Torque:** 883 mN·m (approximately 9 kg·cm) <br> **Motor Diameter:** 37 mm <br> **Price:** $11.90 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165) <br> [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/2235/FIT0492-A_Web.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/bac56521-578c-44f5-b0ce-acb63e1e7f1e" /> | - Higher rated torque than the FIT0492-B. <br> - Slower rotation may improve dispensing control. <br> - Metal gearbox is suitable for mechanical actuation. <br> - Compatible with a 12V supply. <br> - Same listed price as the FIT0492-B. <br> - Available through DigiKey. | - Slower speed may increase dispensing time. <br> - Requires additional mechanical mounting space. <br> - Stall current must be checked before selecting the motor driver. <br> - Higher torque may not be necessary for our dispensing mechanism. |
| **Option 3: Seeed Studio 114090046 DC Gearmotor** <br> **Manufacturer:** Seeed Technology <br> **Part Number:** 114090046 <br> **Operating Voltage:** 6V–12V <br> **Rated Torque:** 137.3 mN·m (approximately 1.4 kg·cm) <br> **Price:** $5.20 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/114090046/10385097) <br> [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/694/114090046_Web.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/4421b90a-1931-4197-93d6-db294454ef89" /> | - Lowest price among the three options. <br> - Supports operation within a 6V–12V range. <br> - Suitable for lightweight mechanical movement. <br> - Can operate from the proposed 12V motor supply if permitted by the manufacturer's specifications. | - Much lower rated torque than the DFRobot motors. <br> - May not provide sufficient force to move the food dispensing mechanism. <br> - Speed is not specified in the referenced DigiKey listing. <br> - Less suitable for a larger dispensing mechanism. |

### Final Selection

**Selected Component: Option 1 – DFRobot FIT0492-B 12V Metal Gearmotor**

**Manufacturer:** DFRobot

**Manufacturer Part Number:** FIT0492-B

**DigiKey Part Number:** 1738-1271-ND

**Motor Type:** Brushed DC Gearmotor

**Operating Voltage:** 12V DC

**No-Load Speed:** 100 RPM

**Rated Torque:** 686.5 mN·m (approximately 7 kg·cm)

**Gear Ratio:** 100:1

**Motor Diameter:** 37 mm

**Output Shaft:** 6 mm

**Unit Price:** $11.90

**Supplier:** DigiKey

### Rationale

The DFRobot FIT0492-B 12V Metal Gearmotor is selected for our Automatic Pet Food Dispenser because it provides a good balance of rotational speed, output torque, mechanical size, and cost.

The motor operates at 12V and has a no-load speed of approximately 100 RPM. This speed makes it a reasonable candidate for rotating the dispensing mechanism at a controlled rate.

The motor also provides a rated torque of approximately 7 kg·cm, making it a promising option for moving a mechanical dispensing system. The metal gearbox increases the available output torque while reducing rotational speed.

Compared with the DFRobot FIT0492-A, the selected motor provides a higher rotational speed while maintaining substantial rated torque. This may allow food to be dispensed more quickly without requiring an excessively fast motor.

Compared with the Seeed Studio 114090046, the FIT0492-B provides significantly greater rated torque, making it a more suitable candidate for a larger dispensing mechanism.

Another advantage is the motor's price of approximately $11.90, which is lower than many comparable geared DC motors. It is also listed through DigiKey, allowing us to maintain consistency with our other component selections.

The 37 mm motor diameter and 6 mm output shaft make it suitable for integration into the mechanical dispensing assembly.

Therefore, the **DFRobot FIT0492-B is our preferred DC motor** because it provides a useful combination of speed, torque, mechanical strength, and affordability.

---


## 5. H-Bridge Motor Driver

**Subsystem: DC Motor Direction and Speed Control**

The H-bridge motor driver will control the direction and speed of the DC motor used in our Automatic Pet Food Dispenser. The driver will receive control signals from the PIC18F57Q43 Curiosity Nano and deliver power to the motor.

Our selected motor is the DFRobot FIT0492-B 12V metal gearmotor. Therefore, the H-bridge must support a 12V motor supply, provide sufficient output current, and operate with the microcontroller's control signals.

The selection criteria include operating voltage, output current, protection features, ease of PCB integration, component availability, and compatibility with our existing schematic.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: Fairchild FAN8100N** <br> **Manufacturer:** Fairchild Semiconductor <br> **Part Number:** FAN8100N <br> **Motor Supply:** 1.8V–9V <br> **Peak Current:** 1.5A per channel <br> **Package:** 12-DIP <br>  [DigiKey Product](https://www.digikey.com/en/products/detail/fairchild-semiconductor/FAN8100N/11558200) <br> [Datasheet](https://rocelec.widen.net/view/pdf/1pizbjqffm/FAIRS23777-1.pdf?t.download=true&u=5oefqw) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/45896ea9-9cc2-474c-bbe5-754e1306a7a2" /> | - Already used in our previous KiCad schematic. <br> - Through-hole package is easy to solder. <br> - Integrated motor driver reduces external circuitry. <br> - Supports low-voltage control applications. | - Maximum recommended motor supply is only 9V. <br> - Cannot safely operate our selected 12V motor at its rated voltage. <br> - Limited output current compared with newer drivers. <br> - Obsolete component is less suitable for a new design. |
| **Option 2: Texas Instruments DRV8876PWPR** <br> **Manufacturer:** Texas Instruments <br> **Part Number:** DRV8876PWPR <br> **Motor Supply:** 4.5V–37V <br> **Peak Output Current:** 3.5A <br> **Package:** 16-HTSSOP <br> **Price:** $2.07 each <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=DRV8876PWPR) <br> [Datasheet](https://www.ti.com/lit/ds/symlink/drv8876.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792210278640&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv8876) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/76256b1a-f6ff-438d-bd7c-86005146f44b" /> | - Supports 12V motor operation. <br> - Compatible with 3.3V and 5V logic inputs. <br> - Integrated current sensing and regulation. <br> - Includes overcurrent and thermal protection. <br> - Supports PWM speed control and bidirectional motor operation. | - Lower peak current than the DRV8874. <br> - May be unsuitable if the selected motor has a high stall current. <br> - Surface-mount package is harder to solder manually. <br> - Requires PCB layout and thermal design considerations. |
| **Option 3: Texas Instruments DRV8874PWPR** <br> **Manufacturer:** Texas Instruments <br> **Part Number:** DRV8874PWPR <br> **Motor Supply:** 4.5V–37V <br> **Peak Output Current:** 6A <br> **Package:** 16-HTSSOP <br>  [DigiKey Product](https://www.digikey.com/en/products/result?keywords=DRV8874PWPR) <br> [Manufacturer Datasheet](https://www.ti.com/lit/ds/symlink/drv8874.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1792210378050&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv8874) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/da58d501-2be9-4a43-bfd7-b6bcd0901c54" /> | - Supports our selected 12V motor supply. <br> - Higher 6A peak current capability than the DRV8876. <br> - Compatible with 3.3V and 5V microcontroller logic. <br> - Integrated current sensing and current regulation. <br> - Includes overcurrent, undervoltage, and thermal protection. <br> - Supports PWM speed control and motor direction control. <br> - Integrated H-bridge reduces the need for external switching MOSFETs. | - Surface-mount package requires careful soldering. <br> - Thermal pad requires appropriate PCB copper and vias. <br> - More complicated PCB layout than a through-hole driver. <br> - 6A is a peak rating, not a guaranteed continuous current capability. <br> - Motor stall current must still be verified. |

### Final Selection

**Selected Component: Option 3 – Texas Instruments DRV8874PWPR**

**Manufacturer:** Texas Instruments

**Manufacturer Part Number:** DRV8874PWPR

**Motor Driver Type:** Integrated Brushed DC H-Bridge

**Operating Supply Voltage:** 4.5V–37V

**Planned Motor Supply:** 12V DC

**Peak Output Current:** 6A

**Control Logic:** Supports 3.3V and 5V inputs

**Control Methods:** PWM, Phase/Enable, Independent Half-Bridge

**Package:** 16-HTSSOP

**Supplier:** DigiKey

### Rationale

The Texas Instruments DRV8874PWPR is selected as the preferred H-bridge motor driver for our Automatic Pet Food Dispenser because it supports 12V motor operation, offers a relatively high peak output current, and includes integrated protection features.

The DRV8874 operates from a motor supply between 4.5V and 37V, making it compatible with the proposed 12V power system.

Its 6A peak output current capability provides greater potential current-handling capacity than the DRV8876, although the selected motor's actual stall current must still be verified.

The DRV8874 also supports 3.3V and 5V logic inputs, allowing it to interface with the PIC18F57Q43 Curiosity Nano without requiring 12V control signals.

The integrated H-bridge allows the microcontroller to control motor direction and speed through digital control signals and PWM.

Another important advantage is the integrated current sensing and current regulation. These features can help detect excessive motor loading and reduce the risk of damage during startup or mechanical jams.

Compared with the FAN8100N used in our previous KiCad schematic, the DRV8874 supports the higher motor supply voltage required by our new 12V motor.

Compared with the DRV8876, the DRV8874 provides a higher peak output current rating and lower combined high-side and low-side MOSFET on-resistance.

Therefore, the **DRV8874PWPR is our preferred H-bridge motor driver**, pending verification of the motor's stall current, driver thermal performance, and final PCB layout.

---


## 6. Linear Voltage Regulator

**Subsystem: 5V Power Regulation**

The linear voltage regulator will convert the main DC power supply voltage into a stable 5V output for compatible electronic components in the Automatic Pet Food Dispenser.

Our existing KiCad schematic already includes an LM7805 voltage regulator, barrel jack, and filtering capacitors. Reusing this design will reduce the changes required for our upcoming schematic assignment.

The final power system is planned to use a 12V DC input. The motor will operate from the 12V supply through the H-bridge driver, while the linear regulator will provide 5V for compatible low-power control circuitry.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: Texas Instruments LM7805CT/NOPB** <br> **Manufacturer:** Texas Instruments <br> **Part Number:** LM7805CT/NOPB <br> **DigiKey Part Number:** 296-47192-ND <br> **Output Voltage:** 5V <br> **Maximum Input Voltage:** 35V <br> **Rated Output Current:** 1.5A <br> **Package:** TO-220-3 <br> **Price:** $1.86 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) <br> [Datasheet](https://www.ti.com/lit/ds/symlink/lm7800.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/a0fd38ea-062e-497a-b857-61c144023200" /> | - Produces a regulated 5V output. <br> - Compatible with a 12V input supply. <br> - Supports up to 1.5A under appropriate thermal conditions. <br> - Includes overcurrent and thermal protection. <br> - Through-hole package simplifies assembly. <br> - Matches the LM7805 regulator family already used in our KiCad schematic. | - Generates heat because excess voltage is dissipated as power. <br> - May require a heatsink at higher output currents. <br> - Less efficient than a switching regulator. <br> - Listed as temporarily out of stock at DigiKey during research. |
| **Option 2: STMicroelectronics L7805CV** <br> **Manufacturer:** STMicroelectronics <br> **Part Number:** L7805CV <br> **DigiKey Part Number:** 497-1443-5-ND <br> **Output Voltage:** 5V <br> **Maximum Input Voltage:** 35V <br> **Rated Output Current:** 1.5A <br> **Package:** TO-220 <br> **Price:** $1.08 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) <br> [Datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/41/4f/b3/b0/12/d4/47/88/CD00000444.pdf/files/CD00000444.pdf/jcr:content/translations/en.CD00000444.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/de6a5caa-0d68-4a10-94dd-355ba2832c44" /> | - Regulated 5V output. <br> - Compatible with a 12V input. <br> - Rated for up to 1.5A with adequate cooling. <br> - Through-hole package is easy to solder. <br> - Lower price than the Texas Instruments option. <br> - Widely available through DigiKey. | - Generates heat during voltage conversion. <br> - May require a heatsink. <br> - Requires checking capacitor values and pin configuration before substituting. <br> - Would require updating the manufacturer part number in our schematic. |
| **Option 3: onsemi MC7805CTG** <br> **Manufacturer:** onsemi <br> **Part Number:** MC7805CTG <br> **DigiKey Part Number:** MC7805CTGOS-ND <br> **Output Voltage:** 5V <br> **Maximum Input Voltage:** 35V <br> **Rated Output Current:** 1A <br> **Package:** TO-220 <br> **Price:** $1.01 <br> [DigiKey Product](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333) <br> [Datasheet](https://www.onsemi.com/pdf/datasheet/mc7800-d.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/765bbd75-7e87-4f8e-a53e-491bd16cc4d5" /> | - Produces a stable 5V output. <br> - Supports 12V input operation. <br> - Through-hole package simplifies PCB assembly. <br> - Lower cost than the other candidates. <br> - Available through DigiKey. | - Lower rated output current than the other options. <br> - Generates heat when converting 12V to 5V. <br> - Requires checking the footprint and pinout before substitution. <br> - May require additional cooling depending on current consumption. |

### Final Selection

**Selected Component: Option 1 – Texas Instruments LM7805CT/NOPB**

**Manufacturer:** Texas Instruments

**Manufacturer Part Number:** LM7805CT/NOPB

**DigiKey Part Number:** 296-47192-ND

**Regulator Type:** Positive Linear Voltage Regulator

**Input Voltage:** Up to 35V

**Planned Input Voltage:** 12V DC

**Output Voltage:** 5V DC

**Rated Output Current:** 1.5A (subject to thermal limitations)

**Package:** TO-220-3 (Through-Hole)

**Unit Price:** $1.86

**Supplier:** DigiKey

### Rationale

The Texas Instruments LM7805CT/NOPB is selected for our Automatic Pet Food Dispenser because it provides a regulated 5V output and is compatible with the LM7805 regulator circuit already created in our previous KiCad assignment.

The regulator supports input voltages up to 35V, allowing it to operate from our proposed 12V DC supply. Its fixed 5V output is suitable for powering compatible sensor and signal-conditioning circuits, including our selected MCP6004 op-amp.

The LM7805CT/NOPB has a rated output current of 1.5A under appropriate thermal conditions. This provides potential current capacity for our low-power electronics, although the actual usable current will depend on heat dissipation and the final power budget.

Compared with the STMicroelectronics L7805CV and onsemi MC7805CTG, the Texas Instruments regulator offers similar basic voltage regulation capabilities. The main reason for selecting it is compatibility with our existing LM7805-based schematic and its established electrical specifications.

The TO-220 through-hole package is also convenient for PCB assembly and allows a heatsink to be added if necessary.

Therefore, the **Texas Instruments LM7805CT/NOPB is our preferred linear voltage regulator**, allowing us to reuse much of our existing power regulation circuit.

---


## 7. External Power Supply

**Subsystem: Main DC Power Supply**

The external power supply will convert AC electricity from a standard wall outlet into regulated 12V DC power for our Automatic Pet Food Dispenser.

The selected power supply must plug directly into a standard US wall outlet without requiring a separate AC power cord. It must also provide sufficient current to operate the 12V DC motor, H-bridge motor driver, and low-voltage electronics.

Our selected DFRobot FIT0492-B motor operates at 12V. The DRV8874 H-bridge motor driver will control the motor, while the LM7805 linear voltage regulator will convert 12V into 5V for compatible electronic components.

### Component Comparison

| Solution | Pros | Cons |
|---|---|---|
| **Option 1: MEAN WELL SGA60U12-P1J** <br> **Manufacturer:** MEAN WELL <br> **Part Number:** SGA60U12-P1J <br> **Output Voltage:** 12V DC <br> **Output Current:** 5A <br> **Output Power:** 60W <br> **Type:** Wall-Mount AC/DC Adapter <br> **Plug:** US Wall Plug <br> **Price:** $27.79 each <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=SGA60U12-P1J) <br> [Manufacturer Information](https://www.meanwellusa.com/upload/pdf/SGA60U/SGA60U-spec.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/ce5f9e25-85b6-4b2a-863e-b2f0691cf6d4" /> | - Provides regulated 12V DC power. <br> - Supplies up to 5A and 60W. <br> - Plugs directly into a standard US wall outlet. <br> - No separate AC power cord required. <br> - Suitable for powering a 12V motor system. | - More expensive than some alternative adapters. <br> - Larger wall-mounted adapter may block nearby outlets. <br> - Connector compatibility must be verified. <br> - Motor stall current must still be checked. |
| **Option 2: TT Electronics PSAW65I-12-B1** <br> **Manufacturer:** TT Electronics / Power Partners <br> **Part Number:** PSAW65I-12-B1 <br> **Output Voltage:** 12V DC <br> **Output Current:** 5A <br> **Output Power:** 60W <br> **Type:** Wall-Mount AC/DC Adapter <br> **Plug:** US Wall Plug <br> **Price:**  $21.59 (verify before purchase) <br> [DigiKey Product Search](https://www.digikey.com/en/products/result?keywords=PSAW65I-12-B1) <br> [Datasheet](https://www.ttelectronics.com/TTElectronics/media/ProductFiles/Datasheet/PSAW65i.pdf) <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/19e5f357-3304-4d21-b6ed-b83167a764a1" /> | - Provides the required 12V DC output. <br> - Supplies up to 5A of current. <br> - Plugs directly into a standard US wall outlet. <br> - Does not require a separate AC power cord. <br> - Provides up to 60W of output power. <br> - Convenient for a compact pet food dispenser. <br> - Reasonable estimated price. | - Larger than lower-power wall adapters. <br> - May block an adjacent wall outlet. <br> - Barrel connector dimensions and polarity must be verified. <br> - Motor startup and stall current must be checked against the supply rating. |
| **Option 3: Adafruit Industries 4880** <br> **Manufacturer:** Adafruit Industries <br> **Part Number:** 4880 <br> **Output Voltage:** Adjustable, 3V–12V DC <br> **Maximum Output Current:** 5A <br> **Maximum Output Power at 12V:** 60W <br> **Type:** External AC/DC Desktop Adapter <br> **AC Connection:** US Wall Plug with Cord <br> **DC Connector:** 5.5mm OD × 2.1mm ID Barrel Plug <br> **Polarity:** Center Positive <br> **Price:** $17.50 <br> [DigiKey Product](https://www.digikey.com/en/products/result?keywords=4880%20Adafruit)  <br> <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/4da8b99c-8676-4ffb-a0f6-642bda7ea254" /> | - Available from DigiKey. <br> - Supports 12V operation. <br> - Provides up to 5A of current. <br> - Uses a common center-positive barrel connector. <br> - Adjustable output voltage provides flexibility. <br> - Lower listed price than our selected adapter. | - Does not plug directly into the outlet as a single wall-mounted unit. <br> - Adjustable voltage must be set correctly to avoid damaging components. <br> - Motor stall current must still be verified. <br> - Less convenient than our selected fixed-voltage wall adapter. |


### Final Selection

**Selected Component: Option 2 – TT Electronics PSAW65I-12-B1**

**Manufacturer:** TT Electronics / Power Partners

**Manufacturer Part Number:** PSAW65I-12-B1

**Power Supply Type:** Wall-Mount AC/DC Adapter

**Output Voltage:** 12V DC

**Maximum Output Current:** 5A

**Maximum Output Power:** 60W

**AC Connection:** Direct US Wall Plug

**Unit Price:**  $21.59 

**Supplier:** DigiKey


### Rationale

The TT Electronics PSAW65I-12-B1 is selected as the preferred external power supply for our Automatic Pet Food Dispenser because it provides the required 12V DC output while plugging directly into a standard US wall outlet.

Unlike desktop power adapters that require a separate AC power cord, this wall-mounted adapter provides a simpler and more convenient power connection.

The adapter has a rated output of 12V at 5A, allowing it to provide up to 60W of electrical power.

Our selected DFRobot FIT0492-B motor operates at 12V, so this supply is compatible with the planned motor voltage.

The 12V output will be connected to the PCB through a barrel jack. The power will then be distributed to the DRV8874 H-bridge motor driver and the LM7805 linear voltage regulator.

The DRV8874 will control motor direction and speed, while the LM7805 will provide a regulated 5V output for compatible sensors and signal-conditioning components.

Compared with the MEAN WELL SGA60U12-P1J, the TT Electronics adapter offers a similar 12V, 5A output rating at a potentially lower price.

Compared with the GE60I12-P1J, the TT Electronics adapter uses a direct US wall-plug configuration without requiring an interchangeable AC plug attachment.

---

eks.
