# Simulation Setup Tutorials for Microfluidics

> Practical, step-by-step guides for setting up simulations of common microfluidic
> problems using COMSOL, OpenFOAM, and Python-based tools. Includes analytical
> calculations, mesh convergence procedures, and validation strategies.

---

## 1. COMSOL Multiphysics Setup Guides

### 1.1 Laminar Flow in a Straight Microchannel

**Objective:** Compute velocity and pressure fields for single-phase flow in a
rectangular microchannel. This is the foundational simulation that validates your
setup before adding complexity.

**Physics Interface:** Laminar Flow (`spf`)

**Step-by-Step Procedure:**

1. **Create geometry**
   - 2D rectangle for a channel cross-section, or 3D block for full channel.
   - For long channels, use a 2D cross-section and extrude results analytically.
   - Typical dimensions: width 50--500 um, height 25--100 um, length 5--50 mm.
   - For 2D simplification of a 3D rectangular channel, enable the **Shallow
     Channel Approximation** (available in the Laminar Flow interface settings).
     This adds an extra volume force term to account for the out-of-plane wall
     friction, valid when channel height is much smaller than width.

2. **Add physics: Laminar Flow**
   - Default nodes created automatically: Fluid Properties, Wall (no-slip), Initial Values.
   - Set fluid properties (water: rho = 998 kg/m3, mu = 1.002e-3 Pa.s).
   - Inlet: use "Laminar inflow" or "Velocity" boundary condition.
     - For validation: use "Fully developed flow" to impose an analytical profile.
     - For realistic setup: specify volumetric flow rate (e.g., 1--50 uL/min).
   - Outlet: "Pressure" boundary condition, p = 0 (gauge pressure).
   - Walls: No-slip (default). For hydrophobic surfaces, consider Navier slip.

3. **Mesh settings**
   - Use "Physics-controlled mesh" initially, set to "Fine" or "Finer."
   - Add **boundary layer mesh** on all walls (at least 5 layers).
   - For rectangular channels, ensure at least 8--10 elements across the narrowest
     dimension.
   - Element type: triangular (2D) or tetrahedral (3D) with boundary layer prisms.

4. **Solver configuration**
   - Stationary study for steady flow.
   - Direct solver (MUMPS or PARDISO) for small/medium problems (<500k DOF).
   - Iterative solver (GMRES with multigrid preconditioner) for large 3D problems.
   - Check convergence: residuals should drop below 1e-6.

5. **Validation**
   - Compare centerline velocity to Poiseuille flow analytical solution.
   - Compare pressure drop to the rectangular channel formula (see Section 4).
   - Expected error: <1% with adequate mesh.

**Common Mistakes:**
- Forgetting boundary layers on walls, leading to inaccurate wall shear stress.
- Using too coarse a mesh in 3D and running out of memory -- start with 2D.
- Not checking Reynolds number: ensure Re < 2300 for the Laminar Flow interface.
- Setting absolute pressure at the outlet instead of gauge pressure.
- Incorrect units: COMSOL uses SI by default; microfluidic dimensions must be
  entered in meters (e.g., 100e-6 for 100 um) or the geometry units changed.

---

### 1.2 T-Junction Mixing Simulation

**Objective:** Simulate two miscible fluids meeting at a T-junction and predict
mixing efficiency along the outlet channel.

**Physics Interfaces:**
- Laminar Flow (`spf`) for velocity field
- Transport of Diluted Species (`tds`) for concentration field

**Step-by-Step Procedure:**

1. **Geometry**
   - Create a T-shaped 2D domain: main channel + side channel at 90 degrees.
   - Typical dimensions: channels 100--200 um wide, junction region needs fine mesh.
   - Add fillets (5--10 um radius) at the junction corners for better meshing and
     physical accuracy.

2. **Laminar Flow setup**
   - Two inlets: main channel and side channel.
   - Specify flow rates or velocities at each inlet.
   - One outlet with pressure = 0 boundary condition.
   - Solve the flow field first as a stationary study.

3. **Transport of Diluted Species setup**
   - Add species concentration variable (e.g., c).
   - Inlet 1: c = c0 (e.g., 1 mol/m3). Inlet 2: c = 0.
   - Diffusion coefficient: set D appropriately (e.g., 1e-9 m2/s for small molecules,
     1e-11 m2/s for proteins).
   - Convection is automatically coupled from the Laminar Flow velocity field.
   - Outlet: "Outflow" boundary condition (zero diffusive flux).
   - Walls: "No flux" boundary condition (default).

4. **Study sequence**
   - Option A: Coupled stationary study (flow + transport simultaneously).
   - Option B: Sequential -- solve flow first, then transport with the frozen
     velocity field. This is faster and often more stable.

5. **Mesh requirements**
   - The concentration boundary layer is thinner than the velocity boundary layer.
   - Rule of thumb: mesh for transport must be finer than for flow alone.
   - At the junction, use a local mesh refinement (element size 1--5 um).
   - Along the mixing channel, ensure at least 20 elements across the width.
   - Use "Extra fine" physics-controlled mesh, or customize with size expressions.

6. **Post-processing: Mixing efficiency**
   - Define mixing index at outlet cross-section:
     ```
     M = 1 - sqrt( (1/A) * integral( ((c - c_avg)/c_avg)^2 dA ) )
     ```
   - Plot concentration profile across the channel at several downstream positions.
   - Plot mixing index vs. downstream distance.

**Common Mistakes:**
- Numerical diffusion from a coarse mesh artificially inflates mixing.
- Not using stabilization (streamline diffusion) for high-Peclet-number transport,
  or conversely, excessive stabilization that smears the concentration field.
- Forgetting to couple the velocity field to the transport equation.
- Using time-dependent study when stationary is sufficient (wastes compute time).

---

### 1.3 Droplet Generation at a T-Junction (Two-Phase Flow)

**Objective:** Simulate immiscible droplet formation at a T-junction using the
Phase Field or Level Set method.

**Physics Interfaces (choose one pair):**
- Laminar Flow + Phase Field (`pf`) -- recommended for droplet problems
- Laminar Flow + Level Set (`ls`) -- alternative, simpler but less conservative

**Phase Field vs. Level Set:**
| Feature | Phase Field | Level Set |
|---------|-------------|-----------|
| Mass conservation | Excellent | Can lose mass |
| Interface thickness | Controlled by parameter | Controlled by reinitialization |
| Computational cost | Higher (4 extra equations) | Lower (2 extra equations) |
| Contact angle | Well-supported | Supported |
| Best for | Droplets, emulsions | Simple interfaces |

**Step-by-Step Procedure:**

