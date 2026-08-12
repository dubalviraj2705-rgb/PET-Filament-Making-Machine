# PET Bottle Filament Making Machine ♻️

A low-cost and sustainable **PET bottle-to-3D-printer-filament machine** designed to convert waste PET bottles into usable filament for 3D printing.

The system directly converts **PET bottle strips** into filament through controlled heating, extrusion, cooling, pulling, sizing, and spooling. The project aims to reduce plastic waste while providing a low-cost alternative to commercially available 3D-printing filament.



## 📌 Project Overview

Plastic waste management is a major environmental challenge. PET (Polyethylene Terephthalate) bottles are widely used and frequently discarded after a single use.

At the same time, 3D-printing filament can be relatively expensive, especially for students, hobbyists, educational institutions, and small workshops.

This project combines **plastic recycling and additive manufacturing** by converting waste PET bottles into 3D-printer filament.

The machine follows this basic process:

**Waste PET Bottle → Bottle Strip → Heating → Melting → Extrusion → Cooling → Pulling → Sizing → Spooling → Recycled Filament**

The proposed machine is designed to be compact, economical, and easier to build compared with large industrial extrusion systems.



## 🎯 Aim

To design and develop a **low-cost, compact PET bottle filament-making machine** that converts PET bottle waste into 3D-printing filament while reducing plastic pollution and supporting sustainable recycling.

---

## 🎯 Objectives

* Cut PET bottles into uniform strips suitable for feeding.
* Develop a controlled PET heating and melting system.
* Extrude molten PET through a controlled nozzle.
* Develop a pulling mechanism for the filament.
* Develop a filament spooling mechanism.
* Maintain filament diameter within approximately **±0.1 mm tolerance**.
* Reduce the cost of 3D-printing consumables.
* Promote sustainable recycling and circular use of plastics.

---

## ⚙️ Working Principle

The machine works in several stages.

### 1. PET Bottle Collection

Waste PET bottles are collected from households, shops, recycling bins, or other sources.

### 2. Sorting

The bottles are sorted and non-PET components such as caps, labels, and other unwanted materials are removed.

### 3. Cleaning

The bottles are thoroughly washed using water and detergent to remove dirt, glue, and other contaminants.

### 4. Drying

The cleaned bottles are dried before processing.

Proper drying is important because moisture can cause bubbles and defects during the heating and extrusion process.

### 5. Bottle Strip Cutting

A cutting mechanism converts the PET bottle into a long, thin strip with approximately uniform width.

### 6. Feeding

The PET strip is guided into the heating system.

### 7. Heating and Melting

The PET strip enters a **V6 heating block** where it is heated until it reaches a molten state.

The proposed PET temperature range is approximately:

**250–270 °C**

Temperature is controlled using a **REX-C100 temperature controller** and SSR.

### 8. Extrusion

The molten PET passes through a nozzle to form a continuous filament.

Possible nozzle sizes mentioned in the project are:

* 1.75 mm
* 3 mm

### 9. Cooling

A DC cooling fan is positioned after the nozzle.

The fan rapidly cools and solidifies the extruded filament.

### 10. Sizing

The filament passes through a sizing guide/hole to help maintain a consistent diameter.

### 11. Pulling

A DC geared motor drives the roller mechanism.

The rollers pull the filament at a controlled speed.

The initial proposed pulling speed is approximately:

**0.5–1 m/min**

The speed can be adjusted to obtain the desired filament diameter.

### 12. Spooling

The cooled filament is guided onto a rotating reel.

The spooler winds the filament evenly to prevent tangling.

---

## 🔲 Block Diagram

```text
       WASTE PET BOTTLES
               │
               ▼
        SORTING & CLEANING
               │
               ▼
             DRYING
               │
               ▼
        BOTTLE STRIP CUTTER
               │
               ▼
          FEEDING SYSTEM
               │
               ▼
       ┌──────────────────┐
       │   V6 HEATER      │
       │  HEATING BLOCK   │
       └──────────────────┘
               │
               ▼
          PET MELTING
               │
               ▼
           NOZZLE
               │
               ▼
       EXTRUDED FILAMENT
               │
               ▼
        COOLING FAN
               │
               ▼
         SIZING GUIDE
               │
               ▼
       PULLING ROLLERS
               │
               ▼
          SPOOLING
               │
               ▼
       RECYCLED PET
       3D PRINTING FILAMENT
```

