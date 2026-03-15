# Laser Processing & Glass/Silicon Microfluidics Fabrication

> Last updated: March 2026

## Overview

This document covers two categories of microfluidic fabrication:
1. **Laser processing** — using CO2, UV, excimer, and femtosecond lasers to directly create microfluidic features in polymers and glass
2. **Glass and silicon microfabrication** — wet etching, dry etching (DRIE), and bonding methods for inorganic substrate microfluidics

These methods complement the thermoplastic replication approaches (hot embossing, injection molding) covered in `07_fabrication_embossing_molding.md`.

---

# Part I: Laser Processing

## 1. CO2 Laser Cutting/Engraving for PMMA Microfluidics

### What It Is

CO2 lasers (wavelength 10.6 um) are strongly absorbed by PMMA/acrylic, enabling direct ablation of channels by raster engraving (area removal) or vector cutting (through-cuts for layer-based devices). This is one of the fastest and most accessible methods for microfluidic prototyping.

### Process Modes

| Mode | Description | Channel Profile | Best For |
|------|-------------|----------------|----------|
| **Raster engraving** | Laser sweeps back and forth, ablating surface | U-shaped, flatter bottom | Wide channels, chambers, reservoirs |
| **Vector cutting** | Laser follows a path in a single pass | V-shaped, Gaussian profile | Narrow channels, through-holes, outlines |
| **Multi-pass vector** | Multiple passes at lower power | More controlled depth | Deeper channels with better control |

### Equipment

| Manufacturer | Model Examples | Power Range | Work Area | Resolution | Approx. Price |
|-------------|---------------|-------------|-----------|------------|---------------|
| **Epilog** | Mini 24, Fusion Pro | 30-120 W | 12"x24" to 32"x20" | Up to 1200 dpi | $8K-$45K |
| **Trotec** | Speedy 100, Speedy 360, SP500 | 30-120 W | 24"x12" to 49"x28" | Up to 1000 dpi | $15K-$60K |
| **Universal Laser** | VLS 2.30, VLS 6.60, PLS 4.75 | 25-75 W | 12"x24" to 32"x18" | Up to 1000 dpi | $10K-$50K |
| **Budget Chinese CO2** | K40, OMTech, etc. | 40-100 W | Various | ~500 dpi | $400-$3,000 |

### Achievable Resolution and Feature Sizes

| Parameter | Typical Range | Notes |
|-----------|--------------|-------|
| Minimum channel width | 50-100 um (high-end); 100-200 um (typical) | Limited by beam spot size (~100 um for focused CO2) |
| Channel depth | 10-500 um (controllable via power/speed) | Depth shows non-linear relationship with fluence |
| Depth control precision | +/- 10-20 um | Affected by material variability |
| Minimum through-hole | ~200 um | Material dependent |
| Surface roughness (channel floor) | Ra 0.5-5 um | Rough compared to mold-replicated; can be improved by chemical polishing |
| Positional accuracy | 25-100 um | Depends on machine quality |

### Cost Analysis

| Item | Cost |
|------|------|
| Equipment (research-grade) | $10K-$50K |
| Equipment (budget) | $400-$3,000 |
| PMMA sheet (per device) | $0.10-$1 |
| Operating cost (electricity, gas) | Minimal |
| **Per-device cost (materials + time)** | **$0.10-$5** |
| Makerspace/fab lab access (hourly) | $10-$50/hr |

### Channel Quality Improvement

CO2 laser channels have rough surfaces. Post-processing options:

1. **Solvent vapor polishing** — brief exposure to chloroform or dichloromethane vapor smooths PMMA surfaces dramatically
2. **Thermal annealing** — heating below Tg smooths surface features
3. **Chemical post-processing** — demonstrated to yield "excellent quality microchannels" after CO2 laser writing

### Pros and Cons

**Pros:**
- Very fast prototyping (minutes per device)
- Low cost equipment widely available (makerspaces, universities)
- No cleanroom required
- PMMA/acrylic is cheap and widely available
- Design changes are instant (change CAD file)
- Can cut complex 2D patterns and layer-based 3D structures

**Cons:**
- Rough channel surfaces (Ra ~1-5 um) — problematic for some applications
- Limited resolution (~100 um minimum practical feature)
- Heat-affected zone can cause material reflow and bulging at edges
- Gaussian beam profile creates V-shaped or rounded channel cross-sections
- Depth control is approximate
- Limited to materials that absorb at 10.6 um (PMMA, PS — not COC/COP easily)

