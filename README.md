# 2-stages Electromagnetic Gun

![Overview](images/overview.jpg)

## Overview

This project is a fully custom two-stage electromagnetic launcher designed to explore high-power electronics, embedded systems, and mechanical design.

| Category | Specification |
|:---------|:--------------|
| Project Duration | 18 months |
| Architecture | Two-stage electromagnetic launcher |
| Energy Storage | 2 kJ (450 V, 6200 µF) |
| Charging System | Dual 1 kW flyback converters |
| Battery | Custom 10S2P Li-ion pack |
| Power Stage | Custom IGBT switching stage |
| Peak Current | >300 A |
| Controller | ESP32 |
| Custom PCBs | 12 |
| Mechanical Design | Custom CAD & 3D printed |
| Maximum Velocity | 40 m/s (90 mph) |

---


## PCB Design

Three PCB's are used: 1st & 2nd host power supplies, controller and charging/firing system, and 3rd is the BMS.
The two main PCB's are long rectangles. I chose to keep them tied for manufacturing, so I reduced the costs.
I started off by grouping most of the components by function around their IC, according to their recommanded layout:
<img width="1615" height="1078" alt="Capture d&#39;écran 2025-04-20 171542" src="https://github.com/user-attachments/assets/f9747d3e-53fb-4c2a-a0ad-310ad99a1de2" />
<img width="1903" height="1316" alt="Capture d&#39;écran 2025-04-21 004925" src="https://github.com/user-attachments/assets/ebc82656-5912-4302-a4ea-6dceed56eb97" />

<img width="2409" height="1312" alt="Final stage routing" src="https://github.com/user-attachments/assets/b6e4efb9-2f37-45b7-8a9f-2122811429c9" />

Here's how the final PCB looks like. I chose 
<img width="2413" height="1313" alt="Capture d&#39;écran 2025-05-12 003320" src="https://github.com/user-attachments/assets/15b95ab1-c4ca-4632-bf9f-307202ce78a9" />


---

## Mechanical Design

(images)

## Technical Challenges

- Designed a 450 V capacitor charging system using dual flyback converters.
- Developed a custom 10S2P Li-ion battery pack with dedicated BMS.
- Designed high-current IGBT switching stages handling peak currents above 300 A.
- Developed ESP32-based control electronics and firmware.
- Designed all PCBs and mechanical assemblies from scratch.

---
