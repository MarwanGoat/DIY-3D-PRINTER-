# ProCore-XY: High-Precision CoreXY 3D Printer

## 1. Project Overview
ProCore-XY is a custom-engineered 3D printer designed to bridge the gap between entry-level kits and industrial machines. By designing the frame and motion system from scratch using Onshape, I am learning the fundamentals of CoreXY kinematics, firmware configuration, and structural engineering.

**View the Full CAD Assembly:** [[CLICK ME](https://cad.onshape.com/documents/f675ace4e6a168e97cb3401b/w/ee7959d844951d23f3b9f2f5/e/f9b3ea5ecbe7a33df748d010)]

**📥 [Download the Full CAD Assembly (.STEP)](https://gofile.io/d/4HFw3o)**

![Full Assembly Overview](https://raw.githubusercontent.com/MarwanGoat/DIY-3D-PRINTER-/refs/heads/main/schematics%20and%20blueprints/picture%20of%20CAD.png)
*Figure 1: Complete 3D assembly in Onshape.*

## 2. Technical Architecture

### The Frame & Motion System
* **Frame:** Built from **1x1" tubular steel** (1.5mm thick) for maximum rigidity. The frame measures **450mm x 380mm x 380mm**.
* **Architecture:** CoreXY. This kinematic system reduces moving mass, allowing for higher acceleration and faster print speeds without ghosting artifacts.
* **Linear Guidance:** The X and Y axes utilize **THK RSH12ZM Linear Rails** (320mm).
* **Z-Axis:** The build utilizes an **SG2602A-250H Ball Screw Actuator Rail** mounted with a custom cantilever bracket.

![Steel Frame Blueprint](https://raw.githubusercontent.com/MarwanGoat/DIY-3D-PRINTER-/refs/heads/main/schematics%20and%20blueprints/frame%20blueprint.png)
*Figure 2: Engineering plans for the steel frame and Z-rail bracket.*

### Electronics & Wiring
* **Mainboard:** **BTT SKR Mini E3 V3.0** (32-bit). Drives the system with TMC2209 silent stepper drivers.
* **Interface:** **FYSETC Mini12864 RGB LCD** connected via dedicated logic paths.
* **Power:** A **24V 16.7A 400W Power Supply** ensures stable current for the heated bed and hotend.

![Electrical Schematic](https://raw.githubusercontent.com/MarwanGoat/DIY-3D-PRINTER-/refs/heads/main/schematics%20and%20blueprints/general%20schematic%20v2.png)
*Figure 3: Full wiring logic for power distribution and logic control.*

### Extrusion System
* **Hotend:** **V6 Hotend Set** with a **CHT 0.4mm Nozzle** for increased melt rates.
* **Feeder:** **Dual Gear Drive Extruder** for high-torque filament grip.

## 3. Engineering Decisions & Justification

**Why the SG2602A-250H?**
Standard budget printers use simple T8 lead screws that lead to "Z-banding." The SG2602A-250H is a fully enclosed actuator rail that constrains the screw at both ends, guaranteeing a perfectly straight Z-path.

**Why Steel over Aluminum?**
While many DIY printers use 2020 aluminum, I am fabricating this frame from **steel tubing** in my dad's workshop to achieve industrial-level mass and damping, which is critical for high-speed CoreXY movements.

## 4. Bill of Materials (BOM)
The project utilizes a mix of industrial-grade motion components and open-source electronics.

![BOM Snapshot](https://github.com/MarwanGoat/DIY-3D-PRINTER-/blob/f6e7c540bce8a4007da4ff4e4244e5b62697e1da/3d%20printer%20bom.csv)
*Figure 4: Complete itemized budget and component list.*
