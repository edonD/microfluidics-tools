# Cost Analysis: Microfluidics Design & Fabrication

> Last updated: March 2026

## Software Licensing Costs

### Simulation Software

| Software | License Type | Approximate Cost | Notes |
|----------|-------------|-----------------|-------|
| **COMSOL Multiphysics** (base) | Perpetual | ~$7,000-$9,000 | Academic pricing significantly lower (~$1,700 CPU single-user) |
| COMSOL Microfluidics Module | Add-on | ~$1,500-$4,000 | Requires base license |
| COMSOL Annual License | Yearly | ~50% of perpetual | Includes updates |
| COMSOL Maintenance Renewal | Annual | ~20% of perpetual | After first year |
| **ANSYS Fluent** | Annual | ~$20,000-$40,000/yr | Single-user commercial. Academic bundles much cheaper |
| ANSYS Academic Research | Annual | ~$5,000-$15,000/yr | Reduced capability vs commercial |
| ANSYS Student | Free | $0 | Limited mesh size, non-commercial |
| **SimScale** | Cloud (Free) | $0 | Community plan: limited compute hours |
| SimScale | Cloud (Pro) | ~$2,000-$5,000/yr | More compute, private projects |
| SimScale | Cloud (Enterprise) | Custom | Unlimited, priority support |
| **OpenFOAM** | Open source | $0 | Free forever. Steep learning curve. |
| **Elmer FEM** | Open source | $0 | Free. Capable but less polished. |
| **FEniCS** | Open source | $0 | Python-based FEM. Excellent for custom problems. |
| **FiPy** | Open source | $0 | Python finite volume for diffusion/transport |
| **Flow-3D** | Perpetual | ~$20,000-$50,000 | Specialized free-surface/microfluidic CFD |
| **Star-CCM+ (Simcenter)** | Annual | ~$15,000-$30,000/yr | Siemens. Generally overkill for microfluidics. |

### CAD Software

| Software | License Type | Approximate Cost | Notes |
|----------|-------------|-----------------|-------|
| **AutoCAD** | Annual | ~$1,900/yr | 2D design, simple channel layouts |
| AutoCAD | Student | $0 | Free for students |
| **SolidWorks** | Annual | ~$4,000-$8,000/yr | 3D CAD, mold design. Academic: ~$100-$500/yr |
| **Fusion 360** | Free (personal) | $0 | Limited features |
| Fusion 360 | Commercial | ~$545/yr | Good for 3D chip/mold design |
| **L-Edit (Siemens)** | Annual | ~$5,000-$15,000/yr | MEMS/microfluidic mask layout |
| **KLayout** | Open source | $0 | GDSII/OASIS viewer and editor |
| **CleWin** | License | ~$2,000-$5,000 | Mask layout (older, less common now) |
| **gdstk/GDSPY** | Open source | $0 | Python scripted mask layouts |
| **FreeCAD** | Open source | $0 | 3D parametric CAD |
| **Onshape** | Free (public) | $0 | Cloud CAD, designs are public |
| Onshape | Pro | ~$1,500/yr | Private designs |
| **3DuF** | Open source | $0 | Browser-based microfluidic design |

### Open-Source Alternatives Summary

| Paid Tool | Free Alternative | Trade-offs |
|-----------|-----------------|------------|
| COMSOL | OpenFOAM + FEniCS | Steeper learning curve, no GUI (OpenFOAM has ParaView) |
| ANSYS Fluent | OpenFOAM | More setup work, but comparable physics |
| SimScale | OpenFOAM on cloud (AWS/GCP) | Need to set up your own environment |
| AutoCAD | FreeCAD, LibreCAD | Less polished, fewer industry templates |
| SolidWorks | FreeCAD, Fusion 360 (free tier) | FreeCAD less stable, Fusion 360 limited |
| L-Edit | KLayout + gdstk | Excellent for mask layout, missing some MEMS-specific features |

---

## Fabrication Cost Comparison

### Per-Chip Costs by Method (Typical Single-Layer Device)

| Method | Prototype (1-10 chips) | Small Batch (10-100) | Medium (100-1000) | Production (1000+) | Min Feature Size |
|--------|----------------------|---------------------|-------------------|-------------------|-----------------|
| **PDMS Soft Lithography** | $50-200/chip* | $5-20/chip | $2-10/chip | Not practical | ~5 µm |
| **3D Printing (SLA)** | $5-50/chip | $3-20/chip | $2-10/chip | Not practical | ~50-200 µm |
| **3D Printing (2PP/Nanoscribe)** | $200-1000/chip | $100-500/chip | Not practical | Not practical | <1 µm |
| **Laser Cut (PMMA/acrylic)** | $10-50/chip | $5-20/chip | $2-10/chip | $1-5/chip | ~100-200 µm |
| **Hot Embossing** | N/A (need mold) | $20-50/chip | $5-15/chip | $1-5/chip | ~1-5 µm |
| **Injection Molding** | N/A (need mold) | N/A | $5-20/chip | $0.50-5/chip | ~1-5 µm |
| **Glass Wet Etch** | $100-500/chip | $50-200/chip | $20-100/chip | $10-50/chip | ~1-5 µm |
| **Silicon DRIE** | $200-1000/chip | $100-500/chip | $50-200/chip | $20-100/chip | <1 µm |

