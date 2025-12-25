# ProCore-XY: High-Precision CoreXY 3D Printer

## 1. Project Overview
ProCore-XY is a custom-engineered 3D printer designed to bridge the gap between entry-level kits and industrial machines. By designing the frame and motion system from scratch using Onshape, I am learning the fundamentals of CoreXY kinematics, firmware configuration, and structural engineering.

**View the Full CAD Assembly:** [[CLICK ME](https://cad.onshape.com/documents/f675ace4e6a168e97cb3401b/w/ee7959d844951d23f3b9f2f5/e/f9b3ea5ecbe7a33df748d010)]

## 2. Technical Architecture

### The Motion System
* **Architecture:** CoreXY. This kinematic system reduces moving mass, allowing for higher acceleration and faster print speeds without ghosting artifacts.
* **Linear Guidance:** The X and Y axes utilize **THK RSH12ZM Linear Rails** (320mm). Unlike standard POM wheels, these industrial guide rails provide constrained, smooth motion with zero play.
* **Z-Axis:** The build utilizes an **SG2602A-250H Ball Screw Actuator Rail**. This integrated module replaces the traditional lead screw/rod setup, eliminating Z-wobble and ensuring perfect layer stacking.

### Electronics & Control
* **Mainboard:** **BTT SKR Mini E3 V3.0** (32-bit). This board drives the system with TMC2209 silent stepper drivers in UART mode, enabling sensorless homing and precise current control.
* **Interface:** **FYSETC Mini12864 RGB LCD**. A compact, clickable interface that allows for full printer control and real-time status monitoring.
* **Power:** A **24V 16.7A 400W Power Supply** ensures stable current for the heated bed and hotend, with overhead for future upgrades.

### Extrusion System
* **Hotend:** **V6 Hotend Set (E3D Clone)** mounted on a custom aluminum bracket.
* **Nozzle:** **CHT 0.4mm Nozzle**. This "Core Heating Technology" nozzle splits the filament path to increase melt rate, essential for high-speed printing.
* **Feeder:** **Dual Gear Drive Extruder**. Provides high-torque filament grip to prevent slipping during fast retractions.|

## 3. Engineering Decisions & Justification

**Why the SG2602A-250H?**
Standard budget printers use a simple T8 lead screw that is often unsupported, leading to "Z-banding" (ribs on the print). The SG2602A-250H is a fully enclosed actuator rail. It constrains the screw at both ends and creates a rigid structural column, guaranteeing that the bed moves in a perfectly straight line.

**Why THK RSH12ZM Rails?**
I chose 12mm linear rails over V-slot wheels because they are maintenance-free and rigid. V-wheels wear down and develop "flat spots" over time, whereas steel linear rails maintain their precision indefinitely, which is critical for a CoreXY machine running at high speeds.

## 4. Assembly Plan
1.  **Frame & Motion:** Assemble the 2020 aluminum profile frame and mount the SG2602A-250H Z-axis.
2.  **Gantry:** Install the THK linear rails and align the CoreXY belt path using the 20T/16T pulleys.
3.  **Wiring:** Crimp connectors for the SKR Mini E3 and route the ribbon cables for the Mini12864 LCD.
4.  **Firmware:** Configure Marlin Firmware to support the specific steps/mm of the ball screw and the kinematics of CoreXY.
