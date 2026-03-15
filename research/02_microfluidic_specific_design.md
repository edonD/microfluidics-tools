# Microfluidic-Specific Design Software: Comprehensive Research

> **Research Date:** March 2026
> **Scope:** Vendor-specific microfluidic design tools, droplet/digital microfluidics tools, circuit analogy simulators, online calculators, and AI/ML-based design automation

---

## Table of Contents

1. [Vendor-Specific Design Tools](#1-vendor-specific-design-tools)
   - [Dolomite Microfluidics (Unchained Labs)](#11-dolomite-microfluidics-unchained-labs)
   - [Micronit](#12-micronit)
   - [Micralyne](#13-micralyne)
   - [Darwin Microfluidics](#14-darwin-microfluidics)
   - [FlowJEM](#15-flowjem)
2. [Microfluidic-Specific CAD and Design Platforms](#2-microfluidic-specific-cad-and-design-platforms)
   - [3DuF (CIDAR Lab)](#21-3duf-cidar-lab)
   - [MINT / Fluigi / LFR (CIDAR Lab Ecosystem)](#22-mint--fluigi--lfr-cidar-lab-ecosystem)
   - [FLUI'DEVICE (Eden Tech)](#23-fluidevice-eden-tech)
   - [Flow Circuits](#24-flow-circuits)
   - [Munich Microfluidics Toolkit (MMFT)](#25-munich-microfluidics-toolkit-mmft)
   - [Flui3d](#26-flui3d)
   - [Micado](#27-micado)
3. [AI/ML-Based Microfluidic Design Tools](#3-aiml-based-microfluidic-design-tools)
   - [DAFD (Design Automation for Fluidics Design)](#31-dafd-design-automation-for-fluidics-design)
   - [uFluidicGenius (uFG)](#32-ufluidicgenius-ufg)
   - [LLM-Based Microfluidic Design](#33-llm-based-microfluidic-design)
   - [Emerging AI/ML Approaches](#34-emerging-aiml-approaches)
4. [Droplet and Digital Microfluidics Tools](#4-droplet-and-digital-microfluidics-tools)
   - [DAFD for Droplet Generation](#41-dafd-for-droplet-generation)
   - [MMFT Droplet Simulator](#42-mmft-droplet-simulator)
   - [DropBot / Sci-Bots (Digital Microfluidics)](#43-dropbot--sci-bots-digital-microfluidics)
   - [OpenDrop (GaudiLabs)](#44-opendrop-gaudilabs)
   - [EWOD Simulation Tools](#45-ewod-simulation-tools)
5. [Circuit Analogy and Network Simulation Tools](#5-circuit-analogy-and-network-simulation-tools)
   - [SPICE-Based Microfluidic Simulation](#51-spice-based-microfluidic-simulation)
   - [Online Calculators and Apps](#52-online-calculators-and-apps)
6. [Equipment Control Software](#6-equipment-control-software)
   - [Fluigent OxyGEN](#61-fluigent-oxygen)
   - [Dolomite Flow Control Centre](#62-dolomite-flow-control-centre)
7. [Community Opinions and Real-World Feedback](#7-community-opinions-and-real-world-feedback)
8. [Comparison Matrix](#8-comparison-matrix)
9. [Recommendations by Use Case](#9-recommendations-by-use-case)
10. [Sources](#10-sources)

---

## 1. Vendor-Specific Design Tools

### 1.1 Dolomite Microfluidics (Unchained Labs)

| Attribute | Details |
|-----------|---------|
| **Vendor** | Dolomite Microfluidics (acquired by Unchained Labs; product line now discontinued) |
| **Products** | Fluidic Factory 3D Printer + Design Library; Flow Control Centre software; Telos System software |
| **Cost/License** | Proprietary/commercial; Fluidic Factory hardware was ~$30,000+; individual chip prints cost ~$1 per device |
| **OS Support** | Windows (bundled with Dolomite hardware) |
| **Learning Curve** | Low-moderate; design library approach reduces design effort |
| **Current Status** | **Discontinued** -- Unchained Labs ended support for the Dolomite product line; existing systems still operational |

**Strengths:**
- The Fluidic Factory was the first commercial 3D printer specifically for microfluidics
- Design Library provided ready-to-print chip designs with validated geometries
- Printed in FDA-approved COC (cyclic olefin copolymer) material -- translucent and chemically robust
- Enabled 3D channel geometries impossible with traditional soft lithography (3D mixers, non-rectangular chips)
- Chips cost as little as $1 to print, enabling rapid iteration
- Users could import designs from any CAD software (STL format)

**Weaknesses:**
- Product line discontinued by Unchained Labs -- no future development
- Limited resolution compared to photolithography
- Proprietary ecosystem tied to Dolomite hardware
- Design library was finite; complex custom designs still required external CAD
- COC material limitations for certain chemical/biological applications

**Who Uses It:**
- Academic labs doing rapid prototyping
- Teaching laboratories for microfluidics courses
- R&D groups needing quick design iteration

**When to Choose It:**
- Only if acquiring used/surplus equipment; not viable for new purchases given discontinuation

---

### 1.2 Micronit

| Attribute | Details |
|-----------|---------|
| **Vendor** | Micronit (Enschede, Netherlands) |
| **Type** | Design services and contract manufacturing (not a software product) |
| **Cost/License** | Custom quotes for design-to-manufacturing services |
| **Materials** | Glass, silicon, polymer, and hybrid substrates |
| **Cleanroom** | 600 m^2 cleanroom (ISO class 5-7) |

**Strengths:**
- Full-service provider: concept through high-volume manufacturing
- Deep expertise in cleanroom microfabrication across multiple material platforms
- Detailed design-for-manufacturability (DFM) support
- Strong track record with lab-on-a-chip and microfluidic products
- Partner in EU research programs (e.g., NextGenMicrofluidics)

**Weaknesses:**
- Not a software tool -- purely a service provider
- Design expertise is human-driven, not available as self-service software
- Custom pricing means costs can be unpredictable
- Longer lead times compared to in-house rapid prototyping

**Who Uses It:**
- Companies transitioning microfluidic prototypes to commercial production
- Organizations needing glass or silicon microfluidic devices
- Medical device companies requiring cleanroom-grade manufacturing

**When to Choose It:**
- When you need expert DFM guidance and commercial-scale production
- When glass or silicon substrates are required
- When regulatory-grade manufacturing quality is needed

---

### 1.3 Micralyne

| Attribute | Details |
|-----------|---------|
| **Vendor** | Micralyne (Edmonton, Canada) |
| **Type** | MEMS product development and commercial manufacturing services |
| **Cost/License** | Custom quotes for development and production |
| **Specialties** | MEMS, sensors, optical MEMS, integrated microfluidic devices |

**Strengths:**
- Can integrate sensors, MEMS, and optical MEMS elements directly into microfluidic devices
- Full custom microfluidic device capability with active micro-machined elements
- Strong semiconductor-grade fabrication facility
- Experience spanning MEMS and microfluidics domains

**Weaknesses:**
- Service provider, not a software tool
- Higher cost for integrated sensor+microfluidics devices
- Primarily serves industrial/commercial clients rather than academic researchers

**Who Uses It:**
- Life sciences companies needing integrated sensor-microfluidic devices
- Organizations requiring complex MEMS+microfluidic hybrid devices

**When to Choose It:**
- When your microfluidic device requires integrated active elements (sensors, actuators)
- When you need a single provider for both MEMS and microfluidics

---

### 1.4 Darwin Microfluidics

| Attribute | Details |
|-----------|---------|
| **Vendor** | Darwin Microfluidics (Paris, France) |
| **Type** | Equipment supplier + free online calculators and tools |
| **Cost/License** | Equipment varies; online tools are **free** |
| **OS Support** | Web-based (all platforms) |
| **Learning Curve** | Very low |

**Design and Calculation Tools Offered:**

| Tool | Purpose |
|------|---------|
| **Droplet Calculator** | Calculate droplet size/volume from diameter |
| **Pressure Converter** | Convert between atm, bar, psi, Pascal, etc. |
| **Unit Converter** | Metric/imperial conversions, including imperial fractions for tubing |
| **Syringe Pump Pressure Calculator** | Calculate incoming pressure based on linear force, channels, syringe diameter |
| **Flow Rate Calculator** | Flow rate from channel dimensions and liquid properties; outputs Reynolds number, resistance, shear stress |

**Control Software:**
- **SyringePumpPro**: Computer control of standalone/OEM syringe pumps with GUI (no command line needed)
- **Flow Control Regulation Software**: For Bartels micropumps management
- **Sensor Reader Software**: Data acquisition, real-time monitoring, feedback control

**Strengths:**
- Free, accessible online tools for quick calculations
- Covers multiple channel geometries (rectangular, circular, etc.)
- No installation needed -- browser-based
- Good for quick sanity checks during design

**Weaknesses:**
- Calculators are simple point tools, not integrated design environments
- No CAD or layout capabilities
- No simulation beyond analytical formulas
- Equipment control software tied to Darwin-sold hardware

**Who Uses It:**
- Researchers needing quick flow calculations
- Students learning microfluidics fundamentals
- Engineers checking design parameters before simulation

**When to Choose It:**
- For quick analytical calculations during early design phases
- When using Darwin Microfluidics hardware (pumps, sensors)

---

### 1.5 FlowJEM

| Attribute | Details |
|-----------|---------|
| **Vendor** | FlowJEM (polymer microfluidic technology company) |
| **Type** | Prototyping and manufacturing service (not a software product) |
| **Cost/License** | Custom quotes for prototyping services |
| **Website** | https://www.flowjem.com/ |

**Strengths:**
- Founded by microfluidic researchers and engineers
- Specializes in converting designs into working polymer microfluidic prototypes
- Bridges the gap between academic design and functional devices

**Weaknesses:**
- Does not offer design software
- Service-based model, not a self-service tool
- Limited public information about specific capabilities

**Who Uses It:**
- Academic researchers needing polymer microfluidic prototyping services
- Small companies without in-house fabrication

**When to Choose It:**
- When you have a design and need it fabricated in polymer
- When internal prototyping capability is unavailable

---

## 2. Microfluidic-Specific CAD and Design Platforms

### 2.1 3DuF (CIDAR Lab)

| Attribute | Details |
|-----------|---------|
| **Full Name** | 3DuF (3D Microfluidics) |
| **Vendor** | CIDAR Lab, Boston University |
| **Cost/License** | **Free, open source** (GitHub: CIDARLAB/3DuF) |
| **OS Support** | **Web-based** -- runs entirely in the browser (JavaScript); no installation needed |
| **Website** | https://3duf.org |
| **Publication** | Scientific Reports 9, 2019 |
| **Learning Curve** | Low-moderate |

**Strengths:**
- First fully open-source interactive microfluidic system designer
- Web-based -- no software installation or cloud infrastructure required
- Combines features from traditional CAD (Autodesk, SolidWorks) and PCB design tools
- Supports design automation algorithms out of the box
- Can reproduce designs from literature
- Provides metrics for evaluating microfluidic design complexity
- Platform for integrating diverse engineering techniques into standard design workflow
- Active development with academic backing

**Weaknesses:**
- Academic tool -- may lack polish of commercial software
- Limited component library compared to mature CAD tools
- No built-in CFD simulation (layout and design only)
- Browser-based performance can lag with very complex designs
- Community is primarily academic

**Who Uses It:**
- Academic researchers designing continuous-flow microfluidic devices
- Students learning microfluidic design principles
- Groups wanting to leverage design automation

**When to Choose It:**
- When you want a free, accessible microfluidic-specific design environment
- When integrating with CIDAR Lab's broader tool ecosystem (MINT, Fluigi, DAFD)
- For teaching and educational purposes
- When reproducing designs from published literature

---

### 2.2 MINT / Fluigi / LFR (CIDAR Lab Ecosystem)

CIDAR Lab at Boston University has developed an interconnected suite of microfluidic design tools inspired by the electronic design automation (EDA) workflow.

#### MINT (Microfluidic Netlist Language)

| Attribute | Details |
|-----------|---------|
| **Type** | Hardware description language (HDL) for microfluidics |
| **Cost/License** | **Free, open source** (GitHub: CIDARLAB/MINT, CIDARLAB/pyMINT) |
| **Analogy** | Equivalent to VHDL/Verilog in electronics |

**Description:** MINT is a text-based language for describing microfluidic hardware netlists, analogous to how VHDL/Verilog describes electronic circuits. It provides fine-grained control over design parameters and supports an ever-increasing library of components: cell traps, valves, ports, multiplexers, mixers, and transposers.

#### Fluigi (Place-and-Route Engine)

| Attribute | Details |
|-----------|---------|
| **Type** | CAD framework for microfluidic device layout |
| **Cost/License** | **Free, open source** (under development, not yet publicly downloadable) |
| **Analogy** | Equivalent to PCB place-and-route tools |

**Description:** Fluigi takes MINT netlists and performs automated placement and routing of microfluidic components on a chip. It optimizes layout of genetic circuits on microfluidic chips, generates valve control sequences, and can simulate expected chip behavior. Currently under active development.

#### LFR (Lab-on-chip Flow Representation)

| Attribute | Details |
|-----------|---------|
| **Type** | Higher-level design abstraction language |

**Description:** LFR provides a higher-level abstraction for describing microfluidic operations, which can then be compiled down to MINT for physical layout.

**Ecosystem Strengths:**
- Mirrors the proven EDA workflow (HDL -> synthesis -> place-and-route -> verification)
- First attempt at bringing full design automation to microfluidics
- Component library is extensible
- Academic publications validate the approach

**Ecosystem Weaknesses:**
- Fluigi is still under development and not publicly released
- Steep learning curve for the HDL-based approach
- Primarily oriented toward synthetic biology applications
- Smaller user community than general-purpose CAD tools
- Limited documentation for non-expert users

---

### 2.3 FLUI'DEVICE (Eden Tech)

| Attribute | Details |
|-----------|---------|
| **Vendor** | Eden Tech (Paris, France) |
| **Cost/License** | **Freemium** -- free version available; premium plans for advanced features |
| **OS Support** | **Web-based** (all platforms) |
| **Website** | https://www.fluidevice.com |
| **Learning Curve** | Very low (drag-and-drop interface) |

**Strengths:**
- Intuitive drag-and-drop interface for assembling microfluidic designs
- Growing library of pre-validated microfluidic modules: inlets, mixers, T-junctions, dividers, sorters, cell culture modules, multilevel designs
- Built-in calculators: flow rate, Reynolds number, pressure drop, hydraulic resistance
- Export to SVG, STL, and DXF formats
- Design precision down to 1 micron
- Templates of published designs available as starting points
- Block details explain how each module works and its applications
- Hydrodynamic calculations on complex geometries (not just simple channels)
- No installation required

**Weaknesses:**
- Relatively new platform -- module library still growing
- Advanced features require premium subscription
- No CFD simulation (analytical calculations only)
- Limited 3D design capabilities compared to SolidWorks/Fusion 360
- Less flexible than freeform CAD for unconventional geometries

**Who Uses It:**
- Researchers new to microfluidics who need guided design
- Engineers wanting quick prototyping without learning complex CAD
- Groups needing rapid design-to-fabrication workflows

**When to Choose It:**
- When you want the fastest path from concept to photomask/3D print file
- When you prefer a guided, component-based design approach over freeform CAD
- When built-in hydrodynamic validation is valuable
- Excellent for beginners and educational settings

---

### 2.4 Flow Circuits

| Attribute | Details |
|-----------|---------|
| **Vendor** | Flow Circuits (startup) |
| **Cost/License** | **Freemium** -- free tier available; paid plans for advanced features |
| **OS Support** | **Web-based** (all platforms) |
| **Website** | https://www.flowcircuits.com |
| **Learning Curve** | Low (2-minute setup claimed) |

**Strengths:**
- Purpose-built for system-level fluidic circuit design (not repurposed from other domains)
- Real-time simulation of flow behavior with volume-accurate calculations
- Programmable sequences for controlling pumps and valves
- Quantifies flow rates, back pressures, and error conditions
- Script export for integration with instrument control software
- Tracks fluid volumes throughout entire protocols
- Solves fluidic circuits at the system level rather than detailed CFD
- Fills gap between oversimplified spreadsheet models and heavyweight CFD tools

**Weaknesses:**
- Relatively new startup -- less proven than established tools
- System-level simulation, not component-level CFD
- Limited public information on pricing for premium tiers
- Smaller user community than COMSOL or ANSYS

**Who Uses It:**
- Microfluidic system designers and engineers
- Teams developing automated fluidic protocols
- Companies building commercial microfluidic instruments

**When to Choose It:**
- When you need system-level fluidic network design and simulation
- When rapid iteration on protocol design is more important than detailed CFD
- When you need to automate pump/valve sequences
- When bridging the gap between Visio/Excel sketches and COMSOL/SolidWorks

---

### 2.5 Munich Microfluidics Toolkit (MMFT)

| Attribute | Details |
|-----------|---------|
| **Vendor** | Chair for Design Automation, Technical University of Munich (TUM) |
| **Cost/License** | **Free, open source** (GitHub: cda-tum organization) |
| **OS Support** | Cross-platform (C++ library + Python package) |
| **Website** | https://www.cda.cit.tum.de/research/microfluidics/munich-microfluidics-toolkit/ |
| **Publication** | ICCAD 2025 |
| **Learning Curve** | Moderate (Python/C++ API) |

**Components:**

| Tool | GitHub Repo | Purpose |
|------|-------------|---------|
| **MMFT Simulator** | cda-tum/mmft-simulator | Collection of simulators for closed channel-based microfluidic devices |
| **MMFT Droplet Simulator** | cda-tum/mmft-droplet-simulator | Droplet behavior simulation using 1D analysis model |
| **MMFT Modular 1D Simulator** | cda-tum/mmft-modular-1D-simulator | Continuous flow, mixing, membranes, droplet routing |

**Design Automation Features:**
- Automated generation of meanders, gradient generators, organs-on-chip layouts
- ISO-22916-compliant routing and validation
- Interactive graphical interfaces and Python APIs
- Placement, routing, device generation tools

**Simulation Capabilities:**
- 1D analysis model suited for pre-fabrication design exploration
- Continuous flow simulation
- Instantaneous mixing modeling
- Droplet simulation and path routing
- Membrane simulation
- Pressure-driven microfluidic flow dynamics

**Strengths:**
- Comprehensive academic toolkit covering both design automation and simulation
- ISO-22916 compliance for standardized microfluidic designs
- 1D simulation enables rapid design space exploration before prototyping
- Modular architecture -- use only the components you need
- Active academic development with recent publications (2024-2025)
- Both C++ (performance) and Python (accessibility) interfaces

**Weaknesses:**
- Academic tool -- documentation may be research-oriented
- Requires programming ability (Python or C++)
- No GUI-based visual design editor (command-line/script-driven)
- 1D simulation trades accuracy for speed compared to full CFD
- Smaller community than commercial tools

**Who Uses It:**
- Academic researchers in microfluidic design automation
- Graduate students working on lab-on-a-chip design
- Groups needing rapid design iteration with simulation feedback

**When to Choose It:**
- When you need both design automation and simulation in one toolkit
- When ISO-22916 compliance is important
- When you want to explore design spaces quickly with 1D simulation
- When you are comfortable with Python/C++ scripting

---

### 2.6 Flui3d

| Attribute | Details |
|-----------|---------|
| **Type** | Open-source interactive design platform for 3D-printed microfluidics |
| **Cost/License** | **Free, open source** |
| **Publication** | Communications Engineering (Nature), 2024 |
| **Target** | Consumer-grade 3D printer fabrication |
| **Learning Curve** | Low-moderate |

**Strengths:**
- Design-for-Manufacturing (DFM) function built in -- dynamically optimizes designs for 3D printing
- Targets consumer-grade 3D printers (not specialized equipment)
- Interactive visual design interface
- Bridges design and fabrication workflows
- Recent development (2024) incorporating latest best practices

**Weaknesses:**
- Limited to 3D-printed devices (not for photolithography-based fabrication)
- Resolution constrained by consumer 3D printer capabilities
- Relatively new with small user community

**When to Choose It:**
- When designing microfluidic devices for 3D printing fabrication
- When you want integrated DFM optimization
- When using consumer-grade 3D printers

---

### 2.7 Micado

| Attribute | Details |
|-----------|---------|
| **Type** | AutoCAD plugin for microfluidic design |
| **Cost/License** | Requires AutoCAD license; Micado plugin availability varies |
| **OS Support** | Windows (AutoCAD dependency) |

**Description:** Micado is a plugin for AutoCAD specifically designed for microfluidic layout. It extends AutoCAD's capabilities with microfluidic-specific features while leveraging AutoCAD's mature drafting environment.

**Strengths:**
- Builds on AutoCAD's proven 2D drafting capabilities
- Familiar interface for AutoCAD users
- Microfluidic-specific features added to general-purpose CAD

**Weaknesses:**
- Requires expensive AutoCAD license
- Limited adoption and community support
- AutoCAD not ideal for 3D microfluidic designs
- File sizes can be large
- Poor hierarchy management noted by users on ResearchGate

---

## 3. AI/ML-Based Microfluidic Design Tools

### 3.1 DAFD (Design Automation for Fluidics Design)

| Attribute | Details |
|-----------|---------|
| **Vendor** | CIDAR Lab, Boston University |
| **Cost/License** | **Free, open source, web-based** |
| **Website** | https://dafdcad.org |
| **OS Support** | Web-based (all platforms) |
| **Publication** | Nature Communications, 2021 & 2023 |
| **Learning Curve** | Very low |

**How It Works:**
1. User specifies desired droplet diameter and generation rate
2. ML algorithms convert performance specifications into required geometry and flow rates
3. System outputs the microfluidic design needed to achieve the target performance

**Accuracy:**
- Droplet diameter prediction: mean absolute error < 10 um
- Generation rate prediction: mean absolute error < 20 Hz
- Delivers user-specified performance within 4.2% (diameter) and 11.5% (rate) of target

**Key Features:**
- **Forward prediction**: Given geometry and flow rates, predict droplet size and rate
- **Inverse design**: Given desired performance, generate required geometry
- **Tolerance analysis**: Predicts performance deviations from fabrication/testing tolerances
- **DAFD Neural Optimizer**: Automated data-to-model ML framework for custom datasets
- **Transfer learning support**: Pre-trained models can be adapted to new fluid combinations
- **Single and double emulsion support** (extended in 2023 publication)

**Strengths:**
- First ML-based microfluidic design automation tool
- Eliminates trial-and-error design iterations for droplet generators
- Accessible to non-experts via web interface
- Community can extend with custom datasets via Neural Optimizer
- Well-validated with published accuracy metrics
- Free and open source

**Weaknesses:**
- Limited to flow-focusing droplet generation geometries
- Requires training data -- accuracy depends on dataset coverage
- Cannot design arbitrary microfluidic devices (specialized for droplets)
- Does not handle complex multi-step protocols
- Accuracy varies with fluid combinations outside training data

**Who Uses It:**
- Researchers designing droplet microfluidic systems
- Groups working on emulsion generation
- Anyone needing rapid droplet generator design without CFD

**When to Choose It:**
- When designing flow-focusing droplet generators
- When you want to avoid manual design iteration
- When you need quick "what geometry gives me X-sized droplets?" answers

---

### 3.2 uFluidicGenius (uFG)

| Attribute | Details |
|-----------|---------|
| **Type** | ML-augmented microfluidic circuit design tool |
| **Cost/License** | **Open access** |
| **Publication** | Science Advances, 2024 |
| **Target Users** | Non-expert users |
| **Learning Curve** | Low |

**How It Works:**
uFG uses a hybrid algorithmic framework integrating ML models with mathematical modeling to enable non-expert users to create functional microfluidic circuits. It automatically generates spatially coded maze structures implementing precise fluidic resistances to meet target flow distributions.

**Strengths:**
- Designed explicitly for non-expert users
- Hybrid approach combines ML speed with physics-based accuracy
- Automates the complex task of resistance network design
- Generates manufacturable maze structures (not just theoretical networks)
- Published in high-impact journal with validation

**Weaknesses:**
- Focused on resistance-based flow distribution networks
- May not cover all microfluidic design scenarios
- Academic prototype -- may lack production-grade robustness
- Limited to specific microfluidic circuit topologies

**When to Choose It:**
- When you need precise flow distribution in microfluidic networks
- When you lack deep microfluidic design expertise
- When designing gradient generators or sample distribution networks

---

### 3.3 LLM-Based Microfluidic Design

| Attribute | Details |
|-----------|---------|
| **Example** | u-Fluidic-LLMs framework; LLM-based autonomous droplet design |
| **Publication** | ACS Omega, 2025-2026 |
| **Status** | Research-stage |

**Description:** Emerging research explores using large language models (LLMs) for microfluidic design tasks, including:
- Processing and feature extraction from tabular microfluidic data
- Autonomous design of droplet microfluidic systems
- Converting natural language specifications into design parameters

**Strengths:**
- Natural language interface potential
- Leverage massive pre-trained knowledge bases
- Could democratize microfluidic design for complete novices

**Weaknesses:**
- Very early stage -- not production-ready
- Accuracy and reliability not yet established for critical applications
- Hallucination risks with LLMs
- Requires significant computational resources

---

### 3.4 Emerging AI/ML Approaches

Several additional AI/ML approaches are emerging in the microfluidic design space:

- **OpenMFDA (Open Microfluidic Design Automation)**: Aims to create an open-source software ecosystem for sharing microfluidic designs with easy-to-use toolchains. Led by the University of Utah's Center of Excellence for Biomedical Microfluidics.

- **Residual Block + Fourier Enhanced Networks**: Data-driven frameworks for optimizing droplet microfluidics using advanced neural architectures (Nature Scientific Reports, 2025).

- **LIBRIS Robotic Platform**: AI-driven robotic microfluidic platform enabling high-throughput automated formulation (1,000 formulations/hour), demonstrating AI+microfluidics convergence for experimental automation.

- **Physics-Informed Neural Networks (PINNs)**: Increasingly applied to microfluidic flow prediction, combining neural network flexibility with physical constraints for more reliable predictions.

---

## 4. Droplet and Digital Microfluidics Tools

### 4.1 DAFD for Droplet Generation

See [Section 3.1](#31-dafd-design-automation-for-fluidics-design) for full details. DAFD is the primary specialized tool for automated droplet generator design, supporting both single and double emulsion configurations.

### 4.2 MMFT Droplet Simulator

| Attribute | Details |
|-----------|---------|
| **Vendor** | TU Munich, Chair for Design Automation |
| **Cost/License** | **Free, open source** (GitHub: cda-tum/mmft-droplet-simulator) |
| **Language** | C++ with Python bindings |
| **Publication** | SoftwareX, 2022; Scientific Reports, 2024 |

**Description:** Specialized simulator for droplet-based microfluidic biochips using a 1D analysis model. Particularly suited for:
- Simulating droplet behavior before fabrication
- Design space exploration for droplet-based systems
- Predicting droplet routing paths in channel networks
- Analyzing droplet-droplet interactions

**Strengths:**
- Fast 1D simulation enables rapid design iteration
- Open source and actively maintained
- Integrates with broader MMFT ecosystem
- Academic validation through publications

**Weaknesses:**
- 1D model sacrifices spatial detail for speed
- May not capture all 3D droplet dynamics
- Requires programming knowledge (Python/C++)

---

### 4.3 DropBot / Sci-Bots (Digital Microfluidics)

| Attribute | Details |
|-----------|---------|
| **Vendor** | Sci-Bots Inc. (Toronto, Canada; acquired by Blue Ocean Technologies in 2024) |
| **Cost/License** | **Open source** -- BSD-3-Clause (software), CC-BY-SA (hardware) |
| **Origin** | Wheeler Lab, University of Toronto |
| **Hardware** | DropBot v3 -- up to 120 independent channels |
| **Software** | Microdrop GUI + Arduino firmware + Python control module |
| **Publication** | Appl. Phys. Lett. 102, 193513 (2013) |

**Description:** DropBot is the most established open-source digital microfluidics (DMF) automation platform. It controls discrete droplet manipulation on electrode arrays coated with hydrophobic insulators using electrowetting-on-dielectric (EWOD) principles.

**Key Components:**
- **DropBot Hardware**: Modular control system with 120 independent electrode channels
- **Microdrop Software**: Graphical user interface for protocol design and execution
- **Plugin Architecture**: Extensible system for custom protocol methods
- **Python API**: Programmable interface for advanced automation

**Strengths:**
- Most mature open-source DMF platform
- Fully open hardware and software -- complete transparency
- Modular, extensible design with plugin support
- Active commercial support (through Sci-Bots/Blue Ocean Technologies)
- Large academic user base with published protocols
- Precise control of electrostatic driving force
- Instantaneous drop velocity measurement capability

**Weaknesses:**
- Requires custom electrode array fabrication
- Limited to DMF (EWOD-based) operations
- Hardware assembly requires electronics expertise
- Not a design tool per se -- it is a control/automation platform
- Acquisition by Blue Ocean Technologies introduces uncertainty about future direction

**Who Uses It:**
- Academic DMF researchers
- Groups automating biological assays on DMF platforms
- Labs developing point-of-care diagnostic devices

**When to Choose It:**
- When building a digital microfluidics automation system
- When you need open-source DMF control with full customizability
- When working with EWOD-based droplet manipulation

---

### 4.4 OpenDrop (GaudiLabs)

| Attribute | Details |
|-----------|---------|
| **Vendor** | GaudiLabs (community project, Hackteria.org network) |
| **Cost/License** | **Open source** |
| **Hardware** | OpenDrop V4 -- 128 electrodes, USB-C powered, Arduino-compatible |
| **Software** | Browser-based UI + Processing-based PC software |
| **Website** | https://www.gaudi.ch/OpenDrop/ |
| **Purchase** | ~$200-400 via GaudiShop |

**Description:** OpenDrop is a do-it-yourself digital microfluidics platform targeting personal/educational use. Part of the DIYBio movement, it makes EWOD-based droplet manipulation accessible to hobbyists and educators.

**Key Features:**
- PCB-based electrowetting cartridge with 128 electrodes
- Battery-operable -- no external pumps needed
- AC driving capability with optical isolation
- Modular cartridge system
- Browser-based software works on laptops, tablets, smartphones
- Reprogrammable Arduino-compatible hardware

**Strengths:**
- Extremely low cost compared to commercial DMF systems
- Portable and self-contained
- Strong community support (DIYBio, Hackteria)
- Educational value -- teaches EWOD principles hands-on
- Browser-based control -- no software installation needed

**Weaknesses:**
- Limited electrode count (128) compared to research-grade systems
- Lower precision than commercial DMF platforms
- DIY quality -- not suitable for production or clinical use
- Limited protocol complexity
- Smaller droplet volume range than DropBot

**Who Uses It:**
- Educators teaching digital microfluidics
- DIYBio hobbyists and makers
- Researchers wanting low-cost DMF experimentation

**When to Choose It:**
- For educational demonstrations of EWOD/DMF concepts
- When budget is severely constrained
- For proof-of-concept experiments before investing in research-grade systems

---

### 4.5 EWOD Simulation Tools

There are no dedicated EWOD simulation software packages. Instead, EWOD simulations are typically performed using general-purpose CFD/multiphysics tools:

| Tool | Application to EWOD |
|------|---------------------|
| **COMSOL Multiphysics** | Most commonly used; supports electrowetting physics, droplet actuation, dielectric layer optimization |
| **Flow-3D** | CFD modeling of EWOD droplet dynamics |
| **CFD-ACE+** | Commercial CFD for electrowetting simulation |
| **ANSYS Fluent** | Multiphase flow and electric field coupling for EWOD modeling |

**Key simulation parameters:** Contact angle dynamics, droplet velocity, pressure differences, dielectric layer thickness optimization (e.g., Teflon + HfO2 layers).

---

## 5. Circuit Analogy and Network Simulation Tools

### 5.1 SPICE-Based Microfluidic Simulation

**Concept:** The hydraulic-electric circuit analogy maps microfluidic elements to electronic circuit equivalents:

| Microfluidic Parameter | Electrical Analog |
|------------------------|-------------------|
| Pressure | Voltage |
| Volumetric flow rate | Current |
| Hydraulic resistance | Electrical resistance |
| Fluidic capacitance | Electrical capacitance |
| Pneumatic valve (pneumatic-FET) | Transistor (FET) |

**How It Works:**
Microfluidic channel networks are modeled as electrical circuits using Hagen-Poiseuille law (analogous to Ohm's law). The resulting circuit is solved using standard SPICE simulators, providing rapid predictions of pressure-driven laminar flow in microchannels.

**SPICE Tools Used for Microfluidics:**

| Tool | License | Notes |
|------|---------|-------|
| **LTspice** | Free (Analog Devices) | Most accessible; used for microfluidic cytometer modeling |
| **PSpice** | Commercial (Cadence) | Used for serial dilution network validation |
| **ngspice** | Free, open source | Full SPICE engine, community-supported |
| **QSPICE** | Free (Qorvo) | Modern SPICE tool with fast simulation |

**Strengths of SPICE Approach:**
- Leverages mature, well-validated simulation technology
- Extremely fast simulation compared to full CFD
- Intuitive for engineers with electronics background
- Good for network-level analysis (serial dilutions, parallel channels, gradient generators)
- Free tools available (LTspice, ngspice)
- Can model active elements (pneumatic valves as transistors)

**Weaknesses:**
- Only valid for laminar, fully-developed flow (low Reynolds number)
- Cannot capture 3D flow effects, mixing dynamics, or droplet behavior
- Requires manual mapping of geometry to circuit elements
- No standardized microfluidic component libraries for SPICE
- Cannot model diffusion, reactions, or multiphase flow
- Approximation breaks down for complex geometries

**Key Publications:**
- Oh et al., "Design of pressure-driven microfluidic networks using electric circuit analogy," Lab on a Chip, 2012
- "Modelling of microfluidics network using electric circuits," IEEE, 2015
- "Hydraulic-electric analogy for design and operation of microfluidic systems," 2023

**When to Use SPICE:**
- Early-stage network-level design of pressure-driven systems
- Serial dilution and gradient generator optimization
- Quick sanity checks before committing to CFD simulation
- When electronics engineers are transitioning to microfluidics

---

### 5.2 Online Calculators and Apps

#### Elveflow Microfluidic Calculator
| Attribute | Details |
|-----------|---------|
| **URL** | https://elveflow.com/microfluidic-calculator/ |
| **Cost** | Free |
| **Capabilities** | Flow rate, pressure, tubing resistance, wall shear stress |
| **Inputs** | Fluid viscosity, density, tubing dimensions |
| **Best For** | System-level setup planning, tubing selection |

#### Fluigent Microfluidic Calculators
| Attribute | Details |
|-----------|---------|
| **URL** | https://www.fluigent.com/resources-support/support-tools/microfluidic-calculators/ |
| **Cost** | Free |
| **Capabilities** | Flow rate to pressure conversion, resistance estimation, pump selection guidance |
| **Best For** | Choosing appropriate Fluigent hardware; quick flow/pressure estimates |

#### Darwin Microfluidics Calculators
| Attribute | Details |
|-----------|---------|
| **URL** | https://blog.darwin-microfluidics.com/resources/tools/ |
| **Cost** | Free |
| **Capabilities** | Flow rate, shear stress, Reynolds number, droplet volume, pressure conversion, syringe pump pressure |
| **Best For** | Multi-parameter quick calculations across various geometries |

#### uFluidix Pressure Drop Calculator
| Attribute | Details |
|-----------|---------|
| **URL** | https://www.ufluidix.com/microfluidic-technical-knowledgebase/pressure-drop-calculator/ |
| **Cost** | Free |
| **Capabilities** | Pressure drop estimation in microchannels |
| **Best For** | Ensuring chips will not be damaged by excessive pressure; pump selection |

#### ELEXAN Scientific Calculator
| Attribute | Details |
|-----------|---------|
| **URL** | https://elexansci.com/blog/microfluidic-resistance-and-pressure-drop-calculator/ |
| **Cost** | Free |
| **Capabilities** | Pressure drop along tubes with constant inner diameter; rectangular cross-section resistance |
| **Best For** | Tubing resistance estimation; rectangular channel pressure drops |

#### FLUI'DEVICE Built-in Calculator
| Attribute | Details |
|-----------|---------|
| **URL** | https://www.fluidevice.com |
| **Cost** | Free (basic) / Premium |
| **Capabilities** | Integrated with visual design; flow rate, pressure, Reynolds number, hydraulic resistance on complex geometries |
| **Best For** | Design-integrated calculation (not a standalone calculator) |

**Summary of Online Calculators:**

| Calculator | Flow Rate | Pressure Drop | Resistance | Shear Stress | Reynolds No. | Geometry Types |
|------------|-----------|---------------|------------|--------------|------------|----------------|
| Elveflow | Yes | Yes | Yes | Yes | No | Tubes, channels |
| Fluigent | Yes | Yes | Yes | No | No | Tubes, channels |
| Darwin | Yes | Yes | Yes | Yes | Yes | Multiple geometries |
| uFluidix | No | Yes | No | No | No | Microchannels |
| ELEXAN | No | Yes | Yes | No | No | Tubes, rectangular |
| FLUI'DEVICE | Yes | Yes | Yes | No | Yes | Complex (visual) |

---

## 6. Equipment Control Software

### 6.1 Fluigent OxyGEN

| Attribute | Details |
|-----------|---------|
| **Vendor** | Fluigent (Paris, France) |
| **Cost/License** | Included with Fluigent hardware; SDK free to download |
| **OS Support** | Windows |
| **SDK Languages** | Python, LabVIEW, C++, C#, MATLAB |

**Capabilities:**
- Unified control interface for all Fluigent instruments (pressure controllers, flow sensors, valves)
- Protocol Editor for automated microfluidic sequences with timing, loops, and conditional logic
- Protocol simulation before hardware execution
- Real-time monitoring dashboard
- Lock controls for simultaneous multi-instrument operation
- Script export for integration with custom instrument control software

**Strengths:**
- Single interface for entire Fluigent ecosystem
- Protocol simulation reduces experimental waste
- Multi-language SDK enables deep integration
- Plug-and-play with Fluigent hardware

**Weaknesses:**
- Tied to Fluigent hardware ecosystem
- Not a design or simulation tool -- purely instrument control
- Windows-only for full GUI

---

### 6.2 Dolomite Flow Control Centre

| Attribute | Details |
|-----------|---------|
| **Status** | Discontinued (with Dolomite product line) |

Pre-loaded on Telos system PCs, managed pressure-driven flow control. No longer actively developed.

---

## 7. Community Opinions and Real-World Feedback

### ResearchGate Discussions

Based on multiple ResearchGate threads ("What is best software for simulation of microfluidic?", "What's a good software for complex designs of microfluidics chips?", "Microfluidic chip design using AutoCAD?"):

**For Simulation:**
- **COMSOL Multiphysics** is the most frequently recommended tool, described as "a very good software for simulating microfluidic and multiphysic problems"
- **ANSYS Fluent** is preferred for turbulent flow cases and particle trajectory simulations
- Researchers emphasize that the choice depends on the specific physics involved

**For Design/Layout:**
- **AutoCAD** is widely used but criticized for large file sizes, poor hierarchy management, and not being designed for MEMS
- **Autodesk Fusion 360** praised as "the best program so far to do the printing after design in the same program"
- **SolidWorks** and **Fusion 360** are the most common 3D CAD tools used by microfluidic developers
- General frustration that there is no single, comprehensive microfluidic-specific design tool

**Common Pain Points Expressed by Users:**
- Steep learning curves for CFD tools (COMSOL, ANSYS)
- Gap between simple 2D layout tools and complex 3D CFD simulation
- Desire for more microfluidic-specific component libraries
- Wish for better design-to-fabrication integration
- Limited specialized tools compared to what is available for electronics (PCB) design

### General Community Sentiment

The microfluidic design tool landscape is fragmented. Most practitioners cobble together workflows from multiple tools:
1. Design in general-purpose CAD (SolidWorks, Fusion 360, AutoCAD)
2. Simulate in CFD (COMSOL, ANSYS)
3. Validate with analytical calculators (Elveflow, Fluigent, Darwin)
4. Fabricate via external services (Micronit, FlowJEM) or in-house

The emergence of microfluidic-specific tools (3DuF, FLUI'DEVICE, Flow Circuits, MMFT) is welcomed but these tools are still maturing. Academic tools (CIDAR Lab ecosystem, MMFT) are powerful but require technical sophistication. Commercial startups (Flow Circuits, FLUI'DEVICE) offer better UX but are newer and less proven.

---

## 8. Comparison Matrix

### Design Tools Comparison

| Tool | Cost | Type | Interface | Simulation | Fabrication Output | Maturity |
|------|------|------|-----------|------------|-------------------|----------|
| **3DuF** | Free/OSS | Web app | GUI (browser) | No (layout only) | Yes (export) | Moderate |
| **FLUI'DEVICE** | Freemium | Web app | Drag-and-drop | Analytical calcs | SVG, STL, DXF | Growing |
| **Flow Circuits** | Freemium | Web app | GUI | System-level sim | Script export | Early |
| **MMFT** | Free/OSS | Library | Python/C++ API | 1D simulation | Programmatic | Moderate |
| **MINT/Fluigi** | Free/OSS | CLI/API | Text-based HDL | Via Fluigi | Programmatic | In development |
| **Flui3d** | Free/OSS | Web app | GUI | DFM optimization | 3D print files | Early |
| **Micado** | Commercial | AutoCAD plugin | AutoCAD GUI | No | AutoCAD formats | Legacy |
| **DAFD** | Free/OSS | Web app | GUI | ML prediction | Geometry specs | Mature |

### AI/ML Tools Comparison

| Tool | Focus Area | ML Type | Accessibility | Validation |
|------|-----------|---------|---------------|------------|
| **DAFD** | Droplet generators | Neural networks | Web GUI | Published, <10um error |
| **uFluidicGenius** | Flow distribution networks | Hybrid ML + physics | Web | Published in Science Advances |
| **u-Fluidic-LLMs** | Tabular data analysis | LLM-based | Research prototype | Early stage |
| **MMFT (ML features)** | General microfluidics | Traditional ML | Python API | Published |

### DMF Platforms Comparison

| Platform | Electrodes | Open Source | Cost | Software | Target User |
|----------|-----------|-------------|------|----------|-------------|
| **DropBot v3** | 120 | Yes (BSD-3) | ~$5,000+ (parts) | Microdrop GUI | Researchers |
| **OpenDrop V4** | 128 | Yes | ~$200-400 | Browser-based | Educators/Hobbyists |

---

## 9. Recommendations by Use Case

### "I am new to microfluidics and need to design my first chip"
- Start with **FLUI'DEVICE** (drag-and-drop, guided, free tier)
- Use **Darwin Microfluidics calculators** for quick parameter checks
- Consider **3DuF** if you want an open-source alternative

### "I need to design a droplet generator"
- Use **DAFD** for automated ML-based design (free, web-based)
- Validate with **COMSOL** if higher fidelity is needed

### "I need system-level fluidic network design"
- Use **Flow Circuits** for system-level simulation with protocol automation
- Use **SPICE (LTspice/ngspice)** for network-level analytical modeling
- Use **uFluidicGenius** for ML-assisted resistance network design

### "I want full design automation like PCB EDA"
- Use the **CIDAR Lab ecosystem** (MINT + 3DuF + DAFD)
- Watch **Fluigi** development for future place-and-route capability
- Consider **MMFT** for combined design automation and simulation

### "I need to do digital microfluidics (EWOD)"
- Use **DropBot/Sci-Bots** for research-grade DMF automation
- Use **OpenDrop** for education and proof-of-concept
- Use **COMSOL** for EWOD physics simulation

### "I need to simulate before fabricating"
- Use **MMFT 1D Simulator** for rapid design space exploration
- Use **Flow Circuits** for system-level fluidic simulation
- Use **COMSOL Microfluidics Module** for detailed CFD (covered in separate research)
- Use **SPICE tools** for network-level analytical predictions

### "I need to go from prototype to production"
- Engage **Micronit** for glass/silicon device scale-up with DFM support
- Engage **Micralyne** if sensors/MEMS integration is needed
- Use **FlowJEM** for polymer microfluidic prototyping services

### "I have minimal budget"
- **3DuF** (free, web-based design)
- **DAFD** (free, ML-based droplet design)
- **MMFT** (free, open-source simulation)
- **LTspice/ngspice** (free SPICE simulation)
- **Online calculators** (all free)
- **OpenDrop** (~$200 for DMF hardware)

---

## 10. Sources

- [Dolomite Microfluidics Systems - Unchained Labs](https://www.unchainedlabs.com/dolomite-microfluidics-systems/)
- [Dolomite Product Line - End of Support](https://www.unchainedlabs.com/%C2%B5encapsulator-systems/)
- [Dolomite Fluidic Factory 3D Printer](https://3dprintingindustry.com/news/dolomites-fluidic-factory-3d-prints-1-microfluidic-chips-60883/)
- [Micronit - Enabling Life Changing Microfluidic Products](https://micronit.com/)
- [Micronit About Us](https://micronit.com/about-us)
- [Microfluidic Foundries - Elveflow (Micralyne details)](https://www.elveflow.com/microfluidics-research-horizon-europe/industrial-partner/microfluidic-foundries/)
- [Darwin Microfluidics Tools](https://blog.darwin-microfluidics.com/resources/tools/)
- [Darwin Microfluidics Flow Rate Calculator](https://blog.darwin-microfluidics.com/microfluidic-flow-rate-shear-stress-calculator/)
- [FlowJEM - Polymer Microfluidic Technology](https://www.flowjem.com/)
- [3DuF - CIDAR Lab](https://www.cidarlab.org/3duf)
- [3DuF GitHub Repository](https://github.com/CIDARLAB/3DuF)
- [3DuF - Scientific Reports (2019)](https://www.nature.com/articles/s41598-019-45623-z)
- [MINT GitHub Repository](https://github.com/CIDARLAB/MINT)
- [MINT Wiki](https://github.com/CIDARLAB/MINT/wiki)
- [Fluigi - CIDAR Lab](https://www.cidarlab.org/fluigi)
- [CIDAR Lab CAD Tools](https://www.cidarlab.org/uf-cad-tools)
- [CIDAR Lab Microfluidics](https://www.cidarlab.org/microfluidics)
- [FLUI'DEVICE - Eden Microfluidics](https://eden-microfluidics.com/fluidevice-device-design/)
- [FLUI'DEVICE Platform](https://www.fluidevice.com/)
- [Microfluidics Made Easy ft. FLUI'DEVICE - CADworks3D](https://cadworks3d.com/microfluidics-made-easy-ft-fluidevice/)
- [Flow Circuits](https://www.flowcircuits.com/)
- [Flow Circuits Product](https://www.flowcircuits.com/product/)
- [Flow Circuits - A Unique Microfluidics Design Platform](https://www.flowcircuits.com/blog/a-unique-microfluidics-design-platform/)
- [Munich Microfluidics Toolkit - TUM](https://www.cda.cit.tum.de/research/microfluidics/munich-microfluidics-toolkit/)
- [MMFT Simulator GitHub](https://github.com/cda-tum/mmft-simulator)
- [MMFT Droplet Simulator GitHub](https://github.com/cda-tum/mmft-droplet-simulator)
- [MMFT Modular 1D Simulator GitHub](https://github.com/cda-tum/mmft-modular-1D-simulator)
- [MMFT ICCAD 2025 Paper (PDF)](https://www.cda.cit.tum.de/files/eda/2025_iccad_munich_microfluidics_toolkit.pdf)
- [Modular and extendable 1D-simulation - Scientific Reports (2024)](https://www.nature.com/articles/s41598-024-77741-8)
- [Flui3d - Communications Engineering (2024)](https://www.nature.com/articles/s44172-024-00217-0)
- [DAFD - CIDAR Lab](https://www.cidarlab.org/dafd)
- [DAFD Web Application](https://dafdcad.org/)
- [DAFD - Nature Communications (2021)](https://www.nature.com/articles/s41467-020-20284-z)
- [DAFD Double Emulsion - Nature Communications (2023)](https://www.nature.com/articles/s41467-023-44068-3)
- [ML-automated microfluidic circuit design - Science Advances](https://www.science.org/doi/10.1126/sciadv.aea7598)
- [Autonomous Droplet Microfluidic Design with LLMs - ACS Omega](https://pubs.acs.org/doi/10.1021/acsomega.5c06253)
- [Automating microfluidic chip design - Phys.org (2026)](https://phys.org/news/2026-02-automating-microfluidic-chip-hybrid-approach.html)
- [ML-Driven Innovations in Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11674507/)
- [Machine learning for microfluidic design and control - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC9361804/)
- [Microfluidic Design Automation - University of Utah](https://mems.utah.edu/research/mfda/)
- [Sci-Bots - Digital Microfluidics](https://sci-bots.com/)
- [DropBot - University of Toronto](https://microfluidics.utoronto.ca/dropbot/)
- [DropBot v3 GitHub](https://github.com/sci-bots/dropbot-v3)
- [DropBot Paper - ResearchGate](https://www.researchgate.net/publication/256197013_DropBot_An_open-source_digital_microfluidic_control_system)
- [OpenDrop - GaudiLabs](https://www.gaudi.ch/OpenDrop/)
- [OpenDrop GitHub](https://github.com/GaudiLabs/OpenDrop)
- [OpenDrop V4 - GaudiShop](https://gaudishop.ch/index.php/product/opendrop-v4-digital-microfluidics-platform/)
- [OpenDrop Paper - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC5590459/)
- [EWOD Simulation with COMSOL - SpringerLink](https://link.springer.com/chapter/10.1007/978-981-97-1571-8_19)
- [Logic-Based DMF Simulation - Springer](https://link.springer.com/chapter/10.1007/978-3-031-78380-7_1)
- [Design of Pressure-Driven Microfluidic Networks Using Electric Circuit Analogy - Lab on a Chip (2012)](https://pubs.rsc.org/en/content/articlelanding/2012/lc/c2lc20799k)
- [Microfluidic SPICE Simulation - IEEE](https://ieeexplore.ieee.org/document/5734635/)
- [Hydraulic-electric analogy - ResearchGate](https://www.researchgate.net/publication/372041418_Hydraulic-electric_analogy_for_design_and_operation_of_microfluidic_systems)
- [LTspice - Analog Devices](https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html)
- [ngspice](https://ngspice.sourceforge.io/)
- [Elveflow Microfluidic Calculator](https://elveflow.com/microfluidic-calculator/)
- [Fluigent Microfluidic Calculators](https://www.fluigent.com/resources-support/support-tools/microfluidic-calculators/)
- [uFluidix Pressure Drop Calculator](https://www.ufluidix.com/microfluidic-technical-knowledgebase/pressure-drop-calculator/)
- [ELEXAN Scientific Calculator](https://elexansci.com/blog/microfluidic-resistance-and-pressure-drop-calculator/)
- [Fluigent Software Solutions](https://www.fluigent.com/research/software-solutions/)
- [Fluigent OxyGEN](https://www.fluigent.com/product/microfluidic-components/microfluidics-automation-tool-2/)
- [What is Microfluidic Software - Fluigent](https://www.fluigent.com/resources-support/expertise/expertise-reviews/what-is-microfluidics/software-in-microfluidics/)
- [Software for Microfluidics - Parallel Fluidics](https://www.parallelfluidics.com/landing-pages/software-for-microfluidics)
- [ResearchGate: Best Software for Simulation of Microfluidic](https://www.researchgate.net/post/What-is-best-software-for-simulation-of-microfluidic)
- [ResearchGate: Good Software for Complex Designs of Microfluidics Chips](https://www.researchgate.net/post/Whats_a_good_Software_for_complex_designs_of_microfluidics_chips)
- [Open Source Platform for 3D Printed Microfluidic Devices - Scientific Reports (2025)](https://www.nature.com/articles/s41598-025-15976-9)
- [Microfluidics Startups 2026 - SeedTable](https://www.seedtable.com/best-microfluidics-startups)
- [Di Carlo Lab Software](https://www.biomicrofluidics.com/software)
