# Advanced Microfluidic Techniques & Platforms

> Last updated: March 2026

## Pneumatic Valves (Quake Valves) & Multilayer Soft Lithography

### Overview

The Quake valve (Unger et al., Science, 2000) revolutionized microfluidics by enabling on-chip valving and pumping using multilayer PDMS devices. This technique remains the foundation of large-scale integrated microfluidics.

### How It Works

1. **Two-layer PDMS device:** Flow channel on bottom layer, control channel on top layer, separated by a thin PDMS membrane (~20-50 µm)
2. **Actuation:** Pressurize control channel (5-30 psi / 35-200 kPa) → membrane deflects → pinches off flow channel
3. **Push-down vs push-up:** Push-down geometry (control on top) is simpler. Push-up geometry (control below, rounded flow channel on top) gives better sealing.
4. **Fabrication:** Requires multilayer soft lithography with aligned PDMS layers

### Design Parameters

| Parameter | Typical Value | Notes |
|-----------|-------------|-------|
| Flow channel width | 50-300 µm | Must be narrower than control channel at crossover |
| Flow channel height | 10-30 µm | Rounded profile for push-up valves (reflow resist) |
| Control channel width | 100-500 µm | Wider than flow channel for good sealing |
| Membrane thickness | 20-50 µm | Thinner = lower actuation pressure, but more fragile |
| Actuation pressure | 5-30 psi | Higher for thicker membranes |
| Response time | <1 ms | Very fast switching |
| Valve density | Up to 1M/cm² | Theoretical; practical devices: thousands/cm² |

### Multiplexing

**Fluidic multiplexor:** A binary tree of valves that controls 2^n flow lines with only n control lines. For example:
- 4 control lines → 16 addressable channels
- 8 control lines → 256 addressable channels
- This is the "microfluidic large-scale integration" (mLSI) concept from Thorsen et al. (Science, 2002)

### Fabrication Tips for Quake Valves

1. **Rounded channels:** Use positive photoresist (AZ 50XT) and reflow at 120°C to get rounded cross-sections for push-up valves
2. **Alignment:** Use alignment marks between layers. Align under stereomicroscope.
3. **Thin membrane control:** Spin coat PDMS on control layer mold at specific rpm to control membrane thickness
4. **Partial cure:** Bond layers by partially curing bottom layer, then adding top layer and completing cure

### Who Uses This

- **Standard BioTools (formerly Fluidigm):** Commercial integrated fluidic circuits (IFCs) with thousands of valves for genomics (qPCR, single-cell sequencing)
- **Academic labs:** Massively parallel assays, cell trapping, combinatorial screening
- **Stanford Microfluidics Foundry:** Offers mLSI fabrication services

---

## Centrifugal Microfluidics (Lab-on-a-Disc)

### Overview

Uses rotation (centrifugal force) to drive fluid flow — no pumps, tubing, or external connections needed. Devices look like modified CDs/DVDs.

### Principles

| Force | Application |
|-------|------------|
| Centrifugal | Primary driving force — pushes fluid outward |
| Coriolis | Creates transverse flow for mixing in curved channels |
| Capillary | Retains fluid in chambers via capillary valves |
| Euler | Transient force during acceleration/deceleration |

### Valve Types on Lab-on-a-Disc

| Valve | Mechanism | Notes |
|-------|-----------|-------|
| **Capillary valve** | Surface tension holds liquid until centrifugal force exceeds | Burst frequency depends on channel geometry |
| **Siphon valve** | Requires priming; triggers at specific spin speed | Sequential operations |
| **Wax valve** | Melted by on-disc heater to open/close | One-time actuation |
| **Dissolvable film** | Film dissolves when contacted by liquid | Timed sequential release |
| **Laser valve** | Laser melts valve material from external unit | Programmable, precise timing |

### Commercial Platforms

| Company | Platform | Application | Status |
|---------|----------|-------------|--------|
| **Abaxis (now Zoetis)** | Piccolo Xpress | Blood chemistry analyzer | Commercial (veterinary/clinical) |
| **Gyros Protein Technologies** | Gyrolab | Immunoassays | Commercial |
| **LaMotte** | WaterLink | Water testing | Commercial |
| **SpinChip Diagnostics** | SpinIt | Point-of-care diagnostics | Commercial (Norway) |
| **Blusense Diagnostics** | ViroTrack | Rapid viral testing | Commercial (Denmark) |
| **Samsung** | Research platforms | Various | R&D |

### Fabrication Methods

1. **CNC milling** of PMMA/PC (most common for prototyping)
2. **3D printing** — SLA or DLP
3. **Injection molding** for production
4. **Hot embossing** for medium volumes
5. **Xurography** (knife cutting of adhesive films) — very low cost

### Advantages vs Limitations

