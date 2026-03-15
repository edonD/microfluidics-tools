# Soft Lithography and PDMS Fabrication for Microfluidics

## Overview

Soft lithography is the set of replica molding techniques used to transfer micro/nanostructures from a master mold (typically SU-8 on silicon, fabricated via photolithography) into a soft elastomer, most commonly PDMS (polydimethylsiloxane). The resulting PDMS slab is then bonded to a flat substrate (glass or another PDMS layer) to create enclosed microfluidic channels. This document covers the complete PDMS fabrication workflow, bonding techniques, and alternatives to PDMS.

---

## 1. PDMS: Sylgard 184 -- The Standard Material

### What It Is

Sylgard 184 (Dow, formerly Dow Corning) is a two-part silicone elastomer kit consisting of a base (vinyl-terminated polydimethylsiloxane) and a curing agent (platinum-catalyzed cross-linker with copolymer of methylhydrosiloxane and dimethylsiloxane). It is the de facto standard material for academic microfluidics research.

### Material Properties

| Property | Value |
|----------|-------|
| Mix ratio | 10:1 (base : curing agent) by weight |
| Pot life (working time) | ~2 hours at room temperature |
| Viscosity (mixed) | ~3,500 cP |
| Cured Young's modulus | ~1.5--2.5 MPa (at 10:1 ratio) |
| Optical transparency | >95% in visible range (240--1100 nm) |
| Refractive index | 1.41 |
| Gas permeability | High (permeable to O2, CO2, N2) -- good for cell culture |
| Water contact angle | ~110 deg (hydrophobic, native) |
| Biocompatible | Yes (USP Class VI) |
| Operating temperature | -45 C to +200 C |
| Dielectric strength | ~21 kV/mm |

### Cost

- **Sylgard 184 kit (0.5 kg):** ~$60--$90 (sufficient for ~20--50 devices depending on thickness)
- **Sylgard 184 kit (1.1 kg):** ~$80--$120
- **Sylgard 184 kit (3.9 kg):** ~$200--$300
- Available from Sigma-Aldrich, Fisher Scientific, Darwin Microfluidics, Ellsworth Adhesives, and direct from Dow

### Complete Casting Protocol

#### Step 1: Weighing and Mixing

1. Tare a clean disposable cup on a precision balance
2. Weigh out PDMS base (e.g., 40 g)
3. Add curing agent at 10:1 ratio (e.g., 4 g for 40 g base)
4. Mix thoroughly with a plastic fork or spatula for 3--5 minutes until uniformly cloudy with bubbles
5. Note: Varying the ratio changes mechanical properties:
   - 5:1 = stiffer (~4 MPa), less flexible
   - 10:1 = standard (~2 MPa)
   - 20:1 = softer (~0.5 MPa), more flexible, useful for valves (Quake-style)

#### Step 2: Degassing

1. Place mixed PDMS in a vacuum desiccator connected to a vacuum pump
2. Apply vacuum (~25--30 inHg / ~85--100 kPa below atmosphere)
3. PDMS will foam dramatically -- use an oversized container (3--4x the volume of PDMS) to prevent overflow
4. Release vacuum periodically to collapse large bubbles
5. Continue until PDMS is completely clear and bubble-free (typically 15--45 min)
6. Alternative: centrifugal degassing at 2000 rpm for 5 min (faster but requires centrifuge with large cups)

#### Step 3: Pouring Over Master

1. Place silanized SU-8 master in a Petri dish or aluminum foil boat
2. Pour degassed PDMS slowly over master to desired thickness:
   - Thin layer (~50--200 um): spin coat PDMS at 500--3000 rpm (for membrane layers)
   - Standard thickness (~3--5 mm): pour and let self-level
   - Thick layer (~5--10 mm): pour more; thicker devices are easier to handle and punch
3. If bubbles appear during pouring, briefly return to vacuum desiccator (5--10 min)
4. Ensure PDMS covers all features with adequate margin

#### Step 4: Curing

| Temperature | Time | Notes |
|-------------|------|-------|
| Room temperature (~25 C) | 24--48 hours | Handleable at 24 hr, full cure at ~7 days. Minimal thermal stress. |
| 65 C | 4 hours | Common lab protocol. Good balance of speed and low stress. |
| 80 C | 2--2.5 hours | Most commonly cited protocol for microfluidics. |
| 100 C | 45--60 min | Faster but more thermal stress; can cause slight feature distortion. |
| 150 C | 10 min | Very fast but risk of thermal warpage and delamination from master. |

