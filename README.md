# Microfluidics Design & Fabrication Tools — Comprehensive Reference

> **The definitive working engineer's guide to every tool needed to design, simulate, and fabricate microfluidic devices.**

> Last updated: March 2026 | 15 research files | 350+ pages of content

---

## Quick Reference: Tool Recommendations

| Task | Recommended Tool | Cost | Free Alternative |
|------|-----------------|------|-----------------|
| **CFD Simulation** | COMSOL Microfluidics Module | ~$7k base + ~$3k module | OpenFOAM (interFoam for two-phase) |
| **Multiphysics** | COMSOL Multiphysics | ~$7k-9k perpetual | Elmer FEM, FEniCS |
| **Cloud CFD** | SimScale | Free tier / $2-5k/yr | OpenFOAM on AWS |
| **2D Mask Layout** | KLayout | Free | gdstk (Python scripting) |
| **3D CAD** | SolidWorks / Fusion 360 | $4-8k/yr / $545/yr | FreeCAD, Onshape (free tier) |
| **Microfluidic Design** | 3DuF | Free | OpenMFDA |
| **Droplet Design** | COMSOL (Phase Field) | See above | OpenFOAM interFoam |
| **Digital Microfluidics** | OpenDrop platform | ~$500 DIY | — |
| **PDMS Prototyping** | Soft lithography | $200-2k (mold) | — |
| **3D Print Prototyping** | Formlabs Form 3/4 (SLA) | $3-5k printer | — |
| **High-Res 3D Print** | BMF microArch | ~$50-100k | — |
| **Nanoscale Features** | Nanoscribe (2PP) | ~$300-600k | — |
| **Production Chips** | Injection molding (COC/COP) | $15-100k tooling | — |
| **Syringe Pump** | Harvard PHD ULTRA | $5-8k | Poseidon DIY (~$400) |
| **Pressure Controller** | Elveflow OB1 MK4 | $8-18k | DIY piezo (~$300-500) |
| **Flow Sensor** | Sensirion SLF3S | $50-100 | — |
| **Connectors** | IDEX NanoPort | $30-80 each | Press-fit (free) |

---

## Research Files

### Part 1: Simulation & Design

| # | File | Topics | Size |
|---|------|--------|------|
| 01 | [CFD & Multiphysics Simulation](research/01_simulation_cfd.md) | COMSOL, ANSYS Fluent, OpenFOAM, Elmer, SimScale, Flow-3D, Star-CCM+ | 39 KB |
| 02a | [Specialized Simulators](research/02_simulation_specialized.md) | Lattice Boltzmann (Palabos, OpenLB), DPD, Surface Evolver, LAMMPS, FEniCS, FiPy, AI/ML tools | 25 KB |
| 02b | [Microfluidic-Specific Design](research/02_microfluidic_specific_design.md) | Dolomite, 3DuF, OpenMFDA, droplet tools, digital microfluidics, circuit analogy, SPICE models, online calculators | 53 KB |
| 03 | [CAD & Layout Tools](research/03_cad_layout.md) | L-Edit, KLayout, AutoCAD, SolidWorks, Fusion 360, CleWin, gdstk, FreeCAD | 24 KB |

### Part 2: Fabrication

| # | File | Topics | Size |
|---|------|--------|------|
| 04 | [Photolithography](research/04_fabrication_lithography.md) | UV lithography, mask aligners (SUSS, EVG), maskless (Heidelberg), photoresists (SU-8, AZ), masks | 25 KB |
| 05 | [Soft Lithography & PDMS](research/05_fabrication_soft_litho.md) | PDMS (Sylgard 184), plasma bonding, PDMS alternatives (OSTEMER, COC, COP, PMMA), material selection | 32 KB |
| 06 | [3D Printing](research/06_fabrication_3dprint.md) | SLA (Formlabs), DLP (BMF microArch), Two-photon (Nanoscribe), post-processing, resolution limits | 33 KB |
| 07 | [Hot Embossing & Injection Molding](research/07_fabrication_embossing_molding.md) | Embossing (Jenoptik, EVG), injection molding, COC/COP/PMMA, mold fabrication, contract manufacturers | 23 KB |
| 08 | [Laser, Glass & Silicon](research/08_fabrication_laser_glass_silicon.md) | CO2 laser, femtosecond laser, glass etching (HF), silicon DRIE, anodic bonding | 32 KB |

### Part 3: Characterization, Surface Treatment & Fluid Handling

| # | File | Topics | Size |
|---|------|--------|------|
| 09a | [Surface Treatment & Bonding](research/09_surface_treatment_bonding.md) | Sputtering, evaporation, hydrophobic/hydrophilic coatings, SAMs, Parylene, thermal/solvent/adhesive bonding | 20 KB |
| 09b | [Characterization & Testing](research/09_characterization.md) | Micro-PIV, fluorescence microscopy, high-speed cameras, pressure/flow sensors, microscopes | 14 KB |
| 11b | [Fluid Handling Equipment](research/11_fluid_handling.md) | Syringe pumps, pressure controllers, flow sensors, tubing, IDEX connectors, chip holders | 12 KB |