### Typical Lead Time

Design to working prototype: **hours to 1 day**

---

## 2. Femtosecond Laser Machining for Glass Microfluidics

### What It Is

Femtosecond (fs) lasers deliver ultrashort pulses (< 1 ps) that modify transparent materials through multiphoton absorption. This enables 3D internal structuring of glass without surface damage. Two main approaches:

1. **Femtosecond Laser Irradiation followed by Chemical Etching (FLICE)** — also called Selective Laser-induced Etching (SLE): laser modifies glass internally, then preferential wet etching (KOH or HF) removes modified regions
2. **Direct ablation** — higher pulse energies directly remove material

### Key Manufacturers/Services

| Company | Technology | Capabilities | Substrate | Approx. System Cost |
|---------|-----------|-------------|-----------|-------------------|
| **LightFab** (Aachen, Germany) | SLE (Selective Laser-induced Etching) via LightFab 3D Printer | 3D channels in fused silica; max depth 5-7 mm; area up to 200x200 mm; pore sizes down to 5 um | Fused silica (quartz glass) | ~$500K-$1M+ |
| **FEMTOprint** (Moutier, Switzerland) | Femtosecond laser + etching | 3D glass microfluidics, micro-optics, micromechanics integrated; sub-micron features; MedTech focus | Fused silica, borosilicate | ~$500K-$1M (system); custom parts as service |
| **Optec** (Frameries, Belgium) | Femtosecond and excimer laser micromachining | Contract manufacturing, systems | Various | $200K-$500K (systems) |

### Resolution and Feature Sizes

| Parameter | FLICE/SLE | Direct fs Ablation |
|-----------|-----------|-------------------|
| Minimum channel diameter | 10-50 um | 5-20 um |
| Minimum wall thickness | ~20 um | ~10 um |
| Surface roughness (channel) | Ra 100-500 nm (post-etch) | Ra 50-200 nm |
| Aspect ratio | Up to 50:1 | Up to 10:1 |
| 3D capability | Full 3D embedded channels | Surface and shallow 3D |
| Maximum processing depth | 5-7 mm in fused silica | ~0.5-1 mm |
| Positional accuracy | < 1 um | < 1 um |

### Cost Considerations

| Item | Cost Range |
|------|-----------|
| Femtosecond laser system | $200K-$1M+ |
| LightFab 3D Printer | ~$500K-$1M |
| Contract manufacturing (per device) | $50-$500 depending on complexity |
| Fused silica substrate | $5-$50 per piece |
| Processing time per chip | Minutes to hours (depends on channel volume) |

### Advantages of Femtosecond Laser Glass Processing

- **True 3D channels** — buried channels at any depth and orientation, impossible with planar lithography
- **Monolithic** — no bonding required (channels are etched inside bulk glass)
- **No cleanroom** — laser processing does not require cleanroom environment
- **Fused silica properties** — ultimate chemical resistance, optical transparency (UV to IR), thermal stability, biocompatibility
- **Integration** — can combine microfluidics, micro-optics, and waveguides in single substrate
- **Rapid design iteration** — CAD-to-part with no masks

### Limitations

- Slow for high volumes (serial writing process)
- High capital cost
- Channel surface roughness can require post-processing
- Etching step adds time and introduces selectivity constraints
- Limited to materials with suitable nonlinear absorption

---

## 3. Excimer Laser Ablation

### What It Is

Excimer lasers produce high-energy UV pulses at specific wavelengths. The UV photons break chemical bonds in polymers directly (photochemical ablation), producing clean channels with minimal heat-affected zone compared to CO2 lasers.

### Excimer Laser Types

| Laser Type | Wavelength | Photon Energy | Best Materials |
|-----------|-----------|---------------|----------------|
| **ArF** | 193 nm | 6.4 eV | PMMA, PS, PC, polyimide — best overall for polymers |
| **KrF** | 248 nm | 5.0 eV | PMMA, polyimide, PET |
| **XeCl** | 308 nm | 4.0 eV | Polyimide, PET, some polymers |
| **XeF** | 351 nm | 3.5 eV | Limited polymer absorption |

### Key Parameters

| Parameter | Typical Range |
|-----------|--------------|
| Fluence | 0.1-10 J/cm2 per pulse |
| Repetition rate | 1-500 Hz |
| Pulse duration | 10-30 ns |
| Ablation rate | 0.1-1 um per pulse (material dependent) |
| Minimum feature (with mask) | 1-5 um |
| Minimum feature (direct write) | 5-20 um |

