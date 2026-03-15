# Soft Lithography and PDMS Fabrication for Microfluidics

## Overview

Soft lithography is the set of replica molding techniques used to transfer micro/nanostructures from a master mold (typically SU-8 on silicon, fabricated via photolithography) into a soft elastomer, most commonly PDMS (polydimethylsiloxane). The resulting PDMS slab is then bonded to a flat substrate (glass or another PDMS layer) to create enclosed microfluidic channels. This document covers the complete PDMS fabrication workflow, bonding techniques, and alternatives to PDMS.

---

## 1. PDMS: Sylgard 184 -- Complete Guide

### What It Is

Sylgard 184 (Dow, formerly Dow Corning) is a two-part silicone elastomer kit consisting of a base (vinyl-terminated polydimethylsiloxane) and a curing agent (platinum-catalyzed cross-linker with copolymer of methylhydrosiloxane and dimethylsiloxane). It is the de facto standard material for academic microfluidics research.

### 1.1 Mixing Ratios

#### Standard 10:1 Ratio

The manufacturer-recommended ratio is 10:1 (base : curing agent) by weight. This provides a good balance of elasticity, strength, and optical clarity for most microfluidic applications.

#### Alternative Ratios and Their Effects

Varying the base-to-curing-agent ratio dramatically changes mechanical and surface properties:

| Ratio (Base:Agent) | Young's Modulus | Characteristics | Use Case |
|---------------------|----------------|-----------------|----------|
| 5:1 | ~3--4 MPa | Stiff, highly crosslinked, more brittle | High-pressure channels, structural layers |
| 7:1 | ~2.5--3 MPa | Moderately stiff | Intermediate applications |
| 9:1 | ~2.5 MPa (near maximum crosslink density) | Optimal crosslink density | When maximum stiffness is needed |
| **10:1 (standard)** | **~1.5--2.5 MPa** | **Standard elasticity, well-characterized** | **General microfluidics** |
| 10:2 (equivalent to ~5:1) | ~1.3--1.5 MPa | Slightly softer than 10:1 due to excess curing agent | Adjusted mechanical response |
| 10:3 | ~1.6 MPa | Excess curing agent, some unreacted | Experimental formulations |
| 15:1 | ~1.0 MPa | Softer, less crosslinked | Flexible membrane layers |
| 20:1 | ~0.5 MPa | Very soft, significant uncrosslinked material | Quake-style pneumatic valves, cell culture substrates |
| 30:1 | ~0.1--0.2 MPa | Extremely soft, tacky, substantial free polymer leaching | Mechanobiology studies (mimicking soft tissue) |
| 40:1--60:1 | ~3--50 kPa | Gel-like, high leachable content | Cell mechanobiology (matching tissue stiffness) |

**Key findings from research:**

- Maximum Young's modulus is reached near a 9:1 ratio, not 10:1, because this is the stoichiometric optimum for crosslink density.
- Reducing the crosslinker fraction below 10:1 leaves a large proportion of free (uncrosslinked) polymer that can leach out over time, potentially affecting cell culture or analytical assays.
- For very soft substrates (cell mechanobiology), an alternative strategy is to blend Sylgard 184 base with Sylgard 527 (a softer silicone gel) rather than simply reducing curing agent, as this avoids the leaching problem.
- Hybrid formulations using Sylgard 184 base with Sylgard 186 curing agent have been explored to achieve intermediate mechanical properties.

#### Practical Considerations for Non-Standard Ratios

- **Leaching:** Ratios above 15:1 have significant uncrosslinked oligomers. For cell culture, extract in ethanol or toluene for 24--48 hours, then dry thoroughly before use.
- **Curing time:** Lower crosslinker ratios require longer cure times.
- **Adhesion:** Higher crosslinker ratios (e.g., 5:1) may bond more readily but are more brittle.

### 1.2 Degassing Procedures and Equipment

#### Standard Vacuum Desiccator Method

1. Place mixed PDMS in a vacuum desiccator connected to a vacuum pump.
2. Apply vacuum (~25--30 inHg / ~85--100 kPa below atmosphere).
3. PDMS will foam dramatically -- use an oversized container (3--4x the volume of PDMS) to prevent overflow.
4. Release vacuum periodically to collapse large bubbles.
5. Continue until PDMS is completely clear and bubble-free (typically 15--45 min).

#### Equipment Options

| Equipment | Cost | Notes |
|-----------|------|-------|
| Polycarbonate vacuum desiccator + rotary vane pump | $300--$800 | Most common lab setup |
| Centrifugal degassing (planetary mixer, e.g., Thinky ARE-310) | $5,000--$15,000 | Simultaneous mixing and degassing in 2--5 min |
| Syringe-based manual degassing | $10 | Slow, only for small volumes (<5 mL) |

#### Tips for Effective Degassing

- Allow 15--30 minutes or until all bubbles are gone.
- After several minutes under vacuum, break the vacuum briefly to pop surface bubbles, then re-apply vacuum.
- For very thick pours (>5 mm), degas for up to 1 hour.
- If bubbles reappear after pouring over the master, return to the desiccator for 5--10 min.
- Alternatively, degass under vacuum for 1 hour before curing for complete removal.

### 1.3 Curing Temperatures and Times

Sylgard 184 cures via a platinum-catalyzed hydrosilylation reaction. The relationship between temperature and cure time spans from ~48 hours at room temperature to ~10 minutes at 150 C.

| Temperature | Time | Young's Modulus | Tensile Strength | Notes |
|-------------|------|-----------------|------------------|-------|
| Room temp (~25 C) | 24--48 hours | Lower (~1.3 MPa) | ~5.1 MPa | Handleable at 24 hr, full cure at ~7 days. Minimal thermal stress. Slowest hydrophobic recovery post-plasma. |
| 45 C | 12--16 hours | ~1.5 MPa | ~5.5 MPa | Gentle heating, low stress |
| 65 C | 4 hours | ~1.7 MPa | ~6.5 MPa | Common lab protocol. Good balance of speed and low stress. |
| 80 C | 2--2.5 hours | ~1.8 MPa | ~7.0 MPa | Most commonly cited protocol for microfluidics. |
| 100 C | 30--45 min | ~2.0 MPa | ~7.5 MPa | For thin layers (<2 mm). More thermal stress; slight feature distortion risk. |
| 125 C | 20 min | ~2.2 MPa | ~7.65 MPa (maximum) | Maximum tensile strength. Risk of thermal warpage. |
| 150 C | 10 min | ~2.3 MPa | ~7.5 MPa | Very fast but risk of warpage and delamination from master. |
| 200 C | ~5 min | Highest stiffness | Reduced (degradation onset) | Not recommended; approaching thermal degradation. Post-cure aging only. |

**Key findings:**

- Higher curing temperatures produce stiffer PDMS with higher ultimate tensile strength, up to a maximum at ~125 C.
- For thicknesses >2 mm, cure at lower temperatures (60--80 C) for longer times to avoid internal stress gradients.
- Room-temperature-cured PDMS has slower hydrophobic recovery after plasma treatment, which can be advantageous for bonding shelf life.
- Rapid cooling after high-temperature cure can introduce internal stresses; allow gradual cooling.

**Recommended protocol:** 65--80 C for 2--4 hours in a convection oven. Avoid rapid cooling after curing.

### 1.4 Mechanical Properties

#### Young's Modulus

The Young's modulus of Sylgard 184 depends strongly on mixing ratio, cure temperature, and test method:

