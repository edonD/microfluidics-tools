# Fluid Handling Equipment for Microfluidics

> Last updated: March 2026

## Syringe Pumps vs Pressure Controllers: When to Use Which

### Head-to-Head Comparison

| Factor | Syringe Pump | Pressure Controller |
|--------|-------------|-------------------|
| **Cost** | $1,500-8,000 | $5,000-20,000 |
| **Setup complexity** | Simple (plug and pump) | Medium (pressure source, reservoirs, software) |
| **Flow stability** | Good (some pulsation at low rates) | Excellent (truly pulseless) |
| **Response time** | Slow (seconds to minutes due to compliance) | Fast (milliseconds) |
| **Volume precision** | Excellent (exact volume delivery) | Medium (calculate from flow rate × time) |
| **Experiment duration** | Limited by syringe size | Hours to days (large reservoirs up to 1L) |
| **Pressure capability** | Very high (hundreds of bar possible) | Limited (typically <10 bar) |
| **Best for** | Precise volume delivery, high pressure, simple setups | Droplets, cell culture, fast optimization, automated sequences |
| **Optimization speed** | ~2 hours to stabilize after parameter change | ~10 minutes to optimize conditions |

**Bottom line:** Start with syringe pumps if budget-constrained or running simple experiments. Switch to pressure controllers for droplet generation, organ-on-chip, or any application requiring stable, pulseless flow and fast parameter changes.

---

## Syringe Pumps

### Commercial Syringe Pumps

| Pump | Vendor | Channels | Flow Range | Accuracy | Approx. Price | Notes |
|------|--------|----------|------------|----------|---------------|-------|
| **PHD ULTRA** | Harvard Apparatus | 1-10 syringes | 1.5 pL/min – 220 mL/min | ±0.25% | $5,000-8,000 | Industry standard. 4.3" touch screen, USB, RS-485. Reproducibility ±0.05%. Infuse/withdraw. |
| **PHD 2000** | Harvard Apparatus | 1-2 syringes | nL/min – mL/min | ±0.35% | $3,000-5,000 | Reliable workhorse. Widely cited in literature. |
| **neMESYS** | Cetoni | 1-12+ modules | fL/min – mL/min | ±0.02% | $8,000-20,000+ | Best precision available. Fully modular — each module independent. QmixElements software. |
| **neMESYS S** | Cetoni | 1 module | fL/min – mL/min | ±0.02% | $5,000-8,000 | Single module entry point to Cetoni ecosystem |
| **Legato 210P** | kdScientific | 2 syringes | pL/min – mL/min | ±0.5% | $2,000-4,000 | Good mid-range option |
| **Fusion 200** | Chemyx | 2 syringes | nL/min – mL/min | ±0.35% | $2,500-4,000 | Touchscreen, compact |
| **AL-1000/Aladdin** | World Precision Instruments | 1-2 syringes | µL/hr – mL/hr | ±0.5-1% | $1,500-3,500 | Budget option |

### Open-Source / DIY Syringe Pumps

