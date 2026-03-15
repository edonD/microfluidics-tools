# Surface Treatment, Thin Film Deposition & Bonding/Sealing for Microfluidics

## 1. Thin Film Deposition

### 1.1 Sputtering Systems for Electrodes and Sensors

Sputtering is the primary method for depositing metal electrodes (Au, Pt, Ti, Cr, ITO) and sensor layers onto microfluidic chips.

#### Major Equipment Vendors

| Vendor | Key Systems | Capabilities | Approx. Price Range |
|--------|------------|--------------|---------------------|
| **Kurt J. Lesker** | Lab-18, PRO Line PVD | Combined e-beam + RF sputter; 2-4 magnetron sources; multi-pocket e-beam | $200K-$600K+ |
| **AJA International** | ATC-2200, ATC Orion series | 4-6 target positions; RF/DC co-sputtering; confocal geometry; load-lock | $150K-$500K |
| **Angstrom Engineering** | Multi-target systems | 4x 3" sputtering sources; RF and DC; configurable PVD processes | $150K-$400K |
| **Denton Vacuum** | Discovery, Explorer | Bench-top to production; magnetron sputtering | $80K-$300K |

**Key considerations for microfluidics:**
- RF sputtering required for insulating targets (SiO2, Al2O3)
- DC sputtering sufficient for metals (Au, Pt, Ti, Cr)
- Substrate compatibility: glass, silicon, polymers (with care for thermal budget)
- Typical electrode stack: Ti/Au (5-10 nm / 50-200 nm) or Cr/Au adhesion layers
- ITO (In2O3/SnO2) sputtered onto glass enables transparent electrodes for optical + electrochemical measurements

### 1.2 E-Beam and Thermal Evaporation

Both are physical vapor deposition (PVD) techniques for metal thin films.

#### E-Beam Evaporation
- Uses a high-energy electron beam directed at source material in a crucible
- Deposition rate: 0.1-100 nm/min
- Produces high-purity, dense films with excellent adhesion
- Suitable for high-melting-point materials (Au, Pt, Ti, W, SiO2)
- Better film quality and purity than thermal evaporation (no crucible contamination)
- Equipment: Lesker Lab-18, Denton Integrity, Temescal systems

#### Thermal Evaporation
- Uses resistive heating (tungsten boats/filaments) to evaporate source material
- Lower cost and simpler setup than e-beam
- Best for low-melting-point metals (Au, Ag, Al, Cr)
- Less dense films with higher impurity risk from crucible heating
- Equipment: Lesker Nano36, Kurt Lesker SPECTROS, Angstrom Amod systems

#### Comparison for Microfluidics

| Parameter | E-Beam | Thermal | Sputtering |
|-----------|--------|---------|------------|
| Film density | High | Moderate | High |
| Purity | Excellent | Good | Good |
| Step coverage | Poor (line-of-sight) | Poor (line-of-sight) | Moderate-good |
| Deposition rate | 0.1-100 nm/min | 0.1-50 nm/min | 0.1-10 nm/min |
| Material range | Very broad | Limited to low-Tm | Broadest |
| Equipment cost | $200K-$500K | $50K-$200K | $150K-$600K |
| Best for | Lift-off patterning, high-purity electrodes | Simple metal layers, prototyping | Uniform conformal coatings |

### 1.3 Parylene Coating

Parylene is a conformal polymer coating applied via chemical vapor deposition (CVD), widely used in microfluidics for biocompatibility, chemical inertness, and barrier properties.

#### Parylene Types

| Type | Properties | Microfluidic Applications |
|------|-----------|--------------------------|
| **Parylene C** | Most common; low permeability; good chemical resistance; biocompatible | Channel coatings, mold release, sensor passivation |
| **Parylene N** | Higher dielectric strength; lower coefficient of friction | Electrical insulation layers |
| **Parylene D** | Higher temperature resistance | High-temp microfluidic applications |
| **Parylene HT** | UV stable; lowest coefficient of friction | Long-term implantable devices |

#### Equipment Vendors

- **Specialty Coating Systems (SCS)**: Industry leader with 50+ years experience; PDS 2010, Labcoter 2 systems; custom production coaters
- **Para Tech Coating**: Custom parylene services
- **Kisco Conformal Coating**: Parylene deposition systems

#### CVD Process
1. **Vaporization**: Dimer powder heated to ~150C to sublimate
2. **Pyrolysis**: Dimer cracked at ~680C into reactive monomer
3. **Deposition**: Monomer condenses and polymerizes on room-temperature substrate
4. Result: Pinhole-free, conformal coating (typical thickness 0.5-50 um)

