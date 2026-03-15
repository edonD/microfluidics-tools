# Microfluidics Glossary & Quick Reference

> Last updated: March 2026

## Abbreviations

| Abbreviation | Full Term |
|-------------|-----------|
| **BAW** | Bulk Acoustic Wave |
| **BioMEMS** | Biological Micro-Electro-Mechanical Systems |
| **Ca** | Capillary number |
| **CAD** | Computer-Aided Design |
| **CE** | Capillary Electrophoresis |
| **CFD** | Computational Fluid Dynamics |
| **COC** | Cyclic Olefin Copolymer (e.g., TOPAS) |
| **COP** | Cyclic Olefin Polymer (e.g., Zeonor) |
| **CTC** | Circulating Tumor Cell |
| **CV** | Coefficient of Variation |
| **DAQ** | Data Acquisition |
| **De** | Dean number |
| **DEP** | Dielectrophoresis |
| **DFR** | Dry Film Resist |
| **DLD** | Deterministic Lateral Displacement |
| **DLP** | Digital Light Processing (3D printing) |
| **DMF** | Digital Microfluidics |
| **DPD** | Dissipative Particle Dynamics |
| **DRIE** | Deep Reactive Ion Etching |
| **EDA** | Electronic Design Automation |
| **EDM** | Electrical Discharge Machining |
| **EOF** | Electroosmotic Flow |
| **EtO** | Ethylene Oxide (sterilization) |
| **EWOD** | Electrowetting on Dielectric |
| **FDTS** | Perfluorodecyltrichlorosilane |
| **FEM** | Finite Element Method |
| **FEP** | Fluorinated Ethylene Propylene |
| **FVM** | Finite Volume Method |
| **GDSII** | Graphic Database System II (layout format) |
| **HF** | Hydrofluoric Acid |
| **IFC** | Integrated Fluidic Circuit |
| **IPA** | Isopropyl Alcohol |
| **IVD** | In Vitro Diagnostic |
| **KOH** | Potassium Hydroxide |
| **LBM** | Lattice Boltzmann Method |
| **LFA** | Lateral Flow Assay |
| **LIGA** | Lithographie, Galvanoformung, Abformung |
| **LNP** | Lipid Nanoparticle |
| **LOC** | Lab-on-a-Chip |
| **MD** | Molecular Dynamics |
| **MEMS** | Micro-Electro-Mechanical Systems |
| **mLSI** | Microfluidic Large-Scale Integration |
| **MOQ** | Minimum Order Quantity |
| **µPAD** | Microfluidic Paper-based Analytical Device |
| **µPIV** | Micro Particle Image Velocimetry |
| **µTAS** | Micro Total Analysis System |
| **NRE** | Non-Recurring Engineering (cost) |
| **OoC** | Organ-on-Chip |
| **OSTE** | Off-Stoichiometry Thiol-Ene |
| **PC** | Polycarbonate |
| **PCR** | Polymerase Chain Reaction |
| **PDB** | Post-Exposure Bake |
| **PDMS** | Polydimethylsiloxane |
| **Pe** | Peclet number |
| **PEEK** | Polyether Ether Ketone |
| **PEG** | Polyethylene Glycol |
| **PGMEA** | Propylene Glycol Monomethyl Ether Acetate |
| **PID** | Proportional-Integral-Derivative (controller) |
| **PINN** | Physics-Informed Neural Network |
| **PLL-g-PEG** | Poly-L-Lysine-grafted-Polyethylene Glycol |
| **PMMA** | Poly(methyl methacrylate) / Acrylic |
| **POC** | Point-of-Care |
| **PP** | Polypropylene |
| **PS** | Polystyrene |
| **PTFE** | Polytetrafluoroethylene (Teflon) |
| **PVA** | Polyvinyl Alcohol |
| **Re** | Reynolds number |
| **SAM** | Self-Assembled Monolayer |
| **SAW** | Surface Acoustic Wave |
| **SBS** | Society for Biomolecular Screening (well plate format) |
| **SEM** | Scanning Electron Microscope |
| **SHM** | Staggered Herringbone Mixer |
| **SLA** | Stereolithography |
| **TMAH** | Tetramethylammonium Hydroxide |
| **2PP** | Two-Photon Polymerization |
| **VOF** | Volume of Fluid (method) |
| **We** | Weber number |

---

## Key Formulas

### Hydraulic Resistance

**Rectangular channel** (h ≤ w):
```
R = 12µL / (wh³) × [1 - 0.63(h/w)]⁻¹
```

**Circular channel:**
```
R = 128µL / (πd⁴)
```

**Pressure-flow relationship** (Hagen-Poiseuille analogy):
```
ΔP = Q × R     (analogous to V = IR)
```

### Reynolds Number
```
Re = ρvDh / µ = ρQDh / (µA)
```
Where: Dh = hydraulic diameter = 4A/P (A = cross-section area, P = wetted perimeter)

For rectangular channel: Dh = 2wh / (w + h)

### Peclet Number
```
Pe = vL / D = QL / (DA)
```
Where: D = molecular diffusion coefficient, L = characteristic length

### Capillary Number
```
Ca = µv / γ
```
Where: γ = surface tension

### Dean Number
```
De = Re × √(Dh / 2R)
```
Where: R = radius of curvature

### Mixing Length (Diffusion-Limited)
```
Lm ≈ Pe × w = v × w² / D
```
Time for complete mixing by diffusion across channel width w.

