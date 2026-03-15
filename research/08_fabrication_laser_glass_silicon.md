# Laser Processing and Glass/Silicon Microfluidics

> Research compiled March 2026. Covers CO2 laser cutting of polymers, femtosecond laser machining of glass (SLE), excimer laser ablation, glass wet etching, silicon DRIE, bonding techniques, and decision criteria for glass/silicon vs. polymer fabrication.

---

## 1. CO2 Laser Cutting for PMMA/Acrylic

### What It Is
CO2 laser cutting/engraving uses a 10.6 um wavelength infrared laser to ablate, cut, or engrave polymer substrates -- most commonly PMMA (poly(methyl methacrylate), acrylic). The laser heats and vaporizes material, leaving channels or through-cuts. This is one of the fastest and most accessible methods for fabricating polymer microfluidic devices.

### How It Works
When a focused CO2 laser spot with appropriate power moves across the acrylic surface, it heats and vaporizes a small volume of material. The resulting cavities serve as microfluidic channels. Two writing modes exist:
- **Raster mode**: The laser scans line-by-line across the surface, producing U-shaped channels with flatter bottoms. Better for wide, shallow channels.
- **Vector mode**: The laser traces a path along channel centerlines, producing V-shaped channels. Better for narrow, deep channels.

### Equipment

| System | Laser Power | Work Area | Resolution | Price (approx.) |
|---|---|---|---|---|
| **Epilog Maker 12** | 30 W CO2 | 12" x 12" | 1000 DPI (25 um spot) | ~$10,000 |
| **Epilog Fusion Pro 32** | 60-120 W CO2 | 32" x 20" | 1000 DPI | ~$25,000-50,000 |
| **Epilog Fusion Pro 48** | 60-200 W CO2 | 48" x 36" | 1000 DPI | ~$35,000-70,000 |
| **Trotec Speedy 100** | 30-80 W CO2 | 24" x 12" | Up to 1000 DPI | ~$10,000-25,000 |
| **Trotec Speedy 300** | 30-120 W CO2 | 29" x 17" | Up to 1000 DPI | ~$20,000-40,000 |
| **Trotec SP 2000** | 100-400 W CO2 | 49" x 28" | Up to 1000 DPI | ~$40,000-80,000 |
| **Universal Laser VLS 3.60** | 30-60 W CO2 | 24" x 12" | 1000 DPI | ~$15,000-30,000 |
| **Universal Laser PLS 4.75** | 30-75 W CO2 | 24" x 18" | 1000 DPI | ~$20,000-35,000 |
| **Budget (e.g., Epilog Zing)** | 30-40 W CO2 | 16" x 12" | 1000 DPI | ~$8,000-12,000 |
| **Chinese imports (K40, OMTech)** | 40-80 W CO2 | varies | Lower precision | ~$400-3,000 |

### Achievable Feature Sizes

| Parameter | Typical Range | Best Demonstrated |
|---|---|---|
| Channel width (raster) | 100-500 um | ~60 um (at 1000 DPI) |
| Channel width (vector) | 100-300 um | ~100 um |
| Channel depth | 30-300 um | Controllable via power/speed |
| Cut-through (PMMA) | Up to 25 mm thick | Depends on laser power |
| Surface roughness (Ra) | 1-10 um | Improved with chemical post-processing |
| Positional accuracy | ~25-50 um | System-dependent |

### Channel Profile Control
- **Power**: Higher power = deeper channels; too much power causes excessive melting and recast
- **Speed**: Slower speed = deeper, wider channels; faster = shallower, narrower
- **Focus**: Defocusing the beam increases spot size and changes channel profile
- **Number of passes**: Multiple passes deepen channels without excessive heat buildup
- **Pulse frequency**: Higher frequency = smoother surface but slower effective speed

### Post-Processing for CO2 Laser-Cut PMMA
- **Solvent vapor polishing**: Brief exposure to chloroform or dichloromethane vapor smooths rough laser-cut surfaces, reducing Ra from ~5-10 um to <1 um
- **Thermal annealing**: Heating to 80-90C (below PMMA Tg of ~105C) relieves thermal stresses
- **Chemical post-processing**: Dipping in chloroform solution improves surface quality and optical clarity of laser-ablated channels

### Bonding Laser-Cut PMMA
- **Thermal bonding**: Heat PMMA layers to near Tg (~105C) under pressure; risk of channel deformation
- **Solvent bonding**: Apply thin layer of chloroform, acetone, or ethanol between layers; press together. Fast but requires skill to avoid channel flooding
- **Adhesive bonding**: Double-sided tape (e.g., 3M 468MP), UV-curable adhesive, or PMMA cement
- **Solvent-assisted thermal bonding**: Combination approach; brief solvent exposure + moderate heat gives strongest bonds with least deformation

### Pros
- Very fast prototyping: design to device in < 1 hour
- Low cost: budget systems from ~$400, professional from ~$10,000
- No cleanroom required
- Cuts through full PMMA thickness for layer-based assembly
- Widely available in makerspaces, fab labs, and university shops
- Large work area (up to 48" x 36")

### Cons
- Resolution limited to ~100-200 um for reliable microfluidic channels
- Rough, tapered channel walls (heat-affected zone)
- V-shaped or U-shaped channel profiles (not rectangular)
- Thermal damage zone creates recast/burr at channel edges
- Not suitable for sub-100 um features
- Inconsistent depth control at small feature sizes
- Only works with thermoplastics that absorb at 10.6 um (PMMA, PS, PC, COC)

### When to Use
- Rapid prototyping with channels > 200 um
- Layer-based microfluidic devices (cut-and-stack assembly)
- Educational settings and teaching labs
- When same-day turnaround is essential
- Budget-constrained projects
- Droplet generators and simple mixing geometries

---

## 2. Femtosecond Laser Machining for Glass (SLE Technology)

### What It Is
Selective Laser-induced Etching (SLE) is a two-step process for fabricating true 3D microstructures inside transparent glass substrates (primarily fused silica/quartz). A femtosecond laser modifies the glass structure internally without surface damage, then chemical etching selectively removes the modified regions. This creates monolithic, fully enclosed 3D channel networks with no bonding required.