*PDMS per-chip cost is low (~$1 material), but requires SU-8 mold ($200-2000 for mold fabrication)

### Upfront Tooling/Mold Costs

| Method | Tooling Cost | Lead Time | Reusability |
|--------|-------------|-----------|-------------|
| **SU-8 Master Mold** (for PDMS) | $200-2,000 | 1-3 days | 50-200+ castings |
| **Chrome Photomask** | $200-800 per mask | 1-2 weeks | Indefinite |
| **Film Photomask** | $50-200 per mask | 2-5 days | Limited (degrades) |
| **CNC Mold** (for embossing) | $2,000-20,000 | 1-4 weeks | 10,000+ parts |
| **Injection Mold** | $10,000-100,000 | 4-12 weeks | 100,000+ parts |
| **Electroformed Mold** (LIGA) | $5,000-50,000 | 4-8 weeks | 10,000+ parts |

---

## Equipment Costs

### Essential Lab Equipment

| Equipment | Budget Option | Mid-Range | High-End | Notes |
|-----------|--------------|-----------|----------|-------|
| **Syringe Pump** | DIY/Poseidon (~$400) | kdScientific ($1,500-3,000) | Harvard PHD Ultra ($5,000-8,000) | Open-source options very capable |
| **Pressure Controller** | DIY Arduino (~$110-400) | Elveflow OB1 ($8,000-15,000) | Fluigent LineUp ($10,000-20,000) | Pressure control superior for steady flow |
| **Microscope (inverted)** | Used Nikon/Olympus ($2,000-5,000) | Nikon Ti2-U ($15,000-30,000) | Zeiss Axio Observer ($30,000-60,000) | Inverted preferred for microfluidics |
| **Plasma Cleaner** | Harrick PDC-32G (~$5,000) | Diener Zepto ($8,000-15,000) | — | Essential for PDMS bonding |
| **Hot Plate** | Lab hot plate ($200-500) | Programmable ($500-2,000) | — | For PDMS curing, bonding |
| **Spin Coater** | Laurell WS-650 ($3,000-5,000) | SUSS MicroTec ($10,000+) | — | For photoresist coating |
| **Vacuum Desiccator** | Basic ($100-300) | With pump ($500-1,500) | — | PDMS degassing |

### Cleanroom Equipment (if building capability)

| Equipment | Approximate Cost | Notes |
|-----------|-----------------|-------|
| **Mask Aligner** (used) | $20,000-80,000 | SUSS MA6 is workhorse |
| **Mask Aligner** (new) | $80,000-300,000 | SUSS MA/BA Gen4 |
| **Maskless Aligner** | $200,000-500,000 | Heidelberg MLA150 |
| **DRIE System** | $500,000-1,500,000 | Oxford, SPTS, Plasma-Therm |
| **E-beam Evaporator** | $100,000-500,000 | For metal deposition |
| **Sputter Coater** | $50,000-200,000 | Kurt Lesker, AJA |
| **Profilometer** | $30,000-100,000 | Dektak, KLA |
| **SEM** | $100,000-500,000 | For characterization |

### Flow Characterization Equipment

| Equipment | Approximate Cost | Notes |
|-----------|-----------------|-------|
| **Micro-PIV System** | $80,000-200,000+ | TSI, Dantec, LaVision |
| **High-Speed Camera** | $20,000-100,000+ | Phantom, Photron, Chronos |
| **Flow Sensors** | $500-3,000 each | Sensirion, Fluigent |
| **Pressure Sensors** | $200-2,000 each | Honeywell, Sensata |
| **Fluorescence Filter Sets** | $500-2,000/set | For flow visualization |

---

## Outsourcing / Foundry Services

### Microfluidic Foundries & Contract Manufacturers