**Recommended:** 65--80 C for 2--4 hours in a convection oven. Avoid rapid cooling after curing.

#### Step 5: Demolding (Peeling)

1. Allow cured PDMS to cool to room temperature
2. Use a scalpel or razor blade to carefully cut around the perimeter of the device
3. Gently peel PDMS from the master, starting from one corner
4. Work slowly -- rushing can tear fine features or damage the master
5. A well-silanized master should release easily; if PDMS tears on the mold, re-silanize

#### Step 6: Port Punching

1. Use a biopsy punch (typically 0.75 mm, 1.0 mm, or 1.5 mm diameter depending on tubing)
2. Punch through the PDMS at inlet/outlet locations from the channel side (feature side down)
3. Punch straight through; twist and pull to remove core
4. For best results, punch on a soft cutting mat
5. Match punch size to tubing OD for friction-fit connections:
   - 0.75 mm punch for 1/32" OD tubing
   - 1.0 mm punch for PEEK tubing
   - 1.5 mm punch for Tygon/silicone tubing (1/16" OD)

#### Step 7: Cleaning

1. Rinse PDMS slab with IPA, then DI water
2. Blow dry with N2 gun or filtered air
3. Use Scotch tape to remove surface particles from the channel side
4. Optionally sonicate in IPA for 5 min to remove debris from channels

---

## 2. Plasma Bonding

### Oxygen Plasma Bonding (Standard Method)

#### How It Works

Oxygen plasma treatment generates reactive oxygen species that:
1. Remove organic contaminants from surfaces
2. Convert surface Si-CH3 groups (hydrophobic) to Si-OH silanol groups (hydrophilic)
3. When two treated surfaces are brought into contact, silanol groups condense to form covalent Si-O-Si siloxane bonds
4. This creates an irreversible, hermetic bond that can withstand >30 psi in typical microfluidic devices

#### Process Parameters

| Parameter | Typical Range | Notes |
|-----------|--------------|-------|
| Gas | O2 (preferred) or air | O2 gives more consistent results; air works but is less efficient |
| Pressure | 200--600 mTorr | Low vacuum range |
| RF Power | 10--30 W (Harrick); varies by system | Too high damages PDMS surface |
| Exposure time | 15--60 seconds | 30 s typical. >2 min causes surface cracking and reduces bond quality |
| Contact time after treatment | <60 seconds | Must bring surfaces into contact quickly after plasma exposure; surface reverts to hydrophobic within minutes |
| Post-bond bake | 80--90 C for 15--30 min | Strengthens bond; optional but recommended |

#### Critical Tips

- **Do not over-treat:** >2 min plasma exposure causes PDMS surface cracking and actually reduces bond strength
- **Speed matters:** After plasma treatment, silanol groups on PDMS recombine within 5--30 minutes, reverting to hydrophobic. Bond surfaces within 60 seconds of treatment.
- **Cleanliness is essential:** Any particles or contamination between surfaces will cause bond failure (leaks)
- **Uniform contact:** Use a roller or gentle finger pressure from center outward to avoid trapping air bubbles at the interface

### Plasma Bonding Equipment

#### Harrick Plasma Cleaners

The most popular plasma systems for PDMS bonding in academic microfluidics labs.

| Model | Chamber Size | Power | Voltage | Notes |
|-------|-------------|-------|---------|-------|
| PDC-32G (Basic) | 1.75" dia x 6.5" | 18 W max | 115V/230V | Entry-level, smallest chamber |
| PDC-001 / PDC-002 (Expanded) | 4" dia x 6.75" | 18 W max | 115V (001) / 230V (002) | Most popular model for microfluidics. Fits glass slides and small wafers. |
| PDC-001-HP / PDC-002-HP (High Power Expanded) | 4" dia x 6.75" | 30 W max | 115V / 230V | 2x cleaning rate of standard Expanded model |

**Price range:** ~$4,000--$8,000 depending on model and accessories (flow controller, vacuum pump sold separately). Vacuum pump adds ~$1,000--$2,000.

**Pros:** Compact benchtop unit, simple to operate, widely cited in literature, good for PDMS-glass and PDMS-PDMS bonding.
**Cons:** Small chamber limits batch size; basic models lack precise gas flow control.

#### Diener Electronic

German manufacturer of plasma systems. Broader range from benchtop to industrial.

| Series | Type | Notes |
|--------|------|-------|
| Zepto | Compact benchtop | Small chamber, good for lab prototyping |
| Nano | Benchtop | Mid-range, commonly used in academic labs |
| Femto | Benchtop | Popular for microfluidics bonding |
| Pico | Larger benchtop/floor | Higher capacity for wafer-scale processing |
| Tetra | Industrial | Production-scale, rack-mounted |

**Price range:** ~$5,000--$25,000+ depending on model, chamber size, and options. Femto and Nano models typically $8,000--$15,000.

#### Henniker Plasma

UK-based manufacturer, strong in academic/research markets.

| Model | Chamber | Notes |
|-------|---------|-------|
| HPT-FI (4" and 6" versions) | Small | Entry-level for basic plasma cleaning and PDMS bonding |
| HPT-100 | Benchtop | Research grade, good repeatability |
| HPT-200 | Benchtop | Most commonly used for microfluidics PDMS bonding |
| HPT-300 | Larger | Multiple tray loading, higher throughput |
| HPT-500 | Largest | Multiple trays, production capable |

**Price range:** ~$5,000--$20,000+ depending on model.

#### PIE Scientific (Tergeo)

- Tergeo plasma cleaner: alternative to Harrick, good for microfluidics
- Features real-time plasma monitoring
- Price range: ~$5,000--$10,000

### Corona Treatment (Low-Cost Alternative)

#### What It Is

A handheld corona discharge device creates a localized plasma in ambient air at atmospheric pressure. The corona tip is swept across the PDMS and glass surfaces for 30--60 seconds, oxidizing them similarly to O2 plasma (but less uniformly).

#### Equipment

- **Electro-Technic Products BD-20AC Laboratory Corona Treater:** ~$400--$600. The most commonly cited device in microfluidics literature.
- **Elveflow Corona Plasma Treater:** ~$300--$500.
- **Blackhole Lab Corona Treater:** ~$400.

#### Process

1. Hold corona tip ~5 mm from surface
2. Sweep slowly across entire bonding area (30--60 s per surface)
3. Immediately bring treated surfaces into contact
4. Press gently and bake at 80 C for 15--30 min

#### Pros and Cons vs. Plasma Chamber

| Aspect | Corona Treatment | O2 Plasma Chamber |
|--------|-----------------|-------------------|
| Cost | $300--$600 | $4,000--$25,000 |
| Portability | Handheld, no vacuum needed | Benchtop, requires vacuum pump |
| Uniformity | Less uniform (operator dependent) | More uniform and reproducible |
| Bond strength | Good (adequate for most microfluidics) | Excellent |
| Reproducibility | Lower | Higher |
| Safety for integrated sensors | Can damage thin-film metal layers | Gentler at low power |
| Best for | Prototyping, low-budget labs | Production, quantitative work |

---

## 3. PDMS-Glass vs. PDMS-PDMS Bonding

### PDMS-Glass Bonding

**Process:** Both the PDMS channel slab and a clean glass slide (or coverslip) are treated with O2 plasma or corona, then pressed together.

**Advantages:**
- Strongest bond (glass has abundant surface hydroxyl groups)
- Flat, rigid bottom surface is ideal for microscopy
- Glass is chemically inert and optically excellent
- Easy to visualize channels with inverted microscope
- Can use standard glass slides ($0.05--$0.50 each)

**Typical configuration:** PDMS slab (channels facing down) bonded to a glass microscope slide (25 x 75 mm) or coverslip.

**Considerations:**
- Glass thickness matters for high-NA microscopy: use #1.5 coverslip (170 um) if using oil-immersion objectives
- Borosilicate glass preferred over soda-lime for fluorescence (lower autofluorescence)

### PDMS-PDMS Bonding

**Process:** Both PDMS surfaces are treated with O2 plasma or corona, then pressed together. Same chemistry as PDMS-glass (silanol condensation).

**Advantages:**
- Enables multilayer PDMS devices (e.g., Quake-style pneumatic valves with thin membrane between layers)
- All-PDMS devices are uniformly gas-permeable (beneficial for cell culture)
- Can bond a thin PDMS membrane to a thick PDMS channel layer

**Challenges:**
- PDMS-PDMS bond is slightly weaker than PDMS-glass
- Alignment between layers is more difficult (both surfaces are flexible)
- Thin PDMS membranes are fragile and hard to handle
- Must ensure both surfaces are clean and particle-free

**Tips for multilayer alignment:**
- Use alignment marks visible through the thin PDMS layer
- Bond under a stereomicroscope
- Some researchers use a thin layer of uncured PDMS as adhesive (stamp-and-transfer technique)
- Align on a clean glass slide for stability

### Alternative Bonding Methods

| Method | Bond Type | Equipment | Notes |
|--------|-----------|-----------|-------|
| O2 Plasma | Irreversible (covalent) | Plasma cleaner | Standard method; strongest |
| Corona discharge | Irreversible (covalent) | Handheld corona treater | Lower cost, less uniform |
| UV/ozone treatment | Irreversible (covalent) | UV/ozone cleaner | Good alternative to plasma; slower |
| Uncured PDMS adhesive | Irreversible | None (use thin spin-coated PDMS layer) | "Mortar" technique; risk of channel clogging |
| Thermal bonding | Irreversible | Oven only | Partial cure + full cure bonding; less common |
| Mechanical clamping | Reversible | Clamps, screws | Reusable devices; limited pressure tolerance |
| Vacuum/conformal contact | Reversible | None | PDMS seals conformally to smooth surfaces; weak bond |
| APTES/GPTMS chemistry | Irreversible | Chemical treatment | For PDMS to non-standard substrates |

---

## 4. Alternatives to PDMS

### Why Move Beyond PDMS?

PDMS is excellent for prototyping but has real limitations:

1. **Small molecule absorption:** PDMS absorbs hydrophobic molecules (drugs, hormones, dyes, fluorescent labels). This is the single biggest problem for drug studies and quantitative biology experiments.
2. **Solvent incompatibility:** PDMS swells or dissolves in many organic solvents (chloroform, toluene, hexane, diisopropylamine, THF). Also affected by acetone, dichloromethane, and even ethanol to some degree.
3. **Scalability:** Manual casting and bonding does not scale. Each device is hand-made.
4. **Mechanical softness:** Low Young's modulus (~2 MPa) limits pressure capability and causes channel deformation under flow. High-pressure applications (>~30 psi) require thick PDMS or alternative materials.
5. **Evaporation and gas permeability:** PDMS is gas-permeable (good for cell culture O2 supply, bad for evaporation-sensitive assays, long-term storage, or volatile reagent handling).
6. **Hydrophobic recovery:** Even after plasma treatment, PDMS surfaces revert to hydrophobic within hours to days.

### Material Comparison

#### OSTEMER (Mercene Labs, Sweden)

**What it is:** Off-Stoichiometry Thiol-Ene (OSTE) polymers. A UV-curable thermoset resin system.

| Property | Value |
|----------|-------|
| Young's modulus | 0.6 MPa -- 1.2 GPa (tunable by formulation) |
| Transparency | Good (visible range) |
| Small molecule absorption | Significantly lower than PDMS |
| Solvent resistance | High (resistant to many organic solvents) |
| Fabrication | Replica molding (similar to PDMS) or injection molding |
| Bonding | Self-bonding via partial cure (no plasma needed) |
| Surface chemistry | Native thiol and allyl groups allow covalent surface modification |
| Biocompatibility | Good (OSTEMER 322 tested in cell-based assays) |

**Products:**
- OSTEMER 220 Crystal Clear: Rigid, optically clear
- OSTEMER 322 Crystal Clear: Semi-rigid, good for microfluidics
- OSTEMER 324 Flex: Flexible variant

**Cost:** ~$200--$500 per 100 g kit (significantly more expensive than PDMS by volume). Available from Mercene Labs.

**When to use:**
- Drug studies where PDMS absorption is unacceptable
- Solvent-resistant microfluidics
- Prototyping rigid devices that mimic thermoplastic properties
- When you need self-bonding without plasma equipment
- Bridging the gap between prototyping (PDMS) and production (thermoplastic)

**Fabrication:**
1. Mix resin components
2. Pour over SU-8 master (same molds as PDMS)
3. UV cure (first cure, partial -- leaves reactive surface groups)
4. Demold
5. Bond to substrate via UV or thermal second cure (no plasma needed)

#### COC (Cyclic Olefin Copolymer)

**What it is:** Amorphous thermoplastic copolymer of ethylene and norbornene. Trade names: TOPAS (Polyplastics/TOPAS Advanced Polymers), APEL (Mitsui Chemicals).

| Property | Value |
|----------|-------|
| Young's modulus | 2.6--3.2 GPa (rigid) |
| Transparency | Excellent (>90% in visible, good UV transmission down to ~250 nm) |
| Water absorption | <0.01% (5x lower than PDMS, 10--30x lower than PMMA) |
| Solvent resistance | Resistant to acids, bases, polar solvents; sensitive to non-polar solvents (toluene, hexane) |
| Autofluorescence | Very low (excellent for fluorescence assays) |
| Fabrication | Injection molding, hot embossing, CNC milling |
| Bonding | Thermal bonding, solvent bonding (cyclohexane vapor), UV-adhesive |

**Cost:** Raw material is inexpensive; fabrication cost depends on tooling (injection mold tools: $5,000--$50,000+). Per-chip cost in volume: $0.50--$5.

**When to use:**
- Production-scale microfluidics (hundreds to millions of chips)
- Fluorescence-based assays (low autofluorescence, good UV transparency)
- Aqueous-phase chemistry with no organic solvents
- Applications requiring dimensional stability and rigidity
- Disposable diagnostic chips

**Limitations:** Cannot be fabricated by soft lithography; requires hot embossing or injection molding equipment; prototyping is slower and more expensive than PDMS.

#### COP (Cyclic Olefin Polymer)

**What it is:** Homopolymer version of COC. Trade name: Zeonor/Zeonex (Zeon Corporation).

| Property | Value |
|----------|-------|
| Very similar to COC | Slightly better chemical resistance and lower birefringence |
| Fabrication | Same as COC (injection molding, hot embossing) |
| Key advantage | Better optical properties for polarization-sensitive measurements |

**When to use:** Same applications as COC. Preferred for optical biosensors, diagnostics. Zeonor 1060R is the most common grade for microfluidics.

#### PMMA (Polymethyl Methacrylate / Acrylic)

**What it is:** Common thermoplastic, widely available as cast or extruded sheets. Trade names: Plexiglass, Lucite.

| Property | Value |
|----------|-------|
| Young's modulus | 2.4--3.3 GPa (rigid) |
| Transparency | Excellent in visible (92% transmission) |
| UV transparency | Poor below 300 nm |
| Solvent resistance | Poor (attacked by acetone, chloroform, IPA) |
| Water absorption | 0.3--0.4% (much higher than COC) |
| Fabrication | CNC milling, laser cutting, hot embossing, solvent bonding |
| Bonding | Solvent bonding (chloroform, dichloromethane), thermal bonding |
| Electrophoresis | Good EOF (electroosmotic flow) properties |

**Cost:** Very low. PMMA sheets: ~$5--$20 per 12" x 12" sheet (1--3 mm thick). CNC milling: fast prototyping from sheet stock.

**When to use:**
- Electrophoresis-based separations (good EOF properties)
- Low-cost disposable chips
- Rapid prototyping via CNC milling or CO2 laser cutting (features >50 um)
- Applications with only aqueous reagents (no organic solvents)
- Teaching and educational labs

**Limitations:** Dissolves in many organic solvents; higher autofluorescence than COC; absorbs water; poor UV transparency.

#### PC (Polycarbonate)

**What it is:** Engineering thermoplastic known for high impact strength and heat resistance.

| Property | Value |
|----------|-------|
| Young's modulus | 2.0--2.4 GPa |
| Transparency | Good in visible |
| Heat resistance | Up to 130--140 C (higher than PMMA or COC) |
| Solvent resistance | Moderate; attacked by acetone, chloroform |
| Fabrication | Injection molding, CNC milling, hot embossing |
| Bonding | Solvent bonding, thermal bonding, adhesive |

**When to use:**
- High-temperature microfluidic applications (PCR, on-chip heating)
- High-pressure applications (strong and tough)
- When impact resistance is needed

**Limitations:** Higher autofluorescence than COC; limited solvent compatibility; can yellow with UV exposure.

#### Flexdym (Eden Tech)

**What it is:** Soft thermoplastic elastomer designed as a direct PDMS replacement.

| Property | Value |
|----------|-------|
| Flexibility | Similar to PDMS |
| Small molecule absorption | Significantly lower than PDMS |
| Fabrication | Hot embossing, compatible with SU-8 masters |
| Bonding | Thermal bonding to glass and thermoplastics |

**When to use:** Drug studies where PDMS absorption is a problem but you want similar mechanical flexibility. Relatively new material with limited track record.

### Material Decision Matrix

| Factor | PDMS | OSTEMER | COC/COP | PMMA | PC |
|--------|------|---------|---------|------|-----|
| Prototyping speed | Excellent | Good | Poor | Good (CNC) | Good (CNC) |
| Production scaling | Poor | Moderate | Excellent | Good | Good |
| Drug absorption | High (bad) | Low | Very low | Low | Low |
| Organic solvent use | Poor | Good | Moderate | Poor | Poor |
| Optical clarity | Excellent | Good | Excellent | Excellent | Good |
| UV transparency | Good | Moderate | Excellent | Poor | Poor |
| Autofluorescence | Low | Low | Very low | Moderate | High |
| Gas permeability | High | Low | Very low | Very low | Very low |
| Flexibility | Excellent | Tunable | Rigid | Rigid | Rigid |
| Cost per chip (prototype) | $1--$5 | $10--$50 | $50--$500 | $5--$50 | $5--$50 |
| Cost per chip (volume) | $5--$20 | $5--$20 | $0.50--$5 | $0.50--$5 | $0.50--$5 |
| Plasma bonding needed | Yes | No (self-bonds) | No | No | No |

---

## 5. When PDMS Is Good Enough vs. When You Need Something Else

### PDMS Is Good Enough When:

1. **You are prototyping.** PDMS is unmatched for speed of iteration: design a mask, make a master, cast PDMS, bond, test -- all in 1--3 days.
2. **You are doing cell biology with aqueous media.** Gas permeability is a feature (O2/CO2 exchange). Biocompatible. Transparent for microscopy.
3. **Your analytes are not small hydrophobic molecules.** Proteins, cells, beads, bacteria -- PDMS is fine.
4. **You need <100 devices.** Hand-casting is acceptable at small scale.
5. **You need pneumatic valves (Quake valves).** PDMS elasticity is essential for membrane deflection.
6. **Your reagents are aqueous.** Water, buffers, cell media -- no compatibility issues.
7. **You are publishing proof-of-concept work.** PDMS is accepted and expected in academic papers.
8. **You need reversible bonding (conformal seal).** PDMS naturally conforms to smooth surfaces.

### Move Away from PDMS When:

1. **You are studying drug-cell interactions or small molecule transport.** PDMS absorbs hydrophobic drugs (e.g., paclitaxel, tamoxifen, rhodamine B). Measured absorption can sequester 50--90% of drug from media. Use OSTEMER, COC, glass, or fluoropolymer-coated PDMS.

2. **You need organic solvents in channels.** PDMS swells in chloroform, toluene, hexane, DCM, THF, diisopropylamine. Even acetone and ethanol cause minor swelling. Use COC, glass, or stainless steel microfluidics.

3. **You need to scale to >100 devices.** Hand-casting and bonding does not scale. Transition to injection-molded COC/COP or hot-embossed PMMA. Note: some groups have demonstrated PDMS injection molding (LSR-IM) for production, but this is still niche.

4. **You need long-term stable surface chemistry.** PDMS hydrophobic recovery after plasma treatment limits stable coatings. COC and glass maintain surface modifications much longer.

5. **You need high pressure (>50 psi).** PDMS channels deform under pressure. Rigid materials (COC, PMMA, glass, silicon) handle higher pressures without distortion.

6. **You need low evaporation.** PDMS is gas-permeable -- water evaporates through the bulk. For long-term experiments (days to weeks), channels dry out. Use glass-glass devices, COC, or add humidity control.

7. **You are developing a commercial diagnostic product.** PDMS is difficult to manufacture at scale with consistent quality. COC/COP injection molding is the industry standard for disposable diagnostics (e.g., lateral flow, PCR cartridges).

8. **You need minimal autofluorescence or UV excitation.** COC and COP have lower autofluorescence than PDMS and are transparent to shorter UV wavelengths.

### Transition Strategy

A practical path many labs follow:

1. **Phase 1 (Proof of concept):** PDMS soft lithography. Fastest to first result. Use SU-8 master + Sylgard 184.
2. **Phase 2 (Validation):** If absorption/solvent issues arise, switch to OSTEMER using the same SU-8 masters. Minimal workflow change.
3. **Phase 3 (Pre-production):** CNC-mill or hot-emboss prototypes in COC/COP to validate thermoplastic design.
4. **Phase 4 (Production):** Commission injection mold tool for COC/COP. Per-chip cost drops to $0.50--$5 at volume.

---

## 6. Complete Soft Lithography Workflow Summary

### Equipment List (Minimum Viable Lab)

| Item | Purpose | Approximate Cost |
|------|---------|-----------------|
| Sylgard 184 (0.5 kg kit) | PDMS casting | $70--$90 |
| Precision balance | Weighing PDMS | $200--$500 |
| Vacuum desiccator + pump | Degassing | $300--$800 |
| Convection oven (or hotplate) | Curing | $500--$2,000 |
| Biopsy punches (0.75, 1.0, 1.5 mm) | Port punching | $5--$10 each |
| Scalpel and cutting mat | Demolding | $20 |
| Plasma cleaner (Harrick PDC-32G) | Bonding | $4,000--$5,000 |
| OR Corona treater (BD-20AC) | Bonding (low-cost) | $400--$600 |
| Glass slides / coverslips | Bonding substrate | $10--$30 per box |
| Scotch tape | Surface cleaning | $5 |
| N2 gun or compressed air | Drying | $50--$200 |
| IPA, DI water | Cleaning | $20--$50 |
| **Total (with corona treater)** | | **~$1,200--$2,300** |
| **Total (with plasma cleaner)** | | **~$5,200--$9,500** |

This does not include the SU-8 master fabrication (see 04_fabrication_lithography.md).

### Timeline: Design to Working Device

| Step | Time | Notes |
|------|------|-------|
| CAD design | 1--4 hours | Depends on complexity |
| Mask procurement (film) | 1--2 days | Same day if in-house printer |
| Mask procurement (chrome) | 1--3 weeks | Faster with express service |
| SU-8 master fabrication | 4--8 hours (cleanroom time) | Includes all bakes, exposure, development |
| Silanization | 1--2 hours | Vacuum desiccator treatment |
| PDMS mixing + degassing | 30--60 min | |
| PDMS curing | 2--4 hours (at 65--80 C) | Overnight at room temp if no oven |
| Demolding + punching | 15--30 min | |
| Plasma bonding | 5--15 min | |
| **Total (with film mask)** | **1--2 days** | |
| **Total (with chrome mask)** | **1--3 weeks** (mask limited) | |
| **Total (with maskless aligner)** | **1 day** | No mask wait |

### Number of Devices from One Master

A single SU-8 master can typically produce 50--200+ PDMS replicas before degradation, assuming:
- Proper silanization (re-silanize every 20--30 castings)
- Careful demolding technique
- No physical damage to master

---

## 7. Troubleshooting PDMS Fabrication

| Problem | Likely Cause | Solution |
|---------|-------------|----------|
| PDMS not curing | Wrong ratio; old curing agent; contaminants | Verify 10:1 ratio; check expiration date; use clean mixing tools (latex gloves can inhibit Pt catalyst -- use nitrile) |
| Bubbles in cured PDMS | Incomplete degassing | Degas longer; use larger container; release vacuum periodically |
| PDMS stuck to master | No silanization; damaged silane coating | Re-silanize master; ensure vacuum desiccation during silanization |
| Weak/failed plasma bond | Over-treatment; too slow to contact; dirty surfaces | Reduce plasma time to 30 s; bond within 60 s; clean surfaces with tape + IPA |
| Leaking at ports | Punch size mismatch; rough punch edges | Match punch to tubing OD; use sharp new punches; punch from channel side |
| Channel collapse (thin, wide channels) | PDMS too soft; channel aspect ratio too high (width >> height) | Use stiffer PDMS (5:1 ratio); redesign with supporting pillars; reduce channel width |
| Non-uniform channel depth | SU-8 thickness non-uniformity | Optimize spin coating; check for edge bead; level spin coater |
| PDMS yellowing | Over-curing at high temperature | Cure at 65--80 C; avoid >120 C |

---

## Sources

- [PDMS Fabrication Guide (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC2917889/)
- [Sylgard 184 PDMS - Darwin Microfluidics](https://darwin-microfluidics.com/products/sylgard-184-pdms-elsatomer)
- [Sylgard 184 Protocol (protocols.io)](https://www.protocols.io/view/preparation-of-sylgard-184-pdms-dmyd47s6.html)
- [Rapid PDMS Curing (RSC Chips and Tips)](https://blogs.rsc.org/chipsandtips/2006/10/23/rapid-curing-of-pdms-for-microfluidic-applications/)
- [Sylgard 184 Curing Properties (Wiley)](https://onlinelibrary.wiley.com/doi/am-pdf/10.1002/app.48530)
- [PDMS Bonding Technologies Review (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8394141/)
- [PDMS Bonding - Harrick Plasma](https://harrickplasma.com/pdms-bonding/)
- [Harrick Plasma Cleaners](https://harrickplasma.com/plasma-cleaners/)
- [Glass/PDMS Bonding - Elveflow](https://elveflow.com/microfluidic-reviews/soft-lithography-glass-pdms-bonding/)
- [Corona Treatment for PDMS - Electro-Technic Products](https://www.electrotechnicproducts.com/blog/electrotechnic-products-blog-corona-treatment-applications-in-microfluidics/)
- [Corona PDMS Bonding (Elveflow)](https://elveflow.com/microfabrication/corona-plasma-treater-for-pdms-bonding-microfabrication-tool/)
- [PDMS Bonding via Corona (PubMed)](https://pubmed.ncbi.nlm.nih.gov/17203160/)
- [Plasma Treatment for PDMS (Henniker)](https://plasmatreatment.co.uk/pt/plasma-treatments/plasma-surface-activation-to-improve-adhesion/pdms-bonding-microfluidics)
- [Diener Electronic Plasma Systems](https://www.plasma.com/en/)
- [Plasma Treatment for PDMS (PIE Scientific)](https://piescientific.com/resource-pdms-bonding/)
- [PDMS Limitations and Alternatives (Micronit)](https://micronit.com/expertise/manufacturing-expertise/pdms-for-microfluidics)
- [Why Not PDMS (Eden Microfluidics)](https://eden-microfluidics.com/news-events/why-not-pdms-microfluidics-alternative/)
- [PDMS Drug Absorption Problem (Eden)](https://eden-microfluidics.com/news-events/pdms-drug-absorption-microfluidics-solution/)
- [PDMS Solvent Compatibility (ACS)](https://pubs.acs.org/doi/10.1021/ac0346712)
- [PDMS to Thermoplastics Evolution (Potomac Laser)](https://www.potomac-laser.com/blog/microfluidics-the-evolution-from-pdms-to-thermoplastics-for-enhanced-scalability-and-cost-effectiveness/)
- [PDMS in Microfluidics Guide (Aline)](https://www.alineinc.com/polydimethylsiloxane-pdms-in-microfluidics/)
- [COC Review in Microfluidics (Wiley)](https://onlinelibrary.wiley.com/doi/full/10.1002/mame.202200053)
- [Microfluidics Materials Comparison (Darwin Blog)](https://blog.darwin-microfluidics.com/the-most-used-microfabrication-materials-for-microfluidics/)
- [OSTEMER Applications](https://www.ostemers.com/applications/)
- [OSTEMER Wikipedia](https://en.wikipedia.org/wiki/Off-stoichiometry_thiol-ene_polymer)
- [OSTEMER 322 Biocompatibility (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC10804231/)
- [Thiol-Ene Polymers for Microfluidics (ACS)](https://pubs.acs.org/doi/10.1021/acsami.9b22050)
- [OSTEMER-Thermoplastic Hybrid Devices (Wiley)](https://advanced.onlinelibrary.wiley.com/doi/full/10.1002/admi.202300972)
- [Microfluidics Chip Materials and Fabrication (Innovation Center)](https://microfluidics-innovation-center.com/reviews/microfluidics-chip-and-tubing-materials-fabrication-techniques/)
- [Flexdym PDMS Alternative (Eden Tech)](https://eden-microfluidics.com/flexdym-pack-alternative-to-pdms/)
- [Chemical Resistance of Microfluidic Materials (Elveflow)](https://www.elveflow.com/microfluidic-reviews/general-microfluidics/chemical-resistance-of-microfluidic-materials/)
- [Microfluidics Fabrication Techniques Comparison (Nature)](https://www.nature.com/articles/s41598-024-80332-2)
- [PDMS Injection Molding for Mass Fabrication (Nature)](https://www.nature.com/articles/s41598-025-16863-z)
- [Parallel Fluidics PDMS Alternative](https://www.parallelfluidics.com/landing-pages/pdms)
- [Soft Lithography Station (Darwin Microfluidics)](https://darwin-microfluidics.com/products/soft-lithography-station)
