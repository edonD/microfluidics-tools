# Workflows: From Idea to Working Microfluidic Chip

> Last updated: March 2026

## Workflow A: Quick Prototype (1-2 weeks, < $500)

**Goal:** Rapidly validate a microfluidic concept with minimal investment.

### Step 1: Design (Day 1-2)

**Tool choices:**
- **CAD:** Fusion 360 (free personal license) or AutoCAD (free student license)
  - Design channel geometry in 2D sketch → extrude to 3D
  - For simple T-junctions, Y-mixers, straight channels: 2D is enough
- **Alternative:** 3DuF (free, browser-based) for standard microfluidic components
- **Channel dimensions:** Keep channels >100 µm wide for easy fabrication

**Design tips:**
- Start with literature designs that are known to work
- Standard channel heights: 50-100 µm (SU-8) or 200-500 µm (3D printed)
- Include alignment marks if multi-layer
- Design inlet/outlet ports to match your tubing (typically 1-1.5 mm diameter)

### Step 2: Quick Simulation (Day 2-3)

**Tool choices (all free):**
- **Analytical calculation first:** Use hydraulic resistance formulas
  - Rectangular channel: R = 12µL/(wh³) × [1 - 0.63(h/w)]⁻¹ (for h < w)
  - Estimate pressure drops and flow rates before simulating
- **COMSOL** (if available through university): Laminar Flow interface, quick 2D simulation
- **OpenFOAM** (free): Use simpleFoam for single-phase steady-state
- **SimScale** (free tier): Cloud-based, no install needed, good for quick checks
- **Python/MATLAB:** Simple finite difference for diffusion/mixing estimates

**What to simulate:**
- Flow velocity profile in channels
- Pressure drop across the device
- Mixing efficiency (if mixer design)
- Residence time distribution

### Step 3: Fabrication — Option A: Soft Lithography (if cleanroom available)

**Requirements:** Access to university cleanroom or makerspace
**Cost:** $100-300

1. **Make photomask:** Order film mask from an online service ($50-100, 2-5 day turnaround)
   - Resolution: ~10-20 µm minimum feature (film mask limitation)
   - Use CAD export to DXF/PDF at high resolution
2. **Spin coat SU-8** on silicon wafer (cleanroom)
   - SU-8 2050 or 2075 for 50-100 µm channels
   - Recipe: spin → soft bake → UV expose → post-bake → develop
3. **Cast PDMS** (Sylgard 184, 10:1 ratio)
   - Mix, degas in vacuum desiccator (30-60 min)
   - Pour over SU-8 mold, cure at 65°C for 2-4 hours
4. **Punch inlet/outlet holes** (biopsy punch, 1 mm or 1.5 mm)
5. **Bond to glass slide** — O₂ plasma or corona treater (BD-20AC, ~$200)
6. **Connect tubing** — Tygon tubing press-fit into ports

### Step 3: Fabrication — Option B: 3D Printing (no cleanroom needed)

**Requirements:** Access to SLA 3D printer (Formlabs Form 3/4 or similar)
**Cost:** $5-50 per chip

1. **Design in CAD** with enclosed channels (design channel cross-section ≥ 200 µm × 200 µm)
2. **Print** using clear resin (Formlabs Clear V4 or BioMed Clear)
   - Orient to minimize support inside channels
   - Use 25 µm layer height for best resolution
3. **Post-process:**
   - Wash in IPA (20 min)
   - Flush channels with IPA using syringe
   - UV post-cure
4. **Connect:** Design integrated Luer-lock connectors or drill ports for tubing

### Step 4: Test (Day 4-7)

**Equipment (budget):**
- Syringe pump: DIY Poseidon (~$400) or manual syringe for qualitative tests
- Microscope: Any stereomicroscope or even smartphone macro lens for initial checks
- Dye: Food coloring in water for flow visualization
- Camera: Smartphone mounted on microscope

**What to check:**
- Channels are clear and continuous
- No leaks at bonds/connections
- Flow is laminar (should be at typical microfluidic Re < 1)
- Qualitative mixing behavior (if mixer)

### Total Cost Breakdown

| Item | Cost |
|------|------|
| Film photomask (or skip if 3D printing) | $50-100 |
| PDMS kit (Sylgard 184, 500g) | $60-80 |
| Glass slides | $10-20 |
| Tubing and connectors | $30-50 |
| 3D print resin (if 3D printing route) | $5-30 |
| Syringe and dye for testing | $10-20 |
| **Total** | **$100-300** |

---

## Workflow B: Research-Grade Device (1-2 months, < $5,000)

**Goal:** Produce a publication-quality microfluidic device with proper characterization.

### Step 1: Rigorous Design (Week 1)

**Tool choices:**
- **3D CAD:** SolidWorks (academic ~$100-500/yr) or Fusion 360
  - Full 3D model of chip including mold geometry
  - Design for manufacturing — draft angles for molding, spacing for bonding