| Company | Location | Specialty | Typical Pricing | Lead Time |
|---------|----------|-----------|----------------|-----------|
| **uFluidix** | Toronto, Canada | PDMS, glass, thermoplastic | ~$60/chip (100 qty example) | ~2 weeks |
| **Microfluidic ChipShop** | Jena, Germany | Injection molding, thermoplastics (COC, COP, PMMA) | Custom quote | 4-12 weeks |
| **Micronit** | Enschede, Netherlands | Glass, silicon, polymer, hybrid | Custom quote (premium) | 4-16 weeks |
| **Dolomite** | Royston, UK | Glass chips, standard designs available | $50-500/chip (standard) | 1-4 weeks (standard) |
| **Vantiva** (formerly Technicolor) | France | High-volume polymer microfluidics | Custom quote | Production: 8-16 weeks |
| **Blackhole Lab** | France | PDMS soft lithography | Custom quote | 1-4 weeks |
| **WenHao** | China | Custom microfluidic chips, mass production | Lower cost, custom quote | 2-6 weeks |
| **Alfa Chemistry Microfluidics** | USA/China | Various materials, prototyping to production | Custom quote | Varies |
| **CMC Microsystems** | Canada | Academic prototyping, multi-project wafers | Subsidized for Canadian academics | Varies |
| **Goodfellow** | UK | Custom microfabrication services | Custom quote | Varies |

### What to Expect When Outsourcing

| Volume | Best Approach | Typical Cost Range | Lead Time |
|--------|--------------|-------------------|-----------|
| 1-10 prototypes | PDMS/3D print in-house or uFluidix | $200-2,000 total | 1-3 weeks |
| 10-100 devices | PDMS foundry or 3D printing service | $500-6,000 total | 2-4 weeks |
| 100-1,000 devices | Hot embossing or early injection molding | $5,000-30,000 total | 4-8 weeks |
| 1,000-10,000 | Injection molding | $10,000-50,000 total | 8-16 weeks |
| 10,000+ | Injection molding (amortized tooling) | $0.50-5/chip | Ongoing production |

---

## Total Project Cost Estimates

### Scenario A: Academic Proof-of-Concept ($500-2,000)

| Item | Cost |
|------|------|
| CAD software (free: Fusion 360, KLayout) | $0 |
| Simulation (OpenFOAM or COMSOL via university license) | $0 |
| SU-8 mold (university cleanroom) | $100-500 |
| PDMS + glass slides | $50-100 |
| Syringe pump (DIY Poseidon) | $400 |
| Tubing and connectors | $50-200 |
| **Total** | **$600-1,200** |

### Scenario B: Research Lab Setup ($20,000-$80,000)

| Item | Cost |
|------|------|
| COMSOL + Microfluidics Module (academic) | $3,000-6,000/yr |
| SolidWorks or Fusion 360 | $500-4,000/yr |
| Syringe pump (Harvard/Cetoni) | $5,000-15,000 |
| Pressure controller (Elveflow OB1) | $8,000-15,000 |
| Plasma cleaner (Harrick) | $5,000 |
| Inverted microscope (used) | $5,000-15,000 |
| Cleanroom access fees | $2,000-10,000/yr |
| Consumables (PDMS, photoresist, masks) | $2,000-5,000/yr |
| **Total first year** | **$30,000-75,000** |

### Scenario C: Product Development ($100,000-$500,000)

| Item | Cost |
|------|------|
| Full simulation suite (COMSOL commercial) | $15,000-30,000 |
| CAD (SolidWorks Professional) | $4,000-8,000/yr |
| Prototype fabrication (PDMS, iterations) | $5,000-20,000 |
| Injection mold tooling | $20,000-100,000 |
| Pilot production run (1,000-10,000 chips) | $10,000-50,000 |
| Testing equipment | $20,000-80,000 |
| Contract foundry services | $10,000-50,000 |
| Regulatory/quality (ISO 13485 if medical) | $20,000-100,000 |
| **Total** | **$100,000-440,000** |

---

## Cost-Saving Tips

1. **Use university cleanrooms** — shared user fees are 10-100x cheaper than building your own
2. **Start with PDMS** — cheapest prototyping material, extensive literature
3. **Use film masks first** — $50-200 vs $200-800 for chrome. Good enough for features >10 µm
4. **Open-source simulation** — OpenFOAM + FEniCS cover 80% of needs at $0
5. **DIY syringe pumps** — Poseidon and Arduino-based designs are research-grade at 1/10 the cost
6. **Multi-project wafers** — CMC Microsystems (Canada) and similar programs share fabrication costs
7. **Order standard chips** — Dolomite and Microfluidic ChipShop have off-the-shelf designs for common applications
8. **3D print prototypes first** — Validate geometry before committing to lithography
9. **Negotiate academic licenses** — Most vendors offer 50-80% discounts for academic use
10. **Buy used equipment** — eBay, LabX, and BioSurplus for microscopes, pumps, and cleanroom equipment
