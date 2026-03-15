# Microfluidics for Environmental Monitoring and Energy Applications

## Overview

Microfluidic technologies are transforming environmental monitoring and energy research by enabling portable, low-cost, rapid-response analytical platforms. From detecting trace heavy metals in drinking water to harvesting energy from microbial fuel cells, lab-on-a-chip systems offer miniaturization, automation, and integration advantages that are driving deployment across water quality, air quality, energy storage, biodiversity monitoring, and precision agriculture domains.

---

## 1. Water Quality Monitoring

### 1.1 Heavy Metal Detection

Heavy metal contamination (lead, arsenic, mercury, cadmium, chromium) in water supplies remains a critical global health concern. Microfluidic platforms offer significant advantages over conventional laboratory methods (ICP-MS, AAS) for field-deployable detection.

#### Detection Methods

| Method | Target Metals | LOD Range | Advantages | Limitations |
|--------|--------------|-----------|------------|-------------|
| Electrochemical (ASV) | Pb, Cd, Cu, Hg | 0.1-10 ppb | High sensitivity, real-time | Electrode fouling |
| Colorimetric | As, Pb, Hg | 1-50 ppb | Simple, visual readout | Limited sensitivity |
| Fluorescence | Hg, Pb, Cd | 0.01-1 ppb | Ultra-sensitive | Complex optics |
| Chemiluminescence | Cu, Cr, Fe | 0.1-5 ppb | No excitation source needed | Reagent consumption |
| LIBS (laser-induced) | Multi-metal | 1-100 ppb | Multi-element, rapid | Equipment cost |
| SERS | Hg, As, Pb | 0.001-0.1 ppb | Extremely sensitive | Substrate preparation |

#### Device Architectures

- **PDMS-based lab-on-chip (LOC)**: Standard platform with integrated electrodes, mixing channels, and detection zones; well-suited for electrochemical detection of Pb, Cd, and Cu
- **Paper-based microfluidics (muPADs)**: Ultra-low-cost devices using capillary-driven flow; ideal for colorimetric detection in resource-limited settings; cost as low as $0.01-0.10 per device
- **3D-printed systems**: Rapid prototyping of complex channel geometries; integration of multi-stage sample preparation and detection
- **Digital microfluidics (DMF)**: Electrowetting-based droplet manipulation; enables multiplexed analysis of multiple metals from a single sample
- **Foldable paper-LIBS devices**: A 2026 development combining colorimetric and LIBS detection achieves dual-mode quantification with R-squared = 0.999 and low detection limits

#### Nanomaterial Enhancements

- Carbon nanotubes and graphene-modified electrodes improve electrochemical sensitivity by 10-100x
- Gold and silver nanoparticles enable SERS-based detection at sub-ppb levels
- Metal-organic frameworks (MOFs) provide selective pre-concentration of target ions
- Quantum dots serve as fluorescent probes for multiplexed metal ion detection

#### AI Integration

Emerging platforms combine microfluidic sensors with artificial intelligence for automated contaminant identification, pattern recognition across multiple analytes, and predictive water quality modeling from real-time sensor data.

### 1.2 Pathogen Detection in Water

Waterborne pathogens (bacteria, viruses, protozoa) cause billions of cases of illness annually. Microfluidic platforms are replacing culture-based methods that require 24-72 hours.

#### Bacterial Detection

- **Centrifugal microfluidic platforms**: Integrate cell lysis, nucleic acid extraction, reagent mixing, and droplet digital LAMP (ddLAMP) on a single disc; complete workflow in under 90 minutes
- **Electrochemical biosensors**: Fully automated detection of E. coli achieving LOD of 50 CFU/mL; antibody- or aptamer-functionalized electrodes
- **Impedimetric sensors**: Real-time monitoring of bacterial growth through impedance changes in microchannels
- **Portable pathogen analysis systems (PPAS)**: Point-of-sample collection systems for field deployment with smartphone readout

#### Virus Detection