1. **Geometry**
   - T-junction with main (continuous phase) and side (dispersed phase) channels.
   - Typical dimensions: 50--200 um channel widths.
   - 2D simulation is usually sufficient for initial studies.

2. **Phase Field interface setup**
   - Define two fluids with properties (density, viscosity).
   - Set interfacial tension (e.g., 5--50 mN/m for water/oil systems).
   - Contact angle on walls: typically 135--180 degrees for the dispersed phase
     (non-wetting condition on channel walls).
   - Mobility tuning parameter: start with the default; reduce if interface is
     too diffuse, increase if solver does not converge.
   - Interface thickness parameter (epsilon): typically 0.5--1x the mesh element
     size at the interface. Too large = smeared interface; too small = solver issues.

3. **Boundary conditions**
   - Continuous phase inlet: velocity or flow rate.
   - Dispersed phase inlet: velocity or flow rate.
   - Outlet: pressure = 0.
   - Walls: wetted wall with specified contact angle.

4. **Mesh**
   - Critical: the mesh must resolve the interface (at least 4--6 elements across
     the interface thickness).
   - Use adaptive mesh refinement near the interface if available.
   - Typical element size near the junction: 1--2 um for a 100 um channel.
   - Total element count for 2D: 20,000--100,000.

5. **Solver settings**
   - Time-dependent study (droplet generation is inherently transient).
   - BDF time stepping, order 1--2.
   - Maximum time step: ensure Courant number < 0.5.
   - Use automatic time stepping with a small initial time step (1e-6 s).
   - Total simulation time: enough to capture 3--5 droplet formation cycles.
   - Segregated solver approach often works better than fully coupled.

6. **Post-processing**
   - Track phase field variable to visualize droplets.
   - Measure droplet length, spacing, and generation frequency.
   - Compare to scaling laws (see Section 4.3).

**Common Mistakes:**
- Interface thickness parameter epsilon set incorrectly relative to mesh size.
- Insufficient mesh resolution at the interface causing numerical breakup.
- Time step too large, leading to Courant number violations and instability.
- Not running long enough to reach periodic steady state (discard first 2--3 droplets).
- Memory issues in 3D -- start with 2D and only go to 3D when necessary.

---

## 2. OpenFOAM Setup Guides

### 2.1 Single-Phase Laminar Flow with simpleFoam

**Objective:** Simulate steady-state laminar flow in a microchannel using OpenFOAM.

**Solver:** `simpleFoam` (steady-state, incompressible, laminar)

**Directory Structure:**
```
case/
  0/          # Initial and boundary conditions
    U         # Velocity field
    p         # Pressure field
  constant/
    transportProperties   # Fluid properties
    polyMesh/             # Mesh files
  system/
    controlDict           # Run control
    fvSchemes             # Discretization schemes
    fvSolution            # Solver settings
    blockMeshDict         # Mesh generation
```

**Step-by-Step Procedure:**

1. **Mesh generation with blockMesh**

   Example `blockMeshDict` for a straight rectangular channel (2D with one cell
   in z-direction):
   ```cpp
   FoamFile
   {
       version     2.0;
       format      ascii;
       class       dictionary;
       object      blockMeshDict;
   }

   convertToMeters 1e-6;  // work in micrometers

   vertices
   (
       (0    0    0)       // vertex 0
       (5000 0    0)       // vertex 1 (5 mm length)
       (5000 100  0)       // vertex 2 (100 um width)
       (0    100  0)       // vertex 3
       (0    0    50)      // vertex 4 (50 um depth, 1 cell)
       (5000 0    50)      // vertex 5
       (5000 100  50)      // vertex 6
       (0    100  50)      // vertex 7
   );

   blocks
   (
       hex (0 1 2 3 4 5 6 7)  // block definition
       (500 20 1)              // cells: 500 along length, 20 across width
       simpleGrading (1 1 1)   // uniform grading
   );

   boundary
   (
       inlet
       {
           type patch;
           faces ( (0 4 7 3) );
       }
       outlet
       {
           type patch;
           faces ( (1 2 6 5) );
       }
       walls
       {
           type wall;
           faces (
               (0 1 5 4)   // bottom wall
               (3 7 6 2)   // top wall
           );
       }
       frontAndBack
       {
           type empty;      // 2D simulation
           faces (
               (0 3 2 1)
               (4 5 6 7)
           );
       }
   );
   ```

2. **Transport properties** (`constant/transportProperties`)
   ```cpp
   transportModel  Newtonian;
   nu              [0 2 -1 0 0 0 0] 1.004e-06;  // kinematic viscosity of water
   ```

3. **Boundary conditions**

   `0/U` (velocity):
   ```cpp
   dimensions      [0 1 -1 0 0 0 0];
   internalField   uniform (0 0 0);
   boundaryField
   {
       inlet
       {
           type            flowRateInletVelocity;
           volumetricFlowRate  constant 8.33e-11;  // 5 uL/min in m3/s
           value           uniform (0 0 0);
       }
       outlet
       {
           type            zeroGradient;
       }
       walls
       {
           type            noSlip;
       }
       frontAndBack
       {
           type            empty;
       }
   }
   ```

   `0/p` (pressure):
   ```cpp
   dimensions      [0 2 -2 0 0 0 0];
   internalField   uniform 0;
   boundaryField
   {
       inlet
       {
           type            zeroGradient;
       }
       outlet
       {
           type            fixedValue;
           value           uniform 0;
       }
       walls
       {
           type            zeroGradient;
       }
       frontAndBack
       {
           type            empty;
       }
   }
   ```

4. **Turbulence model** (`constant/momentumTransport` or `constant/turbulenceProperties`)
   ```cpp
   simulationType  laminar;
   ```

5. **Numerical schemes** (`system/fvSchemes`)
   ```cpp
   ddtSchemes      { default steadyState; }
   gradSchemes     { default Gauss linear; }
   divSchemes
   {
       default         none;
       div(phi,U)      bounded Gauss linearUpwind grad(U);
   }
   laplacianSchemes { default Gauss linear corrected; }
   interpolationSchemes { default linear; }
   snGradSchemes    { default corrected; }
   ```

6. **Solver settings** (`system/fvSolution`)
   ```cpp
   solvers
   {
       p
       {
           solver          GAMG;
           tolerance       1e-08;
           relTol          0.01;
           smoother        GaussSeidel;
       }
       U
       {
           solver          smoothSolver;
           smoother        GaussSeidel;
           tolerance       1e-08;
           relTol          0.01;
       }
   }
   SIMPLE
   {
       residualControl
       {
           p               1e-6;
           U               1e-6;
       }
   }
   relaxationFactors
   {
       fields  { p 0.3; }
       equations { U 0.7; }
   }
   ```

