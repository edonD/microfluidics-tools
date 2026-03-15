# Hot Embossing & Injection Molding for Microfluidics

> Last updated: March 2026

## Overview

Hot embossing and injection molding are the two dominant thermoplastic replication methods for microfluidic device fabrication. Hot embossing excels at prototyping and low-to-medium volumes with high fidelity, while injection molding is the workhorse for mass production at volumes exceeding ~10,000 units.

---

## 1. Hot Embossing

### What It Is

Hot embossing is a thermal imprinting process where a heated mold (stamp) is pressed into a thermoplastic substrate above its glass transition temperature (Tg), transferring micro- and nano-scale features. After cooling below Tg, the mold is separated (demolded) from the patterned substrate.

### Process Steps

1. **Load substrate** onto temperature-controlled platen
2. **Heat** substrate and/or mold above Tg of the polymer
3. **Apply pressure** (typically 50-250 bar) to emboss features
4. **Hold** at temperature and pressure for defined dwell time (1-10 min)
5. **Cool** below Tg while maintaining pressure
6. **Demold** — separate stamp from substrate (critical step)
7. **Bond** a lid layer to seal channels

### Key Process Parameters

| Parameter | Typical Range | Notes |
|-----------|--------------|-------|
| Embossing temperature | Tg + 20-80 deg C | Material-dependent |
| Embossing pressure | 50-250 bar | Higher for finer features |
| Dwell time | 1-10 min | Longer for complex geometries |
| Demolding temperature | 20-40 deg C below Tg | Critical for feature integrity |
| Total cycle time | 3-15 min typical | Up to 1 hour for large/complex parts |

#### Material-Specific Parameters

- **PMMA**: 180 deg C, 240 bar, 6 min embossing time
- **COP (Zeonor)**: 143 deg C, 1.6 MPa at cooling, 80 deg C demold, 2 min hold
- **COC (TOPAS 8007)**: ~100 deg C (Tg ~78 deg C), lower pressures possible

### Resolution and Feature Size

| Capability | Range |
|-----------|-------|
| Minimum feature size | Sub-100 nm (with appropriate mold) |
| Typical microfluidic features | 10-500 um channels |
| Aspect ratio | Up to 10:1 achievable |
| Replication fidelity | Excellent — sub-micron features routinely replicated |
| Area coverage | Up to 200 mm wafer scale |

### Equipment

#### Major Manufacturers

| Manufacturer | Model Series | Key Specifications | Approx. Price Range |
|-------------|-------------|-------------------|-------------------|
| **Jenoptik** | HEX 01, HEX 02, HEX 03, HEX 04 | Proprietary "Active De-Embossing Technology"; HEX 04 configured for high-throughput lab-on-chip; wafer-scale processing | $200K-$600K |
| **EV Group (EVG)** | EVG 520HE, EVG 750 | Feature replication down to 50 nm; integrated alignment for multilayer; automated systems available | $300K-$800K |
| **SUSS MicroTec** | Various NIL/embossing platforms | Combined lithography and embossing capability; wafer bonding integration | $250K-$700K |
| **Sublym** (Darwin Microfluidics) | Desktop embosser | Benchtop system for thermoplastics; lower cost entry point | $15K-$50K |

#### Budget/Research Options

| Option | Approx. Cost | Notes |
|--------|-------------|-------|
| Modified hydraulic press + hot plates | $2K-$10K | DIY approach, limited control |
| Sublym desktop embosser | $15K-$50K | Purpose-built for microfluidics prototyping |
| Used/refurbished EVG or Jenoptik | $50K-$150K | Check semiconductor equipment resellers |

### Pros and Cons

**Pros:**
- Excellent replication fidelity (sub-micron features)
- Low material waste (no sprues/runners)
- Low residual stress in replicated parts
- Suitable for prototyping through medium volume
- Wide material compatibility
- Same mold can be used for many materials

**Cons:**
- Slower cycle time than injection molding (3-15 min vs. seconds)
- Typically single-cavity (one part per cycle)
- Demolding can be challenging for high-aspect-ratio features
- Requires careful process optimization per material
- Not cost-effective above ~10,000 units

