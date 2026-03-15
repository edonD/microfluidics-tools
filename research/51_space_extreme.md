# Microfluidics for Space Applications and Extreme Environments

## Overview

Microfluidic technologies offer transformative advantages for operations in space, extreme terrestrial environments, and resource-limited settings. Their small size, low reagent consumption, minimal power requirements, and capacity for automation make them uniquely suited to contexts where conventional laboratory infrastructure is unavailable. This document surveys the state of the art in microfluidics for space missions, extreme environment deployment, planetary science, defense applications, and off-grid field use.

---

## 1. Microfluidics in Space

### 1.1 How Microgravity Affects Microfluidic Flow

Microgravity fundamentally changes fluid behavior in ways that are both challenging and advantageous for microfluidic systems:

- **No buoyancy-driven convection**: In the absence of gravity, there is no natural convection. Density differences between fluids or between phases (e.g., gas bubbles in liquid) do not cause movement. This eliminates a key mixing mechanism but also removes a source of uncontrolled variability.
- **No sedimentation**: Particles, cells, and beads remain suspended indefinitely. On Earth, sedimentation can clog channels or create nonuniform distributions; in microgravity, this problem disappears.
- **Surface tension dominance**: With gravitational forces negligible, surface tension and capillary forces dominate fluid behavior. Meniscus shapes, wetting, and contact-line dynamics become the primary determinants of flow patterns.
- **Bubble management**: Gas bubbles do not rise in microgravity. Trapped bubbles can block channels and disrupt flow. Microfluidic designs for space must incorporate degassing strategies, hydrophilic surface treatments, or active bubble removal.
- **Diffusion-dominated mixing**: Without convective mixing, molecular diffusion is the primary mixing mechanism. This makes laminar flow interfaces more stable and predictable, but necessitates active or passive micromixers for applications requiring rapid mixing.
- **Advantage for microfluidics**: Because microfluidic devices already operate at low Reynolds numbers where viscous forces dominate over inertial forces, they are inherently better suited to microgravity than macroscale systems. The physics governing flow at the microscale is largely unchanged by the removal of gravity, making microfluidics a natural technology platform for space.

### 1.2 Lab-on-Chip Experiments on the ISS

Multiple lab-on-chip systems have been developed, validated, and flown aboard the International Space Station:

**NASA/NIH Tissue Chips in Space Program**

The Tissue Chips in Space initiative, a collaboration between NASA, the NIH National Center for Advancing Translational Sciences (NCATS), and the ISS National Laboratory, represents the largest coordinated effort to deploy microfluidic organ-on-chip devices in orbit:

- **Phase 1 (2018-2022)**: Nine projects funded, each involving development, ground validation, and approximately month-long ISS experiments. Organ systems studied include heart, lung, kidney, bone marrow, musculoskeletal, and immune tissue.
- **Phase 2 (Tissue Chips in Space 2.0, 2025+)**: Six new grants awarded through cooperative agreements. Researchers design microphysiological systems mimicking complex organ systems, validated on Earth, then sent to the ISS National Laboratory to study microgravity effects on human physiology and age-associated conditions.

Key results from the program include:

| Tissue Type | Finding | Significance |
|-------------|---------|--------------|
| Heart | Impaired contractions, subcellular structural changes, increased stress markers | Model for cardiac atrophy and disease |
| Skeletal muscle | Downregulation of myoblast proliferation and differentiation transcripts | Explains muscle wasting in astronauts |
| Immune cells | Accelerated aging phenotype confirmed (STaARS BioScience-7) | Model for studying immune senescence |
| Muscle (older donors) | Unique downregulated metabolic gene pathways vs. younger donors | Age-dependent spaceflight response |

**Muscle Lab-on-Chip (2025)**

A study published in 2025 examined 3D-bioengineered myobundles from young and older adult donors under microgravity aboard the ISS. Global transcriptomic RNA-seq analyses revealed spaceflight-induced changes in muscle fiber type and metabolic gene expression, with older-donor myobundles showing distinct vulnerability pathways.

**Approximate 8 culturing LOC devices** were under development and testing on the ISS during the 2022-2025 period, investigating diverse cell and tissue behaviors in the space environment.

### 1.3 AcubeSAT: Student CubeSat with Microfluidics