### How the SLE Process Works

**Step 1 -- Laser Modification:**
A femtosecond laser (typically ~300-800 fs pulse duration, 515 nm or 1030 nm wavelength) is tightly focused inside the glass substrate. The ultrashort pulses create nonlinear absorption at the focal point, locally modifying the glass structure (creating nanogratings, densification, or other structural changes) without melting or cracking. The laser scans a 3D pattern corresponding to the desired channel/cavity geometry.

**Step 2 -- Chemical Etching:**
The laser-modified glass is immersed in an etchant:
- **KOH** (potassium hydroxide, typically 8-10 M at 80-90C): Slower but safer; selectivity ratio ~1000:1 (modified:unmodified glass). Preferred for high-precision work.
- **HF** (hydrofluoric acid, typically 2-5%): Faster etching but lower selectivity (~100:1). More hazardous.
- **HF/HNO3 mixtures**: Higher etch rates for bulk removal.

The etchant preferentially attacks the laser-modified zones, creating channels and cavities while leaving the surrounding glass intact.

### Key Equipment

| System | Manufacturer | Laser | Working Volume | Key Features | Price (approx.) |
|---|---|---|---|---|---|
| **LightFab 3D Printer** | LightFab GmbH (Aachen, DE) | fs laser, <2 um focus | Scientific: 120x80x20 mm; Manufacturing: 200x200x150 mm | 3D micro scanner + 3-axis stage; SLE + 2PP + waveguide writing | ~$300,000-600,000 (est.) |
| **Femtoprint** | FEMTOprint SA (Muzzano, CH) | fs laser | Various configs | SLE specialist; contract manufacturing available | ~$200,000-500,000 (est.) |
| **Femtika Laser Nanofactory** | Femtika (Vilnius, LT) | fs laser (various wavelengths) | 160x160 mm working area | Multi-process: 2PP + SLE + ablation in one tool | $415,000+ |
| **Custom SLE setups** | University labs | Commercial fs lasers + stages | Varies | Often built from components; lower cost but less integrated | ~$100,000-300,000 |

### Achievable Features

| Parameter | Typical | Best Demonstrated |
|---|---|---|
| Minimum channel width | 5-20 um | ~1 um |
| Minimum channel height | 5-20 um | ~1 um |
| Aspect ratio (depth:width) | 10:1 typical | >100:1 demonstrated |
| Surface roughness (Ra) | 50-200 nm (KOH) | <50 nm with optimized parameters |
| Positional accuracy | ~1-2 um | Sub-micron with interferometric stages |
| Maximum channel length | Limited by etchant diffusion | Several cm (with etch access ports) |
| Substrate thickness | Up to 10+ mm | Standard: 0.5-2 mm fused silica wafers |

### Materials
- **Fused silica** (Corning 7980, Heraeus Suprasil): Primary material; excellent optical, chemical, and thermal properties
- **Borosilicate glass** (Borofloat 33, Schott D263): Lower cost; good for many applications but lower selectivity
- **Sapphire**: Possible but more challenging; higher hardness
- **Crystalline quartz**: Possible with adapted parameters

### Advantages of SLE Glass Microfluidics
- **Monolithic construction**: No bonding required; channels are buried inside a single piece of glass
- **True 3D channels**: Channels can cross over/under each other, spiral, branch in 3D
- **Excellent optical properties**: Fused silica is transparent from deep UV (180 nm) to near-IR (2.5 um)
- **Chemical inertness**: Fused silica resists virtually all solvents, acids (except HF), and bases
- **Thermal stability**: Operating temperature up to 1000C+
- **No delamination**: Monolithic structure eliminates bonding failures
- **Biocompatibility**: Glass is inherently biocompatible
- **Pressure resistance**: Can withstand very high pressures (hundreds of bar)

### Limitations
- **Slow process**: Laser writing + etching can take hours to days for complex designs
- **Expensive equipment**: $200,000-600,000+ for commercial SLE systems
- **Etch access required**: Long channels need intermediate access ports for etchant diffusion
- **Channel length limited**: Etchant must diffuse in from access points; practical limit ~5-10 mm per access port
- **Surface roughness**: KOH etching leaves ~100-200 nm roughness; additional smoothing may be needed
- **Substrate cost**: High-quality fused silica wafers are expensive ($50-200+ per wafer)

### Contract Manufacturing
Both LightFab and FEMTOprint offer contract manufacturing services for SLE glass microfluidics, providing access to the technology without capital equipment purchase. Typical lead times: 2-6 weeks.

---

## 3. Excimer Laser Ablation

### What It Is
Excimer lasers produce high-energy UV pulses that directly break molecular bonds in polymers (photochemical ablation) rather than heating/melting. This "cold ablation" creates cleaner, sharper features than CO2 laser processing, with minimal heat-affected zone.

### Laser Types and Wavelengths

| Excimer Gas | Wavelength | Photon Energy | Best For |
|---|---|---|---|
| **ArF** | 193 nm | 6.4 eV | Highest precision; PMMA, PTFE, most polymers |
| **KrF** | 248 nm | 5.0 eV | General polymer ablation; most common for microfluidics |
| **XeCl** | 308 nm | 4.0 eV | Larger features; lower cost per pulse |
| **XeF** | 351 nm | 3.5 eV | Limited polymer absorption; less common |

Additionally, frequency-tripled (355 nm) and frequency-quadrupled (266 nm) Nd:YAG lasers can serve as alternatives to excimer lasers, with the advantage of solid-state reliability.

### Achievable Features

| Parameter | Typical Range | Notes |
|---|---|---|
| Channel width | 10-500 um | Mask-defined; 10 um achievable with projection optics |
| Channel depth per pulse | 0.1-1 um | Material and fluence dependent |
| Total depth | 1-500 um | Multiple pulses; controlled by pulse count |
| Wall roughness (Ra) | 50-500 nm | Better than CO2; worse than lithography |
| Aspect ratio | Up to ~10:1 | Limited by beam divergence into channel |
| Taper angle | 1-5 degrees | Slight taper is inherent |

