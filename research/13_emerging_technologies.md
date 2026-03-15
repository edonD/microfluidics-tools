# Emerging Microfluidics Technologies and Tools (2024-2026)

This document covers cutting-edge developments in microfluidics spanning AI-driven design,
organ-on-chip platforms, paper microfluidics, acoustofluidics, digital microfluidics (EWOD),
and inertial microfluidics. The focus is on tools, platforms, and commercial products that
have emerged or matured significantly in the 2024-2026 timeframe.

---

## 1. AI / ML for Microfluidic Design

### 1.1 Bayesian Optimization for Channel Geometry

Bayesian optimization (BO) using Gaussian process surrogate models has become the
leading data-efficient approach for microfluidic design. A 2025 study in *Lab on a Chip*
demonstrated that BO can find optimal mixing geometries **at least an order of magnitude
faster** than previous state-of-the-art optimization methods.

- **How it works**: A Gaussian process models the objective function (e.g., mixing
  efficiency) and an acquisition function (e.g., expected improvement) guides the search,
  balancing exploration and exploitation.
- **Key advantage**: Requires far fewer CFD evaluations than grid search or evolutionary
  algorithms --- typically 50-200 evaluations vs. thousands.
- **Reference**: [Advancing microfluidic design with machine learning: a Bayesian optimization approach](https://pubs.rsc.org/en/content/articlelanding/2025/lc/d4lc00872c) (Lab on a Chip, 2025)

### 1.2 Deep Learning for Droplet Microfluidics

Deep learning models now predict droplet generation parameters with high accuracy:

| Model / Tool | Capability | Accuracy |
|---|---|---|
| DAFD (Stanford) | Predicts droplet diameter and generation rate | 4.2-11.5% error |
| Multi-branch CNN + GAN-LGBMnet | Droplet recognition + small-dataset augmentation | Sub-second prediction |
| U-Net (menisci recognition) | Droplet shape detection in EWOD devices | High-precision contour detection |
| Deep neural networks | Flow component concentration measurement | 0.5% accuracy |

The **mu-Fluidic-LLMs** framework (2025) is notable: it transforms droplet microfluidics data
into linguistic format and feeds it to pretrained LLMs (LLAMA 3.1, DeepSeek-R1), achieving
~40% lower MAE for generation rate prediction and ~26% lower RMSE for droplet diameter
compared to standalone deep learning models.

- **Reference**: [Autonomous Droplet Microfluidic Design Framework with Large Language Models](https://pubs.acs.org/doi/10.1021/acsomega.5c06253) (ACS Omega, 2025)
- **Reference**: [Integrating AI with Droplet-Based Microfluidics](https://advanced.onlinelibrary.wiley.com/doi/10.1002/aisy.202501074) (Advanced Intelligent Systems, 2025)
- **Reference**: [Machine Vision Perspective on Droplet-Based Microfluidics](https://advanced.onlinelibrary.wiley.com/doi/10.1002/advs.202413146) (Advanced Science, 2025)

### 1.3 Physics-Informed Neural Networks (PINNs) for Microfluidics

PINNs embed governing PDEs (Navier-Stokes, convection-diffusion) directly into the neural
network loss function, enabling simulation without traditional meshing.

**Key advantages over FEM in microfluidics**:

- For electroosmotic flow (EOF): PINN achieves ~0.02% relative error vs. ~1.23% for FEM
  using the same number of sample points (20x10 grid).
- For strongly nonlinear problems (e.g., ion concentration polarization): PINNs produce
  correct physical results with sparse sample points where FEM fails entirely.
- No mesh generation required --- critical for complex 3D microfluidic geometries.

**Current applications**:
- Pressure-driven and electrokinetic flow in microchannels
- Multi-physics coupling (electroosmotic + pressure-driven + species transport)
- Fluid-structure interaction in deformable channels

**Limitations**: Training can be slow for high-Reynolds-number flows; multi-scale problems
remain challenging.

- **Reference**: [Physics-informed neural network framework for multi-physics coupling microfluidic problems](https://www.sciencedirect.com/science/article/pii/S0045793024002524) (Computers & Fluids, 2024)
- **Reference**: [Fluid flow and mass transport along a microchannel with PINNs](https://www.frontiersin.org/journals/mechanical-engineering/articles/10.3389/fmech.2025.1651334/full) (Frontiers in Mechanical Engineering, 2025)

### 1.4 Neural Network Surrogate Models Replacing CFD

U-Net convolutional neural networks have been validated as surrogate models for predicting
velocity and pressure fields in microfluidic filter designs, running orders of magnitude
faster than full CFD once trained.

**Emerging architectures (2025)**:

| Architecture | Description |
|---|---|
| **U-Net surrogates** | Predict velocity/pressure fields for microfluidic geometries |
| **MeshGraphNets (MGNs)** | Graph neural networks that encode arbitrary CFD meshes via MLP encoders and message-passing |
| **Neural Fields (MARIO)** | Handle non-parametric geometric variability through shape encoding |
| **Physics-informed multi-fidelity** | Combine low-fidelity and high-fidelity data with physics constraints |

- **Reference**: [U-Net-Based Surrogate Model for Evaluation of Microfluidic Channels](https://www.worldscientific.com/doi/10.1142/S0219876221410188) (Int. J. Computational Methods)
- **Reference**: [Accelerating CFD with Modular Surrogates](https://www.nas.nasa.gov/pubs/ams/2025/07-10-25.html) (NASA, 2025)

### 1.5 Generative AI and LLMs for Microfluidic Design

**muFluidicGenius (muFG)** --- an open-access ML-augmented design tool released via
*Science Advances* --- allows non-expert users to create functional microfluidic circuits by
specifying reservoir placement, channel connections, and desired flow rates. The system
automatically generates spatially coded maze structures implementing precise fluidic
resistances.

- Design generation: **under 10 seconds** on consumer hardware (MacBook Air)
- Experimental validation: **90% accuracy** in reproducing target flow distributions
- **Reference**: [ML-automated microfluidic circuit design](https://www.science.org/doi/10.1126/sciadv.aea7598) (Science Advances)

**GPT-4 for CAD generation**: Researchers have used GPT-4 to generate functional
microfluidic component designs (helix, valve, T-junction, serpentine) in OpenSCAD through
iterative dialogue prompting.

- **Reference**: [Utilizing ChatGPT to assist CAD design for microfluidic devices](https://pubs.rsc.org/en/content/articlelanding/2023/lc/d3lc00518f) (Lab on a Chip)

**Hybrid ML + Fluid Mechanics (February 2026)**: A new open-access tool combines ML
models with mathematical fluid mechanics to determine fluidic resistance values for desired
flow distributions, automating chip design for non-specialists.

- **Reference**: [Automating microfluidic chip design: Hybrid approach](https://phys.org/news/2026-02-automating-microfluidic-chip-hybrid-approach.html) (Phys.org, 2026)

### 1.6 AI-Driven Robotic Microfluidic Platforms

**LIBRIS** (University of Pennsylvania, 2026): A robotic microfluidic platform for automated
lipid nanoparticle formulation that produces up to **1,000 formulations per hour** --- 100x
faster than previous methods. Designed to generate systematic datasets for training
predictive AI models in a closed-loop optimization cycle.

- **Reference**: [Robotic microfluidic platform brings AI to lipid nanoparticle design](https://phys.org/news/2026-03-robotic-microfluidic-platform-ai-lipid.html) (March 2026)

### 1.7 Companies and Startups in AI-Driven Microfluidics

| Company | Focus | Notable |
|---|---|---|
| **Parallel Fluidics** | Rapid microfluidic prototyping | 3-day turnaround (10x faster) |
| **mFluiDx** | Vacuum-based microfluidics diagnostics | Novel pumping approach |
| **Corintis** (Switzerland) | Microfluidic cooling for AI chips | $24M Series A (Sept 2025); Microsoft collaboration |
| **iBioChips** (Texas) | Biosensors and lab-on-chip bioassays | Integrated sensor platforms |

---

## 2. Organ-on-Chip (OoC) Platforms and Tools

### 2.1 Market Overview

The organ-on-chip market is experiencing rapid growth, driven in part by the **FDA
Modernization Act 2.0** and the FDA's October 2025 decision to phase out compulsory
animal studies for monoclonal antibodies.

| Year | Market Size (USD) | Source |
|---|---|---|
| 2025 | $210-390 million | Various estimates |
| 2026 | $284-510 million | Projected |
| 2031 | $1.85 billion | Mordor Intelligence (29.63% CAGR) |
| 2034 | $1.99 billion | Fortune Business Insights |

### 2.2 Leading Commercial Platforms

#### Emulate, Inc.
- **Platform**: Organ-Chip (originally from Wyss Institute, Harvard)
- **Status**: Installed in 150+ labs, including 17 of the top 25 global biopharma companies
- **Chips**: Lung-Chip, Intestine-Chip, Liver-Chip, Kidney-Chip, Brain-Chip, and more
- **Key feature**: Mechanical stretching mimics breathing motions, peristalsis
- **Website**: [wyss.harvard.edu/technology/human-organs-on-chips](https://wyss.harvard.edu/technology/human-organs-on-chips/)

#### MIMETAS
- **Platform**: OrganoPlate (384-well plate format)
- **Key feature**: Membrane-free 3D tissue culture with perfusion; compatible with standard
  plate readers and microscopes
- **Recent (2025)**: New lung model integrating unidirectional flow, perfusable
  microvascular networks, and differentiated airway epithelium
- **Throughput**: Up to 96 chips per plate (high-throughput screening compatible)
- **Website**: [mimetas.com](https://www.mimetas.com/)

#### TissUse GmbH
- **Platform**: HUMIMIC Chip range
- **Key feature**: Multi-organ chips connecting 2-4 organ models
- **Application**: ADME (absorption, distribution, metabolism, excretion) modeling
- **Specialization**: Body-on-chip systems with interconnected organ compartments

#### CN Bio Innovations
- **Platform**: PhysioMimix (single-organ) and PhysioMimix Core (launched October 2025)
- **PhysioMimix Core**: All-in-one multi-organ-on-a-chip system supporting single-organ,
  multi-organ, and high-throughput configurations in a single MPS
- **Organ models**: Liver (primary focus), lung, gut, skin, and multi-organ combinations
- **Website**: [cn-bio.com](https://cn-bio.com/)

#### AlveoliX AG
- **Platform**: AXLung-on-chip
- **Key feature**: Mimics the biophysical microenvironment of the air-blood barrier,
  including mechanical stress of inspiration/expiration
- **Unique**: Breathing motion with physiological cyclic strain
- **Bio-models**: AXLung, AXGut, AXSkin
- **Website**: [alveolix.com](https://www.alveolix.com/)

#### BiomimX S.r.l.
- **Platform**: uBeat system (beating organs-on-chips)
- **Key feature**: Integrates 3D cell culture with mechanical stimulation
- **uGut model**: First Gut-on-Chip in literature to replicate human intestinal architecture
  with faecal microbiome and peristaltic-like movements
- **Website**: [biomimx.com](https://www.biomimx.com/)

#### InSphero
- **Platform**: Akura Flow (Body-on-a-Chip)
- **Status**: Beta testing commercial prototypes (as of 2025)
- **Key feature**: Interconnected 3D microtissues with controlled perfusion
- **Approach**: Scalable body-on-a-chip using hanging-drop spheroid technology

### 2.3 Multi-Organ / Body-on-Chip Systems

Multi-organ systems aim to model systemic drug ADME and organ-organ crosstalk.
As of 2025-2026, no provider offers a fully commercial body-on-a-chip solution,
but several are in advanced beta / early-access stages:

- **InSphero Akura Flow**: Beta-testing body-on-chip configuration
- **TissUse HUMIMIC**: 2-organ and 4-organ chips commercially available
- **CN Bio PhysioMimix Core**: Multi-organ configurations launched October 2025
- **Hesperos, Inc.**: Partnered with Psilera (June 2025) for multi-organ preclinical
  development of neuroplastogen compounds

**NASA AVATAR Mission** (announced 2025): Will use organ chips in space to study effects
of deep space radiation and microgravity on human health --- a significant validation of
the technology.

### 2.4 Software for Organ-on-Chip

Design and simulation tools specific to OoC remain limited. Most groups use:
- General CFD tools (COMSOL, ANSYS Fluent) for flow simulation
- Standard CAD (SolidWorks, AutoCAD) for chip geometry
- Custom Python/MATLAB scripts for data analysis
- Molecular Devices imaging platforms for high-content imaging on OoC platforms

---

## 3. Paper Microfluidics / muPADs

### 3.1 Overview

Microfluidic paper-based analytical devices (muPADs) use capillary-driven flow through
patterned paper substrates for low-cost, disposable diagnostics. Key applications include
point-of-care testing, environmental monitoring, and food safety.

### 3.2 Fabrication Methods

| Method | Mechanism | Resolution | Status (2025) |
|---|---|---|---|
| **Wax printing** | Solid ink printer deposits wax barriers; heat melts wax through paper | ~500 um | Solid ink printers discontinued (2016); thermal reflow alternatives emerging |
| **Thermal transfer printing** | Portable printer deposits wax-like barriers | ~200-500 um | Active development; portable and low-cost |
| **Inkjet printing** | UV-curable hydrophobic ink (AKD, MSQ, HSA) | ~100-300 um | Compatible with consumer printers |
| **Laser cutting** | CO2 or diode laser cuts paper channels or selectively melts wax | ~100 um | High precision; CO2 laser machines widely available |
| **Screen printing** | Wax or hydrophobic ink through screen mask | ~300 um | Low-cost batch production |
| **Spray coating** | Hydrophobic spray through stencil mask | ~500 um | Simplest method; lowest equipment cost |

**Capillary-driven wax patterning** (2025): A new technique uses capillary action of molten
wax itself to define hydrophobic barriers, eliminating the need for a printer entirely.

- **Reference**: [Distinctive Prototyping via Capillary-Driven Wax Patterning](https://pubs.acs.org/doi/10.1021/acsomega.5c06458) (ACS Omega, 2025)

**Laser-induced selective wax reflow**: A diode laser scans pre-deposited wax on filter
paper, selectively melting and penetrating wax through the paper thickness. Combines
the simplicity of wax methods with the precision of laser patterning.

### 3.3 Design Software for muPADs

**AutoPAD**: Cross-platform, open-source software for designing paper microfluidic devices.
Features include automatic zone alignment, design refactoring, and support for nearly any
paper-based device configuration.

- **Reference**: [An Open Software Platform for the Automated Design of Paper-Based Microfluidic Devices](https://www.nature.com/articles/s41598-017-16542-8) (Scientific Reports)

**Systematic 7-Step Design Procedure** (2025): A novel approach uses a State-Task Network
to map processing steps and generate process alternatives, followed by zone pattern
generation and dimensional optimization through imbibition process simulation. Validated
with glucose sensor (tear fluid) and SARS-CoV-2 ELISA sensor designs.

- **Reference**: [Product design: Microfluidic paper-based analytical device](https://www.sciencedirect.com/science/article/abs/pii/S0263876225004344) (Chemical Engineering Research and Design, 2025)

**ML-driven optimization** (2025): Machine learning cyclic optimization for paper-based
devices applied to periodontitis diagnosis, demonstrating that ML can replace trial-and-error
design of muPADs.

- **Reference**: [ML-Driven Cyclic Optimizing Strategy for Paper-Based Microfluidic Devices](https://pubs.acs.org/doi/10.1021/acssensors.5c02031) (ACS Sensors, 2025)

### 3.4 Key Challenges

- Discontinuation of Xerox ColorQube solid ink printers (2016) disrupted the dominant
  wax-printing workflow; thermal transfer and laser methods are filling the gap.
- Quantitative readout remains challenging; smartphone-based colorimetric readers are
  the primary solution.
- Flow control is limited compared to channel-based microfluidics; timing-based
  sequential delivery is the main approach.
- Reproducibility across paper batches requires careful characterization.

---

## 4. Acoustofluidics / SAW Microfluidics

### 4.1 Operating Principles

Surface acoustic wave (SAW) devices use interdigital transducers (IDTs) on piezoelectric
substrates (typically lithium niobate, LiNbO3) to generate MHz-frequency acoustic waves.
When these waves interact with fluid in a microchannel, they induce acoustic streaming
and radiation forces that can manipulate particles and cells.

**Key modes of operation**:
- **Traveling SAW (TSAW)**: Unidirectional wave for pumping and jetting
- **Standing SAW (SSAW)**: Two opposing TSAWs create pressure nodes/antinodes for
  particle trapping and sorting
- **Acoustic streaming**: Bulk fluid motion induced by wave attenuation; used for mixing

### 4.2 Recent Advances (2025)

**Reconfigurable SAW microfluidics** (Physical Review Letters, January 2025): In-situ control
of elastic wave polarization enables switching between acoustohydrodynamic (AHD) and
electrohydrodynamic (EHD) regimes on demand, allowing a single device to perform
multiple manipulation functions.

- **Reference**: [Reconfiguring SAW Microfluidics via In Situ Control of Elastic Wave Polarization](https://link.aps.org/doi/10.1103/PhysRevLett.134.037002)

**SSAW phase modulation** (2025): Efficient particle aggregation through standing SAW phase
modulation demonstrates improved control over particle positioning by dynamically adjusting
the phase relationship between opposing IDTs.

**Aerosol jet printing of SAW devices**: Direct printing of IDTs and microfluidic channels
on piezoelectric substrates, enabling rapid prototyping without cleanroom fabrication.

- **Reference**: [Aerosol jet printing of SAW microfluidic devices](https://www.nature.com/articles/s41378-023-00606-z) (Microsystems & Nanoengineering)

### 4.3 Commercial Platforms

| Company | Product | Application |
|---|---|---|
| **AcouSort** (Sweden) | Acoustic Separation Module | Cell therapy manufacturing, stem cell isolation, flow cytometry sample prep |
| **AcouSort** | AcouWash | Automated acoustic cell washing |
| **Dolomite Microfluidics** | SAW-compatible chip holders | Research-grade SAW microfluidic setups |

AcouSort's separation module uses gentle acoustic forces for label-free, contactless cell
separation, positioning itself as a replacement for centrifugation and magnetic bead-based
methods in cell therapy workflows.

### 4.4 Applications

- **Circulating tumor cell (CTC) isolation**: Acoustofluidic systems achieve up to 100%
  recovery at optimal conditions
- **Exosome isolation**: Label-free separation of extracellular vesicles from blood
- **Cell sorting**: Label-free sorting by size, density, and compressibility
- **Mixing**: Acoustic streaming enables rapid mixing in low-Reynolds-number flows

### 4.5 Design Tools

There are no widely available commercial design tools specifically for SAW microfluidic
devices. Current approaches include:

- **COMSOL Multiphysics**: Piezoelectric + acoustics + fluid dynamics modules
- **Custom FEM codes**: Often MATLAB-based for IDT design and optimization
- **Analytical models**: Nyborg streaming equations for first-order acoustic force estimation
- **Python/MATLAB scripts**: For IDT finger geometry, wavelength, and frequency calculations

### 4.6 Challenges

- Throughput limitations: Most SAW devices operate at uL/min flow rates; scaling to
  mL/min remains difficult
- Substrate cost: LiNbO3 wafers are expensive compared to PDMS or glass
- Integration: Combining SAW actuation with standard microfluidic interconnects is
  non-trivial
- Temperature effects: Acoustic energy dissipation can heat samples

---

## 5. Electrowetting / EWOD / Digital Microfluidics (DMF)

### 5.1 Operating Principles

Digital microfluidics (DMF) uses electrowetting-on-dielectric (EWOD) to manipulate
individual droplets on an array of electrodes. By sequentially activating electrodes,
droplets can be moved, merged, split, and dispensed --- all without pumps, valves, or
channels.

**Architecture**: A typical DMF device consists of:
- Bottom plate: Patterned electrode array (often on PCB)
- Dielectric layer: Parylene, SiO2, or SU-8
- Hydrophobic coating: Teflon AF or Cytop
- Top plate (optional): Ground electrode with hydrophobic coating
- Gap: 50-300 um filled with oil (silicone oil) or air

### 5.2 Commercial Platforms and Companies

#### OpenDrop (GaudiLabs, Switzerland)
- **Type**: Open-source, modular EWOD platform
- **Current version**: OpenDrop V4
- **Specifications**: 14x8 electrode array + 4 reservoirs; USB-C powered; voltage 50-260V
  (DC or AC adjustable)
- **Cost**: Available via GaudiShop for research and education
- **Recent use (2025)**: Orchestrating self-replication in artificial cells using digital
  microfluidics
- **Website**: [gaudi.ch/GaudiLabs](https://www.gaudi.ch/GaudiLabs/?page_id=392)

#### Sci-Bots (Canada)
- **Product**: DropBot --- portable, general-purpose DMF control system
- **Key feature**: Affordable, compact driving robot for EWOD electrode arrays
- **Application**: Research-grade DMF experiments with custom chip designs
- **Website**: [sci-bots.com](https://sci-bots.com/)

#### Baebies (Durham, NC, USA)
- **Product**: SEEKER --- FDA-approved DMF-based newborn screening instrument
- **Founded**: 2014 (same founders as Advanced Liquid Logic)
- **Capabilities**: Molecular, chemistry, coagulation, and immunoassays from a single drop
  of sample
- **Key feature**: No mechanical pumps or valves; fully electronic liquid handling
- **Website**: [baebies.com](https://baebies.com/)

#### PortaDrop
- **Type**: Portable DMF platform for field applications
- **Key feature**: Battery-operated, compact form factor for Lab-on-a-Chip
- **Reference**: [PortaDrop: A portable digital microfluidic platform](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0238581) (PLOS One)

### 5.3 PCB-Based Digital Microfluidics

PCB-based DMF represents a major cost reduction over microfabricated devices.
Standard PCB manufacturing processes (etching, plating, solder mask) can produce
electrode arrays at scale for pennies per device.

**Key developments (2025)**:

- **Lab-on-PCB**: Custom DMF chips designed in **Altium Designer** and commercially
  mass-manufactured in standardized PCB factories for the first time.
- **Cloud-connected PCB EWOD**: Integrated heating and sensing on PCB EWOD chips
  connected to a digital microfluidics cloud platform, enabling remote experiment control.
- **Modular PCB design**: Physically separate boards for control logic and electrodes
  connected by ribbon cables, enabling reusable controllers with disposable electrode
  cartridges.

- **Reference**: [Recent advances in Lab-on-PCB technology](https://www.nature.com/articles/s41378-025-00940-4) (Microsystems & Nanoengineering, 2025)
- **Reference**: [Integrated heating & sensing for PCB EWOD chips on a cloud platform](https://pubs.rsc.org/en/content/articlehtml/2025/lc/d5lc00507h) (Lab on a Chip, 2025)

### 5.4 DMF Design Automation

Design automation for DMF biochips is a well-established subfield of electronic design
automation (EDA). Key capabilities include:

- **Fluidic operation scheduling**: Sequencing droplet operations to minimize assay time
- **Module placement**: Assigning functional modules (mixers, detectors, heaters) to
  electrode regions
- **Droplet routing**: Path planning to avoid collisions and minimize actuation steps
- **Pin assignment**: Mapping logical electrodes to physical control pins (pin-constrained
  designs)

The textbook *Digital Microfluidic Biochips: Design Automation and Optimization* by
Chakrabarty and Xu remains a foundational reference.

- **Reference**: [Design Automation Techniques for Microfluidic Biochips](https://link.springer.com/rwe/10.1007/978-981-97-9314-3_63) (Springer, 2025 edition)

### 5.5 Deep Learning for DMF

U-Net deep learning models are being applied to recognize droplet menisci in EWOD devices,
enabling precise real-time control of droplet movement. This addresses a key challenge in
DMF: reliable feedback for closed-loop droplet actuation.

- **Reference**: [Droplet menisci recognition by deep learning for DMF applications](https://onlinelibrary.wiley.com/doi/10.1002/dro2.151) (Droplet, 2025)

---

## 6. Inertial Microfluidics

### 6.1 Operating Principles

Inertial microfluidics exploits fluid inertia at intermediate Reynolds numbers (1 < Re < 100)
to focus and separate particles/cells without external forces. In curved channels (spirals),
Dean flow creates secondary vortices that interact with inertial lift forces, causing
size-dependent particle equilibration.

**Key physics**:
- **Inertial lift force**: Drives particles away from channel walls and centerline
- **Dean drag force**: Secondary flow in curved channels sweeps particles across the
  cross-section
- **Equilibrium position**: Determined by the balance of lift and Dean drag --- larger
  particles equilibrate at different positions than smaller ones

### 6.2 Spiral Microfluidic Chips

Spiral channels are the dominant geometry for inertial separation. Trapezoidal
cross-sections are preferred over rectangular ones because they generate stronger Dean
vortices and sharper separation.

**Design parameters**:
- Channel width: 200-600 um
- Channel height: 50-180 um (trapezoidal: inner wall shorter than outer wall)
- Spiral radius: 5-15 mm
- Number of loops: 5-10
- Flow rate: 0.5-3 mL/min (high throughput compared to other microfluidic methods)

### 6.3 Commercial Platforms

| Company / Product | Technology | Application |
|---|---|---|
| **ClearCell FX** (Biolidics) | CTChip FR --- spiral Dean Flow Fractionation | CTC isolation from blood (separates ~24 um CTCs from 8-14 um blood cells) |
| **Fluigent + microfluidic ChipShop** | Commercial spiral chips with Fluigent flow control | Research cell sorting |
| **Beta Innovation** (Microfluidics Innovation Center) | Spiral chip kits | Cell size-based sorting |

### 6.4 Recent Advances (2024-2025)

**3D-stacked multi-stage inertial chips**: A 2024 design integrates a trapezoidal spiral
channel with two square serpentine channels in a vertically stacked configuration, enabling
both high-throughput input and downstream-compatible output flow rates for CTC enrichment.

- **Reference**: [3D-Stacked Multistage Inertial Microfluidic Chip for High-Throughput CTC Enrichment](https://pmc.ncbi.nlm.nih.gov/articles/PMC11030111/)

**Key advantage**: Spiral channels can process up to **1 L/min** due to their large channel
geometry, making inertial microfluidics one of the highest-throughput microfluidic separation
methods available.

### 6.5 Design Tools

No dedicated commercial design tools exist for inertial microfluidics. Current approaches:

- **COMSOL Multiphysics**: Particle tracing module with inertial lift force models
- **ANSYS Fluent**: Custom UDFs for inertial lift correlations
- **Analytical models**: Di Carlo's scaling laws for lift force (F_L ~ rho * U^2 * a^4 / D_h^2)
  and Dean number (De = Re * sqrt(D_h / 2R))
- **Python/MATLAB**: Custom scripts for equilibrium position prediction based on
  lift-to-Dean force ratio
- **OpenFOAM**: Free CFD with Lagrangian particle tracking for design exploration

---

## 7. Cross-Cutting Trends and Outlook (2025-2026)

### 7.1 Convergence of AI and Microfluidics

The most significant trend across all subfields is the integration of AI/ML at every stage:

1. **Design**: Generative models and Bayesian optimization replace manual design iteration
2. **Fabrication**: ML-optimized process parameters for 3D printing and soft lithography
3. **Operation**: Real-time feedback control using computer vision and deep learning
4. **Analysis**: Automated image analysis for droplets, cells, and assay readouts
5. **Closed-loop platforms**: Robotic systems (e.g., LIBRIS) that design, fabricate, test,
   and optimize in automated cycles

### 7.2 Regulatory Tailwinds for Organ-on-Chip

The FDA Modernization Act 2.0 and the October 2025 FDA decision on monoclonal antibodies
are creating a regulatory pull for OoC adoption. Pharmaceutical companies are actively
redirecting screening budgets to organ chips, driving commercial platform growth.

### 7.3 Democratization of Microfluidics

Several trends are lowering the barrier to entry:
- **Open-source platforms**: OpenDrop (DMF), AutoPAD (paper microfluidics), muFluidicGenius
  (circuit design), DropBot (DMF control)
- **PCB-based fabrication**: Standard PCB factories producing microfluidic devices at scale
- **AI design tools**: Non-experts can design functional chips in seconds
- **Paper microfluidics**: Sub-dollar diagnostic devices for global health

### 7.4 Key Gaps and Opportunities

| Gap | Opportunity |
|---|---|
| No unified design tool across microfluidic modalities | Integrated platform covering channel, droplet, paper, and digital microfluidics |
| Limited OoC simulation software | PINN-based organ chip simulators trained on experimental data |
| SAW device design requires expert knowledge | AI-assisted IDT design and acoustic field prediction |
| DMF routing algorithms are chip-specific | Universal DMF design automation with ML-based routing |
| Inertial microfluidics lacks rapid design tools | Surrogate models trained on particle trajectory data |
| Paper microfluidic design is empirical | Physics-based imbibition simulation integrated with ML optimization |

---

## 8. Summary Table: Tools and Platforms by Category

| Category | Tool / Platform | Type | Access |
|---|---|---|---|
| **AI Design** | muFluidicGenius (muFG) | ML circuit design | Open-access |
| **AI Design** | DAFD | Droplet flow design | Open-source (Stanford) |
| **AI Design** | LIBRIS | Robotic LNP optimization | Research (UPenn) |
| **AI Simulation** | PINNs (various) | Physics-informed surrogate | Open-source (GitHub) |
| **OoC** | Emulate Organ-Chip | Commercial OoC platform | Commercial |
| **OoC** | MIMETAS OrganoPlate | High-throughput OoC | Commercial |
| **OoC** | CN Bio PhysioMimix Core | Multi-organ MPS | Commercial (Oct 2025) |
| **OoC** | TissUse HUMIMIC | Multi-organ chip | Commercial |
| **OoC** | AlveoliX AXLung | Breathing lung chip | Commercial |
| **OoC** | BiomimX uBeat | Beating organ chips | Commercial |
| **OoC** | InSphero Akura Flow | Body-on-chip | Beta (2025) |
| **Paper** | AutoPAD | muPAD design software | Open-source |
| **Paper** | 7-Step STN method | Systematic design procedure | Published method |
| **Acousto** | AcouSort modules | Acoustic cell separation | Commercial |
| **DMF** | OpenDrop V4 | Open-source EWOD | Commercial (GaudiShop) |
| **DMF** | Sci-Bots DropBot | DMF control system | Commercial |
| **DMF** | Baebies SEEKER | FDA-approved DMF diagnostics | Commercial (FDA) |
| **Inertial** | ClearCell FX (Biolidics) | Spiral CTC isolation | Commercial |
| **Inertial** | Fluigent spiral chips | Research cell sorting | Commercial |

---

## Sources

- [Advancing microfluidic design with ML: Bayesian optimization](https://pubs.rsc.org/en/content/articlelanding/2025/lc/d4lc00872c)
- [ML-automated microfluidic circuit design (muFG)](https://www.science.org/doi/10.1126/sciadv.aea7598)
- [Automating microfluidic chip design: Hybrid ML approach (2026)](https://phys.org/news/2026-02-automating-microfluidic-chip-hybrid-approach.html)
- [Deep learning-driven microfluidic chip architecture design](https://pubs.rsc.org/en/content/articlelanding/2026/lc/d5lc01185j)
- [Autonomous Droplet Microfluidic Design with LLMs](https://pubs.acs.org/doi/10.1021/acsomega.5c06253)
- [PINN framework for multi-physics microfluidic problems](https://www.sciencedirect.com/science/article/pii/S0045793024002524)
- [Fluid flow and mass transport with PINNs](https://www.frontiersin.org/journals/mechanical-engineering/articles/10.3389/fmech.2025.1651334/full)
- [PINNs for complex fluids](https://link.springer.com/article/10.1007/s13367-025-00140-6)
- [Utilizing ChatGPT for microfluidic CAD](https://pubs.rsc.org/en/content/articlelanding/2023/lc/d3lc00518f)
- [Data-driven framework for droplet microfluidics](https://www.nature.com/articles/s41598-025-14730-5)
- [Machine vision for droplet microfluidics](https://advanced.onlinelibrary.wiley.com/doi/10.1002/advs.202413146)
- [Droplet menisci recognition by deep learning](https://onlinelibrary.wiley.com/doi/10.1002/dro2.151)
- [U-Net surrogate model for microfluidic channels](https://www.worldscientific.com/doi/10.1142/S0219876221410188)
- [Top 20 Organ-on-a-Chip Companies in 2026](https://www.scispot.com/blog/top-20-most-innovative-organ-on-a-chip-companies-in-the-world)
- [Organ-on-a-Chip Market Report 2025](https://www.globenewswire.com/news-release/2025/04/11/3060228/0/en/Organ-on-a-Chip-Global-Market-Report-2025-with-Emulate-Mimetas-TissUse-InSphero-CN-Bio-Innovations-and-more.html)
- [CN Bio organ models](https://cn-bio.com/organ-models/)
- [AlveoliX technology](https://www.alveolix.com/our-technology/)
- [BiomimX home](https://www.biomimx.com/)
- [InSphero scalable body-on-a-chip](https://insphero.com/scalable-body-on-a-chip-systems/)
- [AutoPAD: Open software for paper microfluidics](https://www.nature.com/articles/s41598-017-16542-8)
- [Capillary-driven wax patterning for muPADs](https://pubs.acs.org/doi/10.1021/acsomega.5c06458)
- [ML-driven paper microfluidic optimization](https://pubs.acs.org/doi/10.1021/acssensors.5c02031)
- [SAW-based micro/nanoparticle manipulation review](https://www.mdpi.com/1424-8220/25/5/1577)
- [Reconfigurable SAW microfluidics](https://link.aps.org/doi/10.1103/PhysRevLett.134.037002)
- [AcouSort separation module](https://acousort.com/solutions/sample-preparation-modules/separation-module/)
- [Acoustofluidics technology advances 2022-2024](https://pubs.acs.org/doi/10.1021/acs.analchem.4c06803)
- [OpenDrop V4](https://gaudishop.ch/index.php/product/opendrop-v4-digital-microfluidics-platform/)
- [Sci-Bots DMF](https://sci-bots.com/pages/dmf)
- [Baebies technology](https://baebies.com/technology/)
- [Lab-on-PCB technology advances](https://www.nature.com/articles/s41378-025-00940-4)
- [PCB EWOD cloud platform](https://pubs.rsc.org/en/content/articlehtml/2025/lc/d5lc00507h)
- [3D-stacked inertial microfluidic chip for CTCs](https://pmc.ncbi.nlm.nih.gov/articles/PMC11030111/)
- [Inertial focusing in spiral microchannels review](https://www.mdpi.com/2072-666X/15/9/1135)
- [Robotic microfluidic platform for LNP design](https://phys.org/news/2026-03-robotic-microfluidic-platform-ai-lipid.html)
- [Harnessing combinatorial microfluidics and ML](https://chemistry-europe.onlinelibrary.wiley.com/doi/10.1002/cmtd.202500069)
