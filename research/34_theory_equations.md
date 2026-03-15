# Theoretical Foundations: Governing Equations for Microfluidic Modeling

> A comprehensive reference for the mathematical and physical theory underlying
> microfluidic simulations, covering fluid mechanics, electrokinetics, surface
> phenomena, non-Newtonian rheology, and scaling laws.

---

## Table of Contents

1. [Governing Equations for Microfluidics](#1-governing-equations-for-microfluidics)
2. [Non-Newtonian Fluid Models](#2-non-newtonian-fluid-models)
3. [Surface Tension and Wetting](#3-surface-tension-and-wetting)
4. [Electrokinetic Theory](#4-electrokinetic-theory)
5. [Scaling Laws in Microfluidics](#5-scaling-laws-in-microfluidics)

---

## 1. Governing Equations for Microfluidics

### 1.1 The Navier-Stokes Equations (Incompressible, Low Re)

The motion of an incompressible Newtonian fluid is governed by the Navier-Stokes
equations, which express conservation of momentum and mass.

**Momentum equation (incompressible):**

```
rho * (du/dt + (u . nabla)u) = -nabla(p) + mu * nabla^2(u) + f
```

where:
- `rho` -- fluid density (kg/m^3)
- `u` -- velocity vector field (m/s)
- `p` -- pressure (Pa)
- `mu` -- dynamic viscosity (Pa.s)
- `f` -- body force per unit volume (N/m^3), e.g. gravity rho*g

**Continuity equation (incompressible):**

```
nabla . u = 0
```

This states that the velocity field is divergence-free: fluid volume is conserved.

**Dimensionless form.** Introducing characteristic length L, velocity U, and time
L/U, the equations become:

```
Re * (du*/dt* + (u* . nabla*)u*) = -nabla*(p*) + nabla*^2(u*) + f*
```

where `Re = rho * U * L / mu` is the Reynolds number.

**In microfluidics**, typical channel dimensions are 10--500 um, velocities are
0.1--10 mm/s, and the working fluid is often aqueous (rho ~ 1000 kg/m^3,
mu ~ 10^-3 Pa.s). This yields:

```
Re = (1000)(10^-3)(100 x 10^-6) / (10^-3) = 0.1
```

Reynolds numbers of order 0.01--10 are the norm. At these scales, flow is always
laminar, and the nonlinear convective term `(u . nabla)u` is often negligible
compared to the viscous term.

### 1.2 Stokes Flow (Creeping Flow)

When Re << 1, the inertial (convective) terms can be dropped entirely, yielding
the Stokes equations:

```
mu * nabla^2(u) = nabla(p) - f
nabla . u = 0
```

**Key properties of Stokes flow:**

| Property | Implication |
|---|---|
| **Linearity** | Superposition of solutions is valid. If u1 solves Stokes for boundary conditions BC1, and u2 for BC2, then u1+u2 solves for BC1+BC2 |
| **Time-reversibility** | Reversing the boundary motion exactly reverses the flow. This is why mixing is fundamentally difficult at low Re |
| **Instantaneity** | The flow field depends only on current boundary conditions, not on history. There is no "memory" in the flow |
| **Uniqueness** | For given boundary conditions, the Stokes solution is unique |
| **Minimum dissipation** | Among all divergence-free velocity fields satisfying the boundary conditions, the Stokes solution minimizes the viscous dissipation |

**When to use Stokes flow:**
- Re < 0.1 (almost all microfluidic devices at normal operating conditions)
- Steady-state or quasi-steady analyses
- Analytical solutions for channel flows (Hele-Shaw cells, rectangular ducts)

**When NOT to use Stokes flow:**
- High-flow-rate applications (e.g., inertial microfluidics, Re ~ 10--100)
- Flows with strong unsteadiness (oscillatory flows at high Womersley number)
- Flows with non-negligible fluid inertia (Dean flow in curved channels)

### 1.3 Analytical Solutions for Common Geometries

**Poiseuille flow in a circular channel (radius R):**

```
u(r) = (1 / 4mu) * (dP/dz) * (R^2 - r^2)

Q = pi * R^4 * Delta_P / (8 * mu * L)      [Hagen-Poiseuille law]
```

The volumetric flow rate scales as R^4 -- halving the channel radius reduces
flow rate by a factor of 16 for the same pressure drop.

**Flow between parallel plates (gap h, width w >> h):**

```
u(y) = (1 / 2mu) * (dP/dz) * y * (h - y)

Q = w * h^3 * Delta_P / (12 * mu * L)
```

**Rectangular channel (width w, height h).** No closed-form solution exists; the
result is an infinite series:

```
Q = (w * h^3 * Delta_P) / (12 * mu * L) * [1 - sum_{n=1,3,5,...} (192h / (n^5 * pi^5 * w)) * tanh(n * pi * w / (2h))]
```

For w >> h, only the first term matters and Q approaches the parallel-plate
result. For a square channel (w = h), the correction factor reduces Q to about
0.42 of the parallel-plate value.

### 1.4 Convection-Diffusion Equation

The transport of a dilute solute (concentration c) in a flowing fluid is governed
by the convection-diffusion equation:

```
dc/dt + u . nabla(c) = D * nabla^2(c) + R
```

where:
- `D` -- molecular diffusion coefficient (m^2/s)
- `R` -- source/sink term (e.g., chemical reaction rate, mol/(m^3.s))
- `u` -- fluid velocity (obtained from Navier-Stokes or Stokes)

**The Peclet number** measures the relative importance of convection to diffusion:

```
Pe = U * L / D
```

| Regime | Pe value | Behavior |
|---|---|---|
| Diffusion-dominated | Pe << 1 | Species spreads primarily by diffusion; concentration gradients smooth out quickly |
| Balanced | Pe ~ 1 | Convection and diffusion are comparable |
| Convection-dominated | Pe >> 1 | Species is carried by the flow; sharp concentration gradients persist |

**Typical values in microfluidics:**
- Small molecule (D ~ 10^-9 m^2/s), L = 100 um, U = 1 mm/s: Pe ~ 100
- Protein (D ~ 10^-11 m^2/s), same conditions: Pe ~ 10,000
- Nanoparticle (D ~ 10^-12 m^2/s): Pe ~ 100,000

This means that even though flow is laminar (low Re), mass transport can be
strongly convection-dominated (high Pe). This is the fundamental challenge of
mixing in microfluidics: flow is smooth and predictable, but molecular diffusion
across streamlines is slow relative to downstream convection.

**Taylor-Aris dispersion.** In a pressure-driven channel flow with parabolic
velocity profile, the effective axial dispersion coefficient is:

```
D_eff = D * (1 + Pe^2 / K)
```

where K is a geometry-dependent constant (K = 48 for parallel plates, K = 192
for a circular tube). At high Pe, the effective dispersion can be orders of
magnitude larger than molecular diffusion alone.

### 1.5 Brinkman Equation (Porous Media)

When flow occurs in a porous medium (e.g., hydrogel-filled channels, packed bead
columns, paper microfluidics), the Brinkman equation extends Darcy's law to
include viscous shear stress:

```
0 = -nabla(p) - (mu / kappa) * u + mu_eff * nabla^2(u)
```

where:
- `kappa` -- permeability of the porous medium (m^2)
- `mu_eff` -- effective viscosity in the porous medium (often taken as mu)
- `(mu / kappa) * u` -- Darcy drag term (linear resistance)
- `mu_eff * nabla^2(u)` -- Brinkman viscous term

**Relation to Darcy's law.** In the bulk of a porous medium, far from
boundaries, velocity gradients are small and the Brinkman term vanishes, reducing
to Darcy's law:

```
u = -(kappa / mu) * nabla(p)

Q = (kappa * A * Delta_P) / (mu * L)
```

**Relation to Stokes flow.** In the limit of infinite permeability (kappa -> inf),
the Darcy drag vanishes and the Brinkman equation reduces to Stokes flow. This
makes the Brinkman equation ideal for problems with both free-flow and porous
regions (e.g., flow over a porous membrane, flow through a packed column with
clear fluid above).

**When to use the Brinkman equation:**
- Porous media with boundaries (walls, interfaces with free fluid)
- Hydrogel-filled channels
- Paper-based microfluidics (lateral flow assays)
- Packed bead beds in microchannels
- Any domain coupling free flow and porous flow

**Darcy number.** The ratio Da = kappa / L^2 compares permeability to the
characteristic length squared. For Da << 1 (typical of dense packing), Darcy
drag dominates; for Da >> 1 (very open structures), the flow approaches
free Stokes flow.

### 1.6 Nernst-Planck Equation (Electrokinetics)

The transport of ionic species under combined diffusion, convection, and electric
field is described by the Nernst-Planck equation:

```
dc_i/dt + nabla . J_i = R_i

J_i = -D_i * nabla(c_i) - (z_i * F * D_i * c_i) / (R_gas * T) * nabla(phi) + u * c_i
```

where for ionic species i:
- `c_i` -- concentration (mol/m^3)
- `D_i` -- diffusion coefficient (m^2/s)
- `z_i` -- valence (charge number)
- `F` -- Faraday constant (96,485 C/mol)
- `R_gas` -- universal gas constant (8.314 J/(mol.K))
- `T` -- temperature (K)
- `phi` -- electric potential (V)
- `u` -- fluid velocity (m/s)

The three flux contributions are:

| Term | Physical mechanism |
|---|---|
| `-D_i * nabla(c_i)` | Fickian diffusion (down concentration gradient) |
| `-(z_i F D_i c_i)/(RT) * nabla(phi)` | Electromigration (ions driven by electric field) |
| `u * c_i` | Convective transport (ions carried by fluid flow) |

**Coupling with Poisson's equation.** The electric potential is determined by the
charge distribution via Gauss's law:

```
nabla^2(phi) = -rho_e / epsilon

rho_e = F * sum_i (z_i * c_i)
```

Together, these form the Poisson-Nernst-Planck (PNP) system, which is the most
complete description of electrokinetic transport in microfluidics.

**When to use the Nernst-Planck equation:**
- Electrophoretic separations
- Electroosmotic flow with resolved double layers
- Ion concentration polarization (ICP) at nanochannels
- Desalination and electrodialysis microdevices
- Any system where electric fields drive ion transport

### 1.7 Summary: Choosing the Right Equation

| Physical scenario | Governing equation(s) | Key dimensionless numbers |
|---|---|---|
| Simple channel flow, aqueous buffer | Stokes + continuity | Re << 1 |
| Fast flow, inertial effects | Full Navier-Stokes | Re ~ 1--100 |
| Species mixing / reaction | Convection-diffusion (+ Stokes) | Pe, Da (Damkohler) |
| Flow through porous substrate | Brinkman (or Darcy) | Da = kappa/L^2 |
| Electrokinetic transport | Nernst-Planck + Poisson (+ Stokes) | Pe, Debye parameter kappa*a |
| Multiphase / droplet flow | Navier-Stokes + interface tracking | Ca, We, Bo |

---

## 2. Non-Newtonian Fluid Models

Many biofluids (blood, saliva, mucus) and polymer solutions used in microfluidics
exhibit non-Newtonian behavior: their viscosity depends on shear rate, or they
exhibit elastic (memory) effects. This section covers the most important models.

### 2.1 Generalized Newtonian Framework

For purely viscous (inelastic) non-Newtonian fluids, the stress tensor is:

```
tau = 2 * eta(gamma_dot) * S
```

where `S` is the strain rate tensor and `eta(gamma_dot)` is the
shear-rate-dependent apparent viscosity. The function `eta(gamma_dot)` defines
the constitutive model.

### 2.2 Power-Law (Ostwald-de Waele) Model

The simplest non-Newtonian model:

```
eta(gamma_dot) = K * gamma_dot^(n-1)
```

where:
- `K` -- consistency index (Pa.s^n). Numerically equals the viscosity at gamma_dot = 1 s^-1
- `n` -- flow behavior index (dimensionless)
  - n = 1: Newtonian fluid
  - n < 1: Shear-thinning (pseudoplastic) -- most biofluids
  - n > 1: Shear-thickening (dilatant) -- some suspensions

**Limitations:**
- Predicts zero viscosity as gamma_dot -> infinity (for n < 1)
- Predicts infinite viscosity as gamma_dot -> 0 (for n < 1)
- No Newtonian plateau at low or high shear rates
- Unsuitable for viscoelastic effects

**Typical values:**

| Fluid | K (Pa.s^n) | n |
|---|---|---|
| Blood (approx.) | 0.035 | 0.6 |
| Xanthan gum (0.5%) | 8.0 | 0.23 |
| Polyethylene oxide | 0.5 | 0.6 |
| CMC solution (1%) | 0.2 | 0.75 |

**When to use:** Quick estimates where only the mid-range shear rate behavior
matters; screening studies; cases where computational cost must be minimized.

### 2.3 Carreau-Yasuda Model

The most widely used model for blood and other biofluids with well-characterized
shear-thinning behavior:

```
eta(gamma_dot) = eta_inf + (eta_0 - eta_inf) * [1 + (lambda * gamma_dot)^a]^((n-1)/a)
```

where:
- `eta_0` -- zero-shear-rate viscosity (Pa.s)
- `eta_inf` -- infinite-shear-rate viscosity (Pa.s)
- `lambda` -- relaxation time (s), determines the onset of shear thinning
- `n` -- power-law index in the shear-thinning region
- `a` -- Yasuda parameter controlling the transition sharpness

Setting a = 2 recovers the standard **Carreau model**:

```
eta(gamma_dot) = eta_inf + (eta_0 - eta_inf) * [1 + (lambda * gamma_dot)^2]^((n-1)/2)
```

**Parameters for human blood:**

| Parameter | Value | Unit |
|---|---|---|
| eta_0 | 0.056 | Pa.s |
| eta_inf | 0.00345 | Pa.s |
| lambda | 3.313 | s |
| n | 0.3568 | -- |
| a | 2 (Carreau) or 0.64 (Yasuda) | -- |

**Behavior:**
- At low shear rates (gamma_dot << 1/lambda): eta -> eta_0 (Newtonian plateau)
- At high shear rates (gamma_dot >> 1/lambda): eta -> eta_inf (second Newtonian plateau)
- In between: power-law shear thinning

**When to use:**
- Blood flow simulations in microchannels (diameter 20--500 um)
- Any shear-thinning fluid where behavior at both low and high shear rates matters
- When the power-law model's unphysical zero/infinite viscosity limits are problematic
- Validated and recommended for computational hemodynamics

### 2.4 Oldroyd-B Model (Viscoelastic Fluids)

The Oldroyd-B model captures viscoelastic behavior -- fluids that exhibit both
viscous flow and elastic (spring-like) memory effects:

```
tau + lambda_1 * (D tau / D t) = 2 * eta_0 * (S + lambda_2 * (D S / D t))
```

where:
- `lambda_1` -- relaxation time (s)
- `lambda_2` -- retardation time (s)
- `D/Dt` -- upper-convected time derivative (frame-invariant)
- `eta_0` -- zero-shear viscosity

The upper-convected derivative is defined as:

```
D tau / D t = d tau/dt + (u . nabla) tau - (nabla u)^T . tau - tau . (nabla u)
```

This derivative makes the model frame-invariant (objective), meaning it gives the
same predictions regardless of the observer's frame of reference.

**Key predictions:**
- Constant shear viscosity (does NOT shear-thin -- a limitation)
- First normal stress difference: N1 = 2 * eta_0 * (lambda_1 - lambda_2) * gamma_dot^2
- Elastic recoil and stress relaxation
- Rod-climbing (Weissenberg effect)

**The Deborah number** measures the ratio of the relaxation time to the
observation time:

```
De = lambda_1 / t_obs = lambda_1 * U / L
```

At De >> 1, elastic effects dominate; at De << 1, the fluid behaves as viscous.

**The Weissenberg number** measures the ratio of elastic to viscous forces:

```
Wi = lambda_1 * gamma_dot
```

**When to use:**
- Dilute polymer solutions (e.g., PEO, PAA in water)
- Viscoelastic droplet generation
- Elastic instabilities and turbulence at low Re
- DNA solutions in microchannels
- When elastic normal stress effects are important

**Limitations:**
- No shear thinning (constant viscosity)
- Can exhibit unphysical infinite extensional viscosity
- For more realistic shear-thinning viscoelastic behavior, use Giesekus or
  FENE-P models

### 2.5 Other Notable Models

**Casson model** (yield-stress fluid, used for blood at very low shear rates):

```
sqrt(tau) = sqrt(tau_y) + sqrt(K * gamma_dot)
```

where `tau_y` is the yield stress. Blood has tau_y ~ 0.005 Pa.

**Herschel-Bulkley model** (yield-stress + power-law):

```
tau = tau_y + K * gamma_dot^n       for tau > tau_y
gamma_dot = 0                       for tau <= tau_y
```

**Giesekus model** (viscoelastic with shear thinning):

```
tau + lambda * (D tau/Dt) + (alpha * lambda / eta_p) * tau . tau = 2 * eta_p * S
```

The mobility parameter alpha (0 <= alpha <= 1) controls shear thinning. Setting
alpha = 0 recovers Oldroyd-B.

### 2.6 Implementation in Simulation Software

#### COMSOL Multiphysics

COMSOL provides built-in non-Newtonian viscosity models under the **CFD Module**
and **Polymer Flow Module**:

- **Generalized Newtonian models** (power-law, Carreau, Carreau-Yasuda, Cross,
  Herschel-Bulkley): Available under `Fluid Properties > Dynamic viscosity >
  Non-Newtonian`. A lower shear rate limit (default 10^-2 s^-1) prevents
  division-by-zero issues with the power-law model.
- **Viscoelastic models** (Oldroyd-B, Giesekus, FENE-P, PTT): Available in the
  Polymer Flow Module. These require solving additional transport equations for
  the extra stress tensor (conformation tensor approach).
- **User-defined models**: Custom eta(gamma_dot) expressions can be entered
  directly.

#### OpenFOAM

OpenFOAM supports non-Newtonian fluids through the `generalisedNewtonian`
viscosity model framework:

- **Built-in models** (specified in `constant/transportProperties`):
  - `powerLaw`: requires `k` (consistency) and `n` (index)
  - `CrossPowerLaw`: Cross model
  - `BirdCarreau`: Carreau model with `nu0`, `nuInf`, `k`, `n`
  - `HerschelBulkley`: yield-stress model

- **Solver**: Use `nonNewtonianIcoFoam` (transient, incompressible) or
  configure `pimpleFoam` / `simpleFoam` with a generalized Newtonian
  viscosity model.

- **Example transportProperties entry:**
  ```
  transportModel  BirdCarreau;
  BirdCarreauCoeffs
  {
      nu0     [0 2 -1 0 0 0 0] 5.6e-2;    // zero-shear kinematic viscosity
      nuInf   [0 2 -1 0 0 0 0] 3.45e-6;   // infinite-shear kinematic viscosity
      k       [0 0  1 0 0 0 0] 3.313;      // relaxation time
      n       [0 0  0 0 0 0 0] 0.3568;     // power-law index
  }
  ```

- **Viscoelastic models** require the `viscoelasticFluidFoam` solver or
  third-party libraries such as `rheoTool` (highly recommended for
  Oldroyd-B, Giesekus, FENE-P, PTT in OpenFOAM).

---

## 3. Surface Tension and Wetting

Surface tension effects dominate at the microscale because capillary forces scale
as L while gravitational/inertial forces scale as L^2 or L^3. The Bond number
Bo = rho*g*L^2 / gamma is typically << 1, confirming surface tension dominance.

### 3.1 Young's Equation for Contact Angle

At thermodynamic equilibrium, a liquid droplet on a smooth, rigid, homogeneous
surface forms a contact angle theta_Y determined by the balance of interfacial
tensions:

```
cos(theta_Y) = (gamma_SG - gamma_SL) / gamma_LG
```

where:
- `gamma_SG` -- solid-gas surface energy (N/m)
- `gamma_SL` -- solid-liquid interfacial energy (N/m)
- `gamma_LG` -- liquid-gas surface tension (N/m)
- `theta_Y` -- Young's (equilibrium) contact angle

**Classification:**

| Contact angle | Wetting behavior | Example surface for water |
|---|---|---|
| theta < 10 deg | Superhydrophilic | Clean glass, plasma-treated PDMS |
| 10 < theta < 90 deg | Hydrophilic | Native glass (20-30 deg), oxidized silicon |
| 90 < theta < 150 deg | Hydrophobic | Native PDMS (~110 deg), silanized glass |
| theta > 150 deg | Superhydrophobic | Textured fluoropolymer surfaces |

**On rough surfaces**, the Wenzel equation modifies Young's equation:

```
cos(theta_W) = r * cos(theta_Y)
```

where r > 1 is the roughness ratio (actual area / projected area). Roughness
amplifies the intrinsic wettability: hydrophilic surfaces become more
hydrophilic, and hydrophobic surfaces become more hydrophobic.

**On chemically heterogeneous surfaces**, the Cassie-Baxter equation applies:

```
cos(theta_CB) = f_1 * cos(theta_1) + f_2 * cos(theta_2)
```

where f_1 and f_2 are the area fractions of the two surface components.

### 3.2 Young-Laplace Equation for Capillary Pressure

The pressure difference across a curved fluid interface is given by the
Young-Laplace equation:

```
Delta_P = gamma * (1/R_1 + 1/R_2)
```

where R_1 and R_2 are the principal radii of curvature of the interface. For a
spherical meniscus (R_1 = R_2 = R):

```
Delta_P = 2 * gamma / R
```

**In a cylindrical capillary of radius r:**

```
Delta_P = 2 * gamma * cos(theta) / r
```

This is the **capillary pressure** that drives spontaneous filling of hydrophilic
channels (theta < 90 deg). For a typical glass microchannel (theta ~ 30 deg,
gamma = 72 mN/m, r = 50 um):

```
Delta_P = 2 * 0.072 * cos(30 deg) / (50e-6) = 2,490 Pa ~ 25 mbar
```

**In a rectangular microchannel (width w, height h):**

```
Delta_P = -2 * gamma * [cos(theta_t) + cos(theta_b)] / h + [cos(theta_l) + cos(theta_r)] / w]
```

where the subscripts denote top, bottom, left, and right wall contact angles.
Different wall materials yield different contact angles, enabling precise control
of capillary pressure.

### 3.3 Washburn Equation for Capillary Filling

The Washburn (or Lucas-Washburn) equation describes the dynamics of capillary
imbibition -- how fast a wetting liquid fills a channel:

```
L(t) = sqrt(gamma * r * cos(theta) * t / (2 * mu))
```

where L(t) is the penetration distance at time t. Key features:

- **Square-root scaling**: L grows as sqrt(t), meaning the filling rate
  dL/dt ~ 1/sqrt(t) slows over time as the viscous resistance of the
  growing liquid column increases
- **Faster filling for**: higher surface tension, lower viscosity, smaller
  contact angle (more wetting), larger radius (despite lower capillary
  pressure, the reduced resistance wins)

**Modified Washburn for rectangular channels:**

```
L(t) = sqrt(gamma * cos(theta) * h * t / (3 * mu))    [for w >> h]
```

**Practical implications for microfluidics:**
- A 100 um wide, 50 um deep glass channel fills about 1 cm in ~1 second with water
- Paper microfluidics (lateral flow assays) rely entirely on Washburn dynamics
- Filling time scales as L^2 -- doubling the channel length quadruples the fill time

### 3.4 Marangoni Effects

Surface tension gradients along an interface produce tangential stresses
(Marangoni stresses) that drive fluid motion:

```
tau_M = d(gamma) / ds
```

where s is the coordinate along the interface. Surface tension can vary due to:

**Temperature gradients (thermocapillary Marangoni):**

```
d(gamma)/ds = (d(gamma)/dT) * (dT/ds)
```

For most liquids, d(gamma)/dT < 0 (surface tension decreases with temperature),
so fluid flows from hot regions (low gamma) to cold regions (high gamma). Typical
thermocapillary coefficient for water: d(gamma)/dT ~ -0.15 mN/(m.K).

**Concentration gradients (solutal Marangoni):**

```
d(gamma)/ds = (d(gamma)/dc) * (dc/ds)
```

Surfactants reduce surface tension, so fluid flows away from regions of high
surfactant concentration.

**The Marangoni number** quantifies the ratio of Marangoni-driven transport to
diffusion:

```
Ma = |d(gamma)/dT| * Delta_T * L / (mu * alpha)     [thermal]
Ma = |d(gamma)/dc| * Delta_c * L / (mu * D)         [solutal]
```

where alpha is the thermal diffusivity.

**Marangoni effects in microfluidics:**
- Can destabilize or stabilize droplet interfaces
- Drive internal circulation in droplets (important for droplet-based PCR)
- Can cause unwanted droplet motion in non-isothermal systems
- Exploited for active droplet manipulation using laser heating
- Surfactant-laden interfaces are stiffened, suppressing Marangoni flows

### 3.5 Dynamic Contact Angle Models

When a contact line moves, the contact angle deviates from the equilibrium
(Young's) value. The dynamic contact angle theta_D depends on the capillary
number Ca = mu * U / gamma, where U is the contact line velocity.

**Cox-Voinov law** (most widely used for slow flows):

```
theta_D^3 = theta_Y^3 + 9 * Ca * ln(L_macro / L_micro)
```

where L_macro and L_micro are macroscopic and microscopic cutoff lengths (the
latter is typically molecular-scale, ~1 nm). This gives theta_D > theta_Y for
advancing contact lines and theta_D < theta_Y for receding.

**Tanner's law** (complete wetting, theta_Y = 0):

```
theta_D^3 ~ Ca
```

A spreading droplet's contact angle decreases as t^(-3/10).

**Kistler model** (empirical, widely used in CFD):

```
theta_D = f_Hoff(Ca + f_Hoff^-1(theta_Y))
```

where f_Hoff is the Hoffman function (a fitted empirical correlation).

**Contact angle hysteresis.** On real surfaces, the advancing angle theta_A
exceeds the receding angle theta_R. This hysteresis can pin droplets in place
and is critical for:
- Valve-like capillary stop structures
- Droplet trapping
- Capillary burst valves (fluid stops at an abrupt geometry expansion until
  the applied pressure exceeds the capillary back-pressure)

---

## 4. Electrokinetic Theory

### 4.1 The Electrical Double Layer (EDL) and Debye Length

When a solid surface contacts an electrolyte solution, surface charges attract
counterions and repel co-ions, forming the **electrical double layer** (EDL):

1. **Stern layer** (inner layer): Ions adsorbed directly on the surface, ~1
   molecular diameter thick, essentially immobile
2. **Diffuse layer** (outer layer): A cloud of mobile ions with exponentially
   decaying net charge density, extending several Debye lengths from the surface

**The Debye length** characterizes the thickness of the diffuse layer:

```
lambda_D = sqrt(epsilon * R_gas * T / (2 * F^2 * c_0 * z^2))
```

For a symmetric z:z electrolyte at 25 C:

```
lambda_D (nm) ~ 0.304 / sqrt(c_0 (M))       [for 1:1 electrolyte like NaCl]
```

| Concentration | Debye length |
|---|---|
| 1 mM | 9.6 nm |
| 10 mM | 3.0 nm |
| 100 mM | 0.96 nm |
| 1 M | 0.30 nm |

For typical microfluidic buffers (10--100 mM), the Debye length is 1--10 nm,
which is 3--5 orders of magnitude smaller than the channel dimension. This
"thin double layer" limit enables major simplifications.

**The zeta potential** (zeta) is the electric potential at the shear plane
(approximately at the outer edge of the Stern layer). It is the experimentally
measurable potential that determines electrokinetic transport. Typical values:

| Surface | Zeta potential (mV) |
|---|---|
| Glass/silica (pH 7, 10 mM) | -40 to -80 |
| PDMS (native) | -30 to -60 |
| PMMA | -20 to -40 |

### 4.2 Poisson-Boltzmann Equation

In thermodynamic equilibrium (no flow, no applied field), the ion distribution
in the EDL follows the Boltzmann distribution, and the potential satisfies the
Poisson-Boltzmann (PB) equation:

```
nabla^2(phi) = -(2 * z * F * c_0 / epsilon) * sinh(z * F * phi / (R_gas * T))
```

For small potentials (|phi| << R_gas*T/(z*F) ~ 25 mV), this linearizes to the
**Debye-Huckel approximation**:

```
nabla^2(phi) = phi / lambda_D^2
```

with solution (for a flat wall):

```
phi(x) = zeta * exp(-x / lambda_D)
```

The charge density in the diffuse layer decays exponentially with distance from
the wall.

### 4.3 Electroosmotic Flow (EOF)

When an external electric field E_ext is applied tangentially along a charged
surface immersed in an electrolyte, the net charge in the diffuse layer
experiences an electrical body force. This drives the fluid, producing
**electroosmotic flow** (EOF).

**Derivation (thin double layer).** Within the EDL, the Stokes equation with
electrical body force is:

```
mu * d^2(u)/dy^2 = -rho_e * E_ext
```

Using the Poisson equation (rho_e = -epsilon * d^2(phi)/dy^2) and integrating
from the wall (y = 0, u = 0) to the bulk (y >> lambda_D), we obtain the
**Helmholtz-Smoluchowski equation**:

```
u_EOF = -(epsilon * zeta / mu) * E_ext
```

or equivalently, the electroosmotic mobility:

```
mu_EOF = -epsilon * zeta / mu
```

**Key features of EOF:**
- The velocity profile is **plug-like** (uniform across the channel), unlike
  the parabolic profile of pressure-driven flow. This is because the driving
  force acts only within the thin EDL, and the bulk fluid is dragged along
  uniformly by viscous coupling.
- No dispersion of analyte bands (unlike pressure-driven flow with its
  parabolic profile).
- Flow rate is independent of channel dimensions (depends only on
  cross-sectional area, not geometry).
- Flow direction is reversed by reversing the applied field.
- Typical EOF velocities: 0.1--1 mm/s for E ~ 100--1000 V/cm.

**When the thin-double-layer approximation fails:**
- In nanochannels where the channel dimension approaches lambda_D
- At very low ionic strength
- In these cases, the full PNP + Stokes equations must be solved

### 4.4 Electrophoretic Mobility

A charged particle (ion, protein, cell) in an electric field experiences an
electrophoretic force. Its steady-state velocity is:

```
u_EP = mu_EP * E
```

**Thin double layer (kappa*a >> 1, Helmholtz-Smoluchowski):**

```
mu_EP = epsilon * zeta_p / mu
```

where zeta_p is the zeta potential of the particle.

**Thick double layer (kappa*a << 1, Huckel limit):**

```
mu_EP = (2/3) * epsilon * zeta_p / mu
```

where kappa = 1/lambda_D and a is the particle radius. The parameter kappa*a
determines which limit applies:
- kappa*a >> 1: Large particle, thin double layer (Smoluchowski)
- kappa*a << 1: Small particle, thick double layer (Huckel)
- Intermediate kappa*a: Use Henry's function f(kappa*a) which interpolates
  between 2/3 and 1

**Electrophoretic separation.** Different analytes have different mu_EP
(depending on charge, size, and shape), enabling separation in a
microchannel. The apparent velocity in a capillary electrophoresis experiment is:

```
u_apparent = (mu_EOF + mu_EP) * E
```

The EOF carries all species in one direction, but differences in mu_EP cause
differential migration and separation.

### 4.5 Dielectrophoresis (DEP)

Dielectrophoresis is the motion of a polarizable particle in a non-uniform
electric field. Unlike electrophoresis, DEP does not require the particle to
be charged -- it arises from induced dipoles.

**Time-averaged DEP force on a homogeneous sphere:**

```
F_DEP = 2 * pi * epsilon_m * r^3 * Re{K(omega)} * nabla(|E_rms|^2)
```

where:
- `r` -- particle radius (m)
- `epsilon_m` -- permittivity of the suspending medium (F/m)
- `E_rms` -- root-mean-square electric field (V/m)
- `K(omega)` -- complex Clausius-Mossotti factor

**The Clausius-Mossotti factor:**

```
K(omega) = (epsilon_p* - epsilon_m*) / (epsilon_p* + 2 * epsilon_m*)
```

where epsilon* = epsilon - j * sigma / omega is the complex permittivity
(sigma = conductivity, omega = angular frequency of the applied AC field).

**The sign of Re{K(omega)} determines the DEP behavior:**

| Re{K} | Type | Behavior |
|---|---|---|
| > 0 | Positive DEP (pDEP) | Particle moves toward high field regions (electrode edges) |
| < 0 | Negative DEP (nDEP) | Particle moves toward low field regions (away from electrodes) |

The **crossover frequency** where Re{K} = 0 is a characteristic property of each
particle type and is exploited for selective separation.

**Re{K} is bounded:** -0.5 <= Re{K} <= 1.0 for a homogeneous sphere.

**DEP force scaling:**
- Scales as r^3 (particle volume): 10x larger particle experiences 1000x more force
- Scales as nabla(|E|^2): requires strong field gradients, typically achieved
  with micro-electrodes or insulating constrictions
- Independent of field polarity (depends on |E|^2, not E)
- Works with AC fields, enabling operation above the frequency of electrochemical
  reactions (avoiding bubble generation)

**Applications in microfluidics:**
- Cell sorting (separating viable from non-viable cells)
- Concentrating bacteria or particles from dilute suspensions
- Trapping single cells for analysis
- Separating blood cells by type

### 4.6 Summary of Electrokinetic Phenomena

| Phenomenon | Driving force | Moving entity | Key equation |
|---|---|---|---|
| Electroosmosis | Tangential E-field | Bulk fluid | u = -(epsilon*zeta/mu)*E |
| Electrophoresis | Uniform E-field | Charged particle | u = mu_EP * E |
| Dielectrophoresis | Non-uniform E-field (AC or DC) | Polarizable particle | F = 2*pi*eps*r^3*Re{K}*nabla(|E|^2) |
| Streaming potential | Pressure-driven flow | Ions in EDL | V_stream = (epsilon*zeta*Delta_P)/(mu*sigma) |
| Sedimentation potential | Gravity on charged particles | Ions redistributed | Related to electrophoresis by Onsager reciprocity |

---

## 5. Scaling Laws in Microfluidics

Understanding how physical phenomena scale with characteristic length L is
essential for intuiting microfluidic behavior and for designing devices that
exploit microscale advantages.

### 5.1 The Square-Cube Law and Surface-to-Volume Ratio

For a channel of characteristic dimension L:

```
Surface area   ~ L^2
Volume         ~ L^3
Surface/Volume ~ 1/L
```

As L decreases from mm to um (a factor of 1000), the surface-to-volume ratio
increases by 1000x. This has profound consequences:

| Effect | Scaling | Microscale implication |
|---|---|---|
| Surface forces (capillary, electrostatic, van der Waals) | ~ L^1 or L^2 | Dominant over body forces |
| Body forces (gravity, inertia) | ~ L^3 | Negligible |
| Heat transfer through walls | ~ L^2 / L^3 = 1/L | Extremely fast thermal equilibration |
| Friction / viscous drag | ~ L^1 | High resistance per unit volume |
| Evaporation rate | ~ L^2 / L^3 = 1/L | Can be problematic for open systems |

### 5.2 Reynolds Number Scaling

```
Re = rho * U * L / mu
```

If we scale the channel dimension by a factor s (L -> s*L) while maintaining the
same fluid and the same pressure drop per unit length:

- For pressure-driven flow: U ~ L^2 (from Poiseuille's law), so Re ~ L^3
- For electroosmotic flow: U is independent of L, so Re ~ L

In either case, Re decreases rapidly with miniaturization. This is why
**turbulence is virtually impossible in microfluidics** under normal conditions.

### 5.3 Diffusion Time Scaling

The time for diffusion to transport species across a distance L:

```
t_diff ~ L^2 / D
```

| Scenario | L | D (m^2/s) | t_diff |
|---|---|---|---|
| Mixing across a 1 cm pipe | 10 mm | 10^-9 | 10^5 s (~28 hr) |
| Mixing across a 100 um channel | 100 um | 10^-9 | 10 s |
| Mixing across a 10 um channel | 10 um | 10^-9 | 0.1 s |
| Heat diffusion across 100 um (water) | 100 um | 1.4x10^-7 | 70 us |

The L^2 scaling means that reducing dimensions by 10x reduces diffusion time
by 100x. This is the fundamental advantage of microfluidics for:
- Rapid heat exchange (thermal cycling for PCR)
- Fast mixing (when combined with chaotic advection to reduce effective L)
- Precise concentration gradient generation

### 5.4 Peclet Number Scaling

```
Pe = U * L / D
```

For pressure-driven flow (U ~ L^2): Pe ~ L^3 / D
For electroosmotic flow (U ~ const): Pe ~ L / D

As channels shrink, Pe decreases, and diffusion becomes relatively more
important compared to convection in the cross-stream direction.

### 5.5 Capillary Number Scaling

```
Ca = mu * U / gamma
```

The capillary number compares viscous forces to surface tension forces. In
microfluidics:
- Ca is typically 10^-3 to 10^-1
- Surface tension dominates at low Ca (spherical droplets, stable interfaces)
- Viscous forces dominate at high Ca (droplet elongation, jetting)
- Droplet breakup in T-junctions occurs at Ca ~ 10^-2 to 10^-1

### 5.6 Heat Transfer at Microscale

The Biot number Bi = h*L/k compares convective resistance to conductive
resistance within the solid. For micro-devices:
- Bi << 1 (lumped capacitance applies)
- The device equilibrates thermally almost instantly

The thermal time constant:

```
tau_thermal = rho * c_p * L^2 / k
```

For a 100 um thick PDMS layer: tau ~ 0.1 s. For a 10 um layer: tau ~ 1 ms.
This enables:
- Rapid PCR thermal cycling (seconds vs. hours)
- Precise spatial temperature control
- Negligible thermal lag in calorimetric measurements

### 5.7 Why Mixing is Hard at Microscale

**The fundamental challenge:** At low Re, flow is laminar and streamlines do not
cross. Mixing must occur by molecular diffusion alone across streamlines. But for
typical biomolecules (D ~ 10^-11 m^2/s), even in a 100 um channel, Pe ~ 10^4,
meaning the fluid travels far downstream before cross-stream diffusion
homogenizes the concentration.

**Solutions that exploit scaling:**
1. **Reduce the diffusion distance** by splitting and recombining streams
   (lamination): If you create N lamellae, the effective diffusion distance
   becomes L/N and mixing time drops by N^2
2. **Chaotic advection** (e.g., herringbone grooves, serpentine channels):
   Stretching and folding of fluid elements exponentially reduces the
   striation thickness
3. **Use geometry to create secondary flows** (Dean vortices in curved channels
   at moderate Re ~ 1--10)

### 5.8 Why Separation is Easy at Microscale

In contrast to mixing, many separation processes become easier at the microscale:

- **Diffusion-based separation** (H-filter): Two co-flowing streams exchange
  small molecules (which diffuse across) but not large molecules (which do not).
  Efficiency improves as Pe decreases (smaller L).
- **Electrophoretic separation**: Resolution scales as sqrt(V) where V is the
  applied voltage. Microchannels dissipate heat efficiently (high SA/V),
  enabling higher V and better resolution.
- **Deterministic lateral displacement (DLD)**: Particles above a critical
  diameter are deflected by an array of posts. The critical diameter can be
  tuned to sub-micrometer resolution.
- **Inertial separation**: At moderate Re (10--100), size-dependent inertial
  lift forces push particles to equilibrium positions. Channel dimensions set
  the critical particle size.

### 5.9 Summary of Scaling Relationships

| Quantity | Scaling with L | Microscale consequence |
|---|---|---|
| Surface-to-volume ratio | L^-1 | Surface effects dominate |
| Reynolds number (pressure-driven) | L^3 | Always laminar |
| Diffusion time | L^2 | Fast thermal/mass equilibration |
| Peclet number (pressure-driven) | L^3 | Less convection-dominated |
| Capillary pressure | L^-1 | Strong capillary effects |
| Gravitational force / surface force | L^2 | Gravity negligible |
| Heat transfer rate per volume | L^-1 | Rapid thermal response |
| Viscous pressure drop (for given Q) | L^-4 | High back-pressure |
| Evaporation rate per volume | L^-1 | Can be significant |

---

## Appendix A: Key Dimensionless Numbers in Microfluidics

| Number | Definition | Physical meaning | Typical range |
|---|---|---|---|
| Reynolds (Re) | rho*U*L/mu | Inertia / viscous forces | 0.01 -- 10 |
| Peclet (Pe) | U*L/D | Convection / diffusion | 1 -- 10^5 |
| Capillary (Ca) | mu*U/gamma | Viscous / surface tension forces | 10^-3 -- 0.1 |
| Weber (We) | rho*U^2*L/gamma | Inertia / surface tension | << 1 |
| Bond (Bo) | rho*g*L^2/gamma | Gravity / surface tension | << 1 |
| Deborah (De) | lambda*U/L | Relaxation time / flow time | 0 -- 10 |
| Weissenberg (Wi) | lambda*gamma_dot | Elastic / viscous stress | 0 -- 100 |
| Knudsen (Kn) | lambda_mfp/L | Mean free path / channel size | << 1 (liquid) |
| Marangoni (Ma) | (dgamma/dT)*DT*L/(mu*alpha) | Surface tension gradient / viscous+diffusive | 0 -- 10^4 |
| Damkohler (Da) | reaction rate / transport rate | Reaction / convection or diffusion | varies |
| Schmidt (Sc) | mu/(rho*D) = nu/D | Momentum diffusivity / mass diffusivity | ~1000 (liquid) |
| Womersley (Wo) | L*sqrt(omega*rho/mu) | Unsteady inertia / viscous | < 1 |
| Darcy (Da_porous) | kappa/L^2 | Permeability / geometric area | << 1 |

---

## Appendix B: Physical Constants and Typical Fluid Properties

| Property | Water (25 C) | Blood (37 C) | Air (25 C) | Unit |
|---|---|---|---|---|
| Density rho | 997 | 1060 | 1.18 | kg/m^3 |
| Dynamic viscosity mu | 8.9 x 10^-4 | 3.5 x 10^-3 (high shear) | 1.85 x 10^-5 | Pa.s |
| Surface tension gamma | 0.072 | 0.058 | -- | N/m |
| Kinematic viscosity nu | 8.9 x 10^-7 | 3.3 x 10^-6 | 1.57 x 10^-5 | m^2/s |
| Thermal conductivity k | 0.607 | 0.52 | 0.026 | W/(m.K) |
| Thermal diffusivity alpha | 1.4 x 10^-7 | 1.2 x 10^-7 | 2.2 x 10^-5 | m^2/s |
| Permittivity epsilon_r | 78.5 | ~70 | 1.0 | -- |
| Diffusion coeff (small mol.) | ~10^-9 | ~10^-9 | ~10^-5 | m^2/s |
| Diffusion coeff (protein) | ~10^-11 | ~10^-11 | -- | m^2/s |

---

## Appendix C: References and Further Reading

### Textbooks
- Bruus, H. *Theoretical Microfluidics*. Oxford University Press, 2008.
- Kirby, B. *Micro- and Nanoscale Fluid Mechanics*. Cambridge University Press, 2010.
- Tabeling, P. *Introduction to Microfluidics*. Oxford University Press, 2005.
- Squires, T.M. and Quake, S.R. "Microfluidics: Fluid physics at the nanoliter scale." *Rev. Mod. Phys.* 77, 977 (2005).

### Online Resources
- [Stokes Flow (Wikipedia)](https://en.wikipedia.org/wiki/Stokes_flow)
- [COMSOL Blog: Modeling Electroosmotic Flow](https://www.comsol.com/blogs/modeling-electroosmotic-flow-electrical-double-layer/)
- [OpenFOAM Transport/Rheology Models](https://doc.cfd.direct/openfoam/user-guide-v10/transport-rheology)
- [Capillary Microfluidics in Microchannels (Lab on a Chip)](https://pubs.rsc.org/en/content/articlehtml/2018/lc/c8lc00458g)
- [Thermocapillarity in Microfluidics (PMC Review)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6189759/)
- [Non-Newtonian Rheology in Blood (arXiv)](https://arxiv.org/pdf/1306.2067)
- [Electroosmotic Flow: From Microfluidics to Nanofluidics (Wiley)](https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/elps.202000313)
- [Physics of Miniaturization Lecture Notes (ESPCI)](https://blog.espci.fr/mmn/files/2011/05/Lecture-1_Physics_miniaturisation_2017.pdf)
- [Microfluid Mechanics: Scaling Effects (Wikiversity)](https://en.wikiversity.org/wiki/Microfluid_Mechanics/Scaling_Effects_and_Governing_Equations_in_Microflows)
- [Dielectrophoresis (Wikipedia)](https://en.wikipedia.org/wiki/Dielectrophoresis)
- [Lucas-Washburn Equation (Langmuir)](https://pubs.acs.org/doi/10.1021/acs.langmuir.0c03134)
- [Nernst-Planck Equation (Wikipedia)](https://en.wikipedia.org/wiki/Nernst%E2%80%93Planck_equation)