### Process Modes
- **Direct write**: Focused beam scans across substrate; flexible but slower
- **Mask projection**: Excimer beam illuminates a chrome-on-quartz mask; demagnified image projected onto substrate. Higher throughput, better feature definition.
- **Step-and-repeat**: Mask projection with substrate stepping for large-area patterning

### Materials Suitable for Excimer Ablation

| Material | 248 nm Ablation Threshold (mJ/cm2) | Etch Rate (um/pulse) | Quality |
|---|---|---|---|
| **PMMA** | ~100-200 | 0.1-0.5 | Excellent; clean cuts |
| **Polycarbonate (PC)** | ~150-250 | 0.1-0.3 | Good |
| **Polyimide (Kapton)** | ~50-100 | 0.05-0.3 | Excellent; gold standard |
| **PET** | ~100-200 | 0.1-0.3 | Good |
| **COC/COP** | ~150-300 | 0.05-0.2 | Good |
| **PDMS** | >500 | Poor | Nano/micro cracks observed |
| **PGS, APS** | Varies | Varies | Good; no micro-cracks |

### Equipment
Excimer laser micromachining systems are specialized industrial/research tools:
- **Optec (Belgium)**: WS-Flex series -- dedicated microfluidic ablation workstations
- **Coherent (formerly LPKF/Resonetics)**: Excimer micromachining systems
- **IPG Photonics / Oxford Lasers**: UV laser micromachining platforms
- **Cost**: $100,000-500,000+ for a complete system with mask projection optics

### Pros
- Cleaner ablation than CO2 laser (photochemical vs. thermal)
- Minimal heat-affected zone
- Good wall quality with controlled roughness
- Mask projection enables parallel processing of complex patterns
- Works with a wide range of polymers
- Can simultaneously modify surface chemistry (hydrophilicity change)

### Cons
- Expensive equipment ($100,000-500,000+)
- Excimer lasers require toxic/corrosive gas handling (fluorine, chlorine)
- Limited to surface ablation (not buried channels)
- Slower than CO2 for simple cuts
- Mask fabrication adds cost and lead time
- Feature depth controlled by pulse count (slower for deep features)
- Not widely available outside specialized facilities

### When to Use
- Polymer microfluidics requiring 10-100 um features with clean walls
- When CO2 laser resolution (~100+ um) is insufficient
- Mass production of polymer microfluidic patterns (mask projection)
- When surface chemistry modification is desired simultaneously
- Polyimide-based flexible microfluidics

---

## 4. Glass Wet Etching (HF)

### What It Is
Wet chemical etching of glass substrates using hydrofluoric acid (HF) or buffered oxide etch (BOE) is one of the oldest and most established methods for fabricating glass microfluidic channels. The process is isotropic (etches equally in all directions), producing rounded channel profiles.

### Process Steps

1. **Substrate preparation**: Clean glass wafer (fused silica, borosilicate, soda-lime) with piranha or RCA clean
2. **Mask deposition**: Deposit etch-resistant masking layer:
   - **Cr/Au** (20 nm Cr + 200 nm Au): Most common; good HF resistance for depths up to ~100 um
   - **Cr/Au/Cr** trilayer: For deeper etches
   - **Amorphous silicon (a-Si)**: For deep etches in concentrated HF
   - **Polysilicon**: Alternative for deep etches
   - **Photoresist alone**: Only for very shallow etches (<5 um) in dilute HF/BOE
3. **Photolithography**: Spin-coat photoresist, expose, develop to define channel pattern
4. **Mask patterning**: Wet-etch the metal mask through the photoresist pattern
5. **Glass etching**: Immerse in HF solution; etch rate depends on glass type and HF concentration
6. **Strip mask**: Remove remaining metal mask layers
7. **Clean and bond**: Prepare surface for bonding to cover plate

### Etch Rates

| Glass Type | Etchant | Etch Rate | Notes |
|---|---|---|---|
| **Fused silica (SiO2)** | 49% HF | ~1.3 um/min | Slowest; most uniform |
| **Fused silica** | BOE (6:1) | ~0.1 um/min | Very controlled; for shallow features |
| **Borosilicate (Pyrex 7740)** | 49% HF | ~8 um/min | Fast but less uniform |
| **Borosilicate** | 10% HF | ~1-2 um/min | More controllable |
| **Soda-lime glass** | 49% HF | ~5-10 um/min | Cheapest glass; less uniform |
| **Borofloat 33** | 49% HF | ~7-8 um/min | Common for microfluidics |

### Feature Characteristics

| Parameter | Value | Notes |
|---|---|---|
| Minimum channel width | ~5-10 um (defined by lithography) | Actual etched width = mask width + 2x etch depth (isotropic undercutting) |
| Typical channel depth | 10-200 um | Deeper requires more robust masks |
| Maximum practical depth | ~500 um | Limited by mask durability and uniformity |
| Channel profile | Hemispherical/rounded | Due to isotropic etching |
| Surface roughness (Ra) | ~1-10 nm | Extremely smooth; best of all microfabrication methods |
| Aspect ratio | ~0.5:1 maximum | Fundamental limit of isotropic etching |

### Multilevel Etching
Deep multilevel wet etching of fused silica has been demonstrated using BOE solution with multiple lithography-etch cycles. This enables channels at different depths within the same substrate, useful for complex microfluidic networks with 3D crossing channels.

### Safety -- CRITICAL

**HF is one of the most dangerous chemicals in the laboratory.** It can cause severe, potentially fatal burns, and can be absorbed through the skin causing systemic fluoride poisoning (hypocalcemia, cardiac arrest).