| Advantages | Limitations |
|-----------|------------|
| No external pumps or connections | Requires motor/spin stand |
| Simple, self-contained devices | Limited to radial flow patterns |
| Good for point-of-care | Sequential timing can be tricky |
| Low cost per test | Lower throughput than pump-based |
| Easy sample loading | Difficult to integrate sensors |

---

## Droplet Microfluidics

### Overview

Generates discrete droplets (water-in-oil or oil-in-water) at rates of hundreds to thousands per second. Each droplet acts as an independent micro-reactor.

### Key Geometries

| Geometry | Type | Droplet Size Control | Throughput | Notes |
|----------|------|---------------------|-----------|-------|
| **T-junction** | Passive | Flow rate ratio | Medium | Simple fabrication. Shear-driven breakup. |
| **Flow-focusing** | Passive | Flow rate ratio + geometry | High | Two oil streams focus aqueous stream. Most common. |
| **Co-flow** | Passive | Flow rate ratio | Medium | Dripping regime for monodisperse droplets |
| **Step emulsification** | Passive | Geometry only | Very High | Parallelizable. Droplet size independent of flow rate. |
| **Electrospraying** | Active | Voltage | Variable | Electric field-driven |

### Key Parameters

| Parameter | Typical Range | How to Control |
|-----------|-------------|---------------|
| Droplet diameter | 10-200 µm | Channel dimensions, flow rate ratio |
| Generation frequency | 100-10,000 Hz | Total flow rate |
| Monodispersity (CV) | <2-5% | Stable pressure control, flow focusing geometry |
| Surfactant concentration | 0.5-5% w/w | Prevents coalescence. Common: Span 80, PFPE-PEG |

### Surfactants & Oils

| Oil Phase | Surfactant | Notes |
|-----------|-----------|-------|
| **HFE-7500** (fluorinated oil) | PFPE-PEG (008-Fluorosurfactant, RAN Biotechnologies) | Gold standard. Biocompatible. Expensive (~$200/100 mL). |
| **FC-40** (fluorinated oil) | PFPE-PEG | Similar to HFE-7500 |
| **Mineral oil** | Span 80 (2-5% w/w) | Cheap but less biocompatible |
| **Silicone oil** | — | Used for some applications |

### Commercial Droplet Systems

| Company | Product | Application | Approx. Price |
|---------|---------|-------------|---------------|
| **Bio-Rad** | QX200/QX600 ddPCR | Digital PCR | $50-100k (system) |
| **RainDance (now Bio-Rad)** | RainDrop | Digital PCR | Absorbed into Bio-Rad |
| **10x Genomics** | Chromium | Single-cell sequencing | $50-100k (system) |
| **Dolomite** | Droplet chips + Mitos | General droplet generation | $5-20k (starter kit) |
| **Fluigent** | RayDrop | Droplet generation nozzle | $5-15k |
| **Elveflow** | Droplet pack | OB1 + droplet chip | ~$15-25k |

---

## Inertial Microfluidics

### Overview

Uses inertial effects (Re = 1-100) in microchannels for particle/cell focusing and separation. No external fields needed — purely hydrodynamic.

### Key Geometries

| Geometry | Mechanism | Best For | Notes |
|----------|-----------|----------|-------|
| **Straight channel** | Inertial focusing (shear gradient + wall lift) | Focusing to equilibrium positions | Simple but limited separation |
| **Spiral channel** | Dean flow + inertial focusing | Size-based separation (CTCs, blood cells) | Most common for cell sorting |
| **Contraction-expansion** | Dean-like vortices | Focusing, mixing | Robust over wide Re range |
| **Pillar arrays (DLD)** | Deterministic lateral displacement | Size-based sorting | Sub-micron resolution possible |

### Commercial Inertial Devices

| Company | Product | Application |
|---------|---------|------------|
| **Vortex Biosciences** | VTX-1 | CTC isolation from blood |
| **Clearbridge BioMedics** | ClearCell FX1 | CTC enrichment |
| **Cytena (now Cellink)** | UP.SIGHT | Single-cell dispensing |
| **Spiral Biotech** | Research chips | Dean flow separation |

### Design Rules for Inertial Focusing

| Parameter | Guideline |
|-----------|----------|
| **Particle/channel ratio** | a/Dh > 0.07 (a = particle diameter, Dh = hydraulic diameter) |
| **Reynolds number** | Re = 10-100 for good focusing |
| **Dean number** | De = 1-30 for spiral separation |
| **Channel aspect ratio** | High AR (h >> w) focuses to 2 positions; Low AR focuses to 4 |
| **Spiral radius** | 5-15 mm typical, 5-10 loops |
| **Flow rate** | 0.5-5 mL/min (much higher than typical microfluidics) |

---

## Paper Microfluidics (µPADs)

### Overview