7. **Run**
   ```bash
   blockMesh
   simpleFoam
   ```

---

### 2.2 Two-Phase Droplet Generation with interFoam

**Objective:** Simulate droplet formation at a T-junction using the Volume of
Fluid (VOF) method.

**Solver:** `interFoam` (transient, incompressible, two-phase VOF)

**Key Configuration Differences from Single-Phase:**

1. **Transport properties** (`constant/transportProperties`)
   ```cpp
   phases (water oil);

   water
   {
       transportModel  Newtonian;
       nu              [0 2 -1 0 0 0 0] 1.004e-06;
       rho             [1 -3 0 0 0 0 0] 998;
   }
   oil
   {
       transportModel  Newtonian;
       nu              [0 2 -1 0 0 0 0] 5e-05;
       rho             [1 -3 0 0 0 0 0] 850;
   }

   sigma           [1 0 -2 0 0 0 0] 0.025;  // interfacial tension N/m
   ```

2. **Phase fraction field** (`0/alpha.water`)
   ```cpp
   dimensions      [0 0 0 0 0 0 0];
   internalField   uniform 0;  // initially filled with oil

   boundaryField
   {
       inlet_water
       {
           type            fixedValue;
           value           uniform 1;     // water enters here
       }
       inlet_oil
       {
           type            fixedValue;
           value           uniform 0;     // oil enters here
       }
       outlet
       {
           type            inletOutlet;
           inletValue      uniform 0;
           value           uniform 0;
       }
       walls
       {
           type            constantAlphaContactAngle;
           theta0          135;
           limit           gradient;
           value           uniform 0;
       }
       frontAndBack
       {
           type            empty;
       }
   }
   ```

3. **Time step control** (`system/controlDict`)
   ```cpp
   application     interFoam;
   startFrom       startTime;
   startTime       0;
   stopAt          endTime;
   endTime         0.01;          // 10 ms total simulation
   deltaT          1e-7;          // initial time step
   adjustTimeStep  yes;
   maxCo           0.5;           // max Courant number
   maxAlphaCo      0.5;           // max interface Courant number
   maxDeltaT       1e-5;          // max allowed time step
   writeControl    adjustableRunTime;
   writeInterval   1e-4;
   ```

4. **Phase equation settings** (`system/fvSolution`)
   ```cpp
   "alpha.water.*"
   {
       nAlphaCorr      2;
       nAlphaSubCycles 1;
       cAlpha          1;           // interface compression (1 = standard)

       MULESCorr       yes;
       nLimiterIter    3;
       solver          smoothSolver;
       smoother        symGaussSeidel;
       tolerance       1e-8;
       relTol          0;
   }
   ```

5. **Mesh considerations for two-phase microfluidics**
   - Use `snappyHexMesh` for complex junction geometries with local refinement.
   - Refine near walls to capture the thin film between droplet and wall (at least
     3--4 cells in the film).
   - Near the junction, element size should be approximately 1/20 of channel width.
   - Use graded mesh: fine at junction, coarser downstream.
   - Typical cell count for 2D T-junction: 50,000--200,000 cells.

6. **Dealing with spurious currents**
   - At low capillary numbers (Ca < 0.01), interFoam can produce unphysical
     parasitic currents near the interface.
   - Mitigation: use finer mesh near the interface, ensure cAlpha = 1 (not higher),
     and consider the `interIsoFoam` solver which uses geometric VOF reconstruction
     for sharper interfaces and reduced spurious currents.

**Post-Processing with ParaView:**
```bash
# Convert OpenFOAM data to VTK format
foamToVTK

# Or open directly in ParaView with OpenFOAM reader:
paraFoam
# In ParaView:
# - Color by alpha.water to visualize phases
# - Use "Contour" filter at alpha.water = 0.5 to extract interface
# - Use "Plot Over Line" to get velocity/pressure profiles
# - Use "Integrate Variables" on a slice to compute flow rates
```

---

### 2.3 OpenFOAM Tips for Microfluidics

**Scaling issues:**
- OpenFOAM works in SI units. Microfluidic dimensions (micrometers) can cause
  numerical precision issues.
- Strategy 1: Use `convertToMeters` in blockMeshDict (as shown above).
- Strategy 2: Scale up the geometry by 1000x and adjust fluid properties accordingly
  to maintain the same Reynolds number.

**Boundary condition reference for microfluidics:**
| BC Purpose | Velocity (U) | Pressure (p) |
|-----------|-------------|-------------|
| Flow rate inlet | `flowRateInletVelocity` | `zeroGradient` |
| Velocity inlet | `fixedValue` | `zeroGradient` |
| Pressure inlet | `pressureInletOutletVelocity` | `fixedValue` |
| Pressure outlet | `zeroGradient` or `inletOutlet` | `fixedValue` (0) |
| No-slip wall | `noSlip` | `zeroGradient` |
| Symmetry plane | `symmetry` | `symmetry` |
| 2D front/back | `empty` | `empty` |

**Parallel execution:**
```bash
# Decompose the domain
decomposePar -force

# Run in parallel
mpirun -np 4 simpleFoam -parallel

# Reconstruct results
reconstructPar
```

---

## 3. Python-Based Simulation

### 3.1 FEniCS/FEniCSx: Stokes and Navier-Stokes Flow

FEniCS provides a high-level Python interface for solving PDEs using the finite
element method. It is well-suited for microfluidic flow problems where custom
geometries and coupled physics are needed.

**Installation:**
```bash
# FEniCSx (current version) via conda
conda install -c conda-forge fenics-dolfinx mpich pyvista

# Legacy FEniCS via Docker
docker run -ti -v $(pwd):/home/fenics/shared quay.io/fenicsproject/stable
```

