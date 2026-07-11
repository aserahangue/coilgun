# 2-stages Electromagnetic Gun

<img width="904" height="511" alt="Fusion360 - Coilgun 3D design (left side)" src="https://github.com/user-attachments/assets/cd66c6b0-bbf0-42b3-9d6a-43903eeccddc" />

## Overview

This project is a fully custom two-stage electromagnetic launcher designed to explore high-power electronics, embedded systems, and mechanical design.

| Specification | Value |
|:---------|:--------------|
| Maximum Velocity | 40 m/s (90 mph) |
| Projectile | Ø4.9 × 60 mm headless steel pin |
| Energy Storage | 2 × 548 J (6200 µF @ 420 V) |
| Charging System | Dual 500 W flyback converters |
| Capacitor Charging time | < 7 s |
| Peak Discharge Current | ≈ 300 A |
| Battery | Custom 10S2P Li-ion pack (Samsung 25R) |
| Controller | ESP32 |

⚠ For safety reasons, the design files are not publicly available.

---

## Block diagram

The coilgun relies on several power rails, including:

- A conventional power rail for the MCU and user interface (+12 V, +5 V, +3.3 V)
- An isolated +12 V supply for capacitor voltage measurements
- A 1 kW buck converter supplying both capacitor chargers

The entire system is powered by a custom 10S2P lithium-ion battery pack capable of delivering 20 A continuously.

<img width="986" height="602" alt="Capture d&#39;écran 2026-07-11 015324" src="https://github.com/user-attachments/assets/168abf07-ee99-4427-a56e-ea17d21e38a3" />


## PCB Design

Three PCB's are used:
- 1 & 2: host power supplies (+24V @ 1 kW, +12V, +12V_ISO, +5V, +3V3), microcontroller and charging/firing system. It's actually two PCBs in one, to reduce manufacturing costs.
- 3: 10S2P BMS.

I started off by grouping most of the components by function, according to their recommanded layout and expected orientation:
<img width="1903" height="1316" alt="PCB editing - Grouping components" src="https://github.com/user-attachments/assets/ebc82656-5912-4302-a4ea-6dceed56eb97" />

Weeks after, here's how the final PCB looks like:
<img width="5457" height="2130" alt="PCB_COILGUN_V1 0_RevA" src="https://github.com/user-attachments/assets/5a1c153d-648e-4dde-9daa-d003ec5140ef" />

With the completed routing - layers Top & Middle-1. The only ratsnest lines left visible are those between the board-to-board connectors:
<img width="1133" height="493" alt="Coilgun PCB Top" src="https://github.com/user-attachments/assets/a5d324cb-e90b-4029-b14e-254d5d7f5301" />
<img width="1133" height="493" alt="Coilgun PCB Mid1" src="https://github.com/user-attachments/assets/f9a05369-f856-4ce3-b21d-89e8c1a4f438" />

---

## Mechanical Design

After exporting the STEP model of the combined PCB, I split it into two separate boards and imported them into the cannon's 3D model to optimize the mechanical design.
<img width="941" height="494" alt="Fusion360 - PCB in 3D design" src="https://github.com/user-attachments/assets/09884cce-3f6e-4364-9156-f6fc9d529ca9" />

I also printed them out (fully assembled) before putting into fabrication, to ensure a perfect integration.
<img width="953" height="433" alt="image" src="https://github.com/user-attachments/assets/67953338-5eba-4e81-b9dd-1627ac1ecab4" />

## Software

The firmware was written in C++. It is relatively straightforward, as most of the system functionality, including the safety features, is handled directly by the hardware.

Its main responsibilities include:
- User interface (buttons, LEDs, and I²C displays),
- Safety monitoring (watchdog, temperature monitoring, and communication with the BMS),
- Projectile timing (IGBT activation/deactivation and laser-based velocity measurement).


---