- **Centrifugal microfluidic disc (CD)**: Integrates sample concentration, purification, and droplet digital RT-LAMP for virus detection in wastewater; total assay time under 1.5 hours
- **CRISPR-based detection**: Integration of CRISPR-Cas12/Cas13 with microfluidic isothermal amplification for ultrasensitive virus detection
- **Lateral flow integration**: Combining microfluidic sample preparation with lateral flow immunoassay readout for point-of-use testing

#### Key Pathogens Targeted

| Pathogen | Detection Method | Time | LOD |
|----------|-----------------|------|-----|
| E. coli | Electrochemical | 30-60 min | 50 CFU/mL |
| Salmonella | LAMP on chip | 45 min | 100 CFU/mL |
| Cryptosporidium | Immunomagnetic + fluorescence | 2 hr | 10 oocysts/L |
| Norovirus | ddRT-LAMP | 90 min | 10 copies/mL |
| Legionella | qPCR on chip | 60 min | 50 copies/mL |
| SARS-CoV-2 | RT-LAMP | 30-45 min | 5 copies/uL |

### 1.3 Nutrient Monitoring (Nitrate, Phosphate, Ammonium)

Excess nutrients in water bodies cause eutrophication, harmful algal blooms, and dead zones. Continuous in-situ monitoring is essential.

#### Microfluidic Approaches

- **Wet chemistry on chip**: Miniaturized versions of standard colorimetric assays (Griess reaction for nitrate/nitrite, molybdenum blue for phosphate) with integrated optical detection
- **Droplet microfluidics**: Compartmentalized reactions in nanoliter droplets enable non-drifting, lab-quality measurements over extended deployments
- **Capillary electrophoresis on chip**: Simultaneous separation and detection of NO3-, NH4+, K+, and PO4^3- using conductivity measurement
- **Dual-chemistry sensors**: Single instruments measuring both nitrate and dissolved orthophosphate simultaneously, reducing instrument costs

#### Commercial Microfluidic Water Analyzers

| Product/Company | Parameters | Deployment | Key Features |
|----------------|------------|------------|--------------|
| ClearWater Lab-on-Chip (Aquatic Sensors) | Phosphate, nitrate, silicate, dissolved Fe, pH | Submersible to 6000 m | 1-year deployment, 6-min measurement interval, user-swappable reagent canisters |
| Hach portable instruments | Multi-parameter | Field portable | Established market leader, broad parameter range |
| LabSTAF (Chelsea Technologies) | Chlorophyll fluorescence | In-situ | Phytoplankton productivity monitoring |
| SubChemPak (Systea) | Nutrients | Submersible | Autonomous nutrient analysis |

The ClearWater Lab-on-Chip range, originally developed at the National Oceanography Centre (over 200 units deployed worldwide), uses patented flow cell technology for miniaturized, sensitive, and robust submersible chemical sensors.

---

## 2. Air Quality Monitoring

### 2.1 Gas Sensors on Chip

Microfluidic gas sensors offer high accuracy, fast response and recovery times, low cost, ease of use, and reduced analyte/reagent consumption compared to conventional gas analyzers.

#### Monolithic Gas Chromatography on Chip

A breakthrough development (2026) integrated all fluidic components of a gas chromatography system onto a single 15 x 15 mm chip:

- **Platform**: Silicon-on-insulator (SOI) sandwiched between two layers of fused silica
- **Innovation**: Three Knudsen pumps that move gas molecules using heat differentials, eliminating the need for valves
- **Applications**: Industrial chemical/pharmaceutical synthesis monitoring, natural gas pipeline monitoring, residential air quality
- **Name**: Monolithic Gas Sampling and Analysis (monoGSA) system

#### Detection Principles