**Example: Poiseuille Flow in a 2D Channel (Stokes)**
```python
"""
Stokes flow in a 2D rectangular channel.
Validates against analytical Poiseuille solution.
"""
import numpy as np
from mpi4py import MPI
from dolfinx import mesh, fem, io
from dolfinx.fem.petsc import LinearProblem
import ufl

# ---- Parameters ----
L = 5e-3       # channel length (5 mm)
H = 100e-6     # channel height (100 um)
mu = 1e-3      # dynamic viscosity (Pa.s)
dp_dx = -1000  # pressure gradient (Pa/m)
nx, ny = 200, 20

# ---- Mesh ----
domain = mesh.create_rectangle(
    MPI.COMM_WORLD,
    [np.array([0, 0]), np.array([L, H])],
    [nx, ny],
    cell_type=mesh.CellType.triangle
)

# ---- Function spaces (Taylor-Hood P2/P1) ----
P2 = ufl.VectorElement("Lagrange", domain.ufl_cell(), 2)
P1 = ufl.FiniteElement("Lagrange", domain.ufl_cell(), 1)
TH = ufl.MixedElement([P2, P1])
W = fem.functionspace(domain, TH)

# ---- Boundary conditions ----
# No-slip on top and bottom walls
def walls(x):
    return np.isclose(x[1], 0) | np.isclose(x[1], H)

# Pressure at inlet and outlet
def inlet(x):
    return np.isclose(x[0], 0)

def outlet(x):
    return np.isclose(x[0], L)

# ... (boundary condition application follows FEniCSx patterns)

# ---- Weak form (Stokes) ----
# Find (u, p) in W such that:
#   mu * inner(grad(u), grad(v)) * dx - p * div(v) * dx = f . v * dx
#   div(u) * q * dx = 0
# for all (v, q) in W

(u, p) = ufl.TrialFunctions(W)
(v, q) = ufl.TestFunctions(W)

f = fem.Constant(domain, (dp_dx, 0.0))  # body force (pressure gradient)

a = (mu * ufl.inner(ufl.grad(u), ufl.grad(v)) * ufl.dx
     - p * ufl.div(v) * ufl.dx
     + ufl.div(u) * q * ufl.dx)

L_form = ufl.inner(f, v) * ufl.dx

# ---- Solve and compare to analytical ----
# Analytical Poiseuille: u(y) = (1/(2*mu)) * |dp/dx| * y * (H - y)
# u_max = |dp/dx| * H^2 / (8 * mu)
u_max_analytical = abs(dp_dx) * H**2 / (8 * mu)
print(f"Analytical u_max = {u_max_analytical*1e3:.4f} mm/s")
```

**Key Points for FEniCS Microfluidics:**
- Use Taylor-Hood elements (P2/P1) for velocity/pressure to satisfy the
  inf-sup (LBB) stability condition.
- For Stokes flow (Re << 1, typical in microfluidics), drop the nonlinear
  convective term -- the problem becomes linear and solves in one step.
- For species transport, add a second function space and solve the
  advection-diffusion equation coupled to the velocity field.

---

### 3.2 FiPy: Diffusion-Reaction in Microchannels

FiPy (developed by NIST) is a finite volume PDE solver ideal for
diffusion-reaction problems common in microfluidic biosensors and reactors.

**Installation:**
```bash
pip install fipy
```

**Example: 1D Diffusion of Analyte Across a Channel**
```python
"""
Transient diffusion of a species across a microchannel width.
Models the concentration profile evolution when two streams meet.
"""
import fipy as fp
import numpy as np

# ---- Parameters ----
W = 100e-6      # channel width (m)
D = 1e-9        # diffusion coefficient (m2/s)
c0 = 1.0        # initial concentration on one side (mol/m3)
nx = 100         # number of cells
dx = W / nx
dt = 0.001       # time step (s)
steps = 500

# ---- Mesh and variable ----
mesh = fp.Grid1D(dx=dx, nx=nx)
c = fp.CellVariable(name="concentration", mesh=mesh, value=0.0)

# Initial condition: step function at center
c.setValue(c0, where=mesh.cellCenters[0] < W/2)

# ---- Boundary conditions ----
# No flux at both walls (default for FiPy)

# ---- Equation: dc/dt = D * d2c/dx2 ----
eq = fp.TransientTerm() == fp.DiffusionTerm(coeff=D)

# ---- Solve ----
results = []
for step in range(steps):
    eq.solve(var=c, dt=dt)
    if step % 50 == 0:
        results.append(c.value.copy())

# ---- Analytical validation ----
# For diffusion of a step function, solution involves error function:
# c(x,t) = (c0/2) * erfc((x - W/2) / (2*sqrt(D*t)))
from scipy.special import erfc
t_final = steps * dt
x = np.array(mesh.cellCenters[0])
c_analytical = (c0/2) * erfc((x - W/2) / (2*np.sqrt(D*t_final)))
error = np.max(np.abs(c.value - c_analytical))
print(f"Max error vs analytical: {error:.6f} mol/m3")
```

**Example: Advection-Diffusion in a Channel (2D)**
```python
"""
2D advection-diffusion: species transport in a channel with Poiseuille flow.
"""
import fipy as fp
import numpy as np

# ---- Parameters ----
L = 5e-3         # channel length
W = 100e-6       # channel width
D = 1e-9         # diffusion coefficient
u_max = 0.01     # max velocity (m/s)
nx, ny = 500, 50

# ---- Mesh ----
mesh = fp.Grid2D(dx=L/nx, dy=W/ny, nx=nx, ny=ny)
x, y = mesh.cellCenters

# ---- Poiseuille velocity field ----
# u(y) = 4 * u_max * y/W * (1 - y/W)
ux = 4 * u_max * (y / W) * (1.0 - y / W)
uy = fp.CellVariable(mesh=mesh, value=0.0)
velocity = fp.FaceVariable(mesh=mesh, rank=1)
# (Interpolate cell velocities to faces for the convection term)

# ---- Concentration variable ----
c = fp.CellVariable(name="concentration", mesh=mesh, value=0.0)
# Inlet BC: c = 1 on left boundary bottom half, c = 0 on top half
c.constrain(1.0, where=mesh.facesLeft & (mesh.faceCenters[1] < W/2))
c.constrain(0.0, where=mesh.facesLeft & (mesh.faceCenters[1] >= W/2))

# ---- Equation ----
eq = (fp.TransientTerm() == fp.DiffusionTerm(coeff=D)
      - fp.ConvectionTerm(coeff=velocity))

# ---- Solve time-dependent ----
dt = 1e-4
for step in range(1000):
    eq.solve(var=c, dt=dt)
```

---

### 3.3 Other Python Tools

**PyManifold** -- schematic-level microfluidic circuit simulation:
```bash
pip install pymanifold
```
- Models microfluidic networks as nodes, connections, and constraints.
- Useful for calculating pressure and flow distribution in complex channel networks.
- Does not do full CFD; uses hydraulic resistance models.

**MMFT Simulator** (Munich Microfluidics Toolkit):
- Collection of simulators for closed-channel microfluidic devices.
- Provides Python interfaces for network-level and 1D simulations.
- Available at: https://github.com/cda-tum/mmft-simulator

**MPh** -- Python interface to COMSOL:
```python
import mph
client = mph.start()
model = client.load('microfluidic_mixer.mph')
model.solve()
# Extract data for post-processing in Python
```

---

## 4. Quick Analytical Calculations