#### Key Applications in Microfluidics
- Mold release agent for PDMS casting (Parylene-C on SU-8/silicon molds)
- Biocompatible barrier coating for organ-on-chip platforms
- Structural material for MEMS-based microfluidic channels
- Anti-stiction and anti-fouling layer
- Electrical insulation for integrated electrodes

---

## 2. Surface Coatings and Treatments

### 2.1 Hydrophobic Coatings

Essential for droplet microfluidics, digital microfluidics (EWOD), and preventing aqueous wetting.

| Coating | Application Method | Contact Angle | Key Uses |
|---------|-------------------|---------------|----------|
| **Fluorosilanes** (FOTS, FDTS, PFOTS) | Vapor or liquid phase SAM | 110-120 deg | PDMS/glass droplet generators; EWOD |
| **Teflon AF** (amorphous fluoropolymer) | Spin coating, dip coating | 105-120 deg | Digital microfluidics top plate; anti-fouling |
| **Cytop** (Asahi Glass) | Spin coating | 108-115 deg | EWOD dielectric + hydrophobic layer |
| **Rain-X / commercial treatments** | Dip or spray | 90-100 deg | Quick prototyping, temporary coatings |
| **Silicone oil treatment** | Incubation | Variable | PDMS channel pre-treatment for droplets |

**Fluorosilane SAM Protocol (vapor phase):**
1. Clean substrate (O2 plasma, piranha, or UV-ozone)
2. Place substrate and fluorosilane (e.g., trichloro(1H,1H,2H,2H-perfluorooctyl)silane) in vacuum desiccator
3. Apply vacuum (10-50 mbar) for 1-12 hours at room temperature
4. Rinse with isopropanol, dry with N2
5. Optional: bake at 110C for 10 min to improve stability

### 2.2 Hydrophilic Coatings

Needed for continuous-phase aqueous microfluidics, capillary-driven flow, and preventing hydrophobic analyte adsorption.

| Coating | Application Method | Key Properties |
|---------|-------------------|----------------|
| **PEG (polyethylene glycol)** | Grafting, silane-PEG conjugates | Anti-fouling; reduces protein adsorption; water-soluble |
| **PVA (polyvinyl alcohol)** | Dip coating, adsorption | Simple application; temporary to semi-permanent |
| **PEO (polyethylene oxide)** | Surface grafting | Similar to PEG; anti-protein adsorption |
| **O2 plasma treatment** | Plasma chamber | Makes PDMS temporarily hydrophilic (reverts in hours) |
| **UV-ozone** | UV-ozone cleaner | Similar to plasma; slower but gentler |
| **Glass-like coatings** | SiO2 sputtering/PECVD | Permanent hydrophilic; on polymer substrates |

### 2.3 Anti-Fouling Coatings

Critical for biological assays, cell culture, and long-term device operation.

| Coating | Mechanism | Duration | Application |
|---------|-----------|----------|-------------|
| **PLL-g-PEG** | Electrostatic adsorption of PLL backbone; PEG brush repels proteins | Hours to days | Incubate 0.1-1 mg/mL solution, 30-60 min; rinse |
| **BSA blocking** | Protein adsorption saturates surface | Hours | 1-5% BSA in PBS, 30-60 min incubation |
| **Pluronic F-127** | PEO-PPO-PEO triblock copolymer adsorption | Hours to days | 1-5% solution, incubate 1-12 hr |
| **PEG-silane SAMs** | Covalent attachment | Weeks to months | Silane coupling on activated surfaces |
| **Zwitterionic polymers** | Hydration layer repels proteins | Weeks to months | Grafting or coating |
| **Parylene + PEG** | Dual-layer approach | Months | CVD parylene then PEG grafting |

### 2.4 Self-Assembled Monolayer (SAM) Treatments

SAMs provide molecularly precise surface modification for microfluidic channels.

#### Silane SAMs (on glass, silicon, oxidized PDMS)

**Liquid Phase Protocol:**
1. Clean substrate: piranha solution (3:1 H2SO4:H2O2) for 30 min, or O2 plasma 1 min
2. Rinse with DI water, dry with N2
3. Prepare silane solution: 1-5% (v/v) in anhydrous toluene or ethanol
4. Immerse substrate for 30 min to 12 hr at room temperature
5. Rinse sequentially: toluene, ethanol, DI water
6. Cure at 110C for 1 hr (optional, improves stability)