| Principle | Target Gases | Response Time | Sensitivity |
|-----------|-------------|---------------|-------------|
| Metal oxide semiconductor (MOS) | CO, NO2, O3 | 1-30 s | ppb-ppm |
| Electrochemical | CO, SO2, NO2, O3 | 5-60 s | ppb |
| Optical absorption | CO2, CH4, VOCs | 1-10 s | ppm |
| Surface acoustic wave (SAW) | VOCs, nerve agents | < 1 s | ppb |
| Quartz crystal microbalance (QCM) | VOCs, humidity | 1-5 s | ppb |
| Fabry-Perot interferometry | Refractive index gases | < 1 s | ppm |
| Photoionization (PID) | Total VOCs | < 1 s | ppb |

#### Microfluidic Advantages for Gas Detection

- Precise control of gas-sensor interaction through channel geometry optimization
- Integration of pre-concentration, separation, and detection on a single platform
- Reduced power consumption suitable for battery-operated deployment
- Multiplexed sensing through parallel channel architectures
- Enhanced mass transfer at the microscale improves sensitivity

### 2.2 Particulate Matter Analysis

- **Optical scattering cells**: LED-based (780 nm) scattering measurement for PM2.5 quantification in microfluidic flow cells
- **Inertial focusing**: Microfluidic channels exploit particle inertia to size-fractionate airborne particles (PM10, PM2.5, PM1.0)
- **Impactor-on-chip**: Miniaturized virtual impactors for size-selective sampling with downstream chemical analysis
- **Electrostatic collection**: On-chip electrostatic precipitators concentrate particles for elemental analysis

### 2.3 Volatile Organic Compound (VOC) Detection

#### Microfluidic VOC Sensing Platforms

- **Micro gas chromatography (muGC)**: On-chip separation columns with functionalized stationary phases; MEMS-fabricated for portability
- **Nanostructured microfluidic olfaction**: Parylene C-coated microchannels with polymer nanoparticles (e.g., PMMA with molecular imprinting) for selective VOC recognition
- **CMUT sensor arrays**: Capacitive micromachined ultrasonic transducer arrays for multiplex detection of toluene, acetone, ethanol, and methanol from a single readout system
- **Graphene oxide-coated microchannels**: Cylindrical microfeatures with GO coatings for selective VOC detection with enhanced surface area

#### Target VOCs and Applications

| VOC Category | Examples | Source | Health Impact |
|-------------|----------|--------|---------------|
| Aromatic hydrocarbons | Benzene, toluene, xylene | Industrial, traffic | Carcinogenic |
| Aldehydes | Formaldehyde, acetaldehyde | Building materials | Respiratory irritation |
| Halogenated compounds | Chloroform, TCE | Industrial, water treatment | Liver/kidney damage |
| Ketones | Acetone, MEK | Solvents, coatings | CNS effects |
| Alcohols | Methanol, ethanol | Fuels, solvents | Varied toxicity |

---

## 3. Energy Applications

### 3.1 Microfluidic Fuel Cells

Microfluidic fuel cells exploit laminar flow at the microscale to maintain separation between fuel and oxidant streams without a physical membrane, reducing cost and complexity.

#### Types and Performance

| Type | Fuel | Oxidant | Power Density | Key Feature |
|------|------|---------|---------------|-------------|
| Membraneless (co-laminar) | Formic acid, methanol | Dissolved O2, KMnO4 | 50-300 mW/cm2 | No membrane needed |
| Enzymatic biofuel cell | Glucose | O2 | 1-50 uW/cm2 | Biocompatible |
| Microbial fuel cell (MFC) | Organic waste | O2 | 0.1-10 mW/cm2 | Self-sustaining |
| 3D-printed multichannel | Glucose | O2 | 265 uW/cm2 | 24% improvement via geometry |
| Air-breathing | Methanol, ethanol | Air | 100-500 mW/cm2 | Simplified cathode |
| Vanadium redox | V2+/V3+ | V4+/V5+ | 10-100 mW/cm2 | Rechargeable |

#### Recent Innovations (2025-2026)

