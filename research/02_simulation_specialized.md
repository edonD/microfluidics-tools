# Specialized Simulators for Microfluidics

> Research compiled March 2026. Covers Lattice Boltzmann methods, dissipative
> particle dynamics, surface/interface simulation, molecular dynamics, Python/MATLAB
> PDE solvers, and AI/ML-based design optimization tools.

---

## Table of Contents

1. [Lattice Boltzmann Method (LBM) Tools](#1-lattice-boltzmann-method-lbm-tools)
   - [Palabos](#11-palabos)
   - [OpenLB](#12-openlb)
   - [waLBerla](#13-walberla)
   - [LBM Comparison](#14-lbm-tool-comparison)
2. [Dissipative Particle Dynamics (DPD) Tools](#2-dissipative-particle-dynamics-dpd-tools)
3. [Surface Evolver](#3-surface-evolver)
4. [LAMMPS](#4-lammps)
5. [Python/MATLAB PDE Solver Libraries](#5-pythonmatlab-pde-solver-libraries)
   - [FiPy](#51-fipy)
   - [FEniCS](#52-fenics)
   - [Dedalus](#53-dedalus)
6. [AI/ML-Based Design Optimization Tools](#6-aiml-based-design-optimization-tools)
7. [Comparison Matrix](#7-comparison-matrix)
8. [Recommendations by Application](#8-recommendations-by-application)

---

## 1. Lattice Boltzmann Method (LBM) Tools

The Lattice Boltzmann Method is a mesoscale simulation approach that models fluid as a collection of particles on a discrete lattice. Unlike traditional CFD (which solves Navier-Stokes equations), LBM evolves particle distribution functions through streaming and collision steps. This makes LBM particularly well-suited for:

- Multiphase flows (droplets, emulsions, bubbles)
- Complex geometries (porous media, rough microchannels)
- Flows with moving boundaries
- Parallelization on GPUs and HPC clusters

### 1.1 Palabos

| Attribute | Details |
|---|---|
| **Developer** | University of Geneva (FlowKit Ltd spin-off) |
| **License** | AGPLv3 (open source) |
| **Language** | C++ |
| **OS** | Linux, macOS, Windows |
| **Website** | [palabos.unige.ch](https://palabos.unige.ch/) |

#### Strengths

- General-purpose LBM framework suitable for research and engineering.
- Handles incompressible and compressible flows, thermal flows, free surface flows, and multiphase/multi-component flows.
- Well-documented with tutorials and example cases.
- MPI-parallelized for HPC clusters.
- Active academic user community; widely cited in literature.
- Good balance between usability and flexibility.

#### Weaknesses

- AGPLv3 license requires sharing modifications (commercial users must buy FlowKit license).
- No native GPU support (CPU-only, unlike waLBerla).
- Performance lags behind waLBerla for extreme-scale simulations.
- Steeper learning curve than commercial CFD tools.
- Documentation, while good, is not as extensive as OpenFOAM.

#### Microfluidics Applications

- Droplet generation in T-junctions and flow-focusing geometries.
- Multiphase flows in porous media.
- Capillary filling and wetting dynamics.
- Emulsion formation.

---

### 1.2 OpenLB

| Attribute | Details |
|---|---|
| **Developer** | Karlsruhe Institute of Technology (KIT) and collaborators |
| **License** | GPLv2 (open source) |
| **Language** | C++ |
| **OS** | Linux, macOS, Windows |
| **Website** | [openlb.net](https://www.openlb.net/) |

#### Strengths

- Object-oriented C++ framework; modular and extensible.
- Supports MPI + OpenMP hybrid parallelism for CPU clusters.
- GPU support via CUDA and OpenCL.
- Wide range of physics: fluid flow, particulate flows, thermal flows, reactive flows.
- Built-in turbulence models (LES, Smagorinsky).
- Active development with regular releases and workshops.
- Demonstrated microfluidic droplet generation cases.

#### Weaknesses

- Complex API; significant C++ expertise required.
- Documentation could be more beginner-friendly.
- Smaller user community than Palabos.
- Setting up complex geometries requires effort.

#### Microfluidics Applications

- Droplet generation with controlled size in microfluidic channels.
- Double emulsion creation.
- Electroosmotic flow.
- Particulate transport in microchannels.

---

### 1.3 waLBerla

| Attribute | Details |
|---|---|
| **Developer** | Friedrich-Alexander University Erlangen-Nuremberg (FAU) |
| **License** | GPLv3 (open source) |
| **Language** | C++ with Python bindings |
| **OS** | Linux (primary), macOS |
| **Website** | [walberla.net](https://walberla.net/) |

#### Strengths

- **Extreme-scale HPC performance:** Demonstrated on >10^12 lattice nodes; scales to 2048+ NVIDIA A100 GPUs.
- Near-perfect weak and strong scaling with GPUDirect MPI and communication hiding.
- Code generation framework (lbmpy) for optimized LBM kernels.
- Pure-MPI and hybrid MPI+OpenMP+CUDA parallelization.
- Free surface LBM implementation.
- Coupled LBM + finite difference (e.g., electroosmotic flow in microchannels).

#### Weaknesses

- Primarily a research/HPC framework; not designed for casual users.
- Steep learning curve; requires understanding of both LBM theory and HPC concepts.
- Linux-focused; limited Windows support.
- Fewer ready-to-use application examples compared to Palabos.
- Documentation oriented toward HPC researchers.

#### Microfluidics Applications

- Large-scale multiphase simulations (millions to billions of cells).
- Electroosmotic flow in microchannels.
- Free-surface flows.
- Coupled multiphysics problems requiring extreme resolution.

---

### 1.4 LBM Tool Comparison

| Feature | Palabos | OpenLB | waLBerla |
|---|---|---|---|
| **Ease of use** | Moderate | Moderate-Hard | Hard |
| **GPU support** | No | Yes (CUDA/OpenCL) | Yes (CUDA, best-in-class) |
| **Max scale** | ~10^9 cells | ~10^10 cells | ~10^12 cells |
| **Multiphase** | Yes (strong) | Yes | Yes |
| **Documentation** | Good | Moderate | HPC-focused |
| **License** | AGPLv3 | GPLv2 | GPLv3 |
| **Best for** | General LBM research | Diverse physics + GPU | Extreme-scale HPC |

---

## 2. Dissipative Particle Dynamics (DPD) Tools

DPD is a mesoscale particle-based simulation method that bridges molecular dynamics and continuum CFD. Particles represent clusters of molecules ("beads"), interacting through conservative, dissipative, and random forces. DPD is particularly useful for:

- Flows involving polymers, vesicles, and biological cells.
- Blood flow in microcapillaries.
- Droplet dynamics where thermal fluctuations matter.
- Phenomena at length scales of 10 nm - 10 um.

### Available Tools

#### DL_MESO

| Attribute | Details |
|---|---|
| **Developer** | STFC Daresbury Laboratory (UK) |
| **License** | Open source (academic) |
| **Language** | Fortran/C++ |
| **Website** | [dl-sdg.github.io](https://dl-sdg.github.io/RESOURCES/DOCUMENTS/DPDIntro.html) |

- Most comprehensive dedicated DPD code.
- Includes Lattice Boltzmann module as well.
- Well-documented with CCP5 training materials.
- Recommended for complex polymer and biological simulations.

#### LAMMPS (DPD Module)

- LAMMPS includes DPD pair styles (`dpd`, `dpd/tstat`), making it possible to run DPD within the LAMMPS ecosystem.
- Benefits from LAMMPS's massive infrastructure (GPU acceleration, scaling, analysis tools).
- Recommended for users already familiar with LAMMPS.

#### DPDsim (Python)

| Attribute | Details |
|---|---|
| **Source** | [GitHub](https://github.com/petervanya/DPDsim) |
| **Language** | Python |

- Lightweight implementation of several DPD variants.
- Good for learning and prototyping.
- Not suitable for production-scale simulations.

#### Jdpd (Java)

| Attribute | Details |
|---|---|
| **Source** | Published in *Journal of Cheminformatics* |
| **Language** | Java |

- Open Java simulation kernel for Molecular Fragment DPD.
- Parallelizable force calculation with efficient caching.
- Suitable for polymer and molecular fragment simulations.

### When to Use DPD

DPD is the right choice when you need to model soft matter (polymers, membranes, blood cells) in microfluidic geometries, when thermal fluctuations are important, or when atomistic MD is too expensive but continuum CFD cannot capture the relevant physics.

---

## 3. Surface Evolver

| Attribute | Details |
|---|---|
| **Developer** | Ken Brakke, Susquehanna University |
| **License** | Free (public domain) |
| **Language** | C |
| **OS** | Windows (pre-compiled 32/64-bit), macOS (pre-compiled), Linux/Unix (source + Makefile) |
| **Website** | [kenbrakke.com/evolver](https://kenbrakke.com/evolver/evolver.html) |

### Overview

Surface Evolver is an interactive finite-element program for studying surfaces shaped by surface tension, gravity, and other forces. It minimizes energy functionals to find equilibrium shapes of liquid interfaces.

### Strengths

- **Definitive tool for static droplet/meniscus shape calculation.**
- Handles arbitrary topology (droplets, bubbles, thin films, foams).
- Energy contributions: surface tension, gravity, squared mean curvature, user-defined surface integrals.
- Constraints: volume, boundary, contact angles, prescribed mean curvature.
- Crystalline integrands for anisotropic surface energies.
- User-controlled clipping planes and slice views.
- No installation required; runs from unpacked files.
- Extremely lightweight and fast for its domain.
- Widely cited in wetting, electrowetting, and microfluidics literature.

### Weaknesses

- **Not a flow simulator;** computes static equilibrium shapes only.
- Text-based command interface; no modern GUI.
- Steep learning curve for complex geometries.
- Single-threaded; no parallel computing support.
- Documentation is comprehensive but dense.
- Not actively developed (mature/stable codebase).
- No transient dynamics.

### Microfluidics Applications

- Droplet shape on micropillar arrays and superhydrophobic surfaces.
- Contact angle and wetting behavior prediction.
- Meniscus shape in capillary structures.
- Electrowetting-on-dielectric (EWOD) droplet actuation.
- Membrane emulsification droplet formation prediction.
- Capillary valve design and burst pressure estimation.
- Droplet shape on curved surfaces.

### When to Choose It

Choose Surface Evolver when you need accurate static equilibrium shapes of liquid interfaces, when designing capillary structures, or when studying wetting/dewetting phenomena. It complements dynamic flow simulators by providing precise interface shapes as initial or boundary conditions.

---

## 4. LAMMPS

| Attribute | Details |
|---|---|
| **Developer** | Sandia National Laboratories + community |
| **License** | GPLv2 (open source) |
| **Language** | C++ with Python interface |
| **OS** | Linux, macOS, Windows |
| **Website** | [lammps.org](https://www.lammps.org/) |

### Overview

LAMMPS (Large-scale Atomic/Molecular Massively Parallel Simulator) is the most widely used open-source molecular dynamics code. While primarily designed for materials science, it has extensive applications in nanoscale fluidics.

### Strengths

- **Massive model library:** Hundreds of pair potentials, bond styles, and force fields.
- Scales from single CPU to the largest supercomputers (GPU-accelerated via KOKKOS).
- Hybrid atomistic-continuum coupling with OpenFOAM for multiscale simulations.
- Built-in DPD pair styles for mesoscale simulations.
- Lattice Boltzmann fluid coupling (`lb/fluid` fix) for suspended particles.
- Mesh geometry options for micro/nanofluidic device geometries.
- Extensive analysis tools (compute, fix, dump).
- Huge community; thousands of papers; well-documented.

### Weaknesses

- Molecular dynamics is computationally expensive; limited to nanoscale domains (typically < 1 um).
- Input script syntax has a learning curve.
- Not a CFD tool; solves Newton's equations for individual atoms/particles.
- Requires knowledge of force fields and molecular simulation methodology.
- Post-processing requires external tools (VMD, OVITO, etc.).

### Microfluidics Applications

- Nanoscale liquid flows in nanochannels and nanopores.
- Slip length and boundary condition characterization.
- Nanofluidic molecule ejection through nozzles.
- Wetting and contact line dynamics at molecular scale.
- Ion transport and electrokinetic effects.
- Pre-simulations to extract transport properties for continuum models.

### When to Choose It

Choose LAMMPS when studying nanoscale phenomena (< 1 um) where continuum assumptions break down, when molecular-level detail is essential (e.g., slip at walls, molecular sorting), or when coupling atomistic and continuum approaches. Not appropriate for device-scale (mm) microfluidic simulations.

---

## 5. Python/MATLAB PDE Solver Libraries

These general-purpose PDE solvers can be applied to microfluidic problems (Stokes flow, diffusion-reaction, heat transfer) with appropriate problem setup.

### 5.1 FiPy

| Attribute | Details |
|---|---|
| **Developer** | NIST (Materials Science and Engineering Division) |
| **License** | NIST open source (public domain equivalent) |
| **Language** | Python |
| **Method** | Finite Volume |
| **Website** | [pages.nist.gov/fipy](https://pages.nist.gov/fipy/en/latest/index.html) |

#### Strengths

- Pure Python; easy to install and script.
- Object-oriented PDE specification: transient, diffusion, convection, source terms.
- Arbitrary combinations of coupled PDEs.
- 1D, 2D, 3D unstructured meshes.
- Built-in Cahn-Hilliard, phase field, and level set models.
- Good for diffusion-reaction problems common in lab-on-chip devices.

#### Weaknesses

- Slower than compiled FEM/FVM codes for large problems.
- Limited solver options compared to FEniCS.
- Primarily developed for materials science (phase field, electrochemistry); no microfluidics-specific examples.
- Small user community.
- Documentation could be more extensive.

#### Microfluidics Relevance

Useful for species transport, diffusion-reaction kinetics, and concentration gradient modeling in microchannels. Not ideal for solving Navier-Stokes but workable for Stokes flow at low Reynolds numbers typical in microfluidics.

---

### 5.2 FEniCS

| Attribute | Details |
|---|---|
| **Developer** | FEniCS Project (international collaboration) |
| **License** | LGPLv3 (open source) |
| **Language** | Python (with C++ backend: DOLFIN/DOLFINx) |
| **Method** | Finite Element |
| **Website** | [fenicsproject.org](https://fenicsproject.org/) |

#### Strengths

- **Most capable open-source FEM framework** for general PDEs.
- Symbolic problem specification via UFL (Unified Form Language).
- Automatic code generation for efficient assembly.
- Supports mixed elements, DG methods, and adaptive mesh refinement.
- MPI-parallelized; scales to HPC clusters.
- Handles Stokes flow, Navier-Stokes, advection-diffusion, fluid-structure interaction.
- Large academic community; thousands of publications.
- FEATool Multiphysics provides a GUI layer for FEniCS.

#### Weaknesses

- Installation can be complex (Docker recommended).
- Two active versions (legacy FEniCS vs. FEniCSx/DOLFINx) cause confusion.
- Steep learning curve for non-FEM experts.
- No built-in microfluidics examples (must formulate problems from scratch).
- Mesh generation requires external tools (Gmsh, mshr).

#### Microfluidics Relevance

Excellent for low-Reynolds-number flow simulations (Stokes/Navier-Stokes), species transport, electrokinetic flows, and coupled multiphysics problems in microfluidic geometries. Can handle complex 2D/3D channel geometries with unstructured meshes. Commonly used in academic microfluidics research.

---

### 5.3 Dedalus

| Attribute | Details |
|---|---|
| **Developer** | Dedalus Project (astrophysics/geophysics community) |
| **License** | GPLv3 (open source) |
| **Language** | Python (with compiled backends) |
| **Method** | Spectral methods |
| **Website** | [dedalus-project.org](https://dedalus-project.org/) |

#### Strengths

- **Symbolic equation entry:** Translates plain-text PDE descriptions into efficient solvers.
- Spectral accuracy (exponential convergence for smooth solutions).
- MPI-parallelized.
- Supports initial value, boundary value, and eigenvalue problems.
- Simultaneous pressure solve for incompressible flow (no operator splitting).
- High-order DAE timestepping methods.
- Extremely versatile; handles nearly arbitrary equation sets.

#### Weaknesses

- Spectral methods require smooth solutions and simple (rectangular/spherical) domains.
- **Not suitable for complex microfluidic geometries** (irregular channel shapes, T-junctions).
- Designed for astrophysics/geophysics; microfluidics is not a target application.
- Small community outside astrophysics.
- Limited mesh flexibility compared to FEM.

#### Microfluidics Relevance

Limited. Best suited for fundamental studies in simple geometries (straight channels, periodic domains) where spectral accuracy is valuable, such as instability analysis, mixing in simple geometries, or verification benchmarks. Not practical for realistic microfluidic device geometries.

---

## 6. AI/ML-Based Design Optimization Tools

Machine learning is increasingly applied to microfluidic design, enabling automated geometry optimization, performance prediction, and inverse design.

### 6.1 DAFD (Design Automation of Fluid Dynamics)

| Attribute | Details |
|---|---|
| **Developer** | CIDAR Lab, Boston University |
| **Access** | Free web-based tool ([cidarlab.org/dafd](https://www.cidarlab.org/dafd)) |
| **Published** | *Nature Communications* (2020) |

- First ML-based microfluidic design automation tool.
- Trained on experimental datasets of flow-focusing droplet generators.
- **Forward mode:** Predict droplet size and frequency from device geometry and flow rates.
- **Inverse mode:** Specify target droplet properties; tool suggests geometries.
- Integrates with rapid prototyping and CAD workflows.

### 6.2 uFluidicGenius (uFG)

| Attribute | Details |
|---|---|
| **Published** | *Science Advances* (2024) |
| **Access** | Open-access web tool |

- ML-augmented design tool for microfluidic circuits.
- Enables non-expert users to design functional microfluidic circuits.
- Hybrid framework: ML models + mathematical modeling.
- Automatically generates spatially coded maze structures.
- 90% accuracy in reproducing target flow distributions (experimentally validated).

### 6.3 Bayesian Optimization Approaches

- Bayesian optimization has been applied to microfluidic mixer design, achieving optimal geometries **an order of magnitude faster** than traditional optimization.
- Published in *Lab on a Chip* (2025).
- Combines surrogate models (Gaussian processes) with CFD simulation.
- Particularly effective when simulation is expensive and design space is moderate-dimensional.

### 6.4 Deep Learning for Droplet Microfluidics

- Data-driven frameworks using residual blocks and Fourier-enhanced neural networks.
- Forward prediction of droplet characteristics from geometry.
- Inverse design: optimize geometric ratios for target droplet properties.
- Published in *Scientific Reports* (2025).

### 6.5 ChatGPT-Assisted CAD Design

- Researchers have explored using large language models (ChatGPT) to assist with microfluidic device CAD design.
- Published in *Lab on a Chip* (2023).
- LLMs can generate CAD scripts, suggest design parameters, and help with design iteration.
- Still experimental; not a replacement for domain expertise.

### Key Challenges for AI/ML in Microfluidics

1. **Limited training data:** Experimental microfluidic datasets are small compared to ML norms.
2. **Standardization:** No standard data formats or benchmarks for microfluidic ML.
3. **Interpretability:** Complex models are hard to interpret physically.
4. **Generalization:** Models trained on one device type do not transfer easily.
5. **Validation:** ML predictions require experimental validation, closing the loop.

---

## 7. Comparison Matrix

| Tool | Method | Scale | Typical Use | GPU | License | Ease of Use |
|---|---|---|---|---|---|---|
| **Palabos** | LBM | Meso (um-mm) | Multiphase droplet flows | No | AGPLv3 | Moderate |
| **OpenLB** | LBM | Meso (um-mm) | Diverse physics + droplets | Yes | GPLv2 | Moderate-Hard |
| **waLBerla** | LBM | Meso (extreme scale) | HPC multiphase | Yes (best) | GPLv3 | Hard |
| **DL_MESO** | DPD/LBM | Meso (nm-um) | Polymers, bio flows | No | Academic | Moderate |
| **LAMMPS (DPD)** | DPD | Meso (nm-um) | Soft matter in channels | Yes | GPLv2 | Moderate |
| **Surface Evolver** | Energy min. | Interface | Static droplet shapes | No | Free | Moderate-Hard |
| **LAMMPS (MD)** | MD | Nano (<1um) | Nanoscale transport | Yes | GPLv2 | Moderate |
| **FiPy** | FVM | Macro (um-mm) | Diffusion-reaction | No | NIST OSS | Easy |
| **FEniCS** | FEM | Macro (um-mm) | Stokes/NS flow | No* | LGPLv3 | Moderate-Hard |
| **Dedalus** | Spectral | Macro (simple) | Instabilities, mixing | No | GPLv3 | Moderate |
| **DAFD** | ML | Device-level | Droplet generator design | N/A | Free web | Easy |
| **uFG** | ML | Circuit-level | Flow distribution | N/A | Free web | Easy |

*FEniCS has experimental GPU backends in development.

---

## 8. Recommendations by Application

### Droplet Generation and Multiphase Flows

- **Best open-source option:** Palabos or OpenLB (with GPU, OpenLB preferred).
- **Extreme scale:** waLBerla.
- **Quick design iteration:** DAFD (ML-based, no simulation needed).
- **Static droplet shapes:** Surface Evolver.

### Blood Flow and Biological Cell Transport

- **Primary tool:** DL_MESO or LAMMPS (DPD mode).
- **Coupled flow + particles:** OpenLB.

### Wetting, Contact Angles, and Capillary Phenomena

- **Static equilibrium:** Surface Evolver (definitive tool).
- **Dynamic wetting:** Palabos or OpenLB (LBM multiphase).
- **Molecular-scale wetting:** LAMMPS (MD).

### Species Transport and Mixing

- **Simple geometries:** FiPy (easiest) or Dedalus (highest accuracy).
- **Complex geometries:** FEniCS (most flexible FEM).
- **With flow coupling:** FEniCS (Stokes + advection-diffusion).

### Nanoscale Transport (< 1 um)

- **Primary tool:** LAMMPS (molecular dynamics).
- **Mesoscale bridge:** LAMMPS (DPD mode).
- **Multiscale:** LAMMPS-OpenFOAM hybrid coupling.

### Automated Design Optimization

- **Droplet generators:** DAFD.
- **Microfluidic circuits:** uFluidicGenius.
- **Custom optimization:** Bayesian optimization + CFD (FEniCS or OpenFOAM as forward model).
- **Exploratory:** ChatGPT-assisted CAD scripting.

### Quick Start for a New Lab

1. Start with **FEniCS** for general microfluidic flow simulation (most versatile open-source FEM).
2. Add **Surface Evolver** for capillary/wetting problems.
3. Use **DAFD** for rapid droplet generator design without simulation.
4. Add **Palabos** or **OpenLB** when multiphase LBM is needed.
5. Use **LAMMPS** only for nanoscale investigations.

---

## Sources

- [Palabos Official Site](https://palabos.unige.ch/)
- [OpenLB Official Site](https://www.openlb.net/)
- [OpenLB Paper - Computers & Mathematics with Applications](https://www.sciencedirect.com/science/article/pii/S0898122120301875)
- [waLBerla Publications](https://walberla.net/publications.html)
- [waLBerla HPC Scaling Paper - FAU CRIS](https://cris.fau.de/publications/336536976/)
- [List of LBM Codes - GitHub](https://github.com/sthavishtha/list-lattice-Boltzmann-codes)
- [DL_MESO DPD Documentation](https://dl-sdg.github.io/RESOURCES/DOCUMENTS/DPDIntro.html)
- [DPD for Advanced Microfluidics - Microfluidics and Nanofluidics](https://link.springer.com/article/10.1007/s10404-008-0375-4)
- [DPDsim GitHub](https://github.com/petervanya/DPDsim)
- [Jdpd Paper - Journal of Cheminformatics](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-018-0278-7)
- [Surface Evolver - Ken Brakke](https://kenbrakke.com/evolver/evolver.html)
- [Surface Evolver - Wikipedia](https://en.wikipedia.org/wiki/Surface_Evolver)
- [LAMMPS Official Site](https://www.lammps.org/)
- [LAMMPS Paper - Computer Physics Communications](https://www.sciencedirect.com/science/article/pii/S0010465521002836)
- [LAMMPS LB/fluid fix - Computer Physics Communications](https://www.sciencedirect.com/science/article/pii/S0010465522000364)
- [LAMMPS-OpenFOAM Hybrid](https://www.sciencedirect.com/science/article/abs/pii/S0010465513001069)
- [FiPy - NIST](https://pages.nist.gov/fipy/en/latest/index.html)
- [FEniCS Project](https://fenicsproject.org/)
- [Dedalus Project](https://dedalus-project.org/)
- [Dedalus Paper - Physical Review Research](https://link.aps.org/doi/10.1103/PhysRevResearch.2.023068)
- [DAFD - CIDAR Lab](https://www.cidarlab.org/dafd)
- [DAFD Paper - Nature Communications (2020)](https://www.nature.com/articles/s41467-020-20284-z)
- [uFluidicGenius - Science Advances (2024)](https://www.science.org/doi/10.1126/sciadv.aea7598)
- [Bayesian Optimization for Microfluidics - Lab on a Chip (2025)](https://pubs.rsc.org/en/content/articlelanding/2025/lc/d4lc00872c)
- [ML-Driven Innovations in Microfluidics - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11674507/)
- [ChatGPT-Assisted Microfluidic CAD - Lab on a Chip (2023)](https://pubs.rsc.org/en/content/articlelanding/2023/lc/d3lc00518f)
- [ResearchGate - Best Microfluidics Simulation Software](https://www.researchgate.net/post/What-is-best-software-for-simulation-of-microfluidic)
- [ResearchGate - Best Package for Microfluidics Flow](https://www.researchgate.net/post/Which-is-the-best-package-to-simulate-microfluidics-flow)