**Mandatory Safety Requirements:**
- **Buddy system**: Never work with HF alone; at least one other trained person must be in the lab
- **PPE**: Double nitrile gloves (or neoprene gloves), face shield, chemical splash goggles, acid-resistant apron, closed-toe shoes
- **Fume hood**: All HF work must be performed in a properly functioning chemical fume hood or laminar flow bench
- **Calcium gluconate gel**: Must be immediately available at the workstation; apply to any skin exposure immediately
- **Training**: Institutional HF safety training is mandatory before handling
- **Spill kit**: HF-specific spill kit with calcium carbonate neutralizer
- **PTFE/HDPE containers**: HF etches glass; use only compatible plastic containers
- **Emergency procedures**: Know the location of safety shower, eyewash, and emergency contacts
- **Medical monitoring**: Anyone with skin exposure (even if asymptomatic) must seek immediate medical evaluation

### Equipment
- **Wet bench with HF-rated fume hood**: $20,000-100,000
- **PTFE or polypropylene etch tanks**: $500-5,000
- **Temperature-controlled bath** (for heated etch solutions): $2,000-10,000
- **Cleanroom with HF-rated exhaust**: Required for consistent results
- **Profilometer/microscope**: For etch depth measurement
- **Spin coater, mask aligner**: Standard lithography equipment for mask patterning

### Pros
- Extremely smooth channel surfaces (Ra ~1-10 nm) -- best optical quality
- Well-established, mature process
- Excellent repeatability and uniformity
- Low cost per wafer once setup is complete
- Compatible with standard cleanroom photolithography
- Glass substrate advantages (chemical resistance, optical transparency, biocompatibility)

### Cons
- **Isotropic**: Cannot produce vertical sidewalls or high aspect ratio channels
- **HF hazard**: Extremely dangerous chemical requiring rigorous safety protocols
- **Undercutting**: Channel width = mask opening + 2x etch depth; limits minimum feature density
- **Mask erosion**: Metal masks degrade during long etches; limits maximum depth
- **Cleanroom required**: Full photolithography process needed
- **Slow for deep features**: Hours for channels > 100 um deep
- **Environmental concerns**: HF waste disposal is regulated and expensive

### When to Use
- When optically smooth channels are critical (fluorescence microscopy, optical detection)
- Established, validated microfluidic designs for production
- When channels > 10 um wide with rounded profiles are acceptable
- Chemical analysis applications requiring glass inertness
- When bonded to silicon (anodic bonding) or glass (thermal/fusion bonding)

---

## 5. Silicon Dry Etching (DRIE / Bosch Process)

### What It Is
Deep Reactive Ion Etching (DRIE) is a plasma-based dry etching technique that produces deep, high-aspect-ratio trenches and channels in silicon with nearly vertical sidewalls. The Bosch process (patented by Robert Bosch GmbH) is the most widely used DRIE method, alternating between isotropic silicon etching and sidewall passivation.

### How the Bosch Process Works
The Bosch process repeats two alternating plasma cycles:

1. **Etch cycle** (SF6 plasma, 5-15 seconds): Isotropic etching of exposed silicon by fluorine radicals. Etches ~0.5-2 um per cycle.
2. **Passivation cycle** (C4F8 plasma, 3-10 seconds): Deposits a thin fluorocarbon polymer (Teflon-like) film on all surfaces, including sidewalls.

In the next etch cycle, the passivation is removed from horizontal surfaces by ion bombardment but remains on the vertical sidewalls, protecting them from lateral etching. This creates the characteristic scalloped sidewalls (typically 50-200 nm scallop depth) with overall near-vertical profiles.

### Key Process Parameters

| Parameter | Typical Range | Effect |
|---|---|---|
| Etch rate | 1-20 um/min | Depends on feature size, aspect ratio, loading |
| Selectivity (Si:photoresist) | 50:1 to 200:1 | Higher with hard masks (SiO2, metal) |
| Selectivity (Si:SiO2) | 100:1 to 300:1 | Excellent; SiO2 as etch stop |
| Sidewall angle | 88-90 degrees | Near vertical; tunable |
| Scallop depth | 50-200 nm | Reduced with shorter cycle times |
| Aspect ratio | Up to 50:1 | Higher with optimized recipes |
| Etch uniformity | 2-10% across wafer | Load-dependent; better in modern tools |
| Minimum feature | ~1-2 um | Lithography-limited |

### Equipment

| System | Manufacturer | Key Features | Wafer Size | Price (approx.) |
|---|---|---|---|---|
| **PlasmaPro 100 Estrelas** | Oxford Instruments | Total flexibility for DSiE; ICP source; excellent uniformity | Up to 200 mm | ~$500,000-800,000 |
| **PlasmaPro DSiE** | Oxford Instruments | Dedicated DRIE tool; Bosch and cryo processes | Up to 200 mm | ~$400,000-700,000 |
| **Rapier DRIE** | SPTS Technologies (Orbotech) | High-throughput production tool; Bosch + non-switched etching | Up to 200 mm | ~$500,000-1,000,000 |
| **Versaline DSE** | Plasma-Therm | Dual ICP chambers; Bosch process; flexible configurations | Up to 200 mm | ~$400,000-800,000 |
| **RIE-800iPB** | Samco Inc. | ICP-RIE for Si DRIE; compact footprint | Up to 200 mm | ~$300,000-600,000 |
| **ULVAC NLD** | ULVAC | Neutral loop discharge; high-rate DRIE | Up to 300 mm | ~$500,000-1,000,000 |

### Achievable Features for Microfluidics

| Feature | Typical | Best Demonstrated |
|---|---|---|
| Channel width | 2-500 um | Down to ~1 um with e-beam lithography |
| Channel depth | 10-500 um | Through-wafer (525 um) common |
| Aspect ratio | 10:1 to 30:1 routine | >50:1 demonstrated |
| Sidewall roughness (scallops) | 50-200 nm | <20 nm with optimized short-cycle Bosch |
| Through-silicon vias (TSV) | 5-100 um diameter | Standard for 3D microfluidics |
| Etch rate | 3-15 um/min typical | >20 um/min in high-rate modes |

### Masking for DRIE

| Mask Material | Selectivity vs. Si | Max Etch Depth | Notes |
|---|---|---|---|
| **Photoresist (thick, AZ4620)** | ~50-100:1 | ~200-300 um | Easiest; limited depth |
| **SiO2 (thermal or PECVD)** | ~100-300:1 | 500+ um | Standard for deep etches |
| **Al** | ~100:1 | ~200-500 um | Good; easy to deposit |
| **Cr** | ~50:1 | ~100-200 um | Common |
| **Ni (electroplated)** | ~200:1+ | 500+ um | For very deep etches |
| **SiN** | ~100-200:1 | 300+ um | Standard MEMS mask |

