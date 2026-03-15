# Specialized Simulators for Microfluidics

> Research compiled March 2026. Covers Lattice Boltzmann methods, dissipative
> particle dynamics, surface/interface simulation, molecular dynamics, Python/MATLAB
> PDE solvers, and AI/ML-based design optimization tools.

---

## Table of Contents

1. [Lattice Boltzmann Method (LBM) Tools](#1-lattice-boltzmann-method-lbm-tools)
   - [Why LBM for Microfluidics](#why-lbm-over-traditional-cfd-for-microfluidics)
   - [Palabos](#11-palabos)
   - [OpenLB](#12-openlb)
   - [waLBerla](#13-walberla)
   - [LBM Comparison](#14-lbm-tool-comparison)
2. [Dissipative Particle Dynamics (DPD) Tools](#2-dissipative-particle-dynamics-dpd-tools)
   - [DL_MESO](#dl_meso)
   - [HOOMD-blue](#hoomd-blue)
   - [LAMMPS DPD Module](#lammps-dpd-module)
   - [When to Use DPD vs CFD](#when-to-use-dpd-vs-cfd)
   - [DPD Applications](#dpd-applications-in-microfluidics)
3. [Surface Evolver](#3-surface-evolver)
4. [LAMMPS for Molecular Dynamics](#4-lammps-for-molecular-dynamics)
   - [When MD is Needed vs Continuum](#when-md-is-needed-vs-continuum-methods)
5. [Python/MATLAB PDE Solver Libraries](#5-pythonmatlab-pde-solver-libraries)
   - [FEniCS](#51-fenics)
   - [FiPy](#52-fipy)
   - [Dedalus](#53-dedalus)
   - [MATLAB PDE Toolbox and Alternatives](#54-matlab-pde-toolbox-and-alternatives)
6. [AI/ML-Based Design Optimization Tools](#6-aiml-based-design-optimization-tools)
   - [ML for Design Optimization (2024-2026)](#61-ml-for-microfluidic-design-optimization-2024-2026)
   - [Neural Network Surrogate Models](#62-neural-network-surrogate-models-replacing-cfd)
   - [Generative Design](#63-generative-design-for-channel-geometries)
   - [Physics-Informed Neural Networks](#64-physics-informed-neural-networks-pinns)
   - [Practical Tools](#65-practical-tools)
7. [Comparison Matrix](#7-comparison-matrix)
8. [Recommendations by Application](#8-recommendations-by-application)

---

## 1. Lattice Boltzmann Method (LBM) Tools

The Lattice Boltzmann Method is a mesoscale simulation approach that models fluid as a collection of particles on a discrete lattice. Unlike traditional CFD (which directly discretizes the Navier-Stokes equations), LBM evolves particle distribution functions through streaming and collision steps on a regular grid. The macroscopic flow field (velocity, pressure, density) emerges from statistical moments of the distribution functions.

### Why LBM Over Traditional CFD for Microfluidics

LBM offers several distinct advantages for microfluidic simulation that make it preferable in specific scenarios:

**Multiphase and Interface Handling:**
- Phase separations are generated automatically from particle dynamics; no special treatment is needed to track or manipulate interfaces as in traditional CFD methods (Volume of Fluid, Level Set).
- Microscopic interactions (e.g., surface tension, contact angle physics) can be incorporated naturally by modifying the collision operator, whereas these are difficult to implement in macroscopic Navier-Stokes equations.
- Successful LBM applications include interface instability, bubble/droplet dynamics, wetting on solid surfaces, and droplet deformation -- all central to droplet microfluidics.

**Complex Geometries:**
- Lattice grid generation is simpler than unstructured mesh generation: only structured meshes are needed.
- Complex boundaries (porous media, rough channels, pillared surfaces) are handled via simple bounce-back rules rather than requiring body-fitted meshes.
- Setting up and modifying geometries is more straightforward than in mesh-based CFD.

**Parallelization:**
- LBM is inherently local (nearest-neighbor interactions only), making it ideal for GPU acceleration and massive parallelization.
- Near-linear scaling on thousands of GPUs has been demonstrated (waLBerla on 2048+ A100 GPUs).

**When Traditional CFD Is Still Better:**
- Steady-state solutions: LBM is inherently transient; traditional CFD can solve steady-state directly.
- High Mach number flows (not relevant for most microfluidics).
- Heat transfer coupled with flow (LBM thermal models are less mature).
- When existing validated Navier-Stokes models and workflows already exist.
- Single-phase laminar flow in simple geometries (standard CFD is simpler to set up).

---

### 1.1 Palabos

| Attribute | Details |
|---|---|
| **Developer** | University of Geneva (FlowKit Ltd spin-off) |
| **License** | AGPLv3 (open source) |
| **Language** | C++ |
| **OS** | Linux, macOS, Windows |
| **Website** | [palabos.unige.ch](https://palabos.unige.ch/) |
| **GPU Support** | Pre-release GPU-capable version available |

#### Capabilities

- General-purpose LBM framework suitable for both research and engineering applications.
- Handles incompressible and weakly compressible flows, thermal flows, free surface flows, and multiphase/multi-component flows.
- Shan-Chen and free-energy multiphase models for droplet simulation.
- Well-documented with tutorials, example cases, and a published reference paper in *Computers & Mathematics with Applications* (2020).
- MPI-parallelized for HPC clusters.
- Active academic user community; widely cited in microfluidics and porous media literature.
- Good balance between usability and flexibility -- generally considered the most accessible LBM code for newcomers.

#### When to Use Palabos

- First choice for researchers new to LBM who need multiphase/droplet simulation.
- Droplet generation in T-junctions and flow-focusing geometries.
- Multiphase flows in porous media and complex microstructures.
- Capillary filling and wetting dynamics.
- Emulsion formation and stability studies.

#### Limitations

- AGPLv3 license requires sharing modifications (commercial users must acquire a FlowKit license).
- CPU-only in the stable release (GPU version is pre-release as of early 2026).
- Performance lags behind waLBerla for extreme-scale simulations.
- Steeper learning curve than commercial CFD tools like COMSOL.
- Documentation, while good, is not as extensive as OpenFOAM's.

---

### 1.2 OpenLB

| Attribute | Details |
|---|---|
| **Developer** | Karlsruhe Institute of Technology (KIT) and collaborators |
| **License** | GPLv2 (open source) |
| **Language** | C++ |
| **OS** | Linux, macOS, Windows |
| **Website** | [openlb.net](https://www.openlb.net/) |

#### Capabilities

- Object-oriented C++ framework; modular and extensible architecture.
- Supports MPI + OpenMP hybrid parallelism for CPU clusters.
- Full GPU support via CUDA and OpenCL backends.
- Wide range of physics: fluid flow, particulate flows (resolved and unresolved), thermal flows, reactive flows, electrokinetic flows.
- Built-in turbulence models (LES, Smagorinsky subgrid-scale).
- Active development with regular releases, workshops, and symposia.
- Demonstrated microfluidic double emulsion creation as a benchmark case.
- Published reference paper in *Computers & Mathematics with Applications* (2020).

#### When to Use OpenLB

- When GPU acceleration is needed but waLBerla's complexity is not warranted.
- Droplet generation with controlled size in microfluidic channels.
- Double emulsion creation.
- Electroosmotic and electrokinetic flow problems.
- Particulate transport in microchannels.
- Users who need diverse physics models with GPU capability.

#### Limitations

- Complex API requiring significant C++ expertise.
- Documentation could be more beginner-friendly.
- Smaller user community than Palabos.
- Setting up complex geometries requires substantial effort.

---

### 1.3 waLBerla

| Attribute | Details |
|---|---|
| **Developer** | Friedrich-Alexander University Erlangen-Nuremberg (FAU) |
| **License** | GPLv3 (open source) |
| **Language** | C++ with Python bindings (lbmpy for code generation) |
| **OS** | Linux (primary), macOS |
| **Website** | [walberla.net](https://walberla.net/) |

#### Capabilities

- **Extreme-scale HPC performance:** Demonstrated on >10^12 lattice nodes; scales to 2048+ NVIDIA A100 GPUs with near-perfect weak and strong scaling.
- GPUDirect MPI and communication hiding for maximum throughput.
- Code generation framework (lbmpy) that automatically produces optimized LBM kernels from symbolic descriptions.
- Pure-MPI and hybrid MPI+OpenMP+CUDA parallelization.
- Block-structured adaptive mesh refinement (AMR).
- Free surface LBM implementation.
- Fully resolved particulate flows.
- Coupled LBM + finite difference methods (e.g., electroosmotic flow).

#### When to Use waLBerla

- Large-scale multiphase simulations requiring millions to billions of cells.
- When GPU performance is the primary concern.
- Problems that benefit from adaptive mesh refinement.
- Electroosmotic flow in microchannels at high resolution.
- Free-surface flows in microfluidic contexts.
- Coupled multiphysics problems requiring extreme resolution.

#### Limitations

- Primarily a research/HPC framework; not designed for casual users.
- Steep learning curve requiring understanding of both LBM theory and HPC concepts.
- Linux-focused; limited Windows support.
- Fewer ready-to-use application examples compared to Palabos.
- Documentation oriented toward HPC researchers rather than microfluidics practitioners.

---

### 1.4 LBM Tool Comparison

| Feature | Palabos | OpenLB | waLBerla |
|---|---|---|---|
| **Ease of use** | Moderate | Moderate-Hard | Hard |
| **GPU support** | Pre-release | Yes (CUDA/OpenCL) | Yes (CUDA, best-in-class) |
| **Max scale** | ~10^9 cells | ~10^10 cells | ~10^12 cells |
| **Multiphase** | Yes (strong) | Yes | Yes |
| **Particulate flows** | Limited | Yes | Yes (fully resolved) |
| **AMR** | No | No | Yes |
| **Code generation** | No | No | Yes (lbmpy) |
| **Documentation** | Good | Moderate | HPC-focused |
| **License** | AGPLv3 | GPLv2 | GPLv3 |
| **Best for** | General LBM research | Diverse physics + GPU | Extreme-scale HPC |
| **Microfluidics entry** | Best starting point | Good with GPU need | Overkill for most |

---

## 2. Dissipative Particle Dynamics (DPD) Tools

DPD is a mesoscale particle-based simulation method that bridges molecular dynamics and continuum CFD. Each DPD particle ("bead") represents a cluster of atoms or a fluid parcel rather than a single atom. Particles interact through three pairwise forces:

1. **Conservative force:** soft repulsion determining the equation of state.
2. **Dissipative force:** velocity-dependent drag providing viscous damping.
3. **Random force:** stochastic kicks maintaining temperature (fluctuation-dissipation theorem).

This thermostat preserves momentum conservation, ensuring correct hydrodynamic behavior at the mesoscale. DPD accesses length scales of 10 nm to 10 um and time scales up to tens of microseconds -- far beyond what atomistic MD can reach.

### DL_MESO

| Attribute | Details |
|---|---|
| **Developer** | STFC Daresbury Laboratory (UK), CCP5 |
| **License** | Open source (academic; registration required) |
| **Language** | Fortran/C++ |
| **Website** | [dl-sdg.github.io](https://dl-sdg.github.io/RESOURCES/EXERCISES/DPD.html) |

- Most comprehensive dedicated DPD code available.
- Includes a separate Lattice Boltzmann module alongside DPD.
- Well-documented with CCP5 practical training exercises and tutorials.
- Extended to MPI+CUDA for GPU acceleration on hybrid CPU-GPU architectures.
- Recommended for users whose primary focus is DPD simulation of complex polymer and biological systems.
- Handles many-body DPD variants and various thermostat options.

### HOOMD-blue

| Attribute | Details |
|---|---|
| **Developer** | Glotzer Group, University of Michigan |
| **License** | BSD 3-Clause (open source) |
| **Language** | C++/CUDA with Python interface |
| **Website** | [hoomd-blue.readthedocs.io](https://hoomd-blue.readthedocs.io/) |
| **Source** | [github.com/glotzerlab/hoomd-blue](https://github.com/glotzerlab/hoomd-blue) |

- GPU-native design: built from the ground up for NVIDIA GPUs.
- Supports Lennard-Jones, DPD, DLVO, Gaussian, Mie, WCA, Yukawa, and many other pair potentials.
- Demonstrated scaling on up to 3,375 GPUs with DPD simulations of up to 108 million particles.
- Autotuning algorithm optimizes GPU kernel parameters automatically.
- Python-first interface makes scripting and workflow integration straightforward.
- Also supports Monte Carlo methods for hard particle systems.
- DPD force computation requires communicating ghost particle velocities (2x data vs standard forces), but GPU performance remains strong.
- Best choice for GPU-accelerated DPD at large scale.

### LAMMPS DPD Module

| Attribute | Details |
|---|---|
| **DPD pair styles** | `dpd`, `dpd/tstat`, `dpd/fdt`, `dpd/fdt/energy` |
| **Smoothed DPD** | SDPD package available |
| **GPU acceleration** | Via KOKKOS package |

- DPD runs within the full LAMMPS ecosystem, benefiting from its massive infrastructure: hundreds of analysis tools, dump formats, coupling frameworks.
- GPU acceleration through the KOKKOS package.
- Smoothed DPD (SDPD) package available for improved accuracy in hydrodynamic problems, including simulations of red blood cells in tube flow and leukocyte margination.
- Recommended for users already familiar with LAMMPS who want to add DPD capability without learning a new tool.
- Can combine DPD with other LAMMPS force fields in the same simulation.

### When to Use DPD vs CFD

| Criterion | Use DPD | Use CFD (Navier-Stokes) |
|---|---|---|
| **Length scale** | 10 nm - 10 um | 1 um - cm |
| **Time scale** | ns - us | us - s |
| **Deformable objects** | Cells, vesicles, polymers | Rigid particles only |
| **Thermal fluctuations** | Important | Negligible |
| **Solvent detail** | Coarse-grained | Continuum |
| **Phase behavior** | Self-assembly, micelles | Not applicable |
| **Computational cost** | High (per unit volume) | Lower (per unit volume) |
| **Complex rheology** | Natural (from particle interactions) | Requires constitutive models |

**Choose DPD when:**
- Modeling soft, deformable objects (blood cells, polymer vesicles, lipid membranes) in flow.
- Thermal fluctuations affect behavior at the length scale of interest.
- You need to capture self-assembly or phase separation of amphiphilic molecules.
- The system involves complex rheology arising from microstructure (polymer solutions, surfactant systems).

**Choose CFD when:**
- Working at device scale (mm) with well-characterized Newtonian fluids.
- Steady-state or long-time-scale behavior is needed.
- The primary interest is bulk flow patterns rather than molecular-scale phenomena.

### DPD Applications in Microfluidics

**Blood Flow and Cell Transport:**
- Red blood cell deformation and margination in microcapillaries.
- Leukocyte margination and adhesion in microfluidic blood-on-chip devices.
- Platelet aggregation in stenosed microchannels.
- SDPD method has been particularly successful for blood cell simulations.

**Polymer Solutions:**
- Polymer chain dynamics in microfluidic confinement.
- Viscoelastic flow behavior in contraction-expansion geometries.
- Polymer self-assembly, blend behavior, and phase separation.
- Polyelectrolyte transport and interactions.

**Vesicles and Lipid Membranes:**
- Diblock copolymer vesicle dynamics in nanochannels under Poiseuille flow.
- Lipid bilayer vesicle shape changes and budding transitions.
- Drug-loaded polymersomes in microfluidic flow -- informing design of bio-functional carriers.

**Droplet and Emulsion Dynamics:**
- Micro-droplet formation, coalescence, and breakup.
- Multiphase flows in micro-channels and fracture networks.
- Surfactant-laden interfaces and Marangoni effects.

---

## 3. Surface Evolver

| Attribute | Details |
|---|---|
| **Developer** | Ken Brakke, Susquehanna University |
| **License** | Free (public domain) |
| **Language** | C |
| **OS** | Windows (pre-compiled 32/64-bit), macOS (pre-compiled), Linux/Unix (source + Makefile) |
| **Website** | [kenbrakke.com/evolver](https://kenbrakke.com/evolver/evolver.html) |
| **Manual** | [270-page PDF](https://kenbrakke.com/evolver/downloads/manual270.pdf) (Version 2.70, 2013) |

### How It Works

Surface Evolver represents a liquid surface as a simplicial complex (triangulated mesh) and evolves it toward a local energy minimum using gradient descent. At each iteration:

1. The total energy of the surface is computed (contributions from surface tension, gravity, user-defined integrals).
2. The energy gradient with respect to each vertex position is calculated.
3. Vertices are moved in the direction of steepest energy decrease.
4. The process repeats until the energy change falls below a convergence tolerance (typically < 10^-8 energy units).

The surface can be refined (subdivided) during evolution to improve accuracy, and mesh quality operations (equiangulation, vertex averaging) maintain numerical stability.

### Capabilities

- Arbitrary topology: droplets, bubbles, thin films, foams, multiply-connected surfaces.
- **Energy contributions:** surface tension (isotropic or anisotropic/crystalline), gravity, squared mean curvature, user-defined surface and line integrals.
- **Constraints:** fixed volume (body constraints), geometric constraints on vertex positions, boundary contact angles, prescribed mean curvature.
- Solves the Young-Laplace equation and Young's equation via variational energy minimization.
- Extremely lightweight and fast for its domain.
- No installation required; runs from a single executable.
- Companion book: *The Physics of Microdroplets* (Brakke & Berthier) with 100+ downloadable Evolver models for microfluidic scenarios.

### Microfluidics Applications

- **Droplet shape on micropillar arrays:** Predicting Cassie-Baxter to Wenzel collapse transitions on posts of arbitrary shape.
- **Contact angle and wetting behavior:** Advancing and receding contact angles on structured surfaces.
- **Meniscus shape in capillary structures:** Capillary valve design and burst pressure estimation.
- **Electrowetting-on-dielectric (EWOD):** Combined with GUI template libraries for simulating electrowetting arrays.
- **Membrane emulsification:** Predicting droplet formation during membrane emulsification processes.
- **Open microfluidics:** Droplet behavior on open biphasic microfluidic surfaces.
- **Capillary pressure calculations:** Accurate Laplace pressure computation in complex geometries.

### Limitations

- **Not a flow simulator:** Computes static equilibrium shapes only; no velocity field, no transient dynamics.
- Text-based command interface; no modern GUI (scripting-driven workflow).
- Steep learning curve for complex geometries; input file syntax requires practice.
- Single-threaded; no parallel computing support.
- Documentation is comprehensive but dense (270-page manual).
- Mature/stable codebase -- not actively developed with new features (last major version 2.70, 2013).
- Cannot model dynamic processes like droplet breakup, coalescence, or flow-driven deformation.

### When to Choose Surface Evolver

Choose Surface Evolver when you need accurate static equilibrium shapes of liquid interfaces. It is the definitive tool for:
- Predicting droplet shapes on textured/patterned surfaces.
- Designing capillary stop valves and calculating burst pressures.
- Computing meniscus profiles in microfluidic reservoirs and wells.
- Studying wetting transitions (Cassie-Baxter vs Wenzel).

It complements dynamic flow simulators by providing precise interface shapes that can serve as initial or boundary conditions for CFD or LBM simulations.

---

## 4. LAMMPS for Molecular Dynamics

| Attribute | Details |
|---|---|
| **Developer** | Sandia National Laboratories + worldwide community |
| **License** | GPLv2 (open source) |
| **Language** | C++ with Python interface |
| **OS** | Linux, macOS, Windows |
| **Website** | [lammps.org](https://www.lammps.org/) |
| **Latest Symposium** | 9th LAMMPS Workshop, August 2025, Albuquerque, NM |

### Overview

LAMMPS (Large-scale Atomic/Molecular Massively Parallel Simulator) is the most widely used open-source molecular dynamics code. It solves Newton's equations of motion for collections of atoms or coarse-grained particles interacting through specified force fields.

### Capabilities for Nanoscale Fluidics

- **Massive model library:** Hundreds of pair potentials, bond styles, angle/dihedral potentials, and force fields (CHARMM, AMBER, OPLS, DREIDING, ReaxFF, etc.).
- **Scalability:** From a single CPU to the largest supercomputers; GPU-accelerated via KOKKOS package.
- **Hybrid atomistic-continuum coupling:** A fully parallelized hybrid atomistic-continuum (HAC) model built from LAMMPS + OpenFOAM resolves nanoscale features while maintaining computational efficiency at the device scale.
- **LBM coupling:** The `lb/fluid` fix couples suspended particles with a lattice Boltzmann fluid.
- **DPD pair styles:** Built-in mesoscale capability (see Section 2).
- **Analysis infrastructure:** Extensive compute, fix, and dump commands for on-the-fly analysis.
- Thousands of publications; active community with annual workshops.

### When MD Is Needed vs Continuum Methods

| Criterion | Use MD (LAMMPS) | Use Continuum (CFD) |
|---|---|---|
| **Channel size** | < 100 nm | > 1 um |
| **Slip at walls** | Must resolve molecular slip | Apply slip boundary condition |
| **Fluid structure** | Layering near walls matters | Bulk fluid properties sufficient |
| **Ion transport** | Individual ion trajectories needed | Poisson-Boltzmann adequate |
| **Molecular sorting** | Selectivity from molecular interactions | N/A |
| **Confinement effects** | Continuum breaks down | Continuum valid |
| **Computational cost** | Very high; limited to nm-scale domains | Manageable for um-mm scale |

**Key guideline:** When the characteristic dimension of the flow channel approaches the molecular mean free path (Knudsen number Kn > 0.01), continuum assumptions break down and MD becomes necessary. For water, this transition occurs around 1-10 nm channel width.

### Nanoscale Fluidics Applications

- Liquid flows in nanochannels (< 100 nm) and nanopores.
- Slip length characterization at molecular level.
- Nanofluidic molecule ejection through nano-nozzles.
- Wetting and contact line dynamics at the molecular scale.
- Ion transport and electrokinetic effects in nanopores.
- Water-graphene nanofluid behavior and thermal properties.
- Pre-simulations to extract transport properties (viscosity, diffusion coefficients, slip lengths) for use in continuum models.
- Nanoparticle transport in confined geometries.

### Multiscale Approaches

For problems that span nano-to-micro scales, LAMMPS can be coupled with continuum solvers:

- **LAMMPS + OpenFOAM:** Hybrid atomistic-continuum model where LAMMPS resolves near-wall molecular detail and OpenFOAM handles bulk flow.
- **LAMMPS + LBM:** The `lb/fluid` fix couples particles with a lattice Boltzmann fluid background.
- **Sequential multiscale:** Run LAMMPS to extract transport coefficients (slip length, viscosity near walls), then feed those into a device-scale CFD simulation.

---

## 5. Python/MATLAB PDE Solver Libraries

These general-purpose PDE solvers can be applied to microfluidic problems (Stokes flow, diffusion-reaction, heat transfer, electrokinetics) with appropriate problem formulation.

### 5.1 FEniCS

| Attribute | Details |
|---|---|
| **Developer** | FEniCS Project (international collaboration) |
| **License** | LGPLv3 (open source) |
| **Language** | Python (with C++ backend: DOLFIN/DOLFINx) |
| **Method** | Finite Element |
| **Website** | [fenicsproject.org](https://fenicsproject.org/) |

#### Capabilities for Microfluidics

- **Most capable open-source FEM framework** for general PDE problems.
- Symbolic problem specification via UFL (Unified Form Language) -- write equations in near-mathematical notation.
- Automatic code generation for efficient finite element assembly (FFC/FFCx compiler).
- Supports mixed finite elements (Taylor-Hood for Stokes, Raviart-Thomas for divergence-free fields), discontinuous Galerkin (DG) methods, and adaptive mesh refinement.
- MPI-parallelized; scales to HPC clusters.
- Handles:
  - Stokes and Navier-Stokes flow (incompressible, low-Re typical in microfluidics).
  - Advection-diffusion for species transport.
  - Electrokinetic flows (Poisson-Nernst-Planck + Stokes coupling).
  - Fluid-structure interaction problems.
  - Coupled multiphysics with arbitrary equation sets.
- Large academic community; thousands of publications.
- FEATool Multiphysics provides a MATLAB/Octave GUI layer that can use FEniCS as backend solver.
- Experimental GPU backends in development.

#### Limitations

- Two active versions (legacy FEniCS vs. FEniCSx/DOLFINx) cause confusion; legacy version is being phased out.
- Installation can be complex (Docker containers recommended for beginners).
- Steep learning curve for users unfamiliar with finite element theory.
- No built-in microfluidics-specific examples (must formulate problems from PDEs).
- Mesh generation requires external tools (Gmsh, mshr).

#### Example Microfluidics Workflow

```
1. Define geometry in Gmsh -> export mesh
2. Import mesh in FEniCS
3. Formulate Stokes equations in UFL:
   a(u,v) = inner(grad(u), grad(v))*dx
   L(v) = inner(f, v)*dx
4. Apply boundary conditions (no-slip walls, inlet velocity, outlet pressure)
5. Solve and visualize in ParaView
6. Add species transport equation coupled to flow field
```

---

### 5.2 FiPy

| Attribute | Details |
|---|---|
| **Developer** | NIST (Materials Science and Engineering Division) |
| **License** | NIST open source (public domain equivalent) |
| **Language** | Python |
| **Method** | Finite Volume |
| **Website** | [pages.nist.gov/fipy](https://pages.nist.gov/fipy/en/latest/index.html) |

#### Capabilities

- Pure Python; easy to install (`pip install fipy`) and script.
- Object-oriented PDE specification: compose equations from transient, diffusion, convection, and source terms.
- Arbitrary combinations of coupled elliptic, hyperbolic, and parabolic PDEs.
- 1D, 2D, 3D structured and unstructured meshes.
- Built-in models: Cahn-Hilliard (phase separation), phase field, level set.
- Good for diffusion-reaction problems common in lab-on-chip devices.

#### Limitations

- Slower than compiled FEM/FVM codes for large 3D problems.
- Limited solver options compared to FEniCS.
- Primarily developed for materials science applications (phase field, electrochemistry) -- no microfluidics-specific examples.
- Small user community.
- Not well-suited for solving full Navier-Stokes (workable for Stokes flow at low Re).

#### Microfluidics Relevance

Best for species transport, diffusion-reaction kinetics, and concentration gradient modeling in microchannels. Can handle Stokes flow at the low Reynolds numbers typical in microfluidics. Good choice for prototyping coupled PDE problems before moving to a more performant solver.

---

### 5.3 Dedalus

| Attribute | Details |
|---|---|
| **Developer** | Dedalus Project (astrophysics/geophysics community) |
| **License** | GPLv3 (open source) |
| **Language** | Python (with compiled backends) |
| **Method** | Spectral methods |
| **Website** | [dedalus-project.org](https://dedalus-project.org/) |

#### Capabilities

- **Symbolic equation entry:** Translates plain-text PDE descriptions directly into efficient solvers.
- Spectral accuracy (exponential convergence for smooth solutions).
- MPI-parallelized for distributed computing.
- Supports initial value, boundary value, and eigenvalue problems.
- Simultaneous pressure solve for incompressible flow (no operator splitting errors).
- High-order differential-algebraic equation (DAE) timestepping methods.
- Handles nearly arbitrary equation sets specified in text form.

#### Limitations

- Spectral methods require smooth solutions and simple (rectangular, cylindrical, spherical) domains.
- **Not suitable for complex microfluidic geometries** (irregular channel shapes, T-junctions, serpentine channels).
- Designed for astrophysics/geophysics; microfluidics is not a target application.
- Small community outside astrophysics/geophysics.
- Limited mesh flexibility compared to FEM or FVM.

#### Microfluidics Relevance

Limited to fundamental studies in simple geometries (straight channels, periodic domains) where spectral accuracy is valuable:
- Hydrodynamic stability analysis in microchannels.
- Mixing studies in simple periodic geometries.
- Verification benchmarks for other solvers.
- Instability and transition analysis.

Not practical for realistic microfluidic device geometries.

---

### 5.4 MATLAB PDE Toolbox and Alternatives

#### MATLAB PDE Toolbox

The standard MATLAB PDE Toolbox has significant limitations for fluid dynamics:
- The Navier-Stokes equations cannot be directly cast into the coefficient form that the PDE Toolbox solves without placing all nonlinear terms on the right-hand side.
- Not adequate for general fluid mechanics simulation.
- Useful for heat conduction, electrostatics, and structural mechanics but not for microfluidic flow.

#### Better MATLAB-Based Alternatives

**QuickerSim CFD Toolbox for MATLAB:**
| Attribute | Details |
|---|---|
| **Developer** | QuickerSim (commercial) |
| **License** | Commercial (free academic trial) |
| **Website** | [quickersim.com](https://quickersim.com/cfdtoolbox/microfluidics/) |

- Efficient laminar flow solver (steady-state and transient, 2D and 3D).
- Specifically designed for biofluids, medicine, and microfluidic devices.
- Integrates seamlessly into MATLAB workflows for post-processing and optimization.
- Dedicated microfluidic simulation examples and tutorials.
- Good for researchers who want to stay within the MATLAB ecosystem.

**CFDTool / FEATool Multiphysics:**
| Attribute | Details |
|---|---|
| **Developer** | Precise Simulation |
| **License** | Commercial (free community edition) |
| **Website** | [featool.com](https://www.featool.com/matlab-cfd-toolbox/) |

- MATLAB GUI for CFD simulation with built-in integration to OpenFOAM and SU2 solvers.
- Also supports FEniCS as a backend solver.
- Designed to make fluid dynamics and heat transfer simulations accessible within MATLAB.
- Supports coupled multiphysics problems.

#### Recommendation

For MATLAB users doing microfluidics, skip the standard PDE Toolbox. Use QuickerSim for laminar flow problems or FEATool for multiphysics coupling. For maximum capability, consider FEniCS (Python) which surpasses all MATLAB options in flexibility and performance for microfluidic simulation.

---

## 6. AI/ML-Based Design Optimization Tools

Machine learning is transforming microfluidic design from a manual, experience-driven process into an automated, data-driven one. The field has accelerated rapidly in 2024-2026, with several distinct approaches emerging.

### 6.1 ML for Microfluidic Design Optimization (2024-2026)

#### Bayesian Optimization (BO) for Microfluidics

A landmark 2025 study in *Lab on a Chip* demonstrated Bayesian optimization for microfluidic mixer design:

- **Method:** BO uses Gaussian processes to model the objective function (mixing index) and an acquisition function to balance exploration vs exploitation of the design space.
- **Workflow:** Python orchestrates COMSOL CFD simulations, automatically adjusting geometric parameters based on BO suggestions.
- **Results on parallelogram barrier mixer (4 parameters):**
  - Achieved mixing indices near 0.99 at Re = 1.
  - Optimal designs identified for Re = 1 to 100.
- **Results on Tesla mixer (9 parameters):**
  - Achieved MI values of 0.85-0.97 across multiple Reynolds numbers.
  - Demonstrated scalability to higher-dimensional optimization.
- **Performance vs traditional methods:**
  - BO: 33 simulations to reach optimum.
  - Particle Swarm Optimization (PSO): 289 simulations (8.8x more).
  - Differential Evolution (DE): 580 simulations (17.6x more).
  - Genetic Algorithm (GA) and Evolution Strategy (ES): >1000 simulations without convergence.
- **Key advantage:** No separate surrogate model needed; BO works directly with exact CFD simulations.

#### Deep Learning for Chip Architecture (2026)

Published in *Lab on a Chip* (accepted January 2026), a deep learning framework for microfluidic chip architecture design:

- Automatically generates optimized module sequences, geometries, and operating parameters.
- Produces fabrication-ready blueprints for complex channel networks.
- Integration of 5,000 modules in as little as 18 seconds.
- Addresses spatiotemporal manipulation of particles in complex networks.

#### Deep Learning for Microemulsion Prediction

A multi-component deep learning framework combines:
- Multi-branch CNN with residual modules and self-attention for droplet/fluid morphology recognition.
- GAN-LGBMnet combining generative adversarial networks and LightGBM to augment small datasets.
- Multi-output neural network predicting single/double-emulsion parameters.

### 6.2 Neural Network Surrogate Models Replacing CFD

Neural network surrogates aim to approximate CFD solvers at orders-of-magnitude lower computational cost, enabling real-time design exploration.

#### Approaches and Architectures

**Graph Neural Networks (GNNs):**
- MeshGraphNets (MGNs) encode arbitrary CFD/FEA meshes into latent graph representations.
- Deliver orders-of-magnitude speedups over traditional solvers while retaining high accuracy.
- Handle irregular mesh topologies common in microfluidic geometries.

**Neural Fields (Neural Implicit Representations):**
- MARIO (Modulated Aerodynamic Resolution Invariant Operator) approach uses neural fields for discretization-invariant predictions.
- Can train on significantly downsampled meshes while maintaining accuracy during full-resolution inference.
- Reduces computational cost and memory requirements dramatically.

**Convolutional Neural Networks (CNNs):**
- Used to forecast fluid flow patterns within microfluidic channels.
- Analyze extensive datasets from simulations to determine optimal channel geometries and flow rates.
- RNNs complement CNNs for time-dependent flow predictions.

#### Performance

- ML-enhanced CFD can produce results comparable to high-resolution DNS on a 10x coarser grid.
- Potential speedups of 10^3 to 10^4 in 3D simulations.
- Training requires significant upfront computational investment (hundreds to thousands of CFD simulations).

#### Limitations

- Approximation errors are inherent; surrogate models are not exact.
- Large training datasets required (expensive to generate).
- Generalization to unseen geometries remains challenging.
- Physical conservation laws may not be strictly satisfied.
- Validation against experiments still essential.

### 6.3 Generative Design for Channel Geometries

#### muFluidicGenius (muFG) -- Science Advances (2026)

| Attribute | Details |
|---|---|
| **Developer** | Koc University |
| **Access** | Open-access software tool |
| **Published** | *Science Advances* (2026) |

- Hybrid algorithm combining ML models with mathematical fluid mechanics.
- Users specify reservoir placement, channel connections, and target flow rates.
- Algorithm determines required fluidic resistance values and generates maze-like channel geometries to achieve precise flow control.
- **90% accuracy** in achieving target flow rates when chips are 3D-printed.
- Supports complex physiological flow profiles needed in multi-organ-on-chip systems.
- Makes microfluidic design accessible to non-engineers.

#### CNN/RNN-Based Geometry Generation

- Convolutional neural networks trained on simulation datasets propose channel geometries optimized for specific applications (mixing, separation, droplet generation).
- Generative adversarial networks (GANs) can produce novel channel designs that are physically plausible and manufacturable.

### 6.4 Physics-Informed Neural Networks (PINNs)

PINNs embed governing physical equations (Navier-Stokes, advection-diffusion, Poisson-Nernst-Planck) directly into the neural network loss function, enabling training with sparse or no labeled data.

#### How PINNs Work for Microfluidics

1. A neural network takes spatial coordinates (x, y, z) and optionally time (t) as input.
2. The network outputs flow variables (velocity, pressure, concentration).
3. The loss function includes:
   - **PDE residual:** How well the network output satisfies the governing equations (computed via automatic differentiation).
   - **Boundary condition residual:** How well boundary conditions are satisfied.
   - **Data residual (optional):** Agreement with sparse experimental or simulation data.
4. Training minimizes the combined loss, producing a solution that is both data-consistent and physics-consistent.

#### Microfluidics-Specific Results

**Multi-Physics Coupling (2024):**
A PINN framework for multi-physics coupling in microfluidic systems demonstrated:
- Accurate solutions for ion concentration polarization (ICP) problems with strong nonlinearity.
- Advantages over FEM when dealing with sparse sample points: PINNs provide correct physical results where FEM fails on the same mesh.
- Strong interpolation capability for inferring unknown parameters.
- Effective modeling of coupled electrokinetic-flow-transport problems.

**Variational PINNs (VPINNs):**
- Use weak formulation of Navier-Stokes equations.
- Better stability in irregular or highly curved domains.
- Well-suited for bioinspired microfluidic channels and complex geometries.

#### Challenges and Recent Advances

**Known Challenges:**
- PINNs can struggle with stiff fluid problems, converging to local minima and producing physically implausible solutions (flow stagnation artifacts).
- Training is often slower than direct numerical simulation for simple problems.
- Hyperparameter tuning (loss weights, architecture) is nontrivial.

**2025 Advances:**
- **Re-initialization strategy:** Periodically modulating training parameters enables PINNs to escape local minima and explore alternative solutions in stiff problems.
- **Automatic network structure discovery** via knowledge distillation (published in *Nature Communications*, 2025).
- **Sparse data reconstruction:** PINNs can reconstruct full flow fields from sparse and noisy experimental measurements -- particularly valuable for microfluidic experiments where instrumentation access is limited.

### 6.5 Practical Tools

#### DAFD (Design Automation of Fluid Dynamics)

| Attribute | Details |
|---|---|
| **Developer** | CIDAR Lab, Boston University |
| **Access** | Free web-based tool ([cidarlab.org/dafd](https://www.cidarlab.org/dafd)) |
| **Published** | *Nature Communications* (2020) |

- First ML-based microfluidic design automation tool.
- Trained on experimental datasets of flow-focusing droplet generators.
- **Forward mode:** Predict droplet size and frequency from device geometry and flow rates.
- **Inverse mode:** Specify target droplet properties; tool suggests geometries and flow conditions.
- Integrates with rapid prototyping and CAD workflows.
- No simulation required -- predictions in seconds.

#### ChatGPT-Assisted CAD Design

- Explored in *Lab on a Chip* (2023) for LLM-assisted microfluidic device CAD.
- LLMs can generate CAD scripts (OpenSCAD, FreeCAD macros), suggest design parameters, and assist with design iteration.
- Still experimental; not a replacement for domain expertise but useful for accelerating routine design tasks.

### Key Challenges for AI/ML in Microfluidics

1. **Limited training data:** Experimental microfluidic datasets are small (hundreds, not millions of samples) compared to ML norms. Synthetic data from CFD helps but introduces simulation bias.
2. **Standardization:** No standard data formats, benchmarks, or open datasets for microfluidic ML.
3. **Interpretability:** Complex neural network models are difficult to interpret physically; understanding *why* a design works matters for engineering insight.
4. **Generalization:** Models trained on one device type (e.g., flow-focusing droplet generators) do not transfer easily to other geometries (T-junctions, step emulsification).
5. **Validation gap:** ML predictions require experimental validation to close the design loop; in-silico accuracy does not guarantee fabrication success.
6. **Physics compliance:** Pure data-driven models may violate conservation laws; physics-informed approaches (PINNs, constrained architectures) help but add complexity.

---

## 7. Comparison Matrix

| Tool | Method | Scale | Typical Use | GPU | License | Ease of Use |
|---|---|---|---|---|---|---|
| **Palabos** | LBM | Meso (um-mm) | Multiphase droplet flows | Pre-release | AGPLv3 | Moderate |
| **OpenLB** | LBM | Meso (um-mm) | Diverse physics + droplets | Yes | GPLv2 | Moderate-Hard |
| **waLBerla** | LBM | Meso (extreme scale) | HPC multiphase | Yes (best) | GPLv3 | Hard |
| **DL_MESO** | DPD/LBM | Meso (nm-um) | Polymers, bio flows | Yes (CUDA) | Academic | Moderate |
| **HOOMD-blue** | DPD/MD/MC | Meso (nm-um) | GPU-native soft matter | Yes (native) | BSD-3 | Moderate |
| **LAMMPS (DPD)** | DPD | Meso (nm-um) | Soft matter in channels | Yes (KOKKOS) | GPLv2 | Moderate |
| **Surface Evolver** | Energy min. | Interface | Static droplet shapes | No | Public domain | Moderate-Hard |
| **LAMMPS (MD)** | MD | Nano (<100 nm) | Nanoscale transport | Yes (KOKKOS) | GPLv2 | Moderate |
| **FEniCS** | FEM | Macro (um-mm) | Stokes/NS flow, multiphysics | Experimental | LGPLv3 | Moderate-Hard |
| **FiPy** | FVM | Macro (um-mm) | Diffusion-reaction | No | NIST OSS | Easy |
| **Dedalus** | Spectral | Macro (simple geom.) | Instabilities, mixing | No | GPLv3 | Moderate |
| **QuickerSim** | FEM (MATLAB) | Macro (um-mm) | Laminar microfluidics | No | Commercial | Easy |
| **DAFD** | ML | Device-level | Droplet generator design | N/A | Free web | Easy |
| **muFG** | ML+math | Circuit-level | Flow distribution design | N/A | Free web | Easy |

---

## 8. Recommendations by Application

### Droplet Generation and Multiphase Flows

| Priority | Tool | Rationale |
|---|---|---|
| 1st | **Palabos** or **OpenLB** | Best open-source LBM for droplet microfluidics (OpenLB if GPU needed) |
| 2nd | **waLBerla** | Only for extreme-scale problems requiring billions of cells |
| Quick design | **DAFD** | ML-based; no simulation needed; seconds to get design suggestions |
| Static shapes | **Surface Evolver** | Equilibrium droplet shape on structured surfaces |

### Blood Flow and Biological Cell Transport

| Priority | Tool | Rationale |
|---|---|---|
| 1st | **HOOMD-blue** | GPU-native DPD; best performance for large cell simulations |
| 2nd | **DL_MESO** | Most comprehensive DPD implementation |
| 3rd | **LAMMPS (DPD/SDPD)** | If already using LAMMPS ecosystem |
| Coupled flow | **OpenLB** | LBM + resolved particles |

### Wetting, Contact Angles, and Capillary Phenomena

| Priority | Tool | Rationale |
|---|---|---|
| Static | **Surface Evolver** | Definitive tool for equilibrium interface shapes |
| Dynamic | **Palabos** or **OpenLB** | LBM multiphase with dynamic contact lines |
| Molecular | **LAMMPS (MD)** | When molecular-scale wetting detail is needed |

### Species Transport and Mixing

| Priority | Tool | Rationale |
|---|---|---|
| Simple geom. | **FiPy** (easiest) or **Dedalus** (highest accuracy) | Quick setup for diffusion-reaction problems |
| Complex geom. | **FEniCS** | Most flexible; handles arbitrary unstructured meshes |
| MATLAB users | **QuickerSim** | Stays within MATLAB ecosystem |
| With flow | **FEniCS** | Coupled Stokes + advection-diffusion |

### Nanoscale Transport (< 100 nm)

| Priority | Tool | Rationale |
|---|---|---|
| Primary | **LAMMPS (MD)** | Full atomistic detail where continuum breaks down |
| Mesoscale bridge | **LAMMPS (DPD)** or **HOOMD-blue** | Coarser than MD but captures hydrodynamics |
| Multiscale | **LAMMPS + OpenFOAM** | Hybrid atomistic-continuum coupling |

### Automated Design Optimization

| Priority | Tool | Rationale |
|---|---|---|
| Droplet generators | **DAFD** | Instant predictions; experimentally validated |
| Microfluidic circuits | **muFluidicGenius** | ML + fluid mechanics hybrid; 90% flow accuracy |
| Custom optimization | **Bayesian optimization + CFD** | 10x faster than evolutionary algorithms |
| Flow field prediction | **PINNs** | When sparse experimental data must be augmented |
| Exploratory | **ChatGPT-assisted CAD** | Rapid prototyping of design scripts |

### Quick Start for a New Lab

1. Start with **FEniCS** for general microfluidic flow simulation (most versatile open-source FEM).
2. Add **Surface Evolver** for capillary/wetting problems.
3. Use **DAFD** for rapid droplet generator design without simulation.
4. Add **Palabos** or **OpenLB** when multiphase LBM is needed.
5. Use **LAMMPS** only for nanoscale investigations.
6. Explore **Bayesian optimization** workflows for design space exploration.

---

## Sources

### LBM Tools
- [Palabos Official Site](https://palabos.unige.ch/)
- [Palabos Paper - Computers & Mathematics with Applications (2020)](https://www.sciencedirect.com/science/article/pii/S0898122120301267)
- [OpenLB Official Site](https://www.openlb.net/)
- [OpenLB Paper - Computers & Mathematics with Applications (2020)](https://www.sciencedirect.com/science/article/pii/S0898122120301875)
- [waLBerla - ResearchGate](https://www.researchgate.net/publication/225966632_WaLBerla_Exploiting_Massively_Parallel_Systems_for_Lattice_Boltzmann_Simulations)
- [List of LBM Codes - GitHub](https://github.com/sthavishtha/list-lattice-Boltzmann-codes)
- [LBM for Microfluidics Review - Microfluidics and Nanofluidics](https://link.springer.com/article/10.1007/s10404-010-0624-1)
- [LBM Tutorial Review for Inertial Particle Microfluidics (2023)](https://www.tandfonline.com/doi/full/10.1080/23746149.2023.2246704)
- [Navier-Stokes vs LBM Comparison - Fidelis Engineering](https://www.fidelisfea.com/post/navier-stokes-vs-lattice-boltzmann-for-cfd-a-comparative-analysis)
- [LBM Overview - SimScale](https://www.simscale.com/docs/simwiki/cfd-computational-fluid-dynamics/lattice-boltzmann-method-lbm/)

### DPD Tools
- [DL_MESO DPD Documentation](https://dl-sdg.github.io/RESOURCES/EXERCISES/DPD.html)
- [CCP5 DL_MESO DPD Exercises](https://ccp5.gitlab.io/dl_meso/DPDIntro.html)
- [HOOMD-blue Documentation](https://hoomd-blue.readthedocs.io/)
- [HOOMD-blue GitHub](https://github.com/glotzerlab/hoomd-blue)
- [Smoothed DPD Package for LAMMPS](https://www.sciencedirect.com/science/article/abs/pii/S0010465520300825)
- [DPD Overview and Recent Developments - Archives of Computational Methods](https://link.springer.com/article/10.1007/s11831-014-9124-x)
- [DPD for Advanced Microfluidics - Microfluidics and Nanofluidics](https://link.springer.com/article/10.1007/s10404-008-0375-4)
- [DPD Perspective - J. Chem. Phys. (2017)](https://pubs.aip.org/aip/jcp/article/146/15/150901/152357/Perspective-Dissipative-particle-dynamics)
- [DPD Modeling in Polymer Science (2025)](https://wires.onlinelibrary.wiley.com/doi/abs/10.1002/wcms.70018)
- [DPDsim GitHub](https://github.com/petervanya/DPDsim)

### Surface Evolver
- [Surface Evolver - Ken Brakke](https://kenbrakke.com/evolver/evolver.html)
- [Surface Evolver Manual (PDF)](https://kenbrakke.com/evolver/downloads/manual270.pdf)
- [The Physics of Microdroplets - Brakke & Berthier](https://kenbrakke.com/physicsofmicrodroplets/)
- [Surface Evolver - Wikipedia](https://en.wikipedia.org/wiki/Surface_Evolver)
- [Surface Evolver - Experimental Mathematics (1992)](https://www.tandfonline.com/doi/abs/10.1080/10586458.1992.10504253)
- [Droplet Wetting Morphologies - Frontiers (2021)](https://www.frontiersin.org/journals/energy-research/articles/10.3389/fenrg.2021.827116/full)
- [Surface Evolver for Membrane Emulsification](https://www.researchgate.net/publication/8335340_Using_the_Surface_Evolver_to_model_droplet_formation_processes_in_membrane_emulsification)

### LAMMPS
- [LAMMPS Official Site](https://www.lammps.org/)
- [LAMMPS-OpenFOAM Hybrid Model](https://www.sciencedirect.com/science/article/abs/pii/S0010465513001069)
- [MD for Nanoscale Liquid Flows - Microfluidics and Nanofluidics](https://link.springer.com/article/10.1007/s10404-010-0612-5)
- [MD Pre-simulations for Nanoscale CFD](https://link.springer.com/article/10.1007/s10404-014-1443-6)
- [Multiscale Computational Modeling of Nanofluidic Transport - MIT](https://dspace.mit.edu/bitstream/handle/1721.1/128996/1227037122-MIT.pdf)

### Python/MATLAB Libraries
- [FEniCS Project](https://fenicsproject.org/)
- [FEniCS - Wikipedia](https://en.wikipedia.org/wiki/FEniCS_Project)
- [FiPy - NIST](https://pages.nist.gov/fipy/en/latest/index.html)
- [FiPy Publication - NIST](https://www.nist.gov/publications/fipy-finite-volume-pde-solver-using-python)
- [Dedalus Project](https://dedalus-project.org/)
- [QuickerSim CFD Toolbox for MATLAB](https://quickersim.com/cfdtoolbox/microfluidics/)
- [FEATool / CFDTool](https://www.featool.com/matlab-cfd-toolbox/)
- [Python FEA with FEniCS and FEATool - Medium](https://medium.com/multiphysics/multiphysics-simulations-in-python-with-fenics-and-featool-310c775e5fdc)

### AI/ML-Based Design
- [Bayesian Optimization for Microfluidics - Lab on a Chip (2025)](https://pubs.rsc.org/en/content/articlehtml/2025/lc/d4lc00872c)
- [Deep Learning-Driven Chip Architecture - Lab on a Chip (2026)](https://pubs.rsc.org/en/content/articlehtml/2026/lc/d5lc01185j)
- [Automating Microfluidic Chip Design - Phys.org (2026)](https://phys.org/news/2026-02-automating-microfluidic-chip-hybrid-approach.html)
- [ML-Driven Innovations in Microfluidics - PMC (2024)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11674507/)
- [ML for Microfluidic Design and Control - PMC (2022)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9361804/)
- [PINNs for Multi-Physics Microfluidics (2024)](https://www.sciencedirect.com/science/article/pii/S0045793024002524)
- [PINNs for Fluid Mechanics Review (2025)](https://www.mdpi.com/2311-5521/10/9/226)
- [PINNs for Complex Fluids - Korea-Australia Rheology Journal (2025)](https://link.springer.com/article/10.1007/s13367-025-00140-6)
- [Automatic PINN Structure Discovery - Nature Communications (2025)](https://www.nature.com/articles/s41467-025-64624-3)
- [Neural Surrogate Models for CFD - ESANN (2025)](https://www.esann.org/sites/default/files/proceedings/2025/ES2025-70.pdf)
- [MeshGraphNets for CFD - NASA (2025)](https://www.nas.nasa.gov/pubs/ams/2025/07-10-25.html)
- [Intelligence-Driven CFD Paradigm (2024)](https://www.tandfonline.com/doi/full/10.1080/19942060.2024.2407005)
- [DAFD - CIDAR Lab](https://www.cidarlab.org/dafd)
- [Synergizing Microfluidics and ML (2025)](https://www.sciencedirect.com/science/article/abs/pii/S0026265X25022106)