**Vapor Phase Protocol (preferred for microfluidic channels):**
1. Clean substrate (plasma or piranha)
2. Place in vacuum desiccator with 50-100 uL silane in adjacent vial
3. Pull vacuum to ~10 mbar
4. Leave 2-12 hr at room temperature (or 1 hr at 60-80C)
5. Rinse and dry

**Common silanes:**
- APTES (3-aminopropyltriethoxysilane) -- amine-terminated, for biomolecule attachment
- MPTMS (3-mercaptopropyltrimethoxysilane) -- thiol-terminated, for gold nanoparticle binding
- OTS (octadecyltrichlorosilane) -- hydrophobic, C18 chain
- FOTS (perfluorooctyltrichlorosilane) -- superhydrophobic

#### Thiol SAMs (on gold surfaces)

**Protocol:**
1. Clean gold surface: UV-ozone 10 min, or O2 plasma 30 sec
2. Prepare thiol solution: 1-10 mM alkanethiol in ethanol
3. Immerse substrate for 12-24 hr at room temperature
4. Rinse with ethanol, dry with N2
5. Use immediately or store under inert atmosphere

**Common thiols:**
- Alkanethiols (C6-C18) -- hydrophobic SAMs
- PEG-thiol -- anti-fouling surfaces
- 11-mercaptoundecanoic acid (MUA) -- carboxyl-terminated for bioconjugation
- Cysteamine -- amine-terminated for further functionalization

---

## 3. Bonding and Sealing Methods

### 3.1 Thermal Bonding

Relies on heating polymer substrates near or above glass transition temperature (Tg) under pressure.

#### Parameters by Material

| Material | Tg (C) | Bonding Temp (C) | Pressure (MPa) | Time (min) | Bond Strength |
|----------|--------|-------------------|-----------------|------------|---------------|
| **PMMA** | 105 | 85-110 | 0.5-3.0 | 10-30 | Up to 808 kPa |
| **COC** (TOPAS) | 70-180 (grade dependent) | Tg - 10 to Tg | 0.5-2.0 | 5-20 | 0.5-2.0 MPa |
| **COP** (Zeonor) | 100-163 | Tg - 10 to Tg | 0.5-2.0 | 10-30 | 0.5-1.5 MPa |
| **PC** | 150 | 140-155 | 1.0-3.0 | 10-30 | 1.0-3.0 MPa |
| **PS** | 100 | 90-105 | 0.5-2.0 | 10-20 | 0.5-1.5 MPa |

**Advantages:** No additional materials; optically clear; biocompatible; scalable.
**Disadvantages:** Risk of channel deformation near Tg; narrow process window; requires flat surfaces.

**Tips:**
- Use hot press with precise temperature control (within 1C)
- Bonding rate of 95.3% achievable with optimized PMMA parameters
- Surface activation (O2 plasma) before bonding can lower required temperature
- For PDMS-glass: O2 plasma both surfaces, bring into contact within 60 sec, bake 70C for 1 hr

### 3.2 Solvent Bonding

Uses a solvent to partially dissolve the polymer surface, creating chain entanglement upon evaporation.

#### Solvent-Material Combinations

| Polymer | Effective Solvents | Application Method | Notes |
|---------|-------------------|-------------------|-------|
| **PMMA** | Chloroform, acetone, IPA/methanol mixtures, ethylene dichloride | Liquid or vapor | Chloroform vapor gives best results; reduces deformation |
| **COC/COP** | Cyclohexane, decalin, toluene | Liquid or vapor | Cyclohexane most common; brief exposure critical |
| **PC** | Dichloromethane (DCM), chloroform | Liquid or vapor | Very fast dissolution -- careful timing needed |
| **PS** | Acetone, toluene, cyclohexane | Vapor preferred | Acetone vapor at RT effective |

**Vapor Solvent Bonding Protocol (preferred):**
1. Place solvent in shallow dish inside sealed chamber
2. Expose polymer surfaces to solvent vapor for 30 sec to 5 min (material dependent)
3. Remove from chamber; allow excess solvent to evaporate (10-30 sec)
4. Align and press parts together under light pressure (0.1-0.5 MPa)
5. Hold at room temperature or mildly elevated temperature for 10-30 min

**Advantages:** Lower temperature than thermal bonding; maintains channel geometry; strong bonds.
**Disadvantages:** Solvent compatibility concerns; potential channel deformation if over-exposed; requires fume hood.

