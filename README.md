# Microfluidics Design & Fabrication Tools — Comprehensive Reference

> **The definitive working engineer's guide to every tool needed to design, simulate, and fabricate microfluidic devices.**

> Last updated: March 2026 | 36 research files | 1.1 MB of content (~1100 pages)

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

### Part 5: Deep Dives (Phase 2)

| # | File | Topics | Size |
|---|------|--------|------|
| 13 | [Emerging Technologies (2024-2026)](research/13_emerging_technologies.md) | AI/ML design tools, organ-on-chip platforms, paper microfluidics, acoustofluidics, EWOD/DMF, inertial microfluidics | 34 KB |
| 14 | [Foundry Services Directory](research/14_foundry_services.md) | Detailed comparison of 14+ contract manufacturers with capabilities, certifications, and pricing | 19 KB |
| 15 | [Open-Source Ecosystem](research/15_open_source_ecosystem.md) | Complete catalog of open-source microfluidics projects: design tools, hardware, pumps, controllers | 18 KB |
| 16 | [Practical Tips & Troubleshooting](research/16_practical_tips.md) | Design rules, dimensionless numbers, troubleshooting (bubbles, leaks, clogs), PDMS protocols, mixer design, consumable pricing | 16 KB |
| 17 | [Advanced Techniques](research/17_advanced_techniques.md) | Quake valves, mLSI, centrifugal/lab-on-disc, droplet microfluidics, inertial focusing, paper µPADs, electrokinetics, acoustofluidics | 14 KB |

### Part 6: Reference Materials (Phase 3)

| # | File | Topics | Size |
|---|------|--------|------|
| 18 | [Materials Compatibility Database](research/18_materials_database.md) | Chemical compatibility charts for PDMS/COC/COP/PMMA/glass/silicon, swelling data, bonding compatibility matrix, material properties | 37 KB |
| 19 | [Applications Guide](research/19_applications_guide.md) | POC diagnostics, drug discovery, single-cell analysis, flow chemistry, LNP production, environmental monitoring | 58 KB |
| 20 | [Simulation Tutorials](research/20_simulation_tutorials.md) | Step-by-step COMSOL, OpenFOAM, FEniCS setup guides. Analytical calculators. Python code snippets. Mesh convergence. | 48 KB |
| 21 | [Vendor Comparison Matrices](research/21_vendor_comparison.md) | Head-to-head: COMSOL vs ANSYS vs OpenFOAM, Elveflow vs Fluigent, 3D printer comparison, buying guides for 4 lab scenarios | 16 KB |
| 22 | [Fabrication Recipes](research/22_fabrication_recipes.md) | SU-8 process parameters, dry film resists (Ordyl, ADEX), PDMS casting protocol, plasma bonding, mask ordering | 14 KB |
| 23 | [Experiment Automation](research/23_automation_software.md) | Python/LabVIEW control, vendor SDKs (Elveflow, Fluigent), PID feedback, image analysis, data logging | 10 KB |
| 24 | [Standards & Regulatory](research/24_standards_regulatory.md) | ISO 22916 interoperability, FDA 510(k), CE marking (MDR/IVDR), ISO 13485, biocompatibility, cleanroom classification | 8 KB |

### Part 7: Reference & Glossary (Phase 4)

| # | File | Topics | Size |
|---|------|--------|------|
| 25 | [Surface, Interface & QC](research/25_surface_interface_qc.md) | Chip cleaning/reuse, surface functionalization, coatings, chip-to-world interface, quality control, metrology | 45 KB |
| 26 | [Industry & Market Trends](research/26_industry_trends.md) | Market size/forecast, key players, startups, tech trends 2025-2030, career opportunities | 25 KB |
| 27 | [Glossary & Quick Reference](research/27_glossary.md) | 80+ abbreviations, key formulas, physical constants, unit conversions, Python calculators | 11 KB |

### Part 8: Application Platforms (Phase 5)

| # | File | Topics | Size |
|---|------|--------|------|
| 28 | [Niche Tools](research/28_niche_tools.md) | Microfluidic valves/actuators, integrated sensors, gradient generators, cell traps, wearable sensors, LNP production | 36 KB |
| 29 | [Biology Platforms](research/29_biology_platforms.md) | Organ-on-chip (Emulate, TissUse, CN Bio, Mimetas), single-cell (10x Genomics), digital PCR, on-chip FACS | 42 KB |
| 30 | [Flow Chemistry & Microreactors](research/30_flow_chemistry.md) | Syrris, Vapourtec, Chemtrix, NanoAssemblr LNP production, microreactor design, inline PAT | 31 KB |

