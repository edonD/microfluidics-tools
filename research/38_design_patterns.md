# Microfluidic Design Patterns & Standard Geometries

> Last updated: March 2026

## Standard Channel Geometries

### Flow Distribution

| Pattern | Description | Use Case | Design Parameters |
|---------|-------------|----------|-------------------|
| **Bifurcating tree** | Binary splitting network | Equal flow to N outlets (N = 2^n) | Each split doubles total cross-section to maintain velocity |
| **Ladder network** | Parallel channels with shared inlet/outlet | Equal flow through parallel reaction channels | All channels must have equal hydraulic resistance |
| **Manifold (fish-bone)** | Central channel with perpendicular branches | Perfusion arrays, cell culture | Branch spacing and width determine flow uniformity |
| **Radial distribution** | Central inlet, radial outflow | Centrifugal devices, gradient generators | Channel widths increase proportional to radius |

### Mixing Geometries

| Pattern | Mixing Mechanism | Typical Dimensions | Efficiency | Fabrication Complexity |
|---------|-----------------|-------------------|-----------|----------------------|
| **Straight channel** | Diffusion only | 100 µm × 50 µm, length = Pe × w | Low (<30%) for short channels | Very simple |
| **Serpentine** | Chaotic advection at turns | 100-200 µm wide, 10-20 turns | Medium (60-80%) | Simple (single layer) |
| **Staggered herringbone (SHM)** | 3D chaotic advection | Grooves: 30 µm deep, 50 µm wide, 200 µm pitch | Very high (>95%) | Medium (requires 2-height features) |
| **Tesla mixer** | Coanda effect, recirculation | 100-300 µm wide, 5-10 elements | High (>90%) at Re > 1 | Medium |
| **Split-and-recombine (SAR)** | Lamination | 100-200 µm, multi-layer | Very high (>95%) | Complex (3D/multi-layer) |
| **Dean flow (spiral)** | Dean vortices | 100-300 µm, R = 5-15 mm, 5-10 loops | Medium-High at Re > 10 | Simple |
| **Micro-pillars** | Flow around obstacles | Pillars: 20-50 µm diameter, 30-70 µm spacing | Medium | Medium (dense features) |

### Droplet Generation

| Pattern | Mechanism | Droplet Size | Monodispersity (CV) | Flow Rate Range |
|---------|-----------|-------------|---------------------|----------------|
| **T-junction** | Shear-driven breakup | 20-200 µm | <3% | 0.1-50 µL/min |
| **Flow-focusing** | Hydrodynamic focusing + breakup | 10-200 µm | <2% | 0.5-100 µL/min |
| **Co-flow** | Dripping/jetting | 20-500 µm | <3% | 0.1-50 µL/min |
| **Step emulsification** | Geometric confinement + release | 20-100 µm | <1% | Scalable (parallel) |
| **Concentric nozzle** | Axisymmetric flow-focusing | 10-100 µm | <2% | 1-100 µL/min |

### Separation Geometries

| Pattern | Mechanism | Target | Resolution | Throughput |
|---------|-----------|--------|-----------|-----------|
| **H-filter** | Diffusion-based extraction | Small molecules from cells | By molecular weight | Low-Medium |
| **Pinched flow fractionation** | Hydrodynamic pinching | Particles by size | ~1 µm | Low |
| **Deterministic lateral displacement (DLD)** | Pillar array displacement | Cells, particles by size | <0.1 µm | Medium |
| **Spiral (Dean flow)** | Inertial + Dean vortices | Cells by size (CTCs) | ~2-5 µm | High (mL/min) |
| **Acoustophoresis** | Standing acoustic waves | Cells by size/density | ~1 µm | Medium-High |
| **Dielectrophoresis (DEP)** | Non-uniform electric field | Cells by polarizability | Single cell | Low-Medium |
| **Magnetophoresis** | Magnetic field gradient | Magnetically labeled cells | — | Medium |

### Gradient Generators

| Pattern | Type | Description |
|---------|------|-------------|
| **Christmas tree** | Concentration | Serial bifurcation + mixing → linear concentration gradient across outlet channels |
| **Y-junction + long channel** | Concentration | Two inputs merge, diffusion creates gradient across channel width |
| **Microjet array** | Temporal | Pressure-driven jets create temporal pulses |
| **Membrane-based** | Concentration | Diffusion through membrane separating source and sink |
| **Serpentine dilution** | Concentration | Serial dilution through meander + mixing |

---

## Standard Port & Connection Patterns

### Inlet/Outlet Configurations

| Configuration | Ports | Use Case |
|--------------|-------|----------|
| **Single in / single out** | 2 | Simple flow-through |
| **Y-junction** | 3 (2 in, 1 out) | Co-flow, mixing |
| **T-junction** | 3 (2 in, 1 out) | Droplet generation |
| **Flow-focusing** | 4 (3 in, 1 out) | Droplet generation |
| **H-filter** | 4 (2 in, 2 out) | Diffusion-based separation |
| **Multi-outlet** | 2+ in, N out | Sorting, fraction collection |
| **Recirculation** | 2 (shared) | Closed-loop perfusion |