### 3.3 Adhesive Bonding

#### Pressure-Sensitive Tapes (PSA)

| Product | Thickness (um) | Material | Key Properties |
|---------|----------------|----------|----------------|
| **3M 9795R** | 140 (total) | PP film + silicone PSA | Microfluidic diagnostic tape; optically clear; designed for channel sealing |
| **3M 9969** | Variable | Adhesive transfer tape | Medical-grade; microfluidic diagnostics |
| **3M 468MP** | 130 | Acrylic adhesive transfer | High shear strength; biocompatible |
| **ARcare 90106** | 25 (adhesive) | Acrylic on PET carrier | Exceptional structural resolution; biocompatible |
| **ARcare 90445** | 81 (total) | Double-sided acrylic | Robust shear and tensile adhesion |
| **ARcare 92712** | 50 (adhesive) | Acrylic transfer tape | Strong adhesion; biocompatible |

**Application Tips:**
- Cut tape with laser cutter, craft cutter (Silhouette, Cricut), or xurography
- Tape defines channel height -- choose thickness accordingly
- Can laminate multiple layers for complex 3D architectures
- Cost-effective rapid prototyping method

#### UV-Curable Adhesives

| Product | Viscosity (cP) | Cure Wavelength | Bond Strength | Key Properties |
|---------|----------------|-----------------|---------------|----------------|
| **Norland NOA 61** | 300 | 365 nm UV | High | Optically clear; one-part; 100% solids; excellent glass/glass bonding |
| **Norland NOA 63** | 200 | 365 nm UV | High | Lower viscosity than NOA 61; good wicking into gaps |
| **Norland NOA 68** | 5000 | 365 nm UV | Very high | Higher viscosity; gap-filling |
| **Norland NOA 81** | 300 | 365 nm UV | High | Flexible when cured; good for polymer substrates |

**NOA Bonding Protocol:**
1. Apply thin layer of NOA via spin coating, stamping, or capillary filling
2. Align substrates
3. Expose to 365 nm UV light (5-15 J/cm2 total dose)
4. Post-cure at 50C for 12 hr (optional, improves bond strength)

**Advantages:** Room temperature process; excellent optical clarity; biocompatible options.
**Disadvantages:** Potential channel clogging if adhesive flows into channels; UV exposure required.

### 3.4 Ultrasonic Welding

Uses high-frequency vibration (typically 20-40 kHz) to generate localized heat at the interface between thermoplastic parts.

**Key Parameters:**
- Weld time: 4-6 seconds typical
- Weld load: 5-7 N
- Frequency: 20-40 kHz
- Energy directors (raised ridges) on one surface focus energy at bond line

**Advantages:**
- Ultra-fast process (seconds vs. minutes/hours for thermal bonding)
- No adhesives or solvents required
- High bond strength
- Near-100% electrode functionality yield when bonding over thin-film electrodes
- Cost-efficient for production

**Disadvantages:**
- Requires energy director features molded into parts
- Equipment cost ($5K-$50K for bench-top)
- Limited to thermoplastics
- Potential for particle generation

**Best for:** Injection-molded thermoplastic devices, production-scale manufacturing, devices with integrated electrodes.

### 3.5 PDMS Bonding Methods

PDMS is the most common microfluidic material and has multiple bonding options.

| Method | To PDMS | To Glass | To Silicon | To Thermoplastics |
|--------|---------|----------|------------|-------------------|
| **O2 plasma** | Excellent (irreversible) | Excellent | Excellent | Possible (with surface activation) |
| **Corona discharge** | Good | Good | -- | Limited |
| **UV-ozone** | Good | Good | Good | Limited |
| **APTES intermediary** | -- | -- | -- | Good (PDMS to PMMA, PC, PET, COC) |
| **Uncured PDMS glue** | Excellent | Good | Good | Limited |
| **Reversible (conformal)** | Moderate (Van der Waals) | Moderate | Moderate | Poor |

**Plasma Bonding Protocol (PDMS-Glass):**
1. Clean both surfaces (IPA rinse, N2 dry)
2. O2 plasma: 30-60 sec, 30-100 W, 200-500 mTorr
3. Bring surfaces into contact within 60 sec of plasma treatment
4. Light pressure by hand or with roller
5. Bake at 65-80C for 1-12 hr (optional but improves strength)
6. Bond strength: typically > 200 kPa (device failure before delamination)