These Python functions provide rapid estimates for microfluidic design without
running full simulations. Use them for initial design and for validating CFD results.

### 4.1 Pressure Drop Calculator

```python
"""
Pressure drop calculations for common microchannel geometries.
"""
import numpy as np

def pressure_drop_rectangular(Q, mu, L, W, H):
    """
    Pressure drop in a rectangular microchannel.

    Uses the Mortensen et al. approximation for rectangular ducts.
    Valid for any aspect ratio W/H.

    Parameters
    ----------
    Q : float - volumetric flow rate (m3/s)
    mu : float - dynamic viscosity (Pa.s)
    L : float - channel length (m)
    W : float - channel width (m), W >= H
    H : float - channel height (m)

    Returns
    -------
    dP : float - pressure drop (Pa)
    R_h : float - hydraulic resistance (Pa.s/m3)
    """
    if H > W:
        W, H = H, W  # ensure W >= H

    # Approximate formula (Bruus, "Theoretical Microfluidics")
    # Valid to within ~0.5% for any aspect ratio
    alpha = H / W  # aspect ratio <= 1
    correction = 1 - 0.630 * alpha  # Purday correction factor

    R_h = (12 * mu * L) / (W * H**3 * correction)
    dP = R_h * Q

    return dP, R_h


def pressure_drop_circular(Q, mu, L, D):
    """
    Hagen-Poiseuille pressure drop for circular channel.

    Parameters
    ----------
    Q : float - volumetric flow rate (m3/s)
    mu : float - dynamic viscosity (Pa.s)
    L : float - channel length (m)
    D : float - channel diameter (m)

    Returns
    -------
    dP : float - pressure drop (Pa)
    R_h : float - hydraulic resistance (Pa.s/m3)
    """
    R = D / 2
    R_h = (8 * mu * L) / (np.pi * R**4)
    dP = R_h * Q
    return dP, R_h


def hydraulic_diameter(W, H):
    """Hydraulic diameter for rectangular cross-section."""
    return 2 * W * H / (W + H)


# ---- Example ----
if __name__ == "__main__":
    Q = 10e-6 / 60 * 1e-6   # 10 uL/min -> m3/s
    mu = 1e-3                 # water viscosity
    L = 20e-3                 # 20 mm channel
    W = 200e-6                # 200 um wide
    H = 50e-6                 # 50 um tall

    dP, R_h = pressure_drop_rectangular(Q, mu, L, W, H)
    print(f"Flow rate:    {Q*1e9:.2f} nL/s = {Q*60*1e9:.1f} uL/min")
    print(f"Pressure drop: {dP:.0f} Pa = {dP/1e5:.4f} bar = {dP*0.000145:.2f} psi")
    print(f"Hydraulic resistance: {R_h:.3e} Pa.s/m3")
    print(f"Hydraulic diameter: {hydraulic_diameter(W, H)*1e6:.1f} um")
    print(f"Reynolds number: {998 * (Q/(W*H)) * hydraulic_diameter(W,H) / mu:.2f}")
```

### 4.2 Mixing Length Estimation

```python
"""
Estimate the channel length required for diffusive mixing.
"""
import numpy as np

def mixing_length_diffusive(W, U, D, mixing_fraction=0.9):
    """
    Required channel length for diffusive mixing of two co-flowing streams.

    Based on scaling analysis: L_mix ~ Pe * W, where Pe = U*W/D.
    More precisely, uses the solution for mixing of two parallel streams.

    Parameters
    ----------
    W : float - channel width (m) -- distance over which species must diffuse
    U : float - mean flow velocity (m/s)
    D : float - diffusion coefficient (m2/s)
    mixing_fraction : float - desired mixing completeness (0 to 1)

    Returns
    -------
    L_mix : float - required channel length (m)
    Pe : float - Peclet number
    t_mix : float - mixing time (s)
    """
    Pe = U * W / D
    # For 90% mixing of two co-flowing streams:
    # L_mix approx = Pe * W / (2 * pi^2) * (-ln(1 - mixing_fraction)) * correction
    # Simplified scaling: L_mix ~ 0.1 * Pe * W (for ~90% mixing)
    # More rigorous from Fourier series solution:
    t_mix = W**2 / (2 * np.pi**2 * D) * (-np.log(1 - mixing_fraction))
    L_mix = U * t_mix

    return L_mix, Pe, t_mix


def mixing_length_staggered_herringbone(W, H, U, D, n_cycles=None):
    """
    Estimate mixing length for a staggered herringbone mixer (SHM).

    SHM creates chaotic advection, reducing mixing length dramatically.
    Strouhal mixing reduces effective diffusion length to the striation
    thickness, which decreases exponentially with number of cycles.

    Parameters
    ----------
    W : float - channel width (m)
    H : float - channel height (m)
    U : float - mean velocity (m/s)
    D : float - diffusion coefficient (m2/s)

    Returns
    -------
    L_mix_shm : float - approximate mixing length with SHM (m)
    L_mix_plain : float - mixing length without mixer (m)
    improvement : float - fold reduction in length
    """
    Pe = U * W / D
    L_mix_plain = 0.1 * Pe * W  # plain channel

    # SHM typically achieves mixing in L ~ W * ln(Pe) (Stroock et al.)
    L_mix_shm = W * np.log(Pe) * 10  # empirical factor ~10 for practical SHM

    improvement = L_mix_plain / L_mix_shm

    return L_mix_shm, L_mix_plain, improvement


# ---- Example ----
if __name__ == "__main__":
    W = 100e-6   # 100 um channel
    U = 0.01     # 10 mm/s mean velocity
    D = 1e-9     # small molecule in water

    L, Pe, t = mixing_length_diffusive(W, U, D)
    print(f"Peclet number: {Pe:.0f}")
    print(f"Mixing time: {t:.1f} s")
    print(f"Required length (plain channel): {L*1e3:.1f} mm")

    L_shm, L_plain, impr = mixing_length_staggered_herringbone(W, 50e-6, U, D)
    print(f"\nWith staggered herringbone mixer:")
    print(f"  Required length: {L_shm*1e3:.1f} mm")
    print(f"  Improvement factor: {impr:.0f}x shorter")

    # Protein example (much slower diffusion)
    D_protein = 5e-11
    L_prot, Pe_prot, t_prot = mixing_length_diffusive(W, U, D_protein)
    print(f"\nProtein mixing (D={D_protein:.0e} m2/s):")
    print(f"  Pe = {Pe_prot:.0f}, L_mix = {L_prot:.0f} mm -- impractical!")
    print(f"  --> Active or chaotic mixing is essential for proteins")
```

### 4.3 Droplet Size Prediction