---

## 🔌 Electrical System

The electrical system consists of the following major sections:

```text
                 AC INPUT
                    │
                    ▼
          ┌─────────────────┐
          │ Mean Well       │
          │ LRS-100-24      │
          │ 24V / 100W      │
          └─────────────────┘
             │      │     │
             │      │     └────────► Cooling Fan
             │      │
             │      └──────────────► Motor Driver
             │                         │
             │                         ▼
             │                     DC Motor
             │
             ▼
       Heating Control
             │
             ▼
        REX-C100
             │
             ▼
            SSR
             │
             ▼
       24V Heater
             │
             ▼
       V6 Heating Block
```

---

## 🌡️ Temperature Control

The heating system uses:

* **REX-C100 temperature controller**
* **K-type thermocouple**
* **Solid State Relay (SSR)**
* **24V heater cartridge**
* **V6 heating block**

The thermocouple measures the heating-block temperature.

The REX-C100 compares the measured temperature with the desired setpoint and controls the heater through the SSR.

### Proposed Temperature Range

```text
PET Processing Temperature
        ↓
   250 – 270 °C
```

---

## 🧩 Main Components

| Sr. No. | Component              | Specification                      |
| ------: | ---------------------- | ---------------------------------- |
|       1 | Heater Cartridge       | 24V, 40W                           |
|       2 | Temperature Controller | REX-C100                           |
|       3 | Heating Block          | V6                                 |
|       4 | Thermocouple           | K-Type                             |
|       5 | SSR                    | Solid State Relay                  |
|       6 | Power Supply           | Mean Well LRS-100-24               |
|       7 | DC Gear Motor          | 24V, 20–30W                        |
|       8 | Motor Driver           | PWM DC Controller / BTS7960        |
|       9 | Cooling Fan            | 24V                                |
|      10 | Fuse                   | 5A slow-blow                       |
|      11 | Gate Resistor          | 100Ω                               |
|      12 | Gate Pulldown          | 100kΩ                              |
|      13 | Wiring                 | 14–18 AWG power / 22–24 AWG signal |
|      14 | Filament Nozzle        | 1.75 mm / 3 mm                     |

The component specifications above are based on the project presentation.

---

## 🔋 Power Supply

The proposed main power supply is:

**Mean Well LRS-100-24**

### Specifications

* Output Voltage: **24V**
* Rated Power: **100W**
* Rated Current: approximately **4.5A**

The power supply provides power to the DC motor, cooling fan, and heating/control system according to the project design.

> **Note:** Actual power requirements should be verified against the final heater, motor, controller, and fan configuration before selecting the final power supply.

---

## 🔄 Sequence of Operation

```text
POWER ON
   ↓
Temperature Controller Starts
   ↓
Heating Block Reaches Set Temperature
   ↓
PET Strip Enters Heating Block
   ↓
PET Melts
   ↓
Molten PET Passes Through Nozzle
   ↓
Filament Is Cooled
   ↓
Filament Passes Through Sizing Guide
   ↓
Pulling Rollers Pull Filament
   ↓
Spool Motor Winds Filament
   ↓
RECYCLED PET FILAMENT
```

The project presentation summarizes the operating sequence as power supply → heating → PET melting → cooling → roller pulling → spooling.

---

## 📏 Filament Diameter

The target is to maintain approximately:

**±0.1 mm diameter tolerance**

The final diameter depends on several parameters:

* PET strip width
* PET strip thickness
* Heating temperature
* Nozzle diameter
* Pulling speed
* Cooling rate
* Spooling speed
* PET bottle characteristics

Diameter monitoring can be performed manually or upgraded to an automatic sensor-based system.

---

## 🛠️ Mechanical System

The main mechanical sections are:

### Bottle Cutter

Converts the PET bottle into a continuous strip.

### Feeding Mechanism

Guides the PET strip toward the heating block.

### Heating Block

