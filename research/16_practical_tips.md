# Practical Tips, Design Rules & Troubleshooting

> Last updated: March 2026

## Microfluidic Design Rules

### Channel Dimensions

| Parameter | Rule of Thumb | Reason |
|-----------|--------------|--------|
| **Starting dimensions** | 100 µm wide × 20 µm tall | Good balance of flow, fabrication, and observation |
| **Minimum width (PDMS)** | ~5 µm | Below this, demolding becomes difficult |
| **Minimum width (3D print SLA)** | ~200 µm | Resin clearing and resolution limit |
| **Minimum width (3D print DLP/BMF)** | ~20-50 µm | High-end DLP printers |
| **Aspect ratio (h:w)** | Keep between 1:10 and 4:1 | <1:10: channel collapses. >4:1: wall collapse (PDMS) |
| **Wide channel support** | Add posts every 10× height | Prevents roof collapse in wide PDMS channels |
| **Wall between channels** | ≥1.5× channel width | Structural integrity |
| **Inlet/outlet port size** | 1.0-1.5 mm diameter | Matches standard biopsy punches and tubing |
| **Port-to-edge distance** | ≥5 mm | Prevents chip edge cracking |
| **Alignment tolerance** | ±30 µm | Design must work despite this error (multi-layer) |

### Dimensionless Numbers Cheat Sheet

| Number | Formula | Typical Microfluidic Value | Physical Meaning |
|--------|---------|--------------------------|-----------------|
| **Reynolds (Re)** | ρvL/µ | 0.001 – 100 (usually <1) | Inertial vs viscous forces. Re < 2000 = laminar. |
| **Peclet (Pe)** | vL/D | 10 – 10,000 | Advection vs diffusion. High Pe = mixing is hard. |
| **Capillary (Ca)** | µv/γ | 10⁻⁴ – 10⁻¹ | Viscous vs surface tension. Controls droplet formation. |
| **Weber (We)** | ρv²L/γ | <1 | Inertial vs surface tension. |
| **Dean (De)** | Re × √(d/D) | 1 – 100 | Secondary flow in curved channels. Key for spiral separators. |
| **Bond (Bo)** | ΔρgL²/γ | <1 | Gravity vs surface tension. Usually gravity negligible in µfluidics. |
| **Knudsen (Kn)** | λ/L | <0.001 | Mean free path vs channel size. Kn < 0.01 = continuum valid. |

### Hydraulic Resistance Quick Reference

**Rectangular channel** (h < w):
```
R = 12µL / (wh³) × [1 - 0.63(h/w)]⁻¹
```

**Circular channel:**
```
R = 128µL / (πd⁴)
```

**Pressure drop:** ΔP = Q × R (analogous to V = IR in electronics)

Where: µ = viscosity, L = length, w = width, h = height, d = diameter, Q = flow rate

---

## Common Problems & Solutions

### 1. Air Bubbles

**The #1 problem in microfluidics.** Bubbles block channels, distort flow, ruin experiments.

| Cause | Solution |
|-------|----------|
| Dissolved gas coming out of solution (temperature change) | **Degas fluids** before use: vacuum degas for 30+ minutes, or use degassed/autoclaved water |
| Trapped air during chip priming | **Pre-wet channels** with ethanol (wets PDMS easily), then flush with buffer |
| Air at connections/fittings | Ensure all connections are tight. Use Teflon tape on threaded fittings. |
| Sharp corners in design | **Avoid acute angles** in channel design — use rounded corners |
| Temperature increase during experiment | Keep system at **constant temperature** |
| PDMS gas permeability | Can be advantage (bubbles slowly absorb into PDMS) or disadvantage |

**Emergency bubble removal:**
- Apply brief burst of high pressure to push bubble through
- If bubble is stuck, flush with ethanol (low surface tension) to dislodge
- Use a bubble trap upstream of your device (commercial or 3D printed)

### 2. Leaking