### Standard Port Sizes

| Port Size | Tubing Match | Punch Size | Connection Method |
|-----------|-------------|-----------|-------------------|
| 0.75 mm | Tygon 1/32" OD | 0.75 mm biopsy | Press-fit (tight) |
| 1.0 mm | Tygon 1/16" OD (snug) | 1.0 mm biopsy | Press-fit (standard) |
| 1.5 mm | Tygon 1/16" OD (loose) | 1.5 mm biopsy | Press-fit + adhesive |
| 3.0 mm | Luer-lock adapter | 3.0 mm biopsy | Luer adapter inserted |

---

## Multi-Layer Design Patterns

### Two-Layer Devices

| Pattern | Layer 1 (bottom) | Layer 2 (top) | Application |
|---------|-----------------|--------------|-------------|
| **Quake valve** | Flow channels | Control channels | Programmable routing |
| **Membrane sandwich** | Bottom channels | Top channels (separated by membrane) | Cell culture, filtration |
| **3D mixer** | Horizontal channels | Vertical via channels | Efficient mixing |

### Three+ Layer Devices

| Configuration | Description | Application |
|--------------|-------------|-------------|
| **Stacked channels** | Multiple fluid layers separated by membranes | Organ-on-chip |
| **Control matrix** | Flow layer sandwiched between two control layers | Complex valve routing |
| **Hybrid** | PDMS channels + glass substrate + electrode layer | Electrochemical sensing |

### Alignment Methods

| Method | Accuracy | Equipment | Notes |
|--------|----------|-----------|-------|
| **Manual (marks + microscope)** | ±30-50 µm | Stereomicroscope | Good enough for most devices |
| **Mask aligner-assisted** | ±5-10 µm | Mask aligner + custom chuck | For tight-tolerance multi-layer |
| **Self-alignment (posts/holes)** | ±10-20 µm | None (designed in) | Best for production |
| **Optical pattern matching** | ±1-5 µm | Camera + software | High-precision mLSI |

---

## Common Design Mistakes & Fixes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Channel too narrow at turns | Dead zones, bubble trapping | Use rounded corners, minimum radius = 2× channel width |
| No expansion before chamber | Jet formation, uneven filling | Add gradual expansion (taper angle < 15°) |
| Ports too close together | Tubing interference | Minimum 5 mm port-to-port spacing |
| No bubble traps | Bubbles clog channels | Add hydrophobic vent or bypass channel |
| Symmetric T-junction for droplets | Unstable dripping | Ensure oil channel (continuous) is wider than water channel |
| Equal-length branches in tree | Assumes equal resistance | Account for corner effects; use slightly varied widths |
| Deep narrow channels in PDMS | Channel collapse | Keep aspect ratio < 4:1, add support posts |
| Sharp dead-end channels | Air trapping | Add small vent hole or rounded end |
| No waste outlet | Nowhere for bubbles to go | Always include a waste channel after functional region |

---

## Design Templates (Copy-and-Modify)

### Template 1: Simple Mixer

```
Parameters:
- Channel width: 200 µm
- Channel height: 100 µm
- Inlet Y-junction angle: 45°
- Serpentine: 10 turns, 200 µm spacing
- Total mixing length: ~20 mm
- Outlet port: 1.5 mm diameter
- Inlet ports: 1.0 mm diameter
- Chip size: 25 mm × 25 mm

Expected performance:
- Re ≈ 0.5-5 at 1-10 µL/min
- Mixing efficiency: ~70-85% at 5 µL/min
- Pressure drop: ~10-50 mbar at 5 µL/min
```

### Template 2: Droplet Generator (Flow-Focusing)

```
Parameters:
- Orifice width: 50 µm
- Orifice length: 100 µm
- Continuous phase channel width: 100 µm
- Dispersed phase channel width: 50 µm
- Channel height: 50 µm
- Downstream collection channel: 200 µm wide
- Port size: 1.0 mm

Expected performance:
- Droplet diameter: 30-80 µm (depending on flow rate ratio)
- Generation frequency: 100-5000 Hz
- CV: <3%
- Oil: HFE-7500 + 2% PFPE-PEG surfactant
- Aqueous: PBS or cell media
```

### Template 3: Gradient Generator (Christmas Tree)

```
Parameters:
- Input channels: 2 (e.g., buffer + drug)
- Stages: 5 (gives 6 output concentrations: 0, 20, 40, 60, 80, 100%)
- Mixing channel width: 100 µm
- Mixing channel length: 5 mm per stage (serpentine)
- Output channel width: 100 µm
- Channel height: 50 µm

Expected performance:
- Linear concentration gradient across 6 output channels
- Requires ~5-10 min to reach steady state
- Flow rate: 1-5 µL/min per input
```