### Process Approaches

1. **Mask projection** — UV beam illuminates a metal mask; demagnification optics project the pattern onto the substrate. Produces the entire channel pattern in parallel.
2. **Direct write** — focused beam scans across the surface. More flexible but slower.
3. **Step-and-repeat** — combination of mask projection with stage motion for large areas.

### Equipment and Cost

| Component | Cost Range |
|-----------|-----------|
| Excimer laser source | $50K-$200K |
| Beam delivery / projection optics | $20K-$100K |
| Motion stage (precision) | $10K-$50K |
| Complete micromachining station | $100K-$400K |
| Mask fabrication | $500-$5,000 per mask |
| Contract service (per design) | $1K-$10K |

### Resolution

| Attribute | Performance |
|-----------|------------|
| Minimum feature (mask projection) | 1-5 um |
| Channel depth control | +/- 0.5-2 um |
| Surface roughness | Ra 10-100 nm (much smoother than CO2) |
| Sidewall angle | Near-vertical for many polymers |
| Aspect ratio | Up to 10:1 |

### Pros and Cons

**Pros:**
- Clean photochemical ablation — minimal thermal damage
- Excellent surface quality (Ra 10-100 nm)
- High resolution (1-5 um features with mask projection)
- Parallel processing with mask (high throughput)
- Can modify surface chemistry simultaneously (improved wettability)
- Works on many polymers including PMMA, PS, PC, polyimide

**Cons:**
- High equipment cost
- Requires toxic gas handling (fluorine, chlorine, krypton)
- Mask-based approach reduces flexibility
- Limited depth per pulse — slow for deep channels
- Gas refills and tube maintenance
- Not commonly available outside specialized facilities

---

## 4. UV Laser Micromachining (DPSS and Fiber Lasers)

### What It Is

Solid-state UV lasers (typically frequency-tripled Nd:YAG at 355 nm or frequency-quadrupled at 266 nm) provide a more accessible alternative to excimer lasers. These diode-pumped solid-state (DPSS) or UV fiber lasers are maintenance-free compared to gas-based excimer systems.

### Equipment

| Type | Wavelength | Pulse Duration | Typical Power | Approx. Cost |
|------|-----------|---------------|---------------|-------------|
| DPSS Nd:YAG (3rd harmonic) | 355 nm | 10-30 ns | 3-20 W | $30K-$100K |
| DPSS Nd:YAG (4th harmonic) | 266 nm | 10-30 ns | 1-5 W | $50K-$150K |
| UV fiber laser | 355 nm | 1-100 ns (adjustable) | 5-50 W | $20K-$80K |
| Picosecond UV | 355 nm | 10-15 ps | 1-10 W | $80K-$200K |

### Capabilities

| Parameter | Range |
|-----------|-------|
| Minimum feature | 5-25 um |
| Ablation rate | 0.1-5 um/pulse (material dependent) |
| Surface roughness | Ra 50-500 nm |
| Depth control | +/- 2-10 um |
| Materials | PMMA, PS, PC, polyimide, ceramics, thin metals |

### When to Use UV DPSS vs. CO2 vs. Excimer

| Criterion | CO2 | UV DPSS (355 nm) | Excimer (193/248 nm) | Femtosecond |
|-----------|-----|-------------------|---------------------|-------------|
| Resolution | 50-200 um | 5-25 um | 1-5 um | 1-10 um |
| Surface quality | Poor | Moderate | Excellent | Good-Excellent |
| Cost | $5K-$50K | $30K-$150K | $100K-$400K | $200K-$1M |
| Maintenance | Low | Low | High (gas) | Moderate |
| Glass processing | No | Limited | Limited | Yes (3D) |
| Speed | Fast | Moderate | Fast (mask) | Slow |
| Cleanroom needed | No | No | No | No |
| Best for | PMMA prototyping | Mid-resolution polymer | High-res polymer | Glass, 3D |

---

# Part II: Glass & Silicon Microfluidics

## 5. Wet Etching

### Glass Wet Etching (HF-based)

#### Process Overview

Glass is etched using hydrofluoric acid (HF) solutions. The process is **isotropic** — etching proceeds equally in all directions, producing rounded channel cross-sections.

#### Process Steps

