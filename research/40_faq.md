# Microfluidics FAQ — Frequently Asked Questions

> Last updated: March 2026

## Getting Started

**Q: I'm new to microfluidics. Where do I start?**
Start with Tabeling's "Introduction to Microfluidics" textbook, then try the free NPTEL online courses. For hands-on experience, build a simple PDMS chip using soft lithography (if you have cleanroom access) or order a starter kit from LabSmith or Dolomite. See [Learning Resources](12_learning_resources.md) for detailed recommendations.

**Q: What's the minimum budget to get started?**
- DIY/student: ~$500 (Poseidon syringe pump + PDMS + tubing)
- Serious prototyping: ~$2,000-5,000 (proper pump + cleanroom access)
- Full research lab: ~$30,000-80,000 (pressure controller + microscope + simulation software)
See [Cost Analysis](11_cost_analysis.md) and [Workflows](10_workflows.md).

**Q: Do I need a cleanroom?**
Not necessarily. You can:
- 3D print chips (no cleanroom needed, ~200 µm resolution)
- Use dry film resist instead of SU-8 (can laminate on bench)
- Use xurography (vinyl cutter + adhesive tape)
- Order chips from foundries (uFluidix, Dolomite)
A cleanroom is needed for: photolithography with SU-8, metal deposition, DRIE etching.

**Q: What software should I learn first?**
1. **CAD:** Fusion 360 (free, 3D) or KLayout (free, 2D mask layout)
2. **Simulation:** COMSOL (if university provides) or SimScale (free tier)
3. **Analysis:** ImageJ (free) for image measurements
4. **Automation:** Python with vendor SDKs

---

## Design

**Q: What channel dimensions should I use?**
Good starting point: 100 µm wide × 50 µm tall. See [Design Rules](16_practical_tips.md) and [Design Patterns](38_design_patterns.md) for specific applications.

**Q: How do I design a mixer?**
For Re < 1: use a staggered herringbone mixer (SHM) — 95%+ mixing efficiency in ~10 mm length. For simpler fabrication, use a serpentine with 10+ turns. See [Design Patterns](38_design_patterns.md).

**Q: How do I generate droplets?**
Use a flow-focusing or T-junction geometry. Channel width ~50 µm, height ~50 µm. Oil phase: HFE-7500 + 2% PFPE-PEG surfactant. Start with 5:1 oil-to-water flow rate ratio. See [Advanced Techniques](17_advanced_techniques.md).

**Q: What file format do I need for fabrication?**
- Chrome mask: GDSII (.gds) or CIF
- Film mask: High-resolution PDF or DXF (20,000+ DPI)
- 3D printing: STL or OBJ
- Laser cutting: DXF or AI
- Injection molding: STEP or IGES

---

## Simulation

**Q: COMSOL or OpenFOAM?**
COMSOL if: you have a university license, need multiphysics coupling, want a GUI, or are studying electrokinetics.
OpenFOAM if: you're budget-constrained, need to run large parametric studies, want full customization, or are comfortable with command-line tools.
See [Vendor Comparison](21_vendor_comparison.md).

**Q: Is 2D simulation good enough?**
Usually yes for: straight channels, symmetric cross-sections, initial design optimization, mixing studies.
Need 3D when: studying 3D flow structures, non-symmetric geometries, droplet pinch-off dynamics, or validating against experiments for publication.

**Q: How fine should my mesh be?**
Minimum 5-10 elements across channel width. Refine near walls (boundary layer mesh). Do a mesh convergence study — refine until results change <2%. See [Simulation Benchmarks](33_simulation_benchmarks.md).

**Q: How do I validate my simulation?**
Compare against Poiseuille flow (analytical solution) for same geometry. If velocity profile matches within 1-2%, your solver setup is correct. See [Theory & Equations](34_theory_equations.md).

---

## Fabrication

**Q: PDMS or 3D printing?**
PDMS if: you need <50 µm features, gas permeability (cell culture), established protocols, or the cheapest per-chip cost.
3D printing if: you need rapid iteration (<1 day turnaround), 3D channel geometries, no cleanroom access, or integrated connectors. Channels must be >200 µm.
See [Soft Lithography](05_fabrication_soft_litho.md) and [3D Printing](06_fabrication_3dprint.md).

**Q: Why do my PDMS chips leak?**
Common causes: dirty surfaces before bonding, bonded too late after plasma (>60 sec), insufficient plasma power/time, fingerprints on bonding surfaces. See [Troubleshooting](16_practical_tips.md).

**Q: How do I get rid of bubbles?**
Degas all solutions before use. Pre-wet channels with ethanol then switch to buffer. Avoid sharp corners in design. Keep temperature constant. Add a bubble trap. See [Troubleshooting](16_practical_tips.md).