### Alternative DRIE Methods
- **Cryogenic DRIE**: Substrate cooled to -100 to -120C; SF6/O2 chemistry provides sidewall passivation through SiOxFy formation. No scalloping -- smooth sidewalls. Available on Oxford PlasmaPro systems.
- **STiGer process**: Continuous etch with simultaneous deposition; smoother sidewalls than Bosch with comparable etch rates. Emerging alternative.
- **Non-switched / tapered etching**: Continuous process for tapered profiles; useful for fluidic interfaces and nozzles.

### Pros
- **Near-vertical sidewalls**: Rectangular channel cross-sections (unlike isotropic wet etching)
- **High aspect ratios**: Up to 50:1, enabling deep narrow channels
- **Precise depth control**: Etch rate well-characterized; endpoint detection available
- **Through-wafer etching**: 525 um standard wafer thickness routinely etched through
- **Excellent repeatability**: Automated plasma process with recipe control
- **Fine features**: Down to ~1 um with appropriate lithography
- **Clean process**: No wet chemistry during etching itself

### Cons
- **Expensive equipment**: $300,000-1,000,000 per DRIE tool
- **Cleanroom required**: Full semiconductor fabrication environment
- **Sidewall scalloping**: Bosch process leaves periodic roughness (can be smoothed)
- **Silicon is opaque**: Cannot visualize flow through silicon; requires glass capping
- **Loading effects**: Etch rate varies with feature density and size (ARDE -- Aspect Ratio Dependent Etching)
- **Etch lag**: Smaller features etch slower than larger features
- **Process expertise required**: Recipe optimization for specific geometries

### When to Use
- High-aspect-ratio channels with vertical sidewalls required
- Integration with silicon-based sensors (piezoresistive, capacitive)
- Through-wafer fluidic vias and interconnects
- MEMS-integrated microfluidics (valves, pumps, actuators)
- Mass production of silicon microfluidic devices
- When thermal conductivity of silicon is advantageous (PCR, thermal management)
- When electrical functionality is integrated (electrodes, heaters)

---

## 6. Glass-Glass Thermal Bonding and Anodic Bonding

### Glass-Glass Thermal (Fusion) Bonding

#### Process
1. **Surface preparation**: Both glass surfaces must be extremely clean and flat (roughness <1 nm RMS). Clean with piranha (H2SO4:H2O2) or RCA process.
2. **Surface activation** (optional but recommended): O2 plasma treatment or UV/ozone exposure makes surfaces hydrophilic, enabling bonding at lower temperatures.
3. **Pre-bonding**: Bring surfaces into contact at room temperature. Van der Waals forces create initial bond (visible as bonding front propagation).
4. **Thermal annealing**: Heat in furnace to high temperature to convert weak pre-bond to strong covalent bond.

#### Temperature Requirements

| Glass Type | Bonding Temperature | Hold Time | Notes |
|---|---|---|---|
| **Fused silica** | 1000-1100C | 2-8 hours | Highest quality; channels must withstand temperature |
| **Borosilicate (Pyrex)** | 550-650C | 2-6 hours | Below softening point to minimize channel deformation |
| **Soda-lime** | 500-580C | 2-4 hours | Cheapest glass; lower temperature |

#### Low-Temperature Glass Bonding Alternatives

| Method | Temperature | Bond Strength | Notes |
|---|---|---|---|
| **Plasma-activated bonding** | Room temp to 200C | Moderate-high | O2 plasma surface activation; 5-15 MPa bond strength |
| **UV adhesive bonding** | Room temperature | Moderate | Thin UV-curable adhesive layer; fast but adds interface |
| **Intermediate layer (SOG)** | 200-400C | Moderate | Spin-on-glass as bonding layer |
| **HF-assisted bonding** | Room temp to 100C | Moderate | Brief HF dip activates surface; fast bonding |

#### Key Requirements
- Surface roughness: <1 nm RMS (ideally <0.5 nm)
- Flatness: <1 um total thickness variation (TTV) across bonding area
- Particle-free: A single particle >1 um can create unbonded area >1 cm in diameter
- Cleanroom environment: Essential for reliable bonding

### Glass-Glass Anodic Bonding (with Intermediate Layer)

Standard anodic bonding requires mobile alkali ions, which are absent in pure fused silica. Glass-glass anodic bonding requires an intermediate conductive layer:

- **Thin-film Ti layer** (~80 nm): Deposited on one glass surface by sputtering; bonding at 530C with 100V applied
- **Thin-film Si layer** (100-500 nm): Sputtered amorphous silicon between glass surfaces; bond at 350-450C with 500-1000V
- **Thin-film Al layer**: Alternative metallic interlayer

Bond quality: Bubble-free interface achievable when bonding temperature exceeds 275C.

### Pros (Glass-Glass Bonding)
- All-glass device: best optical properties for imaging through both top and bottom
- Excellent chemical resistance on all surfaces
- No material mismatch at bond interface (thermal bonding)
- Suitable for high-pressure applications
- Biocompatible

### Cons (Glass-Glass Bonding)
- Requires extremely clean, flat surfaces
- High temperatures risk channel deformation (thermal bonding)
- Slow process (hours in furnace for thermal bonding)
- Requires cleanroom for reliable results
- Anodic bonding of glass-glass needs intermediate layer
- Expensive substrates and processing

---

## 7. Silicon-Glass Anodic Bonding

### What It Is
Anodic bonding (also called field-assisted bonding or electrostatic bonding) creates an irreversible hermetic seal between a silicon wafer and a sodium-containing glass wafer by applying heat and a high DC voltage. It is the most common method for capping silicon microfluidic channels with a transparent glass lid.

### Process Parameters