1. **Deposit masking layer** — Cr/Au (50/500 nm) or amorphous silicon sputtered onto glass
2. **Photolithography** — spin-coat photoresist, expose, develop
3. **Etch mask pattern** — wet etch metal mask to expose glass
4. **HF etching** — immerse in HF solution; etch time controls depth
5. **Strip mask** — remove remaining Cr/Au
6. **Clean** — thorough rinsing
7. **Bond** — seal with second glass wafer or PDMS

#### Etch Rates

| Glass Type | HF Concentration | Etch Rate | Notes |
|-----------|-----------------|-----------|-------|
| Borosilicate (Pyrex 7740, Borofloat 33) | 49% HF | ~8 um/min | Most common for microfluidics |
| Borosilicate | 10% HF | ~1.5 um/min | Better control for shallow channels |
| Fused silica (quartz) | 49% HF | ~1.3 um/min | Much slower — more resistant |
| Soda-lime glass | 49% HF | ~5-7 um/min | Faster but less controlled, cheaper substrate |
| Borosilicate | BOE (buffered oxide etch) | ~0.5-1 um/min | Most controlled, smoothest surface |

#### Masking Materials

| Mask | Thickness | HF Resistance | Notes |
|------|-----------|---------------|-------|
| Cr/Au | 50/500 nm | Good — hours in 49% HF | Industry standard; Au resists HF, Cr is adhesion layer |
| Amorphous silicon | 100-500 nm | Moderate | CMOS compatible alternative |
| Photoresist alone | 1-10 um | Poor — minutes in concentrated HF | Only for very shallow etches or dilute HF |
| SiN (LPCVD) | 100-500 nm | Excellent | Best for deep etches |
| Polysilicon | 0.5-1 um | Good | Alternative to Cr/Au |

#### Key Characteristics

- **Isotropic** etch profile: undercut equals depth (1:1 aspect ratio limit)
- Maximum practical depth: ~100-200 um (limited by mask erosion and undercut)
- Surface roughness: Ra 1-10 nm (very smooth — excellent for optical applications)
- Channel width = mask opening + 2x depth (due to undercut)

#### Equipment Required

| Equipment | Purpose | Approx. Cost |
|-----------|---------|-------------|
| Fume hood (HF-rated) | Safety containment | $10K-$30K |
| HF-compatible wet bench | Chemical processing | $20K-$80K |
| Spin coater | Photoresist application | $5K-$15K |
| Mask aligner | UV exposure | $50K-$300K |
| Sputter/evaporator | Mask deposition (Cr/Au) | $50K-$300K |
| Profilometer | Depth measurement | $20K-$80K |
| **Total cleanroom setup** | | **$200K-$800K+** |

#### Safety

HF is extremely hazardous. Requires:
- Dedicated HF-rated fume hood and wet bench
- Calcium gluconate gel on hand at all times
- HF-specific PPE (face shield, double gloving with neoprene, apron)
- Buddy system — never work with HF alone
- HF exposure training for all personnel
- Emergency shower and eyewash within 10 seconds travel

### Silicon Wet Etching (KOH/TMAH)

#### Process Overview

Silicon is etched **anisotropically** by KOH or TMAH — the etch rate depends on crystallographic orientation. {111} planes etch ~100-400x slower than {100} planes, producing V-grooves and flat-bottomed trenches with 54.7-degree sidewalls in (100) silicon.

#### Etchant Comparison

| Property | KOH | TMAH |
|----------|-----|------|
| Typical concentration | 30-40 wt% | 20-25 wt% |
| Temperature | 60-80 deg C | 80-90 deg C |
| Etch rate {100} | 0.5-1.5 um/min | 0.5-1.0 um/min |
| {100}:{111} selectivity | ~400:1 | ~30-50:1 |
| SiO2 selectivity | ~200:1 | ~5000:1 |
| CMOS compatible | No (K+ contamination) | Yes |
| Surface roughness | Smooth | Smooth (with IPA additive) |
| Mask material | SiO2 or Si3N4 | SiO2 or Si3N4 |
| Cost | Very low | Moderate |
| Handling | Caustic | Caustic, toxic fumes |

#### Achievable Geometries

| Feature | (100) Wafer | (110) Wafer |
|---------|------------|------------|
| Channel profile | V-groove (54.7 deg walls) or flat bottom | Vertical walls (perpendicular {111} planes) |
| Aspect ratio | Limited by 54.7 deg angle | High aspect ratio possible |
| Minimum width | ~1-2 um | ~1-2 um |
| Maximum depth | Through-wafer (500+ um) | Through-wafer |
| Depth control | +/- 0.5 um with timed etch | +/- 0.5 um |

