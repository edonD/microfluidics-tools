# Nanotechnology and Nanofluidics: The Sub-Micron Frontier

> A comprehensive guide to nanofluidic transport, nanopore sensing, nanoscale device
> fabrication, DNA sequencing at the single-molecule level, and microfluidic nanoparticle
> synthesis -- bridging the gap between microfluidics and the nanometer world.

---

## Table of Contents

1. [Nanofluidics Fundamentals](#1-nanofluidics-fundamentals)
2. [Nanofluidic Devices](#2-nanofluidic-devices)
3. [DNA Sequencing with Nanopores](#3-dna-sequencing-with-nanopores)
4. [Nanoparticle Synthesis in Microfluidic Systems](#4-nanoparticle-synthesis-in-microfluidic-systems)
5. [Nanofabrication for Fluidics](#5-nanofabrication-for-fluidics)
6. [Cross-Cutting Themes](#6-cross-cutting-themes)
7. [Sources and Further Reading](#7-sources-and-further-reading)

---

## 1. Nanofluidics Fundamentals

### 1.1 What Is Nanofluidics?

Nanofluidics is the study and application of fluid transport in and around structures with
at least one characteristic dimension below 100 nm. At this scale, the surface-to-volume
ratio becomes so large that surface forces dominate bulk behavior, enabling phenomena that
are impossible at the microscale or macroscale. The field sits at the intersection of fluid
mechanics, electrochemistry, polymer physics, and materials science.

Key length scales that define the nanofluidic regime:

| Parameter | Typical Value | Significance |
|-----------|--------------|--------------|
| Debye length (lambda_D) | 1--100 nm (depends on ionic strength) | Electrical double layer thickness |
| Channel dimension (h) | 1--100 nm | When h ~ lambda_D, EDL overlap occurs |
| Molecular diameter | 0.2--2 nm | Continuum breakdown threshold |
| Polymer radius of gyration (R_g) | 10--1000 nm | Confinement effects on macromolecules |
| Slip length (b) | 0--80 nm (material-dependent) | Enhanced flow on hydrophobic surfaces |

### 1.2 Transport in Nanochannels (<100 nm)

#### Continuum vs. Molecular Transport

For channels wider than approximately 2 nm, the Navier-Stokes equations (with appropriate
boundary conditions and body-force terms) remain valid. Below ~2 nm, molecular dynamics
simulations become necessary because:

- Water structure becomes layered near surfaces (oscillatory density profiles).
- Hydrogen-bond networks are disrupted: entering a sub-1 nm carbon nanotube requires a
  water molecule to lose approximately two of its four bulk hydrogen bonds.
- Viscosity becomes position-dependent and can differ from bulk values by orders of
  magnitude.

#### Electroosmotic Flow (EOF) in Nanochannels

Electroosmotic flow in nanochannels differs qualitatively from its microscale counterpart.
In a microchannel, the electrical double layer (EDL) is thin compared to the channel width,
producing a plug-like velocity profile. In a nanochannel where the EDL thickness is
comparable to the channel dimension:

- The velocity profile becomes parabolic rather than plug-like.
- Flow rate depends strongly on ionic strength (which sets the Debye length).
- The Helmholtz-Smoluchowski equation breaks down and must be replaced with the full
  Poisson-Boltzmann treatment coupled to Stokes flow.

#### Enhanced Flow in Carbon Nanotubes

Carbon nanotube (CNT) interiors exhibit anomalously fast water transport -- flow rates
3--5 orders of magnitude higher than predicted by classical no-slip Hagen-Poiseuille theory.
This is attributed to:

- Nearly frictionless water-graphene interfaces (large slip lengths, 10--80 nm).
- Ordered single-file water chains in sub-nm CNTs.
- Curvature-dependent water-wall interactions.

These findings, extensively characterized in both experiments and molecular dynamics
simulations, have inspired the development of CNT-based membranes for desalination and
energy harvesting.

### 1.3 Electrical Double Layer Overlap Effects

When a nanochannel dimension h approaches 2 * lambda_D (twice the Debye length), the
electrical double layers from opposing walls overlap. This overlap has profound consequences:

#### Ion Exclusion and Enrichment

- **Co-ion exclusion (Donnan exclusion):** Ions of the same sign as the surface charge are
  partially or fully excluded from the channel. For a negatively charged silica nanochannel
  (typical surface charge density: -5 to -50 mC/m^2), anions are excluded.
- **Counterion enrichment:** Cations accumulate in the channel to maintain electroneutrality.
- **Unipolar transport:** At high overlap (h << lambda_D), the channel transports almost
  exclusively counterions, behaving as an ion-selective membrane.

#### Conductance Behavior

Nanochannel conductance shows three distinct regimes as a function of salt concentration:

1. **High concentration (c > 10 mM):** Bulk-like behavior; conductance proportional to
   concentration and channel cross-section.
2. **Intermediate concentration:** Transition region where surface charge begins to
   dominate.
3. **Low concentration (c < 0.1 mM):** Conductance saturates at a plateau value determined
   by surface charge density, independent of bulk salt concentration. This "surface-charge-
   governed" regime is a hallmark signature of nanofluidic transport.

The plateau conductance per unit channel width is given approximately by:

    G_plateau = 2 * |sigma| * mu / h

where sigma is the surface charge density, mu is the counterion mobility, and h is the
channel height.

### 1.4 Ion Selectivity and Concentration Polarization

#### Ion Selectivity

A nanochannel connecting two reservoirs of different ionic composition acts as an
ion-selective barrier. The selectivity S is defined as the ratio of counterion to total ion
flux:

- S = 1: perfect selectivity (only counterions pass) -- achieved when h << lambda_D.
- S = 0.5: no selectivity (bulk-like behavior) -- when h >> lambda_D.

Factors that increase selectivity:

- Smaller channel dimensions (higher aspect ratio channels).
- Lower ionic strength in the reservoirs.
- Higher surface charge density on channel walls.
- Surface functionalization (e.g., polyelectrolyte coatings, self-assembled monolayers).

#### Concentration Polarization (CP)

When a voltage is applied across an ion-selective nanochannel, concentration polarization
develops at the nanochannel-microchannel interfaces:

- **Enrichment zone:** Ion concentration increases on the side where counterions enter the
  nanochannel.
- **Depletion zone:** Ion concentration drops on the opposite side, potentially to near-zero
  values.

CP is exploited in several applications:

- **Preconcentration:** Analyte molecules accumulate at the enrichment zone boundary,
  achieving 10^3--10^6-fold concentration enhancement for biosensing.
- **Desalination:** The depletion zone excludes salt, producing desalted water streams.
- **Electrokinetic pumping:** CP-induced space charge generates nonlinear electroosmotic
  flows (electroosmosis of the second kind).

At high voltages, the depletion zone can trigger overlimiting current regimes involving
electroconvective instabilities -- vortex-like mixing patterns that enhance ion transport
beyond the classical diffusion-limited current.

### 1.5 Entropic Effects on Polymer and DNA Transport

When a flexible polymer (such as DNA) is confined in a channel smaller than its equilibrium
radius of gyration (R_g), its conformational entropy is reduced. This confinement has
measurable effects on transport:

#### Confinement Regimes for DNA

| Regime | Channel size (d) | Behavior |
|--------|-----------------|----------|
| Bulk (unconfined) | d >> R_g | Random coil; no confinement effects |
| De Gennes regime | p << d < R_g | Chain of blobs; extension ~ d^(-2/3) |
| Odijk regime | d < 2p (~100 nm for dsDNA) | Deflection segments; extension ~ d^(-2/3) |
| Extreme confinement | d ~ molecular width | Single-file; new physics |

Here p is the persistence length (~50 nm for double-stranded DNA).

#### Entropic Trapping

Nanofluidic devices with alternating deep and shallow regions create entropic barriers.
A coiled polymer in a deep region must partially unfold to enter a shallow constriction,
paying an entropic penalty proportional to its size. This enables:

- **Size-dependent separation:** Larger molecules, counterintuitively, cross the barrier
  faster because they have a higher probability of threading a segment into the
  constriction (more surface area in contact with the barrier entrance).
- **Entropic cages:** Femtoliter-scale chambers with ~200 nm openings that trap single DNA
  molecules while remaining permeable to small molecules such as restriction enzymes. DNA
  can be cut inside the cage, and the resulting fragments analyzed upon exit through an
  adjacent nanopore.

#### DNA Extension and Optical Mapping

When DNA is forced into a nanochannel narrower than R_g, it stretches along the channel
axis. The fractional extension depends predictably on channel dimensions, enabling direct
optical measurement of genomic distances. Companies such as BioNano Genomics (now Bionano)
have commercialized this principle for genome mapping, using nanochannel arrays with
cross-sections of ~45 x 45 nm.

---

## 2. Nanofluidic Devices

### 2.1 Nanopore Sensing

Nanopore sensing is arguably the most impactful application of nanofluidics. A single
nanometer-scale pore in a thin membrane separates two electrolyte-filled reservoirs. When
a voltage is applied, ions flow through the pore, producing a measurable current. As a
molecule (DNA, protein, polymer) translocates through the pore, it partially blocks the
current, producing a characteristic signal.

#### Biological Nanopores

Biological nanopores are protein channels inserted into lipid bilayers:

| Nanopore | Pore Diameter | Source | Key Features |
|----------|--------------|--------|--------------|
| alpha-Hemolysin (aHL) | ~1.4 nm (constriction) | *S. aureus* | First nanopore used for DNA sensing; well-characterized |
| MspA | ~1.2 nm (constriction) | *M. smegmatis* | Shorter constriction zone; better spatial resolution |
| CsgG | ~0.9 nm | *E. coli* | Basis for Oxford Nanopore's R9 pore; optimized for sequencing |
| Aerolysin | ~1.0 nm | *A. hydrophila* | Excellent for short peptide sensing |
| FraC | ~1.5 nm (variable) | Sea anemone | Tunable size; used for protein fingerprinting |

Advantages: atomic-level reproducibility, well-defined geometry, amenable to genetic
engineering for custom modifications.

Limitations: fragile lipid bilayer support, limited temperature range, sensitivity to pH
and detergent.

#### Solid-State Nanopores

Solid-state nanopores are fabricated in thin inorganic membranes (SiN_x, SiO_2, HfO_2,
MoS_2, graphene):

| Material | Typical Thickness | Fabrication Method | Advantages |
|----------|------------------|-------------------|------------|
| SiN_x | 5--30 nm | TEM drilling, FIB, e-beam | Robust; tunable size; well-established |
| SiO_2 | 5--20 nm | HF etch + TEM | Chemically modifiable surface |
| Graphene | 0.34 nm (monolayer) | TEM/e-beam punch | Ultimate spatial resolution; single-base |
| MoS_2 | 0.65 nm (monolayer) | Electrochemical etch | Better signal-to-noise than graphene |
| HfO_2 | 5--15 nm | ALD + TEM drilling | Low noise; high dielectric constant |

Advantages: mechanically robust, tunable diameter (sub-nm to 100+ nm), compatible with
standard microfabrication, operable over wide temperature/pH/solvent ranges.

Limitations: less reproducible pore geometry than biological pores, higher 1/f noise,
surface charge effects complicate signal interpretation.

#### Hybrid Approaches

Recent work combines biological and solid-state nanopores -- inserting protein pores into
solid-state nanopores or using DNA origami structures as size-selective adapters within
larger solid-state pores. These hybrids aim to combine the atomic precision of biology with
the robustness of solid-state platforms.

### 2.2 Nanochannel Arrays for Molecular Sieving

Parallel arrays of nanochannels with precisely controlled dimensions enable size-based
separation of macromolecules:

- **Anisotropic nanofilter arrays (ANA):** Periodic arrays of deep wells connected by
  shallow slits (nano-gaps). Molecules are separated by their ability to cross the
  entropic barriers at the deep-to-shallow transitions. Used to separate proteins (20--200
  kDa) and DNA (1--100 kbp) with resolution comparable to gel electrophoresis but in
  seconds rather than hours.

- **Ordered nanopore membranes:** Track-etched polymer membranes or anodic aluminum oxide
  (AAO) with uniform pore diameters (10--200 nm). Used for size-selective filtration of
  proteins, viruses, and nanoparticles.

- **Nanochannel arrays for DNA linearization:** Arrays of channels with 30--100 nm
  cross-sections stretch DNA molecules for optical mapping, enabling direct visualization
  of sequence-specific labels along the genome.

### 2.3 Nanofluidic Diodes and Transistors

By analogy with semiconductor electronics, nanofluidic channels can function as ionic
circuit elements:

#### Nanofluidic Diodes

A nanofluidic diode rectifies ionic current -- conducting preferentially in one direction.
Rectification arises from asymmetry in the channel, which can be:

- **Geometric asymmetry:** Conical nanopores (wide base, narrow tip) create asymmetric
  ion concentration profiles under opposite voltage polarities.
- **Charge asymmetry:** Channels with different surface charges on opposing halves
  (e.g., positive and negative) produce bipolar junctions analogous to p-n diodes.
- **Chemical asymmetry:** Asymmetric surface functionalization (e.g., one end modified with
  polyelectrolyte, the other bare).

Rectification ratios of 100--1000 have been demonstrated. Applications include ionic
logic circuits, energy harvesting from salinity gradients, and sensing.

A notable 2025 advance reported nanofluidic diodes fabricated by confining a spirocyclic
fluorescein derivative within asymmetric track-etched nanopores, creating pH-gated diodes
with adjustable surface chemistry for applications in food safety sensing.

#### Nanofluidic Transistors

A nanofluidic transistor uses a gate electrode to modulate ionic current through a
nanochannel, analogous to a field-effect transistor (FET):

- A metal or polysilicon gate is fabricated on top of (or embedded in) a nanochannel wall.
- Applying a gate voltage modulates the surface charge and thus the ion selectivity and
  conductance.
- Field-effect reconfigurable nanofluidic diodes use asymmetrically placed gates or dual
  split-gates, where forward/reverse directions and degrees of rectification can be
  regulated by gate voltages.

Demonstrated functionalities include ionic switching (on/off ratios > 100), ionic
amplification, and ionic logic gates (AND, OR, NOT). These devices represent the foundation
of "iontronics" -- circuits that process information using ions rather than electrons.

### 2.4 Single-Molecule Detection in Nanochannels

Nanochannels provide natural confinement volumes (attoliter to femtoliter) that enable
detection of individual molecules:

#### Fluorescence-Based Detection

- **Zero-mode waveguides (ZMWs):** Nanoscale apertures (50--200 nm diameter, ~100 nm deep)
  in a metal film on glass. The aperture is below the diffraction limit of visible light,
  so only fluorophores within the bottom 20--30 nm are excited. Originally developed by
  Pacific Biosciences for single-molecule real-time (SMRT) sequencing.

- **Nanochannel-confined fluorescence microscopy:** DNA molecules extended in nanochannels
  are imaged with fluorescence microscopy. Sequence-specific fluorescent labels appear as
  a barcode pattern along the stretched molecule.

#### Electrical Detection

- **Resistive-pulse sensing:** A molecule translocating through a nanopore or nanochannel
  produces a transient drop in ionic current. The amplitude and duration of the "pulse"
  encode the molecule's size, charge, and conformation.

- **Tunneling detection:** Electrodes separated by a 1--2 nm gap across a nanochannel can
  measure quantum tunneling current through individual nucleotides, potentially enabling
  electronic DNA sequencing without the need for enzymes.

- **Field-effect detection:** A nanowire or nanotube FET adjacent to a nanofluidic channel
  detects changes in local charge as molecules pass by -- label-free and in real time.

### 2.5 Two-Dimensional Material Nanofluidics

Two-dimensional (2D) materials -- graphene, MoS_2, hexagonal boron nitride (hBN), MXenes --
have emerged as a transformative platform for nanofluidic devices:

- **Angstrom-scale channels:** Stacking 2D material layers with atomic-scale spacers
  creates channels with heights of 3--10 angstroms, enabling study of water and ion
  transport under extreme confinement.
- **Atomically thin membranes:** Single-layer graphene or MoS_2 membranes with individual
  nanopores provide the ultimate spatial resolution for molecular sensing.
- **Photothermoelectric response:** 2D materials enable light-driven nanofluidic transport
  and energy harvesting from osmotic gradients.
- **Lamellar membranes:** Stacked graphene oxide or MXene nanosheets form laminar
  nanofluidic networks with tunable interlayer spacing for ion sieving and desalination.

---

## 3. DNA Sequencing with Nanopores

### 3.1 Principles of Nanopore Sequencing

Nanopore sequencing determines DNA (or RNA) sequence by measuring changes in ionic current
as a nucleic acid strand passes through a nanometer-scale pore. Each nucleotide (or short
k-mer) partially obstructs the pore to a different degree, producing a characteristic
current level. A trained base-caller algorithm (typically a neural network) converts the
raw current signal into a nucleotide sequence.

Key parameters:

| Parameter | Typical Value | Impact |
|-----------|--------------|--------|
| Pore constriction length | 0.5--5 nm | Determines how many bases influence current simultaneously |
| Translocation speed | 200--450 bases/s (enzyme-controlled) | Faster = lower accuracy; slower = higher accuracy |
| Current levels | 4--6 distinguishable levels per k-mer | Resolution of base calling |
| Read length | No inherent limit; >4 Mb demonstrated | Enables spanning repetitive regions, structural variants |
| Raw accuracy | ~99% (R10.4.1 chemistry, Q20+) | Approaching short-read sequencer accuracy |

### 3.2 Oxford Nanopore Technology

Oxford Nanopore Technologies (ONT) is the leading commercial nanopore sequencing platform.
Their approach uses a motor enzyme (helicase) to ratchet single-stranded DNA through a
biological nanopore one base at a time while measuring ionic current.

#### Evolution of the Nanopore Chemistry

| Generation | Pore | Chemistry | Key Advance |
|-----------|------|-----------|-------------|
| R7 | Modified aHL | Earliest | Proof of concept |
| R9 | CsgG (engineered) | 1D/2D reads | First commercially viable accuracy |
| R9.4.1 | CsgG variant | Improved motor | Workhorse chemistry for years |
| R10.3 | Dual-reader CsgG | Two constrictions | Improved homopolymer resolution |
| R10.4.1 | Optimized dual-reader | Kit 14 | Q20+ raw accuracy (~99%); current standard |

As of 2025, Oxford Nanopore's core chemistry has matured into a streamlined, production-
ready foundation. The company reports stable and consolidated chemistry delivering greater
consistency, predictability, and performance across applications. Output enhancements of
60--70% are targeted into 2026, driving toward a milestone of 200 Gb per flow cell.

#### Device Portfolio

| Device | Flow Cells | Max Pores | Output | Use Case |
|--------|-----------|-----------|--------|----------|
| Flongle | 1 (126 channels) | ~126 | ~2 Gb | Quick tests, small genomes, single amplicons |
| MinION Mk1D | 1 (512 channels) | ~512 | ~50 Gb | Portable field sequencing, education, clinical |
| GridION | 5 (512 ch each) | ~2560 | ~250 Gb | Medium-throughput lab sequencing |
| PromethION 2 Solo | 1--2 (2675 ch each) | ~2675 | ~290 Gb | High-throughput, flexible |
| PromethION 24/48 | 24 or 48 flow cells | ~128k | ~14 Tb | Population-scale sequencing |

The MinION Mk1D features Peltier-based temperature control, enabling reliable sequencing
at ambient temperatures between 10--35 degrees C, making it suitable for field deployment
in remote and resource-limited settings.

#### 2026 Growth Drivers

Key growth drivers for ONT heading into 2026 include:

- The UK Biobank contract to sequence 50,000 samples for the first comprehensive methylome.
- Continued clinical and biopharma adoption.
- Platform improvements in throughput and adaptive sampling.
- High-throughput workflow development allowing more samples per flow cell.
- Flow cell improvements to reduce pore blockage and improve run consistency.

### 3.3 Biological vs. Solid-State Nanopores for Sequencing

| Feature | Biological Nanopores | Solid-State Nanopores |
|---------|---------------------|----------------------|
| Pore reproducibility | Atomic precision (protein structure) | Variable; improving with 2D materials |
| Spatial resolution | ~0.5--1 nm (single k-mer) | 0.34 nm possible (graphene) but noisy |
| Enzyme control | Motor protein ratchets DNA | No enzyme; must slow DNA electrically or mechanically |
| Membrane stability | Lipid bilayer: fragile | SiN, glass, 2D materials: very robust |
| Integration | Complex (lipid membrane handling) | Compatible with semiconductor fabrication |
| Multiplexing | Thousands of pores per flow cell (ONT) | Demonstrated but not yet at commercial scale |
| Base modification detection | Direct (5mC, 6mA, etc.) | Theoretically possible; less mature |

Current commercial sequencing exclusively uses biological nanopores due to the critical
need for enzyme-controlled translocation speed. Solid-state nanopores remain an active
research area, with potential advantages in durability, integration with CMOS electronics,
and scalability. Graphene nanopores offer single-nucleotide spatial resolution but face
challenges with signal-to-noise ratio and DNA speed control.

### 3.4 Integration with Microfluidic Sample Preparation

The combination of nanopore sequencing with microfluidic sample preparation creates
powerful end-to-end analysis systems:

#### Sample Preparation Modules

- **Cell lysis:** On-chip mechanical, thermal, or chemical lysis of cells upstream of
  library preparation.
- **DNA extraction and purification:** Solid-phase extraction using silica pillars or
  magnetic beads in microchannels.
- **Library preparation:** Enzymatic reactions (end-repair, adapter ligation) performed in
  microfluidic reaction chambers with precise temperature control.
- **Size selection:** Deterministic lateral displacement (DLD) arrays or gel-free
  electrophoretic methods for selecting DNA fragment lengths.

#### Integrated Platforms

- **VolTRAX:** Oxford Nanopore's programmable microfluidic sample preparation device,
  designed to automate library preparation directly upstream of MinION sequencing.
- **Fluidigm/Standard BioTools:** Microfluidic processors for targeted amplification before
  nanopore sequencing.
- **Custom PDMS devices:** Academic labs have demonstrated fully integrated sample-to-
  sequence chips combining cell capture, lysis, DNA extraction, library prep, and loading
  onto nanopore flow cells.

#### Field-Deployable Systems

The combination of MinION's portability with microfluidic sample prep enables:

- Pathogen identification in outbreak settings (Ebola, Zika, SARS-CoV-2).
- Environmental DNA (eDNA) monitoring in remote ecosystems.
- Point-of-care antimicrobial resistance profiling.
- Food safety testing at processing facilities.

---

## 4. Nanoparticle Synthesis in Microfluidic Systems

### 4.1 Why Microfluidics for Nanoparticle Synthesis?

Conventional batch synthesis of nanoparticles suffers from poor reproducibility, broad size
distributions, and difficulty in scaling. Microfluidic reactors address these challenges:

| Parameter | Batch Synthesis | Microfluidic Synthesis |
|-----------|----------------|----------------------|
| Mixing time | Seconds to minutes | Milliseconds |
| Temperature uniformity | Gradients common | Excellent (high surface-to-volume) |
| Size distribution (CV) | 15--40% | 3--10% |
| Reproducibility | Batch-to-batch variation | Run-to-run consistency |
| Reagent consumption | mL to L | uL to mL |
| Throughput per device | High (batch volume) | Low (continuous flow) |
| Scale-up strategy | Larger vessels (nonlinear) | Numbering up (parallelization) |

Microfluidic approaches are broadly classified into:

- **Passive methods:** Hydrodynamic flow focusing, vortex generation, droplet generation,
  and chaotic advection -- no external energy input required.
- **Active methods:** Use of acoustic, electric, magnetic, or thermal actuation to enhance
  mixing or control nucleation.

### 4.2 Metal Nanoparticle Synthesis

#### Gold Nanoparticles (AuNPs)

Gold nanoparticles are among the most studied nanomaterials due to their surface plasmon
resonance (SPR), biocompatibility, and catalytic properties. Microfluidic synthesis methods:

- **Citrate reduction (Turkevich):** HAuCl_4 reduced by sodium citrate in a continuous-flow
  microchannel at 70--100 degrees C. Particle size controlled by flow rate ratio, temperature,
  and citrate/gold ratio. Typical sizes: 10--50 nm with CV < 10%.

- **HEPES-mediated reduction:** A recent 2026 study demonstrated tunable gold nanoparticle
  synthesis using microfluidic flow focusing enabled by reusable 3D-printed multimaterial
  connectors, with HEPES serving as both reducing and capping agent.

- **Seed-mediated growth:** Gold seeds (2--5 nm) are mixed with growth solution in
  serpentine microchannels to produce anisotropic structures (nanorods, nanostars,
  nanotriangles) with shape controlled by flow rate and surfactant concentration.

- **Droplet-based synthesis:** Individual droplets serve as isolated nanoreactors, enabling
  highly controlled synthesis of branched gold nanoparticles with minimal polydispersity.

#### Silver Nanoparticles (AgNPs)

- **Borohydride reduction:** AgNO_3 reduced by NaBH_4 in T-junction or flow-focusing
  microchannels. Rapid mixing (<10 ms) produces monodisperse particles (5--30 nm).
- **Green synthesis:** Plant extracts or biopolymers as reducing agents in microfluidic
  channels, enabling environmentally benign production.
- **3D-printed microfluidic devices:** Recent work demonstrated silver nanoparticle
  synthesis in entirely 3D-printed microfluidic systems, lowering the barrier to entry.

#### Other Metal Nanoparticles

- **Platinum (Pt):** Continuous-flow reduction for catalytic applications.
- **Copper (Cu):** Oxygen-free microfluidic synthesis to prevent oxidation.
- **Bimetallic (Au/Ag, Au/Pt):** Sequential or co-reduction in multi-inlet microchannels
  for alloy or core-shell structures.

### 4.3 Quantum Dot Synthesis on Chip

Quantum dots (QDs) are semiconductor nanocrystals (2--10 nm) with size-tunable
photoluminescence. Microfluidic synthesis offers precise control over the nucleation and
growth stages that determine QD size and optical properties.

#### Materials Systems

| QD Material | Emission Range | Synthesis Temperature | Precursors |
|------------|---------------|----------------------|------------|
| CdSe | 450--650 nm | 200--300 C | Cd(oleate), Se-TOP |
| CdTe | 500--750 nm | 150--250 C | CdCl_2, NaHTe |
| InP | 500--700 nm | 180--300 C | In(myristate), P(TMS)_3 |
| PbS | 800--2000 nm (NIR) | 80--150 C | Pb(oleate), bis(TMS) sulfide |
| CsPbX_3 (perovskite) | 400--700 nm | 100--200 C | Cs-oleate, PbX_2 |
| Carbon dots | 350--600 nm | 150--250 C | Citric acid, amine |

#### Microfluidic Reactor Designs

- **Single-phase continuous flow:** Reagents mixed at a T-junction and flowed through a
  heated capillary. Simple but suffers from residence time distribution broadening.

- **Segmented/droplet flow:** QD precursors encapsulated in droplets within an immiscible
  carrier fluid. Each droplet is an identical nanoreactor, producing narrower size
  distributions (CV 3--5% vs. 8--15% for single-phase).

- **Multi-stage reactors:** Separate nucleation (high temperature, short residence time)
  from growth (lower temperature, longer residence time) stages using temperature zones
  along the channel. Enables decoupled control of particle number and size.

- **Additive-manufactured reactors:** 3D-printed reactor platforms enabling ultrafast QD
  synthesis with integrated optical monitoring.

#### Real-Time Monitoring

Microfluidic QD synthesis enables in-line characterization:

- **Absorption spectroscopy:** Fiber-optic probes measure absorption edge shift as QDs
  grow, providing real-time size feedback.
- **Photoluminescence:** In-line PL measurement monitors emission wavelength and FWHM.
- **Machine learning control:** Integration of microfluidics with ML algorithms creates
  "intelligent microfluidics" for autonomous optimization of QD synthesis parameters --
  adjusting flow rates, temperature, and precursor ratios in real time to target specific
  emission wavelengths.

### 4.4 Core-Shell Nanoparticle Production

Core-shell nanoparticles (e.g., CdSe/ZnS QDs, Au@SiO_2, Fe_3O_4@polymer) require
sequential deposition of materials. Microfluidic approaches excel here because:

- **Staged addition:** Multiple reagent inlets along the channel length enable sequential
  shell deposition without intermediate purification steps.
- **Precise timing:** Shell thickness is controlled by residence time in each growth zone,
  which is set by channel length and flow rate.
- **Temperature zoning:** Different zones maintained at different temperatures optimize
  core nucleation (high T) and shell growth (lower T).

Common architectures:

| Core-Shell | Application | Shell Purpose |
|-----------|-------------|---------------|
| CdSe/ZnS | Fluorescent labels | Passivate surface traps; increase quantum yield |
| Fe_3O_4@SiO_2 | MRI contrast, drug delivery | Biocompatibility; functionalization surface |
| Au@SiO_2 | SERS substrates | Dielectric spacer; stability |
| Au@polymer | Theranostics | Drug loading; stealth coating |
| Upconversion@SiO_2 | Bioimaging | Protection; functionalization |

### 4.5 Microfluidic Control of Particle Size and Shape

#### Size Control

Particle size is governed by the interplay between nucleation and growth rates, which
microfluidics controls through:

- **Supersaturation level:** Set by precursor concentration and mixing efficiency (faster
  mixing = higher initial supersaturation = more nuclei = smaller particles).
- **Residence time:** Longer time in the growth zone = larger particles.
- **Temperature:** Higher nucleation temperature = more nuclei = smaller particles (for
  a given precursor amount).
- **Flow rate ratio:** The ratio of precursor to reducing agent flow rates tunes the
  reaction stoichiometry and thus particle size.

#### Shape Control

Anisotropic nanoparticles (rods, plates, stars, cubes) require controlled growth kinetics
on specific crystal facets:

- **Surfactant-directed growth:** CTAB for gold nanorods, PVP for silver nanocubes.
  Microfluidics provides consistent surfactant/precursor ratios impossible in batch.
- **Seed-mediated growth in droplets:** Each droplet provides identical conditions,
  producing uniform populations of anisotropic particles.
- **Segmented temperature profiles:** Different temperatures along the channel can
  sequentially activate growth on different facets.

---

## 5. Nanofabrication for Fluidics

### 5.1 Overview of Nanofabrication Approaches

Fabricating nanofluidic devices requires patterning features at the 1--100 nm scale. The
principal approaches divide into top-down (subtractive lithographic methods) and bottom-up
(self-assembly) strategies:

| Approach | Method | Resolution | Throughput | Cost |
|----------|--------|-----------|-----------|------|
| Top-down | E-beam lithography (EBL) | <5 nm | Very low | Very high |
| Top-down | Focused ion beam (FIB) | ~5 nm | Very low | Very high |
| Top-down | Nanoimprint lithography (NIL) | ~10 nm | High | Low (per unit) |
| Top-down | Interference/holographic lithography | ~50 nm | High | Moderate |
| Top-down | Extreme UV (EUV) lithography | ~7 nm | Very high | Extremely high |
| Bottom-up | Block copolymer self-assembly | 5--50 nm | High | Low |
| Bottom-up | Anodic oxidation (AAO) | 10--200 nm | High | Low |
| Bottom-up | Track etching | 10 nm--um | Moderate | Low |

### 5.2 Electron Beam Lithography (EBL) for Nanochannels

EBL uses a focused beam of electrons to write patterns directly into an electron-sensitive
resist. It is the most versatile tool for prototyping nanofluidic structures.

#### Process Flow for Nanochannel Fabrication

1. **Substrate preparation:** Silicon wafer or fused silica, cleaned and dehydrated.
2. **Resist coating:** Spin-coat thin layer of e-beam resist.
   - Positive resist: PMMA (poly(methyl methacrylate)), ZEP-520A.
   - Negative resist: HSQ (hydrogen silsesquioxane) -- converts to SiO_2-like material
     upon exposure, acting as a permanent structural element.
   - Typical thickness: 30--200 nm.
3. **Electron beam writing:** Focused beam (spot size 1--5 nm) scans the desired pattern.
   Typical acceleration voltage: 30--100 kV. Dose: 100--1000 uC/cm^2 for PMMA.
4. **Development:** Exposed (positive) or unexposed (negative) resist dissolved.
5. **Pattern transfer:** Reactive ion etching (RIE) transfers the pattern into the
   substrate. Typical etch depth: 10--100 nm for nanochannels.
6. **Resist removal and bonding:** Remaining resist stripped; channel sealed by bonding
   a cover (glass, PDMS, or another Si wafer).

#### Capabilities and Limitations

- **Resolution:** Sub-5 nm features achievable in HSQ; ~10 nm in PMMA.
- **Flexibility:** Arbitrary 2D patterns; can write channels, pillars, constrictions.
- **Write speed:** Extremely slow -- a 1 cm^2 area at 10 nm resolution can take many hours.
- **Cost:** $200--1000/hr for instrument time; economical only for prototyping.
- **Proximity effect:** Backscattered electrons expose resist outside the intended area,
  limiting pattern density at the smallest scales. Corrected with dose modulation software.

#### Applications in Nanofluidics

- Nanochannel arrays for DNA stretching (45 nm x 45 nm channels).
- Nanoconstrictions for entropic trapping.
- Nanopore definition (combined with FIB or TEM drilling for final pore opening).
- Nanofluidic transistor gate structures.

### 5.3 Focused Ion Beam (FIB) Milling for Nanostructures

FIB uses a focused beam of ions (typically Ga+, increasingly He+ or Ne+) to directly
remove material from a substrate -- a maskless, resistless, single-step process.

#### FIB for Nanofluidics

- **Direct nanopore drilling:** FIB can drill individual nanopores in SiN_x membranes
  with diameters of 5--50 nm. Ga+ FIB achieves ~10 nm; He+ FIB (HIM) reaches sub-5 nm.
- **Nanochannel milling:** Channels with widths of 20--100 nm milled directly into silicon,
  glass, or polymer substrates.
- **3D nanostructure sculpting:** FIB can create complex 3D topographies by varying dwell
  time and beam current across the pattern.
- **Cross-section analysis:** FIB slice-and-view provides 3D reconstruction of fabricated
  nanofluidic devices for quality verification.

#### Advantages

- Single-step process: no resist, no mask, no development, no etching.
- Direct-write on almost any material (metals, semiconductors, insulators, polymers).
- Can combine milling with ion-beam-induced deposition (IBID) for adding material locally.
- Ideal for rapid prototyping and modifying existing devices.

#### Limitations

- Extremely low throughput (single pore/channel at a time).
- Ga+ implantation contaminates the substrate (~10 nm affected zone).
- Surface amorphization degrades crystal quality of the milled region.
- Redeposition of milled material can partially fill features.
- Cost comparable to EBL for instrument time.

#### Helium Ion Microscope (HIM) FIB

The helium ion beam offers:

- Smaller probe size (~0.3 nm) enabling sub-5 nm features.
- Negligible implantation and sputtering compared to Ga+.
- Minimal sample damage.
- Well-suited for nanopore drilling in 2D materials (graphene, MoS_2).

### 5.4 Nanoimprint Lithography (NIL)

NIL transfers a pattern from a pre-fabricated master (mold) to a substrate by mechanical
deformation of a resist, achieving nanoscale features at high throughput and low cost.

#### Variants

| NIL Type | Mechanism | Temperature | Resolution | Typical Use |
|----------|----------|-------------|-----------|-------------|
| Thermal NIL (T-NIL) | Thermoplastic resist softened by heat, impressed by mold, cooled | 100--200 C | ~10 nm | Silicon/glass nanochannels |
| UV-NIL | UV-curable resist cross-linked under pressure + UV | Room temp | ~10 nm | Polymer nanochannels, biodevices |
| Roll-to-roll NIL | Continuous imprint on flexible substrates | Variable | ~50 nm | High-volume production |
| Step-and-flash | Small-field UV-NIL stepped across wafer | Room temp | <10 nm | Semiconductor-grade patterning |

#### Process Flow for Nanofluidic Device Fabrication

1. **Master fabrication:** Create the nanochannel pattern on a silicon or quartz master
   using EBL or FIB (one-time cost).
2. **Working mold replication:** Cast a daughter mold in hard-PDMS, OrmoStamp, or nickel
   electroform to preserve the expensive master.
3. **Imprint:** Press the mold into resist-coated substrate under controlled pressure
   and temperature (or UV exposure).
4. **Demolding:** Separate mold from substrate; mold reused many times (>1000 imprints).
5. **Residual layer removal:** Brief RIE etch to clear thin residual resist at pattern
   base.
6. **Pattern transfer (optional):** RIE or wet etch into underlying substrate.
7. **Bonding:** Seal channels with cover substrate.

#### Advantages for Nanofluidics

- **Throughput:** Minutes per wafer vs. hours for EBL.
- **Cost:** Master is expensive, but cost amortized over hundreds/thousands of imprints.
- **Resolution:** ~10 nm demonstrated routinely; sub-5 nm possible with careful master
  fabrication.
- **Scalability:** Roll-to-roll NIL enables continuous production of nanofluidic devices
  on polymer foils -- a path to disposable, low-cost nanofluidic diagnostics.
- **Material compatibility:** Works on silicon, glass, polymers (PMMA, COC, PC, PDMS).

#### Challenges

- Defect management: trapped air, particle contamination, incomplete fill.
- Overlay alignment for multi-layer devices.
- Mold wear over many imprint cycles.
- Aspect ratio limitations (deep, narrow features are difficult to demold).

### 5.5 Block Copolymer Self-Assembly

Block copolymers (BCPs) are macromolecules consisting of two or more chemically distinct
polymer blocks covalently bonded together. When cast into thin films, they spontaneously
self-assemble into periodic nanostructures with feature sizes of 5--50 nm, determined by
the molecular weight and composition of the blocks.

#### Morphologies

| Volume Fraction (f_A) | Morphology | Nanofluidic Relevance |
|----------------------|-----------|----------------------|
| ~0.15--0.25 | Spheres in matrix | Nanopore arrays after selective removal |
| ~0.25--0.35 | Cylinders in matrix | Aligned nanochannels / nanopore membranes |
| ~0.35--0.45 | Gyroid (bicontinuous) | Interconnected nanoporous networks |
| ~0.45--0.55 | Lamellae | Alternating layers; less useful for fluidics |

#### Fabrication of Nanoporous Membranes

1. **Thin film casting:** BCP solution spin-coated or drop-cast onto a substrate.
2. **Annealing:** Thermal annealing (above glass transition) or solvent vapor annealing
   to achieve long-range order. Typical domain spacing: 20--50 nm.
3. **Selective removal:** One block is selectively degraded or dissolved:
   - UV/ozone degradation of PMMA in PS-b-PMMA.
   - Reactive ion etching selective to one block.
   - Chemical etching (e.g., HF for removal of PLA in PS-b-PLA).
4. **Result:** Nanoporous membrane with monodisperse, hexagonally ordered pores.

#### Commonly Used Block Copolymer Systems

| BCP | Domain Spacing | Removal Method | Pore Size |
|-----|---------------|----------------|-----------|
| PS-b-PMMA | 20--50 nm | UV + acetic acid wash | 10--30 nm |
| PS-b-PLA | 15--40 nm | NaOH hydrolysis | 8--25 nm |
| PS-b-PEO | 15--60 nm | Water dissolution of PEO | 8--35 nm |
| PS-b-P2VP | 20--50 nm | Quaternization + swelling | 10--30 nm |
| PS-b-P4VP | 20--60 nm | SNIPS process | 15--40 nm |

#### Applications in Nanofluidics

- **Ultrafiltration membranes:** Isoporous membranes with narrow pore size distributions
  for protein separation, virus filtration, and water purification.
- **Templates for inorganic structures:** BCP films used as etch masks to transfer
  nanopatterns into silicon, SiN_x, or metal films for nanofluidic device fabrication.
- **Hierarchical structures:** Combining BCP self-assembly with conventional lithography
  (directed self-assembly, DSA) to produce application-specific nanofluidic channel
  networks with both long-range order and nanoscale features.

#### Advantages

- High resolution (5--50 nm) without expensive lithographic equipment.
- High throughput (wafer-scale self-assembly in minutes to hours).
- Low cost (polymer materials and simple processing).
- Narrow pore size distribution (comparable to track-etched membranes but with much higher
  pore density).

#### Limitations

- Limited pattern complexity (periodic structures only without DSA).
- Defect density higher than top-down lithography.
- Requires careful control of film thickness, substrate chemistry, and annealing conditions.
- Feature size range limited by available block copolymer molecular weights.

### 5.6 Other Nanofabrication Methods

#### Anodic Aluminum Oxide (AAO)

Electrochemical anodization of aluminum produces self-ordered arrays of nanopores:

- Pore diameter: 10--200 nm (controlled by voltage and electrolyte).
- Interpore distance: 50--500 nm.
- Membrane thickness: 1--100 um.
- Applications: molecular filtration, templates for nanowire growth, nanofluidic studies.

#### Ion Track Etching

Heavy ion irradiation followed by chemical etching produces cylindrical nanopores in
polymer membranes (PET, PC, PI):

- Pore diameter: 10 nm to several um (controlled by etch time).
- Pore density: 1 to 10^9 pores/cm^2 (controlled by irradiation dose).
- Conical pores achievable by asymmetric etching.
- Widely used for nanofluidic diodes and ion-selective membranes.

#### Interference Lithography

Two or more coherent laser beams interfere to produce periodic intensity patterns:

- Feature size: lambda/4 achievable (~50 nm with deep UV sources).
- Large area (cm^2) in a single exposure.
- Limited to periodic patterns (lines, dots, grids).
- Used for nanochannel arrays and nanofluidic sieving structures.

---

## 6. Cross-Cutting Themes

### 6.1 Energy Harvesting with Nanofluidics

Nanofluidic devices that exploit ion selectivity can harvest energy from salinity gradients
(blue energy):

- **Reverse electrodialysis:** Ion-selective nanochannels between salt and fresh water
  generate membrane potential. Single nanopore power density: >10^3 W/m^2 (normalized to
  pore area) -- orders of magnitude above macroscopic membranes.
- **Electrokinetic streaming:** Pressure-driven flow through charged nanochannels generates
  streaming current/potential.
- **Osmotic power from 2D membranes:** Single-layer MoS_2 nanopores have demonstrated
  extraordinary osmotic power generation.

### 6.2 Water Desalination

Nanofluidic approaches to desalination leverage ion exclusion:

- **CNT membranes:** Vertically aligned carbon nanotubes in a polymer matrix allow water
  to pass while rejecting salt, with permeabilities 3--5 orders of magnitude above
  conventional reverse osmosis membranes.
- **Graphene oxide laminates:** Stacked GO sheets with controlled interlayer spacing (~7--8
  angstroms) allow water passage while blocking hydrated ions.
- **Concentration polarization desalination:** Microfluidic/nanofluidic devices using ion
  depletion zones to separate salt from water at low pressures.

### 6.3 From Lab to Product: Scaling Challenges

Translating nanofluidic research into products faces several hurdles:

- **Fabrication reproducibility:** Nanometer-scale features are sensitive to process
  variations. Pore-to-pore and device-to-device consistency remains challenging.
- **Throughput:** Single-nanopore devices have inherently low throughput. Parallelization
  (arrays of thousands to millions of pores) is essential but introduces uniformity
  challenges.
- **Integration:** Connecting nanofluidic elements with microfluidic sample handling and
  macro-world interfaces requires multi-scale design.
- **Fouling and clogging:** Nanoscale features are easily blocked by contaminants,
  demanding stringent sample preparation and surface treatments.
- **Characterization:** Confirming the dimensions, surface chemistry, and transport
  properties of individual nanochannels requires specialized tools (TEM, AFM, ionic
  conductance measurements).

### 6.4 Simulation and Modeling at the Nanoscale

| Method | Length Scale | Time Scale | What It Captures |
|--------|-------------|-----------|------------------|
| Ab initio / DFT | <1 nm | fs | Electronic structure, bond breaking/forming |
| Molecular dynamics (MD) | 1--100 nm | ns--us | Water structure, ion solvation, slip |
| Coarse-grained MD | 10--1000 nm | us--ms | Polymer confinement, DNA dynamics |
| Poisson-Nernst-Planck (PNP) | 10 nm--um | Steady state | Ion transport, current-voltage curves |
| Poisson-Boltzmann | 1 nm--um | Equilibrium | EDL structure, Donnan equilibrium |
| Finite element (COMSOL, etc.) | nm--mm | Varies | Coupled multi-physics simulations |

### 6.5 Safety Considerations for Nanomaterials

Working with nanomaterials introduces unique safety concerns:

- **Inhalation hazard:** Nanoparticles (<100 nm) can penetrate deep into the lungs and
  enter the bloodstream. Work in fume hoods or with appropriate respiratory protection.
- **Skin absorption:** Some nanomaterials can penetrate intact skin. Wear nitrile gloves
  and lab coats.
- **Environmental release:** Nanoparticle-containing waste streams require special handling.
  Do not dispose of down the drain.
- **Characterization of exposure:** Standard occupational health metrics (mass-based PELs)
  may not adequately capture nanoparticle risk; surface area and particle number are more
  relevant metrics.
- **EBL/FIB safety:** E-beam and ion beam tools involve high voltages, vacuum systems, and
  (for FIB) toxic gallium. Follow cleanroom safety protocols.

---

## 7. Sources and Further Reading

### Review Articles and Key References

- [Transport Phenomena in Nanofluidics](https://link.aps.org/doi/10.1103/RevModPhys.80.839) -- Schoch, Han, Renaud, *Reviews of Modern Physics* (2008). Foundational review of nanofluidic transport theory.
- [Transport Phenomena in Nano/Molecular Confinements](https://pubs.acs.org/doi/abs/10.1021/acsnano.0c07372) -- *ACS Nano* (2020). Updated review covering sub-nm confinement effects.
- [Carbon Nanotube Nanofluidics](https://pubs.rsc.org/en/content/articlehtml/2025/cs/d5cs00233h) -- *Chemical Society Reviews* (2025). Comprehensive review of CNT-based nanofluidic phenomena.
- [Review: Fabrication of Nanofluidic Devices](https://pmc.ncbi.nlm.nih.gov/articles/PMC3612116/) -- *Biomicrofluidics* (2013). Methods for nanochannel and nanopore fabrication.
- [Fabrication of Nanochannels](https://pmc.ncbi.nlm.nih.gov/articles/PMC5512911/) -- *PMC* (2017). Detailed nanochannel fabrication protocols.
- [Nanofluidic Systems for Ion Transport with Tunable Surface Charges](https://www.frontiersin.org/journals/lab-on-a-chip-technologies/articles/10.3389/frlct.2024.1356800/full) -- *Frontiers in Lab on a Chip Technologies* (2024).

### Nanopore Sensing and Sequencing

- [Nanopore Sensing: Current Progress and Future Challenges](https://www.sciencedirect.com/science/article/abs/pii/S0165993625004091) -- *Trends in Analytical Chemistry* (2025).
- [Two-Dimensional Material-Based Nanofluidic Devices](https://pubs.acs.org/doi/10.1021/acsnano.4c12051) -- *ACS Nano* (2024).
- [Oxford Nanopore MinION: Delivery of Nanopore Sequencing](https://link.springer.com/article/10.1186/s13059-016-1103-0) -- *Genome Biology* (2016).
- [How Nanopore Sequencing Works](https://nanoporetech.com/platform/technology) -- Oxford Nanopore Technologies.
- [London Calling 2025 Technology Update](https://nanoporetech.com/news/london-calling-2025-technology-update) -- Oxford Nanopore Technologies (2025).
- [Oxford Nanopore at JPM 2026](https://www.bio-itworld.com/news/2026/01/13/oxford-nanopore-at-jpm-2026--passing-the-baton-on-a-20-year-journey) -- Bio-IT World (2026).

### Nanofluidic Circuit Elements

- [Field-Effect Reconfigurable Nanofluidic Ionic Diodes](https://www.nature.com/articles/ncomms1514) -- *Nature Communications*.
- [Nanofluidic Ionic Diodes: Comparison of Analytical and Numerical Solutions](https://pubs.acs.org/doi/abs/10.1021/nn800306u) -- *ACS Nano*.
- [Nanofluidic Circuitry](https://en.wikipedia.org/wiki/Nanofluidic_transistor) -- Wikipedia overview.
- [Spirocyclic Fluorescein Nanofluidic Diodes](https://onlinelibrary.wiley.com/doi/10.1002/smll.202501424) -- *Small* (2025).

### DNA Confinement and Entropic Effects

- [Entropic Cages for Trapping DNA Near a Nanopore](https://www.nature.com/articles/ncomms6222) -- *Nature Communications*.
- [Entropic Unfolding of DNA in Nanofluidic Channels](https://pubs.acs.org/doi/abs/10.1021/nl802256s) -- *Nano Letters*.
- [Conformational Analysis of Single DNA Molecules in Nanochannels](https://pmc.ncbi.nlm.nih.gov/articles/PMC1471858/) -- *PMC*.

### Nanoparticle Synthesis

- [Advances in Nanoparticle Synthesis Assisted by Microfluidics](https://pubs.rsc.org/en/content/articlehtml/2025/lc/d5lc00194c) -- *Lab on a Chip* (2025).
- [Redefining Quantum Dot Synthesis with Additive-Manufactured Microfluidics](https://www.mdpi.com/2571-8800/8/2/18) -- *MDPI* (2025).
- [Tunable Gold Nanoparticle Synthesis Using Microfluidic Flow Focusing](https://link.springer.com/article/10.1007/s00604-026-07848-4) -- *Microchimica Acta* (2026).
- [Intelligent Control of Nanoparticle Synthesis with Machine Learning](https://www.nature.com/articles/s41427-022-00416-1) -- *NPG Asia Materials*.

### Nanofabrication

- [Advancements in Lithography Techniques for Nanostructure Fabrication](https://pmc.ncbi.nlm.nih.gov/articles/PMC11988993/) -- *PMC* (2024).
- [Fabrication of Nanodevices Through Block Copolymer Self-Assembly](https://www.frontiersin.org/journals/nanotechnology/articles/10.3389/fnano.2022.762996/full) -- *Frontiers in Nanotechnology* (2022).
- [Nanoporous Block Copolymer Membranes for Ultrafiltration](https://pubs.acs.org/doi/abs/10.1021/nn505234v) -- *ACS Nano*.
- [Block Copolymers for Nanostructured Porous Coatings](https://pmc.ncbi.nlm.nih.gov/articles/PMC6122062/) -- *PMC* (2018).