| Condition | Young's Modulus | Notes |
|-----------|----------------|-------|
| 10:1, cured 80 C/2h | 1.5--2.5 MPa | Standard conditions; literature values vary due to test method |
| 10:1, cured 25 C/48h | ~1.3 MPa | Softer due to incomplete crosslinking |
| 10:1, cured 150 C/10min | ~2.5--3.0 MPa | Stiffest standard formulation |
| 5:1, cured 80 C/2h | ~3--4 MPa | High crosslink density |
| 20:1, cured 80 C/4h | ~0.3--0.5 MPa | Soft, for valves/membranes |
| 60:1, cured 80 C/4h | ~3--50 kPa | Gel-like, for mechanobiology |

**Important:** Published Young's modulus values for PDMS vary significantly (from 0.5 to 4 MPa even for 10:1 ratio) due to differences in:
- Test method (tensile vs. compression vs. nanoindentation vs. AFM)
- Sample geometry and dimensions
- Strain rate
- Cure history (time, temperature, age of sample)
- Batch-to-batch variation in Sylgard 184

#### Other Mechanical Properties

| Property | Typical Value (10:1, 80 C cure) |
|----------|-------------------------------|
| Elongation at break | 120--160% |
| Tear strength | ~2.6 kN/m |
| Poisson's ratio | ~0.49 (nearly incompressible) |
| Shore A hardness | ~44 |
| Compressive modulus | ~1.5--2.0 MPa |

### 1.5 Optical Properties

#### Transparency

PDMS is highly transparent across a broad wavelength range, making it the preferred material for microscopy-compatible microfluidics.

| Wavelength Range | Transmittance | Notes |
|------------------|--------------|-------|
| 240--400 nm (UV) | >75% (>90% above 300 nm) | Two absorption peaks: 266 nm (UV) and 908 nm (IR) |
| 400--700 nm (Visible) | >95% | Excellent for bright-field and fluorescence microscopy |
| 700--1100 nm (NIR) | >90% | Good for NIR imaging and Raman spectroscopy |

- Refractive index: 1.41 (at 589 nm)
- Absorption peaks at 266 nm (UV, Si-CH3 related) and 908 nm (IR, Si-O-Si stretching)

#### Autofluorescence

- PDMS has **low autofluorescence** compared to most polymers, making it suitable for fluorescence microscopy.
- At 633 nm excitation, PDMS has the **lowest autofluorescence** among PMMA, PC, and COC.
- However, at shorter wavelengths (UV excitation, <400 nm), PDMS autofluorescence increases and can interfere with DAPI or Hoechst staining experiments.
- Curing at higher temperatures can slightly increase autofluorescence.
- COC/COP materials (e.g., Zeonex) have roughly **half the autofluorescence** of PDMS at UV wavelengths.

#### Practical Implications

- For standard fluorescence microscopy (GFP, RFP, Cy5): PDMS is excellent.
- For UV-excited fluorophores (DAPI, Hoechst): PDMS is acceptable but COC/COP may be better.
- For quantitative fluorescence measurements requiring minimal background: consider COC/COP or glass.

### 1.6 Gas Permeability

PDMS has exceptionally high gas permeability compared to other polymers, which is both its greatest advantage and a significant limitation.

#### Permeability Coefficients

| Gas | Permeability (Barrer) | Solubility (cm3/cm3-atm) | Notes |
|-----|----------------------|--------------------------|-------|
| O2 | ~600 | 0.18 | Key for cell culture oxygenation |
| CO2 | ~3,200--3,970 | ~1.0 | Critical for pH buffering in cell media |
| N2 | ~280--590 | 0.09 | Lower than O2 (O2/N2 selectivity ~2) |
| H2O vapor | High | -- | Causes media evaporation |

(1 Barrer = 10^-10 cm3(STP)-cm / cm2-s-cmHg)

#### Advantages (Cell Culture)

- Thick PDMS slabs serve as gas reservoirs, enabling constant O2 and CO2 supply to cells without external gas control.
- Enables long-term cell culture (days to weeks) in sealed microfluidic devices.
- Allows oxygen tension control by flowing defined gas mixtures through adjacent control channels separated by thin PDMS membranes (10--100 um).
- No need for gas-permeable culture inserts or specialized incubator connections.

#### Disadvantages

- **Media evaporation:** Water vapor permeates through PDMS, causing media concentration changes and eventually channel drying in long-term experiments. Mitigation: add humidified air channels around the device, use thicker PDMS, or add a PDMS-free barrier layer.
- **Bubble formation:** Dissolved gases can nucleate bubbles in channels, especially during temperature changes.
- **Volatile reagent loss:** Volatile organic compounds (e.g., anesthetics, fragrances, volatile drugs) permeate out of channels through PDMS.
- **Uncontrolled oxygen levels:** For hypoxia studies, the high permeability makes it difficult to maintain low O2 unless specifically designed gas control channels are used.

#### Effect of Plasma Treatment on Gas Permeability

- Plasma treatment converts the PDMS surface to a SiO2-like layer, which is gas-impermeable.
- Freshly oxidized PDMS shows significantly reduced gas diffusion coefficients.
- This SiO2 barrier disappears after ~3 days of storage in air (hydrophobic recovery exposes native PDMS).
- If PDMS is maintained in contact with water after plasma treatment, the barrier effect persists for up to 3 weeks.

### 1.7 Chemical Compatibility

#### Solvent Swelling

PDMS swelling in organic solvents is the primary chemical compatibility concern. The swelling ratio (S = swollen dimension / original dimension) depends on solvent polarity:

| Solvent | Swelling (% weight increase) | Compatibility | Notes |
|---------|------------------------------|---------------|-------|
| Water | <1% | Excellent | Standard working fluid |
| DMSO | <1% | Excellent | Common cell biology solvent |
| Ethylene glycol | <1% | Excellent | |
| Acetonitrile | <5% | Good | Usable for short experiments |
| Methanol | ~2% | Good | Short-term OK |
| Ethanol | ~5% | Moderate | Minor swelling, usable with care |
| IPA (isopropanol) | ~10--15% | Moderate | Used for cleaning but causes some swelling |
| Acetone | ~15--20% | Poor | Significant swelling; avoid prolonged contact |
| Ethyl acetate | >70% | Very poor | Severe swelling and deformation |
| Toluene | >85% | Very poor | Massive swelling; leaks through channel walls |
| Hexane | >85% | Very poor | Fastest swelling kinetics (~15 min to plateau) |
| Chloroform | >80% | Very poor | Severe swelling; PDMS becomes gel-like |
| DCM (dichloromethane) | >80% | Very poor | |
| THF | >70% | Very poor | |
| Diisopropylamine | >50% | Very poor | |

**General rule:** PDMS swells most in non-polar solvents with low surface tension. Solvents with high polarity and high surface tension (water, DMSO, glycols) are compatible.

**Key practical implications:**
- Hexane reaches steady-state swelling in ~40 minutes, with most swelling occurring in the first 15 minutes.
- Toluene in PDMS channels leaks out through the channel walls rapidly, making it unusable.
- For organic chemistry on chip, use glass, COC, stainless steel, or fluoropolymer-coated channels.
- PDMS can be used for brief contact with moderate solvents (ethanol, IPA) such as cleaning steps.

#### Acid/Base Compatibility

| Reagent | Compatibility | Notes |
|---------|---------------|-------|
| Dilute acids (HCl, H2SO4 <1M) | Good | Short-term exposure OK |
| Concentrated acids | Poor | Surface degradation |
| Dilute bases (NaOH <1M) | Good | |
| Piranha solution (H2SO4:H2O2) | Poor | Attacks PDMS; used intentionally for surface activation |

### 1.8 Surface Properties and Hydrophobic Recovery

#### Native Surface

