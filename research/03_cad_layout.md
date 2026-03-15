# CAD and Layout Tools for Microfluidics Design

> Research compiled March 2026. Covers mask layout editors, 2D/3D CAD, scripting
> libraries, and microfluidics-specific design automation platforms.

---

## Table of Contents

1. [L-Edit (Siemens / Tanner EDA)](#1-l-edit-siemens--tanner-eda)
2. [KLayout](#2-klayout)
3. [AutoCAD](#3-autocad)
4. [SolidWorks](#4-solidworks)
5. [Fusion 360 (Autodesk Fusion)](#5-fusion-360-autodesk-fusion)
6. [CleWin](#6-clewin)
7. [GDSPY / gdstk (Python)](#7-gdspy--gdstk-python)
8. [Open-Source Microfluidic Layout Generators](#8-open-source-microfluidic-layout-generators)
9. [FreeCAD](#9-freecad)
10. [Onshape](#10-onshape)
11. [Comparison Matrix](#11-comparison-matrix)
12. [Recommendations by Use Case](#12-recommendations-by-use-case)

---

## 1. L-Edit (Siemens / Tanner EDA)

| Attribute | Details |
|---|---|
| **Vendor** | Siemens EDA (formerly Tanner EDA, acquired ~2017) |
| **Current version** | v22.15+ (as of 2025 training materials) |
| **Cost / License** | Commercial; historically ~$20,000+ per seat depending on features. Academic licenses available through CMC Microsystems and similar university programs (restricted to non-commercial research). Contact Siemens EDA for current quotes. |
| **OS support** | Windows (primary); Linux versions available in the broader Siemens EDA suite |
| **Learning curve** | Moderate. Dedicated training courses exist (Siemens Xcelerator Academy). Concepts transfer from other EDA layout editors. |

### Strengths

- **Gold standard for MEMS mask layout.** Purpose-built for MEMS with curved polygon support, all-angle Boolean operations, and clear/dark field visualization.
- Interactive DRC (Design Rule Check) catches errors during editing.
- Hierarchical cell-based design for reuse of components.
- Tight integration with Siemens MEMS design flow (T-Spice, CoventorMP).
- Handles GDSII, CIF, DXF import/export natively.
- Object snapping and alignment tools tuned for mask-level precision.

### Weaknesses

- Expensive commercial license; cost-prohibitive for small labs or startups.
- Windows-centric; less flexible for Linux-heavy HPC environments.
- Overkill for simple channel layouts that do not require MEMS-level features.
- Academic licenses come with restrictive legal agreements.
- Not 3D-aware; purely a 2D mask layout editor.

### Who Uses It

- University MEMS/microfluidics research groups (via academic licenses).
- Foundries and cleanroom facilities producing photomasks.
- Companies designing commercial MEMS sensors, actuators, and lab-on-chip devices.

### When to Choose It

Choose L-Edit when designing multi-layer photomasks for soft lithography or MEMS processes, when curved geometries and DRC are critical, and when the budget supports a commercial EDA license. It is the right tool when your workflow integrates with Siemens MEMS simulation tools.

---

## 2. KLayout

| Attribute | Details |
|---|---|
| **Vendor** | Open-source (Matthias Koefferlein, community-maintained) |
| **Cost / License** | Free, GPLv2 |
| **OS support** | Windows, macOS, Linux |
| **Learning curve** | Low to moderate. Good documentation, active forum. |

### Strengths

- **Free and fully open source** with no license restrictions.
- Reads and writes GDS2, OASIS, DXF, CIF, Gerber, LEF/DEF formats.
- Integrated Python and Ruby scripting IDE for parametric design automation.
- Built-in DRC and LVS scripting engines.
- XOR/diff tools for comparing layout revisions.
- Full editor mode: draw polygons, boxes, wires; Boolean operations; move, rotate, scale, mirror.
- Extensible via plugins; integrates with GDSFactory ecosystem.
- Actively maintained with frequent releases.

### Weaknesses

- Originally designed for semiconductor IC layouts, not microfluidics specifically.
- No built-in microfluidic component library (serpentines, droplet generators, etc.) -- must be scripted or imported.
- Curve support is via polygon approximation (faceted arcs), not true curves like L-Edit.
- No integrated simulation; purely a layout tool.
- GUI can feel utilitarian compared to commercial tools.

### Who Uses It

- Nanofabrication facilities (UCSB Nanofab, Hacker Fab, nanoFAB Alberta, EPFL CMi).
- Photonics and semiconductor researchers who also do microfluidics.
- Anyone needing a free mask layout editor.

### When to Choose It

Choose KLayout when budget is limited, when you need scriptable/parametric mask generation, when your fab accepts GDSII, or when you want to integrate with GDSFactory or other Python-based design flows. Excellent for SU-8 photomask design for PDMS soft lithography.

---

## 3. AutoCAD

| Attribute | Details |
|---|---|
| **Vendor** | Autodesk |
| **Cost / License** | ~$1,975/year (commercial subscription). Free for students/educators. |
| **OS support** | Windows, macOS (limited), web version |
| **Learning curve** | Moderate. Widely taught; extensive tutorials available. |

### Strengths

- **Industry standard 2D drafting tool** with precise dimensioning.
- Widely used in microfluidics foundries (Stanford Microfluidics Foundry requires DXF submissions).
- Units can be set to microns for mask-level precision.
- Closed polyline workflow maps directly to photomask features.
- DXF export is universally accepted by mask shops and film printers.
- Huge user base means abundant tutorials and community support.

### Weaknesses

- General-purpose; no microfluidics-specific features.
- No DRC or layer-aware operations.
- Expensive for non-academic users.
- Must be careful with units (default is inches, must switch to microns).
- Hatched/filled features can cause mask printing errors; requires discipline.
- No parametric design unless using AutoLISP scripting.

### Who Uses It

- Academic microfluidics labs designing PDMS soft lithography masks.
- Stanford Microfluidics Foundry users (de facto standard).
- Engineers familiar with AutoCAD from other disciplines.

### When to Choose It

Choose AutoCAD when your foundry requires DXF files, when designs are relatively simple channel networks, when team members already know AutoCAD, or when using the free educational license. Good for straightforward single- or multi-layer photomask designs.

---

## 4. SolidWorks

| Attribute | Details |
|---|---|
| **Vendor** | Dassault Systemes |
| **Cost / License** | ~$3,995+ (standard license) + annual subscription ~$1,295. Academic licenses available. |
| **OS support** | Windows only |
| **Learning curve** | Moderate to steep. Powerful but feature-rich. |

### Strengths

- **Full 3D parametric CAD** ideal for chip body design, mold design, and packaging.
- Feature tree enables easy design modifications and parametric sweeps.
- Direct export to 3D printing (STL) and CNC machining formats.
- Large library of tutorials and GrabCAD community models for microfluidics.
- Integrated flow simulation (SolidWorks Flow Simulation add-on) for basic CFD.
- Bill of materials and assembly modeling for complete device stacks.

### Weaknesses

- Windows-only; no macOS or Linux support.
- Expensive for non-academic users.
- Not designed for 2D mask layout; poor fit for photolithographic workflows.
- Complex microfluidic routing revisions require substantial rework.
- Overkill for simple 2D channel designs.

### Who Uses It

- Labs and companies designing 3D-printed microfluidic devices.
- Engineers creating CNC-machined acrylic/PMMA chips and injection mold inserts.
- Parallel Fluidics and similar commercial microfluidic manufacturers.

### When to Choose It

Choose SolidWorks when you need a 3D model of the physical chip (not just the mask), when designing molds for injection molding or hot embossing, when integrating with 3D printing or CNC workflows, or when you need basic flow simulation in the same tool.

---

## 5. Fusion 360 (Autodesk Fusion)

| Attribute | Details |
|---|---|
| **Vendor** | Autodesk |
| **Cost / License** | Free for personal non-commercial use (3-year subscription, <$1K annual revenue). Commercial: ~$595/year. Educational licenses available. |
| **OS support** | Windows, macOS (cloud-based with local client) |
| **Learning curve** | Low to moderate. More approachable than SolidWorks for beginners. |

### Strengths

- **Free tier** makes it accessible to students, hobbyists, and early-stage researchers.
- Combined CAD + CAM + basic simulation in one platform.
- Cloud-based collaboration and version control built in.
- 2D sketch export to DXF for photomask workflows.
- Direct 3D print preparation in the same application.
- Active community; many microfluidics tutorials available.
- Cross-platform (Windows + macOS).

### Weaknesses

- Free tier has limitations on file count, export formats, and features.
- Less precise control of micro-scale features compared to dedicated mask editors.
- Cloud dependency can be frustrating for secure/air-gapped lab environments.
- Not as mature for parametric sweeps as SolidWorks.
- No GDSII support.

### Who Uses It

- Students and academic researchers on tight budgets.
- Makers and citizen scientists building low-cost microfluidic devices.
- Labs doing rapid prototyping with 3D printing or laser cutting.

### When to Choose It

Choose Fusion 360 when budget is the primary constraint, when you need combined design-and-fabrication workflow (especially 3D printing), when collaboration features matter, or when getting started with microfluidic CAD for the first time.

---

## 6. CleWin

| Attribute | Details |
|---|---|
| **Vendor** | WieWeb Software (developed in cooperation with MESA+ Research Institute, University of Twente, and Deltamask) |
| **Cost / License** | CleWin 6: EUR 1,295 - EUR 2,590 depending on license type. Academic licenses allow up to 40 simultaneous users. Annual support/update subscription at 15% of license cost. |
| **OS support** | Windows 10 and higher |
| **Learning curve** | Low to moderate. Purpose-built for mask design; intuitive for that task. |

### Strengths

- **Purpose-built mask layout editor** with 30+ years of evolution.
- Hierarchical design with tree-view access to every symbol definition.
- Scripting engine supports C, MATLAB, MaskEngineer language, Lua, and Python (since v5.4).
- Good polygon and wire editing with node-level manipulation.
- Well-established in European cleanroom facilities (DTU Nanolab, MESA+, McGill Microfab).
- Affordable compared to L-Edit; generous academic licensing.
- Actively maintained: CleWin 6.2 released January 2025.

### Weaknesses

- Windows-only.
- Smaller user community compared to KLayout or AutoCAD.
- Less feature-rich than L-Edit for advanced MEMS design.
- Limited ecosystem integration (no GDSFactory, no plugin marketplace).
- Niche product; harder to find tutorials and community support outside European academic circles.

### Who Uses It

- European university cleanrooms and microfabrication facilities.
- Researchers at MESA+, DTU Nanolab, McGill, and similar institutions.
- Mask shops that grew up with CleWin in the 1990s-2000s.

### When to Choose It

Choose CleWin when your facility already has licenses and institutional knowledge, when you want a dedicated mask editor at lower cost than L-Edit, or when you need multi-language scripting for parametric mask generation. Good value for academic groups needing many seats.

---

## 7. GDSPY / gdstk (Python)

| Attribute | Details |
|---|---|
| **Vendor** | Open-source (Lucas H. Gabrielli / heitzmann) |
| **Cost / License** | Free, Boost Software License (gdstk) / GPL (gdspy) |
| **OS support** | Any platform with Python (Windows, macOS, Linux) |
| **Learning curve** | Requires Python programming skills. Low barrier for Python-proficient users. |

### gdspy vs. gdstk

- **gdspy**: Original Python library for GDSII creation. Version 1.6 is the final major release; maintenance mode only (bug fixes).
- **gdstk**: Successor to gdspy. Core rewritten in C++ with thin Python wrapper for dramatically improved performance on large layouts. Actively developed.

### Strengths

- **Programmatic, scriptable mask layout** -- version-controllable designs, parametric sweeps, batch generation.
- Boolean operations (AND, OR, NOT, XOR) on polygons.
- Polygon offset (inward/outward scaling).
- GDSII and OASIS file I/O.
- gdstk is significantly faster than gdspy for large designs.
- Integrates naturally with NumPy, SciPy, matplotlib for analysis and visualization.
- Foundation for higher-level libraries like GDSFactory and phidl.

### Weaknesses

- No GUI; requires writing code for every design.
- Debugging layouts requires exporting and viewing in KLayout or similar.
- Curve primitives must be approximated with polygon segments.
- No built-in DRC (must use external tools).
- Learning curve for non-programmers.

### Who Uses It

- Photonics researchers generating parametric device libraries.
- Microfluidics researchers who want reproducible, version-controlled mask designs.
- Anyone building automated design flows or integrating with optimization loops.

### When to Choose It

Choose gdstk when you want full programmatic control over mask generation, when designs are parametric and need to be swept across many variants, when integrating mask layout into a larger Python-based design or optimization pipeline, or when working with GDSFactory.

### Related: GDSFactory

GDSFactory builds on gdstk/gdspy and KLayout to provide higher-level functions for building GDSII components, PDKs, and masks. Originally focused on photonics but increasingly used for other planar microfabrication including microfluidics.

---

## 8. Open-Source Microfluidic Layout Generators

### 8.1 3DuF (3D Microfluidic Device Designer)

| Attribute | Details |
|---|---|
| **Source** | CIDAR Lab, Boston University ([GitHub](https://github.com/CIDARLAB/3DuF)) |
| **License** | Open source |
| **Type** | Web-based interactive editor |

- First completely open-source interactive microfluidic system designer.
- Supports design automation algorithms for continuous-flow devices.
- Component library with valves, mixers, and other standard microfluidic elements.
- Browser-based; no installation required.

### 8.2 OpenMFDA (Open Microfluidic Design Automation)

| Attribute | Details |
|---|---|
| **Source** | University of Utah ([GitHub: openmfda_flow](https://github.com/utah-MFDA/openmfda_flow)) |
| **License** | Open source |
| **Type** | Automated layout + simulation + fabrication pipeline |

- Adapts EDA (electronic design automation) concepts to microfluidics.
- Input: component list + connections. Output: laid-out device, simulation results, 3D CAD for DLP printing.
- Includes component PDK libraries (e.g., h.r.3.3_pdk).
- Published in *Scientific Reports* (2025).

### 8.3 Flui3d

| Attribute | Details |
|---|---|
| **Source** | Published in *Communications Engineering* (2024) |
| **License** | Open source |
| **Type** | Interactive platform for 3D-printed microfluidics |

- Multilayer co-design: users place modules in 2D; tool auto-generates 3D geometry.
- No 3D modeling expertise required.
- Parameterized component library.
- Targets DLP/SLA 3D printing fabrication.

### 8.4 Neptune

| Attribute | Details |
|---|---|
| **Source** | CIDAR Lab / iGEM ([GitHub](https://github.com/CIDARLAB/Neptune-iGEM-2016)) |
| **License** | Open source |
| **Type** | High-level microfluidic specification language |

- Uses Liquid Flow Relation (LFR) files for chip specification.
- Built-in library of standard components (valves, gradient generators, serpentine mixers, droplet generators).
- Generates physical layouts from abstract specifications.

### 8.5 PyMicrofluidics

| Attribute | Details |
|---|---|
| **Source** | [GitHub](https://github.com/guiwitz/PyMicrofluidics) |
| **License** | Open source |
| **Type** | Python module for DXF microfluidics drawings |

- Pre-made parametric functions for serpentines, alignment markers, and other standard features.
- Generates channels with rounded contours and fixed width.
- DXF output for mask printing.
- Lightweight; good for scripted design generation.

### 8.6 DAFD (Design Automation of Fluid Dynamics)

| Attribute | Details |
|---|---|
| **Source** | CIDAR Lab, Boston University ([Web tool](https://www.cidarlab.org/dafd)) |
| **License** | Open source |
| **Type** | ML-powered design tool for droplet generators |

- First microfluidic design automation tool using machine learning.
- Free web-based interface.
- Predicts droplet generation performance; suggests geometry for target droplet size/frequency.

---

## 9. FreeCAD

| Attribute | Details |
|---|---|
| **Vendor** | Open-source community (FreeCAD project) |
| **Cost / License** | Free, LGPLv2+ |
| **OS support** | Windows, macOS, Linux |
| **Learning curve** | Moderate to steep. Powerful but less polished UI than commercial alternatives. |

### Strengths

- **Completely free and open source** with no feature restrictions.
- Full 3D parametric modeling with Python scripting.
- Cross-platform including Linux.
- Active development community; growing ecosystem of workbenches.
- Can export STL for 3D printing, STEP for CNC, DXF for masks.
- No cloud dependency.

### Weaknesses

- Less stable and polished than SolidWorks or Fusion 360.
- Topological naming problem can cause feature tree breakage on edits (being addressed).
- No microfluidics-specific tools or component libraries.
- Smaller community for microfluidics-specific help.
- File compatibility issues with commercial formats (SLDPRT, etc.).

### Who Uses It

- Open-source advocates and Linux-based research labs.
- Budget-constrained groups needing 3D CAD without license costs.
- Researchers who value reproducibility and open formats.

### When to Choose It

Choose FreeCAD when you need free 3D CAD on Linux, when open-source licensing is a requirement, or when budget prohibits SolidWorks/Fusion 360 commercial licenses. Be prepared for a rougher user experience and occasional stability issues.

---

## 10. Onshape

| Attribute | Details |
|---|---|
| **Vendor** | PTC (acquired 2019) |
| **Cost / License** | Free for public projects (Onshape Free). Professional: ~$1,500/year. Enterprise: custom pricing. Educational: free. |
| **OS support** | Any platform with a web browser (fully cloud-based). Also iOS/Android apps. |
| **Learning curve** | Low to moderate. Clean interface; well-documented. |

### Strengths

- **Fully cloud-native** -- no installation, runs in browser on any OS.
- Real-time multi-user collaboration (Google Docs-style).
- Built-in version control with branching and merging.
- Parametric 3D modeling with FeatureScript custom feature language.
- Free tier for educational and public-project use.
- Mobile apps for reviewing designs.

### Weaknesses

- All designs on free tier are public; not suitable for proprietary work.
- Cloud-only; requires internet connection; no offline mode.
- Less mature ecosystem for advanced simulation compared to SolidWorks.
- No GDSII or mask-specific features.
- General-purpose CAD; no microfluidics-specific tooling.
- Data sovereignty concerns for some institutions.

### Who Uses It

- Academic labs wanting collaborative 3D design without license management.
- Distributed teams working across institutions.
- Educators teaching CAD fundamentals.

### When to Choose It

Choose Onshape when collaboration is the priority, when you need cross-platform access without software installation, when designs can be public (free tier), or when your institution does not have SolidWorks/Fusion 360 infrastructure.

---

## 11. Comparison Matrix

| Tool | Type | Cost | OS | 2D Mask | 3D CAD | GDSII | Scripting | Microfluidic-Specific |
|---|---|---|---|---|---|---|---|---|
| **L-Edit** | Mask layout | $$$$  | Win | Yes | No | Yes | Limited | MEMS-focused |
| **KLayout** | Mask layout | Free | All | Yes | No | Yes | Python/Ruby | No (extensible) |
| **AutoCAD** | 2D/3D CAD | $$$   | Win/Mac | DXF | Basic | No | AutoLISP | No |
| **SolidWorks** | 3D CAD | $$$$  | Win | No | Yes | No | VBA/API | No |
| **Fusion 360** | 3D CAD | Free/$$ | Win/Mac | DXF | Yes | No | Python API | No |
| **CleWin** | Mask layout | $$    | Win | Yes | No | Yes | Multi-lang | Mask-focused |
| **gdstk** | Script lib | Free | All | Yes | No | Yes | Python | No (extensible) |
| **3DuF** | Design auto | Free | Web | Yes | Partial | No | No | Yes |
| **OpenMFDA** | Design auto | Free | CLI | Yes | Yes | No | Scripted | Yes |
| **FreeCAD** | 3D CAD | Free | All | DXF | Yes | No | Python | No |
| **Onshape** | 3D CAD | Free/$$ | Web | No | Yes | No | FeatureScript | No |

Cost key: Free = $0 | $$ = <$3K | $$$ = $3-5K | $$$$ = >$5K

---

## 12. Recommendations by Use Case

### Photomask for PDMS Soft Lithography (2D)

- **Budget available:** L-Edit (best curve support + DRC) or CleWin (lower cost)
- **No budget:** KLayout (most capable free option) or gdstk + KLayout viewer
- **Foundry requires DXF:** AutoCAD (educational license) or Fusion 360 (free tier)
- **Parametric/automated designs:** gdstk or PyMicrofluidics

### 3D-Printed Microfluidic Devices

- **Professional:** SolidWorks (best 3D CAD + simulation ecosystem)
- **Budget-friendly:** Fusion 360 (free tier, integrated 3D print prep)
- **Open source:** FreeCAD
- **Collaborative:** Onshape
- **Automated:** OpenMFDA or Flui3d

### Research Lab Starting from Scratch

1. Start with KLayout (free, handles GDSII, scriptable) for mask layouts.
2. Add Fusion 360 (free tier) for 3D chip models and mold designs.
3. Use gdstk/Python for parametric design sweeps.
4. Consider 3DuF or DAFD for automated microfluidic-specific design.

### Industry / Production

- L-Edit for mask layout (integrates with Siemens MEMS flow).
- SolidWorks for 3D mechanical design and mold engineering.
- AutoCAD for foundry-compatible DXF submissions.

---

## Sources

- [Siemens MEMS Design Flow](https://resources.sw.siemens.com/en-US/fact-sheet-tanner-mes-design-flow/)
- [L-Edit MEMS - EDA Solutions](https://www.eda-solutions.com/products/tanner-l-edit-mems/)
- [KLayout Official Site](https://www.klayout.de/)
- [KLayout Microfluidic Forum Discussion](https://www.klayout.de/forum/discussion/2452/microfluidic-device-design)
- [Stanford Microfluidics Foundry - Design Basics](https://www.stanfordmicrofluidics.com/design-basics)
- [Artwork Systems - Mask Design for Microfluidics](https://www.artwork.com/acad/microfl/index.htm)
- [Parallel Fluidics - SolidWorks Microfluidic Design](https://www.parallelfluidics.com/resources/knowledge-base/how-to-design-a-microfluidic-device-in-solidworks)
- [Autodesk Fusion Personal Use](https://www.autodesk.com/products/fusion-360/personal)
- [WieWeb CleWin Official](https://wieweb.com/site/)
- [CleWin 6 Product Page](https://wieweb.com/site/product/clewin-6/)
- [DTU Nanolab CleWin Guide](https://labadviser.nanolab.dtu.dk/index.php?title=Specific_Process_Knowledge/Pattern_Design/CleWin)
- [gdstk GitHub](https://github.com/heitzmann/gdstk)
- [gdspy GitHub](https://github.com/heitzmann/gdspy)
- [GDSFactory Documentation](https://gdsfactory.github.io/gdsfactory/index.html)
- [3DuF GitHub - CIDAR Lab](https://github.com/CIDARLAB/3DuF)
- [OpenMFDA - Scientific Reports (2025)](https://www.nature.com/articles/s41598-025-15976-9)
- [Flui3d - Communications Engineering (2024)](https://www.nature.com/articles/s44172-024-00217-0)
- [PyMicrofluidics GitHub](https://github.com/guiwitz/PyMicrofluidics)
- [DAFD - CIDAR Lab](https://www.cidarlab.org/dafd)
- [Onshape Official](https://www.ptc.com/en/products/onshape)
- [EPFL CMi Layout Design](https://www.epfl.ch/research/facilities/cmi/process/photolithography/layout-design/)
- [ResearchGate - Mask Design Software Discussion](https://www.researchgate.net/post/Is-there-any-specific-software-for-designing-a-lithography-mask-in-micron-scale)
- [ResearchGate - Microfluidic CAD Discussion](https://www.researchgate.net/post/Microfluidic_chip_design_using_AutoCAD)
- [Parallel Fluidics - Software for Microfluidics](https://www.parallelfluidics.com/landing-pages/software-for-microfluidics)