- **3D-printed multichannel architectures**: Multi-stage series microfluidic fuel cells achieving 0.87 V and 265 uW/cm2 power density through optimized channel geometries
- **TiS2 nanosheet anodes**: Vertically oriented TiS2 nanosheets synthesized via facile and scalable methods for green energy harvesting in microfluidic microbial fuel cells
- **Miniaturized microbial fuel cells (MMFCs)**: Emerging as next-generation power sources for microelectronics and smart medical devices; applications in biosensing, ingestible electronics, and environmental monitoring by harvesting energy from wastewater, bodily fluids, and gut microbiota

### 3.2 Battery Research on Chip

Microfluidic platforms serve as analytical tools and testing platforms for battery development.

#### Applications

- **Electrolyte screening**: Rapid evaluation of electrolyte compositions using microfluidic flow cells with controlled electrochemical environments
- **Electrode material testing**: High-throughput screening of electrode materials with minimal material consumption (microliters vs. milliliters)
- **Degradation studies**: Real-time monitoring of electrode degradation mechanisms under controlled flow and temperature conditions
- **Redox flow batteries**: Microfluidic redox batteries as proof-of-concept platforms for studying vanadium, zinc-bromine, and organic redox chemistries
- **Nanomaterial synthesis**: Microfluidic synthesis of micro/nanomaterials with controlled morphology for enhanced electrochemical energy storage performance

#### Microfluidic Advantages for Battery R&D

- Controlled mass transport at microscale reduces variability
- Real-time electrochemical characterization during operation
- Minimal material consumption accelerates screening campaigns
- Integration of optical/spectroscopic monitoring during cycling
- Cost-effective laboratory-scale approach before scale-up

### 3.3 Solar Cell Testing

- **Microfluidic all-vanadium photoelectrochemical cell (muVPEC)**: Designed for solar energy storage; miniaturization enhances photon and mass transport, reduces internal cell resistance, and improves uniformity of light distribution
- **Dye-sensitized solar cells (DSSCs)**: Microfluidically augmented DSSCs integrate nanoscale materials with microfluidic architectures for performance and longevity enhancement
- **Artificial photosynthesis test-bed**: Berkeley Lab's JCAP developed the first fully integrated microfluidic test-bed for evaluating solar-driven electrochemical energy conversion, adaptable for photovoltaic electrolysis and fuel cell research
- **Microfluidic electrolyzers**: Testing platforms for water splitting and CO2 reduction using solar-generated electricity

### 3.4 Electrochemical Energy Storage and Conversion

A comprehensive 2025-2026 review (Lab on a Chip) identifies microfluidic tools as accelerators for diverse electrochemical technologies:

#### Key Research Areas

- **Batteries**: Flow cell configurations for studying lithium-ion, sodium-ion, and solid-state battery chemistries
- **Fuel cells**: Membraneless designs, catalyst screening, and degradation monitoring
- **Electrolyzers**: Water electrolysis and CO2 reduction with controlled mass transport
- **Supercapacitors**: Electrode material evaluation and electrolyte optimization

#### Scale-Up Pathway

Microfluidic platforms provide insights that guide scale-up by:
1. Establishing fundamental electrochemical kinetics at controlled conditions
2. Screening materials and conditions at low cost
3. Validating computational models with experimental microfluidic data
4. Identifying degradation mechanisms before committing to large-scale testing

---

## 4. Environmental DNA (eDNA)

### 4.1 Overview

Environmental DNA (eDNA) technology enables detection of organisms through genetic material shed into the environment (water, soil, air) without requiring direct observation or capture. Microfluidic platforms are accelerating eDNA analysis by integrating sampling, extraction, amplification, and detection.

### 4.2 Microfluidic eDNA Analysis Platforms

#### Sample Processing on Chip

| Step | Microfluidic Approach | Advantage |
|------|----------------------|-----------|
| Water sampling | Automated filtration and concentration | Standardized collection volumes |
| DNA extraction | On-chip lysis and solid-phase extraction | Reduced contamination risk |
| Amplification | Digital PCR, qPCR, LAMP | Quantitative, sensitive |
| Detection | Fluorescence, electrochemical | Real-time readout |
| Data analysis | Integrated microprocessor | Field-deployable results |