AcubeSAT is a 3U+ CubeSat (340.5 x 100 x 100 mm plus tuna-can extension) developed by SpaceDot, a student team based primarily at the Aristotle University of Thessaloniki, Greece, under ESA's "Fly Your Satellite!" educational program.

**Mission objectives:**
- Evaluate combined effects of microgravity and cosmic radiation on gene expression in *Saccharomyces cerevisiae* (baker's yeast), a eukaryotic model organism
- Demonstrate Lab-on-a-Chip (LOC) functionality as modular devices for multi-parallel biotechnological experiments in orbit

**Technical approach:**
- Parallel microfluidic channels for simultaneous cultivation of multiple yeast cultures
- Integrated imaging system for high-quality visual observation of cell growth
- Automated fluidic control with onboard pumps and valves
- Environmental monitoring (temperature, humidity, pressure)
- Multi-month mission duration enabling extended experiments

**Scale of ambition**: The mission aims to study gene expression at 100-200x greater throughput than previous spaceflight biology missions. AcubeSAT passed its Critical Design Review and completed environmental testing at ESA's ESEC facility in 2024.

**Significance**: AcubeSAT demonstrates that microfluidic payloads can be miniaturized to fit within CubeSat form factors, dramatically reducing the cost of biological experiments in space and opening access to universities and smaller research groups.

### 1.4 NASA/ESA Microfluidics Programs

**NASA Programs:**
- **Tissue Chips in Space** (with NIH/NCATS): Flagship program for organ-on-chip in microgravity
- **3D Tissue Chips**: Investigation of 3D tissue constructs in the space environment
- **Atacama Rover Astrobiology Drilling Studies (ARADS)**: Testing microfluidic life-detection instruments in Mars-analog environments
- **SpaceX CRS resupply missions**: Regular transport of microfluidic payloads to ISS

**ESA Programs:**
- **Fly Your Satellite!**: Educational program supporting student CubeSats with microfluidic payloads (e.g., AcubeSAT)
- **SciSpacE**: Science in Space Environment program funding microfluidic experiments
- **Biolab on ISS Columbus module**: Facility supporting biological experiments including microfluidic-based studies

**Planned missions:**
- Satellite launch with microfluidic payload for *C. elegans* research in cis-lunar orbit (planned ~2025)
- Continued expansion of tissue chip experiments with more complex multi-organ systems

---

## 2. Extreme Environment Applications

### 2.1 Deep-Sea Sensors (Pressure-Tolerant Microfluidics)

Operating microfluidic devices at ocean depths requires addressing extreme hydrostatic pressures (up to 1,100 bar at the deepest trenches) and low temperatures (1-4 degrees C):

**Pressure compensation strategies:**
- Oil-filled, hydraulically pressure-compensated housings protect electronics while allowing microfluidic chips to operate at ambient deep-sea pressures
- Rigid chip materials (glass, silicon) tolerate high pressures better than PDMS, which compresses and deforms
- Channel geometries must account for pressure-dependent fluid viscosity changes

**High-pressure microfluidics research:**
- Devices operating at pressures up to 700 bar have been demonstrated for studying deep-sea microbial phenotyping
- High-pressure microfluidic systems enable investigation of microbiology under conditions mimicking the deep ocean, deep subsurface, and hydrothermal vents
- Parameters explored include extreme ranges of pressure, salinity, and temperature simultaneously

**Marine environmental monitoring applications:**
- Water quality analysis: dissolved oxygen, pH, nutrients (nitrate, phosphate, silicate)
- Pollutant detection: oil, heavy metals, persistent organic pollutants
- Emerging contaminant monitoring: microplastics, pharmaceuticals
- Climate research: ocean acidification, aerosol phase behavior, ice nucleating particles

**Heavy metal detection**: Microfluidic tools can measure heavy metals in seawater portably and efficiently, with sensitivity comparable to ICP-MS but at a fraction of the size and cost.

### 2.2 Arctic/Polar Field-Deployable Devices

Polar environments present unique challenges: extreme cold (-40 degrees C and below), limited power, remote locations, and harsh weather:

- **Cold-tolerant reagents**: Standard biochemical reagents freeze; formulations with cryoprotectants or lyophilized reagents activated by sample addition are necessary
- **Thermal management**: Integrated heaters maintain chip temperature; insulated enclosures reduce power draw
- **Rugged packaging**: Devices must withstand vibration from transport over rough terrain, ice, and snow
- **Applications**: Water quality monitoring in polar lakes and streams, ice core analysis, monitoring of permafrost melt chemistry, wildlife disease surveillance in remote Arctic communities

### 2.3 Desert and Hot Environment Operation

High temperatures (50 degrees C+), intense UV radiation, dust, and sand present distinct challenges:

- **Evaporation control**: Open or semi-open microfluidic devices lose sample rapidly; sealed systems with minimal dead volumes are essential
- **Thermal stability**: Reagent degradation accelerates at high temperatures; lyophilized or thermostable reagent formulations extend shelf life
- **Dust and sand protection**: IP-rated enclosures, filtered inlets, and self-sealing sample ports prevent particle intrusion
- **Solar power availability**: Hot, sunny environments are well-suited to solar-powered microfluidic systems

### 2.4 Radiation-Hardened Microfluidics

For nuclear facilities, space radiation environments, and post-disaster monitoring:

**Material considerations:**
- PDMS degrades under sustained radiation exposure; glass, silicon, and certain ceramics are more radiation-tolerant
- Polymer-based devices may yellow, embrittle, or change surface properties after exposure to ionizing radiation
- Metal and glass hybrid chips offer superior radiation resistance

**Nuclear environment applications:**
- Microfluidic electrochemical cells for in-situ analysis of radioactive materials, reducing radiation exposure to personnel through small sample volumes and high throughput
- Nanomaterial-based sensors (quantum dots, metal-organic frameworks, gold nanoparticles) integrated on microfluidic platforms for detecting radioactive ions in nuclear wastewater and seawater
- Radiation-resistant microsensors capable of surviving 1,832 degrees F and intense radiation inside advanced nuclear reactors

**Space radiation hardening:**
- Electronic components of microfluidic control systems require radiation hardening for deep-space missions
- Three main approaches: hardening by process (radiation-tolerant fabrication), by shielding (physical barriers), and by design (redundant circuits, error correction)
- Total ionizing dose and single-event effects can degrade sensor electronics; microfluidic chips themselves (being passive fluid circuits) are generally more radiation-tolerant than their control electronics

### 2.5 Deep Underground and Geological Environments

Microfluidic systems enable study of deep subsurface life and geology:

- Access to critical parameters of deep life at the microscale: high pressure, high temperature, low fluid volumes
- Study of microbial communities in deep rock formations, oil reservoirs, and geothermal systems
- Ecology-on-a-chip platforms study interactions between microbes and hydrocarbons (e.g., oil droplet interactions relevant to deep-sea oil spill response)

---

## 3. Planetary Science

### 3.1 Life Detection Instruments for Mars Missions

Microfluidics is central to next-generation astrobiology instruments designed to search for evidence of life on Mars and other solar system bodies:

**Microfluidics Life Analyzer (MILA)**
- Extracts organic molecules from soil samples, including amino acids that could indicate microbial life
- Developed as part of NASA's Atacama Rover Astrobiology Drilling Studies (ARADS)
- Tested in the hyper-arid core of the Atacama Desert, the closest Mars analog on Earth
- Designed for integration with rover-mounted drilling systems

**SOLID-LDChip (Signs of Life Detector - Life Detector Chip)**
- Antibody microarray-based biosensor instrument
- Contains up to 200 antibodies targeting molecular biomarkers associated with life
- Operated remotely and autonomously as part of a rover payload during ARADS field campaigns
- Demonstrated capability for in-situ detection of microbial biomarkers in subsurface samples retrieved by drilling
- Proven maturity as a tool for remote life detection on future solar system missions

**Miniaturized Capillary Electrophoresis**
- Microfluidic capillary electrophoresis devices detect amino acids, nucleobases, and other molecules critical to life
- Capable of chiral analysis (distinguishing left- and right-handed amino acids), a potential biosignature since terrestrial life preferentially uses L-amino acids
- Extremely low sample and reagent requirements suit the mass-constrained environment of planetary missions

### 3.2 Chemical Analysis of Extraterrestrial Samples

Beyond life detection, microfluidic instruments enable broad chemical characterization:

- **Mineral and elemental analysis**: Microfluidic sample preparation for spectroscopic analysis of rock and soil composition
- **Water chemistry**: If liquid water is found (subsurface brines, icy moon oceans), microfluidic analyzers can characterize pH, salinity, dissolved gases, and organic content
- **Sample return support**: Microfluidic pre-screening could prioritize which samples to cache for eventual return to Earth

### 3.3 Microfluidic Instruments on Space Probes

Relevant mission concepts and instruments:

| Mission/Concept | Target | Microfluidic Component | Status |
|----------------|--------|----------------------|--------|
| ARADS/MILA | Mars analog | Organic molecule extraction and analysis | Field tested |
| SOLID-LDChip | Mars analog | Antibody microarray biosensor | Field tested |
| Europa Clipper concepts | Europa | Potential ocean sample analysis | Conceptual |
| Enceladus Life Finder concepts | Enceladus | Plume sample analysis | Conceptual |
| ExoMars-related instruments | Mars | Biomarker detection | In development |

**Design constraints for planetary instruments:**
- Mass: typically < 5 kg for complete instrument
- Power: typically < 10 W average
- Volume: must fit within rover or lander instrument bays
- Temperature: survive -120 degrees C to +50 degrees C (Mars surface)
- Radiation: withstand galactic cosmic rays and solar particle events during transit
- Autonomy: must operate with minimal ground intervention due to communication delays (4-24 minutes one-way to Mars)
- Contamination control: planetary protection requirements demand extreme cleanliness

---

## 4. Military and Defense

### 4.1 Chemical/Biological Agent Detection

The defense sector has been a major driver of microfluidics development since the 1990s:

**Historical context:**
- DARPA funded early microfluidics research specifically to develop field-deployable devices for detecting chemical and biological warfare agents
- The concept of a "miniaturized total analysis system" (mu-TAS) emerged partly from defense needs for rapid, on-site analysis

**Current capabilities:**
- Detection of nerve agents (sarin, VX), blister agents (mustard gas), blood agents (cyanide), and choking agents (phosgene)
- Biological agent detection: anthrax spores, ricin, botulinum toxin, plague bacteria
- Multiplex detection of multiple agents simultaneously on a single chip
- Time to result: minutes rather than hours required by traditional methods

**Key systems:**
- **Aerosol Vapor Chemical Agent Detector (AVCAD)**: Next-generation detector that alerts warfighters to chemical agents. Man-portable, vehicle-mountable, or integrable into naval vessels. Detects, identifies, alarms, and reports threat vapors and aerosols.
- **Joint Biological Tactical Defense System (JBTDS)**: Lightweight, low-cost, man-portable biological warfare agent aerosol detection, collection, and identification system. Achieved Milestone C for production.

### 4.2 Field-Portable Diagnostic Devices

Military medical diagnostics in forward-deployed settings require devices that work without laboratory infrastructure:

- **Trauma diagnostics**: Rapid blood typing, coagulation assessment, hemoglobin measurement
- **Infectious disease screening**: Malaria, dengue, tuberculosis, COVID-19 in deployment zones
- **Toxicology**: Rapid identification of exposure to chemical agents or environmental toxins
- **Minimal training requirement**: Devices must be operable by personnel with limited medical training

### 4.3 DARPA Microfluidics Programs

**DIGET (Detect It with Gene Editing Technologies)**
- Develops massively multiplexed devices incorporating CRISPR-based gene editors into portable detectors
- Target: distributed health biosurveillance and rapid point-of-need diagnostics
- Capable of screening clinical or environmental samples for up to 1,000 nucleic acid targets
- Program goal: results in 15 minutes
- Led by teams including Draper and MRIGlobal

**ADEPT (Autonomous Diagnostics to Enable Prevention and Therapeutics)**
- Supports individual troop readiness and total force health protection
- Technologies for rapidly identifying and responding to natural and engineered disease threats
- Subset of technologies designed for use by personnel with minimal medical training
- Delivers centralized laboratory capabilities in low-resource military environments

**Biodefense programs (Draper)**
- Automated sample preparation with custom microfluidics and integrated optical systems
- Portable form factors for field biodetection
- Advanced biosurveillance technology to counter rapid pathogen spread

### 4.4 Dual-Use Concerns

A 2019 article in the U.S. Naval Institute *Proceedings* ("Microfluidics Should Scare You") highlighted concerns about the dual-use nature of microfluidic technology:
- The same miniaturization that enables defensive detection could enable offensive synthesis of harmful agents
- Microreactors could theoretically produce chemical or biological agents in distributed, hard-to-detect facilities
- This underscores the importance of export controls and monitoring of advanced microfluidic equipment

---

## 5. Remote and Resource-Limited Settings

### 5.1 Battery-Free Microfluidics

Eliminating the need for external power dramatically expands where microfluidics can be deployed:

**Passive flow mechanisms:**
- Capillary-driven flow: Wicking through paper or porous substrates (lateral flow assays are the simplest example)
- Gravity-driven flow: Pre-loaded reservoirs drain through channels without pumps
- Finger-powered actuation: Simple mechanical pressure replaces electronic pumps
- Vacuum-driven degassing: Pre-evacuated chambers draw fluid through channels

**Self-powered systems:**
- **SIMPLE chip (Self-powered Integrated Microfluidic Point-of-care Low-cost Enabling)**: Uses negative pressure from degassed PDMS to drive flow without any external equipment
- **Biofuel cell integration**: Sweat-based biofuel cells generate electricity from lactate in perspiration, powering sensor electronics
- **Salinity gradient power**: Reverse electrodialysis integrated on-chip uses salinity differences between sample and reference solutions to generate electricity, eliminating external electrodes and power sources

**Battery-free wearable platforms:**
- Skin-interfaced microfluidic/electronic systems for sweat analysis
- Simultaneously monitor sweat rate/loss, pH, lactate, glucose, and chloride
- Wireless data transmission via NFC (powered by smartphone reader)
- Significantly lighter, cheaper, and smaller than battery-powered alternatives

### 5.2 Solar-Powered Diagnostics

Solar energy integration with microfluidics enables operation in sunny, off-grid environments:

- **Solar thermal PCR**: Solar heating replaces electrical thermal cycling for nucleic acid amplification. Eliminates the largest power draw in molecular diagnostics.
- **Photovoltaic-powered pumps**: Small solar panels (< 1 W) can drive micropumps for continuous monitoring applications
- **Solar-charged battery systems**: Portable systems use solar chargers alongside battery packs and hand cranks for flexible power sourcing
- **Consistent performance**: Studies demonstrate consistent reaction yield and heater performance regardless of electrical power source (solar, battery, or hand crank)

### 5.3 Ruggedized Devices for Field Use

Transitioning microfluidics from controlled laboratory environments to field use requires systematic ruggedization:

**Mechanical robustness:**
- Rigid substrate materials (glass, COC, COP) instead of flexible PDMS
- Permanent bonding (thermal, adhesive, or laser welding) rather than reversible sealing
- Shock-absorbing enclosures rated to military drop-test standards (MIL-STD-810)
- Vibration resistance for transport by vehicle, helicopter, or drone

**Environmental protection:**
- IP67/IP68-rated enclosures for dust and water ingress protection
- Operating temperature ranges of -20 to +55 degrees C (extended military range)
- UV-resistant materials and coatings for outdoor deployment
- Humidity-sealed reagent storage with desiccant packs

**Reagent stability:**
- Lyophilized (freeze-dried) reagents with multi-year shelf life at ambient temperature
- Wax-sealed reagent reservoirs that release upon heating
- Pre-loaded, sealed cartridges for single-use operation
- Cold-chain-independent formulations for tropical and desert deployment

**Deployment platforms:**
- **Lab-on-a-drone**: Nucleic acid diagnostics deployed by drone to remote locations, with smartphone-based readout
- **Vehicle-integrated systems**: Ruggedized analyzers mounted in military vehicles, ambulances, or field stations
- **Backpack-portable kits**: Complete diagnostic systems weighing under 5 kg including power source, reader, and consumables

### 5.4 Minimal-Instrumentation Approaches

The ultimate goal for resource-limited settings is to minimize or eliminate the need for external instruments:

- **Colorimetric readout**: Results visible to the naked eye, no reader required
- **Smartphone-based detection**: Camera and flash serve as optical detector and light source
- **Paper-based microfluidics (mu-PADs)**: Extremely low cost (cents per device), disposable, no external equipment needed
- **Electrochemical detection with printed electrodes**: Screen-printed electrodes integrated directly on chip, read by simple handheld meters

---

## 6. Cross-Cutting Technical Challenges

### 6.1 Miniaturization vs. Capability Trade-offs

| Parameter | Laboratory System | Field-Portable | CubeSat/Probe |
|-----------|------------------|----------------|---------------|
| Mass | 10-50 kg | 1-10 kg | 0.1-5 kg |
| Power | 100-1000 W | 1-50 W | 0.1-10 W |
| Sample volume | 1-100 mL | 10-1000 uL | 1-100 uL |
| Reagent shelf life | Days-weeks (cold chain) | Months (ambient) | Years (lyophilized) |
| Autonomy | Operator-attended | Semi-autonomous | Fully autonomous |
| Data output | Full dataset | Targeted results | Compressed/prioritized |

### 6.2 Reliability Requirements

Space and defense applications demand reliability far beyond standard laboratory devices:

- **Space qualification**: Vibration testing (launch loads), thermal vacuum cycling, radiation exposure testing, outgassing verification
- **Military qualification**: MIL-STD-810 environmental testing, electromagnetic compatibility (MIL-STD-461), chemical/biological contamination survivability
- **Mean time between failures**: Space instruments target 10,000+ hours; military field devices target 1,000+ hours
- **Graceful degradation**: Systems must provide useful (if reduced) output even when individual components fail

### 6.3 Sample Handling in Extreme Environments

Acquiring and introducing samples into microfluidic devices is often the hardest problem:

- **Space**: Biological samples must be preserved during launch vibration and stored in microgravity; no manual pipetting possible for autonomous missions
- **Deep sea**: Samples must be captured at pressure without depressurization artifacts
- **Planetary surfaces**: Soil/rock must be drilled, crushed, sieved, and dissolved before introduction to microfluidic channels
- **Contamination**: Planetary protection (forward contamination of other worlds) and sample integrity (preventing Earth contamination of extraterrestrial samples) impose stringent requirements

---

## 7. Future Directions

### 7.1 Near-Term (2025-2030)

- Expanded Tissue Chips in Space 2.0 experiments with multi-organ systems on ISS
- AcubeSAT launch and demonstration of CubeSat-scale microfluidic biology
- Next-generation DARPA biosurveillance devices with 1,000+ target multiplexing
- Commercial deep-sea microfluidic monitoring systems for ocean observatories
- Solar-powered autonomous water quality monitors for remote environmental stations

### 7.2 Medium-Term (2030-2040)

- Microfluidic life-detection instruments on Mars sample return or next-generation rover missions
- Organ-on-chip systems for crew health monitoring on Artemis lunar missions and Gateway station
- Autonomous underwater microfluidic sensor networks for ocean climate monitoring
- Integration of AI/ML with field-portable microfluidic diagnostics for real-time decision support

### 7.3 Long-Term (2040+)

- Microfluidic analyzers on Europa or Enceladus ocean-world missions
- In-space pharmaceutical manufacturing using microfluidic reactors
- Closed-loop life support systems incorporating microfluidic water and air quality monitoring
- Fully autonomous microfluidic laboratories for permanent lunar or Mars bases

---

## 8. Key Organizations and Programs

| Organization | Program/Focus | Domain |
|-------------|--------------|--------|
| NASA | Tissue Chips in Space, ARADS | Space biology, astrobiology |
| NIH/NCATS | Tissue Chips in Space 2.0 | Microphysiological systems |
| ESA | Fly Your Satellite!, Biolab | Space biology, education |
| DARPA | DIGET, ADEPT | Biosurveillance, defense diagnostics |
| Draper | Biodefense, DIGET | Military biodetection |
| SpaceDot/AcubeSAT | CubeSat microfluidics | Student space biology |
| U.S. Army DEVCOM | AVCAD, JBTDS | Chemical/biological defense |
| MRIGlobal | DIGET | Pathogen detection |

---

## Sources

- [Lab-on-chip technologies for space research -- current trends and prospects (Springer)](https://link.springer.com/article/10.1007/s00604-023-06084-4)
- [Lab-on-a-Chip Technologies for Microgravity Simulation and Space Applications (MDPI)](https://www.mdpi.com/2072-666X/14/1/116)
- [Lab-on-chip technologies for space research (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC10721686/)
- [Microfluidic Actuated and Controlled Systems for Lab-on-Chip in Space Life Science](https://spj.science.org/doi/10.34133/space.0008)
- [Tissue Chips in Space 2.0 (NCATS)](https://ncats.nih.gov/news/news-and-events/tissue-chips-in-space-2.0-will-reveal-age-related-disease-mechanisms-and-possible-therapies)
- [Tissue Chips in Space: Modeling Human Diseases in Microgravity (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8294131/)
- [Tissue Chips Accurately Model Organs in Space (NASA)](https://www.nasa.gov/image-article/tissue-chips-accurately-model-organs-in-space/)
- [Human skeletal muscle tissue chip autonomous payload (Nature)](https://www.nature.com/articles/s41526-023-00322-y)
- [Microgravity accelerates skeletal muscle degeneration: ISS muscle lab-on-chip (PubMed)](https://pubmed.ncbi.nlm.nih.gov/40578352/)
- [AcubeSAT About Page](https://acubesat.spacedot.gr/about/)
- [ESA - Meet the team: AcubeSAT](https://www.esa.int/Education/CubeSats_-_Fly_Your_Satellite/Meet_the_team_AcubeSAT)
- [AcubeSAT successfully passes Critical Design Review (ESA)](https://www.esa.int/Education/CubeSats_-_Fly_Your_Satellite/AcubeSAT_successfully_passes_Critical_Design_Review)
- [AcubeSAT Environmental Test Campaign (ESA)](https://www.esa.int/Education/CubeSats_-_Fly_Your_Satellite/AcubeSAT_team_travel_to_ESA_ESEC_for_intense_Environmental_Test_Campaign)
- [Microfluidics for macrofluidics: marine-ecosystem challenges (RSC)](https://pubs.rsc.org/en/content/articlehtml/2024/lc/d4lc00468j)
- [Small chips, big ocean: microfluidic technology for marine monitoring (ScienceDirect)](https://www.sciencedirect.com/science/article/abs/pii/S2214158825000078)
- [High-Pressure Microfluidics for Ultra-Fast Microbial Phenotyping (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9168469/)
- [Microfluidics for studying the deep underground biosphere (Oxford Academic)](https://academic.oup.com/femsec/article/100/12/fiae151/7900670)
- [A Life-Detection Mini-lab - ARADS (NASA)](https://www.nasa.gov/image-article/life-detection-mini-lab-atacama-rover-astrobiology-drilling-studies/)
- [Life Detection with SOLID-LDChip during Mars Drilling Simulation (Astrobiology)](https://astrobiology.com/2023/11/life-detection-and-microbial-biomarker-profiling-with-signs-of-life-detector-life-detector-chip-during-a-mars-drilling-simulation-campaign-in-the-hyperarid-core-of-the-atacama-desert.html)
- [Role of microfluidics in accelerating new space missions (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9033306/)
- [Biosignature stability in space enables life detection on Mars (Science Advances)](https://www.science.org/doi/10.1126/sciadv.abn7412)
- [DARPA ADEPT Program](https://www.darpa.mil/research/programs/autonomous-diagnostics-to-enable-prevention-and-therapeutics)
- [Draper Biodefense](https://www.draper.com/market-areas/biotechnology-systems/biodefense)
- [Draper DIGET Biosurveillance for DARPA](https://www.draper.com/media-center/news-releases/detail/23205/draper-to-develop-biosurveillance-technology-for-darpa-to-counter-the-rapid-spread-of-pathogens)
- [Microfluidics Should Scare You (USNI Proceedings)](https://www.usni.org/magazines/proceedings/2019/june/microfluidics-should-scare-you)
- [U.S. Army Deployable Microsensors](https://www.army.mil/article/287324/deployable_microsensors)
- [U.S. Army Next-generation chemical detector AVCAD](https://www.army.mil/article/276958/next_generation_chemical_detector_to_provide_enhanced_cbrn_defense_to_warfighter)
- [Microfluidics-based strategies for molecular diagnostics of infectious diseases (Military Medical Research)](https://link.springer.com/article/10.1186/s40779-022-00374-3)
- [Battery-free, skin-interfaced microfluidic/electronic systems (Science Advances)](https://www.science.org/doi/10.1126/sciadv.aav3294)
- [SIMPLE chip: Self-powered Integrated Microfluidic Point-of-care (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5362183/)
- [Towards non- and minimally instrumented microfluidics-based diagnostic devices (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC2776042/)
- [Advancing radioactive material research with microfluidic electrochemical cell (Frontiers)](https://www.frontiersin.org/journals/nuclear-engineering/articles/10.3389/fnuen.2023.1206110/full)
- [Detection of radioactive ions: nanomaterial-based sensors (Springer)](https://link.springer.com/article/10.1007/s00604-025-07308-5)
- [Lab-on-a-Drone: Smartphone-Enabled Nucleic Acid Diagnostics (ACS)](https://pubs.acs.org/doi/10.1021/acs.analchem.5b04153)
