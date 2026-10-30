---
title: Bill of Materials
tags:
- tag1
- tag2
---



## Overview

This Bill of Materials (BOM) lists the components used in the motor-control subsystem of the EGR 304 Automatic Pet Food Dispenser. The subsystem uses a PIC18F57Q43 Curiosity Nano to control a DRV8874 H-bridge motor driver and a 12V DC gearmotor. A linear regulator provides the 5V supply for the controller.

The DC motor, H-bridge, linear voltage regulator, and external DC power supply are sourced from DigiKey. Resistors, capacitors, fuse, barrel jack, LED, and pushbutton are supplied from Peralta's electronics inventory. The PIC18F57Q43 Curiosity Nano is already provided. Components obtained from Peralta or already provided have a project purchase cost of $0.00.

## Bill of Materials

| Part Name / Description | Qty | Unit Cost | Total Cost | Manufacturer | Manufacturer # | Vendor Link | Datasheet Link | Schematic Reference Designators |
|---|---:|---:|---:|---|---|---|---|---|
| 0.1 µF ceramic capacitor, 10V minimum | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | C1 |
| 0.33 µF capacitor, 25V / 10V minimum respectively | 2 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | C2, C3 |
| 100 µF capacitor, 50V | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | C4 |
| 0.022 µF ceramic capacitor, 50V | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | C5 |
| 0.1 µF ceramic capacitor, 50V | 2 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | C6, C7 |
| Indicator LED | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | D1 |
| 3A time-delay fuse, DC-rated | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | F1 |
| 8-pin male PCB header, 2.54 mm pitch | 1 | $0.00 | $0.00 | Peralta inventory | Generic 1x8 pin header | Peralta | N/A | J1 |
| DC barrel jack | 1 | $0.00 | $0.00 | Peralta inventory | Stock item| Peralta | N/A | J2 |
| 12V, 100 RPM, 5W DC gearmotor | 1 | $11.90 | $11.90 | DFRobot | FIT0492-B | [DigiKey](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-B/7087168) | [Datasheet](https://media.digikey.com/pdf/Data%20Sheets/DFRobot%20PDFs/FIT0492-B_Web.pdf) | M1 |
| 10 kΩ resistor, 0.25W | 5 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | R1, R3, R4, R7, R8 |
| 330 Ω resistor, 0.25W | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | R2 |
| 1 kΩ resistor, 0.25W | 2 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | R5, R6 |
| 3.3 kΩ resistor, 0.25W | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | R9 |
| Pushbutton | 1 | $0.00 | $0.00 | Peralta inventory | Stock item | Peralta | N/A | SW1 |
| PIC18F57Q43 Curiosity Nano development board | 1 | $0.00 | $0.00 | Microchip Technology | PIC18F57Q43 Curiosity Nano | Already provided | [Datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/UserGuides/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf) | U1 |
| 5V, 1.5A linear voltage regulator, TO-220 | 3 | $1.08 | $3.24 | STMicroelectronics | L7805CV; DigiKey 497-1443-5-ND | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | U2 |
| H-bridge motor driver, 16-HTSSOP | 3 | $3.85 | $11.55 | Texas Instruments | DRV8874PWPR ; DigiKey 296-DRV8874PWPRCT-ND | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/DRV8874PWPR/11502339) | [Datasheet](https://www.ti.com/lit/ds/symlink/drv8874.pdf) | U3 |
| 12V, 5A, 60W AC/DC external power supply | 1 | $20.36 | $20.36 | TT Electronics / Power Partners | PSAW65I-12-B1; DigiKey 3989-PSAW65I-12-B1-ND | [DigiKey](https://www.digikey.com/en/products/detail/tt-electronics-power-partners-inc/PSAW65I-12-B1/15838872) | [Datasheet](https://www.ttelectronics.com/TTElectronics/media/ProductFiles/Datasheet/PSAW65I.pdf) | External power supply |

## Cost Summary

| Source | Estimated Purchase Cost |
|---|---:|
| DigiKey - DC gearmotor | $11.90 |
| DigiKey - DRV8874 motor driver | $11.55 |
| DigiKey - L7805CV regulator | $3.24 |
| DigiKey - 12V power supply | $20.36 |
| Peralta-provided components | $0.00 |
| Previously provided PIC board | $0.00 |
| **Purchasing-components subtotal** | **$47.05** |

**Note:** Prices are single-unit DigiKey listing prices checked October 2026 and may change. Shipping, taxes, and other costs are excluded.

  