### Typical Lead Time

| Phase | Timeline |
|-------|----------|
| Mold fabrication (CNC milled) | 1-3 weeks |
| Mold fabrication (lithography + electroforming) | 3-6 weeks |
| Process optimization | 1-2 weeks |
| Embossing + bonding per batch | Hours to days |
| **Total prototype to first chips** | **2-6 weeks** |

---

## 2. Injection Molding

### What It Is

Injection molding forces molten polymer into a precision mold cavity under high pressure, producing net-shape parts with cycle times of seconds. For microfluidics, micro-injection molding uses specialized machines with precise shot control, often with variotherm (rapidly heated/cooled) mold temperature control to fill micro-features before the polymer solidifies.

### When Injection Molding Makes Sense

| Factor | Threshold |
|--------|----------|
| **Volume** | > 1,000 units (rapid tooling); > 10,000 units (production tooling) |
| **Per-unit cost target** | < $1-5 per chip |
| **Design stability** | Design should be locked — mold changes are expensive |
| **Cycle time requirement** | Seconds per part (vs. minutes for embossing) |
| **Regulatory pathway** | IVD/medical device requiring validated manufacturing |

### Minimum Order Quantities (MOQs)

| Tooling Approach | Typical MOQ | Mold Cost | Per-Part Cost |
|-----------------|-------------|-----------|---------------|
| **Rapid tooling** (aluminum molds, Proto Labs-style) | 25-500 parts | $2,000-$5,000 | $5-$50 |
| **Bridge tooling** (soft steel, single cavity) | 500-5,000 parts | $10,000-$30,000 | $2-$10 |
| **Production tooling** (hardened steel, multi-cavity) | 10,000-100,000+ | $30,000-$100,000+ | $0.30-$2 |
| **High-volume production** (multi-cavity, automated) | 100,000+ | $50,000-$200,000+ | $0.10-$0.50 |

### Resolution and Feature Size

| Capability | Range |
|-----------|-------|
| Minimum feature size | ~1-5 um (with variotherm and vacuum) |
| Standard microfluidic channels | 50-500 um |
| Aspect ratio | Up to ~5:1 typical; higher with special techniques |
| Part-to-part variation | < 1% (production tooling) |
| Surface roughness | Ra < 50 nm (polished mold) |

### Equipment

Micro-injection molding machines differ from standard injection molding in their precision shot control, clamping force, and mold temperature management.

| Manufacturer | Model | Key Feature |
|-------------|-------|-------------|
| **Wittmann Battenfeld** | MicroPower series | 5-15 ton, dedicated micro-molding |
| **ENGEL** | e-motion / victory series | All-electric precision, variotherm capable |
| **Arburg** | Allrounder micro | Micro-injection unit, 0.05 cm3 min shot |
| **Sumitomo (SHI) Demag** | IntElect series | All-electric, high repeatability |
| **Sodick** | LP20EH2 | Specialized for micro/nano features |

Equipment cost: $150K-$500K+ for micro-injection molding machines.

### Pros and Cons

**Pros:**
- Very low per-part cost at volume (< $1/chip)
- Fast cycle times (10-60 seconds)
- Highly repeatable and automatable
- Multi-cavity molds for parallel production
- Established supply chain and quality systems
- Compatible with medical device manufacturing (ISO 13485)

**Cons:**
- High upfront tooling cost ($10K-$200K+)
- Long tooling lead times (4-12 weeks)
- Design changes require new/modified tooling
- Feature fidelity slightly lower than hot embossing for sub-micron
- Gate/runner/ejector marks on parts
- Requires injection molding expertise

### Typical Lead Time

| Phase | Timeline |
|-------|----------|
| Rapid tooling (aluminum) | 1-3 weeks |
| Production tooling (steel) | 6-12 weeks |
| First article inspection | 1-2 weeks |
| Production run | Days to weeks depending on volume |
| **Total (rapid)** | **2-4 weeks** |
| **Total (production)** | **8-16 weeks** |

---

## 3. Materials for Embossing & Injection Molding

### Cyclic Olefin Polymers (COC/COP)