### Part 9: Advanced Reference (Phase 6)

| # | File | Topics | Size |
|---|------|--------|------|
| 31 | [MEMS Sensors & Actuators](research/31_sensors_actuators.md) | Pressure/temperature/optical/electrochemical sensors, micropumps (Bartels), microvalves (Lee, Festo) | 39 KB |
| 32 | [Packaging & Scale-Up](research/32_packaging_scaleup.md) | Device packaging, reagent storage, sample introduction, prototype-to-product, commercial success stories | 40 KB |
| 33 | [Simulation Benchmarks](research/33_simulation_benchmarks.md) | Analytical validation solutions, CFD benchmarks, mesh convergence, computational costs, common pitfalls | 38 KB |

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
| 2026-03-15 | **Phase 3** — Added 6 reference files: materials database, simulation tutorials, vendor comparisons, fabrication recipes, experiment automation |
| 2026-03-15 | New: Materials compatibility database with PDMS swelling chart, bonding matrix, sterilization guide |
| 2026-03-15 | New: Step-by-step simulation tutorials for COMSOL, OpenFOAM, FEniCS with Python code |
| 2026-03-15 | New: Complete SU-8 recipes, dry film resist alternatives, PDMS casting protocol |
| 2026-03-15 | New: Experiment automation with Python SDKs, PID control, image analysis |
| 2026-03-15 | **Phase 2** — Added 5 deep-dive files: emerging technologies, foundry directory, open-source ecosystem, practical tips, advanced techniques |
| 2026-03-15 | New: AI/ML for microfluidic design (PINNs, surrogate models, generative design) |
| 2026-03-15 | New: 14+ foundry services compared with capabilities and certifications |
| 2026-03-15 | New: Troubleshooting guide (bubbles, leaks, clogs) + PDMS protocol + mixer design guide |
| 2026-03-15 | New: Advanced techniques — Quake valves, droplet microfluidics, inertial focusing, acoustofluidics, paper µPADs |
| 2026-03-15 | New: Consumable pricing reference (PDMS, SU-8, wafers, masks) |
| 2026-03-15 | **Phase 1 (Initial)** — 15 research files covering simulation, design, fabrication, characterization, fluid handling, workflows, costs, and learning resources |
| 2026-03-15 | Comprehensive CFD comparison: COMSOL vs ANSYS vs OpenFOAM vs SimScale vs Flow-3D |
| 2026-03-15 | Full fabrication methods guide: soft lithography, 3D printing, hot embossing, injection molding, laser processing, glass/silicon |
| 2026-03-15 | Equipment buyer's guide with real pricing: syringe pumps, pressure controllers, flow sensors, connectors |
| 2026-03-15 | Three complete workflows with step-by-step instructions and cost breakdowns |
| 2026-03-15 | Open-source alternatives cataloged for every commercial tool |
| 2026-03-15 | 30+ GitHub repositories indexed for open-source microfluidics |

---

## How to Use This Reference

1. **New to microfluidics?** → Start with [Learning Resources](research/12_learning_resources.md), then read the [Workflows](research/10_workflows.md)
2. **Choosing simulation software?** → [CFD Comparison](research/01_simulation_cfd.md) has head-to-head analysis
3. **Designing a chip?** → [CAD Tools](research/03_cad_layout.md) + [Microfluidic Design](research/02_microfluidic_specific_design.md)
4. **Fabricating?** → Start with [Soft Lithography](research/05_fabrication_soft_litho.md) or [3D Printing](research/06_fabrication_3dprint.md)
5. **Setting up a lab?** → [Fluid Handling](research/11_fluid_handling.md) + [Cost Analysis](research/11_cost_analysis.md)
6. **Going to production?** → [Injection Molding](research/07_fabrication_embossing_molding.md) + [Workflow C](research/10_workflows.md)
7. **On a budget?** → [Cost Analysis](research/11_cost_analysis.md) has budget-optimized setups at every price point
8. **Troubleshooting?** → [Practical Tips](research/16_practical_tips.md) covers bubbles, leaks, clogs, and common mistakes
9. **Advanced techniques?** → [Advanced Techniques](research/17_advanced_techniques.md) covers valves, droplets, inertial sorting, acoustofluidics
10. **Looking for a foundry?** → [Foundry Directory](research/14_foundry_services.md) compares 14+ contract manufacturers
11. **Want open-source?** → [Open-Source Ecosystem](research/15_open_source_ecosystem.md) catalogs every major project

---

## Contributing

This is a living document. If you find outdated information, incorrect pricing, or missing tools, please open an issue or PR.

## License

This research compilation is provided as-is for educational and professional reference.