Microfluidic devices fabricated on paper — uses capillary wicking for fluid transport. Ultra-low cost ($0.01-1 per device). Ideal for point-of-care diagnostics in low-resource settings.

### Fabrication Methods

| Method | Resolution | Cost | Equipment |
|--------|-----------|------|-----------|
| **Wax printing** | ~500 µm | Very low | Standard wax printer (Xerox ColorQube) + hot plate |
| **Inkjet printing** | ~100-300 µm | Low | Modified inkjet printer |
| **Screen printing** | ~200-500 µm | Very low | Screen printing setup |
| **Laser cutting** | ~100 µm | Low-Medium | CO2 laser cutter |
| **Photolithography** | ~100 µm | Medium | SU-8 on paper |
| **Craft cutting** | ~200 µm | Very low | Silhouette/Cricut cutter |

### Paper Types

| Paper | Properties | Best For |
|-------|-----------|----------|
| **Whatman No. 1** | Standard cellulose filter paper, 11 µm pores | General µPADs |
| **Whatman 903** | Blood collection card | Blood-based assays |
| **Nitrocellulose** | Protein binding | Lateral flow assays (LFAs) |
| **Glass fiber** | High flow rate, low background | Sample pads |
| **Polyester backing** | Structural support | Multi-layer devices |

### Readout Methods

| Method | Equipment | Sensitivity | Cost |
|--------|-----------|-------------|------|
| **Visual (colorimetric)** | None / smartphone | Low-Medium | Free |
| **Smartphone camera** | Phone + app | Medium | App cost |
| **Electrochemical** | Potentiostat | High | $50-500 (portable) |
| **Fluorescence** | UV lamp + camera | High | $100-500 |

### Key Applications

- Glucose, cholesterol, liver function tests
- Infectious disease detection (HIV, malaria, COVID-19)
- Environmental monitoring (heavy metals, pH)
- Food safety testing

---

## Electrokinetic Methods

### Electrophoresis on Chip

- Capillary electrophoresis (CE) on microfluidic chips
- Gel electrophoresis on chip (Agilent Bioanalyzer)
- Free-flow electrophoresis for continuous separation

### Electroosmotic Flow (EOF)

- Driven by electric field acting on charged double layer
- Plug-like velocity profile (unlike parabolic for pressure-driven)
- Used for pumping in glass/silica channels without moving parts
- Voltage: typically 100-1000 V/cm

### Dielectrophoresis (DEP)

- Manipulation of polarizable particles in non-uniform electric field
- Positive DEP: particles move toward field maximum
- Negative DEP: particles move toward field minimum
- Used for cell sorting, trapping, characterization
- Commercial: LabSmith DEP chips, LUMICKS

### Equipment for Electrokinetics

| Equipment | Application | Approx. Cost |
|-----------|------------|--------------|
| High-voltage power supply (LabSmith HVS448) | EOF/CE | $3,000-8,000 |
| Function generator + amplifier | DEP | $2,000-5,000 |
| Agilent Bioanalyzer | CE on chip | $20,000-40,000 |
| Custom PCB electrodes | DEP arrays | $100-500 |

---

## Acoustofluidics (SAW / Bulk Acoustic Waves)

### Surface Acoustic Wave (SAW) Devices

| Feature | Details |
|---------|---------|
| **Mechanism** | Interdigitated transducers (IDTs) on piezoelectric substrate generate acoustic waves |
| **Substrate** | LiNbO₃ (lithium niobate), most common |
| **Frequency** | 10-500 MHz |
| **Applications** | Mixing, sorting, droplet manipulation, cell patterning |
| **Advantages** | Non-contact, biocompatible, label-free, precise |
| **Fabrication** | Metal lift-off on piezoelectric wafer + PDMS channel bonded on top |

### Bulk Acoustic Wave (BAW) Devices

| Feature | Details |
|---------|---------|
| **Mechanism** | Standing acoustic waves in channel create pressure nodes |
| **Frequency** | 1-10 MHz |
| **Applications** | Particle focusing, separation by size/density/compressibility |
| **Substrate** | Silicon, glass (hard materials needed for acoustic coupling) |
| **Advantages** | Strong forces, high throughput |

### Commercial Acoustofluidic Platforms

| Company | Product | Application |
|---------|---------|------------|
| **AcouSort** | AcouWash, AcouTrap | Cell washing, trapping (Sweden) |
| **Acoustic Biosystems** | BACS™ | Bulk acoustic cell sorting |
| **FloDesign Sonics** | — | Acoustic cell processing |

### Design Tools for SAW Devices

- **COMSOL:** Piezoelectric Devices + Acoustics modules (can simulate SAW + fluid coupling)
- **OnScale (now Ansys):** Cloud-based piezoelectric simulation
- **Custom MATLAB/Python:** IDT design, acoustic field calculations