| Cause | Solution |
|-------|----------|
| Poor plasma bonding | Ensure surfaces are clean (no fingerprints, dust). Bond within 60 sec of plasma. Use 30-50 W, 30-60 sec O₂ plasma. |
| Loose connections | Tighten fittings. Use IDEX fingertight → wrench-tight. Add Teflon tape. |
| PDMS port too large | Use biopsy punch slightly smaller than tubing OD for interference fit |
| Delamination at high pressure | Add bake step after bonding (65°C, 2-24 hr). Consider epoxy reinforcement. |
| Bonding to wrong material | PDMS-glass needs plasma. PDMS-PDMS needs plasma. Glass-glass needs thermal or anodic bonding. |

### 3. Channel Clogging

| Cause | Solution |
|-------|----------|
| Particle aggregation | **Filter all solutions** before loading (0.2-0.45 µm syringe filter) |
| Cell clumping | Add surfactant (Pluronic F-68, 0.1%), filter through cell strainer |
| PDMS debris | Clean channels with scotch tape before bonding. Blow with N₂. |
| Precipitation at junctions | Re-design mixing region. Add dilution step. |
| Bubble-induced clogging | See bubble solutions above |

**Recovery from clog:**
- Back-flush with clean buffer at higher pressure
- Sonicate chip briefly (be careful — can delaminate bonds)
- Flush with enzyme solution (trypsin for protein clogs, DNase for DNA)

### 4. Unstable Flow

| Cause | Solution |
|-------|----------|
| Syringe pump pulsation | Switch to **pressure controller** (Elveflow OB1, Fluigent MFCS) |
| Compliant tubing | Use shorter tubing, switch to **PEEK** (rigid, low compliance) |
| Air bubbles in system | Degas, add bubble trap |
| Syringe/tubing compliance | Use rigid syringe (glass), minimize tubing length |
| Evaporation from reservoir | Use sealed reservoirs. Add humidified air. |

### 5. PDMS-Specific Issues

| Problem | Cause | Solution |
|---------|-------|----------|
| **Hydrophobic recovery** | PDMS surface returns to hydrophobic after plasma | Apply PVA, PEG coating, or BSA blocking immediately. Or use PDMS surface modification (APTES). Alternatively, use immediately after plasma (<30 min). |
| **Small molecule absorption** | PDMS absorbs hydrophobic drugs (logP > 1.5) | Switch to **COC, glass, or Flexdym**. Or coat PDMS with parylene, sol-gel, or Pluronic. |
| **Solvent swelling** | Organic solvents swell PDMS (hexane, toluene, DCM) | Use glass, silicon, or PTFE-coated channels. Avoid solvents with Hildebrand solubility parameter close to PDMS (δ ≈ 15.5 MPa^½). |
| **Gas permeability** | CO₂/O₂ passes through PDMS | Advantage for cell culture. Disadvantage for anaerobic or gas-sensitive assays. |
| **Autofluorescence** | PDMS background fluorescence | Use thin PDMS layers. Switch to COC/COP for sensitive fluorescence. |

---

## Sterilization Methods for Microfluidic Chips

| Method | Temperature | Time | PDMS | Glass | COC/COP | PMMA | Notes |
|--------|------------|------|------|-------|---------|------|-------|
| **70% Ethanol flush** | RT | 10-30 min | Yes | Yes | Yes | Caution | Most common lab method. Follow with sterile PBS rinse. |
| **UV exposure** | RT | 15-60 min | Caution* | Yes | Yes | Yes | *Makes PDMS brittle with prolonged exposure. Surface-only. |
| **Autoclave** | 121°C | 15-30 min | Yes | Yes | No** | No** | **Thermoplastics deform above Tg. PDMS tolerates well. |
| **O₂ plasma** | RT | 30-120 sec | Yes | Yes | Yes | Yes | Sterilizes + activates surface for bonding. Two-for-one. |
| **Gamma irradiation** | RT | — | Yes | Yes | Yes | Caution | Deep penetration. Good for sealed devices. May yellow some plastics. |
| **Ethylene oxide (EtO)** | 37-63°C | Hours | Yes | Yes | Yes | Yes | Penetrates packaging. Industry standard for medical devices. Requires aeration. |
| **H₂O₂ vapor** | Low temp | 30-60 min | Yes | Yes | Yes | Yes | Low temperature alternative to autoclave. |

