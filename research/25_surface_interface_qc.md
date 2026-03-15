# Surface Treatment, Chip-to-World Interfacing, and Quality Control

> Practical guide covering microfluidic chip cleaning and reuse, surface functionalization
> and coatings, chip-to-world interfacing strategies, and quality control metrology.

---

## Table of Contents

1. [Microfluidic Chip Cleaning and Reuse](#1-microfluidic-chip-cleaning-and-reuse)
2. [Surface Functionalization and Coatings](#2-surface-functionalization-and-coatings)
3. [Chip-to-World Interfacing](#3-chip-to-world-interfacing)
4. [Quality Control and Metrology](#4-quality-control-and-metrology)

---

## 1. Microfluidic Chip Cleaning and Reuse

### 1.1 When Chips Can vs. Cannot Be Reused

**Generally reusable:**
- Simple channel geometries (straight channels, Y-junctions) with no irreversible fouling
- Glass and silicon chips (robust to harsh cleaning chemicals)
- PDMS chips with reversible bonding (can be disassembled, cleaned, re-bonded)
- Chips used with buffers, dyes, or simple aqueous solutions
- Thermoplastic chips (COC, COP, PMMA) used with compatible solvents

**Generally NOT reusable:**
- Chips with permanent protein/cell fouling in narrow channels (<20 um)
- PDMS chips after prolonged exposure to organic solvents (swelling/distortion)
- Chips with clogged channels where particulate matter cannot be dislodged
- Devices with degraded surface coatings critical to function
- Chips where antibodies or capture molecules have been covalently immobilized
- Any chip showing delamination or bond failure

### 1.2 PDMS Chip Cleaning Protocols

#### Basic Cleaning (Between Runs with Aqueous Solutions)

1. Flush channels with warm deionized (DI) water at moderate flow rate (10-50 uL/min) for 5-10 minutes
2. Flush with mild soap solution (1% Micro-90 or similar) for 5 minutes
3. Rinse with DI water for 10 minutes
4. Flush with 70% ethanol for 5 minutes (optional, for sterilization)
5. Final rinse with DI water for 5 minutes
6. Dry with filtered nitrogen or compressed air
7. Store in a clean, dust-free container

#### Intermediate Cleaning (Protein or Cell Residue)

1. Flush with 1% sodium dodecyl sulfate (SDS) solution for 10-15 minutes
2. Rinse with DI water for 5 minutes
3. Flush with 0.1 M NaOH for 10 minutes (caution: can affect bonding over time)
4. Rinse with DI water for 10 minutes
5. Flush with 70% isopropanol for 5 minutes
6. Final DI water rinse for 5 minutes
7. Dry with nitrogen

#### Deep Cleaning (Heavy Contamination)

1. If reversibly bonded: disassemble the chip
2. Soak PDMS pieces in Terg-a-zyme enzymatic cleaner (1% solution) at 37C for 1-2 hours
3. Sonicate in DI water for 10 minutes at low power
4. Rinse thoroughly with DI water
5. Soak in 70% ethanol for 30 minutes
6. Dry and reassemble

**Solvents to AVOID with PDMS:**
- Acetone (causes severe swelling)
- Toluene, hexane, dichloromethane (extreme swelling, distortion)
- Concentrated acids (HCl, H2SO4) -- can degrade PDMS
- DMSO at high concentrations

**Solvents SAFE for PDMS:**
- Water, PBS, Tris buffers
- Ethanol, methanol, isopropanol (mild swelling, recoverable)
- Dilute surfactant solutions (SDS, Tween-20)
- Dilute NaOH (0.1 M, short exposure)

### 1.3 Glass and Silicon Chip Cleaning Protocols

Glass and silicon are far more chemically resistant than PDMS and can tolerate aggressive cleaning.

#### Standard Glass/Silicon Cleaning

1. Flush with acetone for 5 minutes
2. Flush with isopropanol for 5 minutes
3. Flush with DI water for 5 minutes
4. Place chip in ultrasonic bath with 2% Micro-90 detergent for 10-15 minutes
5. Rinse in DI water ultrasonic bath for 10 minutes
6. Dry with nitrogen

#### Piranha Clean (Heavy Organic Contamination)

> WARNING: Piranha solution is extremely dangerous. Use only in a properly equipped chemistry lab with full PPE (face shield, acid-resistant gloves, lab coat).

1. Prepare piranha solution: 3:1 ratio of concentrated H2SO4 to 30% H2O2
2. Immerse glass/silicon chip for 10-30 minutes at room temperature (solution self-heats)
3. Remove chip with acid-resistant tweezers
4. Rinse extensively with DI water (at least 5 rinse cycles)
5. Dry with nitrogen
6. Use immediately or store in clean, dry container

Piranha cleaning removes all organic residues and simultaneously activates the glass surface with hydroxyl groups (useful for subsequent bonding or functionalization).

#### RCA Clean (Semiconductor-Grade)

For silicon microfluidic chips requiring the highest cleanliness:

- **RCA-1 (SC-1):** 5:1:1 ratio of H2O : NH4OH : H2O2 at 70-80C for 10-15 minutes. Removes organic contaminants.
- **RCA-2 (SC-2):** 6:1:1 ratio of H2O : HCl : H2O2 at 70-80C for 10-15 minutes. Removes metallic contaminants.

Rinse with DI water between steps and after the final step.

### 1.4 Ultrasonic Cleaning Considerations

- Use low-power ultrasonic baths (40 kHz typical) for 5-15 minutes
- Effective for dislodging particulate matter from channels
- Risk: can damage delicate structures, thin membranes, or weak bonds
- For PDMS: keep sonication time short (<10 min) and power low
- For glass/silicon: more tolerant; can use longer sonication times
- Always place chips in a beaker with cleaning solution inside the ultrasonic bath (not directly in bath water)

### 1.5 Storage After Cleaning

- Store PDMS devices in a sealed container (Petri dish, ziplock bag)
- Keep in a dust-free environment
- If surface treatment is critical: use within 24-48 hours of plasma treatment (PDMS hydrophobic recovery occurs)
- Glass/silicon chips can be stored dry in cleanroom-grade containers for weeks
- For long-term storage of PDMS devices: wrap in aluminum foil to block UV, store at room temperature

---

## 2. Surface Functionalization and Coatings

### 2.1 PEG-Silane Coatings for Anti-Fouling

PEG (polyethylene glycol) is the gold standard for creating anti-fouling surfaces. When grafted as a brush layer, PEG chains create a hydration layer that physically and entropically resists protein adsorption.

#### One-Step PEG-Silane Protocol (Glass/Silicon)

**Materials:**
- mPEG-silane (MW 2000-5000; e.g., methoxy-PEG-triethoxysilane)
- Anhydrous toluene or ethanol
- Piranha solution or oxygen plasma for surface activation

**Protocol:**
1. Clean substrate with piranha solution or O2 plasma (100 W, 2 min) to generate surface hydroxyl groups
2. Prepare 1-10 mg/mL mPEG-silane solution in anhydrous toluene
3. Immerse activated substrate in PEG-silane solution
4. Incubate at room temperature for 1-2 hours (or overnight for denser brush)
5. Remove and rinse sequentially with toluene, ethanol, DI water
6. Dry with nitrogen
7. Optional: cure at 110C for 30 minutes to strengthen siloxane bonds

**Key tip:** Minimize water content in the PEG-silane solution. Water hydrolyzes the silane, reducing coating efficiency and causing solution-phase polymerization rather than surface grafting.

**Performance:** Reduces nonspecific protein adsorption to a few ng/cm2. Coating is stable for days to weeks under physiological conditions.

#### Three-Step PEG Protocol (Higher Density Brush)

1. Create amine monolayer using aminopropylsilatrane on cleaned glass (30 min incubation)
2. React with heterobifunctional crosslinker (e.g., NHS-PEG-maleimide) for 30 minutes
3. Graft thiol-PEG (mPEG-SH, MW 5000) via thiol-maleimide click chemistry for 2-4 hours

This approach yields denser PEG brushes and superior anti-fouling compared to the one-step method.

### 2.2 PLL-g-PEG Surface Treatment

PLL-g-PEG (poly-L-lysine-graft-polyethylene glycol) is a copolymer where positively charged PLL backbone adsorbs electrostatically to negatively charged surfaces (glass, oxidized PDMS, silicon oxide), while PEG side chains extend outward to resist protein adsorption.

#### Protocol

**Materials:**
- PLL(20)-g[3.5]-PEG(2) or PLL(20)-g[3.5]-PEG(5) (from SuSoS or custom synthesis)
- HEPES buffer (10 mM, pH 7.4) or PBS

**Steps:**
1. Clean and activate surface (O2 plasma for PDMS; piranha or plasma for glass)
2. Prepare 0.1-0.5 mg/mL PLL-g-PEG in 10 mM HEPES pH 7.4 or PBS
3. Fill microfluidic channels with PLL-g-PEG solution
4. Incubate at room temperature for 30-60 minutes (static, no flow)
5. Rinse with buffer (3x channel volumes)
6. Device is ready for use

**Performance:**
- Reduces electroosmotic flow (EOF) by 83-88% on PDMS and quartz
- Reduces protein adsorption by approximately 45-50%
- Simple dip-and-rinse protocol, no specialized equipment needed
- Coating is stable for hours to days under continuous flow

**Limitations:**
- Electrostatic adsorption means the coating can be displaced by high ionic strength buffers or pH extremes
- Not as durable as covalent PEG-silane coatings
- Best for short-duration experiments (hours)

### 2.3 BSA and Casein Blocking Protocols

Protein blocking is the simplest and cheapest passivation method, commonly used when a quick, disposable solution is acceptable.

#### BSA Blocking Protocol

1. Prepare 1-3% (w/v) BSA in PBS (with or without Ca2+/Mg2+)
2. Filter the solution through a 0.22 um syringe filter
3. Fill microfluidic channels with BSA solution
4. Incubate at room temperature for 30-60 minutes (or at 37C for faster adsorption)
5. Rinse gently with PBS (2-3x channel volumes)
6. Proceed with experiment immediately (do not let channels dry)

**Typical concentrations:** 0.5-3% BSA, with 1% being most common. Higher concentrations provide slightly better coverage but also increase the risk of aggregates.

#### Casein Blocking Protocol

1. Prepare 0.5-1% (w/v) casein in PBS (use commercial casein blocker for convenience)
2. Filter through 0.45 um filter (casein can clog 0.22 um filters)
3. Fill channels and incubate for 30-60 minutes at room temperature
4. Rinse with PBS

**When to use BSA vs. casein:**
- BSA: general-purpose blocking; suitable for most immunoassays and cell-based applications
- Casein: better for reducing background in chemiluminescent detection; lower endogenous biotin (important for streptavidin-biotin systems)
- Neither is suitable for experiments where the blocking protein itself would interfere (e.g., albumin-binding studies)

**Durability:** Protein blocking layers are physically adsorbed and will desorb over time (hours to days). They are not suitable for long-term or high-shear applications.

### 2.4 Fluorosilane Coatings for Hydrophobic Treatment

Fluorosilane coatings render surfaces highly hydrophobic (contact angle >110 degrees) and are essential for water-in-oil droplet generation in microfluidics.

#### Liquid-Phase Fluorosilanization Protocol

**Materials:**
- 1H,1H,2H,2H-perfluorodecyltrichlorosilane (FDTS) or (tridecafluoro-1,1,2,2-tetrahydrooctyl)trichlorosilane
- Fluorinated solvent (e.g., HFE-7500, FC-3283, or Novec 7100)
- O2 plasma cleaner

**Steps:**
1. Activate surface with O2 plasma (100 W, 1-2 minutes) to generate -OH groups
2. Prepare 1-2% (v/v) fluorosilane in fluorinated solvent
3. Fill channels with fluorosilane solution immediately after plasma treatment
4. Incubate for 10-30 minutes at room temperature
5. Flush channels with pure fluorinated solvent to remove unreacted silane
6. Flush with air or nitrogen to dry
7. Bake at 110C for 30 minutes to cure

#### Vapor-Phase Fluorosilanization Protocol

This method provides more uniform coatings and avoids solvent handling.

1. Activate surface with O2 plasma
2. Place device and a small dish containing 20-50 uL of fluorosilane in a vacuum desiccator
3. Pull vacuum (house vacuum or roughing pump, ~100 mbar)
4. Leave for 1-4 hours (or overnight for thicker coating)
5. Remove from desiccator and bake at 110C for 30 minutes

**Commercial products:**
- Aquapel (commercially available fluoropolymer, simple single-step coating for glass)
- FluoPel (Cytonix) -- fluoropolymer coatings in various grades for different wettability targets
- Fluo-ST1 (Emulseo) -- specifically designed for PDMS and glass microfluidic droplet generators

**Performance:** Contact angles >110 degrees on glass, stable for days to weeks under continuous flow with fluorinated oils.

### 2.5 Parylene C Deposition for Barrier Coating

Parylene C is a conformal polymer coating deposited by chemical vapor deposition (CVD). It provides an excellent chemical barrier and is biocompatible (USP Class VI).

#### Deposition Process

Parylene C deposition uses a three-stage CVD process:

1. **Vaporization:** Parylene dimer is heated to >80C to sublimate
2. **Pyrolysis:** Dimer passes through a furnace at 690C, decomposing into reactive monomer
3. **Deposition:** Monomer enters the room-temperature deposition chamber and polymerizes conformally on all exposed surfaces

**Typical parameters:**
- Film thickness: 0.5-25 um (controlled by dimer charge mass)
- Deposition rate: ~0.5-2 um/hour
- Substrate temperature: room temperature (no thermal stress)
- Equipment: Labcoater 2 (SCS), PDS 2010 (SCS), or equivalent

#### Protocol for Microfluidic Devices

1. Clean device surfaces (IPA wash, UV post-cure if resin-printed)
2. Apply silane adhesion promoter (A-174, gamma-methacryloxypropyltrimethoxysilane) via vapor phase in the deposition chamber
3. Load parylene dimer (e.g., 5 g for ~5 um coating on small devices)
4. Run deposition cycle (typically 2-4 hours total)
5. Remove devices; parylene vapor penetrates into channels through inlet/outlet holes

**Key considerations:**
- Film thickness decreases with distance from channel access holes (gradient may occur in long, narrow channels)
- Coatings >1 um form an airtight seal (air bubbles in dead-end channels will not escape)
- Adhesion promoter is critical; without it, parylene can delaminate under stress
- Parylene C is insoluble in organic solvents below ~150C

**Applications:**
- Chemical barrier for 3D-printed resin devices (prevents leaching of cytotoxic monomers)
- Moisture barrier for integrated electronics
- Biocompatible coating for cell culture devices
- Dielectric layer for electrowetting-on-dielectric (EWOD) digital microfluidics

### 2.6 Dynamic Coating Protocols (Pluronic, PVA)

Dynamic coatings are physically adsorbed surfactants or polymers that modify surface properties through simple channel flushing. They are the easiest coatings to apply but are also the least durable.

#### Pluronic F127 Coating

Pluronic F127 is a triblock copolymer (PEO-PPO-PEO) where the hydrophobic PPO block adsorbs to hydrophobic PDMS while the hydrophilic PEO blocks extend into solution.

**Protocol:**
1. Prepare 0.1-1% (w/v) Pluronic F127 in PBS or DI water
2. Optionally UV-sterilize the PDMS device
3. Fill channels with Pluronic F127 solution
4. Incubate at room temperature for 1-2 hours
5. Rinse with PBS
6. Use device immediately

**Alternative (with cell adhesion molecule):**
- For cell culture: coat with 100 ug/mL F127-PDL (Pluronic conjugated with poly-D-lysine) for 2 hours, rinse with PBS, equilibrate with culture medium

**Performance:**
- Reduces PDMS contact angle from ~110 degrees to ~40-60 degrees
- Reduces nonspecific protein adsorption significantly
- Prevents cell adhesion (useful for suspension culture, droplet microfluidics)

**Limitations:**
- Coating can desorb over time, especially under continuous flow
- Bulk PDMS modification (adding Pluronic to PDMS prepolymer) provides more durable results than surface immersion
- Not suitable for long-term experiments (>24 hours) without replenishment

#### PVA (Polyvinyl Alcohol) Coating

PVA coating provides a more durable hydrophilic layer on PDMS than Pluronic.

**Protocol (plasma-assisted PVA deposition):**
1. Degrease PDMS device in IPA, blow dry with nitrogen
2. Dehydrate in oven at 110C for 40 minutes
3. Plasma treat: O2 plasma at 100 W, 20 sccm O2, 0.65 mbar, 1 minute
4. Immediately fill channels with PVA solution (1-5% w/v in DI water)
5. Incubate at room temperature for 10 minutes
6. Flush channels with pressurized nitrogen to remove excess PVA
7. Bake at 110C for 15 minutes
8. **Repeat steps 3-7 two more times** (three coats total)

**Performance:**
- Contact angle reduced to 22.7 +/- 5.4 degrees (from ~110 degrees)
- Coating is more durable than Pluronic because PVA cross-links to the oxidized PDMS surface
- Suitable for self-driven (capillary) microfluidic chips

### 2.7 Coating Durability Summary

| Coating | Durability | Reapplication | Best For |
|---------|-----------|---------------|----------|
| PEG-silane (covalent) | Days to weeks | Not needed during experiment | Long-term anti-fouling |
| PLL-g-PEG | Hours to days | Every 4-8 hours under flow | Quick passivation |
| BSA/casein blocking | Hours | Every 1-4 hours | Short experiments |
| Fluorosilane | Days to weeks | Rarely needed | Droplet generation |
| Parylene C | Months to years | Not applicable (permanent) | Barrier coating |
| Pluronic F127 | Hours | Every 2-4 hours under flow | Quick anti-adhesion |
| PVA (multi-coat) | Days to weeks | After cleaning/reuse | Hydrophilic PDMS |

---

## 3. Chip-to-World Interfacing

### 3.1 The Interface Problem

The chip-to-world interface bridges the mismatch between the macro-scale lab environment (syringes, pumps, reservoirs at mL scale) and the micro-scale chip (channels at nL-uL scale). Key challenges include:

- Sealing fluidic connections without leaks at operating pressures
- Minimizing dead volume at connections (critical for precious samples)
- Enabling rapid chip swapping for high-throughput experiments
- Providing electrical connections for sensing/actuation
- Maintaining optical access for microscopy

### 3.2 Standard Port Sizes and Threading

**Common tubing outer diameters (OD) used in microfluidics:**
- 1/32" (0.79 mm) -- for low-flow applications, minimal dead volume
- 1/16" (1.59 mm) -- most common size for research microfluidics
- 1/8" (3.18 mm) -- for higher flow rates

**Standard fittings:**
- **UNF 1/4"-28:** The de facto standard thread for microfluidic connections (inherited from HPLC). Compatible with Upchurch/IDEX, LabSmith, and most commercial fittings.
- **M6 thread:** Used by some European suppliers (e.g., Dolomite)
- **Luer lock (male/female):** Common for syringe connections; adapters available for chip ports
- **Barb fittings:** Press-fit into PDMS; simple but lower maximum pressure

**Fitting types:**
- Flat-bottom fittings (most common for microfluidics): provide zero dead volume when properly seated
- Coned fittings: self-centering, good seal, but slight dead volume
- Compression fittings (ferrule-based): permanent connection, highest pressure rating

### 3.3 PDMS Chip Connections

The most common approach for PDMS devices:

1. **Punch-and-insert method:**
   - Punch inlet/outlet holes with a biopsy punch (0.75 mm for 1/32" tubing, 1.0 mm for 1/16" tubing)
   - Use a punch slightly smaller than tubing OD for an interference fit
   - Insert tubing directly into the punched hole
   - The elasticity of PDMS creates a self-sealing connection
   - Typical max pressure: 30-60 kPa (5-9 psi)

2. **Needle-stub method:**
   - Punch a slightly larger hole
   - Insert a blunt-end dispensing needle (e.g., 20 gauge for 1/16" tubing)
   - Connect tubing to the needle hub
   - Higher pressure tolerance than bare tubing insertion

### 3.4 Custom Chip Holders

#### 3D Printed Chip Holders

3D printing enables rapid prototyping of custom chip holders with integrated fluidic, electrical, and optical connections.

**Design guidelines:**
- Material: use SLA/DLP resin for highest resolution, or SLS nylon for durability
- Include O-ring grooves around each fluidic port (standard O-ring sizes: AS568-001 for 1/16" ports)
- Design for threaded inserts (1/4"-28 UNF) that accept standard HPLC fittings
- Include alignment features (pins, edges) for repeatable chip positioning
- Leave optical windows where needed for microscopy

**Typical architecture:**
- Base plate with alignment features and O-ring grooves
- Chip placed on base plate, channels facing down (or up, depending on imaging needs)
- Top clamp plate that compresses O-rings to create sealed fluidic connections
- Fastened with screws (4-6 screws, M3 or 4-40) or magnetic clamps

**Resolution requirements:**
- O-ring grooves: minimum wall thickness 0.3 mm, groove depth tolerance +/- 0.05 mm
- Port alignment: +/- 0.1 mm registration accuracy
- SLA/DLP printers with 35-50 um XY resolution are suitable

#### CNC-Machined Holders

For production use or high-pressure applications:

- Material: acetal (Delrin), PEEK, or anodized aluminum
- Tighter tolerances than 3D printing (+/- 0.025 mm achievable)
- Can integrate threaded ports directly (1/4"-28 UNF tapped holes)
- Better surface finish for O-ring sealing
- Higher cost per unit but more durable and chemically resistant

### 3.5 Magnetic Clamping Solutions

Magnetic clamping provides tool-free, rapid chip loading and unloading.

**Design approach:**
- Embed rare-earth magnets (NdFeB, N42 or stronger) in both the base plate and top clamp
- Use 3-6 mm diameter cylindrical magnets, 2-3 mm thick
- Arrange magnets symmetrically around the chip perimeter
- Clamping force must compress O-rings sufficiently (typically 5-15 N total force needed)
- PDMS elasticity seals the tubing, and the PDMS-device interface is sealed through magnetic clamping

**Advantages:**
- No tools required for chip exchange
- Sub-second chip loading/unloading
- No risk of over-tightening (screw-based systems can crack glass chips)
- No chemical contamination (no glue or adhesive needed)

**Limitations:**
- Lower maximum pressure than screw-clamped systems
- Magnets can interfere with sensitive magnetic measurements
- Must carefully design magnet placement to avoid interfering with optical path

### 3.6 Integration with Well Plates (SBS Format)

The SBS (Society for Biomolecular Screening) standard defines microtiter plate dimensions:
- Footprint: 127.76 mm x 85.48 mm
- Height: varies by plate type (14.35 mm for standard 96-well)
- Well spacing: 9.0 mm (96-well), 4.5 mm (384-well)

**Integration strategies:**

1. **Handling frames:** Commercial handling frames (e.g., from microfluidic ChipShop) accept microfluidic chips and conform to SBS microtiter plate dimensions, enabling use with standard plate readers, robotic liquid handlers, and incubators.

2. **Chip-in-well-plate format:** Microfluidic channels are fabricated directly into the bottom of a well plate, combining the fluidic advantages of microfluidics with the workflow familiarity of well plates.

3. **Adapter plates:** Custom 3D-printed or CNC-machined adapter plates that hold multiple microfluidic chips in an SBS-format frame.

**Benefits:**
- Compatibility with standard laboratory automation (liquid handlers, plate readers)
- Familiar form factor for biologists
- Facilitates high-throughput experiments

### 3.7 PCB-Based Chip Interfaces

Printed circuit boards (PCBs) provide an excellent platform for integrating electrical connections with microfluidic chips.

**Architecture:**
- Microfluidic chip (glass, PDMS, or polymer) is bonded or clamped to a custom PCB
- PCB provides patterned electrodes for sensing (impedance, electrochemistry)
- Through-holes in PCB serve as fluidic vias
- Edge connectors or pin headers provide macro-scale electrical interface

**Advantages:**
- PCB fabrication is extremely mature, low cost, and scalable
- Easy combination of electrodes, electronics, and fluidic channels
- Standard PCB connectors (e.g., edge card, ZIF) provide reliable electrical contact
- Enables integration of evaluation electronics close to sensors

**Design considerations:**
- A flat PCB surface is required for leak-free bonding to the microfluidic chip
- Solder mask and component placement must avoid the bonding area
- Use gold or platinum electrode finishes for electrochemical compatibility (avoid tin, which corrodes)
- Standard PCB through-holes (0.3-1.0 mm) can serve as fluidic ports
- Hybrid Lab-on-PCB (separate PCB and polymer chip bonded together) is easier to design than monolithic approaches

**Fabrication approaches:**
- Standard FR-4 PCB with polymer microfluidic layer bonded on top
- Flexible PCB (polyimide) for curved or conformal applications
- Multi-layer PCB with embedded channels (advanced, requires specialized fab house)
- 3D-printed microfluidic structures directly on PCB substrate using DLP/mSLA printers (35 um XY resolution achievable)

### 3.8 ISO 22916 Standard

ISO 22916:2022 ("Microfluidic devices -- Interoperability requirements for dimensions, connections and initial device classification") defines standardized dimensions and connection points for microfluidic devices.

**Key provisions:**
- **Chip naming convention:** Rectangular chips are named by X x Y dimensions (in mm), where X is the axis with most fluidic connections
- **Coordinate system:** Reference point at top-left corner; X-axis left to right; Z-axis for side connections, with the bottom side on the X-Y plane
- **Port grid:** Standardized port spacing and positioning to enable interoperable fixtures
- **Connection types:** Defines both top-side and side connections
- **Device classification:** Initial classification framework for different microfluidic device types

**Standard chip sizes defined:**
- 15.5 x 15.5 mm (small, single-function)
- 45.0 x 15.0 mm (medium, multi-channel)
- 75.5 x 25.5 mm (microscope slide format)

**Relevance:** Designing chips to ISO 22916 dimensions enables compatibility with commercial chip holders, fixtures, and interconnect systems from multiple vendors, reducing custom tooling requirements.

### 3.9 Connector-Free Approaches

For applications requiring minimal dead volume or avoiding chemical contamination from connector materials:

- **Interference fit:** Tubing press-fit directly into chip port holes. Works well with PDMS elasticity.
- **Adhesive bonding:** Epoxy or UV-curable adhesive applied around tubing-port junction. Permanent, high pressure, but not reversible.
- **Integrated reservoirs:** Open wells fabricated directly on the chip, eliminating tubing entirely. Driven by capillary action, gravity, or centrifugal force.
- **Compression gasket:** Flat PDMS gasket between chip and manifold, compressed by mechanical or magnetic force. Reversible and leak-free up to moderate pressures.

---

## 4. Quality Control and Metrology

### 4.1 Channel Dimension Measurement

Accurate measurement of channel width, depth, and cross-sectional profile is essential for validating fabrication processes and ensuring device performance.

#### Optical Profilometry (Recommended for Open Channels)

Optical profilometry uses white-light interferometry or confocal chromatic sensing to measure surface topography without contact.

**Procedure:**
1. Place the open (unbonded) chip on the profilometer stage
2. Set measurement area to span the channel cross-section with margin
3. Acquire a 3D surface profile scan
4. Extract cross-sectional profiles perpendicular to channel direction
5. Measure width (at top of channel) and depth from the profile

**Specifications:**
- Lateral resolution: 0.5-2 um (depending on objective)
- Vertical resolution: <1 nm (interferometric), ~10 nm (confocal chromatic)
- Measurement range (Z): up to several mm
- Non-contact, non-destructive
- Fast acquisition (seconds to minutes per field of view)

**Instruments:** Bruker ContourGT, Zygo NewView, Keyence VK-X series, Sensofar S neox

Optical profilometry has been identified as the most reliable method for microfluidic channel characterization, offering the lowest measurement uncertainty and highest consistency with nominal geometry values.

#### Stylus Profilometry

A diamond-tipped stylus physically traces the surface. Simple and reliable but contact-based.

**Procedure:**
1. Program a linear scan perpendicular to the channel
2. Set stylus force (1-5 mg for soft materials like PDMS, higher for hard materials)
3. Scan across the channel
4. Read depth and width directly from the profile trace

**Specifications:**
- Vertical resolution: 1-10 nm
- Lateral resolution: limited by stylus tip radius (typically 2-12.5 um)
- Cannot measure enclosed channels
- Risk of scratching soft substrates (PDMS, polymer)
- Instruments: Bruker DektakXT, KLA-Tencor P-series

#### Scanning Electron Microscopy (SEM)

SEM provides high-resolution imaging of channel cross-sections.

**Procedure:**
1. Cleave or cut the chip to expose a channel cross-section
2. If non-conductive (PDMS, glass): sputter-coat with Au/Pd (5-10 nm)
3. Mount on SEM stub with carbon tape
4. Image the cross-section at appropriate magnification
5. Measure dimensions from the calibrated SEM image

**Specifications:**
- Resolution: 1-10 nm (depends on instrument and imaging conditions)
- Provides true cross-sectional shape (reveals rounded corners, undercut, sidewall angle)
- Destructive (requires cutting the chip)
- Requires vacuum-compatible samples
- Time-consuming sample preparation

**Best used for:** Validating fabrication process development, not routine QC.

#### Optical Microscopy (Quick Check)

For routine dimensional checks with moderate accuracy:

1. Place chip on calibrated microscope (brightfield, 5-20x objective)
2. Focus on channel features
3. Measure width using calibrated reticle or image analysis software
4. For depth: use confocal microscopy or focus-through technique

**Accuracy:** Typically +/- 1-5 um for width; depth requires confocal or other Z-resolved technique.

#### Measurement of Enclosed (Bonded) Channels

Measuring channels inside sealed devices is significantly more challenging:

- **Confocal microscopy:** Focus through transparent materials to image channel boundaries. Works for glass-PDMS devices. Requires refractive index correction for accurate depth measurements.
- **Optical coherence tomography (OCT):** Non-destructive cross-sectional imaging through transparent materials. Resolution ~5-15 um. Good for rapid whole-device screening.
- **X-ray micro-CT:** Non-destructive 3D imaging of internal features. Resolution 1-50 um depending on instrument. Works with any material (opaque or transparent). Slow (hours per scan).
- **Confocal Grid Structured Illumination (CGSI):** Can measure large XY areas (>0.5 mm2) and deep Z heights (>1 mm) in a single scan. Enables multi-surface imaging for enclosed channels.
- **Dye absorption method (muSCAPE):** Fill channels with colorimetric dye, scan with flatbed scanner at 2 um resolution, calculate depth from Lambert-Beer's law. Simple and low-cost but moderate accuracy.

### 4.2 Bonding Quality Verification

Poor bonding is the primary cause of microfluidic device failure. Multiple methods exist to assess bond quality.

#### Visual Inspection

**Procedure:**
1. Examine the bonded interface under a stereomicroscope (5-40x)
2. Look for interference fringes (Newton's rings) indicating unbonded areas
3. Check for trapped air bubbles at the bond interface
4. Verify uniform contact across the entire bonding area

**Indicators of good bonding:**
- Uniform appearance with no fringes or voids
- No visible gap between layers
- Channels have crisp edges without smearing (indicates no adhesive overflow)

**Indicators of poor bonding:**
- Newton's rings (colored fringes) indicating partial contact
- Air bubbles trapped at the interface
- Visible gaps or delamination at edges
- Channel deformation (over-bonding with excessive pressure/temperature)

#### Burst Pressure Testing

**Procedure:**
1. Block all outlet ports
2. Connect a pressure source (compressed air or nitrogen) to one inlet
3. Include a pressure gauge in the line
4. Slowly increase pressure (ramp at ~10 kPa/min)
5. Observe the device under a microscope while pressurizing
6. Record the pressure at which the first leak or delamination occurs

**Typical burst pressures:**
- PDMS-PDMS (O2 plasma bond): 200-350 kPa (30-50 psi)
- PDMS-glass (O2 plasma bond): 200-500 kPa (30-70 psi)
- Glass-glass (thermal fusion bond): >1 MPa (>145 psi)
- Glass-glass (anodic bond): >2 MPa (>290 psi)
- COC-COC (thermal bond): 300-800 kPa (45-115 psi)
- 3D-printed resin (monolithic): depends on print; typically 100-500 kPa

**Acceptance criteria:** Burst pressure should be at least 3-5x the maximum operating pressure of the device.

#### Tensile / Peel Testing

For quantitative bond strength measurement:
- **Tensile test:** Glue pull stubs to each side of the bonded device, pull apart in a tensile tester. Measures bond strength in Pa.
- **Razor blade test:** Insert a razor blade at the bond interface edge and measure crack propagation length. Allows calculation of surface energy.
- **Blister test:** Pressurize a circular area at the bond interface and measure deformation.

### 4.3 Leak Testing

#### Pressure Decay Test (Most Common)

**Procedure:**
1. Fill all channels with test fluid (DI water or colored dye solution)
2. Seal all outlets
3. Apply a known pressure to one inlet (e.g., 50-100 kPa above operating pressure)
4. Close the inlet valve to isolate the system
5. Monitor pressure over time (5-30 minutes)
6. A pressure drop indicates a leak

**Acceptance criteria:**
- Pressure decay <1% over 30 minutes is generally acceptable for research devices
- For production devices: <0.1% pressure decay over the test period
- High-precision testing: use flow sensors with nL/min resolution to quantify leak rate

#### Visual Leak Testing with Dye

**Procedure:**
1. Fill channels with a colored dye solution (e.g., food coloring in water, or fluorescein)
2. Apply moderate pressure (operating pressure or 1.5x operating pressure)
3. Observe under microscope for 5-15 minutes
4. Look for dye leaking from channel edges into the bond interface
5. For fluorescent dye: use fluorescence microscopy for higher sensitivity

**Advantages:** Simple, inexpensive, immediately shows the location of leaks. Fluorescent dye detection can identify leaks as small as nanoliters.

#### Mass Loss/Gain Test

1. Weigh the filled, pressurized device on an analytical balance
2. Wait a defined period under pressure
3. Re-weigh
4. Mass change indicates leak volume (1 mg ~ 1 uL for water)

### 4.4 Channel Roughness Measurement

Surface roughness affects flow resistance, mixing behavior, cell adhesion, and optical clarity.

#### AFM (Atomic Force Microscopy)

**Procedure:**
1. Prepare a sample of the channel surface (open chip or cut section)
2. Mount on AFM sample stage
3. Use tapping mode (intermittent contact) to avoid damaging soft surfaces
4. Scan a representative area (typically 5x5 um to 50x50 um)
5. Extract roughness parameters: Ra (arithmetic average), Rq (RMS), Rz (peak-to-valley)

**Specifications:**
- Lateral resolution: 5-10 nm
- Vertical resolution: sub-nanometer (0.1 nm typical)
- Measurement area: up to ~100x100 um per scan
- Cannot measure inside enclosed channels

**Typical values for microfluidic surfaces:**
- Polished glass: Ra < 1 nm
- PDMS (cast from SU-8 master): Ra = 0.5-5 nm
- Etched silicon (DRIE): Ra = 5-50 nm (scalloping from Bosch process)
- 3D-printed resin (SLA/DLP): Ra = 50-500 nm (layer lines)
- Hot-embossed COC/COP: Ra = 1-10 nm (depends on mold quality)
- Laser-ablated glass: Ra = 100 nm - 1 um

#### Optical Profilometry for Roughness

Optical profilometers (white-light interferometry or confocal) can also measure roughness over larger areas:
- Measurement area: up to several mm2
- Vertical resolution: <1 nm (interferometric)
- Faster than AFM for larger-area roughness characterization
- Better for production QC where per-sample time is limited

#### SEM for Qualitative Roughness Assessment

While SEM cannot directly quantify roughness parameters, it provides excellent qualitative assessment:
- Reveals surface texture, grain structure, and fabrication artifacts
- Shows scalloping from DRIE, layer lines from 3D printing, or tool marks from CNC
- Useful for comparing process variations side by side

### 4.5 Contact Angle Measurement for Surface Verification

Contact angle measurement is the primary method for verifying that surface treatments have been applied correctly.

#### Sessile Drop Method (Standard)

**Equipment:** Contact angle goniometer (Kruss DSA, Biolin Theta, Ossila, or similar)

**Procedure:**
1. Place the treated surface on the goniometer stage
2. Dispense a small droplet of DI water (1-5 uL) using the instrument's automated syringe
3. Capture a side-view image of the droplet on the surface
4. Software fits the droplet profile and calculates the contact angle

**Key parameters:**
- Droplet volume: 1-5 uL (smaller is better for small samples)
- Wait time: 5-10 seconds after deposition for equilibrium
- Measure at least 3-5 spots per sample for statistical significance
- Report mean +/- standard deviation

#### Reference Contact Angle Values

| Surface | Expected Contact Angle |
|---------|----------------------|
| Native PDMS | 105-115 degrees |
| O2 plasma-treated PDMS (fresh) | 10-30 degrees |
| O2 plasma-treated PDMS (24h aged) | 60-90 degrees |
| PVA-coated PDMS (3 coats) | 20-30 degrees |
| Pluronic F127-coated PDMS | 40-60 degrees |
| Clean glass (piranha or plasma) | <10 degrees |
| Native glass (ambient) | 30-50 degrees |
| PEG-silane-coated glass | 30-45 degrees |
| Fluorosilane-coated glass | 105-120 degrees |
| Parylene C | 80-90 degrees |

#### Low-Cost Contact Angle Measurement

For labs without a dedicated goniometer:
1. Place a known-volume droplet (e.g., 2 uL from a calibrated micropipette) on the surface
2. Photograph from the side using a USB microscope or DSLR with macro lens
3. Ensure the camera is level with the surface
4. Measure the contact angle from the image using free software (ImageJ with the Contact Angle plugin, or OpenDrop)

**Accuracy:** +/- 2-5 degrees with careful technique (vs. +/- 0.1-1 degree for commercial goniometers).

#### Dynamic Contact Angle (Advancing/Receding)

For more complete surface characterization:
- **Advancing angle:** Measured while adding volume to the droplet. Indicates the hydrophobicity of the least wettable domains.
- **Receding angle:** Measured while withdrawing volume. Indicates the hydrophilicity of the most wettable domains.
- **Contact angle hysteresis** = advancing - receding. Large hysteresis (>20 degrees) indicates chemical heterogeneity or roughness. Small hysteresis (<10 degrees) indicates a uniform surface.

### 4.6 QC Checklist for Microfluidic Device Fabrication

A practical checklist for validating fabricated devices before use:

- [ ] **Visual inspection:** No visible defects, delamination, or particulates under stereomicroscope
- [ ] **Channel dimensions:** Width and depth within +/- 10% of design (or tighter, per application)
- [ ] **Bonding quality:** No Newton's rings, voids, or unbonded regions visible at the interface
- [ ] **Leak test:** Pressure decay <1% at 1.5x operating pressure over 30 minutes
- [ ] **Flow test:** DI water flows through all channels without blockage or air trapping
- [ ] **Surface treatment verification:** Contact angle within expected range for the applied coating
- [ ] **Optical clarity:** No haze, bubbles, or surface damage in the observation region (if optical readout is used)
- [ ] **Port integrity:** All inlet/outlet ports accept tubing or fittings without cracking or leaking

---

## References and Resources

### Chip Cleaning
- [How to Clean Your Microfluidic Chip (Darwin Microfluidics)](https://blog.darwin-microfluidics.com/how-to-clean-your-microfluidic-chip/)
- [Efficient Cleaning of a Microfluidic Chip (RSC Chips and Tips)](https://blogs.rsc.org/chipsandtips/2016/02/08/efficient-cleaning-of-a-microfluidic-chip/)
- [Practical Guide to Cleaning Microfluidic Devices (Thierry Corp)](https://www.thierry-corp.com/plasma-treatment-articles/the-practical-guide-to-cleaning-microfluidic-devices/)
- [Ultrasonic Cleaning of Microfluidic Chips (BubClean)](https://www.bubclean.nl/microfluidic-chips-cleaning/)

### Surface Functionalization
- [Anti-fouling Coatings of PDMS Devices (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4414934/)
- [Recent Advances in Nonbiofouling PDMS Surface Modification (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5501164/)
- [PEG Coating for Hydrophilicity Enhancement of PDMS (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S0257897216313470)
- [Hydrophilic Surface Modification of PDMS via PVA Deposition (Nature Microsystems & Nanoengineering)](https://www.nature.com/articles/micronano201691)
- [PLL-g-PEG for Microfluidic Devices (Langmuir)](https://pubs.acs.org/doi/abs/10.1021/la060198m)
- [Efficient One-Step PEG-Silane Passivation (ACS AMI)](https://pubs.acs.org/doi/abs/10.1021/acsami.8b15796)
- [PLL-g-PEG Coatings (SuSoS)](https://susos.com/beschichtungsprodukte/life-science/pegilierte-beschichtungen/pll-g-peg-beschichtungen/)
- [Fouling Resistant PEG Coatings (Sigma-Aldrich)](https://www.sigmaaldrich.com/US/en/technical-documents/technical-article/materials-science-and-engineering/nanoparticle-and-microparticle-synthesis/fouling-resistant)
- [Parylene C as Multipurpose Material for Microfluidics (MDPI Polymers)](https://www.mdpi.com/2073-4360/15/10/2277)
- [Parylene-C Coating Protects 3D Printed Devices (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC10754061/)
- [Fluorosilane Surface Treatments (Emulseo)](https://www.emulseo.com/products/surface-treatments/)
- [Hydrophilic and Hydrophobic Coatings for Droplet Generation (Darwin Microfluidics)](https://blog.darwin-microfluidics.com/hydrophilic-and-hydrophobic-coatings-for-droplet-generation/)
- [Surface Modification of PDMS via Pluronic (Nature Scientific Reports)](https://www.nature.com/articles/s41598-019-43625-5)
- [BSA Surface Properties on PDMS Microfluidic Chips (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC2835281/)
- [PDMS Surface Modification (SimpleMicrofluidics)](https://simplemicrofluidics.com/diy-microfluidics-prototyping/surface-modification-techniques-for-pdms-microfluidic-circuits/)
- [Review of Methods to Modify PDMS Surface Wettability (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11205751/)

### Chip-to-World Interfacing
- [3D Printing Solutions for Microfluidic Chip-To-World Connections (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6187806/)
- [Connector-Free World-to-Chip Interconnection (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6471718/)
- [Universal Magnetic Connectors for Microfluidic Devices (MDPI)](https://www.mdpi.com/2072-666X/15/6/803)
- [3D Microfluidic Chip Holders (Universitat Bremen)](https://www.uni-bremen.de/en/imsas/research/projects-group-vellekoop/3d-microfluidic-chip-holders-and-systems)
- [Handling Frames (microfluidic ChipShop)](https://www.microfluidic-chipshop.com/catalogue/accessories/handling-frames/)
- [ISO 22916:2022 Standard](https://www.iso.org/standard/74157.html)
- [Design Guideline for Microfluidic Interfacing (EnablingMNT)](https://enablingmnt.com/wp-content/uploads/2019/11/Design-for-Microfluidic-Interfacing-White-Paper-part-1-version-3-1.pdf)
- [3D Printed Microfluidic Connectors (Aline)](https://www.alineinc.com/3d-printed-microfluidic-connectors/)
- [PCB-Based Microfluidics: Recent Advances (Nature Microsystems & Nanoengineering)](https://www.nature.com/articles/s41378-025-00940-4)
- [3D Printed PCB Microfluidics (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8955900/)

### Quality Control and Metrology
- [Comparison of Measurement Protocols for Microfluidic Channels (MDPI)](https://www.mdpi.com/2673-8244/5/1/4)
- [Measuring Microchannels (Filmetrics)](https://www.filmetrics.com/applications/microfluidics)
- [Wettability and Surface Roughness Measurement for Microfluidics QC (IJMQE)](https://www.metrology-journal.org/articles/ijmqe/full_html/2025/01/ijmqe240012/ijmqe240012.html)
- [Protocols for Leakage Testing (NIST)](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=934652)
- [Development of a Tool for Verifying Leakage Detection (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11857335/)
- [Overcoming Technological Barriers: Leakage Testing (Frontiers)](https://www.frontiersin.org/journals/bioengineering-and-biotechnology/articles/10.3389/fbioe.2022.958582/full)
- [Leak Resistance in Microfluidic Channels (Elveflow)](https://elveflow.com/microfluidics-research-summaries/fabrication-of-a-leak-resistant-microfluidic-chip/)
- [Microfluidic Leakage Testing Pack (Fluigent)](https://www.fluigent.com/research/instruments/packages/application-packages/microfluidic-leakage-testing-pack/)
- [Contact Angle Measurements and Wettability (Nanoscience Instruments)](https://www.nanoscience.com/techniques/tensiometry/contact-angle-measurements-and-wettability/)
- [Contact Angle Measurement Guide (Ossila)](https://www.ossila.com/pages/contact-angle-measurements-surface-wetting)
