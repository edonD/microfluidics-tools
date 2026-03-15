# Open-Source Microfluidics Ecosystem

> Research date: March 2026

## Overview

The open-source microfluidics ecosystem spans design software, fabrication tools, control hardware, simulation engines, and community repositories. This document catalogs all significant projects, their maturity levels, and how they interconnect.

---

## 1. Community Platforms and Repositories

### Metafluidics (metafluidics.org)
- **Origin:** MIT Media Lab / MIT Lincoln Laboratory
- **Published:** Nature Biotechnology, 2017
- **Purpose:** Open-source, community-driven repository for fluidic device designs
- **Features:**
  - Free repository of lab-on-a-chip device designs
  - Social platform: users submit, like, comment on, and download designs
  - Designs range from simple cell sorters and fluid mixers to complex chips for ocular fluid analysis and gene synthesis
  - Includes digital design files, assembly specifications, bills of materials, and operating software
  - Open to trained scientists, hobbyists, students, and amateur makers
- **Status:** Active community platform
- **URL:** https://metafluidics.org/
- **Reference:** [Nature Biotechnology article](https://www.nature.com/articles/nbt.3873)

### GitHub Microfluidics Topic
- **URL:** https://github.com/topics/microfluidics
- **Active repositories:** 20+ with significant activity
- **Most starred:** 3DuF (81 stars), Mirheo (62 stars), Fluigent SDK (38 stars)

---

## 2. Design Software (Open Source)

### 3DuF — Interactive Microfluidic Design Editor
- **Repository:** https://github.com/CIDARLAB/3DuF
- **Stars:** 81
- **Last updated:** November 2025
- **Developer:** CIDAR Lab (Boston University)
- **License:** Open source
- **Description:** First completely open-source interactive microfluidic system designer. Browser-based (JavaScript), no cloud infrastructure needed.
- **Key Features:**
  - Parametric Component Library (PCL)
  - Functional Layer Design (FLD)
  - Component-Connection Architecture (CCA)
  - Design for Manufacturing (DFM)
  - Multi-layer support (FLOW and CONTROL layers)
  - DXF border import with auto-resizing
  - Automatic control layer generation
  - Design complexity metrics
  - Published in Scientific Reports (2019)
- **Activity:** Active development; last release November 2025

### Flui3d — 3D-Printed Microfluidic Design Platform
- **Published:** Communications Engineering (Nature), 2024
- **Description:** Open-source interactive software platform for designing microfluidic devices specifically for 3D printing
- **Key Features:**
  - Standard parameterized component library
  - Multi-layer design support
  - Design-for-Manufacturing (DFM) function for consumer-grade 3D printers
  - No specialized knowledge required
- **Reference:** [Nature Communications Engineering](https://www.nature.com/articles/s44172-024-00217-0)

### OpenMFDA — Open Microfluidic Design Automation
- **Published:** Scientific Reports, 2025
- **Description:** Automated design, verification, and manufacturing toolchain for 3D-printed microfluidic devices
- **Features:**
  - Builds on electronic design automation (EDA) principles
  - Automatic layout from component lists and connections
  - Device simulation
  - 3D CAD file generation for DLP 3D printing
- **Reference:** [Scientific Reports](https://www.nature.com/articles/s41598-025-15976-9)

### mmft-openSLAice — Open-Source Slicer for mSLA Printing
- **Repository:** https://github.com/cda-tum/mmft-openSLAice
- **Stars:** 13
- **Last updated:** February 2026
- **Developer:** CDA-TUM (Technical University of Munich)
- **Description:** Dedicated slicer for masked stereolithography 3D printing of microfluidic chips

### mmft-routing-block-channel-router
- **Repository:** https://github.com/cda-tum/mmft-routing-block-channel-router
- **Stars:** 11
- **Last updated:** November 2025
- **Description:** Design tool for microfluidic routing blocks

---

## 3. Simulation and Analysis Software

### Mirheo — Computational Microfluidics
- **Repository:** https://github.com/cselab/Mirheo
- **Stars:** 62
- **Last updated:** July 2025
- **Developer:** CSE Lab (ETH Zurich)
- **Description:** High-performance computational microfluidics simulation
- **Activity:** Active

### porousMicroTransport
- **Repository:** https://github.com/gerlero/porousMicroTransport
- **Stars:** 30
- **Last updated:** March 2026 (very active)
- **Description:** Flow and transport simulation tools for paper-based microfluidics
- **Activity:** Actively maintained

### mmft-modular-1D-simulator
- **Repository:** https://github.com/cda-tum/mmft-modular-1D-simulator
- **Stars:** 9
- **Last updated:** February 2025
- **Description:** Abstract microfluidic simulation tool (1D modular approach)

### droplet-microfluidics-lbm
- **Repository:** https://github.com/lynspica/droplet-microfluidics-lbm
- **Stars:** 17
- **Description:** Droplet dynamics modeling using lattice Boltzmann methods

### BERNAISE
- **Repository:** https://github.com/MattH688/BERNAISE
- **Stars:** 9
- **Description:** CFD modeling for droplet formation and Dean drag forces

### corpuscles
- **Repository:** https://github.com/cselab/corpuscles
- **Stars:** 9
- **Last updated:** July 2025
- **Description:** Cell and particle simulation software (ETH Zurich)

---

## 4. Hardware — Digital Microfluidics

### OpenDrop — Open Source Digital Microfluidics Platform
- **Repository:** https://github.com/GaudiLabs/OpenDrop
- **Developer:** GaudiLabs (Switzerland)
- **Current version:** V4
- **Description:** Open-source digital microfluidics bio lab using electrowetting on dielectric (EWOD) technology
- **Key Features:**
  - USB-C powered high voltage pump
  - Arduino compatible, reprogrammable
  - Adjustable voltage: 150-300V, DC or AC
  - 128 individual electrodes on PCB-based cartridge
  - True AC driving capability
  - Optical isolation
  - Modular cartridge system
  - Embedded UI with soft menu
  - Open-source PC software (Processing-based)
- **Purchase:** Available via GaudiShop (~CHF 990 for V4)
- **Applications:** Lab-on-chip automation, digital biology
- **URL:** https://www.gaudi.ch/GaudiLabs/?page_id=392

### OpenFluxl — Open Source Digital Microfluidic Device
- **Repository:** https://github.com/waagsociety/OpenFluxl
- **Developer:** Waag Society (Netherlands)
- **Description:** Open source digital microfluidic device

### microdroplet_electrowetting
- **Repository:** https://github.com/CGrassin/microdroplet_electrowetting
- **Stars:** 22
- **Description:** Platform for electrowetting experimentation with electrode arrays

---

## 5. Hardware — Pumps, Controllers, and Workstations

### Poseidon — Open Source Syringe Pumps and Microscope
- **Repository:** https://github.com/pachterlab/poseidon
- **Developer:** Pachter Lab (Caltech)
- **Published:** Scientific Reports, 2019
- **Cost:** < $400 total
- **Assembly time:** ~1 hour
- **Key Features:**
  - Up to 4 simultaneous syringe pumps
  - Integrated microscope capability
  - Raspberry Pi + Arduino + CNC shield architecture
  - Stepper motor with lead screw on linear bearings
  - GUI for Windows, Mac, Linux, Raspberry Pi
  - Single-click executables for all platforms
  - 3D printed components
  - Complete documentation: CAD files, BOM, assembly instructions, firmware
- **Design principles:** Functionality, robustness, safety, simplicity, modularity, benchmarking, documentation

### Rio Controller — Open Source Microfluidics Controller
- **Repository:** https://github.com/wenzel-lab/rio-controller
- **Stars:** 9
- **Last updated:** January 2026
- **Developer:** Wenzel Lab (Universidad Adolfo Ibanez, Chile)
- **License:** CERN-OHL-W-2.0 (hardware), GPL-3.0 (software)
- **Description:** Free and open-source microfluidics controller
- **Controls:**
  - Fast imaging
  - Gas-pressure control
  - Pressure and flow measurement with feedback control
  - Sample holders with heating and stirring
  - Temperature control (4 channels)
- **Key specs:** Fast reaction times, low-pressure fluctuations

### Open Microfluidics Workstation
- **Repository:** https://github.com/wenzel-lab/open-microfluidics-workstation
- **Developer:** Wenzel Lab
- **Description:** Modular, compact working station for microfluidic research
- **Architecture:** Raspberry Pi, Arduino, 3D printing, on-board components
- **Software:** Python-based; open/accessible design software
- **Goal:** Fully functional research-grade equipment that is modular and easily combined

### Wenzel Lab Syringe Pumps
- **Repository:** https://github.com/wenzel-lab/syringe-pumps-and-controller
- **Description:** 3D printable syringe pumps and dual controller

### Wenzel Lab Droplet Sorter (FADS)
- **Repository:** https://github.com/wenzel-lab/droplet-sorter-master
- **Description:** Open-source Fluorescence Activated Droplet Sorter (FADS)
- **Related:** FPGA controller for real-time droplet analysis (RedPitaya-based)

### Flow Microscopy Platform
- **Repository:** https://github.com/wenzel-lab/flow-microscopy-platform
- **Description:** Open hardware flow microscopy with pressure, flow, temperature control in 4 channels

---

## 6. Hardware — Comprehensive Collections

### OpenMicrofluidics
- **Repository:** https://github.com/MakerTobey/OpenMicrofluidics
- **Developer:** MakerTobey (community-driven)
- **Description:** In-progress collection of open-source hardware instrumentation for microfluidics and ultra-high throughput life science experimentation
- **Includes:**
  - Droplet imaging systems
  - Fluorescence-activated droplet sorting (FADS) systems
  - Review and testing of various open-source approaches
- **Activity:** Community-driven; ongoing contributions

---

## 7. Machine Learning and Image Analysis

### droplet_detection
- **Repository:** https://github.com/karl-gardner/droplet_detection
- **Stars:** 14
- **Description:** Deep learning detector for cell encapsulation monitoring in microfluidic droplets

### DeepLearning-SCDBiochip
- **Repository:** https://github.com/hincz-lab/DeepLearning-SCDBiochip
- **Stars:** 11
- **Description:** Deep learning integration for red blood cell classification on biochips

### molyso — Mother Machine Analysis Software
- **Repository:** https://github.com/modsim/molyso
- **Stars:** 10
- **Description:** Analysis software for mother machine (single-cell microfluidic) experiments

---

## 8. Instrument Control and Automation

### Fluigent SDK
- **Repository:** https://github.com/Fluigent/fgt-SDK
- **Stars:** 38
- **Last updated:** December 2024
- **Description:** Software Development Kit for Fluigent microfluidic instruments
- **Note:** Commercial hardware, open-source SDK

### automancer
- **Repository:** https://github.com/adaptyvbio/automancer
- **Stars:** 26
- **Description:** Software for designing and automating laboratory experiments, applicable to microfluidic workflows

### ufcs-pc
- **Repository:** https://github.com/watsaig/ufcs-pc
- **Stars:** 9
- **Description:** PC control software for microfluidics systems

---

## 9. Application-Specific Projects

### AcubeSAT Microfluidics
- **Repository:** https://github.com/AcubeSAT/microfluidics
- **Description:** Lab-on-a-chip design for multiplexed cell culturing and observation in-orbit aboard a CubeSat
- **Unique:** Space application of microfluidics; complete design schematics and fabrication procedures

### Brownian-dynamics-in-a-time-varying-force-field
- **Repository:** https://github.com/zaman13/Brownian-dynamics-in-a-time-varying-force-field
- **Stars:** 20
- **Description:** Simulation of colloidal particle motion; applicable to microfluidic particle manipulation

### lrDMS-IRED
- **Repository:** https://github.com/Hollfelder-Lab/lrDMS-IRED
- **Stars:** 10
- **Description:** Enzyme engineering workflows using ultra-high throughput microfluidics

---

## 10. 3D Printing for Microfluidics

### Key Publications and Tools

| Tool/Paper | Year | Description |
|-----------|------|-------------|
| Flui3d | 2024 | Interactive design platform for 3D-printed devices |
| OpenMFDA | 2025 | Automated design-to-manufacturing pipeline |
| mmft-openSLAice | 2025-2026 | Open-source slicer for mSLA printing of microfluidic chips |
| Open-source sensor flow cells | 2024 | 3D-printed sensor integration for temperature, EC, pH |

### Accessible Fabrication
- Processes developed requiring only domestic equipment and desktop 3D printers
- Free-to-use software reduces cost barriers
- Consumer-grade printers validated for microfluidic device fabrication

---

## 11. Open Hardware for Lab Instrumentation (Raspberry Pi-based)

A growing trend involves using Raspberry Pi single-board computers and camera modules for customizable laboratory instrumentation applicable to microfluidics:
- Strobe-enhanced microscopy
- Flow monitoring
- Temperature/pressure logging
- Image analysis pipelines

**Reference:** [PMC Article on Open Hardware for Microfluidics](https://pmc.ncbi.nlm.nih.gov/articles/PMC10605846/)

---

## 12. Ecosystem Map

```
                        OPEN SOURCE MICROFLUIDICS ECOSYSTEM
                        ===================================

    DESIGN                    FABRICATION              CONTROL & AUTOMATION
    ------                    -----------              --------------------
    3DuF (81 stars)           Metafluidics.org         Poseidon (<$400)
    Flui3d                    OpenMicrofluidics        Rio Controller
    OpenMFDA                  BlackHole Lab (DIY)      Open uFluidics Workstation
    mmft-routing              mmft-openSLAice          Fluigent SDK
                                                       automancer

    SIMULATION                DIGITAL uFLUIDICS        ML & ANALYSIS
    ----------                -----------------        -------------
    Mirheo (62 stars)         OpenDrop V4              droplet_detection
    porousMicroTransport      OpenFluxl                DeepLearning-SCDBiochip
    droplet-lbm               microdroplet_ewod        molyso
    BERNAISE
    mmft-1D-simulator

    SPECIALIZED
    -----------
    AcubeSAT (space)
    Wenzel FADS (droplet sorting)
    lrDMS-IRED (enzyme engineering)
```

---

## 13. Activity Summary (as of March 2026)

### Very Active (updated within last 6 months)
| Project | Last Update | Stars |
|---------|-------------|-------|
| porousMicroTransport | Mar 2026 | 30 |
| mmft-openSLAice | Feb 2026 | 13 |
| Rio Controller | Jan 2026 | 9 |
| 3DuF | Nov 2025 | 81 |
| mmft-routing-block | Nov 2025 | 11 |
| Mirheo | Jul 2025 | 62 |
| corpuscles | Jul 2025 | 9 |

### Moderately Active (updated within last 1-2 years)
| Project | Last Update | Stars |
|---------|-------------|-------|
| Fluigent SDK | Dec 2024 | 38 |
| lrDMS-IRED | Dec 2024 | 10 |
| Brownian dynamics | Nov 2024 | 20 |
| mmft-1D-simulator | Feb 2025 | 9 |

### Stable / Mature (less frequent updates)
| Project | Last Update | Stars |
|---------|-------------|-------|
| OpenDrop | -- | Popular |
| Poseidon | -- | Well-documented |
| automancer | Jul 2023 | 26 |
| droplet-lbm | Mar 2023 | 17 |
| ufcs-pc | Mar 2022 | 9 |

---

## 14. Getting Started Recommendations

### For Chip Design
1. Start with **3DuF** for continuous flow device design (browser-based, no install)
2. Use **Flui3d** if targeting 3D printing fabrication
3. Browse **Metafluidics.org** for existing designs to adapt

### For Building Lab Equipment
1. **Poseidon** for syringe pumps + microscope (<$400, 1-hour assembly)
2. **Rio Controller** + **Open Microfluidics Workstation** for a complete research setup
3. **OpenDrop V4** for digital microfluidics experiments

### For Simulation
1. **Mirheo** for high-performance computational microfluidics
2. **porousMicroTransport** for paper-based microfluidics
3. **mmft-modular-1D-simulator** for quick abstract simulations

### For Fabrication
1. **mmft-openSLAice** for mSLA 3D printing of chips
2. **BlackHole Lab** stations for PDMS soft lithography
3. **Metafluidics.org** for community-tested fabrication protocols

---

## Sources

- [Metafluidics - Nature Biotechnology](https://www.nature.com/articles/nbt.3873)
- [MIT News - Microfluidics for the Masses](https://news.mit.edu/2017/open-source-microfluidics-0613)
- [Metafluidics.org](https://metafluidics.org/)
- [3DuF - GitHub](https://github.com/CIDARLAB/3DuF)
- [3DuF - Scientific Reports](https://www.nature.com/articles/s41598-019-45623-z)
- [Flui3d - Communications Engineering](https://www.nature.com/articles/s44172-024-00217-0)
- [OpenMFDA - Scientific Reports 2025](https://www.nature.com/articles/s41598-025-15976-9)
- [OpenDrop - GaudiLabs](https://github.com/GaudiLabs/OpenDrop)
- [Poseidon - GitHub](https://github.com/pachterlab/poseidon)
- [Poseidon - Scientific Reports](https://www.nature.com/articles/s41598-019-48815-9)
- [Rio Controller - GitHub](https://github.com/wenzel-lab/rio-controller)
- [Open Microfluidics Workstation - GitHub](https://github.com/wenzel-lab/open-microfluidics-workstation)
- [OpenMicrofluidics - GitHub](https://github.com/MakerTobey/OpenMicrofluidics)
- [Mirheo - GitHub](https://github.com/cselab/Mirheo)
- [porousMicroTransport - GitHub](https://github.com/gerlero/porousMicroTransport)
- [GitHub Microfluidics Topic](https://github.com/topics/microfluidics)
- [Open Hardware for Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC10605846/)
- [Open-source and DIY Microfluidics - ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0925400521011928)
- [mmft-openSLAice - Scientific Reports](https://www.nature.com/articles/s41598-025-32448-2)