Melts the PET strip before extrusion.

### Nozzle

Shapes the molten PET into filament.

### Cooling Mechanism

Rapidly cools the extruded filament.

### Sizing Guide

Helps maintain consistent filament diameter.

### Pulling Rollers

Pull the filament at a controlled speed.

### Spooling Mechanism

Collects and winds the finished filament.

---

## 📊 Proposed Parameters

| Parameter              | Proposed Value             |
| ---------------------- | -------------------------- |
| PET Material           | PET bottle                 |
| Processing Temperature | 250–270 °C                 |
| Filament Target        | 1.75 mm / 3 mm             |
| Pulling Speed          | 0.5–1 m/min starting range |
| Heater                 | 24V, 40W                   |
| Main Supply            | 24V, 100W                  |
| Motor                  | 24V DC geared motor        |
| Diameter Target        | ±0.1 mm                    |

## These are proposed/project-design values and should be experimentally tuned during machine operation.

## ✅ Advantages

* Low-cost and relatively simple design.
* Converts waste PET bottles into a useful product.
* Reduces plastic waste.
* Can reduce the cost of 3D-printing filament.
* Suitable for students and educational laboratories.
* Suitable for makerspaces and small workshops.
* Compact compared with large screw-extrusion systems.
* Demonstrates circular-economy principles.
* Can be further automated.

The project identifies low cost, waste conversion, reduced filament expense, sustainability, and compact construction as major advantages.

---

## ⚠️ Limitations

* Designed primarily for PET bottle strips.
* Filament diameter may be less consistent than industrial filament.
* Production speed can be lower than commercial machines.
* Clean and clear PET bottles are required.
* PET processing requires careful temperature control.
* Material properties can vary between different bottles.
* Manual diameter monitoring may be required in the basic version.

These limitations are consistent with those identified in the project presentation.

---

## 🌱 Environmental Impact

The project aims to support sustainable plastic waste management by converting discarded PET bottles into a higher-value product.

Instead of sending PET bottles directly to waste streams or lower-value recycling routes, the system attempts to convert them into material usable for additive manufacturing.

### Circular Process

```text
PET BOTTLE
    ↓
WASTE
    ↓
COLLECTION
    ↓
CLEANING
    ↓
STRIP CUTTING
    ↓
FILAMENT PRODUCTION
    ↓
3D PRINTING
    ↓
USEFUL PRODUCT
```

---

## 🎓 Applications

### 1. Low-Cost 3D Printing

Produces recycled filament for students, hobbyists, and makers.

### 2. Educational Laboratories

Can be used to demonstrate:

* Plastic recycling
* Polymer processing
* Temperature control
* Motor control
* Mechanical systems
* Sustainable manufacturing

### 3. Prototyping

Can provide recycled filament for rapid prototyping and model development.

### 4. Community Recycling

Can be used as a demonstration system for community-level PET recycling.

### 5. Makerspaces

The compact system can be used for experimental recycling and filament production.

### 6. Research

Can be used for research involving:

* Recycled PET
* Filament quality
* Diameter control
* Sustainable manufacturing
* Material properties

The project identifies educational, prototyping, community recycling, small-business, environmental, research, and portable applications.

---

## 🚀 Future Scope

Future improvements can include:

* Automatic PET strip feeding.
* Automatic filament diameter measurement.
* Closed-loop diameter control.
* Improved cooling system.
* Automatic spool synchronization.
* IoT-based temperature monitoring.
* IoT-based production monitoring.
* Real-time quality monitoring.
* Improved extrusion control.
* Higher production speed.
* Improved mechanical design.
* Larger-scale recycling capability.

The project specifically proposes automatic feeding, diameter sensors, improved cooling, IoT monitoring, and scaling for schools, makerspaces, and small industries.

---

## 📁 Repository Structure


```text
PET-Filament-Making-Machine/
│
├── README.md
│
├── Documentation/
│   ├── Project_Report.pdf
│   └── PET_Filament_Machine_Presentation.pptx
│
├── Images/
│   ├── machine.jpg
│   ├── block_diagram.png
│   ├── circuit_diagram.png
│   └── filament_sample.jpg
│
├── CAD/
│   └── mechanical_design/
│
├── Electronics/
│   ├── circuit_diagram/
│   └── PCB/
│
├── BOM/
│   └── components.xlsx
│
├── Code/
│   └── controller/
│
└── LICENSE
```