---

## 4. Bonding Method Selection Guide

### Material-Method Compatibility Matrix

| Material Combination | Thermal | Solvent | PSA Tape | UV Adhesive | Plasma | Ultrasonic |
|---------------------|---------|---------|----------|-------------|--------|------------|
| PDMS - PDMS | -- | -- | OK | OK | **Best** | -- |
| PDMS - Glass | -- | -- | OK | Good | **Best** | -- |
| PDMS - Thermoplastic | -- | -- | OK | Good | Possible | -- |
| PMMA - PMMA | Good | **Best** | Good | Good | Limited | Good |
| COC - COC | **Best** | Good | Good | Good | Limited | Good |
| COP - COP | **Best** | Good | Good | Good | Limited | Good |
| PC - PC | Good | Good | Good | Good | Limited | Good |
| PS - PS | Good | Good | Good | Good | Limited | Good |
| Glass - Glass | Fusion | -- | OK | **Best** | Anodic | -- |
| Glass - Silicon | Anodic | -- | -- | OK | -- | -- |
| Mixed polymers | Limited | Limited | **Best** | Good | Limited | Limited |

### Decision Flowchart

1. **Is it PDMS?** --> O2 plasma bonding (standard, well-characterized)
2. **Rapid prototyping?** --> PSA tape or UV adhesive (fastest, most flexible)
3. **Thermoplastic production?** --> Thermal bonding (scalable, no consumables)
4. **Need to preserve thin-film electrodes?** --> Ultrasonic welding (best electrode survival)
5. **Mixed materials?** --> PSA tape or UV adhesive (most material-agnostic)
6. **Lowest channel deformation?** --> Solvent vapor bonding (lower temperature)
7. **Highest bond strength needed?** --> Thermal bonding or plasma bonding (strongest)

---

## 5. Sources and References

- [Kurt J. Lesker - Sputtering Targets](https://www.lesker.com/materials-division.cfm?section=sputtering-targets)
- [AJA Sputtering System - UNL](https://thinfilm.unl.edu/aja-sputtering/)
- [Specialty Coating Systems - Parylene](https://scscoatings.com/parylene-coatings/)
- [Parylene-C in Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC6187609/)
- [Parylene-C OSTE Molds for PDMS - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12191429/)
- [Hydrophobic/Hydrophilic Coatings for Droplet Generation - Darwin Microfluidics](https://blog.darwin-microfluidics.com/hydrophilic-and-hydrophobic-coatings-for-droplet-generation/)
- [Fouling Resistant PEG Coatings - Sigma-Aldrich](https://www.sigmaaldrich.com/US/en/technical-documents/technical-article/materials-science-and-engineering/nanoparticle-and-microparticle-synthesis/fouling-resistant)
- [Microfluidic Coatings - Aculon](https://www.aculon.com/microfluidic/)
- [PDMS Surface Modification - TE Connectivity](https://www.te.com/en/industries/medical-technologies/ivd-microfluidic-solutions/articles-overview/hydrophobic-vs-hydrophilic.html)
- [Organosilane Deposition for Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC3364836/)
- [Self-Assembled Silane Monolayers Protocol](https://arxiv.org/abs/1212.0998)
- [PDMS Bonding Technologies Review - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC8394141/)
- [Solvent Bonding PMMA and COP - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC5352265/)
- [Thermoplastic Microfluidic Bonding Review - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC8949906/)
- [Double-Sided Tape in Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11118809/)
- [3M Microfluidic Diagnostic Tape 9795R](https://www.solventum.com/en-us/home/f/b00042377/)
- [Norland NOA 61 Datasheet](https://www.gluespec.com/Materials/adhesive/norland/noa-61)
- [Ultrasonic vs Thermal Bonding for Electrodes - MDPI](https://www.mdpi.com/1424-8220/16/11/1795)
- [Thermoplastic Microfluidics Fabrication and Bonding - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC9503322/)
- [E-Beam vs Thermal Evaporation](https://www.sputtertargets.net/blog/electron-beam-evaporation-vs-thermal-evaporation.html)
- [E-Beam Evaporation Overview - Wevolver](https://www.wevolver.com/article/what-is-e-beam-evaporation-and-how-does-it-compare-to-other-pvd-methods)
- [Gold Deposition - DTU LabAdviser](https://labadviser.nanolab.dtu.dk/index.php?title=Specific_Process_Knowledge/Thin_film_deposition/Deposition_of_Gold)