- **Mask layout:** KLayout (free) or L-Edit
  - Export to GDSII format for chrome mask fabrication
  - Include alignment marks, test structures, scale bars

**Design rules:**
- Minimum feature size: 5-10 µm (limited by mask and lithography)
- Channel aspect ratio: keep < 10:1 to prevent collapse
- Wall thickness between channels: ≥ 1.5× channel width
- Inlet/outlet spacing: ≥ 5 mm from chip edge

### Step 2: Comprehensive Simulation (Week 1-2)

**Tool choices:**
- **COMSOL Multiphysics + Microfluidics Module** (preferred for research)
  - 2D and 3D models
  - Laminar flow + transport of diluted species (for mixing)
  - Two-phase flow (Level Set or Phase Field method for droplets)
  - Electrophoresis/electroosmosis if using electric fields
- **OpenFOAM** (free alternative)
  - interFoam for two-phase flow / droplet generation
  - simpleFoam for single-phase with custom boundary conditions
  - Requires more setup but fully capable

**Simulation protocol:**
1. Mesh independence study — refine until results converge (<2% change)
2. Validate against known analytical solutions (Poiseuille flow)
3. Parameter sweep — optimize channel dimensions, flow rates
4. Export results for publication-quality figures

### Step 3: Fabrication (Week 2-4)

**Photomask:** Order chrome mask ($200-500, 1-2 week lead time)
- Vendor options: Front Range Photomask, Compugraphics, Photo Sciences
- Resolution: 1-2 µm features on chrome-on-glass

**SU-8 Mold Fabrication (Cleanroom):**
1. Dehydrate silicon wafer (200°C, 5 min)
2. Spin coat SU-8 (recipe depends on target height)
   - SU-8 2050: ~50 µm at 3000 rpm
   - SU-8 2075: ~75 µm at 3000 rpm
   - SU-8 2100: ~100 µm at 3000 rpm
3. Soft bake (65°C → 95°C ramp, time depends on thickness)
4. UV expose (mask aligner: SUSS MA6 or similar)
   - Dose: ~150-250 mJ/cm² depending on thickness
5. Post-exposure bake (65°C → 95°C)
6. Develop in PGMEA (SU-8 developer)
7. Hard bake (optional, 150°C for durability)
8. Silanize mold (FDTS or trichloro(1H,1H,2H,2H-perfluorooctyl)silane vapor)

**PDMS Casting:**
1. Mix Sylgard 184 (10:1 base:curing agent by weight)
2. Degas in vacuum desiccator (30-60 min, until no bubbles)
3. Pour over mold (target ~5 mm thickness)
4. Cure at 65°C for 4 hours (or 80°C for 2 hours)
5. Peel, punch ports (biopsy punch)
6. Clean with tape and IPA

**Bonding:**
1. O₂ plasma treatment (30-60 seconds, 30-50 W)
   - Equipment: Harrick PDC-32G or Diener Zepto
2. Bring PDMS and glass into contact within 60 seconds of plasma treatment
3. Bake at 65°C for 10 min to strengthen bond
4. Let sit overnight for full bond strength

### Step 4: Characterization (Week 3-6)

**Equipment:**
- **Syringe pump:** Harvard PHD 2000 or Cetoni neMESYS (precise flow control)
- **Pressure controller:** Elveflow OB1 or Fluigent MFCS-EZ (if steady flow needed)
- **Microscope:** Inverted fluorescence microscope (Nikon Ti2, Olympus IX73, or Zeiss Axio Observer)
- **Camera:** Scientific CMOS (Hamamatsu ORCA) or high-speed camera for droplets
- **Flow sensors:** Sensirion SLF3x series for real-time flow measurement

**Characterization protocol:**
1. Leak test at 1.5× operating pressure
2. Flow visualization with fluorescent dyes (fluorescein, rhodamine B)
3. Velocity measurement via micro-PIV (if available) or particle tracking
4. Mixing efficiency quantification from fluorescence intensity profiles
5. Droplet size distribution (if droplet generator)
6. Reproducibility study (n ≥ 3 devices, n ≥ 3 repeats each)

### Step 5: Documentation (Week 5-8)

- Photograph devices with scale bars
- Record all fabrication parameters
- Process simulation data for figures
- Compare experimental vs simulation results
- Prepare for publication in Lab on a Chip, Biomicrofluidics, etc.

### Total Cost Breakdown

| Item | Cost |
|------|------|
| Chrome photomask | $200-500 |
| Cleanroom fees (10-20 hours) | $500-2,000 |
| PDMS + consumables | $200-500 |
| Simulation software (COMSOL academic or free tools) | $0-3,000 |
| Tubing, connectors, reagents | $200-500 |
| Equipment usage fees (microscope, pumps) | $500-1,500 |
| **Total** | **$1,600-8,000** |

---

## Workflow C: Production-Ready Device (3-6 months, $10k-$50k+)

**Goal:** Develop a manufacturable microfluidic product ready for volume production.

### Step 1: Design for Manufacturing (Month 1)