These are the premium thermoplastic materials for microfluidics, offering optical clarity rivaling glass with excellent chemical resistance.

#### COC — Cyclic Olefin Copolymer

| Property | TOPAS 5013 | TOPAS 8007 | TOPAS 6013 |
|----------|-----------|-----------|-----------|
| Manufacturer | TOPAS Advanced Polymers | TOPAS Advanced Polymers | TOPAS Advanced Polymers |
| Tg | 134 deg C | 78 deg C | 138 deg C |
| Optical transmittance (visible) | >91% | >91% | >91% |
| UV transparency | Good (down to ~300 nm) | Good | Good |
| Water absorption (24h) | <0.01% | <0.01% | <0.01% |
| Chemical resistance | Good to polar solvents, acids, bases | Good | Good |
| Autofluorescence | Very low | Very low | Very low |
| Notes | Workhorse grade | Lower Tg, easier processing, more optically transparent, easier demolding | Higher Tg for demanding applications |

#### COP — Cyclic Olefin Polymer

| Property | Zeonor 1060R | Zeonex 480R | Zeonex 690R |
|----------|-------------|-------------|-------------|
| Manufacturer | Zeon | Zeon | Zeon |
| Tg | 100 deg C | 138 deg C | 136 deg C |
| Optical transmittance | >92% | >92% | >92% |
| Water absorption | <0.01% | <0.01% | <0.01% |
| Birefringence | Very low | Very low | Very low |
| Chemical resistance | Excellent to polar solvents | Excellent | Excellent |
| Notes | Easy processing | High Tg, optical grade | Injection molding optimized |

**COC vs. COP key differences:**
- COC (TOPAS) is a copolymer of ethylene and norbornene — tunable Tg by varying norbornene content
- COP (Zeonor/Zeonex) is made by ring-opening metathesis polymerization of cyclic monomers followed by hydrogenation
- Both attacked by non-polar solvents (toluene, hexane)
- Both have outstanding low water absorption and water vapor permeability
- COP tends to have slightly better optical properties; COC offers more Tg grades

#### Other Common Materials

| Material | Tg (deg C) | Pros | Cons | Best For |
|----------|-----------|------|------|----------|
| **PMMA** (acrylic) | 105 | Low cost, good optical clarity, easy to bond, well-characterized | Poor solvent resistance, absorbs water, higher autofluorescence than COC | Prototyping, academic research, disposables |
| **Polystyrene (PS)** | 100 | Very low cost, cell culture standard, good optical properties | Brittle, limited chemical resistance | Cell-based assays (biologists familiar with it) |
| **Polycarbonate (PC)** | 150 | High Tg, tough, good thermal stability | High autofluorescence, poor UV transmission, absorbs water | High-temperature applications, robust devices |
| **PEEK** | 143 | Extreme chemical resistance, high temperature | Opaque, expensive, difficult to process | Chemical reactors, harsh environments |

### Material Selection Guide

```
Need optical detection (fluorescence)?
  ├─ Yes → COC/COP (lowest autofluorescence) or PMMA (good, lower cost)
  └─ No  → PS (cheapest) or PC (toughest)

Need solvent resistance?
  ├─ Polar solvents → COC/COP (excellent) or PMMA (moderate)
  └─ Non-polar solvents → None of the above — consider glass or fluoropolymers

Need UV transparency (< 350 nm)?
  ├─ Yes → COC/COP (best polymer option) or quartz glass
  └─ No  → Any of the above

Need lowest cost per unit?
  ├─ Yes → PS or PMMA
  └─ No  → COC/COP for performance

Need cell culture compatibility?
  ├─ Standard culture → PS (industry standard surface treatments available)
  └─ Custom surface → COC/COP (surface modification possible)
```

---

## 4. Mold Fabrication Methods

The mold (stamp, tool insert) is the critical component determining feature quality, resolution, and cost.

### CNC Micromilling

