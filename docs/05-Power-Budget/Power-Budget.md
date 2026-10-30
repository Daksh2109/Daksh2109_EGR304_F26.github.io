---
title: Power Budget
---


# Power Budget

## Overview

This power budget evaluates the electrical requirements of the motor-control subsystem for the EGR 304 Automatic Pet Food Dispenser.

The subsystem uses a 12V DC power supply to operate a FIT0492-B DC gearmotor through a DRV8874 H-bridge motor driver. An L7805CV linear voltage regulator converts 12V to 5V to power the PIC18F57Q43 Curiosity Nano and supporting circuitry.

The purpose of this power budget is to determine the current required by each component, calculate the total current on each power rail, apply a 25% safety margin, and verify that the selected power supply can support the subsystem.

**Note:** The motor currents are based on the previously selected motor specifications. Some logic and driver currents are preliminary design estimates and will be verified during testing.

---

## All Major Components

| Component Name | Part Number | Supply Voltage Range | Qty. | Design Current (mA) | Total Current (mA) | Unit |
|---|---|---|---:|---:|---:|---|
| DC Gearmotor | FIT0492-B | +12V | 1 | 680 | 680 | mA |
| H-Bridge Motor Driver | DRV8874 | +12V | 1 | 5 | 5 | mA |
| PIC18F57Q43 Curiosity Nano | PIC18F57Q43 | +5V | 1 | 50 | 50 | mA |
| Debug LED and Resistor | D1, R2 | +5V | 1 | 9.09 | 9.09 | mA |
| VREF Voltage Divider | R4, R5, R6, R7 | +5V | 1 | 0.227 | 0.227 | mA |
| Manual Button Pull-Up | R3 | +5V | 1 | 0.5 | 0.5 | mA |
| DISPENSE_REQ Pull-Down | R1 | +5V | 1 | 0.5 | 0.5 | mA |

The motor is the primary electrical load. The PIC18F57Q43 and supporting circuitry require significantly less current.

The 680mA motor value represents rated-load operation, not the absolute maximum current. The motor's unregulated stall current is approximately 2190mA.

---

## +12V Power Rail

| Component Name | Part Number | Supply Voltage Range | Qty. | Design Current (mA) | Total Current (mA) | Unit |
|---|---|---|---:|---:|---:|---|
| DC Gearmotor | FIT0492-B | +12V | 1 | 680 | 680 | mA |
| H-Bridge Control Circuitry | DRV8874 | +12V | 1 | 5 | 5 | mA |
| +5V Linear Regulator Input | L7805CV | +12V | 1 | 68.32 | 68.32 | mA |
| **Subtotal** | | | | | **753.32** | **mA** |
| Safety Margin | 25% | | | | 188.33 | mA |
| **Total Current Required on +12V Rail** | | | | | **941.65** | **mA** |

### +12V Rail Calculations

Motor current:

I_motor = 680mA

H-bridge estimated control current:

I_driver = 5mA

Regulator input current:

I_regulator = 60.32mA + 8mA = 68.32mA

Total current:

I_total = 680 + 5 + 68.32

**I_total = 753.32mA**

Safety margin:

I_margin = 753.32 x 0.25

**I_margin = 188.33mA**

Total design current:

I_design = 753.32 + 188.33

**I_design = 941.65mA**

---

## +5V Power Rail

| Component Name | Part Number | Supply Voltage Range | Qty. | Design Current (mA) | Total Current (mA) | Unit |
|---|---|---|---:|---:|---:|---|
| PIC18F57Q43 Curiosity Nano | PIC18F57Q43 | +5V | 1 | 50 | 50 | mA |
| Debug LED and Resistor | D1, R2 | +5V | 1 | 9.09 | 9.09 | mA |
| VREF Voltage Divider | R4-R7 | +5V | 1 | 0.227 | 0.227 | mA |
| Manual Button Pull-Up | R3 | +5V | 1 | 0.5 | 0.5 | mA |
| DISPENSE_REQ Pull-Down | R1 | +5V | 1 | 0.5 | 0.5 | mA |
| **Subtotal** | | | | | **60.32** | **mA** |
| Safety Margin | 25% | | | | 15.08 | mA |
| **Total Current Required on +5V Rail** | | | | | **75.40** | **mA** |

### +5V Rail Calculations

PIC18F57Q43 estimated current:

I_PIC = 50mA

Debug LED current (assuming 2V LED forward voltage):

I_LED = (5V - 2V) / 330 ohms

**I_LED = 9.09mA**

VREF divider current:

R_total = 10k + 1k + 1k + 10k = 22k ohms

I_VREF = 5V / 22000 ohms

**I_VREF = 0.227mA**

Manual button pull-up current when pressed:

I_button = 5V / 10000 ohms

**I_button = 0.5mA**

DISPENSE_REQ pull-down current when driven HIGH at 5V:

I_request = 5V / 10000 ohms

**I_request = 0.5mA**

Total:

I_total = 50 + 9.09 + 0.227 + 0.5 + 0.5

**I_total = 60.32mA**

Safety margin:

I_margin = 60.32 x 0.25

**I_margin = 15.08mA**

Total design current:

I_design = 60.32 + 15.08

**I_design = 75.40mA**

---

## Regulators

| Power Rail | Component Name | Part Number | Input Voltage | Output Voltage | Qty. | Estimated Output Current | Rated Output Current |
|---|---|---|---|---|---:|---:|---:|
| +5V | Linear Voltage Regulator | L7805CV | +12V | +5V | 1 | 60.32mA | 1500mA* |

*The L7805CV's rated current is subject to thermal operating conditions.

### Regulator Power Calculations

Input voltage:

Vin = 12V

Output voltage:

Vout = 5V

Estimated output current:

Iout = 0.06032A