**Tool choices:**
- **3D CAD:** SolidWorks Professional or CATIA
  - Design chip AND packaging (chip holder, connectors, housing)
  - Design injection mold or hot embossing tool geometry
  - Include draft angles (1-3°), ejection features, gate location
- **Simulation:** COMSOL (commercial license) or ANSYS Fluent
  - Full 3D simulation with actual operating conditions
  - Include thermal effects, stress analysis
  - Moldflow simulation for injection mold design (ANSYS or Moldex3D)

**Material selection:**
- **COC (TOPAS 5013, 6013, 8007):** Excellent optical clarity, chemical resistance, low autofluorescence
- **COP (Zeonor 1060R, 1420R):** Similar to COC, good for biological applications
- **PMMA:** Cheapest thermoplastic, good optical properties, limited chemical resistance
- **PS:** Biologically familiar (cell culture), cheap, poor solvent resistance
- **PC:** High temperature resistance, but high autofluorescence

### Step 2: Prototype Validation (Month 1-2)

1. **PDMS prototypes** — rapid iterations (3-5 design versions)
2. **3D printed prototypes** — for testing mechanical integration, connectors
3. **CNC-milled prototypes** — in target thermoplastic material for material compatibility testing
4. Test with real biological/chemical samples (not just dye water)
5. Validate against simulations

### Step 3: Tooling & Pilot Production (Month 2-4)

**Mold fabrication options:**

| Method | Cost | Lead Time | Best For |
|--------|------|-----------|----------|
| CNC micromilling (aluminum) | $5,000-15,000 | 2-4 weeks | Prototype molds, 1,000-10,000 parts |
| CNC micromilling (steel) | $15,000-50,000 | 4-8 weeks | Production molds, 100,000+ parts |
| Electroforming (nickel) | $10,000-30,000 | 4-8 weeks | Fine features, high replication |
| EDM (electrical discharge) | $10,000-40,000 | 4-8 weeks | Complex 3D features |

**Contract manufacturer selection:**
1. **Microfluidic ChipShop** (Germany) — ISO 13485, thermoplastic expertise, injection molding
2. **Micronit** (Netherlands) — Glass, silicon, hybrid, full development support
3. **Vantiva** (France) — High-volume polymer microfluidics
4. **Stratec** (Germany) — IVD consumable manufacturing
5. **uFluidix** (Canada) — Flexible, small-to-medium batches

**Pilot run:** 100-1,000 devices for validation testing

### Step 4: Testing & Validation (Month 3-5)

**Functional testing:**
- Performance against design specifications
- Device-to-device reproducibility (Cp/Cpk analysis)
- Shelf life / aging studies
- Material compatibility with target reagents
- Sterilization compatibility (if biomedical)

**Quality testing:**
- Dimensional metrology (profilometry, optical measurement)
- Burst pressure testing
- Optical clarity measurement
- Surface energy / contact angle measurement
- Bond strength testing (peel test, pressure test)

### Step 5: Scale-Up & Production (Month 4-6+)

**Production setup:**
- Injection molding: cycle time 15-60 seconds per part
- Bonding: thermal, UV adhesive, or ultrasonic welding
- Assembly: manual or semi-automated
- Quality control: inline inspection

**Regulatory (if medical device):**
- ISO 13485 quality management system
- Design history file (DHF)
- Risk analysis (ISO 14971)
- Biocompatibility testing (ISO 10993) if patient contact
- FDA 510(k) or CE marking as applicable

### Total Cost Breakdown

| Item | Cost |
|------|------|
| CAD + simulation software (commercial) | $10,000-30,000/yr |
| PDMS prototyping (10-20 iterations) | $2,000-5,000 |
| Injection mold tooling | $15,000-100,000 |
| Pilot production (500-1,000 units) | $5,000-20,000 |
| Testing equipment & characterization | $5,000-20,000 |
| Contract manufacturer NRE | $5,000-30,000 |
| Regulatory / quality (if medical) | $20,000-100,000 |
| **Total** | **$60,000-300,000+** |

---

## Decision Matrix: Choosing Your Workflow

| Factor | Workflow A (Quick) | Workflow B (Research) | Workflow C (Production) |
|--------|-------------------|----------------------|------------------------|
| **Timeline** | 1-2 weeks | 1-2 months | 3-6 months |
| **Budget** | <$500 | $2,000-8,000 | $50,000-300,000+ |
| **Feature size** | >100 µm (3D print) or >10 µm (PDMS) | >5 µm | >1 µm |
| **Material** | PDMS or 3D print resin | PDMS | Thermoplastic (COC/COP/PMMA) |
| **Quantity** | 1-10 | 10-50 | 1,000-1,000,000 |
| **Reproducibility** | Low-Medium | Medium-High | High |
| **When to choose** | Concept validation, student projects | Publications, grant-funded research | Product development, commercialization |
| **Simulation depth** | Analytical + quick 2D | Full 3D, parameter sweeps | Full 3D + manufacturing simulation |