| Attribute | Details |
|-----------|---------|
| **Process** | Rotating micro-endmills (down to 10 um diameter) cut material from metal blank |
| **Mold materials** | Aluminum (prototyping), brass, steel, nickel alloys |
| **Minimum feature** | ~20-50 um (limited by endmill diameter) |
| **Surface roughness** | Ra 50-200 nm typical; can be improved by polishing |
| **Aspect ratio** | Limited to ~3:1 by tool deflection |
| **Cost** | $500-$5,000 for prototype mold; $3,000-$15,000 for production insert |
| **Lead time** | 1-5 days for simple molds |
| **Advantages** | Fast turnaround, widely accessible, iterative design changes easy, no cleanroom needed |
| **Limitations** | Minimum feature size ~20 um, tool marks on surface, limited aspect ratio |

### EDM (Electrical Discharge Machining)

| Attribute | Details |
|-----------|---------|
| **Process** | Spark erosion removes material; wire-EDM for through-cuts, sinker-EDM for cavities |
| **Mold materials** | Any conductive metal (hardened steel, tungsten carbide) |
| **Minimum feature** | ~10-25 um |
| **Surface roughness** | Ra 100-500 nm (can be polished) |
| **Aspect ratio** | Up to 20:1 or higher |
| **Cost** | $5,000-$30,000 for microfluidic inserts |
| **Lead time** | 1-4 weeks |
| **Advantages** | Machines hardened materials, high aspect ratio, no cutting forces |
| **Limitations** | Slow, electrode wear, surface finish requires post-polishing |

### Electroforming (Nickel)

| Attribute | Details |
|-----------|---------|
| **Process** | Electrodeposition of nickel onto a patterned master (typically SU-8 on silicon); master is sacrificed |
| **Mold materials** | Nickel (Ni), nickel-cobalt (NiCo) |
| **Minimum feature** | Sub-micron (limited by master quality) |
| **Surface roughness** | Replicates master — Ra < 10 nm possible |
| **Aspect ratio** | Up to 10:1 |
| **Thickness** | 0.3-3 mm nickel shim |
| **Cost** | $3,000-$20,000 (includes master fabrication) |
| **Lead time** | 2-6 weeks |
| **Advantages** | Excellent surface finish, sub-micron features, directly compatible with injection molding |
| **Limitations** | Requires cleanroom for master, shim fragility, slower iteration |

### LIGA (Lithographie, Galvanoformung, Abformung)

| Attribute | Details |
|-----------|---------|
| **Process** | Deep X-ray (synchrotron) or UV lithography of thick resist (PMMA or SU-8), followed by electroforming and replication |
| **Mold materials** | Nickel, nickel alloys |
| **Minimum feature** | < 1 um |
| **Surface roughness** | Ra < 10 nm |
| **Aspect ratio** | Up to 100:1 (X-ray LIGA); up to 20:1 (UV-LIGA) |
| **Cost** | $20,000-$100,000+ (X-ray LIGA requires synchrotron access) |
| **Lead time** | 4-12 weeks |
| **Advantages** | Highest aspect ratio and precision of any mold technique |
| **Limitations** | Extremely expensive, limited synchrotron access (X-ray LIGA), slow |

### UV-LIGA (SU-8 based)

A more accessible variant of LIGA using UV lithography instead of synchrotron X-rays:

| Attribute | Details |
|-----------|---------|
| **Process** | UV lithography of SU-8 photoresist (up to 1 mm thick), followed by nickel electroforming |
| **Minimum feature** | ~2-5 um |
| **Aspect ratio** | Up to 20:1 |
| **Cost** | $3,000-$15,000 |
| **Lead time** | 2-4 weeks |
| **Advantages** | No synchrotron needed, good aspect ratio, established process |
| **Limitations** | Requires cleanroom, SU-8 master fragile |

### Mold Method Selection Guide

| Need | Recommended Method |
|------|--------------------|
| Fastest prototype mold | CNC micromilling |
| Features < 20 um | Electroforming or UV-LIGA |
| Hardened steel production mold | EDM + CNC + polishing |
| Extreme aspect ratio (>20:1) | X-ray LIGA |
| Sub-micron features | Electroforming from e-beam master |
| Lowest cost | CNC micromilling (aluminum) |

---

## 5. Cost Comparison: Prototype vs. Production

### Cost Model Summary