---

## 📸 Project Images


<img width="625" height="302" alt="image" src="https://github.com/user-attachments/assets/d24469c6-39a6-45d5-91ae-0d2b0b5b0cfe" />
<img width="572" height="168" alt="image" src="https://github.com/user-attachments/assets/3db827d6-58ff-4c66-8344-1a7fc1e0712a" />
<img width="568" height="422" alt="image" src="https://github.com/user-attachments/assets/3acb6969-e73b-4900-8dc1-d7a1a064aa7f" />
<img width="340" height="416" alt="image" src="https://github.com/user-attachments/assets/e293648b-da65-4161-b241-81d6b3b90190" />
<img width="603" height="481" alt="image" src="https://github.com/user-attachments/assets/0a646619-5787-4166-b2b7-1005408b6ccb" />


## 🔬 Testing

The machine should be tested by varying:

1. Heating temperature
2. PET strip width
3. Pulling speed
4. Cooling airflow
5. Nozzle diameter
6. Spooling speed

### Suggested observations

| Test | Temperature | Pull Speed |  Nozzle | Filament Diameter | Observation |
| ---- | ----------: | ---------: | ------: | ----------------: | ----------- |
| 1    |       250°C |  0.5 m/min | 1.75 mm |            1.82mm | ok          |
| 2    |       255°C |  0.5 m/min | 1.75 mm |            1.80mm | ok          |
| 3    |       260°C |  0.7 m/min | 1.75 mm |            1.76mm | excellent   |
| 4    |       265°C |  0.8 m/min | 1.75 mm |            1.74mm | good        |
| 5    |       270°C |  1.0 m/min | 1.75 mm |            1.68mm | good          |



---

## 💰 Cost Analysis


| Sr. No. | Component                      | Specification                         |  Qty. |    Cost (₹) |
| ------: | ------------------------------ | ------------------------------------- | ----: | ----------: |
|       1 | Heater Cartridge               | 24 V, 40 W                            |     2 |        ₹600 |
|       2 | Temperature Controller         | REX-C100                              |     1 |      ₹1,000 |
|       3 | SSR                            | Solid State Relay                     |     1 |        ₹500 |
|       4 | MOSFET                         | IRLZ44N / equivalent                  |     2 |        ₹100 |
|       5 | Gate Resistor & Pulldown       | 100 Ω / 100 kΩ                        | 1 set |        ₹100 |
|       6 | Power Supply                   | 24 V, 100 W                           |     1 |      ₹1,500 |
|       7 | DC Gear Motor                  | 24 V, 20–30 W                         |     1 |        ₹800 |
|       8 | Motor Driver / PWM Controller  | DC PWM / BTS7960                      |     1 |        ₹500 |
|       9 | Cooling Fan                    | 24 V                                  |     1 |        ₹300 |
|      10 | V6 Heating Block               | Heat block + heat break + heatsink    |     1 |        ₹500 |
|      11 | K-Type Thermocouple            | Temperature sensor                    |     1 |        ₹250 |
|      12 | Fuse & Protection              | Fuse, holder, etc.                    | 1 set |        ₹250 |
|      13 | Wiring & Connectors            | Power and signal wiring               | 1 set |        ₹400 |
|      14 | PET Bottle Cutter              | Strip cutting mechanism               |     1 |        ₹500 |
|      15 | Pulling Roller Mechanism       | Rollers, shafts, supports             | 1 set |      ₹1,000 |
|      16 | Spooling Mechanism             | Reel, shaft, supports                 | 1 set |        ₹600 |
|      17 | Mechanical Frame & Fabrication | Frame, brackets, fasteners, machining | 1 set |      ₹1,100 |
|         |                                | **TOTAL PROJECT COST**                |       | **₹11,000** |



---

## 🧰 Tools & Technologies

### Hardware