#### Process Steps

1. **Grow/deposit mask** — thermal SiO2 (for moderate etch depths) or LPCVD Si3N4 (for deep etches)
2. **Photolithography** — pattern the mask layer
3. **Etch mask** — BOE for SiO2, hot phosphoric acid for Si3N4
4. **KOH/TMAH etch** — timed immersion at controlled temperature
5. **Clean** — piranha or SC-1 clean
6. **Bond** — anodic bonding to glass, or fusion bonding to another silicon wafer

---

## 6. Dry Etching — DRIE (Deep Reactive Ion Etching)

### What It Is

DRIE enables deep, high-aspect-ratio etching of silicon with near-vertical sidewalls. The dominant process is the **Bosch process** (patented by Robert Bosch GmbH), which alternates between etching and passivation steps.

### Bosch Process Mechanism

1. **Etch step**: SF6 plasma isotropically etches silicon (~1-5 um per cycle)
2. **Passivation step**: C4F8 plasma deposits conformal fluorocarbon polymer on all surfaces
3. **Next etch step**: Ion bombardment preferentially removes passivation from horizontal surfaces; vertical sidewall passivation protects against lateral etching
4. **Repeat**: Cycles of 5-15 seconds each, hundreds to thousands of cycles for deep features

This creates the characteristic "scalloped" sidewalls (scallop amplitude 50-200 nm).

### Alternative: Cryogenic DRIE

- Substrate cooled to -100 to -120 deg C
- SiF4 passivation occurs naturally at low temperature
- Produces smooth sidewalls (no scalloping)
- Less commonly available

### Equipment

| Manufacturer | Model Series | Key Features | Wafer Size | Approx. Price |
|-------------|-------------|-------------|-----------|---------------|
| **Oxford Instruments** | PlasmaPro 100 Estrelas (DSiE) | Flexible Bosch and cryo modes; R&D through production | Up to 200 mm | $500K-$1.5M |
| **Oxford Instruments** | PlasmaPro 100 Cobra | ICP-RIE for general etching; Bosch capable | Up to 200 mm | $400K-$800K |
| **SPTS Technologies** | Omega Rapier | High etch rates, production-grade; dual plasma source | Up to 200 mm | $500K-$1.5M |
| **SPTS Technologies** | DSi-v2 | R&D focused DRIE | Up to 200 mm | $300K-$700K |
| **Plasma-Therm** | Versaline DSE | Deep silicon etching; modular platform | Up to 200 mm | $400K-$1M |
| **Samco** | RIE-400iPBc | ICP-RIE with Bosch process | Up to 200 mm | $300K-$600K |
| **ULVAC** | NLD series | Neutral Loop Discharge; high uniformity | Up to 300 mm | $500K-$1.5M |

### Performance Specifications

| Parameter | Typical | Best Reported |
|-----------|---------|---------------|
| Etch rate | 5-20 um/min | >50 um/min |
| Aspect ratio | 20:1 typical | >50:1 |
| Sidewall angle | 89-90 deg | 90 +/- 0.5 deg |
| Scallop amplitude | 50-200 nm | <20 nm (optimized) |
| Selectivity to SiO2 mask | 100-200:1 | >300:1 |
| Selectivity to photoresist | 50-100:1 | >150:1 |
| Uniformity (across wafer) | +/- 2-5% | <1% |
| Maximum depth | Through-wafer (775 um for 200mm wafer) | >1 mm |
| Minimum feature | ~1 um | ~0.5 um |

### Cost Considerations

| Item | Cost Range |
|------|-----------|
| DRIE equipment | $300K-$1.5M |
| Operating cost per wafer (gas, power) | $10-$50 |
| Process time per wafer | 30 min - 4 hours (depth dependent) |
| Cleanroom access fee (university fab) | $50-$200/hr |
| Contract DRIE service (per wafer) | $200-$1,000 |
| Full process (lithography + DRIE) per wafer | $500-$2,000 |

### When to Use DRIE vs. Wet Etching

| Criterion | DRIE (Bosch) | Wet Etch (KOH/TMAH) |
|-----------|-------------|---------------------|
| Sidewall profile | Vertical (any geometry) | Crystallographic (54.7 deg or vertical for specific orientations) |
| Aspect ratio | >20:1 | Limited by crystal planes |
| Design freedom | Any 2D pattern | Constrained to crystal-aligned features |
| Surface quality | Scalloped (can be smoothed) | Atomically smooth {111} planes |
| Cost | High (equipment) | Low (chemicals) |
| Throughput | Moderate (single wafer) | High (batch, multiple wafers) |
| Depth uniformity | Good with optimization | Excellent (crystallographic etch stop) |
| Through-wafer capability | Yes | Yes (with proper masking) |