```python
"""
Predict droplet size in T-junction and flow-focusing geometries.
"""
import numpy as np

def droplet_size_t_junction(w_c, Q_d, Q_c, mu_c, sigma, regime="auto"):
    """
    Predict droplet length in a T-junction microfluidic device.

    Uses scaling laws from Garstecki et al. (Lab Chip, 2006).

    Parameters
    ----------
    w_c : float - width of continuous phase channel (m)
    Q_d : float - dispersed phase flow rate (m3/s)
    Q_c : float - continuous phase flow rate (m3/s)
    mu_c : float - continuous phase viscosity (Pa.s)
    sigma : float - interfacial tension (N/m)
    regime : str - "squeezing", "dripping", or "auto"

    Returns
    -------
    L_drop : float - predicted droplet length (m)
    Ca : float - capillary number
    regime_detected : str - detected flow regime
    """
    # Mean velocity of continuous phase
    # Assume square cross section for simplicity
    U_c = Q_c / (w_c**2)

    # Capillary number
    Ca = mu_c * U_c / sigma

    # Flow rate ratio
    phi = Q_d / Q_c

    # Determine regime
    if regime == "auto":
        if Ca < 0.002:
            regime_detected = "squeezing"
        elif Ca < 0.01:
            regime_detected = "transition"
        else:
            regime_detected = "dripping"
    else:
        regime_detected = regime

    if regime_detected == "squeezing":
        # Garstecki scaling law: L/w = 1 + alpha * (Q_d/Q_c)
        alpha = 1.0  # fitting parameter, typically 0.5 -- 2
        L_drop = w_c * (1 + alpha * phi)
    elif regime_detected == "dripping":
        # Shear-dominated: L/w ~ Ca^(-1/3) * phi^(1/3)  (approximate)
        L_drop = w_c * Ca**(-1/3) * phi**(1/3) * 0.5  # empirical prefactor
    else:  # transition
        # Interpolate
        L_squeeze = w_c * (1 + phi)
        L_drip = w_c * Ca**(-1/3) * phi**(1/3) * 0.5
        L_drop = (L_squeeze + L_drip) / 2

    return L_drop, Ca, regime_detected


def droplet_frequency(Q_d, V_drop):
    """
    Estimate droplet generation frequency.

    Parameters
    ----------
    Q_d : float - dispersed phase flow rate (m3/s)
    V_drop : float - droplet volume (m3)

    Returns
    -------
    f : float - frequency (Hz)
    """
    return Q_d / V_drop


# ---- Example ----
if __name__ == "__main__":
    w_c = 100e-6       # 100 um channel
    Q_d = 0.5e-6/60    # 0.5 uL/min -> m3/s
    Q_c = 2e-6/60      # 2 uL/min -> m3/s
    mu_c = 3e-3        # mineral oil viscosity
    sigma = 0.01       # water-oil interfacial tension

    L, Ca, regime = droplet_size_t_junction(w_c, Q_d, Q_c, mu_c, sigma)
    print(f"Capillary number: {Ca:.4f}")
    print(f"Flow regime: {regime}")
    print(f"Predicted droplet length: {L*1e6:.1f} um")
    print(f"Droplet length / channel width: {L/w_c:.2f}")

    # Estimate volume (assuming plug shape: cylinder + 2 hemispheres)
    R = w_c / 2
    V_drop = np.pi * R**2 * (L - 2*R) + (4/3) * np.pi * R**3
    print(f"Estimated droplet volume: {V_drop*1e12:.2f} nL")

    f = droplet_frequency(Q_d, V_drop)
    print(f"Estimated generation frequency: {f:.1f} Hz")
```

### 4.4 Residence Time Distribution

```python
"""
Residence time distribution (RTD) for microfluidic channels.
"""
import numpy as np
from scipy.special import erfc

def rtd_laminar_tube(t, t_mean, D_ax=None, L=None):
    """
    Residence time distribution for laminar flow in a tube.

    Without axial dispersion (Taylor dispersion neglected):
        E(t) = t_mean^2 / (2 * t^3)  for t >= t_mean/2

    With Taylor dispersion:
        E(t) = (1/sqrt(4*pi*D_eff*t/U^2)) * exp(-(L - U*t)^2 / (4*D_eff*t))

    Parameters
    ----------
    t : array - time values (s)
    t_mean : float - mean residence time L/U_mean (s)
    D_ax : float, optional - axial dispersion coefficient (m2/s)
    L : float, optional - channel length (m), needed if D_ax given

    Returns
    -------
    E : array - RTD function E(t) (1/s), normalized so integral = 1
    """
    if D_ax is None or L is None:
        # Pure laminar (no dispersion)
        E = np.zeros_like(t)
        mask = t >= t_mean / 2
        E[mask] = t_mean**2 / (2 * t[mask]**3)
        return E
    else:
        # Taylor dispersion model (plug flow with dispersion)
        U = L / t_mean
        Pe_ax = U * L / D_ax
        E = np.sqrt(Pe_ax / (4 * np.pi * t / t_mean)) * \
            np.exp(-Pe_ax * (1 - t/t_mean)**2 / (4 * t/t_mean))
        E /= t_mean
        return E


def taylor_dispersion_coefficient(U, R, D):
    """
    Taylor-Aris dispersion coefficient for a circular tube.

    D_eff = D + U^2 * R^2 / (48 * D)

    Parameters
    ----------
    U : float - mean velocity (m/s)
    R : float - tube radius (m)
    D : float - molecular diffusion coefficient (m2/s)

    Returns
    -------
    D_eff : float - effective axial dispersion coefficient (m2/s)
    """
    return D + (U**2 * R**2) / (48 * D)


def mean_residence_time(L, Q, W, H):
    """Mean residence time for rectangular channel."""
    A = W * H
    U = Q / A
    return L / U


# ---- Example ----
if __name__ == "__main__":
    L = 50e-3       # 50 mm channel
    W = 200e-6      # 200 um
    H = 50e-6       # 50 um
    Q = 5e-6/60     # 5 uL/min

    t_mean = mean_residence_time(L, Q, W, H)
    U_mean = Q / (W * H)
    R_eff = np.sqrt(W * H / np.pi)  # equivalent radius
    D = 1e-9

    D_eff = taylor_dispersion_coefficient(U_mean, R_eff, D)

    print(f"Mean velocity: {U_mean*1e3:.2f} mm/s")
    print(f"Mean residence time: {t_mean:.2f} s")
    print(f"Taylor dispersion coeff: {D_eff:.3e} m2/s")
    print(f"  (vs molecular D = {D:.0e} m2/s)")
    print(f"  Enhancement factor: {D_eff/D:.0f}x")

    # Plot RTD
    t = np.linspace(0.01, 3*t_mean, 1000)
    E_laminar = rtd_laminar_tube(t, t_mean)
    E_taylor = rtd_laminar_tube(t, t_mean, D_ax=D_eff, L=L)
    # (Plot with matplotlib as needed)
```