| Parameter | Typical Range | Optimized |
|---|---|---|
| Temperature | 300-450C | 350-400C most common |
| Voltage | 200-1200 V DC | 500-1000V typical |
| Time | 5-30 minutes | Until current drops to baseline |
| Atmosphere | Vacuum or N2 | Vacuum preferred for bubble-free bonds |
| Applied pressure | 0-500 kPa | Moderate contact pressure helps initiate bonding |

### Low-Temperature Anodic Bonding
Satisfactory bond quality has been demonstrated at temperatures as low as 200C with higher voltages (2500V) and process times under 1.5 minutes. This is important for preserving temperature-sensitive structures or pre-deposited materials.

### Mechanism
1. Silicon wafer placed on hot plate (anode, grounded)
2. Glass wafer placed on top of silicon
3. Cathode (point probe or plate) contacts the glass surface
4. High negative voltage applied to the glass surface
5. Na+ ions in the glass migrate toward the cathode (away from the Si-glass interface)
6. Depletion layer forms at the interface, creating a strong electrostatic field
7. Electrostatic force pulls the glass into intimate contact with silicon
8. At elevated temperature, oxygen ions diffuse to the interface and form Si-O bonds
9. Result: permanent, hermetic, covalent bond

### Compatible Glass Types

| Glass | CTE (x10^-6/K) | Na2O Content | Compatibility | Notes |
|---|---|---|---|---|
| **Corning Pyrex 7740** | 3.25 | Contains Na2O | Excellent | Gold standard for Si anodic bonding |
| **Schott Borofloat 33** | 3.25 | Contains Na2O | Excellent | CTE matched to Si (2.6); widely used |
| **Schott Tempax** | 3.25 | Contains Na2O | Excellent | Similar to Borofloat |
| **Hoya SD-2** | ~3.2 | Contains Na2O | Good | Alternative supplier |
| **Fused silica** | 0.55 | **No Na2O** | **Not directly compatible** | Requires intermediate layer or modified process |
| **Soda-lime glass** | ~8.5 | High Na2O | Poor (CTE mismatch) | Cracks on cooling due to thermal expansion mismatch |

**Critical requirement**: The glass must contain mobile alkali ions (Na+) and have a CTE close to silicon (2.6 x 10^-6/K at room temperature). Pyrex 7740 / Borofloat 33 (CTE = 3.25) are the standard choices.

### Surface Preparation Requirements
- **Roughness**: <10 nm RMS on both surfaces; <1 nm RMS preferred
- **Cleanliness**: Piranha clean (H2SO4:H2O2) or RCA clean; particle-free surfaces essential
- **Flatness**: <2 um TTV across bonding area
- **Oxide on silicon**: Native oxide (~2 nm) is sufficient; thick thermal oxide reduces bond quality

### Equipment
- **Commercial bonders**: EVG (EVG520), SUSS MicroTec (SB6/8), AML (AML-AWB): $100,000-500,000
- **Simple lab setup**: Hot plate + DC power supply (0-1200V) + point probe electrode: $5,000-20,000
- **Vacuum bonding chamber**: Recommended for bubble-free bonds: $50,000-200,000

### Bond Quality Characterization
- **Visual inspection**: Bonded areas appear dark (no interference fringes); unbonded areas show Newton's rings
- **Infrared imaging**: IR camera reveals voids and particles at the interface
- **Razor blade test**: Wedge inserted at edge; crack should propagate along interface, not into substrates
- **Leak testing**: Pressurize microfluidic channels to verify hermetic seal
- **Bond strength**: Typically 10-30 MPa; limited by glass fracture strength

### Pros
- **Hermetic seal**: Vacuum-tight, leak-free bond
- **Strong**: Bond strength approaches glass fracture toughness (~20-30 MPa)
- **Transparent window**: Glass cap enables optical access to silicon channels
- **No adhesive**: Clean interface with no outgassing or contamination
- **Well-characterized**: Decades of MEMS manufacturing experience
- **Compatible with thin films**: Metal electrodes, oxide layers can be patterned on Si before bonding
- **Moderate temperature**: 350-400C is compatible with many pre-deposited materials

### Cons
- **Requires sodium-containing glass**: Limits glass choice; fused silica not directly compatible
- **Temperature**: 300-450C may damage temperature-sensitive materials
- **Requires clean, flat surfaces**: Particles cause unbonded regions
- **Equipment cost**: Commercial bonders are expensive
- **Wafer-level process**: Not practical for individual chip bonding (though possible)
- **Non-reversible**: Once bonded, cannot be separated without destroying device

### When to Use
- Sealing DRIE-etched silicon channels with a transparent glass cap
- MEMS-integrated microfluidics requiring hermetic encapsulation
- High-pressure microfluidic devices (bond withstands >10 bar easily)
- When optical access to silicon channels is needed
- Production-scale silicon microfluidic devices
- When long-term reliability and hermeticity are critical

---

## 8. When to Choose Glass/Silicon Over Polymers -- Decision Criteria

### Quick Decision Matrix

| Criterion | Polymer (PDMS, PMMA, COC) | Glass (Wet Etch / SLE) | Silicon (DRIE) |
|---|---|---|---|
| **Cost per device** | $1-50 | $50-500 | $50-500 |
| **Setup cost** | $1,000-50,000 | $50,000-500,000 | $200,000-1,000,000 |
| **Prototyping speed** | Hours | Days-weeks | Days-weeks |
| **Min. channel size** | 1-10 um (soft litho); 100+ um (laser/3D print) | 5-10 um (wet etch); 1 um (SLE) | 1-2 um (DRIE) |
| **Channel profile** | Rectangular (soft litho); rounded (laser) | Rounded (wet etch); arbitrary (SLE) | Rectangular (DRIE) |
| **Aspect ratio** | Low-moderate | Low (wet etch: 0.5:1); high (SLE: >100:1) | High (DRIE: up to 50:1) |
| **Optical transparency** | Good (PDMS, COC); moderate (PMMA) | Excellent (UV to IR) | Opaque (need glass cap) |
| **Chemical resistance** | Poor (PDMS swells in organics); moderate (PMMA, COC) | Excellent (resists all except HF) | Excellent (resists most chemicals) |
| **Thermal stability** | <200C (most polymers) | >1000C (fused silica) | >500C (limited by dopant diffusion) |
| **Pressure tolerance** | Low-moderate (<5 bar PDMS; higher for thermoplastics) | High (>100 bar fused silica) | High (>100 bar) |
| **Biocompatibility** | Good (PDMS, COC) | Excellent | Good (with oxide coating) |
| **Gas permeability** | High (PDMS) -- advantage for cell culture | Very low | Very low |
| **Surface stability** | Hydrophobic recovery (PDMS) | Stable, well-defined surface chemistry | Stable (with oxide) |
| **Electrical integration** | Difficult | Possible (ITO, metal deposition) | Excellent (integrated circuits, heaters, sensors) |
| **Scalability to production** | Injection molding (COC, PMMA) | Glass etching is scalable | Semiconductor-standard; highly scalable |