| Volume | Tooling Method | Mold Cost | Per-Part Cost | Total Cost (per unit) | Best Approach |
|--------|---------------|-----------|---------------|----------------------|---------------|
| 1-10 | CNC-milled mold + hot embossing | $500-$2,000 | $50-$200 | $100-$500 | Hot embossing |
| 10-100 | CNC-milled mold + hot embossing | $1,000-$3,000 | $20-$50 | $30-$80 | Hot embossing |
| 100-1,000 | Rapid injection mold (aluminum) | $2,000-$5,000 | $5-$20 | $7-$25 | Rapid injection molding |
| 1,000-10,000 | Bridge tooling (soft steel) | $10,000-$30,000 | $2-$10 | $3-$13 | Injection molding |
| 10,000-100,000 | Production tooling (hardened steel) | $30,000-$100,000 | $0.50-$2 | $0.80-$3 | Injection molding |
| 100,000+ | Multi-cavity production mold | $50,000-$200,000 | $0.10-$0.50 | $0.15-$0.60 | Injection molding |

### Breakeven Analysis

The crossover point where injection molding becomes cheaper than hot embossing is typically around **1,000-5,000 units**, depending on part complexity and tooling investment.

```
Cost per part ($)
100 |\ Hot embossing
    | \
 50 |  \___________
    |      \
 10 |       \ ← Crossover (~1,000-5,000 units)
  5 |        \_____
  1 |              \_____ Injection molding
0.1 |                    \____________
    |________________________________
    1    100   1K   10K  100K   1M
              Volume (units)
```

### Hidden Costs to Budget For

- **Bonding/sealing**: Thermal, solvent, adhesive, or ultrasonic — adds $0.50-$5/chip
- **Surface treatment**: Plasma activation, coatings — $0.10-$2/chip
- **Quality control**: Optical inspection, leak testing — $0.50-$5/chip
- **Packaging**: Cleanroom packaging for medical devices — $0.20-$2/chip
- **Design iteration**: Each mold revision costs $1,000-$50,000+

---

## 6. Contract Manufacturers

### Major Microfluidic Contract Manufacturers

| Company | Location | Capabilities | Volume Range | Materials | Notes |
|---------|----------|-------------|--------------|-----------|-------|
| **Microfluidic ChipShop** | Jena, Germany | Hot embossing, injection molding, standard chip catalog, custom design, assembly | Prototype to high volume | COC, COP, PMMA, PS, PC | Largest catalog of standard microfluidic chips; full custom fabrication; design support |
| **Stratec (formerly STRATEC Consumables)** | Anif, Austria & Birkenfeld, Germany | Injection molding, assembly, surface treatment, bonding | Medium to high volume (10K+) | COC, COP, PS, PMMA | Focus on IVD consumables; ISO 13485 certified; automated assembly lines |
| **thinXXS Microtechnology** | Zweibrucken, Germany | Injection molding, hot embossing, thermal/UV bonding, reagent deposition | Prototype to large-scale production | COC, COP, PMMA, PS | Contract development and manufacturing; biomedical focus; design-to-production support |
| **Micronit** | Enschede, Netherlands | Glass, silicon, and polymer microfluidics; etching, bonding, laser processing | Prototype to high volume | Glass, silicon, COC, COP, PMMA | Strong in glass/silicon alongside polymer; ISO 9001 & ISO 13485; design services |

### Other Notable Manufacturers

| Company | Location | Specialty |
|---------|----------|-----------|
| **Dolomite** (Blacktrace) | Royston, UK | Glass and polymer chips, droplet systems |
| **Enplas** | Japan/US | Injection molded consumables, optics-grade |
| **Potomac Photonics** | Baltimore, USA | Laser processing, hot embossing, hybrid |
| **uFluidix** | Toronto, Canada | PDMS and polymer prototyping to production |
| **ALine** | Rancho Dominguez, USA | Laminated polymer microfluidics |
| **Proto Labs** | Maple Plain, USA | Rapid injection molding (not micro-specialized but fast) |
| **Natech Plastics** | Ronkonkoma, USA | Micro-injection molding for microfluidics |

### What to Expect from Contract Manufacturers