### Droplet Volume (Approximate)
```
V ≈ π/6 × d³     (spherical droplet)
```

### Flow Rate to Velocity
```
v = Q / A = Q / (w × h)
```

### Residence Time
```
τ = V_channel / Q = L × A / Q
```

---

## Useful Constants

| Constant | Value | Unit |
|----------|-------|------|
| Water viscosity (20°C) | 1.002 × 10⁻³ | Pa·s |
| Water viscosity (37°C) | 0.692 × 10⁻³ | Pa·s |
| Water density (20°C) | 998 | kg/m³ |
| Water surface tension (20°C) | 72.8 × 10⁻³ | N/m |
| Blood viscosity | ~3-4 × 10⁻³ | Pa·s |
| PDMS-water contact angle | ~110° | degrees |
| PDMS-water contact angle (after O₂ plasma) | ~10-30° | degrees |
| Diffusion coeff. of fluorescein in water | ~4.25 × 10⁻¹⁰ | m²/s |
| Diffusion coeff. of small protein in water | ~1 × 10⁻¹⁰ | m²/s |
| Diffusion coeff. of 1 µm bead in water | ~4.4 × 10⁻¹³ | m²/s |

---

## Unit Conversions

| From | To | Multiply by |
|------|----|-------------|
| 1 µL/min | nL/s | 16.67 |
| 1 µL/min | m³/s | 1.667 × 10⁻¹¹ |
| 1 mbar | Pa | 100 |
| 1 psi | Pa | 6895 |
| 1 psi | mbar | 68.95 |
| 1 bar | psi | 14.5 |
| 1 bar | Pa | 100,000 |
| 1 µm | m | 10⁻⁶ |
| 1 nm | m | 10⁻⁹ |
| 1 cP | Pa·s | 10⁻³ |
| 1 cSt | m²/s | 10⁻⁶ |

---

## Quick Design Calculator

### Pressure Drop in a Rectangular Microchannel

**Inputs:** Channel width (w), height (h), length (L), flow rate (Q), fluid viscosity (µ)

```python
def pressure_drop_rectangular(w_um, h_um, L_mm, Q_uL_min, mu_Pa_s=1e-3):
    """Calculate pressure drop in a rectangular microchannel.

    Args:
        w_um: channel width in µm
        h_um: channel height in µm
        L_mm: channel length in mm
        Q_uL_min: flow rate in µL/min
        mu_Pa_s: dynamic viscosity in Pa·s (default: water at 20°C)

    Returns:
        Pressure drop in mbar
    """
    # Convert units to SI
    w = w_um * 1e-6   # m
    h = h_um * 1e-6   # m
    L = L_mm * 1e-3   # m
    Q = Q_uL_min * 1e-6 / 60  # m³/s (from µL/min)

    # Hydraulic resistance (rectangular, h < w)
    R = (12 * mu_Pa_s * L) / (w * h**3) * 1 / (1 - 0.63 * h/w)

    # Pressure drop
    dP = Q * R  # Pa
    dP_mbar = dP / 100  # convert to mbar

    return dP_mbar

# Example: 100µm × 50µm channel, 10mm long, 10 µL/min water
dp = pressure_drop_rectangular(100, 50, 10, 10)
print(f"Pressure drop: {dp:.1f} mbar")
# Output: ~32 mbar
```

### Reynolds Number Calculator

```python
def reynolds_number(w_um, h_um, Q_uL_min, rho=998, mu=1e-3):
    """Calculate Reynolds number for rectangular microchannel.

    Args:
        w_um: width in µm
        h_um: height in µm
        Q_uL_min: flow rate in µL/min
        rho: density in kg/m³
        mu: viscosity in Pa·s

    Returns:
        Reynolds number (dimensionless)
    """
    w = w_um * 1e-6
    h = h_um * 1e-6
    Q = Q_uL_min * 1e-6 / 60  # m³/s

    A = w * h
    Dh = 2 * w * h / (w + h)  # hydraulic diameter
    v = Q / A  # velocity

    Re = rho * v * Dh / mu
    return Re

# Example: 100µm × 50µm, 10 µL/min
re = reynolds_number(100, 50, 10)
print(f"Re = {re:.2f}")
# Output: Re ≈ 2.2 (laminar, as expected)
```

### Mixing Length Estimator

```python
def mixing_length(w_um, h_um, Q_uL_min, D_m2s=4.25e-10):
    """Estimate required channel length for complete diffusive mixing.

    Args:
        w_um: width in µm
        h_um: height in µm
        Q_uL_min: flow rate in µL/min
        D_m2s: diffusion coefficient in m²/s (default: fluorescein)

    Returns:
        Required mixing length in mm
    """
    w = w_um * 1e-6
    h = h_um * 1e-6
    Q = Q_uL_min * 1e-6 / 60

    A = w * h
    v = Q / A

    # Peclet number
    Pe = v * w / D_m2s

    # Mixing length ≈ Pe × w (for diffusion across full width)
    L_mix = Pe * w  # meters
    L_mix_mm = L_mix * 1000

    return L_mix_mm, Pe

L, Pe = mixing_length(100, 50, 10)
print(f"Pe = {Pe:.0f}")
print(f"Mixing length ≈ {L:.0f} mm")
# Without mixer: need ~500+ mm of channel for complete mixing!
# This is why passive mixers (SHM) are essential.
```