### Choose Glass When...

1. **Organic solvents are used**: Glass resists virtually all organic solvents (toluene, hexane, DCM, THF, acetone, etc.) that would swell or dissolve PDMS and many thermoplastics.
2. **High-temperature operation**: Reactions above 200C (e.g., high-temperature synthesis, supercritical fluid applications).
3. **Optical detection is critical**: Fused silica offers the widest spectral transparency (180 nm - 2.5 um), lowest autofluorescence, and smoothest surfaces for optical detection. UV-transparent unlike most polymers.
4. **Long-term surface stability**: Glass surface chemistry does not change over time (unlike PDMS hydrophobic recovery after plasma treatment).
5. **High pressure**: Fused silica devices withstand >100 bar; PDMS typically fails above 2-5 bar.
6. **Regulatory/validation**: Glass is well-characterized for medical and diagnostic applications; easier regulatory pathway for IVD devices.
7. **No molecular absorption**: PDMS absorbs small hydrophobic molecules (drugs, lipids); glass does not.
8. **Reusability**: Glass devices can be cleaned with strong acids/bases/solvents and reused indefinitely.

### Choose Silicon When...

1. **Integrated electronics**: Heaters, temperature sensors, electrochemical electrodes, piezoresistive pressure sensors -- all can be fabricated on the same silicon substrate.
2. **High-aspect-ratio channels**: DRIE produces vertical sidewalls with aspect ratios up to 50:1, impossible with isotropic glass etching.
3. **Thermal management**: Silicon's high thermal conductivity (150 W/mK vs. 1.4 W/mK for glass) is critical for PCR thermal cycling, exothermic reactions, and heat dissipation.
4. **MEMS integration**: Valves, pumps, actuators, and resonant sensors integrated monolithically.
5. **Very fine features**: DRIE can produce 1-2 um features with vertical sidewalls.
6. **Mass production**: Silicon processing is the most mature microfabrication technology; wafer-level manufacturing scales to millions of devices.
7. **Through-wafer interconnects**: TSVs enable 3D stacking of microfluidic layers.

### Choose Polymers When...

1. **Rapid prototyping**: PDMS soft lithography or 3D printing produces devices in hours, not days/weeks.
2. **Low cost**: Per-device cost of PDMS is negligible after master fabrication.
3. **Gas permeability needed**: Cell culture requires O2/CO2 exchange; PDMS is gas-permeable while glass and silicon are not.
4. **Flexibility**: Deformable channels for pneumatic valves (Quake valves), peristaltic pumps.
5. **Biocompatibility without coating**: PDMS is inherently biocompatible and optically transparent.
6. **No cleanroom access**: PDMS casting and laser cutting can be done outside cleanrooms.
7. **Disposable devices**: Low per-unit cost enables single-use devices.
8. **Teaching and training**: Fastest, cheapest path to functional microfluidics.

### Hybrid Approaches

| Combination | How | Why |
|---|---|---|
| **PDMS on glass** | PDMS channels bonded to glass slide (O2 plasma) | Easy fabrication + good optics + solvent-compatible bottom surface |
| **Silicon + glass** | DRIE channels in Si, anodic-bonded glass cap | Precise channels + optical access + integrated electronics |
| **Glass + polymer gaskets** | Glass channels with PDMS or elastomer interconnects | Chemical resistance + easy world-to-chip connections |
| **SLE glass + PDMS interface** | Monolithic glass channels with PDMS tubing adapters | Best of both: buried glass channels + compliant connections |
| **3D printed + glass slide** | 3D printed PMMA or resin channels bonded to glass | Rapid prototyping of complex 3D geometries + glass imaging surface |

---

## 9. Comparison Table: All Fabrication Approaches

| Method | Min. Feature | Aspect Ratio | Surface Roughness | Throughput | Equipment Cost | Per-Device Cost | Cleanroom? |
|---|---|---|---|---|---|---|---|
| **CO2 laser (PMMA)** | ~100 um | Low | 1-10 um Ra | Very high | $400-70,000 | $1-10 | No |
| **Excimer laser (polymer)** | ~10 um | Moderate | 50-500 nm Ra | Moderate | $100,000-500,000 | $10-50 | Preferred |
| **Femtosecond SLE (glass)** | ~1 um | Very high (>100:1) | 50-200 nm Ra | Low | $200,000-600,000 | $50-500 | Preferred |
| **Glass wet etch (HF)** | ~5 um | Low (0.5:1) | 1-10 nm Ra | High (batch) | $50,000-200,000 | $20-100 | Yes |
| **Silicon DRIE** | ~1 um | Very high (50:1) | 50-200 nm Ra | High (batch) | $300,000-1,000,000 | $20-100 | Yes |
| **Anodic bonding** | N/A (bonding) | N/A | N/A | High (batch) | $5,000-500,000 | $5-20 | Preferred |
| **Glass thermal bonding** | N/A (bonding) | N/A | N/A | Moderate | $10,000-100,000 | $5-20 | Yes |

---

## 10. Emerging Trends (2025-2026)

1. **Hybrid SLE + 2PP**: Femtika and others combining subtractive glass SLE with additive two-photon polymerization in a single workstation -- enabling polymer microstructures inside glass channels.