| Service Phase | Typical Timeline | Typical Cost |
|--------------|-----------------|-------------|
| Design review / DFM | 1-2 weeks | Free - $5K |
| Prototype tooling + first articles | 4-8 weeks | $5K-$30K |
| Process validation (IQ/OQ/PQ) | 4-8 weeks | $10K-$50K |
| Production ramp | 2-4 weeks | Volume-dependent |
| Ongoing production | Per schedule | $0.50-$10/chip depending on complexity and volume |

### Selection Criteria for Contract Manufacturers

1. **Materials expertise** — Do they routinely process your chosen polymer?
2. **Feature size capability** — Can they achieve your required resolution?
3. **Quality systems** — ISO 13485 for medical/IVD, ISO 9001 minimum
4. **Volume flexibility** — Can they scale from prototype to production?
5. **Secondary operations** — Bonding, surface treatment, reagent deposition, assembly
6. **Geographic proximity** — Shipping, communication, site visits
7. **IP protection** — NDA terms, data security
8. **Design support** — DFM (Design for Manufacturing) feedback

---

## 7. Bonding Methods for Sealed Channels

After embossing or molding, channels must be sealed with a lid layer.

| Method | Temperature | Bond Strength | Advantages | Disadvantages |
|--------|------------|---------------|------------|---------------|
| **Thermal bonding** | Near Tg | Moderate-High | No adhesives, biocompatible | Risk of channel deformation |
| **Solvent bonding** | Room temp | High | Low temperature, strong | Solvent compatibility, fumes, channel clogging risk |
| **UV adhesive** | Room temp | High | Low temperature, selective | Adhesive biocompatibility, channel blockage |
| **Ultrasonic welding** | Local heating | High | Fast (< 1 sec), no consumables | Requires energy directors, localized damage |
| **Laser welding** | Local heating | Moderate-High | Selective, no contact | Requires absorber layer or transmission welding |
| **Pressure-sensitive adhesive (PSA)** | Room temp | Low-Moderate | Simple, fast, no equipment | Lower bond strength, adhesive interaction with fluids |

---

## References and Sources

- [Microfluidic ChipShop — Fabrication Services](https://www.microfluidic-chipshop.com/content/19-fabrication-services)
- [Microfluidic ChipShop — Polymers in Microfluidics](https://www.microfluidic-chipshop.com/microfluidics/materials-in-microfluidics/polymers-in-microfluidics/)
- [EV Group — Hot Embossing Systems](https://www.evgroup.com/products/nanoimprint-lithography/hot-embossing/)
- [Micronit — Manufacturing](https://www.micronit.com/working-together/from-idea-to-product/manufacturing)
- [thinXXS — What We Do](https://www.thinxxs.com/en/what-we-do)
- [Fundamentals of Rapid Injection Molding for Microfluidic Cell-Based Assays (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5790604/)
- [Fabrication Methods for Microfluidic Devices: An Overview (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8002879/)
- [Cyclic Olefin Polymers: Emerging Materials for Lab-on-a-Chip Applications (Springer)](https://link.springer.com/article/10.1007/s10404-010-0605-4)
- [A Review of COC Applications in Microfluidics (Wiley)](https://onlinelibrary.wiley.com/doi/full/10.1002/mame.202200053)
- [Ultra-Precise Molds Energize the Microfluidics Market (MoldMaking Technology)](https://www.moldmakingtechnology.com/articles/ultra-precise-molds-energize-the-microfluidics-market)
- [Micromilling for Ultra-Rapid Prototyping (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4439323/)
- [Microfluidics Hub — Hot Embossing](https://www.microfluidicshub.eu/manufacturing/hot-embossing)
- [Ultra-Precision Mass Production for Microfluidics (Medical Micro Molding)](https://www.medicalmicromolding.com/ultra-precision-mass-production-for-microfluidics-devices/)
- [Parallel Fluidics — Manufacturing Basics](https://www.parallelfluidics.com/resources/knowledge-base/manufacturing-basics-for-microfluidic-devices)
- [Elveflow — Microfluidic Foundries](https://www.elveflow.com/microfluidics-research-horizon-europe/industrial-partner/microfluidic-foundries/)