Output power:

Pout = Vout x Iout

Pout = 5 x 0.06032

**Pout = 0.302W**

Estimated voltage drop:

Vdrop = 12 - 5

**Vdrop = 7V**

Estimated regulator heat dissipation from load current:

Pheat = Vdrop x Iout

Pheat = 7 x 0.06032

**Pheat = 0.422W**

Allowing an estimated 8mA of regulator ground current:

Pground = 12 x 0.008 = 0.096W

Total estimated regulator dissipation:

Pheat_total = 0.422 + 0.096

**Pheat_total = 0.518W**

This heat dissipation must be considered during PCB design and verified by temperature measurements during testing.

---

## External Power Source 1

### Power Source 1 Selection

| Component Name | Part Number | Input Voltage | Output Voltage | Maximum Current | Maximum Power |
|---|---|---|---|---:|---:|
| AC/DC Power Supply | PSAW65I-12-B1 | AC Mains | +12V DC | 5000mA | 60W |

The selected power supply provides a regulated 12V output with a maximum current rating of 5A.

### Power Rails Connected to External Power Source 1

| Power Rail | Total Current Required (mA) |
|---|---:|
| +12V Rail (including regulator input) | 753.32 |
| Safety Margin (25%) | 188.33 |
| **Total Current Required** | **941.65** |
| Available Supply Current | 5000 |
| **Remaining Current Capacity** | **4058.35** |

The +5V rail is powered by the L7805CV regulator connected to the +12V rail. Its current is already accounted for in the regulator input current and must not be added again to the external supply total.

### Power Supply Verification

Power supply output:

P_supply = 12V x 5A

**P_supply = 60W**

Estimated normal operating power:

P_system = 12V x 0.75332A

**P_system = 9.04W**

Estimated power with 25% current margin:

P_design = 12V x 0.94165A

**P_design = 11.30W**

Normal operating supply utilization:

Utilization = (9.04 / 60) x 100

**Utilization = 15.1%**

The selected power supply has sufficient nominal capacity for the estimated rated-load operation.

---

## Motor Startup and Stall Current

The FIT0492-B DC gearmotor has the following approximate operating characteristics:

| Operating Condition | Motor Current | Motor Electrical Input Power |
|---|---:|---:|
| No Load | 170mA | 2.04W |
| Rated Load | 680mA | 8.16W |
| Unregulated Stall | 2190mA | 26.28W |

The DRV8874 motor driver includes current regulation to reduce excessive motor current.

The schematic uses an estimated VREF of 2.273V and an IPROPI resistor of 3.3k ohms.

Using a nominal current-sense gain of 455 microamps per amp:

I_trip = 2.273 / (3300 x 0.000455)

**I_trip = approximately 1.51A**

This is a nominal calculation, not a guaranteed current limit. Actual behavior depends on the motor driver configuration, tolerances, and current-regulation operation.

At a nominal 1.51A current-limit reference:

P_motor = 12V x 1.51A

**P_motor = approximately 18.1W**

The selected 12V, 5A supply has enough rated output capacity for this estimated transient condition. Actual startup and stall current must be measured.

---

## Fuse and Protection

| Component | Rating | Purpose |
|---|---|---|
| F1 | 3A Slow-Blow (preliminary) | Protects the 12V power input |
| DRV8874 | Current Regulation | Limits motor current under configured conditions |
| L7805CV | Thermal Protection | Provides internal regulator thermal protection |

The 3A fuse rating is preliminary and must be validated against the power supply, wire ratings, DC interrupting capacity, and expected fault current.

---

## Power Budget Summary

| Parameter | Calculated Value |
|---|---:|
| Main Supply Voltage | 12V |
| Main Supply Maximum Current | 5000mA |
| Main Supply Maximum Power | 60W |
| Estimated Normal System Current | 753.32mA |
| Estimated Normal System Power | 9.04W |
| +12V Design Current With 25% Margin | 941.65mA |
| +5V Estimated Current | 60.32mA |
| +5V Design Current With 25% Margin | 75.40mA |
| Regulator Estimated Heat Dissipation | 0.518W |
| Motor Rated Current | 680mA |
| Motor Unregulated Stall Current | 2190mA |
| Estimated DRV8874 Current Limit | 1510mA |
| Estimated Supply Utilization | 15.1% |

---

## Conclusions

From the preliminary power budget, the selected 12V, 5A power supply is sufficient for the estimated normal operating requirements of the motor-control subsystem.

The FIT0492-B gearmotor is the primary electrical load, requiring approximately 680mA during rated operation. The PIC18F57Q43 Curiosity Nano and supporting 5V circuitry require an estimated 60.32mA.

The +12V rail requires approximately 753.32mA during rated motor operation. Including a 25% safety margin increases the design requirement to approximately 941.65mA, which is below the selected power supply's 5000mA rating.

The L7805CV regulator provides the required 5V output for the controller. Its estimated heat dissipation is approximately 0.518W and should be verified during hardware testing.

The DRV8874 motor driver provides motor-current regulation. The nominal current-limit calculation is approximately 1.51A, but actual current regulation and startup behavior must be confirmed experimentally.

Overall, the subsystem is expected to operate within the nominal capacity of the selected power supply. Final validation will include current measurements, regulator temperature measurements, and verification of the fuse and motor driver protection.

---

## Resources

- [FIT0492-B DC Gearmotor Datasheet](https://media.digikey.com/pdf/Data%20Sheets/DFRobot%20PDFs/FIT0492-B_Web.pdf)
- [DRV8874 Motor Driver Datasheet](https://www.ti.com/lit/ds/symlink/drv8874.pdf)
- [L7805CV Linear Regulator Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf)
- [Microchip PIC18F57Q43 Curiosity Nano](https://www.microchip.com/)