2. **High-speed SLE**: LightFab's micro-scanner technology maintains high velocities on short vectors and sharp turns, significantly reducing SLE processing times for complex 3D microfluidics.

3. **Eco-friendly glass etching**: Research into alternatives to HF for glass etching, including alkaline etchants and plasma-based methods, motivated by environmental and safety concerns.

4. **Low-temperature bonding**: Plasma-activated direct bonding at near room temperature, eliminating thermal budget constraints and enabling bonding of pre-functionalized surfaces.

5. **Wafer-level packaging**: Adaptation of semiconductor packaging technologies for mass production of glass/silicon microfluidic devices at wafer scale.

6. **Deep multilevel glass etching**: Multiple-depth channel networks in single glass substrates using sequential lithography-etch cycles in BOE, enabling 3D channel crossings.

7. **Cryo-DRIE improvements**: Smoother sidewalls than Bosch process, enabling better optical and fluidic performance in silicon channels.

---

## Sources

- [CO2 laser machining for microfluidics mold fabrication from PMMA](https://www.sciencedirect.com/science/article/abs/pii/S1226086X21001568)
- [Assessment of PMMA and polystyrene microfluidic chips by CO2 laser](https://www.sciencedirect.com/science/article/abs/pii/S0169433220323990)
- [Excellent quality microchannels by CO2 laser with chemical post-processing](https://link.springer.com/article/10.1007/s10404-019-2291-1)
- [Simple, low-cost fabrication of acrylic droplet microfluidics](https://www.nature.com/articles/s41598-018-27037-5)
- [Trotec: Laser cutting plastics](https://www.troteclaser.com/en-us/laserable-materials/laser-cutting-plastics)
- [Epilog Laser: Product line](https://www.epiloglaser.com/laser-machines/product-line/)
- [Selective Laser-Induced Etching of 3D Glass Components for Microfluidics](https://pmc.ncbi.nlm.nih.gov/articles/PMC6190087/)
- [FEMTOprint: Understanding SLE](https://www.femtoprint.ch/media/understanding-selective-laser-induced-etching-sle-how-it-works-and-what-it-enables/)
- [Optimization of SLE for 3D glass microfluidic device](https://link.springer.com/article/10.1186/s40486-019-0094-5)
- [LightFab 3D Printer](https://lightfab.de/products/3d-printer/)
- [LightFab 3D Printer Data Sheet (2025)](https://lightfab.de/wp-content/uploads/2025/11/Flyer_Lightfab-3d-printer.pdf)
- [3D-printed glass microfluidics for fluid dynamics and rheology](https://www.sciencedirect.com/science/article/pii/S1359029418301341)
- [Maskless rapid manufacturing of glass microfluidics using picosecond pulsed laser](https://www.nature.com/articles/s41598-019-56711-5)
- [UV Laser Micromachining of Polymers for Microfluidic Applications](https://www.sciencedirect.com/science/article/pii/S1535553504001790)
- [Direct Micromachining of Microfluidic Channels Using Laser Ablation](https://pmc.ncbi.nlm.nih.gov/articles/PMC6432037/)
- [Eco-friendly glass wet etching for MEMS: A review (2024)](https://ceramics.onlinelibrary.wiley.com/doi/full/10.1111/jace.19961)
- [Chemical etching of glasses in hydrofluoric acid: A brief review](https://www.sciencedirect.com/science/article/abs/pii/S2214785321077865)
- [Glass etch wet process SOP (UC Irvine)](https://www.inrf.uci.edu/wordpress/wp-content/uploads/sop-wet-glass-etch-wet-process.pdf)
- [MIT HF etching safety procedures](https://www1.psfc.mit.edu/esh/hf.html)
- [Deep multilevel wet etching of fused silica in BOE](https://www.nature.com/articles/s41598-023-32503-w)
- [A practical guide for fabrication of microfluidic devices using glass and silicon](https://pmc.ncbi.nlm.nih.gov/articles/PMC3365353/)
- [Deep Reactive Ion Etching -- Oxford Instruments](https://plasma.oxinst.com/technology/deep-reactive-ion-etching)
- [Comparison between Bosch and STiGer processes for deep silicon etching](https://pmc.ncbi.nlm.nih.gov/articles/PMC8537062/)
- [Reduced etch lag and high aspect ratios by DRIE](https://pmc.ncbi.nlm.nih.gov/articles/PMC8150727/)
- [DRIE -- Wikipedia](https://en.wikipedia.org/wiki/Deep_reactive-ion_etching)
- [Silicon etching and DRIE (Samco)](https://www.samcointl.com/processes/etching/si-etching/)
- [Anodic bonding -- Wikipedia](https://en.wikipedia.org/wiki/Anodic_bonding)
- [Anodic bonding procedure (UC Berkeley)](https://qb3.berkeley.edu/wp-content/uploads/2020/09/AnodicBondingProcedure.pdf)
- [Fabrication of microfluidic cavities using Si-to-glass anodic bonding](https://pubs.aip.org/aip/rsi/article/89/7/073902/358389/)
- [Silicon-glass anodic bonding at low temperature](https://www.researchgate.net/publication/253563489_Silicon-glass_anodic_bonding_at_low_temperature)
- [Simple low-temperature glass bonding with O2 plasma activation](https://www.mdpi.com/2072-666X/11/9/804)
- [What is anodic bonding -- UniversityWafer](https://www.universitywafer.com/anondic-bonding.html)
- [PDMS and microfluidics review (Elveflow)](https://elveflow.com/microfluidic-reviews/the-polydimethylsiloxane-pdms-and-microfluidics/)
- [PDMS for microfluidics: Limitations and alternatives (Micronit)](https://micronit.com/expertise/manufacturing-expertise/pdms-for-microfluidics)
- [Microfluidics chips fabrication techniques comparison (2024)](https://www.nature.com/articles/s41598-024-80332-2)
- [How to choose a microfluidic chip (Fluigent)](https://www.fluigent.com/resources-support/expertise/expertise-reviews/what-is-microfluidics/microfluidic-chips/how-to-choose-a-microfluidic-chip/)