**Q: SU-8 or dry film resist?**
SU-8: better resolution (<5 µm), higher aspect ratios, more established. Requires cleanroom.
Dry film (Ordyl, ADEX): easier process, no spin coater needed, cheaper, safer developer. Resolution ~20 µm. Can work outside cleanroom.
See [Fabrication Recipes](22_fabrication_recipes.md).

**Q: When should I switch from PDMS to thermoplastic?**
When: you need >100 devices, small molecule studies (PDMS absorbs drugs), organic solvents, production manufacturing, or low autofluorescence. See [Materials Database](18_materials_database.md).

---

## Equipment

**Q: Syringe pump or pressure controller?**
Syringe pump: simpler, cheaper ($1.5-8k), precise volume control.
Pressure controller: faster response, pulseless flow, better for droplets and cell culture ($8-20k).
For most beginners: start with syringe pump, upgrade to pressure controller when needed.
See [Fluid Handling](11_fluid_handling.md).

**Q: What microscope do I need?**
Inverted is preferred (allows viewing through glass slide below chip). Minimum: 4×, 10×, 20× objectives. Fluorescence capability if doing any dye/fluorophore work. Budget: $5-15k used, $20-50k new. See [Characterization](09_characterization.md).

**Q: Can I use a DIY syringe pump for research?**
Yes. The Poseidon system (~$400) has been used in published research. For serious quantitative work, consider adding a Sensirion flow sensor ($50-100) for closed-loop feedback. See [Open-Source Ecosystem](15_open_source_ecosystem.md).

---

## Applications

**Q: Can microfluidics replace well plates?**
For some applications, yes. Advantages: less reagent (µL vs mL), better control, continuous flow. Disadvantages: throughput can be lower, specialized equipment needed, harder to parallelize. Organ-on-chip and droplet-based screening are the main areas where microfluidics offers clear advantages over well plates.

**Q: What's the state of organ-on-chip?**
Commercially available from: Emulate, TissUse, CN Bio, Mimetas, Alveolix. FDA has accepted organ-on-chip data as supplementary evidence. Full regulatory acceptance as drug testing replacement is still evolving (as of 2026). See [Biology Platforms](29_biology_platforms.md).

**Q: Can I do PCR on a microfluidic chip?**
Yes. Options: (1) Continuous flow PCR (serpentine through temperature zones), (2) Stationary chamber PCR (heater under chip), (3) Digital PCR in droplets (Bio-Rad QX600). Commercial platforms exist from Bio-Rad, Stilla, and Standard BioTools.

---

## Production & Commercialization

**Q: How do I go from prototype to product?**
1. Validate concept in PDMS (10-50 iterations)
2. Transfer design to thermoplastic (COC/COP) via CNC mold
3. Validate in target material
4. Commission injection mold ($15-100k)
5. Pilot production (100-1000 units)
6. Scale to mass production
Timeline: 6-18 months. Budget: $100-500k. See [Packaging & Scale-Up](32_packaging_scaleup.md).

**Q: What does regulatory approval cost?**
FDA 510(k): $30-100k + 4-12 months. CE marking (IVDR): $50-200k + 6-18 months. Total for US + EU: $250k-1.2M. See [Standards & Regulatory](24_standards_regulatory.md).

**Q: Where can I outsource fabrication?**
- PDMS prototypes: uFluidix (~$60/chip for 100 qty)
- Injection molding: Microfluidic ChipShop, Micronit, Vantiva
- Glass/silicon: Micronit, Dolomite
- Standard chips: Dolomite, Microfluidic ChipShop (off-the-shelf)
See [Foundry Services](14_foundry_services.md).

---

## Common Misconceptions

**"Microfluidics is only for biologists"** — False. Applications include flow chemistry, materials synthesis, environmental monitoring, food safety, and energy.

**"You need a cleanroom for microfluidics"** — False for prototyping. 3D printing, laser cutting, dry film resist, and xurography all work without a cleanroom.

**"PDMS is the only material"** — False for production. COC, COP, PMMA, glass, and silicon are all used commercially. PDMS is primarily for academic prototyping.

**"Simulation replaces experiments"** — False. Simulation guides design but must be validated experimentally. Many microfluidic phenomena (fouling, air bubbles, manufacturing variability) are not captured by simulation.

**"Smaller is always better"** — False. Smaller channels mean higher pressure drops, easier clogging, and harder fabrication. Choose dimensions based on your application, not a desire to miniaturize.

**"Microfluidics is expensive"** — False for getting started. A functional setup can cost <$500 with DIY approaches. Commercial equipment is expensive, but open-source alternatives exist for almost everything.
