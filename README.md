# Drone Power Distribution Board (PDB)

Custom-designed power distribution board for quadcopter drones, created using TSCircuit.

![3D Render](drone-pdb_3d.png)

## Overview

This PDB provides clean power distribution for a 4S LiPo-powered quadcopter with integrated voltage regulation and battery monitoring capabilities.

## Features

- **XT60 Battery Input** with fused protection (0.01Ω current sense resistor)
- **4x ESC Power Outputs** for quadcopter motor controllers  
- **5V Buck Regulator** (up to 3A) for flight controller and receiver
- **3.3V LDO Regulator** (up to 1A) for peripheral electronics
- **Battery Voltage Sensing** circuit with 100kΩ/10kΩ divider for ADC monitoring
- **80mm x 60mm** form factor suitable for 5" racing drones

## Specifications

| Parameter | Value |
|-----------|-------|
| Input Voltage | 14.8V - 16.8V (4S LiPo) |
| Max Current (per ESC) | 30A |
| 5V Output | Up to 3A |
| 3.3V Output | Up to 1A |
| Board Dimensions | 80mm x 60mm |

## Design Views

### Schematic
![Schematic](drone-pdb_schematic.png)

### PCB Layout
![PCB Layout](drone-pdb_pcb.png)

### 3D Render
![3D View](drone-pdb_3d.png)

## Circuit Architecture
```
Battery (XT60)
    ↓
  Fuse (0.01Ω sense resistor)
    ↓
    ├──→ ESC 1 (VBAT + GND)
    ├──→ ESC 2 (VBAT + GND)
    ├──→ ESC 3 (VBAT + GND)
    ├──→ ESC 4 (VBAT + GND)
    ├──→ 5V Buck Regulator → Flight Controller
    │       ↓
    │    3.3V LDO → Peripherals
    └──→ Voltage Divider → ADC (Battery Monitoring)
```

## Component List

- **J_BAT**: XT60 battery connector (2-pin)
- **F1**: 0.01Ω current sense resistor (2512 footprint)
- **J_ESC1-4**: ESC power output connectors (4x 2-pin)
- **U5V**: 5V buck regulator module (3-pin)
- **U3V3**: 3.3V LDO regulator module (3-pin)
- **C1**: 100µF input capacitor (1206)
- **C2**: 220µF output capacitor (1206)
- **C3-C4**: 10µF filtering capacitors (0805)
- **R1**: 100kΩ voltage divider resistor (0805)
- **R2**: 10kΩ voltage divider resistor (0805)
- **C_SENSE**: 0.1µF sense filter capacitor (0805)
- **J_ADC**: Voltage sense output header (2-pin)

## Files Included

- `drone-pdb.json` - TSCircuit design file (can be imported into TSCircuit editor)
- `drone-pdb_schematic.png` - Schematic diagram
- `drone-pdb_pcb.png` - PCB layout view
- `drone-pdb_3d.png` - 3D render of assembled board
- `drone-pdb_fabrication_files.zip` - Gerber files for PCB manufacturing
- `drone-pdb_kicad.zip` - KiCad project files for further editing

## Design Tools

- **TSCircuit** - Open-source PCB design in TypeScript/React
- **Cloud Autorouter** - Automatic trace routing engine

## Project Context

This PDB was designed as part of an **autonomous drone swarm project** using STM32 microcontrollers with ROS2 for inter-drone communication. The board provides stable, regulated power to:
- Flight controller (Pixhawk/Betaflight)
- ESCs and brushless motors
- Telemetry and communication modules
- Sensors (GPS, IMU, etc.)

## Manufacturing

The included Gerber files can be sent directly to PCB manufacturers like:
- JLCPCB
- PCBWay
- OSH Park

**Recommended specs:**
- 2oz copper weight (for high current capacity)
- 1.6mm board thickness
- HASL or ENIG surface finish

## Future Improvements

- [ ] Add copper pour/planes for better current distribution
- [ ] Increase trace width to 2mm+ for high-current paths
- [ ] Add TVS diode for reverse voltage protection
- [ ] Add status LEDs (Power, 5V, 3.3V indicators)
- [ ] Add mounting holes (M3, 45mm spacing)
- [ ] Implement dedicated current sensing IC (INA219/INA226)
- [ ] Add JST-GH connectors for direct flight controller integration

## Related Projects

- [Autonomous Drone Swarm](https://github.com/BrianEstime1) *(link when available)*

## License

This project is open-source under the MIT License.

## Author

**Brian Estime**  
Electrical Engineering Student @ UCF (Transfer Fall 2026)  
Focus: Robotics, Autonomous Systems, GNC Engineering

[LinkedIn](https://linkedin.com/in/brianestime) | [GitHub](https://github.com/BrianEstime1)

## Acknowledgments

- Designed with [TSCircuit](https://tscircuit.com)
- Inspired by commercial PDBs from Matek Systems and Holybro
```

5. Scroll down and click **"Commit changes"**

---

## Step 2: Pin This Repo

1. Go to your GitHub profile: `github.com/BrianEstime1`
2. Click **"Customize your pins"**
3. Check the box for **"drone-pdb"**
4. Click **"Save pins"**

Now it shows up prominently on your profile! 🎯

---

## Step 3: Add Topics/Tags

On your repo page:
1. Click the gear icon ⚙️ next to "About"
2. Add these topics:
   - `pcb-design`
   - `tscircuit`
   - `drone`
   - `quadcopter`
   - `power-distribution`
   - `embedded-systems`
   - `electrical-engineering`
3. Click **"Save changes"**

This makes your repo discoverable by search.

---

## You're Done! 🚀

Your repo is now:
- ✅ Live on GitHub
- ✅ Professionally documented
- ✅ Has all design files
- ✅ Shows manufacturing capability
- ✅ Demonstrates real-world application

**Next steps:**
1. Update your LinkedIn:
   - Add to "Projects" section
   - Link to the GitHub repo
   
2. Add to your resume under projects:
```
   Drone Power Distribution Board Design
   • Designed custom PCB for autonomous quadcopter using TSCircuit
   • Implemented 5V/3.3V buck regulators, battery monitoring, and 4x ESC outputs
   • Generated manufacturing-ready Gerber files for PCB fabrication
   GitHub: github.com/BrianEstime1/drone-pdb