- Water contact angle: ~110 degrees (hydrophobic)
- Surface energy: ~20 mN/m (very low)
- Surface chemistry: methyl groups (Si-CH3) dominate

#### After Plasma Treatment

- Water contact angle: <10 degrees (superhydrophilic)
- Surface chemistry: silanol groups (Si-OH) dominate
- Resembles silica glass surface

#### Hydrophobic Recovery Timeline

PDMS surfaces revert to their native hydrophobic state after plasma treatment through migration of low-molecular-weight (LMW) uncrosslinked chains from the bulk to the surface:

| Time After Treatment | Contact Angle | Surface State |
|---------------------|---------------|---------------|
| 0 min | <10 deg | Superhydrophilic (Si-OH surface) |
| 15 min | ~30--40 deg | Rapid initial recovery (LMW migration) |
| 1 hour | ~50--60 deg | Significantly recovered |
| 24 hours | ~70--80 deg | Mostly recovered |
| 48 hours | ~85--95 deg | Nearly fully recovered |
| 7 days | ~100--110 deg | Essentially original hydrophobicity |

#### Strategies to Slow Hydrophobic Recovery

| Strategy | Duration of Hydrophilicity | Notes |
|----------|---------------------------|-------|
| Storage in DI water after treatment | 1--3 weeks | Practical and simple; store bonded device in water |
| Storage at -80 C | >100 days | Superhydrophilicity maintained; impractical for routine use |
| Thermal aging (pre-bake at 200 C before plasma) | ~12 days | Drives out LMW species before treatment |
| Repeated solvent extraction (toluene soak) | Weeks | Removes LMW chains from bulk |
| PEG surface grafting | Weeks to months | Chemical modification; more complex |
| Room-temperature curing (vs high-temp cure) | Slower recovery | RT-cured PDMS has different LMW distribution |
| Thicker PDMS slabs | Slightly slower | More LMW reservoir, but also longer diffusion path |

**Important findings:**
- The primary mechanism is diffusion of LMW chains to the surface, not degradation of surface silanol groups.
- Curing PDMS at room temperature over several days (rather than high-temp cure) slows hydrophobic recovery and decreases the extent of recovery at equilibrium.
- Sample thickness and curing conditions have the most significant effects on recovery rate.

### 1.9 Material Properties Summary Table

| Property | Value |
|----------|-------|
| Mix ratio | 10:1 (base : curing agent) by weight |
| Pot life (working time) | ~2 hours at room temperature |
| Viscosity (mixed) | ~3,500 cP |
| Cured Young's modulus | ~1.5--2.5 MPa (at 10:1 ratio) |
| Elongation at break | 120--160% |
| Optical transparency | >95% in visible range (240--1100 nm) |
| Refractive index | 1.41 |
| Gas permeability (O2) | ~600 Barrer |
| Gas permeability (CO2) | ~3,200 Barrer |
| Water contact angle (native) | ~110 deg (hydrophobic) |
| Water contact angle (post-plasma) | <10 deg (reverts in hours--days) |
| Biocompatible | Yes (USP Class VI) |
| Operating temperature | -45 C to +200 C |
| Dielectric strength | ~21 kV/mm |
| Shore A hardness | ~44 |
| Specific gravity | 1.03 (cured) |

### 1.10 Cost

- **Sylgard 184 kit (0.5 kg):** ~$60--$90 (sufficient for ~20--50 devices depending on thickness)
- **Sylgard 184 kit (1.1 kg):** ~$80--$120
- **Sylgard 184 kit (3.9 kg):** ~$200--$300
- Available from Sigma-Aldrich, Fisher Scientific, Darwin Microfluidics, Ellsworth Adhesives, and direct from Dow

---

## 2. Complete Casting Protocol

### Step 1: Weighing and Mixing

1. Tare a clean disposable cup on a precision balance
2. Weigh out PDMS base (e.g., 40 g)
3. Add curing agent at 10:1 ratio (e.g., 4 g for 40 g base)
4. Mix thoroughly with a plastic fork or spatula for 3--5 minutes until uniformly cloudy with bubbles
5. **Warning:** Latex gloves can inhibit the Pt catalyst -- use nitrile gloves only

### Step 2: Degassing

1. Place mixed PDMS in a vacuum desiccator connected to a vacuum pump
2. Apply vacuum (~25--30 inHg / ~85--100 kPa below atmosphere)
3. PDMS will foam dramatically -- use an oversized container (3--4x the volume of PDMS) to prevent overflow
4. Release vacuum periodically to collapse large bubbles
5. Continue until PDMS is completely clear and bubble-free (typically 15--45 min)
6. Alternative: centrifugal degassing at 2000 rpm for 5 min (faster but requires centrifuge with large cups)

### Step 3: Pouring Over Master

1. Place silanized SU-8 master in a Petri dish or aluminum foil boat
2. Pour degassed PDMS slowly over master to desired thickness:
   - Thin layer (~50--200 um): spin coat PDMS at 500--3000 rpm (for membrane layers)
   - Standard thickness (~3--5 mm): pour and let self-level
   - Thick layer (~5--10 mm): pour more; thicker devices are easier to handle and punch
3. If bubbles appear during pouring, briefly return to vacuum desiccator (5--10 min)
4. Ensure PDMS covers all features with adequate margin

### Step 4: Curing

| Temperature | Time | Notes |
|-------------|------|-------|
| Room temperature (~25 C) | 24--48 hours | Handleable at 24 hr, full cure at ~7 days. Minimal thermal stress. |
| 65 C | 4 hours | Common lab protocol. Good balance of speed and low stress. |
| 80 C | 2--2.5 hours | Most commonly cited protocol for microfluidics. |
| 100 C | 45--60 min | Faster but more thermal stress; can cause slight feature distortion. |
| 150 C | 10 min | Very fast but risk of thermal warpage and delamination from master. |

**Recommended:** 65--80 C for 2--4 hours in a convection oven. Avoid rapid cooling after curing.

### Step 5: Demolding (Peeling)

1. Allow cured PDMS to cool to room temperature
2. Use a scalpel or razor blade to carefully cut around the perimeter of the device
3. Gently peel PDMS from the master, starting from one corner
4. Work slowly -- rushing can tear fine features or damage the master
5. A well-silanized master should release easily; if PDMS tears on the mold, re-silanize

### Step 6: Port Punching