* REX-C100 Temperature Controller
* V6 Heating Block
* K-Type Thermocouple
* SSR
* 24V Heater Cartridge
* DC Gear Motor
* Motor Driver
* Cooling Fan
* Mean Well Power Supply
* PET Bottle Cutter
* Pulling Rollers
* Spooling Mechanism

### Manufacturing

* Mechanical fabrication
* Drilling
* Cutting
* Assembly
* Wiring
* Temperature-control setup

### Software / Documentation

* CAD tools
* Circuit-design tools
* Technical documentation

---

## 🛡️ Safety

This project involves **high-temperature heating elements and electrical power**.

Important precautions:

* Do not touch the heating block while operating.
* Use appropriate thermal protection.
* Keep wiring properly insulated.
* Use an appropriate fuse.
* Ensure proper electrical grounding where applicable.
* Keep flammable materials away from the heating system.
* Do not operate the machine unattended.
* Allow the heating system to cool before maintenance.
* Verify the REX-C100 configuration and sensor type before operation.
* Verify actual current and power requirements before finalizing the power supply.

---

## 📚 Literature & References

The project literature review includes work related to recycled PET filament, recycling methods, and extrusion-based processing.

References included in the project:

1. Anderson, I. (2017). *Mechanical properties of specimens 3D printed with virgin and recycled polylactic acid*. 3D Printing and Additive Manufacturing, 4(2), 110–115.

2. Cruz Sanchez, F. A., Boudaoud, H., Hoppe, S., & Camargo, M. (2017). *Polymer recycling in an open-source additive manufacturing context: Mechanical issues*. Additive Manufacturing, 17, 87–105.

3. Woern, A. L., & Pearce, J. M. (2018). *3D printing of recycled plastics*. Materials Today Sustainability, 1–2, 100008.

4. Tymrak, B. M., Kreiger, M., & Pearce, J. M. (2014). *Mechanical properties of components fabricated with open-source 3D printers under realistic environmental conditions*. Materials & Design, 58, 242–246.

5. Hopewell, J., Dvorak, R., & Kosior, E. (2009). *Plastics recycling: challenges and opportunities*. Philosophical Transactions of the Royal Society B: Biological Sciences, 364(1526), 2115–2126.

---

## 📌 Project Status

**Status:** Prototype / Development

### Completed / Proposed Areas

*  PET recycling concept
*  System methodology
*  Bottle-strip cutting concept
*  Heating system design
*  Temperature-control concept
*  Cooling mechanism
*  Pulling mechanism
*  Spooling mechanism
### Proposed Areas
*  Automated diameter sensing
*  Automatic feeding
*  IoT monitoring
*  Industrial-scale production



---

## 👨‍💻 Project Team

**Project:** PET Bottle Filament Making Machine

**College:** Pimpri Chinchwad College of Engineering and Research (PCCOER), Ravet, Pune

**Branch:** Electronics & Telecommunication Engineering

### Team Members

* Viraj Dubal


---

## ⭐ Project Highlights

♻️ **Waste PET → 3D Printing Filament**

🌱 Sustainable plastic recycling

💰 Low-cost approach

⚙️ Controlled heating and extrusion

🌡️ REX-C100 temperature control

❄️ Active filament cooling

🔄 Controlled pulling and spooling

🎓 Suitable for educational and maker applications

---

## 📖 Conclusion

The PET Bottle Filament Making Machine provides a low-cost approach for converting waste PET bottles into 3D-printing filament.

The system combines bottle-strip cutting, controlled heating, extrusion, cooling, filament sizing, pulling, and spooling to create a recycled filament-production workflow.

Although the prototype has limitations in production speed, diameter precision, and automation, it provides a foundation for future improvements such as automatic feeding, diameter sensing, improved cooling, and IoT-based monitoring.

The project demonstrates how engineering can be used to convert plastic waste into a useful material while supporting sustainable manufacturing and circular-economy principles.

---

## ⭐ If You Find This Project Useful

If this project helps you with your academic work, feel free to:

* ⭐ Star the repository
* 🍴 Fork the project
* 🛠️ Improve the design
* 📢 Share the project
* 🤝 Contribute improvements

**Thank you for visiting this project! ♻️**