---

## Quick Protocol: PDMS Chip from Start to Finish

### Day 1: Mold Fabrication (cleanroom, 4-6 hours)

1. **Clean wafer:** Acetone rinse → IPA rinse → N₂ dry → dehydrate bake (200°C, 5 min)
2. **Spin coat SU-8:**
   - 50 µm: SU-8 2050, 500 rpm 10 sec → 3000 rpm 30 sec
   - 100 µm: SU-8 2100, 500 rpm 10 sec → 3000 rpm 30 sec
3. **Soft bake:** 65°C 3 min → 95°C (6 min for 50 µm, 20 min for 100 µm)
4. **UV expose:** 150-250 mJ/cm² (depends on thickness). Hard contact mode.
5. **Post-exposure bake:** 65°C 1 min → 95°C (6 min for 50 µm, 10 min for 100 µm)
6. **Develop:** PGMEA (SU-8 developer), agitate gently, 5-15 min. Rinse with fresh PGMEA, then IPA. White residue in IPA = underdeveloped.
7. **Hard bake (optional):** 150°C, 15 min (makes mold more durable)
8. **Silanize:** Place mold in vacuum desiccator with 2-3 drops FDTS or trichloro(perfluorooctyl)silane. Vacuum for 1 hour. **Do this in fume hood — vapors are toxic.**

### Day 2: PDMS Casting (bench, 4-6 hours active)

1. **Mix PDMS:** Weigh 10:1 ratio (base:curing agent) Sylgard 184. Mix thoroughly (2-3 min). Will be very bubbly.
2. **Degas:** Place in vacuum desiccator. Pump down. Bubbles will expand then pop. Continue until no bubbles (~30-60 min).
3. **Pour:** Pour over SU-8 mold in petri dish. Target ~5 mm thick.
4. **Degas again:** Brief vacuum to remove bubbles introduced during pouring (~10-15 min).
5. **Cure:** 65°C for 4 hours (standard) or 80°C for 2 hours (faster).
6. **Peel:** Cut around mold with scalpel. Carefully peel PDMS from mold starting from edge.
7. **Punch ports:** Use biopsy punch (1.0 or 1.5 mm). Punch from channel side (features facing up) through to flat side. Push straight through.
8. **Clean:** Remove debris with scotch tape. Blow with N₂.

### Day 2-3: Bonding (bench, 30 min)

1. **Clean glass slide:** Acetone → IPA → N₂ dry
2. **Plasma treat:** Place PDMS (channel side up) and glass in plasma cleaner. 30 W O₂ plasma, 30-60 seconds. (Or use handheld corona treater BD-20AC: wave over surfaces for 30-60 sec at ~1 cm distance)
3. **Bond:** Remove from plasma, bring surfaces into contact within 60 seconds. Press gently. Channels should remain open.
4. **Bake:** 65°C for at least 10 min (overnight = stronger bond)

### Day 3: Test

1. **Connect tubing:** Insert Tygon tubing (OD slightly larger than port) into punched holes. Friction fit.
2. **Prime:** Slowly inject ethanol to wet channels (ethanol wets PDMS easily). Then switch to water/buffer.
3. **Check:** Look under microscope for channel filling, no leaks, no bubbles.
4. **Run experiment:** Connect to syringe pump or pressure controller.

---

## Common Mistakes to Avoid