| Project | Cost | Build Time | Features | Link |
|---------|------|------------|----------|------|
| **Poseidon** | ~$400 | ~1 hour | 3 pumps + microscope, 3D printed, Arduino | [github.com/pachterlab/poseidon](https://github.com/pachterlab/poseidon) |
| **Arduino Multichannel** | ~$200-400 | 2-4 hours | Arduino UNO + CNC shield + A4988 drivers | [ACS J. Chem. Ed. (2024)](https://pubs.acs.org/doi/10.1021/acs.jchemed.4c00033) |
| **Feedback-Controlled Pump** | ~$110 | 2-3 hours | PID pressure feedback, Arduino | [PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0175089) |
| **Wenzel Lab Pumps** | ~$300-500 | 2-4 hours | 3D printable, dual controller | [github.com/wenzel-lab](https://github.com/wenzel-lab/syringe-pumps-and-controller) |
| **OpenSyringePump** | ~$150-300 | 1-2 hours | Simplest design | [github.com/manimino/OpenSyringePump](https://github.com/manimino/OpenSyringePump) |

---

## Pressure Controllers

### Commercial Pressure Controllers

| Controller | Vendor | Channels | Pressure Range | Response Time | Approx. Price | Notes |
|-----------|--------|----------|---------------|---------------|---------------|-------|
| **OB1 MK4** | Elveflow | 1-4 | -900 mbar to 8 bar (per channel) | <10 ms | $8,000-18,000 | Piezoelectric regulators. Configurable per channel (200 mbar, 2 bar, 8 bar, vacuum). ESI software with sequencer. 100 Hz data logging. |
| **MFCS-EZ** | Fluigent | 4-8 | -800 mbar to 7 bar | <30 ms | $10,000-20,000 | FASTAB™ technology. Proven, reliable. |
| **Flow EZ** | Fluigent | 1 (modular) | -800 mbar to 7 bar | <30 ms | $3,000-6,000/module | Compact modular. Stack for more channels. |
| **LineUp** | Fluigent | Modular | Various | <30 ms | $8,000-25,000 | Next-gen modular platform |
| **Mitos P-Pump** | Dolomite | 1-4 | 0-10 bar | — | $5,000-10,000 | Integrated with Dolomite chip ecosystem |
| **AF1** | Elveflow | 1-4 | 0-2 bar | ~50 ms | $5,000-10,000 | Budget Elveflow option |
| **Push-Pull** | Fluigent | 2 | Bidirectional | <30 ms | $8,000-12,000 | Perfusion applications |

### Open-Source Pressure Controllers

| Project | Cost | Stability | Link |
|---------|------|-----------|------|
| **Piezo Pressure Controller** (2025) | ~$300-500 | ±0.2 mbar (10-500 mbar range) | [Biosensors 2025](https://pmc.ncbi.nlm.nih.gov/articles/PMC11940448/) |
| **Rio Controller** | ~$500-1,000 | Good | [github.com/wenzel-lab/rio-controller](https://github.com/wenzel-lab/rio-controller) |

---

## Flow Sensors

| Sensor | Vendor | Flow Range | Accuracy | Interface | Approx. Price | Notes |
|--------|--------|------------|----------|-----------|---------------|-------|
| **SLF3S-0600F** | Sensirion | 0-40 µL/min | ±5% | I2C digital | $50-100 | Excellent for DIY, Arduino-compatible |
| **SLF3S-1300F** | Sensirion | 0-500 µL/min | ±5% | I2C digital | $50-100 | Higher flow range |
| **SLF3S-4000B** | Sensirion | 0-40 mL/min | ±5% | I2C digital | $50-100 | High flow variant |
| **Flow Unit (S/M/L/XL)** | Fluigent | 0.07-5,000 µL/min | ±5% | Fluigent bus | $1,000-3,000 | Integrates with MFCS/LineUp for closed-loop control |
| **MFS Series** | Elveflow | 0.07-5,000 µL/min | ±5% | Elveflow bus | $1,000-3,000 | Integrates with OB1 for closed-loop |
| **BFS** | Elveflow | 0.04-7 µL/min | ±5% | Elveflow bus | $2,000-4,000 | Non-contact bubble-based sensor |

**Closed-loop flow control:** Combine a pressure controller (Elveflow or Fluigent) with their matching flow sensor for real-time PID flow rate control. The pressure controller adjusts pressure to maintain target flow rate regardless of fluidic resistance changes.

---

## Tubing

| Material | Common Sizes (OD × ID) | Max Pressure | Chemical Resistance | Transparency | Best For | Cost |
|----------|----------------------|-------------|--------------------|----|----|----|
| **Tygon (PVC)** | 1/16" × 0.010-0.030" | Low-Medium | Limited (no organics) | Translucent | Aqueous, general use | $15-30/25 ft |
| **PEEK** | 1/16" × 25-500 µm | Very High (>100 bar) | Excellent | Opaque (tan) | Solvents, HPLC, high pressure | $30-80/5 ft |
| **PTFE (Teflon)** | 1/16" × various | High | Excellent | Translucent | Chemical resistance | $15-40/10 ft |
| **FEP** | 1/16" × various | High | Excellent | Transparent | Optical observation | $20-50/10 ft |
| **Silicone** | Various | Low | Poor (absorbs) | Transparent | Gas-permeable cell culture | $10-25/25 ft |
| **ETFE** | 1/16" × various | High | Very good | Translucent | Balance of flexibility + resistance | $20-40/10 ft |
| **Fused silica** | 360 µm OD × 50-200 µm ID | Very High | Inert | Transparent | Smallest dead volumes, CE | $30-100/m |

### Selection Guide
- **Aqueous, low pressure:** Tygon or silicone (cheapest, easiest)
- **Organic solvents:** PEEK or PTFE (mandatory)
- **High pressure (>5 bar):** PEEK
- **Need to see the fluid:** FEP or fused silica
- **Cell culture:** Silicone (gas permeable) or PTFE (inert)
- **Minimum dead volume:** Fused silica capillary

---

## Connectors & Fittings

### IDEX Health & Science (Industry Standard)

IDEX (formerly Upchurch Scientific) makes the standard connectors for microfluidics. All NanoPort components use biocompatible PEEK polymer, Perlast® perfluoroelastomer gaskets, and ETFE ferrules.

| Product | Description | Price | Notes |
|---------|-------------|-------|-------|
| **NanoPort Assemblies** | Chip-to-tube connections (adhesive or clamped) | $30-80 each | Accepts 1/16", 1/32", 360 µm tubing. Gold standard for chip interfaces. |
| **10-32 Coned Fittings** | Standard threaded fittings | $3-10 each | PEEK. Fingertight or wrench-tight. |
| **Super Flangeless** | Low dead volume fittings | $5-15 each | Reusable PEEK ferrule |
| **MicroTight** | Ultra-low dead volume | $10-20 each | For capillary connections |
| **Unions/Connectors** | Tube-to-tube | $5-15 each | Zero dead volume options available |
| **Tees/Crosses** | Flow splitting/combining | $10-25 each | PEEK body, various bore sizes |

### Alternative Connection Methods

| Method | Cost | Pressure Limit | Reusable | Best For |
|--------|------|---------------|----------|----------|
| **Press-fit into PDMS** | $0 | ~0.5 bar | Yes | Quick prototyping, low pressure |
| **Luer-lock adapters** | $1-5 each | ~1-2 bar | Yes | PDMS devices, medical connectors |
| **Epoxy/UV adhesive** | $10-30/tube | High | No (permanent) | Permanent, strong bonds |
| **3D-printed connectors** | ~$1 each | ~1-3 bar | No | Integrated chip design |
| **O-ring chip holders** | $50-200 | High | Yes | Glass/silicon/thermoplastic chips |
| **Magnetic connectors** | $20-50 each | ~1 bar | Yes | Quick connect/disconnect |

---

## Chip Holders & World-to-Chip Interfaces

| Product | Vendor | Compatibility | Price | Notes |
|---------|--------|---------------|-------|-------|
| **H-Series Holders** | Dolomite | Dolomite chips | $200-500 | Snap-in, integrated connectors |
| **Fluidic Connect PRO** | Micronit | Micronit chips | $300-800 | Professional, reusable |
| **Custom CNC holders** | DIY/machine shop | Any chip format | $100-500 | Aluminum or PMMA, O-ring sealed |
| **3D-printed holders** | DIY | Any chip format | $5-20 | Quick prototyping |
| **Microscope stage inserts** | Various | Standard slides | $50-200 | For live imaging on microscope |

---

## Complete Setup Recommendations

### Budget Setup (<$1,000)
| Item | Cost |
|------|------|
| DIY Poseidon syringe pump (3 channels) | $400 |
| Tygon tubing (25 ft) | $20 |
| Luer-lock connectors (10-pack) | $20 |
| Press-fit into PDMS ports | $0 |
| **Total** | **~$440** |

### Research Setup ($5,000-$15,000)
| Item | Cost |
|------|------|
| Harvard PHD 2000 or Cetoni neMESYS base | $3,000-8,000 |
| Sensirion SLF3S flow sensor (×2) | $100-200 |
| PEEK tubing + IDEX fittings kit | $200-500 |
| NanoPort assemblies (×4) | $200-400 |
| Custom chip holder | $200-500 |
| **Total** | **$3,700-9,600** |

### Professional Setup ($15,000-$40,000)
| Item | Cost |
|------|------|
| Elveflow OB1 MK4 (4 channel) | $12,000-18,000 |
| Elveflow MFS flow sensors (×4) | $4,000-8,000 |
| PEEK tubing + full IDEX connector set | $500-1,000 |
| NanoPort assemblies + chip holder | $500-1,000 |
| Reservoir system (pressurized) | $200-500 |
| **Total** | **$17,200-28,500** |

---

## Vendors & Where to Buy

| Vendor | Specialty | Website |
|--------|-----------|---------|
| **Darwin Microfluidics** | One-stop shop reseller (pumps, controllers, chips, connectors) | [darwin-microfluidics.com](https://darwin-microfluidics.com) |
| **Elveflow** | Premium pressure controllers, flow sensors | [elveflow.com](https://elveflow.com) |
| **Fluigent** | Pressure controllers, modular flow systems | [fluigent.com](https://www.fluigent.com) |
| **Dolomite** | Integrated microfluidic systems, chips, pumps | [dolomite-microfluidics.com](https://www.dolomite-microfluidics.com) |
| **Harvard Apparatus** | Classic syringe pumps | [harvardapparatus.com](https://www.harvardapparatus.com) |
| **Cetoni** | Highest-precision syringe pumps | [cetoni.com](https://www.cetoni.com) |
| **IDEX Health & Science** | Connectors, fittings, tubing | [idex-hs.com](https://www.idex-hs.com) |
| **Cole-Parmer** | Tubing, general lab supplies | [coleparmer.com](https://www.coleparmer.com) |
| **Sensirion** | Low-cost digital flow sensors | [sensirion.com](https://www.sensirion.com) |
| **MSE Supplies** | Elveflow reseller (US) | [msesupplies.com](https://www.msesupplies.com) |