#### Key Technologies

- **Microfluidic centrifugation-assisted precipitation**: Increases detection limits and efficiency by enabling quick and quantitative DNA analysis from environmental water samples
- **High-throughput qPCR (HT-qPCR)**: The BiomarkHD microfluidic platform enables large-scale parallel eDNA analysis, processing hundreds of samples simultaneously
- **Droplet digital PCR (ddPCR)**: Absolute quantification of eDNA copies without calibration curves; microfluidic droplet generation produces thousands of reaction partitions
- **Isothermal amplification (LAMP)**: Simplified thermal requirements enable battery-powered field devices

### 4.3 Species Identification

#### Applications

- **Aquatic biodiversity**: Detection of fish, amphibians, and invertebrate species from water samples without electrofishing or netting
- **Invasive species monitoring**: Early detection of invasive species (e.g., Asian carp, zebra mussels) from trace eDNA in waterways
- **Endangered species surveys**: Non-invasive monitoring of threatened species populations
- **Pathogen surveillance**: Detection of wildlife diseases (e.g., chytrid fungus, ranavirus) from environmental samples

#### Multiplexed Detection

- Metabarcoding on microfluidic platforms enables simultaneous detection of hundreds of species from a single water sample
- Species-specific microfluidic assays targeting mitochondrial DNA markers (COI, 12S, 16S rRNA genes)
- Custom primer panels designed for regional biodiversity assessment

### 4.4 Biodiversity Monitoring

#### Field Deployment Advances (2025-2026)

- **Airborne eDNA**: Proof-of-concept studies demonstrating detection of mosquito species (Aedes albopictus) from airborne eDNA, expanding beyond traditional water-based sampling
- **On-farm water source surveillance**: Standardized eNA (environmental nucleic acid) sampling methods for early detection of pathogens in agricultural water sources; comparison of four water-sampling methods shows all approaches effectively recover community profiles
- **Real-time environmental monitoring**: Lab-on-chip systems enabling in-situ eDNA analysis of water bodies without sample transport to centralized laboratories
- **Standardization efforts**: Development of standardized protocols for eDNA collection, storage, extraction, and analysis to ensure data comparability across studies

#### Challenges and Future Directions

- eDNA degradation rates vary with environmental conditions (UV, temperature, pH, microbial activity)
- Distinguishing between live organisms and recently dead organisms remains difficult
- Quantitative interpretation requires understanding of eDNA shedding and transport dynamics
- Integration of eDNA data with traditional survey methods for comprehensive biodiversity assessment
- Advancing accuracy, scalability, and applicability of eDNA across diverse ecosystems

---

## 5. Soil and Agriculture

### 5.1 Soil Nutrient Analysis on Chip

#### Target Analytes and Methods

| Nutrient | Detection Method | LOD | Measurement Time |
|----------|-----------------|-----|-----------------|
| Nitrate (NO3-) | Colorimetric (Griess) | 0.1 mg/L | 5-10 min |
| Ammonium (NH4+) | Berthelot reaction | 0.05 mg/L | 10 min |
| Phosphate (PO4^3-) | Molybdenum blue | 0.01 mg/L | 10-15 min |
| Potassium (K+) | Capillary electrophoresis | 0.5 mg/L | 5 min |
| pH | Electrochemical / indicator | 0.1 pH unit | Instant |
| Electrical conductivity | Conductimetric | 10 uS/cm | Instant |

#### Integrated Platforms

- **Mobile lab-on-a-chip**: Portable devices integrating soil solution extraction with multi-parameter nutrient analysis; designed for on-site use in agricultural fields
- **Microfluidic soil nutrient detection systems**: Simultaneous measurement of nitrite, pH, and electrical conductivity on a single chip
- **Capillary electrophoresis on chip**: Separation and detection of multiple ion species (NO3-, NH4+, K+, PO4^3-) from soil extracts using conductivity measurement
- **Droplet microfluidic soil nitrate monitor**: In-situ sensor using droplet microfluidics for continuous monitoring of free nitrate in soil with minimal reagent consumption

