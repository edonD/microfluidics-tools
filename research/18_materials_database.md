# Materials Compatibility Database for Microfluidics

> Comprehensive reference for chemical compatibility, material properties, bonding methods,
> and sterilization options for all common microfluidic materials.

---

## Table of Contents

1. [PDMS Chemical Compatibility](#1-pdms-chemical-compatibility)
2. [Thermoplastic Compatibility](#2-thermoplastic-compatibility)
3. [Glass and Silicon Compatibility](#3-glass-and-silicon-compatibility)
4. [Tubing Compatibility](#4-tubing-compatibility)
5. [Material Properties Comparison Table](#5-material-properties-comparison-table)
6. [Bonding Compatibility Matrix](#6-bonding-compatibility-matrix)
7. [Sterilization Compatibility](#7-sterilization-compatibility)

---

## 1. PDMS Chemical Compatibility

PDMS (polydimethylsiloxane, Sylgard 184) is the most widely used elastomer in academic microfluidics. Its chemical compatibility is governed by the Hildebrand solubility parameter: PDMS has delta ~ 7.3 cal^(1/2) cm^(-3/2), and solvents with similar solubility parameters cause the greatest swelling.

### 1.1 Swelling Ratios for Common Solvents

Based on the landmark study by Lee, Park, and Whitesides (Anal. Chem. 2003, 75, 6544-6554), which measured the swelling ratio S = D/D0 (swollen diameter / original diameter) for PDMS in 39 solvents:

| Solvent | Swelling Ratio (S) | Solubility Parameter (delta) | Compatibility |
|---------|-------------------|------------------------------|---------------|
| **Low Swelling (S < 1.06) -- Safe** | | | |
| Water | 1.00 | 23.4 | Excellent |
| Glycerol | 1.00 | 21.1 | Excellent |
| Ethylene glycol | 1.00 | 16.3 | Excellent |
| Dimethyl sulfoxide (DMSO) | 1.00 | 13.0 | Excellent |
| Propylene carbonate | 1.00 | 13.3 | Excellent |
| Nitromethane | 1.01 | 12.7 | Excellent |
| Dimethylformamide (DMF) | 1.02 | 12.1 | Excellent |
| Acetonitrile | 1.01 | 11.9 | Excellent |
| Perfluorotributylamine | 1.00 | 5.6 | Excellent |
| Perfluorodecalin | 1.00 | 6.0 | Excellent |
| **Moderate Swelling (S = 1.06-1.30) -- Use with Caution** | | | |
| Methanol | 1.02 | 14.5 | Good |
| Ethanol | 1.04 | 12.7 | Good |
| 2-Propanol (IPA) | 1.09 | 11.5 | Acceptable |
| 1-Butanol | 1.13 | 11.3 | Caution |
| Acetone | 1.06 | 9.9 | Caution |
| 1-Propanol | 1.09 | 11.9 | Acceptable |
| Pyridine | 1.25 | 10.7 | Caution |
| N-Methylpyrrolidone (NMP) | 1.03 | 11.3 | Good |
| **High Swelling (S > 1.30) -- Incompatible** | | | |
| Dichloromethane (DCM) | 1.22 | 9.7 | Poor |
| Chloroform | 1.39 | 9.3 | Bad |
| Tetrahydrofuran (THF) | 1.38 | 9.1 | Bad |
| Toluene | 1.31 | 8.9 | Bad |
| Hexane | 1.35 | 7.3 | Bad |
| Heptane | 1.34 | 7.4 | Bad |
| Pentane | 1.44 | 7.1 | Bad |
| Cyclohexane | 1.33 | 8.2 | Bad |
| Xylenes | 1.41 | 8.8 | Bad |
| Diethyl ether | 1.38 | 7.4 | Bad |
| Ethyl acetate | 1.18 | 9.1 | Poor |
| Diisopropylamine | 1.58 | 7.3 | Very Bad |
| Triethylamine | 1.58 | 7.5 | Very Bad |

**Practical rule of thumb**: Solvents with solubility parameters close to PDMS (delta ~ 7.3) cause the most swelling. Highly polar solvents (water, DMSO, glycols) and perfluorinated solvents cause no swelling.

### 1.2 Detailed Chemical Resistance (at 20C)

| Chemical | Resistance |
|----------|-----------|
| Acetic acid (dilute) | Resistant |
| Acetic acid (concentrated/glacial) | Limited resistance |
| Hydrochloric acid (dilute) | Resistant |
| Hydrochloric acid (concentrated) | Resistant |
| Sulfuric acid (dilute) | Resistant |
| Sulfuric acid (concentrated) | Limited resistance |
| Nitric acid (dilute) | Resistant |
| Nitric acid (concentrated) | Not resistant |
| Sodium hydroxide (dilute) | Resistant |
| Sodium hydroxide (concentrated) | Resistant |
| Hydrogen peroxide (30%) | Resistant |
| Ammonia (aqueous) | Resistant |
| Formaldehyde | Resistant |
| Mineral oils | Limited resistance |
| Vegetable oils | Resistant |
| Saline solutions | Resistant |
| Phosphate buffers | Resistant |
| Cell culture media | Resistant |

### 1.3 Small Molecule Absorption

PDMS absorbs hydrophobic small molecules from solution, which is a critical concern for drug studies, organ-on-chip devices, and any assay involving hydrophobic compounds.

**The LogP Rule (Toepke & Beebe, 2006; Wang et al., 2012)**:

| LogP Range | Absorption | Practical Impact |
|------------|-----------|-----------------|
| LogP < 2.0 | Minimal (<5%) | Safe for quantitative assays |
| LogP 2.0 - 2.5 | Moderate (5-50%) | Test before use; may need corrections |
| LogP > 2.5 | Extensive (50-90%+) | Unsuitable without surface coatings |
| LogP > 3.5 | Near-complete (>90%) | Do not use PDMS |

**Critical threshold**: LogP ~ 2.5 is the crossover point. Molecules below LogP 2.47 exhibit <10% absorption; molecules above LogP 2.62 exhibit >90% absorption into PDMS channel walls.

**Additional predictive factors beyond LogP**:
- Topological polar surface area (TPSA): higher TPSA reduces absorption
- Number of H-bond donors: more donors reduce absorption
- Molecular weight: larger molecules diffuse more slowly but may still partition

**Common drugs affected by PDMS absorption**:

| Compound | LogP | Absorption Risk |
|----------|------|----------------|
| Rhodamine B | ~1.95 | Moderate |
| Nile Red | 3.8 | Very high |
| Diazepam | 2.8 | High |
| Paclitaxel | 3.0 | High |
| Fluorescein | -0.67 | None |
| Doxorubicin | 1.27 | Low |
| Caffeine | -0.07 | None |

**Mitigation strategies**:
- Glass or TiO2 coatings reduce absorption 2-4.5x
- Parylene C coating creates diffusion barrier
- Use glass, COC, or COP devices instead for hydrophobic compounds
- Pre-saturate PDMS by soaking in compound solution before experiment
- Use computational models to predict and correct for absorption

---

## 2. Thermoplastic Compatibility

### 2.1 COC (Cyclic Olefin Copolymer) -- TOPAS

COC is a copolymer of ethylene and norbornene. Higher norbornene content yields higher Tg.

**TOPAS Grades and Glass Transition Temperatures**:

| Grade | Norbornene Content | Tg (C) | Primary Applications |
|-------|-------------------|--------|---------------------|
| 8007F-04 | Low | 78 | Low-temp bonding, general microfluidics |
| 5013L-10 | Medium | 134 | General purpose, good balance |
| 6013M-07 | ~50% | 130 | Injection molding, diagnostics |
| 6015S-04 | Medium-high | 158 | Higher-temp applications |
| 6017S-04 | ~60% | 178 | PCR chips, high-temp microfluidics |

**Chemical Resistance**:

| Chemical Category | Resistance | Notes |
|-------------------|-----------|-------|
| Water | Excellent | <0.01% water absorption |
| Acids (HCl, H2SO4, HNO3) | Excellent | Resistant to mineral acids |
| Bases (NaOH, KOH) | Excellent | Resistant to strong bases |
| Alcohols (methanol, ethanol, IPA) | Excellent | Key advantage over PMMA |
| Acetone | Excellent | Key advantage over PMMA/PC |
| Acetonitrile | Excellent | Suitable for HPLC applications |
| DMSO | Excellent | |
| Saline solutions | Excellent | |
| Toluene | Not resistant | Causes swelling/dissolution |
| Hexane | Not resistant | Attacks COC |
| Benzene | Not resistant | Dissolves COC |
| Chlorinated solvents (DCM, CHCl3) | Not resistant | Dissolves COC |
| Halogenated hydrocarbons | Not resistant | Attacks COC |
| Mineral oils | Not resistant | Causes swelling |
| Gasoline/petroleum ether | Not resistant | Dissolves COC |

**Key advantages of COC**: 10x lower water absorption than PMMA; excellent UV transparency down to ~250 nm; very low autofluorescence; excellent optical clarity (91.4% transmission); low birefringence.

### 2.2 COP (Cyclic Olefin Polymer) -- Zeonor/Zeonex

COP is the homopolymer form of cyclic olefin materials (ring-opened metathesis polymerization of norbornene).

**Zeonor/Zeonex Grades**:

| Grade | Type | Tg (C) | Notes |
|-------|------|--------|-------|
| Zeonor 1020R | COP | 105 | General purpose, injection molding |
| Zeonor 1060R | COP | 100 | Good flowability |
| Zeonex 480R | COP | 138 | High heat resistance |
| Zeonex 690R | COP | 136 | Optical applications |
| Zeonex E48R | COP | 139 | High purity for diagnostics |

**Chemical Resistance** (similar profile to COC):

| Chemical | Resistance |
|----------|-----------|
| Polar organic solvents (acetone, IPA) | Resistant |
| Alcohols | Resistant |
| Acids and bases | Resistant |
| Water | Excellent (very low absorption) |
| Non-polar solvents (toluene, hexane) | Not resistant |
| Chlorinated solvents | Not resistant |

**Advantages over COC**: slightly higher purity; even lower extractables; superior moisture barrier; very low autofluorescence; excellent for optical biosensing.

### 2.3 PMMA (Polymethyl Methacrylate)

| Chemical | Resistance | Notes |
|----------|-----------|-------|
| Water | Excellent | |
| Dilute acids | Excellent | HCl, H2SO4 at low concentration |
| Dilute bases | Good | |
| Alcohols (methanol, ethanol) | Limited | Can cause crazing |
| Isopropanol | Limited | Stress cracking risk |
| Acetone | Not resistant | Dissolves/crazes PMMA |
| Chloroform | Not resistant | Dissolves PMMA rapidly |
| Dichloromethane (DCM) | Not resistant | Dissolves PMMA (used for solvent bonding) |
| Toluene | Not resistant | Dissolves PMMA |
| THF | Not resistant | Dissolves PMMA |
| Ethyl acetate | Not resistant | Dissolves/crazes |
| DMSO | Good | |
| Acetonitrile | Limited | Can craze under stress |
| Mineral oils | Limited | May cause crazing |

**Key properties**: Tg = 105C; excellent optical clarity (93% transmission); good UV transparency down to ~340 nm; moderate autofluorescence (blue-green range); Young's modulus ~ 3100 MPa.

**Bonding solvents**: DCM, chloroform, and acetic acid are commonly used for solvent bonding of PMMA, exploiting its solubility in these solvents.

### 2.4 PC (Polycarbonate)

| Chemical | Resistance | Notes |
|----------|-----------|-------|
| Water | Excellent | |
| Dilute acids | Good | |
| Dilute bases | Good | |
| Concentrated NaOH | Limited | Can cause degradation |
| Alcohols (methanol, ethanol) | Good | Better than PMMA |
| Acetone | Not resistant | Dissolves/crazes PC |
| Chloroform | Not resistant | Dissolves PC |
| DCM | Not resistant | Dissolves PC |
| Toluene | Not resistant | |
| THF | Not resistant | |
| DMSO | Limited | Can cause stress cracking |
| Acetonitrile | Limited | |
| Strong oxidizers | Not resistant | |

**Key properties**: Tg = 145-148C (higher than PMMA -- suitable for PCR); 88% optical transmission; higher autofluorescence than COC/COP (problematic for fluorescence assays); high dispersion and birefringence; Young's modulus ~ 2400 MPa; excellent impact resistance.

### 2.5 PS (Polystyrene)

| Chemical | Resistance | Notes |
|----------|-----------|-------|
| Water | Excellent | |
| Dilute acids | Good | |
| Dilute bases | Good | |
| Alcohols | Good | Resistant to methanol, ethanol |
| Acetone | Not resistant | Dissolves PS |
| Chloroform | Not resistant | Dissolves PS |
| DCM | Not resistant | |
| Toluene | Not resistant | Dissolves PS (same solubility parameter) |
| THF | Not resistant | |
| DMSO | Good | |

**Key properties**: Tg = 95-100C; good optical clarity; standard material for cell culture (tissue-culture treated PS); biocompatible with established cell biology track record; Young's modulus ~ 3000-3500 MPa; rigid and brittle.

### 2.6 Thermoplastic Chemical Resistance Summary

| Chemical | COC/COP | PMMA | PC | PS |
|----------|---------|------|----|----|
| Water | OK | OK | OK | OK |
| Methanol | OK | Caution | OK | OK |
| Ethanol | OK | Caution | OK | OK |
| IPA | OK | Caution | OK | OK |
| Acetone | OK | FAIL | FAIL | FAIL |
| DMSO | OK | OK | Caution | OK |
| Acetonitrile | OK | Caution | Caution | Caution |
| Toluene | FAIL | FAIL | FAIL | FAIL |
| Hexane | FAIL | OK | OK | OK |
| Chloroform | FAIL | FAIL | FAIL | FAIL |
| DCM | FAIL | FAIL | FAIL | FAIL |
| THF | FAIL | FAIL | FAIL | FAIL |
| Dilute HCl | OK | OK | OK | OK |
| Dilute NaOH | OK | OK | OK | OK |
| Conc. H2SO4 | OK | FAIL | FAIL | FAIL |

**Decision guide**: If your application requires organic solvents, COC/COP is the best thermoplastic choice for polar solvents. For non-polar solvents (alkanes, aromatics), no common thermoplastic is suitable -- use glass, silicon, or fluoropolymers instead.

---

## 3. Glass and Silicon Compatibility

### 3.1 Glass (Borosilicate, Soda-lime, Fused Silica/Quartz)

Glass is the gold standard for chemical inertness in microfluidics.

**Chemical Resistance**:

| Chemical | Resistance | Notes |
|----------|-----------|-------|
| Nearly all organic solvents | Excellent | Universal compatibility |
| Acids (HCl, H2SO4, HNO3) | Excellent | All concentrations |
| Hydrofluoric acid (HF) | Not resistant | Etches glass -- used for fabrication |
| Concentrated hot phosphoric acid | Limited | Slowly attacks glass |
| Strong hot alkali (NaOH, KOH) | Limited | Slowly dissolves at high conc./temp. |
| Bases (dilute/moderate) | Excellent | |
| Biological fluids | Excellent | |
| All common buffers | Excellent | |

**Temperature limits**:

| Glass Type | Max Continuous (C) | Softening Point (C) | Annealing Point (C) |
|------------|-------------------|---------------------|---------------------|
| Soda-lime | 500 | 700 | 545 |
| Borosilicate (Pyrex) | 500 | 820 | 560 |
| Fused silica/quartz | 1000 | 1665 | 1140 |

**Biocompatibility**: Glass is highly biocompatible and widely accepted for biological applications. It supports well-established surface chemistries (silanization), has low nonspecific adsorption compared to PDMS, and is FDA-approved for many medical device applications.

**Optical properties**: Excellent transparency; negligible autofluorescence; fused silica is transparent deep into the UV (down to ~170 nm); no birefringence in amorphous glass.

### 3.2 Silicon

**Chemical Resistance**:

| Chemical | Resistance | Notes |
|----------|-----------|-------|
| Most organic solvents | Excellent | |
| Dilute acids (HCl, H2SO4) | Excellent | |
| HF/HNO3 mixtures | Not resistant | Standard Si etchant |
| KOH/TMAH (hot) | Not resistant | Anisotropic Si etchant |
| XeF2 | Not resistant | Isotropic dry etch |
| SF6 plasma | Not resistant | Used in DRIE |
| Piranha (H2SO4/H2O2) | Resistant | Cleans but doesn't etch Si |
| BOE (buffered HF) | Resistant (etches native oxide) | Si itself is resistant |

**Temperature limits**: Up to ~1400C (melting point 1414C). Practical limit depends on dopant diffusion and device packaging.

**Biocompatibility**: Silicon is generally biocompatible but is opaque to visible/UV light, limiting optical detection. Commonly used as a bottom substrate bonded to a glass top for optical access. Excellent for applications requiring integrated electronics, heaters, or sensors.

**Key properties**: Young's modulus ~ 130-180 GPa; excellent thermal conductivity (150 W/mK); semiconductor properties enable integrated sensors; well-established MEMS fabrication processes.

---

## 4. Tubing Compatibility

### 4.1 PEEK (Polyetheretherketone)

The premium tubing material for microfluidics, standard in HPLC systems.

**Operating range**: -40C to 250C continuous; short excursions to 300C.

| Chemical | Compatibility | Notes |
|----------|--------------|-------|
| Water | Excellent | |
| Most organic solvents | Excellent | Acetone, alcohols, THF, DCM |
| Acids (dilute) | Excellent | |
| Acids (concentrated) | Good | |
| Strong oxidizing acids | Limited | Conc. HNO3, hot H2SO4 |
| Bases (dilute/moderate) | Excellent | |
| Halogenated solvents | Good | CHCl3, DCM -- much better than thermoplastics |
| Hexane, toluene | Excellent | |
| HPLC mobile phases | Excellent | All standard mobile phases |
| Acetonitrile | Excellent | |
| DMSO, DMF | Excellent | |

**Limitations**: Attacked by concentrated sulfuric acid at elevated temperatures; concentrated nitric acid; some very strong oxidizers. Opaque (tan/beige color) -- no visual flow monitoring.

**Pressure rating**: Up to 5000-10000 psi depending on wall thickness and ID/OD ratio.

### 4.2 PTFE (Polytetrafluoroethylene, Teflon)

Near-universal chemical resistance.

| Chemical | Compatibility | Notes |
|----------|--------------|-------|
| Virtually all chemicals | Excellent | |
| All organic solvents | Excellent | |
| All acids (including HF) | Excellent | |
| All bases | Excellent | |
| Strong oxidizers | Excellent | |
| Molten alkali metals | Not resistant | Only known incompatibility |
| Elemental fluorine | Not resistant | At elevated temperatures |

**Operating range**: -200C to 260C.

**Limitations**: Not transparent (white/translucent); relatively high gas permeability; higher coefficient of friction than FEP; difficult to bond; cannot be autoclaved repeatedly without degradation of mechanical properties. Poor compatibility with gamma irradiation.

### 4.3 FEP (Fluorinated Ethylene Propylene)

Similar chemical resistance to PTFE with improved processability.

| Chemical | Compatibility | Notes |
|----------|--------------|-------|
| Virtually all chemicals | Excellent | Same as PTFE |
| Molten alkali metals | Not resistant | |
| Elemental fluorine | Not resistant | At elevated temperature |

**Operating range**: -200C to 205C (slightly lower than PTFE).

**Advantages over PTFE**: Optically clear/transparent (excellent for flow visualization); lower gas permeability; better UV transmission; melt-processable (can be thermally formed/welded); smoother inner bore.

**Common use**: Preferred tubing material for droplet microfluidics due to optical clarity and chemical inertness.

### 4.4 Silicone Tubing (Platinum-cured)

| Chemical | Compatibility | Notes |
|----------|--------------|-------|
| Water | Excellent | |
| Dilute acids | Good | |
| Dilute bases | Good | |
| Alcohols | Good | |
| Acetone | Limited | Some swelling |
| Chlorinated solvents | Not resistant | Same as PDMS |
| Aromatic solvents | Not resistant | Same swelling behavior as PDMS |
| Alkanes | Not resistant | Hexane causes significant swelling |
| Mineral oils | Limited | |
| Cell culture media | Excellent | |
| Biological buffers | Excellent | |

**Operating range**: -60C to 200C (intermittent to 230C).

**Limitations**: Same absorption issues as PDMS (absorbs hydrophobic small molecules); permeable to gases (advantage for cell culture, disadvantage for anaerobic work); prone to swelling with non-polar solvents; lower pressure rating than PEEK or fluoropolymers.

**Advantages**: Flexible, easy to connect; biocompatible; gas permeable (supports cell culture); autoclavable; inexpensive.

### 4.5 Tygon Tubing

Multiple formulations available with different chemical resistance profiles:

| Formulation | Best For | Limitations | Temp Range (C) |
|-------------|---------|------------|----------------|
| E-3603 (E-Lab) | General lab use, aqueous solutions | Limited with strong solvents | -40 to 74 |
| 2375 (Ultra Chemical Resistant) | Acids, bases, ketones, salts, alcohols | Cost | -40 to 74 |
| E-LFL (Long Flex Life) | Peristaltic pumps, repeated flexing | Lower chemical resistance range | -50 to 74 |
| LMT-55 | Pump applications | Limited chemical breadth | -50 to 74 |
| XL-60 | Peristaltic pump, flexibility | Not for strong solvents | -50 to 74 |
| S3 B-44-3 (Beverage) | Food/beverage applications | Not for organic solvents | -40 to 74 |

**General Tygon limitations**: Lower temperature range than silicone or fluoropolymers; not suitable for most organic solvents; potential for plasticizer leaching in some formulations; limited pressure rating.

### 4.6 Tubing Selection Quick Reference

| Application | Recommended Tubing | Rationale |
|-------------|-------------------|-----------|
| Organic solvents | PEEK or PTFE/FEP | Chemical resistance |
| HPLC connections | PEEK | Pressure rating + compatibility |
| Droplet microfluidics | FEP | Optical clarity + inertness |
| Cell culture | Silicone (Pt-cured) | Gas permeable, biocompatible |
| Peristaltic pumps | Tygon E-LFL or silicone | Flex life |
| Acids/bases | PTFE/FEP or PEEK | Universal resistance |
| High pressure (>100 psi) | PEEK | Mechanical strength |
| Visual flow monitoring | FEP | Transparency + chemical resistance |
| Low-cost prototyping | Tygon E-Lab | Inexpensive, easy to cut |

---

## 5. Material Properties Comparison Table

### 5.1 Mechanical Properties

| Material | Young's Modulus | Tensile Strength (MPa) | Elongation at Break (%) | Hardness |
|----------|----------------|----------------------|------------------------|----------|
| PDMS (10:1) | 0.3-0.5 MPa | 3.5-7.7 | 100-300 | Shore A 44 |
| PDMS (5:1) | 1.0-1.7 MPa | 5-10 | 80-200 | Shore A 55 |
| PMMA | 3100 MPa | 70-80 | 3-5 | Rockwell M 95 |
| PC | 2400 MPa | 55-75 | 80-150 | Rockwell M 70 |
| PS | 3000-3500 MPa | 35-55 | 1-3 | Rockwell M 80 |
| COC (TOPAS) | 3200 MPa | 46-63 | 2-5 | Rockwell M 85 |
| COP (Zeonor) | 2300 MPa | 50-63 | 2-30 | Rockwell M 80 |
| Borosilicate glass | 63,000 MPa | 50 (flexural) | <0.1 | Mohs 6 |
| Fused silica | 73,000 MPa | 50 (flexural) | <0.1 | Mohs 7 |
| Silicon | 130,000-180,000 MPa | 7000 (single crystal) | <0.1 | Mohs 7 |
| PEEK | 4000 MPa | 100-110 | 30-50 | Rockwell M 99 |
| PTFE | 500-700 MPa | 20-35 | 200-400 | Shore D 55 |

### 5.2 Optical Properties

| Material | Transmission (%) | UV Cutoff (nm) | Autofluorescence | Birefringence | Refractive Index |
|----------|-----------------|----------------|-------------------|---------------|-----------------|
| PDMS | 95+ | 240 | Very low | None | 1.43 |
| PMMA | 93 | 340 | Moderate (blue-green) | Very low | 1.49 |
| PC | 88 | 380 | High | High | 1.586 |
| PS | 90 | 340 | Moderate | Low | 1.59 |
| COC (TOPAS) | 91 | 250-300 | Very low | Very low | 1.533 |
| COP (Zeonor/Zeonex) | 92 | 250-300 | Very low | Very low | 1.533 |
| Borosilicate glass | 92 | 300 | Very low | None | 1.474 |
| Fused silica | 94 | 170 | Negligible | None | 1.458 |
| Silicon | 0 (opaque) | Opaque in vis/UV | N/A | N/A | 3.42 (IR) |
| FEP | 95 | 200 | Very low | Low | 1.34 |

### 5.3 Thermal Properties

| Material | Tg (C) | Max Service Temp (C) | Thermal Conductivity (W/mK) | CTE (ppm/C) |
|----------|--------|---------------------|---------------------------|-------------|
| PDMS | -125 | 200 (intermittent 300) | 0.15 | 310 |
| PMMA | 105 | 80-95 | 0.19 | 70 |
| PC | 145-148 | 130 | 0.20 | 65-70 |
| PS | 95-100 | 70-80 | 0.13 | 70 |
| COC (TOPAS 5013) | 134 | 120 | 0.15 | 60 |
| COC (TOPAS 6017) | 178 | 160 | 0.15 | 60 |
| COP (Zeonor) | 100-139 | 90-130 | 0.15 | 60-70 |
| Borosilicate glass | 525 | 500 | 1.14 | 3.3 |
| Fused silica | 1140 | 1000 | 1.38 | 0.55 |
| Silicon | 1414 (mp) | 1200+ | 150 | 2.6 |
| PEEK | 143 | 250 | 0.25 | 47 |
| PTFE | 327 (mp) | 260 | 0.25 | 100-150 |

### 5.4 Gas Permeability and Biological Properties

| Material | O2 Permeability | Water Absorption (%) | Biocompatibility | Drug Absorption Risk |
|----------|----------------|---------------------|------------------|---------------------|
| PDMS | Very high (~600 barrer) | <0.1 | Excellent | High (LogP > 2.5) |
| PMMA | Low (~0.12 barrer) | 0.2-0.3 | Good | Low |
| PC | Very low (~1.5 barrer) | 0.15-0.3 | Good | Low |
| PS | Low (~2.6 barrer) | 0.03-0.1 | Excellent (TC-treated) | Low |
| COC/COP | Very low (~0.5 barrer) | <0.01 | Good | Very low |
| Borosilicate glass | Zero | 0 | Excellent | Negligible |
| Fused silica | Zero | 0 | Excellent | Negligible |
| Silicon | Zero | 0 | Good | Negligible |
| PEEK | Very low | 0.1-0.5 | Good | Very low |
| PTFE | Moderate (~3.5 barrer) | <0.01 | Excellent (inert) | Very low |
| FEP | Low (~2.0 barrer) | <0.01 | Excellent (inert) | Very low |
| Silicone tubing | Very high (~600 barrer) | <0.1 | Excellent | High (same as PDMS) |

**Note on gas permeability**: High O2 permeability is advantageous for cell culture (provides oxygenation) but disadvantageous for anaerobic chemistry, oxygen-sensitive reactions, and bubble-free operation.

---

## 6. Bonding Compatibility Matrix

### 6.1 PDMS Bonding to Various Substrates

| PDMS + Substrate | Bonding Method | Surface Treatment | Typical Bond Strength | Notes |
|-----------------|----------------|-------------------|----------------------|-------|
| PDMS-PDMS | O2 plasma | 30-60s O2 plasma, both surfaces | ~400 kPa burst | Bond within 15 min of treatment |
| PDMS-PDMS | Corona discharge | Handheld corona treater | ~300 kPa burst | Simpler, atmospheric pressure |
| PDMS-PDMS | Pre-polymer gluing | Spin thin PDMS layer as adhesive | ~671 kPa burst | Strongest PDMS-PDMS method |
| PDMS-Glass | O2 plasma | 30-60s O2 plasma, both surfaces | ~510 kPa burst | Most common method; Si-O-Si bonds |
| PDMS-Glass | Corona discharge | Corona treat both surfaces | ~350 kPa burst | Quick and easy |
| PDMS-Glass | UV/ozone | 10-30 min UV/ozone exposure | ~400 kPa burst | No vacuum required |
| PDMS-Silicon | O2 plasma | Same as glass | ~500 kPa burst | Native oxide surface |
| PDMS-PMMA | Chemical gluing | O2 plasma + APTES silane | ~1.6 MPa tensile | Requires organosilane coupling |
| PDMS-PC | Chemical gluing | O2 plasma + APTES silane | >1.6 MPa tensile | Higher than PMMA bond |
| PDMS-PS | Chemical gluing | O2 plasma + APTES silane | >500 kPa burst | Organosilane required |
| PDMS-COC | Air plasma | N2/O2 mixed plasma | >500 kPa burst | Optimized plasma parameters |
| PDMS-PET | Chemical gluing | O2 plasma + APTES/GPTMS | ~579 kPa burst | |
| PDMS-Metal (Au, Cu) | Chemical gluing | MPTMS thiol coupling | Thiol-metal bonds | For electrode integration |

**Critical timing**: After plasma activation, PDMS surfaces must be brought into contact within 15-60 minutes. Surface hydrophobicity recovery begins immediately and is substantially complete within 1-2 hours.

### 6.2 Thermoplastic-Thermoplastic Bonding

| Material Combination | Method | Conditions | Notes |
|---------------------|--------|-----------|-------|
| PMMA-PMMA | Thermal bonding | 90-105C, 1-5 MPa, 10-30 min | Stay below Tg to avoid channel deformation |
| PMMA-PMMA | Solvent bonding (DCM) | Room temp, brief solvent exposure | Fast; risk of channel clogging |
| PMMA-PMMA | Solvent bonding (acetic acid) | Room temp + UV | Gentler than DCM |
| PMMA-PMMA | Adhesive tape | PSA transfer tape at room temp | Quick prototyping; lower bond strength |
| PC-PC | Thermal bonding | 130-148C, 1-5 MPa | Higher temp than PMMA |
| PC-PC | Solvent bonding | Acetone/n-pentane mixture | |
| COC-COC | Thermal bonding | Near Tg (grade-dependent) | Excellent; low channel deformation possible |
| COC-COC | Solvent bonding (cyclohexane) | Brief exposure + pressure | Limited solvent options |
| COP-COP | Thermal bonding | Near Tg | Similar to COC |
| PS-PS | Thermal bonding | 80-100C | |
| PS-PS | Solvent bonding (acetone vapor) | Brief vapor exposure | |

### 6.3 Glass and Silicon Bonding

| Material Combination | Method | Conditions | Notes |
|---------------------|--------|-----------|-------|
| Glass-Glass | Fusion bonding | >600C, clean surfaces | Permanent, high strength |
| Glass-Glass | Adhesive bonding | UV-cure or thermal adhesive | Lower temp alternative |
| Glass-Glass | HF-assisted | HF pre-etch + room temp contact | For pre-etched channels |
| Glass-Silicon | Anodic bonding | 300-500C, 200-1000V DC | Gold standard; hermetic seal |
| Glass-Silicon | Adhesive bonding | Various adhesives | Lower temperature alternative |
| Silicon-Silicon | Fusion bonding | >800C, hydrophilic surfaces | Requires very clean, flat surfaces |
| Silicon-Silicon | Eutectic bonding (Au) | 363C with Au interlayer | Lower temp than fusion |

### 6.4 Cross-Material Bonding Quick Reference

This matrix indicates whether direct bonding is feasible and the preferred method:

|  | PDMS | Glass | Si | PMMA | PC | COC | PS |
|---|------|-------|----|----|----|----|-----|
| **PDMS** | Plasma | Plasma | Plasma | Silane | Silane | Plasma | Silane |
| **Glass** | Plasma | Fusion/adhesive | Anodic | Adhesive | Adhesive | Adhesive | Adhesive |
| **Si** | Plasma | Anodic | Fusion | Adhesive | Adhesive | Adhesive | Adhesive |
| **PMMA** | Silane | Adhesive | Adhesive | Thermal/solvent | Adhesive | Adhesive | Adhesive |
| **PC** | Silane | Adhesive | Adhesive | Adhesive | Thermal/solvent | Adhesive | Adhesive |
| **COC** | Plasma | Adhesive | Adhesive | Adhesive | Adhesive | Thermal | Adhesive |
| **PS** | Silane | Adhesive | Adhesive | Adhesive | Adhesive | Adhesive | Thermal/solvent |

**Key**: "Plasma" = O2 plasma activation; "Silane" = requires organosilane coupling agent; "Thermal" = thermal fusion bonding; "Solvent" = solvent-assisted bonding; "Fusion" = high-temp glass fusion; "Anodic" = anodic bonding; "Adhesive" = adhesive/tape bonding.

---

## 7. Sterilization Compatibility

### 7.1 Sterilization Methods Overview

| Method | Conditions | Mechanism | Residue Risk |
|--------|-----------|-----------|-------------|
| Autoclave (steam) | 121C, 15 psi, 15-30 min | Moist heat denatures proteins | None |
| Dry heat | 160-180C, 1-2 hours | Oxidation | None |
| Ethylene oxide (EtO) | 37-63C, 1-6 hours | Alkylation of DNA/proteins | Residual EtO (requires aeration) |
| Gamma irradiation | 25-50 kGy, ambient temp | DNA strand breakage | None |
| E-beam | 25-50 kGy, ambient temp | DNA strand breakage | None |
| UV exposure | 254 nm, 15-60 min | DNA crosslinking | None |
| H2O2 plasma | 37-44C, 30-75 min | Oxidation | Minimal |
| 70% ethanol | Room temp, 10-30 min | Protein denaturation/dehydration | Residual ethanol |

### 7.2 Material-Sterilization Compatibility Matrix

| Material | Autoclave (121C) | Dry Heat (170C) | EtO | Gamma | E-beam | UV | H2O2 Plasma | 70% EtOH |
|----------|-----------------|----------------|-----|-------|--------|----|------------|----------|
| PDMS | Good | Good | Good | Good | Good | Good* | Good | Good |
| PMMA | FAIL (Tg 105) | FAIL | Good | Good | Good | Good | Good | Caution** |
| PC | Marginal (Tg 148) | FAIL | Good | Good | Good | Good | Good | Good |
| PS | FAIL (Tg 100) | FAIL | Good | Good | Good | Good | Good | Good |
| COC (high Tg) | Marginal*** | FAIL | Good | Good | Good | Good | Good | Good |
| COP | FAIL to Marginal | FAIL | Good | Good | Good | Good | Good | Good |
| Borosilicate glass | Excellent | Excellent | Good | N/A | N/A | Excellent | Good | Excellent |
| Fused silica | Excellent | Excellent | Good | N/A | N/A | Excellent | Good | Excellent |
| Silicon | Excellent | Excellent | Good | N/A | N/A | Excellent | Good | Excellent |
| PEEK | Excellent | Good | Good | Good | Good | Good | Good | Excellent |
| PTFE | Good | Good | Good | FAIL | FAIL | Good | Good | Excellent |
| FEP | Good | Good | Good | Fair | Fair | Good | Good | Excellent |
| Silicone tubing | Good | Good | Good | Good | Good | Good* | Good | Good |

**Notes**:
- \* UV can degrade PDMS/silicone after repeated sterilization cycles (surface becomes brittle)
- \** Ethanol can cause stress cracking in PMMA under mechanical stress
- \*** Only COC grades with Tg > 140C (e.g., TOPAS 6015, 6017) may survive autoclaving; lower Tg grades will deform

### 7.3 Sterilization Recommendations by Material

**PDMS devices**:
- Preferred: Autoclave (single use), UV exposure, 70% ethanol rinse
- Also suitable: EtO, gamma irradiation
- Caution: Repeated autoclaving can alter mechanical properties; repeated UV degrades surface

**Thermoplastic devices (PMMA, PS, COC, COP)**:
- Preferred: EtO sterilization (low temperature, compatible with all)
- Also suitable: Gamma/E-beam irradiation (except check dose limits for specific grades)
- Suitable for quick lab sterilization: UV exposure, 70% ethanol rinse
- Avoid: Autoclave (except high-Tg COC/PC), dry heat

**PC devices** (special case -- high Tg):
- Can sometimes survive autoclave at 121C (Tg is 148C, but bonded devices may delaminate)
- Preferred for production: Gamma irradiation or EtO

**Glass and silicon devices**:
- Preferred: Autoclave or dry heat (no material concerns)
- All other methods also compatible
- Glass bonded to polymers: sterilize according to the polymer's limitations

**Tubing sterilization**:
- PEEK: Autoclave or any chemical method
- PTFE/FEP: Autoclave or chemical methods; avoid gamma for PTFE
- Silicone: Autoclave or any method
- Tygon: EtO or 70% ethanol only (low Tg)

### 7.4 Sterilization Decision Flowchart

```
Is the device made entirely of glass/silicon/metal?
  YES --> Autoclave (simplest, most reliable)
  NO --> Contains thermoplastics or elastomers?
    Is the device for single-use disposable application?
      YES --> Gamma or E-beam irradiation (industrial scale)
            or EtO (smaller batches)
    Is it for reusable lab application?
      YES --> Can the material withstand 121C?
        YES --> Autoclave
        NO --> UV exposure or 70% ethanol rinse (quick lab sterilization)
              or EtO (thorough sterilization)
    Does the application involve drug studies?
      YES --> Avoid EtO (residue concern)
            Use gamma, UV, or 70% ethanol
```

---

## Quick Reference Cards

### Material Selection by Application

| Application | Recommended Materials | Avoid |
|-------------|----------------------|-------|
| Organic synthesis (polar solvents) | Glass, silicon, COC, PEEK | PDMS, PMMA, PS |
| Organic synthesis (non-polar solvents) | Glass, silicon, PTFE/FEP | All polymers |
| Cell culture / organ-on-chip | PDMS, PS, glass, COC | -- |
| Drug screening | Glass, COC, COP, PMMA | PDMS (absorption) |
| PCR / thermal cycling | Glass, PC, high-Tg COC | PDMS (gas perm.), PMMA, PS |
| Fluorescence detection | Glass, fused silica, COC/COP | PC (autofluorescence) |
| Disposable diagnostics | COC, COP, PMMA, PS | Glass (cost), silicon (cost) |
| High-pressure applications | Glass, silicon, PEEK | PDMS (low modulus) |
| Rapid prototyping | PDMS, PMMA (laser cut) | Glass, silicon (slow fab) |
| Droplet generation | PDMS, glass, FEP tubing | -- |

### Solvent Selection by Device Material

| Device Material | Safe Solvents | Unsafe Solvents |
|-----------------|--------------|----------------|
| PDMS | Water, DMSO, DMF, glycols, acetonitrile, perfluorosolvents | Hexane, toluene, chloroform, THF, ether |
| PMMA | Water, DMSO, dilute acids/bases | Acetone, chloroform, DCM, THF, toluene, alcohols (caution) |
| PC | Water, dilute acids/bases, alcohols | Acetone, chloroform, DCM, THF, toluene |
| COC/COP | Water, acetone, alcohols, DMSO, acids, bases | Toluene, hexane, chloroform, DCM |
| PS | Water, DMSO, dilute acids/bases, alcohols | Acetone, toluene, chloroform, DCM, THF |
| Glass | Everything except HF | HF, hot concentrated alkali |
| Silicon | Most solvents | KOH/TMAH (hot), HF/HNO3 mixtures |

---

## References and Sources

1. Lee, J.N., Park, C., Whitesides, G.M. "Solvent Compatibility of Poly(dimethylsiloxane)-Based Microfluidic Devices." *Analytical Chemistry* 75, 6544-6554 (2003). https://pubs.acs.org/doi/10.1021/ac0346712
2. Toepke, M.W., Beebe, D.J. "PDMS absorption of small molecules and consequences in microfluidic applications." *Lab on a Chip* 6, 1484-1486 (2006). https://pubmed.ncbi.nlm.nih.gov/17203151/
3. Wang, J.D., et al. "Quantitative analysis of molecular absorption into PDMS microfluidic channels." *Annals of Biomedical Engineering* 40, 1862-1873 (2012). https://pubmed.ncbi.nlm.nih.gov/22484830/
4. Nunes, P.S., et al. "Cyclic olefin polymers: emerging materials for lab-on-a-chip applications." *Microfluidics and Nanofluidics* 9, 145-161 (2010). https://link.springer.com/article/10.1007/s10404-010-0605-4
5. Agha, A., et al. "A Review of Cyclic Olefin Copolymer Applications in Microfluidics." *Macromolecular Materials and Engineering* 307, 2200053 (2022). https://onlinelibrary.wiley.com/doi/full/10.1002/mame.202200053
6. Borók, A., et al. "PDMS Bonding Technologies for Microfluidic Applications: A Review." *Biosensors* 11, 292 (2021). https://pmc.ncbi.nlm.nih.gov/articles/PMC8394141/
7. Tsao, C.W. "Recent Advances in Thermoplastic Microfluidic Bonding." *Micromachines* 13, 486 (2022). https://pmc.ncbi.nlm.nih.gov/articles/PMC8949906/
8. PDMS Chemical Resistance Chart -- Darwin Microfluidics. https://blog.darwin-microfluidics.com/pdms-chemical-resistance-chart/
9. TOPAS COC Chemical Resistance Chart -- Darwin Microfluidics. https://blog.darwin-microfluidics.com/topas-coc-chemical-resistance-chart/
10. Chemical Resistance of Microfluidic Materials -- Elveflow. https://www.elveflow.com/microfluidic-reviews/general-microfluidics/chemical-resistance-of-microfluidic-materials/
11. Material Selection for Microfluidic Devices -- Parallel Fluidics. https://www.parallelfluidics.com/resources/knowledge-base/material-selection-for-microfluidic-devices
12. Sterilization Guide for Microfluidic Medical Devices -- Parallel Fluidics. https://www.parallelfluidics.com/resources/knowledge-base/sterilization-guide-for-microfluidic-medical-devices
13. Gamma Irradiation Sterilization Compatibility Chart -- Darwin Microfluidics. https://blog.darwin-microfluidics.com/gamma-irradiation-sterilization-compatibility-chart/
14. PEEK Chemical Compatibility -- Darwin Microfluidics. https://blog.darwin-microfluidics.com/peek-chemical-compatibility/
15. Fluoropolymer Tubing in Microfluidics -- Darwin Microfluidics. https://blog.darwin-microfluidics.com/fluoropolymer-tubing-in-microfluidics-a-short-guide/
16. TOPAS COC Polymers product information. https://topas.com/products/topas-coc-polymers/
17. Zeon Specialty Materials -- COP for microfluidics. https://zeonsmi.com/applications/microfluidics/
18. Sciuto, E.L., et al. "Sorption and release of small molecules in PDMS and COC for Organs on chip." *Scientific Reports* 15, 97111 (2025). https://www.nature.com/articles/s41598-025-97111-2