---

## 7. Glass-Glass Bonding

### Thermal (Fusion) Bonding

| Parameter | Details |
|-----------|---------|
| **Process** | Two clean, flat glass surfaces brought into contact; heated to near softening point; pressure applied |
| **Temperature** | 500-650 deg C (borosilicate); 1000+ deg C (fused silica) |
| **Pressure** | 1-10 kN (light contact) |
| **Time** | 2-8 hours at temperature |
| **Surface prep** | Critical — RCA clean or piranha; surfaces must be particle-free, <1 nm roughness |
| **Bond strength** | Very high (monolithic) |
| **Advantages** | No intermediate layers, optically transparent bond, chemically inert |
| **Disadvantages** | High temperature (incompatible with pre-deposited metals/reagents), stringent surface requirements |

### Adhesive Bonding

| Parameter | Details |
|-----------|---------|
| **Adhesives** | UV-curable epoxy, SU-8, BCB, silicone |
| **Temperature** | Room temperature to 200 deg C |
| **Bond strength** | Moderate to high |
| **Advantages** | Low temperature, tolerant of surface roughness |
| **Disadvantages** | Adhesive in channel risk, chemical compatibility limits, outgassing |

### Anodic Bonding (Glass-Glass with Intermediate Layer)

Direct glass-glass anodic bonding is possible using a thin metal intermediate layer (e.g., Ti, 80 nm) or a thin sputtered silicon layer between the glass substrates.

| Parameter | Details |
|-----------|---------|
| **Temperature** | 400-530 deg C |
| **Voltage** | 100-800 V |
| **Intermediate layer** | Ti (~80 nm) or sputtered Si (~100-500 nm) |
| **Time** | 30-60 minutes |
| **Materials** | Borosilicate glass (Corning 7740, Borofloat 33, Tempax) |
| **Bond strength** | High |
| **Advantages** | Strong hermetic seal, lower temperature than fusion bonding |
| **Disadvantages** | Requires intermediate layer deposition, limited glass types |

---

## 8. Silicon-Glass Anodic Bonding

### Process Overview

Anodic bonding creates an irreversible, hermetic bond between silicon and alkali-containing glass (typically Pyrex/Borofloat). An electric field at elevated temperature drives Na+ ions away from the interface, creating a strong electrostatic attraction and permanent chemical bond.

### Process Parameters

| Parameter | Typical Range | Optimized |
|-----------|--------------|-----------|
| Temperature | 300-450 deg C | 350-400 deg C |
| Voltage | 200-1200 V | 600-1000 V |
| Time | 10-60 minutes | 30-45 minutes |
| Pressure | Contact to 2000 mbar | Process dependent |
| Atmosphere | Air, N2, or vacuum | Vacuum for sealed cavities |
| Leakage rate | | < 0.4 x 10^-9 Pa m3/s achievable |

### Compatible Materials

| Glass | CTE Match to Si | Notes |
|-------|----------------|-------|
| Corning 7740 (Pyrex) | Good | Classic choice, discontinued in some forms |
| Borofloat 33 (Schott) | Good | Widely available alternative to Pyrex |
| Tempax (Schott) | Good | Similar to Borofloat |
| SD-2, SD-4 (Hoya) | Good | Japanese supplier |

**Critical requirement**: Glass must contain mobile Na+ ions (alkali glass). CTE must match silicon (2.6 x 10^-6 /K) to avoid cracking.

### Process Physics

1. Elevated temperature increases Na+ ion mobility in glass
2. Applied voltage (glass negative) drives Na+ away from glass-silicon interface
3. Depletion region forms at interface with strong electrostatic field
4. Electrostatic force pulls surfaces into intimate contact
5. At contact, oxygen from glass reacts with silicon to form SiO2 — permanent covalent bond

### Key Process Factors (by Influence on Bond Quality)

1. **Temperature** — most dominant influence on leakage rate and bond strength
2. **Time** — second most important factor
3. **Voltage** — third most important; higher voltage speeds process but risk of dielectric breakdown

### Equipment