### Part 4: Workflows, Costs & Resources

| # | File | Topics | Size |
|---|------|--------|------|
| 10 | [Workflows](research/10_workflows.md) | Quick prototype (<$500), research-grade (<$5k), production-ready ($50-300k) — complete step-by-step | 13 KB |
| 11a | [Cost Analysis](research/11_cost_analysis.md) | Software licensing, per-chip fabrication costs, equipment costs, foundry pricing, total project estimates | 12 KB |
| 12 | [Learning Resources](research/12_learning_resources.md) | Textbooks, online courses, YouTube, communities, conferences, journals, GitHub repos | 13 KB |

---

## Key Findings

### Simulation
- **COMSOL is the industry standard** but expensive (~$10k+ with modules). For academics with university licenses, it's the clear first choice.
- **OpenFOAM is surprisingly viable** for microfluidics — interFoam handles two-phase (droplets), simpleFoam handles single-phase. Steep learning curve but zero cost.
- **SimScale** offers a free tier with real CFD capability — good entry point for students.
- **AI/ML-based design** is emerging rapidly — neural network surrogates are replacing CFD for design optimization (10,000× faster than full simulation).

### Fabrication
- **PDMS soft lithography remains dominant** in academic research. Material cost ~$1/chip, but requires SU-8 mold (cleanroom).
- **3D printing is closing the gap** — Formlabs SLA achieves ~200 µm channels; BMF microArch gets down to ~20 µm. Direct-print chips are viable for prototyping.
- **Two-photon lithography (Nanoscribe)** achieves sub-micron features but costs $300-600k — reserved for niche applications.
- **For production:** injection molding in COC/COP is the path. Tooling costs $15-100k but per-chip cost drops to $0.50-5.

### Fluid Handling
- **Pressure controllers beat syringe pumps** for most microfluidic applications (faster response, pulseless flow, longer runtime). But they cost 2-5× more.
- **Open-source syringe pumps** (Poseidon, Arduino-based) are research-grade at ~$400 — legitimate for publications.
- **Sensirion flow sensors** ($50-100) are a game-changer for DIY setups — previously only available as $1-3k integrated units.

### Cost
- **Academic proof-of-concept: $500-2,000** — use free CAD/simulation, DIY pumps, university cleanroom
- **Research lab setup: $20-80k** — COMSOL, commercial pumps, microscope, cleanroom access
- **Product development: $100-500k** — full simulation, injection mold tooling, pilot production, regulatory

---

## What's New

| Date | Update |
|------|--------|
| 2026-03-15 | **Initial release** — Complete research across all 15 files covering simulation, design, fabrication, characterization, fluid handling, workflows, costs, and learning resources |
| 2026-03-15 | Comprehensive CFD comparison: COMSOL vs ANSYS vs OpenFOAM vs SimScale vs Flow-3D |
| 2026-03-15 | Full fabrication methods guide: soft lithography, 3D printing, hot embossing, injection molding, laser processing, glass/silicon |
| 2026-03-15 | Equipment buyer's guide with real pricing: syringe pumps, pressure controllers, flow sensors, connectors |
| 2026-03-15 | Three complete workflows with step-by-step instructions and cost breakdowns |
| 2026-03-15 | Open-source alternatives cataloged for every commercial tool |
| 2026-03-15 | 20+ GitHub repositories indexed for open-source microfluidics |

---

## How to Use This Reference

1. **New to microfluidics?** → Start with [Learning Resources](research/12_learning_resources.md), then read the [Workflows](research/10_workflows.md)
2. **Choosing simulation software?** → [CFD Comparison](research/01_simulation_cfd.md) has head-to-head analysis
3. **Designing a chip?** → [CAD Tools](research/03_cad_layout.md) + [Microfluidic Design](research/02_microfluidic_specific_design.md)
4. **Fabricating?** → Start with [Soft Lithography](research/05_fabrication_soft_litho.md) or [3D Printing](research/06_fabrication_3dprint.md)
5. **Setting up a lab?** → [Fluid Handling](research/11_fluid_handling.md) + [Cost Analysis](research/11_cost_analysis.md)
6. **Going to production?** → [Injection Molding](research/07_fabrication_embossing_molding.md) + [Workflow C](research/10_workflows.md)
7. **On a budget?** → [Cost Analysis](research/11_cost_analysis.md) has budget-optimized setups at every price point

---

## Contributing

This is a living document. If you find outdated information, incorrect pricing, or missing tools, please open an issue or PR.

## License

This research compilation is provided as-is for educational and professional reference.
