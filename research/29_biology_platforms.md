# Microfluidics for Biological Applications: Platforms, Tools, and Technologies

> Deep dive into the intersection of microfluidics and biology, covering organ-on-chip systems,
> single-cell analysis, flow cytometry on chip, cell culture platforms, and genomics tools.
> Last updated: March 2026.

---

## Table of Contents

1. [Organ-on-Chip Commercial Platforms](#1-organ-on-chip-commercial-platforms)
2. [Single-Cell Analysis Platforms](#2-single-cell-analysis-platforms)
3. [Flow Cytometry on Chip](#3-flow-cytometry-on-chip)
4. [Cell Culture on Chip](#4-cell-culture-on-chip)
5. [Microfluidics for Genomics](#5-microfluidics-for-genomics)

---

## 1. Organ-on-Chip Commercial Platforms

### Market Overview

The organ-on-a-chip (OoC) market has seen explosive growth, driven by FDA regulatory support
(the FDA Modernization Act 2.0, signed 2022, removed the animal-testing mandate for drug
approval), pharma adoption, and increasing platform maturity.

- **2025 market size**: ~$230--390 million (estimates vary by source)
- **2026 projected**: ~$310--510 million
- **2031--2035 forecast**: $1.8--3.4 billion
- **CAGR**: 29--35% (2025--2034)
- **Dominant end users**: Pharmaceutical and biotech companies (59% of 2025 revenue)
- **Leading organ types**: Lung chips (~34% share), liver chips (~33%), with heart chips as
  the fastest-growing segment (~32% CAGR)
- **Geographic leadership**: North America (42% revenue), Asia-Pacific fastest growth (~34% CAGR)

### 1.1 Emulate -- Human Emulation System

**Website**: [emulatebio.com](https://emulatebio.com)

Emulate, spun out of the Wyss Institute at Harvard, is the most recognized name in the OoC
space. The company partners with top pharma (Johnson & Johnson, Pfizer, Roche) and has
piloted chips with the FDA.

**Platform Components**:
- **Zoe Culture Module**: Hardware that provides controlled perfusion, mechanical stretch,
  and environmental control for organ-chips
- **Organ-Chips**: Flexible polymer chips (~AA battery size) with two parallel microfluidic
  channels separated by a porous membrane; one channel for tissue cells, one for vascular
  endothelium; channels support fluid flow and mechanical stretching (breathing, peristalsis)
- **Pod Portable Module**: Single-use fluidic interface connecting chips to the Zoe module
- **Analysis Software**: Integrated imaging and data analysis applications

**Available Organ Models**:
| Organ-Chip       | Key Application                                  |
|-------------------|--------------------------------------------------|
| Lung-Chip         | Inhalation toxicity, respiratory disease, COPD   |
| Liver-Chip        | Drug metabolism, DILI prediction, hepatotoxicity  |
| Duodenum Intestine-Chip | Drug absorption, gut inflammation           |
| Colon Intestine-Chip    | IBD modeling, microbiome studies             |
| Kidney-Chip       | Nephrotoxicity, drug clearance                   |
| Brain-Chip        | Blood-brain barrier, neuroinflammation            |

**Pricing**: Not publicly listed; estimated ~$1,000--2,000 per chip, ~$150k--250k for full
system (Zoe module + software). Emulate targets service-based and collaborative models with
pharma partners. An internal analysis showed that use of Liver-Chip in drug development could
provide the equivalent of $3 billion in improved R&D productivity.

**Status (2025--2026)**: Active commercial sales; FDA pilot programs; strong pharma partnerships.
Raised $82M Series E (2021) for expansion. Market leader alongside Mimetas.

---

### 1.2 TissUse -- HUMIMIC Platform

**Website**: [tissuse.com](https://www.tissuse.com)

TissUse (Berlin, Germany) specializes in multi-organ integration -- connecting multiple human
tissues on a single microfluidic circuit to model systemic interactions, ADME behavior, and
complex disease mechanisms. Their HUMIMIC platform is PBPK-compliant (physiologically-based
pharmacokinetic), enabling quantitative in vitro to in vivo extrapolation (IVIVE).

**Chip Variants**:

| Chip Model       | Organ Compartments | Microfluidic Volume | Surface Area       | Cell Culture Inserts           |
|-------------------|--------------------|---------------------|--------------------|-------------------------------|
| HUMIMIC Chip2     | 2 organs           | 5 uL                | 115 mm^2           | 1x 96-well CCI                |
| HUMIMIC Chip3     | 3 organs           | 10 uL               | 235 mm^2           | 2x 96-well + 1x 24-well CCI   |
| HUMIMIC Chip3plus | 3 organs (larger)  | 11 uL               | 255 mm^2           | 2x 24-well + 1x 96-well CCI   |
| HUMIMIC Chip4     | 4--5 organs        | 82 uL total         | 705 mm^2 total     | Separate blood + urine circuits|

**HUMIMIC Chip4 Details**: Enables integration of up to four organ models (e.g., intestine +
liver + kidney + neuronal tissue) with separate blood circuit (32.5 uL) and urine circuit
(49.5 uL). Blood circuit surface: 465 mm^2; urine circuit surface: 240 mm^2.

**HUMIMIC AutoLab (2025)**: Compact automated platform capable of operating up to 24
multi-organ chips in parallel. Automates media perfusion, dosing protocols, and environmental
control. Includes integrated bright-field and fluorescence microscopy for real-time imaging and
data acquisition.

**Key Differentiators**:
- True multi-organ crosstalk via on-chip microfluidic channels simulating systemic circulation
- Long-term dynamic co-culture capability (weeks)
- PBPK-compliant design for pharmacokinetic studies
- Automated parallel operation (AutoLab)

---

### 1.3 CN Bio Innovations -- PhysioMimix

**Website**: [cn-bio.com](https://cn-bio.com)

CN Bio (Cambridge, UK) is the other top-tier OoC company alongside Emulate. They are
especially strong in liver-focused and multi-organ microphysiological systems (MPS).

**PhysioMimix Core System**:
- Only MPS platform delivering validated performance across single-organ, multi-organ, and
  higher-throughput configurations
- Each controller runs up to 6 multi-chip plates simultaneously
- Plates made from inert cyclic olefin copolymer (COC), minimizing non-specific drug binding

**Multi-Chip Plate Configurations**:

| Plate Type            | Wells/Chips per Plate | Key Application                      |
|-----------------------|----------------------|---------------------------------------|
| Liver-12              | 12 chips             | Hepatotoxicity, DILI, drug metabolism |
| Liver-48              | 48 chips             | Higher-throughput liver studies        |
| Barrier Plate         | 12 chips             | Barrier tissue models (gut, lung)     |
| Dual-Organ Plate      | 6 systems            | Two-organ crosstalk (e.g., gut-liver) |

**Liver-on-Chip Details**: Each well contains an enclosed recirculating perfusion system with
a collagen-coated scaffold containing microchannels/pores. Primary hepatocytes and
non-parenchymal cells form liver microtissues maintained for at least 4 weeks. Sampling volume
up to 1 mL per chip supports omics and microscopy endpoints.

**Multi-Organ Models**: Dual-organ plates enable two individually cultured organs (e.g., lung
and liver) communicating via inter-organ fluidic flow for drug safety, efficacy, and metabolism
prediction.

**2025 Milestone**: Distribution agreement with Primetech (Japan) for PhysioMimix OOC Systems
market expansion in the region (January 2025).

---

### 1.4 Mimetas -- OrganoPlate

**Website**: [mimetas.com](https://www.mimetas.com)

Mimetas (Leiden, Netherlands) differentiates with high-throughput, plate-based organ-on-chip
technology designed for drug discovery screening workflows.

**OrganoPlate Platform**:
- Standard SBS 384-well plate footprint (127.76 x 85.48 x 14.8 mm)
- Integrates 40--96 microfluidic chips per plate
- Patented PhaseGuide technology for membrane-free patterning of extracellular matrix gels
- Gravity-driven perfusion (no external pumps required -- just a rocker)

**Plate Variants**:

| Variant              | Chips/Plate | Lanes | Configuration                |
|----------------------|-------------|-------|------------------------------|
| OrganoPlate 2-lane 96| 96          | 2     | Gel + perfusion channel       |
| OrganoPlate 3-lane 40| 40          | 3     | Gel + 2 perfusion channels    |

**Optical Quality**: 150 +/- 5 um glass bottom (#1 coverslip thickness); inter-chip flatness
within 120 um, intra-chip flatness within 5 um -- optimized for high-content imaging.

**Compatible Readouts**:
- Live and fixed cell imaging (confocal compatible)
- Barrier function (TEER) with integrated impedance electrodes
- Off-plate assays: ELISA, qPCR
- Temporal sampling of perfusate

**Key Differentiator**: The only OoC platform designed for 96-well-scale throughput, making it
uniquely suited for compound screening in drug discovery. No external pumps or tubing needed.

---

### 1.5 AlveoliX -- Lung-on-Chip

**Website**: [alveolix.com](https://alveolix.com)

AlveoliX (Bern, Switzerland) focuses exclusively on lung-on-chip models with a unique emphasis
on mechanical breathing motion.

**Technology**: Specialized instruments impose rhythmic three-dimensional stretching forces on
recreated alveolar barriers, mimicking the cyclic strain of breathing. This is critical because
lung tissue behavior (drug absorption, inflammatory response) is profoundly affected by
mechanical forces.

**2025 Breakthrough**: Researchers at the Francis Crick Institute and AlveoliX developed the
first human lung-on-chip using iPSC-derived cells from a single donor, enabling genetically
matched studies. This model simulates breathing motions and lung disease in a patient-specific
manner, with applications in tuberculosis research and personalized medicine.

**Applications**: Respiratory drug testing, inhalation toxicity, COPD modeling, TB research,
air-liquid interface studies.

---

### 1.6 BiomimX -- uBeat

**Website**: [biomimx.com](https://biomimx.com)

BiomimX (Milan, Italy, founded 2017) focuses on contractile tissue modeling.

**uBeat Stretch Platform**: Provides physiological uniaxial strain of 10% to 3D microtissues,
mimicking the stretching stimuli experienced by tissues in vivo.

**Applications**: Cardiovascular and musculoskeletal drug development. The platform is
particularly suited for modeling cardiac tissue contraction, skeletal muscle mechanics, and
vascular wall dynamics.

---

### 1.7 Cherry Biotech -- Temperature Control for OoC

**Website**: [cherrybiotech.com](https://www.cherrybiotech.com)

Cherry Biotech (Rennes, France) provides enabling technology for organ-on-chip and organoid
research, focusing on precise temperature control and 3D cell culture.

**CherryTemp System**:
- Two independent Peltier channels for precise temperature control
- Range: 5 degC to 45 degC
- Ultra-fast temperature shifts: <10 seconds
- Microfluidic chip-based heat exchange near the sample
- Feedback loop compensates for room temperature and objective lens heat sinking
- Originally developed for live-cell imaging; now extended to OoC applications

**CubiX Platform**: Cherry Biotech's organ-on-chip technology platform for multi-analyte
monitoring and drug testing in 3D tissue models.

**Applications**: Temperature-controlled OoC experiments, phase separation studies, live-cell
imaging, organoid culture.

---

### 1.8 Organ-on-Chip Platform Comparison Table

| Company      | Platform          | Organ Focus              | Throughput         | Perfusion      | Multi-Organ | Key Differentiator                    |
|--------------|-------------------|--------------------------|--------------------|----------------|-------------|----------------------------------------|
| Emulate      | Human Emulation   | Lung, liver, gut, kidney, brain | Low-med (per chip) | Pump-driven | Limited     | FDA partnerships, mechanical stretch   |
| TissUse      | HUMIMIC           | Multi-organ (2--5)       | 24 chips (AutoLab) | On-chip pump   | Yes (core)  | PBPK-compliant, multi-organ crosstalk  |
| CN Bio       | PhysioMimix       | Liver (primary), multi   | 6--48 per plate    | Recirculating  | Yes (dual)  | COC material, long-term liver culture  |
| Mimetas      | OrganoPlate       | Tubular tissues, barriers| 40--96 per plate   | Gravity/rocker | No          | 96-well throughput, no pumps needed    |
| AlveoliX     | AX Lung-on-Chip   | Lung (alveolar)          | Low-med            | Perfused       | No          | 3D breathing motion, iPSC compatible   |
| BiomimX      | uBeat             | Heart, muscle, vascular  | Low-med            | Perfused       | No          | Uniaxial stretch for contractile tissue|
| Cherry Biotech| CubiX / CherryTemp| Temperature-sensitive    | Low                | Integrated     | No          | Ultra-fast temperature control (<10s)  |

---

## 2. Single-Cell Analysis Platforms

### Market Context

Single-cell analysis has become foundational in biology, enabling researchers to resolve
cellular heterogeneity invisible to bulk assays. Microfluidics is the enabling technology
for most commercial single-cell platforms.

### 2.1 10x Genomics -- Chromium Platform

**Website**: [10xgenomics.com](https://www.10xgenomics.com)

10x Genomics dominates the single-cell market with its Chromium platform, which uses
microfluidic partitioning to capture individual cells in Gel Beads-in-Emulsion (GEMs).

**Instrument Lineup**:

| Instrument       | Price (approx.) | Throughput                    | Key Feature                  |
|------------------|-----------------|-------------------------------|------------------------------|
| Chromium X       | ~$60,000        | 1--128 samples, up to 2.56M cells/run | High-throughput, 8-channel chip |
| Chromium Xo      | ~$25,000        | Same chip compatibility       | Low-cost entry point          |
| Chromium iX      | ~$75,000+       | Highest throughput            | Automated, connected workflow |

**How It Works**:
1. Cells flow through microfluidic channels at limiting dilution
2. Each cell is captured in a nanoliter-scale GEM with a gel bead carrying unique barcodes
3. Within each GEM, the cell is lysed and target molecules (mRNA, DNA, protein tags) are
   captured and barcoded
4. GEMs are broken, and barcoded cDNA/DNA is pooled for library preparation
5. Sequencing on Illumina instruments; computational demultiplexing assigns reads to cells

**Performance**:
- Up to 20,000 cells per sample (standard); up to 80,000+ with GEM-X Flex
- Cell capture efficiency: ~65--80%
- GEM generation: 10,000+ GEMs in ~4 minutes per channel
- 8 channels per chip (parallel processing)
- GEM-X technology reduces sequencing costs by >50% compared to earlier versions

**Assay Portfolio**:
- Single Cell Gene Expression (3' and 5' RNA-seq)
- Single Cell Immune Profiling (V(D)J + gene expression)
- Single Cell ATAC-seq (chromatin accessibility)
- Single Cell Multiome (ATAC + gene expression from same cell)
- Single Cell CNV (copy number variation)
- Feature Barcoding (CITE-seq compatible, cell surface proteins)
- Visium Spatial (tissue-level spatial transcriptomics, though not single-cell microfluidics)

**Cost Per Run**: ~$2,000--5,000 per sample (reagents + consumables), excluding sequencing.
10x targets ~$100/sample with GEM-X assays at scale.

---

### 2.2 Standard BioTools (formerly Fluidigm) -- C1 System

**Website**: [standardbio.com](https://www.standardbio.com)

The C1 system was the first commercially available platform for automated single-cell isolation
and processing, using valve-based microfluidics (integrated fluidic circuits, IFCs).

**How It Works**:
- Proprietary microfluidic chips (IFCs) with integrated valves and chambers
- Cells flow through the chip; pneumatic valves isolate individual cells into separate chambers
- On-chip lysis, reverse transcription, and pre-amplification
- Processes 96 individual cells per IFC in <24 hours

**Capabilities**:
- Targeted gene expression profiling
- Full-length mRNA sequencing (Smart-seq2 compatible)
- miRNA expression profiling
- Targeted DNA sequencing and whole exome sequencing
- Multi-omic applications: C1 REAP-seq (simultaneous analysis of up to 82 proteins + 20,000
  genes per cell)
- Single-cell epigenetics (ATAC-seq, bisulfite sequencing)

**Strengths**: Full-length transcript coverage (vs. 10x's 3'/5' end counting); visual
confirmation of single-cell capture; wide application menu.

**Limitations**: Lower throughput (96 cells) vs. 10x (thousands--tens of thousands); higher
per-cell cost; cell size restrictions per IFC type.

**Status**: Standard BioTools continues to support the C1 but has shifted emphasis to its
mass cytometry (CyTOF) and other platforms. The C1 remains valuable for applications requiring
full-length transcripts or low cell numbers.

---

### 2.3 Bio-Rad -- ddSEQ Single-Cell Isolator

**Website**: [bio-rad.com](https://www.bio-rad.com)

Bio-Rad's ddSEQ uses droplet-based microfluidics (similar concept to 10x Genomics) for
single-cell gene expression and chromatin accessibility studies.

**Technical Specifications**:
- Disposable microfluidic cartridges co-encapsulate single cells/nuclei with barcoded beads
  into sub-nanoliter droplets
- Throughput: Hundreds to tens of thousands of cells per experiment
- Dimensions: 15.0" x 11.0" x 5.0" (compact benchtop)
- Weight: 4.9 kg

**Applications**:
- Single Cell 3' RNA-Seq (with ddSEQ RNA-Seq Kit)
- Single Cell ATAC-Seq (chromatin accessibility)
- Analysis via Bio-Rad Omnition Analysis Software

**Positioning**: Lower-cost alternative to 10x Genomics for labs with existing Bio-Rad
infrastructure. Less dominant market share but competitive on price.

---

### 2.4 Mission Bio -- Tapestri Platform

**Website**: [missionbio.com](https://missionbio.com)

Mission Bio's Tapestri is the only single-cell platform providing simultaneous DNA mutation
and protein analysis from the same cells -- a critical capability for cancer research and
cell therapy characterization.

**How It Works**:
1. **Step 1**: Two-step microfluidic process isolates DNA and oligo-conjugated antibodies
   from single cells in individual droplets
2. **Step 2**: Targeted multiplex PCR amplification within droplets
3. Sequencing on Illumina instruments; single-cell genotype + protein co-analysis

**What It Measures (simultaneously from each cell)**:
- Single nucleotide variants (SNV)
- Insertions and deletions (INDEL)
- Focal and genome-wide copy number variants (CNV)
- Loss of heterozygosity (LOH)
- Translocations
- Surface protein expression (via antibody-oligo conjugates)

**Key Applications**:
- Clonal architecture analysis in hematologic malignancies (AML, MPN, MDS)
- Cell therapy characterization (CAR-T editing verification)
- Minimal residual disease (MRD) monitoring
- Biomarker discovery

**2025 Highlight**: Tapestri supported exploratory biomarker analysis for Incyte's INCA033989
clinical trial for myeloproliferative neoplasms (MPNs), with data presented at ASH 2025.
The platform has also been adapted for single-cell RNA-seq through the SDR-Seq method.

---

### 2.5 Single-Cell Platform Comparison

| Platform           | Technology      | Throughput/Run    | Key Modality         | Per-Cell Cost | Instrument Cost |
|--------------------|-----------------|-------------------|----------------------|---------------|-----------------|
| 10x Chromium X     | Droplet (GEM)   | 500--80,000+      | RNA, ATAC, protein tags | ~$0.10--0.50 | ~$60k           |
| 10x Chromium Xo    | Droplet (GEM)   | 500--80,000+      | Same as X            | ~$0.10--0.50 | ~$25k           |
| Standard Bio C1    | Valve-based IFC | 96 cells          | Full-length RNA, DNA | ~$10--50      | ~$100--150k     |
| Bio-Rad ddSEQ      | Droplet         | 100s--10,000s     | RNA, ATAC            | ~$0.50--2.00  | ~$30--40k       |
| Mission Bio Tapestri| Droplet (2-step)| 1,000s--10,000s  | DNA + protein        | ~$1--5        | ~$75--125k      |

*Per-cell costs are approximate and exclude sequencing.*

---

## 3. Flow Cytometry on Chip

### 3.1 Overview: On-Chip FACS Alternatives

Traditional fluorescence-activated cell sorting (FACS) instruments are expensive ($150k--500k+),
large, and require trained operators. Microfluidic alternatives promise smaller footprint,
lower cost, gentler handling, and novel sorting modalities.

### 3.2 Acoustic Cell Sorting -- AcouSort

**Website**: [acousort.com](https://acousort.com)

AcouSort (Lund, Sweden) commercializes acoustofluidic technology -- combining ultrasonic
standing waves with microfluidics for label-free, contact-free cell/particle manipulation.

**How It Works**:
- Acoustic standing waves in a microfluidic channel push cells/particles to pressure nodes
  or antinodes based on their size, density, and compressibility
- Cells can be fractionated, enriched, washed, or transferred between fluid streams without
  physical contact

**Applications**:
- Blood cell fractionation (separating platelets, RBCs, WBCs)
- Extracellular vesicle isolation
- Cell washing (removing contaminants without centrifugation)
- In-line quality control for bioreactor and cell therapy production
- Integration with downstream flow cytometers

**2025 Status**: FDA approval for first OEM commercialization in critical care diagnostics.
Expanding commercial presence in North America, Europe, and Asia. AcouSort's technology is
designed for seamless in-line integration with existing instruments.

**Key Advantage**: Gentle, label-free sorting preserves cell viability and phenotype. No
fluorescent labeling required for size/density-based separation.

---

### 3.3 Fluorescence-Activated Droplet Sorting (FADS)

FADS is the droplet-microfluidics analog of traditional FACS: individual cells are
encapsulated in droplets, incubated (allowing enzymatic reactions, secretion, etc.), then
sorted based on fluorescence.

**How It Works**:
1. Single cells are encapsulated in picoliter--nanoliter aqueous droplets in oil
2. Droplets are incubated (on or off chip) to allow biological reactions
3. Droplets flow past a fluorescence detector
4. Dielectrophoretic (DEP) or acoustic actuators deflect target droplets into a collection
   channel

**Performance**:
- Sorting rates: 2--3 kHz (2,000--3,000 droplets/second) for standard FADS
- Ultra-high-throughput variants reaching 10+ kHz
- >99% sorting accuracy demonstrated in multi-path sorting systems

**Commercial Systems**:
- **CytoSpark** (Zhejiang Dapu Biotechnology): Commercial FADS platform
- Most FADS systems remain in academic/custom-built territory, but commercialization is
  accelerating

**Applications**:
- Directed evolution (screening enzyme variant libraries)
- Antibody discovery (screening single B-cell secretions)
- Drug screening at single-cell level
- Metabolite detection
- Small-molecule and protein analysis

---

### 3.4 Integrated Photonic Flow Cytometry

On-chip flow cytometers integrating photonic waveguides with microfluidic channels are
emerging as compact, multichannel alternatives.

**Recent Advances (2024--2025)**:
- Monolithically integrated photonics and fluidics on a single chip: both cell illumination
  and scattered light collection via photonic integrated circuits
- Detection of human leukocytes demonstrated with integrated photonic cytometers
- Cost-effective systems using photon incremental counting for fluorescence detection (1/50th
  the data of traditional methods)

**2026 Development**: Diaphragm-actuated sorting systems using elastomeric or piezoelectric
membranes for rapid, reversible, biocompatible sorting in response to upstream detection events.
Ideal for high-throughput cytometry.

---

### 3.5 In-Air Microfluidic Sorting (2025)

A novel approach where droplets containing single cells are ejected into air, interrogated
in-flight, and sorted by a microfluidic DEP sorter with a cylindrical electrode:
- Sorting accuracy: >99% across all sorting paths
- High cell survival rates
- Enables isolation of multiple subpopulations simultaneously
- Demonstrated with three cell-type mixtures

---

## 4. Cell Culture on Chip

### 4.1 Perfusion Systems

Microfluidic perfusion provides continuous nutrient/waste exchange, mimicking in vivo
conditions far better than static culture.

**Commercial Perfusion Platforms**:

| Platform                 | Company     | Key Features                                            |
|--------------------------|-------------|--------------------------------------------------------|
| Be-Flow                  | Beonchip    | Two independent channels, 2D/3D culture, rocker-compatible, Fluigent-compatible |
| PhysioMimix              | CN Bio      | Recirculating perfusion, COC plates, 4+ week culture    |
| OrganoPlate              | Mimetas     | Gravity-driven perfusion via rocking, 96-chip/plate     |
| ibidi Lab-on-Chip        | ibidi       | Commercial perfusion slides for long-term culture       |
| HUMIMIC                  | TissUse     | On-chip micropump, multi-organ perfusion                |

**Dissociable Perfusion Chip (DPC, 2026)**: A new chip design enabling parallel culture and
drug perturbation of five thick tissue slices (e.g., human glioblastoma resections). Uses
mechanical clamping for positive-pressure perfusion of 3D slices with nondisruptive dissociation.

---

### 4.2 3D Cell Culture in Microfluidics

Microfluidic platforms enable 3D culture architectures that are impossible in standard plates:

**Approaches**:
- **Hydrogel patterning**: PhaseGuide technology (Mimetas) patterns ECM gels in channels
  without physical barriers, creating tubular structures
- **Scaffold-based**: CN Bio's collagen-coated scaffolds with microchannels for liver
  microtissue formation
- **Droplet encapsulation**: Cells encapsulated in hydrogel microspheres within microfluidic
  channels for long-term 3D culture and analysis
- **Organoid integration**: Organ-on-chip platforms increasingly accommodate pre-formed
  organoids (e.g., Cherry Biotech CubiX, Emulate Brain-Chip)
- **Tissue slice culture**: Perfused culture of primary tissue explants (DPC chip)

**Automated Long-Term Culture**: Systems combining microfluidic perfusion with deep
learning-based image analysis enable automated T-cell proliferation tracking and cell behavior
monitoring over days to weeks.

---

### 4.3 Gradient Generators for Chemotaxis

Microfluidic gradient generators create controlled, stable chemical concentration gradients
for studying cell migration, differentiation, and signaling.

**Design Architectures**:

| Type                     | Principle                           | Pros                        | Cons                      |
|--------------------------|-------------------------------------|-----------------------------|---------------------------|
| Christmas-tree (Y-mixer) | Serial splitting and mixing         | Uniform flow, predictable   | Large footprint           |
| Diffusion-based          | Hydrogel barrier between source/sink| Shear-free, continuous      | Slow establishment        |
| Flow-based               | Laminar flow of different concentrations | Fast, tunable           | Shear stress on cells     |
| Static pressure-driven   | Gravity-driven reservoirs           | No pumps, long-term stable  | Limited dynamic range     |

**Commercial Product**: Fluigent **Be-Gradient** -- automated and integrated system creating
chemical gradients in organ-on-chip studies with simultaneous shear stress, flow rate, and
pressure control. Two channels flank a central cell culture chamber; varying concentrations
between channels establishes the gradient.

**2025 Advance**: Deep learning-based quantitative analysis of cell chemotaxis in microfluidic
chips, enabling automated tracking and response quantification.

---

### 4.4 Shear Stress Control

Controlling fluid shear stress is critical for:
- Endothelial cell studies (vascular biology)
- Mechanotransduction research
- Drug transport modeling
- Blood cell behavior

**Approaches**:
- **Parallel plate flow chambers**: Constant, calculable wall shear stress
- **Tapered channels**: Create a gradient of shear stress along the channel length
- **Shear-free systems**: Hydrogel-barrier gradient generators eliminate convective flow over
  cells while maintaining chemical gradients
- **Programmable perfusion**: Fluigent and similar pump systems allow real-time modulation of
  flow rates to simulate pulsatile (arterial) or steady (venous) flow

**Key Specification**: Physiological arterial shear stress is ~1--7 Pa (10--70 dyn/cm^2);
venous shear is ~0.1--0.6 Pa. Microfluidic systems can reproduce the full physiological range
with high precision.

---

## 5. Microfluidics for Genomics

### 5.1 Digital PCR Platforms

Digital PCR (dPCR) partitions a sample into thousands--millions of individual reactions,
enabling absolute quantification of nucleic acid targets without standard curves.

#### Bio-Rad Droplet Digital PCR (ddPCR)

Bio-Rad dominates the dPCR market and expanded significantly in 2025 through the acquisition
of Stilla Technologies and launch of new platforms.

**Current Product Portfolio**:

| System          | Multiplexing    | Throughput    | Partitioning Method       | Key Feature                |
|-----------------|-----------------|---------------|---------------------------|----------------------------|
| QX200           | 2-color         | 96 wells/run  | Oil-water emulsion droplets| Workhorse, widely adopted  |
| QX600           | 6-color         | 96 wells/run  | Oil-water emulsion droplets| 12 targets/well, launched 2024 |
| QX Continuum    | Multi-color     | 96 wells/run  | Droplet                   | New (2025 launch)          |
| QX700 series    | Multi-color     | Scalable      | Stilla-derived technology | Acquired via Stilla (2025) |

**QX600 Details**: 6-color detection quantifies up to 12 targets per well. Simple user
workflow with powerful data analysis. Advancing measurable residual disease (MRD) research
in oncology.

#### Stilla Technologies -- naica System (now Bio-Rad)

Bio-Rad acquired Stilla Technologies in 2025, integrating their microfluidic chip-based
dPCR technology.

**naica Platform**:
- **Partitioning**: Oil-water emulsion generates a 2D monolayer of droplet crystals on a
  microfluidic chip (Sapphire chip for high sensitivity, Opal chip for higher throughput)
- **Workflow**: Sample loaded into chip -> partitioned in Geode instrument -> PCR thermal
  cycling -> imaging in Prism6 (6-channel fluorescence)
- **Multiplexing**: 6 fluorescent channels
- **Key Advantage**: 2D droplet crystal array enables visual inspection and imaging-based
  readout (vs. flow-through counting in Bio-Rad QX systems)

**Combined Portfolio**: With the acquisition, Bio-Rad now offers the most comprehensive
digital PCR product line with >400,000 validated assays.

#### QIAGEN -- QIAcuity

- **Partitioning**: Nanoplate-based microfluidics without oil-water emulsion
- **Multiplexing**: Up to 5-color
- **Throughput**: 8, 16, or 96 partitions per plate
- **Key Advantage**: Integrated system (partition + PCR + read in one instrument); no oil
  or droplet generation step

---

### 5.2 Library Preparation on Chip

Microfluidic library preparation for next-generation sequencing (NGS) reduces reagent
consumption, minimizes hands-on time, and enables work with ultra-low DNA input.

**Platforms and Approaches**:

| Platform/System        | Type                  | Key Capability                          |
|------------------------|-----------------------|-----------------------------------------|
| Oxford Nanopore VolTRAX| Electrowetting (DMF)  | Automated sample prep for nanopore seq  |
| Vivalytic (Bosch)      | Lab-on-chip           | PCR enrichment, end-repair, ligation    |
| Droplet-based systems  | Academic/custom       | 10x reagent reduction, 10 pg input      |
| Standard BioTools IFCs | Valve-based           | Integrated with C1 single-cell workflow |

**Benefits of Microfluidic Library Prep**:
- Reagent consumption reduced by 10x or more
- DNA input as low as 10 pg per library (vs. 1--100 ng for standard protocols)
- Reduced pipetting steps and contamination risk
- Higher reproducibility through automation

**VolTRAX**: Oxford Nanopore's electrowetting-based digital microfluidic (DMF) device is
currently the only commercially available automated library preparation system using
electrowetting. Samples are manipulated as discrete droplets on a programmable electrode array.

---

### 5.3 Isothermal Amplification on Chip

Isothermal amplification methods (LAMP, RPA) eliminate the need for thermal cycling, enabling
simpler, cheaper, and more portable nucleic acid detection.

**Key Methods**:

| Method | Full Name                              | Temperature | Time     | Sensitivity        |
|--------|----------------------------------------|-------------|----------|--------------------|
| LAMP   | Loop-mediated isothermal amplification | 60--65 degC | 30--60 min| ~10 copies/rxn    |
| RPA    | Recombinase polymerase amplification   | 37--42 degC | 10--20 min| ~10 copies/rxn    |

**Microfluidic Implementations**:

- **VirChip (2025)**: Autonomously loaded chip for multiplexed detection of SARS-CoV-2,
  influenza A/B, and RSV. Crude nasal swab samples applied directly; no RNA isolation needed.
  LOD: 100 RNA copies/reaction.

- **Two-stage RPA+LAMP chip**: First-stage RPA amplification followed by fluorescence LAMP on
  a portable microfluidic system. Parallel multiplex detection in ~1 hour. LOD: ~10 copies.
  Clinical testing: 100% specificity/sensitivity for measles; 94--96% for SARS-CoV-2.

- **Centrifugal microfluidic LAMP**: CapitalBio Technology (China) developed centrifugal
  chips detecting 19 respiratory pathogens. Approved by Chinese NMPA for clinical use.

- **Digital LAMP**: Real-time digital isothermal amplification on commercial microfluidic
  chips (e.g., Stilla naica Sapphire chips) for absolute quantification.

---

### 5.4 CRISPR-Based Diagnostics on Chip

CRISPR-Cas systems have been repurposed as highly specific nucleic acid detection tools,
and microfluidic integration enables point-of-care deployment.

**Major Platforms**:

| Platform   | CRISPR Enzyme | Target  | Amplification | Detection          | Sensitivity |
|------------|---------------|---------|---------------|--------------------|-------------|
| SHERLOCK   | Cas13a        | RNA     | RPA           | Fluorescent ssRNA probe | Attomolar |
| DETECTR    | Cas12a        | DNA     | RPA or LAMP   | Fluorescent ssDNA probe | Attomolar |
| STOP-COVID | Cas12b        | RNA     | LAMP          | Lateral flow strip  | 100 copies  |

**Microfluidic Integration**:
- **Digital microfluidic CRISPR**: Samples automatically flow through chip components; cell
  lysis, RPA amplification, and Cas12a trans-cleavage occur in automated sequence. Complete
  detection in 55 minutes.
- **Paper-based microfluidic CRISPR**: Low-cost lateral flow integration for resource-limited
  settings.

**Regulatory Status (as of 2025)**:
- SHERLOCK: FDA Emergency Use Authorization (EUA) for SARS-CoV-2 detection
- DETECTR: CE certification for HPV typing
- Active FDA applications for expanded indications

**2025--2026 Trends**:
- Integration of CRISPR diagnostics with sample preparation on single microfluidic chips
- Multiplexed detection panels (respiratory, STI, tropical diseases)
- Smartphone-readable fluorescence for true point-of-care deployment
- Clinical validation expanding beyond COVID-19 to oncology (ctDNA), transplant monitoring,
  and infectious disease panels

---

## Summary: Technology Readiness and Selection Guide

| Application                    | Most Mature Platform              | Emerging Alternative           | Typical Budget    |
|--------------------------------|-----------------------------------|--------------------------------|-------------------|
| Organ-on-chip (single organ)   | Emulate, CN Bio PhysioMimix       | AlveoliX (lung), BiomimX (heart)| $150--250k system |
| Organ-on-chip (multi-organ)    | TissUse HUMIMIC, CN Bio dual      | Emulate (limited)              | $100--300k system |
| Organ-on-chip (high-throughput)| Mimetas OrganoPlate               | --                             | ~$50--150k        |
| Single-cell RNA-seq            | 10x Genomics Chromium X/Xo        | Bio-Rad ddSEQ                  | $25--75k instrument|
| Single-cell DNA+protein        | Mission Bio Tapestri              | --                             | $75--125k         |
| Single-cell (full-length)      | Standard BioTools C1              | Plate-based Smart-seq3         | $100--150k        |
| On-chip cell sorting           | AcouSort (acoustic)               | FADS (droplet)                 | $50--200k         |
| Digital PCR                    | Bio-Rad QX200/QX600               | QIAGEN QIAcuity, Stilla naica | $90--200k         |
| Isothermal amplification       | CapitalBio centrifugal LAMP       | VirChip, custom LAMP chips     | $10--50k          |
| CRISPR diagnostics             | Sherlock Biosciences (SHERLOCK)    | Mammoth Biosciences (DETECTR)  | Research stage    |
| Perfusion cell culture          | Beonchip Be-Flow, ibidi          | Fluigent integrated systems    | $5--50k           |
| Gradient generation            | Fluigent Be-Gradient              | Custom PDMS devices            | $5--20k           |

---

## Sources

- [Organ-on-a-Chip Global Market Report 2025](https://www.globenewswire.com/news-release/2025/04/11/3060228/0/en/Organ-on-a-Chip-Global-Market-Report-2025-with-Emulate-Mimetas-TissUse-InSphero-CN-Bio-Innovations-and-more.html)
- [Organ-on-a-Chip Market to Reach $2.2B by 2033 -- Astute Analytica](https://www.globenewswire.com/news-release/2026/02/09/3234681/0/en/Organ-on-a-Chip-Market-to-Reach-US-2-238-28-Million-by-2033-as-FDA-Support-and-Pharma-Adoption-Accelerate-Says-Astute-Analytica.html)
- [Mordor Intelligence OoC Market Forecast 2026-2031](https://www.mordorintelligence.com/industry-reports/organs-on-chips-market)
- [Top 20 Organ-on-a-Chip Companies 2026 -- SciSpot](https://www.scispot.com/blog/top-20-most-innovative-organ-on-a-chip-companies-in-the-world)
- [Emulate Organ-Chips](https://emulatebio.com/organ-chips/)
- [TissUse HUMIMIC Chip2](https://www.tissuse.com/en/humimic/chips/humimic-chip2/)
- [TissUse HUMIMIC Chip4](https://www.tissuse.com/en/humimic/chips/humimic-chip4/)
- [HUMIMIC Multi-Organ Crosstalk Review (2025)](https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.70031)
- [CN Bio PhysioMimix Core](https://cn-bio.com/physiomimix-core/)
- [CN Bio Organ Models](https://cn-bio.com/organ-models/)
- [Mimetas OrganoPlate Technology](https://www.mimetas.com/technology)
- [Mimetas OrganoPlate 2-lane 96](https://www.mimetas.com/en/organoplate-2-lane-96/)
- [AlveoliX Lung-on-Chip Breakthrough](https://medicalxpress.com/news/2025-12-lung-chip-genetically-identical-cells.html)
- [Commercially Available Lung-on-a-Chip Systems Review](https://www.frontiersin.org/journals/lab-on-a-chip-technologies/articles/10.3389/frlct.2024.1373029/full)
- [Cherry Biotech CherryTemp](https://www.cherrybiotech.com/cherrytemp/)
- [Cherry Biotech CubiX](https://www.cherrybiotech.com/organ-on-a-chip-technologies)
- [10x Genomics Chromium Platform](https://www.10xgenomics.com/platforms/chromium)
- [10x Genomics Chromium Xo Launch](https://www.prnewswire.com/news-releases/10x-genomics-unveils-chromium-xo-a-low-cost-instrument-to-expand-access-to-high-performance-single-cell-research-302237175.html)
- [10x Genomics GEM-X Technology](https://www.10xgenomics.com/platforms/chromium/technology)
- [Standard BioTools Single-Cell Microfluidics](https://www.standardbio.com/area-of-interest/single-cell-analysis/single-cell-analysis-with-microfluidics)
- [Bio-Rad ddSEQ Isolator](https://www.bio-rad.com/en-us/life-science/digital-pcr/single-cell-sample-preparation-for-ngs/ddseq-single-cell-isolator)
- [Mission Bio Tapestri Platform](https://missionbio.com/products/platform/)
- [Mission Bio ASH 2025 Data](https://www.pharmiweb.com/press-release/2025-12-04/mission-bio-s-tapestri-single-cell-multi-omics-platform-for-exploratory-biomarker-analysis-supports)
- [AcouSort Technology](https://acousort.com/technology/)
- [Cost-Effective Microfluidic Flow Cytometry (2025)](https://pubs.rsc.org/en/content/articlelanding/2025/lc/d4lc00900b)
- [Diaphragm-Based Sorting Platforms (2026)](https://pubs.rsc.org/en/content/articlehtml/2026/lc/d5lc00984g)
- [In-Air Microfluidic Sorting (2025)](https://www.nature.com/articles/s41378-025-01024-z)
- [ML-Enhanced Microfluidic Cell Sorting](https://www.science.org/doi/10.1126/sciadv.aea6007)
- [Bio-Rad QX600 ddPCR](https://www.bio-rad.com/en-us/product/qx600-droplet-digital-pcr-system?ID=b07d12ac-0585-fc4c-a586-3ddf20d5c4a0)
- [Bio-Rad Acquires Stilla, Expands ddPCR Portfolio](https://investors.bio-rad.com/press-releases/news-details/2025/Bio-Rad-Expands-Droplet-Digital-PCR-Offering-Through-Strategic-Acquisition-and-Platform-Rollout/default.aspx)
- [Stilla naica dPCR Reagents](https://www.stillatechnologies.com/multiplex-pcr/digital-pcr-reagents/)
- [Comparative Performance of Three dPCR Platforms](https://academic.oup.com/jambio/article/136/10/lxaf243/8266528)
- [VirChip Multiplexed Isothermal Detection (2025)](https://pubs.rsc.org/en/content/articlehtml/2025/lc/d5lc00509d)
- [Microfluidic LAMP for Viral Detection Review](https://pmc.ncbi.nlm.nih.gov/articles/PMC9628606/)
- [CRISPR Diagnostics Review (2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11717804/)
- [SHERLOCK and DETECTR Review](https://pmc.ncbi.nlm.nih.gov/articles/PMC8106734/)
- [Fluigent Be-Flow Perfusion Chip](https://www.fluigent.com/research/instruments/microfluidic-chips/cell-culture-organ-on-a-chip-microscopy/be-flow/)
- [Fluigent Be-Gradient](https://www.fluigent.com/research/instruments/microfluidic-chips/cell-culture-organ-on-a-chip-microscopy/be-gradient/)
- [Dissociable Perfusion Chip (2026)](https://pubs.rsc.org/en/content/articlehtml/2026/lc/d5lc01105a)
- [Automated NGS Library Prep on Open Microfluidic Platform](https://www.nature.com/articles/s41598-024-67950-6)