1. Use a biopsy punch (typically 0.75 mm, 1.0 mm, or 1.5 mm diameter depending on tubing)
2. Punch through the PDMS at inlet/outlet locations from the channel side (feature side down)
3. Punch straight through; twist and pull to remove core
4. For best results, punch on a soft cutting mat
5. Match punch size to tubing OD for friction-fit connections:
   - 0.75 mm punch for 1/32" OD tubing
   - 1.0 mm punch for PEEK tubing
   - 1.5 mm punch for Tygon/silicone tubing (1/16" OD)

### Step 7: Cleaning

1. Rinse PDMS slab with IPA, then DI water
2. Blow dry with N2 gun or filtered air
3. Use Scotch tape to remove surface particles from the channel side
4. Optionally sonicate in IPA for 5 min to remove debris from channels

---

## 3. Plasma Bonding

### 3.1 Oxygen Plasma Bonding Process

#### Surface Chemistry

Oxygen plasma treatment generates reactive oxygen species that:
1. Remove organic contaminants from surfaces
2. Convert surface Si-CH3 groups (hydrophobic) to Si-OH silanol groups (hydrophilic)
3. When two treated surfaces are brought into contact, silanol groups condense to form covalent Si-O-Si siloxane bonds
4. This creates an irreversible, hermetic bond that can withstand >30 psi in typical microfluidic devices

The reaction: Surface-Si-OH + HO-Si-Surface --> Surface-Si-O-Si-Surface + H2O

#### Process Parameters

| Parameter | Typical Range | Notes |
|-----------|--------------|-------|
| Gas | O2 (preferred) or air | O2 gives more consistent results; air works but is less efficient |
| Pressure | 200--600 mTorr (0.27--0.8 mbar) | Low vacuum range |
| RF Power | 10--30 W (Harrick); 50 W (Diener Zepto); varies by system | Too high damages PDMS surface |
| Exposure time | 10--60 seconds | 30 s typical. >2 min causes surface cracking and reduces bond quality |
| Contact time after treatment | <60 seconds | **Critical:** Must bring surfaces into contact immediately; surface reverts within minutes |
| Post-bond bake | 80--100 C for 15--60 min | Provides thermal activation energy for additional bond formation; recommended |

#### Bond Strength

| Method | Typical Bond Strength | Notes |
|--------|----------------------|-------|
| O2 plasma, standard | ~300--550 kPa | Adequate for most microfluidic applications |
| O2 plasma + IPA incorporation | up to ~3,060 kPa | Enhanced method using isopropanol during plasma |
| O2 plasma + 80 C post-bake | ~400--600 kPa | Post-bake strengthens bond |
| Corona discharge | ~200--400 kPa | Lower but sufficient for most uses |
| Conformal (no treatment) | ~5--20 kPa | Reversible, weak |

#### Critical Tips

- **Do not over-treat:** >2 min plasma exposure causes PDMS surface cracking (brittle SiO2 layer) and actually reduces bond strength
- **Speed matters:** After plasma treatment, silanol groups on PDMS recombine within 5--30 minutes, reverting to hydrophobic. Bond surfaces within 60 seconds of treatment. More than 60 seconds after activation risks failed bonding.
- **Cleanliness is essential:** Any particles, fingerprints, or contamination between surfaces will cause bond failure (leaks). The cleanliness of glass is of utmost importance.
- **Uniform contact:** Use a roller or gentle finger pressure from center outward to avoid trapping air bubbles at the interface
- **Pressure after contact:** Press together lightly for 30 seconds, then heat at 80--100 C for 60 seconds on a hot plate or 15--30 minutes in an oven

### 3.2 Equipment

#### Harrick Plasma Cleaners

The most popular plasma systems for PDMS bonding in academic microfluidics labs.

| Model | Chamber Size | Power | Voltage | Notes |
|-------|-------------|-------|---------|-------|
| PDC-32G (Basic) | 1.75" dia x 6.5" | 18 W max | 115V/230V | Entry-level, smallest chamber |
| PDC-001 / PDC-002 (Expanded) | 4" dia x 6.75" | 18 W max | 115V (001) / 230V (002) | Most popular model for microfluidics. Fits glass slides and small wafers. |
| PDC-001-HP / PDC-002-HP (High Power) | 4" dia x 6.75" | 30 W max | 115V / 230V | 2x cleaning rate of standard Expanded model |

**Price range:** ~$4,000--$8,000 depending on model and accessories (flow controller, vacuum pump sold separately). Vacuum pump adds ~$1,000--$2,000.

**Pros:** Compact benchtop unit, simple to operate, widely cited in literature, good for PDMS-glass and PDMS-PDMS bonding.
**Cons:** Small chamber limits batch size; basic models lack precise gas flow control.

**Typical protocol (Harrick PDC-001):**
1. Place PDMS and glass in chamber
2. Pump down to ~200--500 mTorr
3. Introduce O2 at low flow
4. Activate plasma at medium power (~18 W) for 30--60 seconds
5. Vent chamber, remove samples, bond within 60 seconds

#### Diener Electronic

German manufacturer of plasma systems. Broader range from benchtop to industrial.

| Series | Type | Notes |
|--------|------|-------|
| Zepto | Compact benchtop | Small chamber, good for lab prototyping. ~$5,000--$8,000 |
| Nano | Benchtop | Mid-range, commonly used in academic labs |
| Femto | Benchtop | Popular for microfluidics bonding. ~$8,000--$15,000 |
| Pico | Larger benchtop/floor | Higher capacity for wafer-scale processing |
| Tetra | Industrial | Production-scale, rack-mounted |

**Typical protocol (Diener Zepto):**
1. Pump chamber to 0.1 mbar
2. Introduce O2 for 7 minutes until pressure reaches 0.4 mbar
3. Activate plasma at 50 W
4. Expose for 20 seconds (PDMS-glass) or 10 seconds (PDMS-PDMS)
5. Vent, remove, bond immediately
6. Post-bake at 100 C for 20 minutes

**Price range:** ~$5,000--$25,000+ depending on model, chamber size, and options.

#### Henniker Plasma

UK-based manufacturer, strong in academic/research markets.

| Model | Chamber | Notes |
|-------|---------|-------|
| HPT-FI (4" and 6") | Small | Entry-level for basic plasma cleaning and PDMS bonding |
| HPT-100 | Benchtop | Research grade, good repeatability |
| HPT-200 | Benchtop | Most commonly used for microfluidics PDMS bonding |
| HPT-300 | Larger | Multiple tray loading, higher throughput |
| HPT-500 | Largest | Multiple trays, production capable |

**Price range:** ~$5,000--$20,000+ depending on model.

#### PIE Scientific (Tergeo)

- Tergeo plasma cleaner: alternative to Harrick, good for microfluidics
- Features real-time plasma monitoring
- Price range: ~$5,000--$10,000

### 3.3 Corona Discharge Treatment (Low-Cost Alternative)

#### What It Is

A handheld corona discharge device creates a localized plasma in ambient air at atmospheric pressure. The corona tip is swept across the PDMS and glass surfaces, oxidizing them similarly to O2 plasma but less uniformly. It is presented in the literature as an effective, inexpensive, and portable alternative for irreversible PDMS bonding.

#### Equipment

| Device | Price | Notes |
|--------|-------|-------|
| **Electro-Technic Products BD-20AC** | ~$400--$600 | Most commonly cited in microfluidics literature; uses BD-20A electrode tip |
| Elveflow Corona Plasma Treater | ~$300--$500 | |
| Blackhole Lab Corona Treater | ~$400 | |

#### Process

1. Clean PDMS and glass surfaces (tape + IPA + N2 dry)
2. Hold corona tip ~3--5 mm from surface
3. Sweep slowly across entire bonding area (30--60 s per surface)
4. Immediately bring treated surfaces into contact (<60 seconds)
5. Press gently from center outward
6. Bake at 80 C for 15--30 min

#### Corona vs. Plasma Chamber Comparison

| Aspect | Corona Treatment (BD-20AC) | O2 Plasma Chamber |
|--------|---------------------------|-------------------|
| Cost | $300--$600 | $4,000--$25,000 |
| Portability | Handheld, no vacuum needed | Benchtop, requires vacuum pump |
| Uniformity | Less uniform (operator dependent) | More uniform and reproducible |
| Bond strength | ~200--400 kPa (adequate for most microfluidics) | ~300--600 kPa |
| Reproducibility | Lower (depends on technique) | Higher (controlled parameters) |
| Throughput | One device at a time | Multiple devices per run |
| Safety for sensors | Can damage thin-film metal layers | Gentler at low power |
| Atmosphere | Ambient air only | O2, air, or Ar selectable |
| Best for | Prototyping, low-budget labs, field work | Production, quantitative work |

### 3.4 Bond Failure Modes

| Failure Mode | Cause | Prevention |
|--------------|-------|------------|
| Adhesive failure (bond peels) | Insufficient plasma treatment; surfaces contacted too late | Increase treatment time (but <2 min); bond within 30 s |
| Cohesive failure (PDMS tears) | Bond stronger than bulk PDMS; excellent bond | Not a failure -- indicates optimal bonding |
| Delamination at edges | Incomplete contact at periphery; trapped air | Apply uniform pressure from center outward |
| Pinhole leaks | Particle contamination at interface | Clean with tape and IPA; work in clean environment |
| Channel collapse | Over-pressure during post-bake; thin PDMS | Reduce post-bake pressure; support during bake |

---

## 4. PDMS-Glass vs. PDMS-PDMS Bonding

### 4.1 PDMS-Glass Bonding

**Process:** Both the PDMS channel slab and a clean glass slide (or coverslip) are treated with O2 plasma or corona, then pressed together.

**Advantages:**
- Strongest bond (glass has abundant surface hydroxyl groups natively; plasma further activates)
- Flat, rigid bottom surface is ideal for microscopy
- Glass is chemically inert and optically excellent
- Easy to visualize channels with inverted microscope
- Can use standard glass slides ($0.05--$0.50 each)

**Typical configuration:** PDMS slab (channels facing down) bonded to a glass microscope slide (25 x 75 mm) or coverslip.

**Bond strength:** ~510 kPa in liquid injection tests

**Considerations:**
- Glass thickness matters for high-NA microscopy: use #1.5 coverslip (170 um) if using oil-immersion objectives
- Borosilicate glass preferred over soda-lime for fluorescence (lower autofluorescence)
- Glass cleanliness is paramount -- fingerprints or grease cause bond failure
- Longer plasma treatment does not improve glass surface activation beyond the optimum

### 4.2 PDMS-PDMS Bonding

**Process:** Both PDMS surfaces are treated with O2 plasma or corona, then pressed together. Same chemistry as PDMS-glass (silanol condensation).

**Bond strength:** ~551 kPa in liquid injection tests (slightly higher than PDMS-glass in some studies, though this varies)

**Advantages:**
- Enables multilayer PDMS devices (e.g., Quake-style pneumatic valves with thin membrane between layers)
- All-PDMS devices are uniformly gas-permeable (beneficial for cell culture)
- Can bond a thin PDMS membrane to a thick PDMS channel layer
- Both surfaces are flexible, allowing conformal contact even on slightly uneven surfaces

**Challenges:**
- Alignment between layers is more difficult (both surfaces are flexible and opaque to alignment marks)
- Thin PDMS membranes are fragile and hard to handle
- Must ensure both surfaces are clean and particle-free
- Flexible-to-flexible bonding can trap air bubbles more easily

### 4.3 Process Differences

| Aspect | PDMS-Glass | PDMS-PDMS |
|--------|-----------|-----------|
| Plasma time (Diener Zepto, 50 W) | 20 seconds | 10 seconds (shorter to avoid cracking both surfaces) |
| Contact window after plasma | <60 seconds | <60 seconds |
| Post-bond bake | 80--100 C, 15--60 min | Same |
| Alignment difficulty | Easy (glass is rigid base) | Harder (both flexible) |
| Optical access | One side glass (excellent for inverted microscopy) | Both sides PDMS (can image from either side but less rigid) |
| Gas permeability | Asymmetric (glass bottom is impermeable) | Symmetric (gas exchange from all sides) |
| Bond strength | ~510 kPa | ~551 kPa |
| Typical use | Single-layer channel devices, microscopy | Multi-layer valved devices, organ-on-chip |

### 4.4 Multi-Layer PDMS Devices

Multi-layer PDMS devices (3+ layers) are used for:
- **Quake-style pneumatic valves:** Flow layer + control layer + membrane between them
- **3D channel networks:** Channels on multiple levels with vias connecting them
- **Integrated membranes:** Thin PDMS membranes for cell culture barriers

#### Fabrication Strategies for Multi-Layer Devices

| Method | Description | Pros | Cons |
|--------|-------------|------|------|
| Sequential plasma bonding | Bond layers one at a time, plasma treating each interface | Simple, standard equipment | Multiple alignment steps; each bond cycle can damage previous |
| Partial-cure bonding | Cast one layer, partially cure, add next layer, complete cure | Excellent bond; no plasma needed | Timing-critical; risk of channel clogging |
| Adhesive layer (uncured PDMS stamp-transfer) | Spin-coat thin uncured PDMS on glass, stamp onto cured layer, bond | Good for 3+ layers; precise adhesive thickness | Risk of adhesive flowing into channels |
| APTES/GPTMS chemical bonding | Chemical surface modification for bonding | Works with non-PDMS substrates | More complex chemistry |
| Curing agent adhesive method | Use patterned curing agent as adhesive between fully cured layers | Selective bonding possible; good for complex stacking | Requires patterned adhesive; heat-initiated cure aids alignment |

#### Tips for Multi-Layer Alignment

- Use alignment marks visible through the thin PDMS layer
- Bond under a stereomicroscope
- Use a thin layer of uncured PDMS as adhesive (stamp-and-transfer technique)
- Align on a clean glass slide for stability
- For high-precision alignment (< 10 um), use a mask aligner with bottom-side alignment capability

### 4.5 When to Use Each Configuration

| Application | Recommended Configuration | Rationale |
|-------------|--------------------------|-----------|
| Standard channel device for microscopy | PDMS-glass | Best optical access from bottom |
| Pneumatic valves (Quake-style) | PDMS-PDMS (2--3 layers) | Requires flexible membrane between layers |
| Cell culture with controlled O2 | PDMS-PDMS or PDMS-glass | PDMS-PDMS for symmetric O2; glass bottom for imaging |
| High-pressure flow (>30 psi) | PDMS-glass | Glass provides rigid support |
| Organ-on-chip with membrane | PDMS-PDMS with thin membrane | Membrane flexibility and gas permeability needed |
| Simple prototype | PDMS-glass | Easiest and most robust |

---

## 5. Alternatives to PDMS

### 5.1 Why Move Beyond PDMS?

PDMS is excellent for prototyping but has real limitations:

1. **Small molecule absorption:** PDMS absorbs hydrophobic molecules (drugs, hormones, dyes). Lipophilic molecules like imipramine (logP = 4.80) can decrease from 100 uM to 0.038 uM after 24 h incubation in PDMS. Absorption can sequester 50--90% of drug from media. PDMS acts as a "chemical capacitor," slowly absorbing then leaching drugs.
2. **Solvent incompatibility:** PDMS swells or dissolves in many organic solvents (chloroform, toluene, hexane, THF). Also affected by acetone, dichloromethane, and ethanol.
3. **Scalability:** Manual casting and bonding does not scale. Each device is hand-made. "PDMS is not suitable for high-throughput or mass production" (though recent LSR injection molding research is emerging).
4. **Mechanical softness:** Low Young's modulus (~2 MPa) limits pressure capability and causes channel deformation under flow.
5. **Evaporation and gas permeability:** Good for cell culture O2 supply, bad for evaporation-sensitive assays, long-term storage, or volatile reagent handling.
6. **Hydrophobic recovery:** Even after plasma treatment, PDMS surfaces revert to hydrophobic within hours to days, limiting shelf life of surface treatments.

### 5.2 OSTEMER (Mercene Labs, Sweden)

**What it is:** Off-Stoichiometry Thiol-Ene (OSTE) polymers. A UV-curable thermoset resin system developed at KTH Royal Institute of Technology and commercialized by Mercene Labs AB.

| Property | Value |
|----------|-------|
| Chemistry | Thiol-ene crosslinking (OSTE) or thiol-ene-epoxy (OSTE+) |
| Young's modulus | 0.6 MPa -- 1.2 GPa (tunable by formulation) |
| Transparency | Good (visible range) |
| Small molecule absorption | Significantly lower than PDMS |
| Solvent resistance | High (resistant to many organic solvents where PDMS fails) |
| Gas permeability | Low (impermeable -- unlike PDMS) |
| Fabrication | Replica molding (same SU-8 masters as PDMS) or injection molding |
| Bonding | Self-bonding via partial UV cure (no plasma needed); latent epoxy for OSTE+ |
| Surface chemistry | Native thiol and allyl groups enable covalent surface modification |
| Biocompatibility | Good (OSTEMER 322 tested in cell-based microfluidic assays) |

**Products:**
- OSTEMER 220 Crystal Clear: Rigid, optically clear
- OSTEMER 322 Crystal Clear: Semi-rigid, good for microfluidics
- OSTEMER 324 Flex: Flexible variant

**Cost:** ~$200--$500 per 100 g kit (significantly more expensive than PDMS by volume). Available from Mercene Labs.

**Fabrication workflow:**
1. Mix resin components
2. Pour over SU-8 master (same molds as PDMS)
3. UV cure (first cure, partial -- leaves reactive surface groups)
4. Demold
5. Bond to substrate via UV or thermal second cure (no plasma needed)

**Key advantages over PDMS:**
- Does not expand under pressure (rigid, maintains channel geometry)
- Complete chemical inertness after final cure
- Good barrier properties (low gas/solvent permeability)
- Self-bonding eliminates need for plasma equipment
- Scalable via industrial reaction injection molding
- Seamless integration with thermoplastics and glass as hybrid devices

**When to use:**
- Drug studies where PDMS absorption is unacceptable
- Solvent-resistant microfluidics
- Prototyping rigid devices that mimic thermoplastic properties
- When you need self-bonding without plasma equipment
- Bridging the gap between prototyping (PDMS) and production (thermoplastic)
- Hypoxia studies (controllable O2 due to low permeability)

### 5.3 COC (Cyclic Olefin Copolymer)

**What it is:** Amorphous thermoplastic copolymer of ethylene and norbornene. Trade names: TOPAS (Polyplastics/TOPAS Advanced Polymers), APEL (Mitsui Chemicals).

| Property | Value |
|----------|-------|
| Young's modulus | 2.6--3.2 GPa (rigid) |
| Transparency | Excellent (>90% in visible, good UV transmission down to ~250 nm) |
| Water absorption | <0.01% (5x lower than PDMS, 10--30x lower than PMMA) |
| Solvent resistance | Resistant to acids, bases, polar solvents (acetone, IPA); sensitive to non-polar solvents (toluene, hexane) |
| Autofluorescence | Very low (excellent for fluorescence assays) |
| Gas permeability | Very low (no gas exchange; no evaporation) |
| Fabrication | Injection molding, hot embossing, CNC milling |
| Bonding | Thermal bonding, solvent bonding (cyclohexane vapor), UV-adhesive |

**Cost:** Raw material is inexpensive; fabrication cost depends on tooling (injection mold tools: $5,000--$50,000+). Per-chip cost in volume: $0.50--$5.

**When to use:**
- Production-scale microfluidics (hundreds to millions of chips)
- Fluorescence-based assays (low autofluorescence, good UV transparency)
- Aqueous-phase chemistry with no non-polar organic solvents
- Applications requiring dimensional stability and rigidity
- Disposable diagnostic chips
- High mold detail replication for micron-scale features

**Limitations:** Cannot be fabricated by soft lithography; requires hot embossing or injection molding equipment; prototyping is slower and more expensive than PDMS.

### 5.4 COP (Cyclic Olefin Polymer)

**What it is:** Homopolymer version of COC. Trade name: Zeonor/Zeonex (Zeon Corporation).

| Property | Value |
|----------|-------|
| Very similar to COC | Slightly better chemical resistance and lower birefringence |
| Autofluorescence | Ultra-low (roughly half the fluorescence of PMMA and TOPAS at UV wavelengths) |
| Water vapor permeability | Extremely low |
| Fabrication | Same as COC (injection molding, hot embossing) |
| Key advantage | Best optical properties for polarization-sensitive measurements; highest mold replication fidelity |

**Common grade:** Zeonor 1060R for microfluidics.

**When to use:** Same applications as COC. Preferred for:
- Optical biosensors requiring ultra-low autofluorescence
- UV-excited fluorescence assays where background must be minimized
- Diagnostics requiring glass-like clarity with plastic moldability
- Polarization-sensitive measurements

### 5.5 PMMA (Polymethyl Methacrylate / Acrylic)

**What it is:** Common thermoplastic, widely available as cast or extruded sheets. Trade names: Plexiglass, Lucite.

| Property | Value |
|----------|-------|
| Young's modulus | 2.4--3.3 GPa (rigid) |
| Transparency | Excellent in visible (92% transmission) |
| UV transparency | Poor below 300 nm |
| Solvent resistance | Poor (attacked by acetone, chloroform, IPA) |
| Water absorption | 0.3--0.4% (much higher than COC) |
| Autofluorescence | Moderate (higher than COC/COP) |
| Fabrication | CNC milling, laser cutting (CO2), hot embossing, solvent bonding |
| Bonding | Solvent bonding (chloroform, dichloromethane), thermal bonding |
| Electrophoresis | Good EOF (electroosmotic flow) properties |

**Cost:** Very low. PMMA sheets: ~$5--$20 per 12" x 12" sheet (1--3 mm thick). CNC milling is fast prototyping from sheet stock.

**When to use:**
- Electrophoresis-based separations (good EOF properties)
- Low-cost disposable chips
- Rapid prototyping via CNC milling or CO2 laser cutting (features >50 um)
- Applications with only aqueous reagents (no organic solvents)
- Teaching and educational labs

**Limitations:** Dissolves in many organic solvents; higher autofluorescence than COC; absorbs water; poor UV transparency.

### 5.6 PC (Polycarbonate)

**What it is:** Engineering thermoplastic known for high impact strength and heat resistance.

| Property | Value |
|----------|-------|
| Young's modulus | 2.0--2.4 GPa |
| Transparency | Good in visible |
| Heat resistance | Up to 130--140 C (higher than PMMA or COC) |
| Autofluorescence | High (worst among common microfluidic polymers) |
| Solvent resistance | Moderate; attacked by acetone, chloroform |
| Fabrication | Injection molding, CNC milling, hot embossing |
| Bonding | Solvent bonding, thermal bonding, adhesive |

**When to use:**
- High-temperature microfluidic applications (PCR, on-chip heating)
- High-pressure applications (strong and tough)
- When impact resistance is needed

**Limitations:** Higher autofluorescence than COC, COP, PMMA, and PDMS; limited solvent compatibility; can yellow with UV exposure.

### 5.7 Norland NOA (Thiol-Ene Optical Adhesive)

**What it is:** NOA 81 (Norland Products Inc.) is a single-component UV-curable liquid adhesive that cures in seconds to a tough, hard polymer. Based on mercapto-ester (thiol-ene) crosslinking chemistry.

| Property | Value |
|----------|-------|
| Cure method | UV exposure (seconds to minutes) |
| Transparency | Optically clear |
| Chemical resistance | Better than PDMS; resistant to many organic solvents |
| Gas/water vapor permeability | Impermeable (unlike PDMS) |
| Surface properties | Adjustable (hydrophilic or hydrophobic via treatment) |
| Fabrication | Replica molding from PDMS molds (double-casting) |

**When to use:**
- Chemically resistant microchannels for organic solvents
- Mid-infrared spectroscopy applications (IR-transparent)
- Low-cost fabrication without plasma bonding equipment
- When gas impermeability is needed

**Fabrication approach:**
1. Cast PDMS mold from SU-8 master (standard soft lithography)
2. Pour NOA 81 into PDMS mold
3. UV cure to crosslink
4. Demold rigid NOA device
5. Bond to glass via partial UV cure + contact + final UV cure

### 5.8 Off-Stoichiometry Thiol-Ene (OSTE) -- General

Beyond the commercial OSTEMER products, the OSTE chemistry platform allows researchers to create custom formulations:
- Tunable mechanical properties from rubber-like to glassy
- Inherent surface functionality from excess thiol or allyl groups
- Click-chemistry-based surface modification
- Low non-specific protein adsorption
- Scalable via reaction injection molding

### 5.9 Flexdym (Eden Tech)

**What it is:** Soft thermoplastic elastomer designed as a direct PDMS replacement.

| Property | Value |
|----------|-------|
| Flexibility | Similar to PDMS |
| Small molecule absorption | Significantly lower than PDMS |
| Fabrication | Hot embossing, compatible with SU-8 masters |
| Bonding | Thermal bonding to glass and thermoplastics |

**When to use:** Drug studies where PDMS absorption is a problem but you want similar mechanical flexibility. Relatively new material with limited track record.

---

## 6. When PDMS Is Good Enough vs. When You Need Something Else

### 6.1 PDMS Is Good Enough When:

1. **You are prototyping.** PDMS is unmatched for speed of iteration: design a mask, make a master, cast PDMS, bond, test -- all in 1--3 days.
2. **You are doing cell biology with aqueous media.** Gas permeability is a feature (O2/CO2 exchange). Biocompatible. Transparent for microscopy.
3. **Your analytes are not small hydrophobic molecules.** Proteins, cells, beads, bacteria -- PDMS is fine. Rule of thumb: if logP < 2, PDMS absorption is minimal.
4. **You need <100 devices.** Hand-casting is acceptable at small scale.
5. **You need pneumatic valves (Quake valves).** PDMS elasticity is essential for membrane deflection.
6. **Your reagents are aqueous.** Water, buffers, cell media -- no compatibility issues.
7. **You are publishing proof-of-concept work.** PDMS is accepted and expected in academic papers.
8. **You need reversible bonding (conformal seal).** PDMS naturally conforms to smooth surfaces.

### 6.2 Move Away from PDMS When:

1. **You are studying drug-cell interactions or small molecule transport.** PDMS absorbs hydrophobic drugs (e.g., paclitaxel, tamoxifen, rhodamine B, imipramine). For compounds with logP > 2, absorption can reach >90%. Use OSTEMER, COC, glass, or NOA.

2. **You need organic solvents in channels.** PDMS swells in chloroform, toluene, hexane, DCM, THF. Even acetone and ethanol cause minor swelling. Use COC, glass, NOA, or stainless steel microfluidics.

3. **You need to scale to >100 devices.** Hand-casting and bonding does not scale. Transition to injection-molded COC/COP or hot-embossed PMMA. Note: PDMS injection molding (LSR-IM) is emerging but still niche.

4. **You need long-term stable surface chemistry.** PDMS hydrophobic recovery after plasma treatment limits stable coatings (hours to days). COC and glass maintain surface modifications much longer.

5. **You need high pressure (>50 psi).** PDMS channels deform under pressure. Rigid materials (COC, PMMA, glass, silicon) handle higher pressures without distortion.

6. **You need low evaporation.** PDMS is gas-permeable -- water evaporates through the bulk. For long-term experiments (days to weeks), channels dry out. Use glass-glass devices, COC, or add humidity control.

7. **You are developing a commercial diagnostic product.** PDMS is difficult to manufacture at scale with consistent quality. COC/COP injection molding is the industry standard for disposable diagnostics (e.g., lateral flow, PCR cartridges).

8. **You need minimal autofluorescence or UV excitation.** COC and COP (especially Zeonex) have lower autofluorescence than PDMS and are transparent to shorter UV wavelengths.

### 6.3 Material Decision Matrix

| Factor | PDMS | OSTEMER | COC/COP | PMMA | PC | NOA 81 |
|--------|------|---------|---------|------|-----|--------|
| Prototyping speed | Excellent | Good | Poor | Good (CNC) | Good (CNC) | Good |
| Production scaling | Poor | Moderate | Excellent | Good | Good | Moderate |
| Drug absorption | High (bad) | Low | Very low | Low | Low | Low |
| Organic solvent use | Poor | Good | Moderate* | Poor | Poor | Good |
| Optical clarity | Excellent | Good | Excellent | Excellent | Good | Good |
| UV transparency | Good | Moderate | Excellent | Poor | Poor | Moderate |
| Autofluorescence | Low | Low | Very low | Moderate | High | Low |
| Gas permeability | High | Low | Very low | Very low | Very low | Very low |
| Flexibility | Excellent | Tunable | Rigid | Rigid | Rigid | Rigid |
| Cost per chip (proto) | $1--$5 | $10--$50 | $50--$500 | $5--$50 | $5--$50 | $5--$20 |
| Cost per chip (volume) | $5--$20 | $5--$20 | $0.50--$5 | $0.50--$5 | $0.50--$5 | $2--$10 |
| Plasma bonding needed | Yes | No (self-bonds) | No | No | No | No |
| Heat resistance | Good (-45 to 200 C) | Good | Moderate | Poor (<80 C) | High (<140 C) | Moderate |

*COC/COP: resistant to polar solvents (acetone, IPA) but sensitive to non-polar solvents (toluene, hexane).

### 6.4 Decision Flowchart

```
START: What is your application?
|
+-- Need organic solvents? --> YES --> Use COC, glass, NOA, or stainless steel
|                           --> NO  --> Continue
|
+-- Drug/small molecule study (logP > 2)? --> YES --> Use OSTEMER, COC, NOA, or glass
|                                          --> NO  --> Continue
|
+-- Need >100 devices? --> YES --> Use COC/COP (injection molding)
|                       --> NO  --> Continue
|
+-- Need pneumatic valves? --> YES --> Use PDMS (essential)
|                           --> NO  --> Continue
|
+-- Need cell culture with gas exchange? --> YES --> Use PDMS
|                                         --> NO  --> Continue
|
+-- Need stable surface chemistry (>1 week)? --> YES --> Use COC, glass, or surface-modified PDMS
|                                              --> NO  --> Continue
|
+-- Budget-constrained prototyping? --> YES --> Use PDMS
|                                    --> NO  --> Choose based on specific requirements
```

### 6.5 Transition Strategy

A practical path many labs follow:

1. **Phase 1 (Proof of concept):** PDMS soft lithography. Fastest to first result. Use SU-8 master + Sylgard 184.
2. **Phase 2 (Validation):** If absorption/solvent issues arise, switch to OSTEMER using the same SU-8 masters. Minimal workflow change.
3. **Phase 3 (Pre-production):** CNC-mill or hot-emboss prototypes in COC/COP to validate thermoplastic design.
4. **Phase 4 (Production):** Commission injection mold tool for COC/COP. Per-chip cost drops to $0.50--$5 at volume.

---

## 7. Complete Soft Lithography Workflow Summary

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

## 8. Troubleshooting PDMS Fabrication

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
| Hydrophobic recovery too fast | High LMW content in PDMS | Store devices in DI water after bonding; pre-bake PDMS at 200 C to drive out LMW; cure at room temperature |
| Surface cracking after plasma | Over-treatment (too long or too high power) | Reduce plasma time (<60 s); reduce power; use air plasma instead of O2 |
| Bond fails with corona treater | Uneven treatment; too far from surface | Hold tip 3--5 mm from surface; sweep slowly and uniformly; bond immediately |

---

## Sources

- [Mechanical Characterization of PDMS with Different Mixing Ratios (ScienceDirect)](https://www.sciencedirect.com/science/article/pii/S245232162200107X)
- [PDMS Elastic Properties: Influence of Fabrication Protocol and Test Method (arXiv)](https://arxiv.org/html/2404.16960v1)
- [Development of PDMS Substrates with Tunable Elastic Modulus (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3519875/)
- [Mechanical Characterization of Bulk Sylgard 184 for Microfluidics (ADS)](https://ui.adsabs.harvard.edu/abs/2014JMiMi..24c5017J/abstract)
- [Rapid Curing of PDMS for Microfluidic Applications (RSC Chips and Tips)](https://blogs.rsc.org/chipsandtips/2006/10/23/rapid-curing-of-pdms-for-microfluidic-applications/)
- [Tailoring Properties of Sylgard 184: Curing (Wiley)](https://onlinelibrary.wiley.com/doi/am-pdf/10.1002/app.48530)
- [NRF PDMS Processing SOP (UFL)](https://nrf.aux.eng.ufl.edu/_files/documents/987.pdf)
- [PDMS Pouring Protocol (OpenWetWare)](https://openwetware.org/wiki/Love:PDMS_pouring)
- [Sylgard 184 PDMS Elastomer (Darwin Microfluidics)](https://darwin-microfluidics.com/products/sylgard-184-pdms-elsatomer)
- [PDMS Properties, Advantages, and Limitations (Alfa Chemistry)](https://microfluidics.alfa-chemistry.com/what-makes-pdms-the-gold-standard-for-microfluidic-chips-properties-advantages-and-limitations.html)
- [PDMS Review in Microfluidics (Elveflow)](https://www.elveflow.com/microfluidic-reviews/general-microfluidics/the-polydimethylsiloxane-pdms-and-microfluidics/)
- [PDMS Optical Properties Characterization (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6928256/)
- [Autofluorescence in Microfluidic Chips (uFluidix)](https://www.ufluidix.com/microfluidic-technical-knowledgebase/autofluorescence-in-microfluidic-chips/)
- [Viable Cell Culture in PDMS-Based Microfluidic Devices](https://taylab.uchicago.edu/uploads/9/1/8/0/91804060/1-s2.0-S0091679X18301304-main.pdf)
- [Variation in Diffusion of Gases Through PDMS (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3945670/)
- [Gas Permeation in PDMS (Wiley)](https://onlinelibrary.wiley.com/doi/abs/10.1002/(SICI)1099-0488(20000201)38:3%3C415::AID-POLB8%3E3.0.CO;2-Z)
- [PDMS Gas Permeability and Crosslinking Temperature (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S1383586613006503)
- [Solvent Compatibility of PDMS-Based Microfluidic Devices (ACS)](https://pubs.acs.org/doi/10.1021/ac0346712)
- [PDMS Solvent Compatibility (Harvard)](https://projects.iq.harvard.edu/files/gmwgroup/files/899.pdf)
- [PDMS Bonding Technologies Review (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8394141/)
- [PDMS Bonding (Harrick Plasma)](https://harrickplasma.com/pdms-bonding/)
- [PDMS Bonding by Corona System (RSC)](https://pubs.rsc.org/en/content/articlelanding/2006/lc/b610567j)
- [PDMS Plasma Bonding (Thierry Corporation)](https://www.thierry-corp.com/pdms-bonding-microfluidics)
- [Plasma Treatment of PDMS (Henniker)](https://plasmatreatment.co.uk/pt/plasma-treatments/plasma-surface-activation-to-improve-adhesion/pdms-bonding-microfluidics)
- [Plasma Treatment for PDMS Bonding (PIE Scientific)](https://piescientific.com/resource-pdms-bonding/)
- [PDMS-PDMS Bonding with O2 Plasma and IPA (MDPI)](https://www.mdpi.com/2073-4360/15/4/1006)
- [Soft Lithography: Glass/PDMS Bonding (Elveflow)](https://elveflow.com/microfluidic-reviews/soft-lithography-glass-pdms-bonding/)
- [Bonding Techniques in Microfluidics (Blackhole Lab)](https://www.blackholelab-soft-lithography.com/bonding-techniques-in-microfluidics)
- [Hydrophobic Recovery of PDMS Surfaces (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8950181/)
- [Long-term Hydrophilization of PDMS (Springer)](https://link.springer.com/article/10.1007/s10404-019-2302-2)
- [PDMS Hydrophobic Recovery and SEM Investigation (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S0925400506006113)
- [Methods to Modify PDMS Surface Wettability (MDPI)](https://www.mdpi.com/2072-666X/15/6/670)
- [PDMS Drug Absorption in Microfluidics (Eden Microfluidics)](https://eden-microfluidics.com/news-events/pdms-drug-absorption-microfluidics-solution/)
- [PDMS Absorption of Small Molecules (PubMed)](https://pubmed.ncbi.nlm.nih.gov/17203151/)
- [Small Molecule Absorption by PDMS in Drug Bioassays (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5240851/)
- [Why You Should Think Twice Before Using PDMS (Eden)](https://eden-microfluidics.com/news-events/why-not-pdms-microfluidics-alternative/)
- [PDMS Mass Fabrication by Injection Molding (Nature)](https://www.nature.com/articles/s41598-025-16863-z)
- [Sorption and Release of Small Molecules in PDMS and COC (Nature)](https://www.nature.com/articles/s41598-025-97111-2)
- [OSTEMER 322 Biocompatibility in Microfluidics (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC10804231/)
- [Off-Stoichiometry Thiol-Ene Polymer (Wikipedia)](https://en.wikipedia.org/wiki/Off-stoichiometry_thiol-ene_polymer)
- [OSTEMER-Thermoplastic Hybrid Microfluidic Devices (Wiley)](https://advanced.onlinelibrary.wiley.com/doi/full/10.1002/admi.202300972)
- [Thiol-Ene Microfluidics for Hypoxia Assays (RSC)](https://pubs.rsc.org/en/content/articlehtml/2021/lc/d0lc01292k)
- [COC Review in Microfluidics (Wiley)](https://onlinelibrary.wiley.com/doi/full/10.1002/mame.202200053)
- [Cyclic Olefin Polymers for Lab-on-a-Chip (Springer)](https://link.springer.com/article/10.1007/s10404-010-0605-4)
- [Polymers in Microfluidics (microfluidic ChipShop)](https://www.microfluidic-chipshop.com/microfluidics/materials-in-microfluidics/polymers-in-microfluidics/)
- [Zeonor COP for Microfluidics (Zeon)](https://zeonsmi.com/applications/microfluidics/)
- [NOA 81 Microchannels with Chemical Resistance (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S0925400511001031)
- [NOA 81 Optical Adhesive (Norland Products)](https://norlandproducts.com/product/noa-81/)
- [Diener Zepto Plasma Bonding Protocol (EPJ Conferences)](https://www.epj-conferences.org/articles/epjconf/pdf/2021/09/epjconf_eosam2021_12009.pdf)
- [PDMS Soft Lithography: Plasma Cleaner (Elveflow)](https://www.elveflow.com/microfluidic-reviews/soft-lithography-microfabrication/pdms-soft-lithography-plasma-cleaner/)