#### Soil Solution Extraction

- Microfluidic extraction of soil solution directly into chip channels
- Challenges include particulate filtering and matrix complexity
- Pre-treatment steps (washing, filtering) remain time-consuming
- Ongoing development of integrated sample preparation modules

### 5.2 Pesticide Detection

#### Detection Approaches

- **Centrifugal microfluidic devices**: Automated detection of pesticide residues in vegetables and soil with minimal sample preparation
- **IR absorption microspectroscopy**: Analysis of organic pollutants including petroleum hydrocarbons, polyaromatic hydrocarbons, and organic pesticides/herbicides in soil matrices
- **Raman scattering microspectroscopy**: Surface-enhanced Raman spectroscopy (SERS) on microfluidic platforms for trace pesticide identification
- **Enzyme inhibition assays**: Acetylcholinesterase (AChE) inhibition assays miniaturized on chip for organophosphate and carbamate detection
- **Immunoassay-based detection**: Antibody-functionalized microfluidic channels for specific pesticide identification

#### Target Pesticides

| Class | Examples | Detection Method | LOD |
|-------|----------|-----------------|-----|
| Organophosphates | Malathion, chlorpyrifos | AChE inhibition | 0.1 ug/L |
| Carbamates | Carbofuran, carbaryl | AChE inhibition | 0.5 ug/L |
| Neonicotinoids | Imidacloprid, thiamethoxam | Immunoassay | 0.01 ug/L |
| Triazines | Atrazine, simazine | Immunoassay | 0.05 ug/L |
| Glyphosate | Glyphosate, AMPA | Electrochemical | 1 ug/L |
| Pyrethroids | Permethrin, cypermethrin | SERS | 0.1 ug/L |

### 5.3 Plant Health Monitoring

#### Microfluidic Applications

- **Phytohormone analysis**: On-chip measurement of plant hormones (auxin, cytokinin, abscisic acid) from sap or tissue extracts
- **Disease diagnosis**: Nucleic acid-based detection of plant pathogens (bacteria, fungi, viruses) using isothermal amplification on chip
- **Mycotoxin detection**: Microfluidic immunoassays for aflatoxin, ochratoxin, and deoxynivalenol in grain and feed samples
- **Nutrient deficiency assessment**: Rapid analysis of plant tissue nutrient status through on-chip colorimetric assays
- **Sap flow analysis**: Microfluidic sensors integrated with plant stems for real-time monitoring of water transport

#### Precision Agriculture Integration

- **Smartphone-coupled devices**: Microfluidic sensors integrated with smartphone cameras for colorimetric readout; GPS-tagged results for spatial nutrient mapping
- **IoT connectivity**: Wireless data transmission from field-deployed sensors to cloud platforms for real-time decision support
- **Drone-deployed sensors**: Concept designs for aerial deployment of microfluidic sampling devices across large agricultural areas

---

## 6. Cross-Cutting Technologies

### 6.1 Materials for Environmental Microfluidics

| Material | Advantages | Typical Application |
|----------|-----------|-------------------|
| PDMS | Flexible, transparent, biocompatible | Laboratory prototyping |
| Paper | Ultra-low cost, disposable, capillary-driven | Field screening |
| Glass | Chemical resistance, optical clarity | Long-term deployment |
| PMMA/COC | Mass-producible, low cost | Commercial devices |
| 3D-printed resins | Rapid prototyping, complex geometries | Research platforms |
| Silicon | Precise microfabrication, electronic integration | Gas sensors, MEMS |

### 6.2 Detection Modalities Summary

| Modality | Sensitivity | Cost | Field Deployability | Best For |
|----------|------------|------|-------------------|----------|
| Electrochemical | High | Low | Excellent | Metals, nutrients, gases |
| Colorimetric | Moderate | Very low | Excellent | Screening, paper devices |
| Fluorescence | Very high | Moderate | Good | DNA, pathogens, metals |
| SERS | Ultra-high | High | Moderate | Trace organics, pesticides |
| Mass spectrometry | Ultra-high | Very high | Poor | Comprehensive analysis |
| Impedimetric | High | Low | Excellent | Bacteria, cells |