---

## 5. Mesh Independence and Validation

### 5.1 How to Perform a Mesh Convergence Study

A mesh convergence study (also called mesh independence study or grid refinement
study) is mandatory before trusting any CFD result. The procedure:

**Step-by-step:**

1. **Choose a target quantity** -- the result you care about most:
   - Pressure drop across the device
   - Maximum velocity at a cross-section
   - Mixing efficiency at the outlet
   - Droplet length or generation frequency

2. **Create a sequence of meshes** (at least 4, ideally 5--6):
   - Each mesh should have approximately 1.5--2x the number of elements of the
     previous one (or equivalently, element size reduced by factor ~1.3--1.5).
   - Example sequence: 5k, 10k, 20k, 40k, 80k elements.

3. **Run the simulation on each mesh** with identical settings.

4. **Tabulate results:**

   | Mesh | Elements | Element size (um) | dP (Pa) | u_max (m/s) | CPU time (s) |
   |------|----------|-------------------|---------|-------------|--------------|
   | M1   | 5,000    | 10.0              | 485     | 0.0089      | 5            |
   | M2   | 10,000   | 7.1               | 502     | 0.0094      | 12           |
   | M3   | 20,000   | 5.0               | 510     | 0.0096      | 35           |
   | M4   | 40,000   | 3.5               | 513     | 0.00965     | 120          |
   | M5   | 80,000   | 2.5               | 514     | 0.00968     | 450          |

5. **Check convergence:** when the target quantity changes by less than 1--2%
   between successive meshes, the solution is mesh-independent.

6. **Select the mesh** that balances accuracy and computational cost (typically
   M3 or M4 in the example above).

**Grid Convergence Index (GCI):**

For rigorous reporting, compute the GCI following Roache's method:

```python
def grid_convergence_index(f1, f2, f3, r, p=None, Fs=1.25):
    """
    Compute Grid Convergence Index (GCI) for three meshes.

    Parameters
    ----------
    f1 : float - result on finest mesh
    f2 : float - result on medium mesh
    f3 : float - result on coarsest mesh
    r : float - grid refinement ratio (h_coarse / h_fine), typically 1.3-2.0
    p : float, optional - observed order of convergence (computed if None)
    Fs : float - safety factor (1.25 for 3+ grids, 3.0 for 2 grids)

    Returns
    -------
    GCI_fine : float - GCI for fine grid (% uncertainty)
    p_observed : float - observed order of convergence
    """
    if p is None:
        # Observed order of convergence
        p = np.log(abs((f3 - f2) / (f2 - f1))) / np.log(r)

    # Relative error
    e = abs((f1 - f2) / f1)

    # GCI
    GCI_fine = Fs * e / (r**p - 1) * 100  # percentage

    return GCI_fine, p


# Example
f_coarse = 485   # pressure drop on coarse mesh
f_medium = 510   # pressure drop on medium mesh
f_fine = 514     # pressure drop on fine mesh
r = 2.0**(1/2)   # element count doubles -> size ratio = sqrt(2) in 2D

gci, p = grid_convergence_index(f_fine, f_medium, f_coarse, r)
print(f"Observed order of convergence: {p:.2f}")
print(f"GCI (fine grid): {gci:.2f}%")
print(f"  -> Estimated uncertainty in fine-grid result: +/- {gci:.2f}%")
```

### 5.2 Recommended Mesh Sizes for Microfluidics

| Application | Minimum elements across width | Typical element size | Notes |
|-------------|------------------------------|---------------------|-------|
| Single-phase flow (velocity/pressure) | 10--15 | W/10 to W/15 | Boundary layers need 5+ layers |
| Species transport (mixing) | 20--40 | W/20 to W/40 | Concentration BL is thinner than velocity BL |
| Two-phase (droplet) at interface | 15--30 across interface region | 1--3 um | Use local refinement at interface |
| Two-phase (thin film near wall) | 3--5 in the film | 0.5--2 um | Critical for correct droplet shape |
| Electrokinetic (EDL) | N/A -- use analytical | Debye length ~1--100 nm | Do not resolve EDL directly; use slip velocity |
| Dean flow (curved channels) | 15--20 radially | W/15 | Need to capture secondary flow vortices |

**Wall-normal resolution:**
- For accurate wall shear stress: first cell height should give y+ < 1 (which
  is automatically satisfied in microfluidics since flow is laminar).
- Boundary layer mesh with growth ratio 1.1--1.2 and 5--8 layers.

### 5.3 Validation Against Analytical Solutions

Always validate your simulation setup against a problem with a known solution
before moving to the actual device geometry.

**Validation Case 1: Poiseuille Flow**
```python
"""
Validate CFD pressure drop and velocity profile against
Hagen-Poiseuille solution for a rectangular channel.
"""
def poiseuille_velocity_rect(y, z, W, H, dp_dx, mu, n_terms=50):
    """
    Analytical velocity profile in a rectangular duct.
    Series solution (Bruus, Theoretical Microfluidics, Ch. 3).

    Parameters
    ----------
    y, z : float or array - cross-section coordinates (0 to W, 0 to H)
    W, H : float - channel width and height
    dp_dx : float - pressure gradient (negative for flow in +x)
    mu : float - dynamic viscosity
    n_terms : int - number of terms in Fourier series

    Returns
    -------
    u : float or array - axial velocity
    """
    u = np.zeros_like(y, dtype=float)
    for n in range(1, 2*n_terms, 2):  # odd terms only
        alpha_n = n * np.pi / H
        coeff = ((-1)**((n-1)//2)) / (n**3)
        cosh_ratio = np.cosh(alpha_n * (y - W/2)) / np.cosh(alpha_n * W/2)
        u += coeff * (1 - cosh_ratio) * np.sin(alpha_n * z)

    u *= (4 * H**2 * (-dp_dx)) / (mu * np.pi**3)
    return u


def validate_pressure_drop(dP_cfd, Q, mu, L, W, H):
    """Compare CFD pressure drop to analytical."""
    dP_analytical, _ = pressure_drop_rectangular(Q, mu, L, W, H)
    error_pct = abs(dP_cfd - dP_analytical) / dP_analytical * 100
    print(f"  CFD:        {dP_cfd:.2f} Pa")
    print(f"  Analytical: {dP_analytical:.2f} Pa")
    print(f"  Error:      {error_pct:.2f}%")
    if error_pct < 2:
        print("  PASS: Within 2% tolerance")
    else:
        print("  FAIL: Error exceeds 2% -- check mesh or boundary conditions")
    return error_pct
```