| Equipment | Approx. Cost |
|-----------|-------------|
| Anodic bonder (manual, research) | $20K-$80K |
| Automated wafer bonder (EVG, SUSS) | $200K-$800K |
| Hot plate + DC power supply (DIY) | $1K-$5K |

### Pros and Cons

**Pros:**
- Hermetic seal (gas-tight)
- Strong bond (approaching bulk fracture strength)
- Relatively low temperature (vs. glass fusion bonding)
- No adhesives or intermediate materials in bond
- Optically clear bond interface
- Well-established, reliable process

**Cons:**
- Limited to alkali-containing glass
- CTE matching required
- High voltage (safety considerations)
- Sodium contamination concern for CMOS devices
- Requires very clean, smooth surfaces
- Metal traces near bond area can interfere

---

## 9. When to Use Glass/Silicon vs. Polymer

### Decision Matrix

| Criterion | Glass | Silicon | Polymer (COC/COP/PMMA) |
|-----------|-------|---------|------------------------|
| **Chemical resistance** | Excellent (all solvents, acids, bases) | Good (most solvents; attacked by KOH, HF) | Moderate (polar solvents OK, non-polar attack COC/COP) |
| **Optical transparency** | Excellent (UV to IR) | Opaque (IR only) | Good visible; COC/COP fair UV |
| **Autofluorescence** | Very low | N/A (opaque) | Low (COC/COP) to moderate (PMMA) |
| **Thermal stability** | Excellent (>500 deg C) | Excellent (>500 deg C) | Limited (< Tg, typically 80-150 deg C) |
| **Surface chemistry** | Well-characterized silanol groups | Native oxide (SiO2-like) | Variable; requires activation |
| **Biocompatibility** | Excellent, bioinert | Good | Good (COC/COP, PS) |
| **Gas permeability** | Zero | Zero | Low (COC/COP) to moderate (PMMA) |
| **Protein adsorption** | Low (with treatment) | Low (with treatment) | Low to moderate |
| **Fabrication cost (prototype)** | High ($500-$5K/wafer) | High ($200-$2K/wafer) | Low ($1-$50/device) |
| **Mass production cost** | Very high | High | Very low ($0.10-$2/device) |
| **Lead time (prototype)** | 2-6 weeks | 2-6 weeks | Hours to days |
| **Scalability** | Limited (batch, wafer-level) | Good (semiconductor infrastructure) | Excellent (injection molding) |
| **Design iteration speed** | Slow (new masks, etching) | Slow (new masks, etching) | Fast (new mold or direct write) |

### When to Choose Glass

- **Solvent-based chemistry**: organic synthesis, solvent extraction, chromatography
- **High-pressure applications**: glass withstands higher pressures than thin-wall polymer
- **Optical detection requiring UV/deep-UV**: fluorescence excitation < 350 nm
- **Long-term stability**: implantable devices, reusable instruments
- **Electrokinetic separations**: well-characterized electroosmotic flow on glass surfaces
- **Droplet generation**: glass surface chemistry is more stable and controllable than polymer

### When to Choose Silicon

- **High-aspect-ratio structures**: DRIE enables >20:1 vertical features
- **Integrated electronics/sensors**: natural substrate for CMOS, thin-film electrodes
- **Thermal management**: excellent thermal conductivity (150 W/mK) for PCR, chemical reactions
- **Precision geometries**: DRIE and anisotropic etching give submicron precision
- **Harsh environments**: high temperature, high pressure

### When to Choose Polymer

- **Disposable/single-use devices**: cost-effective at any volume
- **Point-of-care diagnostics**: injection molding enables mass production at $0.10-$1/chip
- **Rapid prototyping**: iterate designs in hours, not weeks
- **Biological assays**: PS is cell-culture standard; COC/COP have low protein binding
- **Cost-sensitive applications**: overwhelmingly cheaper at scale
- **Regulatory path for IVD**: established manufacturing processes (injection molding, ISO 13485)

### Hybrid Approaches

Many practical devices combine materials:

| Combination | Application |
|-------------|-------------|
| Glass channels + PDMS valves | Solvent-resistant channels with pneumatic control |
| Silicon heaters + glass channels | PCR microfluidics |
| Polymer chip + glass detection window | Cost-effective with optical quality where needed |
| Silicon substrate + polymer microfluidics | Integrated sensors with disposable fluidics |

---

## 10. Process Comparison Summary

