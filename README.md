# 2-stages Electromagnetic Gun

<img width="904" height="511" alt="Fusion360 - Coilgun 3D design (half)" src="https://github.com/user-attachments/assets/cd66c6b0-bbf0-42b3-9d6a-43903eeccddc" />

## Overview

This project is a fully custom two-stage electromagnetic launcher designed to explore high-power electronics, embedded systems, and mechanical design.

| Category | Specification |
|:---------|:--------------|
| Project Duration | 18 months |
| Energy Storage | 2 kJ (450 V, 6200 µF) |
| Charging System | Dual 1 kW flyback converters |
| Battery | Custom 10S2P Li-ion pack |
| Peak Current | >300 A |
| Controller | ESP32 |
| Maximum Velocity | 40 m/s (90 mph) |

---
deee

## PCB Design

Three PCB's are used: 1st & 2nd host power supplies, controller and charging/firing system, and 3rd is the BMS.
The two main PCB's are long rectangles. I chose to keep them tied for manufacturing, so I reduced the costs.
I started off by grouping most of the components by function around their IC, according to their recommanded layout:
<img width="1903" height="1316" alt="PCB editing - Grouping components" src="https://github.com/user-attachments/assets/ebc82656-5912-4302-a4ea-6dceed56eb97" />

<img width="2409" height="1312" alt="PCB editing - Final stage routing" src="https://github.com/user-attachments/assets/b6e4efb9-2f37-45b7-8a9f-2122811429c9" />

Here's how the final PCB looks like.
<img width="5457" height="2130" alt="PCB_COILGUN_V1 0_RevA" src="https://github.com/user-attachments/assets/db2a6016-43cb-447c-82a7-48b03ea57f8f" />



---

## Mechanical Design

After exporting STEP file of the 2 tied PCB, I split then uploaded them in Fusion360, so I can adjust the 3D design.
I also printed them out (fully assembled) before putting into fabrication, to ensure a perfect integration.
<img width="941" height="494" alt="Fusion360 - PCB in 3D design" src="https://github.com/user-attachments/assets/09884cce-3f6e-4364-9156-f6fc9d529ca9" />

## Technical Challenges

- Designed a 450 V capacitor charging system using dual flyback converters.
- Developed a custom 10S2P Li-ion battery pack with dedicated BMS.
- Designed high-current IGBT switching stages handling peak currents above 300 A.
- Developed ESP32-based control electronics and firmware.
- Designed all PCBs and mechanical assemblies from scratch.

---