**Validation Case 2: Mixing Length Scaling**
- Simulate two co-flowing streams with known diffusion coefficient.
- Measure concentration profile at several downstream positions.
- Compare to the analytical error-function solution:
  ```
  c(x, y) = (c0/2) * erfc((y - W/2) / (2 * sqrt(D * x/U)))
  ```
- Verify that mixing efficiency scales with Pe as expected.

**Validation Case 3: Droplet Scaling Laws**
- Simulate T-junction droplet generation at several flow rate ratios.
- Plot L_drop / w_c vs. Q_d / Q_c.
- In the squeezing regime (Ca < 0.002), verify linear relationship:
  L/w = 1 + alpha * Q_d/Q_c
- Compare alpha to literature values (typically 0.5--2).

### 5.4 Checklist Before Running a Production Simulation

```
[ ] Geometry dimensions verified against design (um, mm units correct)
[ ] Fluid properties set correctly (density, viscosity, diffusivity)
[ ] Reynolds number computed and within laminar regime (Re < 2300)
[ ] Boundary conditions physically reasonable (flow rate, pressure values)
[ ] Mesh convergence study completed on simplified geometry
[ ] Boundary layer mesh added on all walls
[ ] Solver converged (residuals < 1e-6 for stationary; Courant < 1 for transient)
[ ] Results validated against analytical solution for a simple case
[ ] Mass conservation verified (inlet mass flow = outlet mass flow)
[ ] For two-phase: interface resolution checked (4+ elements across interface)
[ ] For transient: time step small enough; simulation long enough for steady state
[ ] Results make physical sense (velocity, pressure, concentration ranges)
```

---

## Summary: Choosing the Right Tool

| Problem | Best Tool | Why |
|---------|-----------|-----|
| Quick pressure/flow estimate | Python analytical (Sec 4) | Instant, no simulation needed |
| Single-phase steady flow | COMSOL or OpenFOAM simpleFoam | Straightforward; COMSOL easier, OpenFOAM free |
| Mixing/transport | COMSOL (Laminar Flow + TDS) or FEniCS | COMSOL has best GUI; FEniCS fully scriptable |
| Droplet generation (2D) | COMSOL Phase Field or OpenFOAM interFoam | Both capable; COMSOL easier setup |
| Droplet generation (3D, large) | OpenFOAM interFoam | Better parallel scaling, no license cost |
| Diffusion-reaction kinetics | FiPy or COMSOL | FiPy is lightweight; COMSOL for coupling |
| Network-level flow distribution | PyManifold or MMFT | Circuit-analog models, very fast |
| Electrokinetics (EOF, DEP) | COMSOL Microfluidics Module | Best physics interface support |
| Parameter sweeps / optimization | Python (FEniCS/FiPy) + scripting | Full automation, batch runs |

---

## Sources

- [COMSOL Microfluidics Module](https://www.comsol.com/microfluidics-module)
- [COMSOL Laminar Flow Interface Setup](https://www.comsol.com/support/learning-center/article/setting-up-the-laminar-flow-interface-102592/302)
- [COMSOL Droplet Breakup in a T-Junction Model](https://www.comsol.com/model/droplet-breakup-in-a-t-junction-1994)
- [COMSOL Microfluidics Module User's Guide](https://doc.comsol.com/5.4/doc/com.comsol.help.mfl/MicrofluidicsModuleUsersGuide.pdf)
- [Xi Engineering: Microfluidic Droplet Generation FEM Modeling](https://xiengineering.com/microfluidic-droplet-generation-finite-element-modelling/)
- [OpenFOAM interFoam Wiki](https://openfoamwiki.net/index.php/InterFoam)
- [OpenFOAM Multiphase Flow Tutorial Guide](https://www.openfoam.com/documentation/tutorial-guide/4-multiphase-flow)
- [OpenFOAM flowRateInletVelocity BC](https://www.openfoam.com/documentation/guides/latest/doc/guide-bcs-inlet-flow-rate-inlet.html)
- [OpenFOAM blockMesh Utility](https://www.openfoam.com/documentation/user-guide/4-mesh-generation-and-conversion/4.3-mesh-generation-with-the-blockmesh-utility)
- [VOF Simulations in Microfluidic T-Junction (arXiv)](https://arxiv.org/pdf/1703.00937)
- [Garstecki et al.: Droplet Formation Scaling Laws](http://www.princeton.edu/~stonelab/Publications/pdfs/From%20Howard/LabOnAChipSoftMatter/GarsteckiFuerstmanStoneWhitesidesLabOnAChip06.pdf)
- [Correlations of Droplet Formation in T-Junction Devices](https://link.springer.com/article/10.1007/s10404-008-0306-4)
- [FEniCSx Navier-Stokes Tutorial](https://jsdokken.com/dolfinx-tutorial/chapter2/navierstokes.html)
- [FEniCS Stokes Equation Tutorial](https://www.karlin.mff.cuni.cz/~hron/fenics-tutorial/stokes/doc.html)
- [FiPy Documentation](https://www.ctcms.nist.gov/fipy/)
- [FiPy Diffusion Tutorial](https://pages.nist.gov/fipy/en/latest/generated/examples.diffusion.mesh1D.html)
- [Solving Diffusion Equations with FiPy](https://matforge.org/solving-diffusion-equations-with-fipy/)
- [PyManifold on PyPI](https://pypi.org/project/pymanifold/)
- [MMFT Simulator (GitHub)](https://github.com/cda-tum/mmft-simulator)
- [Microfluidic Pressure Drop Calculator (ELEXAN)](https://elexansci.com/blog/microfluidic-resistance-and-pressure-drop-calculator/)
- [Pressure Drop in Microfluidics Guide (Aline)](https://www.alineinc.com/pressure-drop-in-microfluidics-a-comprehensive-guide/)
- [Microfluidics Mixing (Wikibooks)](https://en.wikibooks.org/wiki/Microfluidics/Mixing)
- [SimScale Mesh Sensitivity Study](https://www.simscale.com/knowledge-base/mesh-sensitivity-cfd/)
- [Grid Convergence Index (NASA)](https://www.grc.nasa.gov/www/wind/valid/tutorial/spatconv.html)
- [LEAP Australia: Convergence and Mesh Independence](https://www.leapaust.com.au/blog/cfd/convergence-and-mesh-independent-study/)
- [V&V for Microfluidic CFD (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S0307904X22000828)