| Method | Min Feature | Surface Roughness | Cost/Device (Proto) | Cost/Device (Volume) | Lead Time | Best Application |
|--------|-----------|-------------------|--------------------|--------------------|-----------|-----------------|
| CO2 laser (PMMA) | 50-100 um | Ra 1-5 um | $0.10-$5 | $0.10-$1 | Hours | Rapid PMMA prototypes |
| UV DPSS laser | 5-25 um | Ra 50-500 nm | $5-$50 | $2-$20 | Days | Mid-resolution polymer |
| Excimer laser | 1-5 um | Ra 10-100 nm | $50-$500 | $10-$100 | 1-2 weeks | High-res polymer |
| Femtosecond/SLE (glass) | 10-50 um | Ra 100-500 nm | $50-$500 | $20-$200 | 1-4 weeks | 3D glass microfluidics |
| Glass wet etch (HF) | 5-20 um | Ra 1-10 nm | $200-$2K | $50-$200 | 2-6 weeks | Optical/chemical apps |
| Si wet etch (KOH) | 1-2 um | Atomically smooth | $100-$1K | $20-$100 | 2-6 weeks | Crystallographic channels |
| Si DRIE (Bosch) | 0.5-2 um | Scalloped 50-200 nm | $200-$2K | $50-$200 | 2-6 weeks | High-AR, vertical walls |
| Hot embossing | Sub-um (mold dep.) | Mold-dependent | $20-$200 | $2-$10 | 2-6 weeks | Low-volume thermoplastic |
| Injection molding | 1-5 um | Mold-dependent | $5K-$50K (setup) | $0.10-$2 | 6-16 weeks | Mass production |

---

## References and Sources

- [A Practical Guide for the Fabrication of Microfluidic Devices Using Glass and Silicon (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3365353/)
- [Fabrication Methods for Microfluidic Devices: An Overview (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8002879/)
- [LightFab Products — Selective Laser Etching](https://lightfab.de/LightFab_Products.html)
- [FEMTOPRINT — 3D Printing for Glass Microdevices](https://www.femtoprint.ch/)
- [SLE of 3D Precision Quartz Glass Components (MDPI)](https://www.mdpi.com/2072-666X/8/4/110)
- [Oxford Instruments — PlasmaPro 100 Estrelas DRIE](https://plasma.oxinst.com/products/dsie/plasmapro-100-estrelas-dsie)
- [SPTS / Plasma-Therm — DRIE Technology](https://corial.plasmatherm.com/en/technologies/drie-deep-reactive-ion-etching)
- [Deep Reactive-Ion Etching (Wikipedia)](https://en.wikipedia.org/wiki/Deep_reactive-ion_etching)
- [Anodic Bonding (Wikipedia)](https://en.wikipedia.org/wiki/Anodic_bonding)
- [What Is Anodic Bonding? (UniversityWafer)](https://www.universitywafer.com/anondic-bonding.html)
- [Glass vs Polymer Microfluidics (Potomac Laser)](https://www.potomac-laser.com/material/microfluidics-polymers-vs-glass/)
- [Choosing Materials for Microfluidic Chips (Blacksheep Sciences)](https://www.blacksheepsciences.com/publications/choosing-materials-for-microfluidic-chips)
- [Microfluidics Hub — Wet Etching](https://www.microfluidicshub.eu/manufacturing/wet-etching)
- [Micronit — Etching Capabilities](https://www.micronit.com/manufacturing/capabilities/etching)
- [CO2 Laser Machining for Microfluidics (Springer)](https://link.springer.com/article/10.1007/s00542-020-04902-w)
- [UV Laser Micromachining of Polymers for Microfluidic Applications (SLAS Technology)](https://slas-technology.org/article/S1535-5535(04)00179-0/fulltext)
- [KOH and TMAH Etching of Bulk Silicon](https://microfluidicfoundry.com/Literature/Wet-Etching-of-Bulk-Silicon.pdf)
- [Chemical Resistance of Microfluidic Materials (Elveflow)](https://elveflow.com/microfluidic-reviews/chemical-resistance-of-microfluidic-materials/)
- [Maskless Rapid Manufacturing of Glass Microfluidic Devices Using Picosecond Laser (Nature)](https://www.nature.com/articles/s41598-019-56711-5)
- [Material Selection for Microfluidic Devices (Parallel Fluidics)](https://www.parallelfluidics.com/resources/knowledge-base/material-selection-for-microfluidic-devices)
- [Laser Processing for Bio-Microfluidics Applications (Springer)](https://link.springer.com/article/10.1007/s00216-006-0514-2)