1. **Not degassing PDMS** → Bubbles in channels, rough surfaces
2. **Bonding too late after plasma** → Weak bond. Must bond within 60 seconds.
3. **Touching activated surfaces** → Fingerprints kill the bond
4. **Punching ports wrong direction** → Features on wrong side
5. **Using contaminated PDMS** → Curing inhibition, failed bonds
6. **Not filtering solutions** → Clogging within minutes
7. **Ignoring temperature effects** → Bubbles forming during experiment
8. **Too-long tubing** → Slow response time, flow instability
9. **Not checking for leaks before experiment** → Wasted reagents
10. **Overexposing SU-8** → T-topping (overhanging edges), poor feature fidelity
11. **Underdeveloping SU-8** → Residue in channels, blocked features
12. **Not silanizing mold** → PDMS sticks to mold, tears on demolding

---

## Mixer Design Guide

### Passive Mixer Comparison

| Mixer Type | Mixing Efficiency | Fabrication Complexity | Best Re Range | Notes |
|-----------|------------------|----------------------|---------------|-------|
| **T/Y-junction** | Low (30-50%) | Very simple | Any | Only diffusion-based. Need long channels for complete mixing. |
| **Serpentine** | Medium (60-80%) | Simple | < 10 | Chaotic advection from turns. Easy to fabricate. Good starting point. |
| **Staggered Herringbone (SHM)** | High (>95%) | Medium (multi-layer) | < 10 | Asymmetric ridges create transverse flows. ~96% theoretical efficiency. Gold standard for passive mixing. |
| **Split-and-recombine** | High (>90%) | Complex (3D) | 1-100 | Multi-layer structures. Better at higher Re. |
| **Dean flow (spiral)** | Medium-High | Simple | 10-100 | Dean vortices in curved channels. Also used for particle separation. |
| **Tesla mixer** | High (>90%) | Medium | 1-100 | Uses Coanda effect. Good across Re range. |

**Rule of thumb:** At Re < 1 and Pe > 100, mixing is diffusion-limited. You need either very long channels (L = Pe × w) or 3D mixing elements (SHM). At Re > 10, inertial effects help and simpler geometries work.

### Active Mixer Options

| Method | Mixing Efficiency | Complexity | Notes |
|--------|------------------|-----------|-------|
| Acoustic (SAW, ultrasonic) | Very high | High | Fast mixing, no geometric features needed |
| Electrokinetic | High | Medium | Requires electrodes, AC/DC fields |
| Magnetic (ferrofluid) | High | High | Requires magnetic particles and external magnets |
| Pressure pulsation | Medium-High | Low | Alternate flow rates using pressure controller |
| Thermal | Medium | Medium | Temperature gradients create Marangoni flows |

---

## Consumables Pricing Reference