### 6.3 Challenges and Future Directions

#### Current Challenges

- **Sample complexity**: Environmental samples (soil, wastewater) require extensive pre-treatment that is difficult to integrate on chip
- **Selectivity in complex matrices**: Interference from matrix components reduces accuracy in real-world samples
- **Long-term stability**: Reagent degradation, biofouling, and sensor drift limit deployment duration
- **Scalability**: Transitioning from laboratory prototypes to commercially viable products remains difficult
- **Standardization**: Lack of standardized protocols and reference methods for microfluidic environmental analysis
- **Power requirements**: Field-deployed devices need low-power operation or energy harvesting capability

#### Future Directions

- **AI-integrated sensing**: Machine learning for pattern recognition, sensor drift compensation, and multi-analyte classification from sensor arrays
- **Sustainable fabrication**: Biodegradable substrates and green manufacturing processes for disposable environmental sensors
- **Autonomous monitoring networks**: Self-powered sensor nodes with wireless connectivity forming distributed environmental monitoring grids
- **Multi-modal integration**: Combining chemical, biological, and physical sensing on single platforms for comprehensive environmental assessment
- **Digital twins**: Coupling real-time microfluidic sensor data with computational environmental models for predictive monitoring

---

## 7. Key Resources and References

### Review Articles and Key Publications

- "Innovative Microfluidic Technologies for Rapid Heavy Metal Ion Detection" - MDPI Chemosensors (2025)
- "A foldable and paper-based microfluidic device integrated with LIBS and colorimetric for accurate heavy metals detection" - Sensors and Actuators B (2026)
- "Microfluidic tools for electrochemical energy storage and conversion" - Lab on a Chip (2026)
- "Recent Advances in Microfluidics-Based Monitoring of Waterborne Pathogens" - PMC (2025)
- "Environmental DNA (eDNA) Technology in Biodiversity and Ecosystem Health Research" - PMC (2025)
- "Microfluidics in environmental analysis: advancements, challenges, and future prospects" - Lab on a Chip (2024)
- "Microfluidic integrated gas sensors for smart analyte detection" - Frontiers in Chemistry (2023)

### Commercial Platforms and Companies

| Company | Product | Application |
|---------|---------|-------------|
| Aquatic Sensors | ClearWater Lab-on-Chip | Submersible nutrient monitoring |
| Hach | Portable analyzers | Multi-parameter water quality |
| Aeroqual | Series 500 | Portable VOC monitoring |
| Chelsea Technologies | LabSTAF | Phytoplankton monitoring |
| Systea | SubChemPak | Autonomous nutrient analysis |

### Online Resources

- [MDPI Chemosensors - Heavy Metal Detection Review](https://www.mdpi.com/2227-9040/13/4/149)
- [Frontiers - Microfluidic Gas Sensors Review](https://www.frontiersin.org/journals/chemistry/articles/10.3389/fchem.2023.1267187/full)
- [Lab on a Chip - Electrochemical Energy Tools](https://pubs.rsc.org/en/content/articlehtml/2026/lc/d5lc00445d)
- [PMC - Waterborne Pathogen Monitoring](https://pmc.ncbi.nlm.nih.gov/articles/PMC12029729/)
- [Frontiers - Low-cost Microfluidics for Environmental Monitoring](https://www.frontiersin.org/journals/lab-on-a-chip-technologies/articles/10.3389/frlct.2022.1074009/full)
- [Aquatic Sensors - ClearWater Product Range](https://www.aquaticsensors.com/product/nitrate-sensor/)
- [TechXplore - Monolithic Gas Analysis Chip](https://techxplore.com/news/2026-02-microfluidic-chip-gases-motionless.html)

---

*Last updated: 2026-03-15*