| Item | Typical Price | Size | Vendor(s) | Notes |
|------|-------------|------|-----------|-------|
| **PDMS (Sylgard 184)** | ~€270 / ~$300 | 1.1 kg kit | Dow (via Darwin Microfluidics, Ellsworth) | 10:1 ratio, enough for ~50-100 chips |
| **PDMS (Sylgard 184)** | ~€1,050 / ~$1,150 | 5.5 kg kit | Dow | Better value for high-volume use |
| **SU-8 photoresist** | ~$500-700 | 500 mL | Kayaku Advanced Materials (formerly MicroChem) | Price varies by viscosity grade |
| **SU-8 developer (PGMEA)** | ~$50-100 | 1 L | Sigma-Aldrich, Fisher | Propylene glycol monomethyl ether acetate |
| **Silicon wafers (4")** | ~$5-15 each | Pack of 25 | UniversityWafer, WRS Materials | Test-grade is fine for molds |
| **Glass slides (75×25mm)** | ~$20-40 | Box of 72 | Fisher, VWR | Standard microscope slides |
| **Chrome photomask** | $200-800 | Per mask | Front Range Photomask, Compugraphics | 1-2 µm resolution |
| **Film photomask** | $50-200 | Per mask | CAD/Art Services, OutputCity | ~10-20 µm resolution |
| **Biopsy punches** | ~$30-50 | Pack of 50 | Miltex, Harris Uni-Core | 1.0 mm or 1.5 mm diameter |
| **Tygon tubing (1/16")** | ~$15-30 | 25 ft | Cole-Parmer | Various ID options |
| **PEEK tubing (1/16")** | ~$30-80 | 5 ft | IDEX, Cole-Parmer | For solvents/high pressure |

---

## PDMS Material Selection Decision Tree

```
Start
  |
  +-- Will you use organic solvents?
  |     |-- YES → Use glass, silicon, COC, or PEEK-lined channels
  |     |-- NO → Continue
  |
  +-- Do you need to study small molecule drugs (logP > 1.5)?
  |     |-- YES → Use COC, COP, glass, or Flexdym (PDMS absorbs them)
  |     |-- NO → Continue
  |
  +-- Do you need mass production (>1000 devices)?
  |     |-- YES → Use injection molding in COC/COP/PMMA
  |     |-- NO → Continue
  |
  +-- Do you need low autofluorescence?
  |     |-- YES → Use COC/COP or glass
  |     |-- NO → Continue
  |
  +-- Do you need gas permeability (cell culture)?
  |     |-- YES → PDMS is ideal
  |     |-- NO → PDMS is fine, but COC/glass also work
  |
  +-- PDMS is your best choice for prototyping
```

---

## Pre-Fabrication Design Checklist

Before sending your design to fabrication, verify each item:

### Geometry
- [ ] Channel widths and heights are within fabrication limits
- [ ] Aspect ratio is between 1:10 and 4:1
- [ ] No negative draft angles (for molding/embossing)
- [ ] Support posts added for wide channels (every 10× height)
- [ ] Rounded corners (no acute angles) to prevent bubble trapping
- [ ] Wall thickness between channels ≥1.5× channel width

### Ports & Connections
- [ ] Inlet/outlet port diameter matches your tubing (1.0 or 1.5 mm for PDMS)
- [ ] Ports are ≥5 mm from chip edge
- [ ] Port spacing allows for tubing/connectors without interference
- [ ] Dead volume at connections is minimized

### Alignment & Layers
- [ ] Alignment marks on every layer (for multi-layer devices)
- [ ] Layer registration tolerance accounted for (±30 µm typical)
- [ ] Scale bar included for verification after fabrication

### Simulation
- [ ] Pressure drop at working flow rate is within pump/controller range
- [ ] Reynolds number calculated and confirmed laminar (Re < ~2000)
- [ ] Mixing length estimated (need mixer if channel too short?)
- [ ] No dead-end channels (or intentional)

### Fabrication
- [ ] Design format matches fabrication method (GDSII for masks, STL for 3D print, DXF for laser)
- [ ] Feature sizes are achievable with chosen method
- [ ] Channel dimensions constant depth where possible (easier to fabricate)
- [ ] Designed for the right polarity (dark-field vs light-field for mask)

### Testing
- [ ] Plan for how to connect tubing
- [ ] Plan for how to prime channels (ethanol first?)
- [ ] Plan for leak testing protocol
- [ ] Microscope access — can you see the channels?

### Documentation
- [ ] All dimensions labeled on design file
- [ ] Fabrication parameters documented (resist thickness, exposure dose)
- [ ] Version number on the design file

---

## Education & Starter Kits

| Kit | Vendor | Price | Includes | Best For |
|-----|--------|-------|----------|----------|
| **Microfluidics Education Kit** | LabSmith | ~$3,000-5,000 | Research-grade pumps, chips, automation software, curriculum | University courses, 1-4 students per kit |
| **Educational Starter Kit** | Dolomite | ~$2,000-4,000 | Compact system, chips, Mitos Fluika software, USB-powered | Portable demos, intro courses |
| **DIY Poseidon Kit** | Open source | ~$400 | 3 syringe pumps + microscope, 3D printed | Budget teaching, maker spaces |
| **PDMS Casting Demo** | DIY | <$100 | Sylgard 184, glass slides, biopsy punch, tubing | Hands-on fabrication intro |
