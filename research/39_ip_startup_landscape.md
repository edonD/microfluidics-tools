# Microfluidics IP, Patents, and Startup Landscape

## Overview

The microfluidics field sits at the intersection of engineering, biology, and chemistry,
with a complex intellectual property landscape shaped by foundational academic patents,
aggressive corporate IP strategies, and a growing open-source movement. The global
microfluidic device market was valued at approximately USD 15.4 billion in 2025 and is
projected to reach USD 93.6 billion by 2035 (CAGR ~19.8%). More than 20,000 patent
families related to microfluidics have been published worldwide, with over 150 new
patent families published each month.

---

## 1. Key Microfluidics Patents

### 1.1 Foundational Patents

#### Quake Valves (Multilayer Soft Lithography)
- **Origin:** Stephen Quake's group at Caltech/Stanford introduced the pneumatic
  microvalve architecture in 2000 ("Monolithic microfabricated valves and pumps by
  multilayer soft lithography," Unger, Chou, Thorsen, Scherer & Quake, *Science* 288,
  113-116, 2000).
- **How it works:** A three-layer PDMS architecture with a microchannel lying
  orthogonally on top of another microchannel, separated by a thin elastomeric membrane.
  When the control channel is pressurized, the membrane deflects to interrupt flow in the
  orthogonal flow channel.
- **Patent impact:** Quake holds over 80 US and international patents. These patents
  formed the basis for Fluidigm Corporation (now Standard BioTools), which built
  commercial integrated fluidic circuits (IFCs) for genomics and proteomics.
- **Status:** Many of the earliest Quake valve patents (filed ~2000-2002) have expired
  or are nearing expiration given the 20-year patent term, opening up the foundational
  PDMS valve technology for broader use.

#### Droplet Microfluidics
- **Key contributors:** Groups led by Quake, David Weitz (Harvard), and Howard Stone
  pioneered droplet generation in microchannels, demonstrating exquisite control over
  multiphase droplet systems.
- **Core patents:** Cover T-junction and flow-focusing droplet generators, surfactant
  stabilization, and droplet manipulation techniques.
- **Litigation:** Bio-Rad Laboratories and the University of Chicago won a patent
  infringement case against 10x Genomics in 2018, with $23.9 million in damages
  awarded for infringement of droplet microfluidics patents. The dispute was eventually
  resolved through a cross-licensing agreement.
- **Current status:** Many foundational droplet generation patents from the early 2000s
  have expired. However, application-specific patents (single-cell sequencing, digital
  PCR) remain active.

#### Digital Microfluidics (Electrowetting-on-Dielectric / EWOD)
- **Key patents:** Cover manipulation of individual droplets on planar electrode arrays
  using electrowetting. Foundational work from Duke University (Richard Fair) and UCLA
  (CJ Kim).
- **Commercial implementations:** Illumina (acquired Advanced Liquid Logic), Baebies,
  and Sci-Bots have commercialized EWOD-based platforms.
- **Status:** Core EWOD patents from the early 2000s are expiring, but newer patents
  on specific electrode geometries, dielectric materials, and application methods remain
  active.

#### Other Foundational Technologies
- **Paper microfluidics:** George Whitesides' group at Harvard pioneered
  microfluidic paper-based analytical devices (muPADs). Early patents are expiring.
- **Centrifugal microfluidics (lab-on-a-disc):** Patents held by various groups
  including Gyros Protein Technologies and universities.
- **Organ-on-chip:** Emulate Inc. holds significant IP derived from Donald Ingber's
  work at the Wyss Institute (Harvard).

### 1.2 Patent Expiration and Field Opening

Key patent expiration milestones:

| Technology | Approximate Filing Period | Estimated Expiration | Impact |
|---|---|---|---|
| Quake valves (basic PDMS) | 1999-2002 | 2019-2022 | Core valve architecture now open |
| Early droplet generation | 2001-2005 | 2021-2025 | Basic T-junction/flow-focusing open |
| Soft lithography methods | 1998-2003 | 2018-2023 | PDMS molding techniques widely available |
| Early EWOD | 2000-2004 | 2020-2024 | Basic electrowetting manipulation open |
| Paper microfluidics | 2007-2010 | 2027-2030 | Still partially protected |

The expiration of foundational patents is a significant opportunity for startups, as
basic microfluidic architectures (simple valves, droplet generators, channel geometries)
are increasingly available for use without licensing fees. However, application-specific
patents and improvements remain active.

### 1.3 Patent Thickets and Freedom-to-Operate

Microfluidics is characterized by dense patent thickets in several areas:

- **Single-cell analysis:** Overlapping patents from 10x Genomics, Bio-Rad, Fluidigm/
  Standard BioTools, and multiple universities create a complex licensing environment.
- **Digital PCR:** Bio-Rad and Stilla Technologies hold key patents on droplet digital
  PCR implementations.
- **Point-of-care diagnostics:** Abbott, Roche, Cepheid (Danaher), and numerous
  startups hold overlapping claims on sample-to-answer microfluidic cartridges.
- **Drug delivery microparticles:** Patents on microfluidic production of drug-loaded
  nanoparticles and microparticles from multiple pharmaceutical companies.

Freedom-to-operate (FTO) risks are particularly high in:
- Droplet-based single-cell genomics
- Integrated sample preparation cartridges
- Microfluidic PCR and isothermal amplification

---

## 2. IP Strategy for Microfluidics Startups

### 2.1 What to Patent vs. Keep as Trade Secret

**Patent candidates (publicly observable or reverse-engineerable):**
- Novel chip geometries and channel architectures
- New valve or pump mechanisms
- Unique droplet generation or manipulation methods
- Novel material compositions for chip fabrication
- Integration of sensors with microfluidic channels
- Application-specific cartridge designs

**Trade secret candidates (hard to reverse-engineer):**
- Specific fabrication process parameters (temperatures, pressures, timing)
- Surface treatment recipes and protocols
- Software algorithms for flow control and data analysis
- Proprietary reagent formulations used with chips
- Quality control procedures and yield optimization techniques
- Supplier relationships and custom material specifications

### 2.2 Design-Around Strategies

When encountering blocking patents, common design-around approaches include:

1. **Alternative channel geometries:** If a specific T-junction design is patented,
   use flow-focusing, co-flow, or step emulsification instead.
2. **Different materials:** Substitute PDMS with thermoplastics (COC, COP, PMMA),
   glass, or paper to avoid material-specific claims.
3. **Alternative actuation:** Replace pneumatic valves with piezoelectric, thermal,
   magnetic, or capillary-driven approaches.
4. **Passive vs. active methods:** Use capillary forces, gravity, or surface tension
   instead of external pumps if pump-related patents are blocking.
5. **Manufacturing method changes:** Switch from soft lithography to injection molding,
   hot embossing, or 3D printing.

### 2.3 Freedom-to-Operate Analysis

A thorough FTO analysis for a microfluidics startup should include:

1. **Prior art search:** Search patent databases (Google Patents, USPTO, EPO Espacenet,
   WIPO) for relevant claims in your technology area.
2. **Claim mapping:** Map your product features against identified patent claims to
   assess potential infringement.
3. **Expiration check:** Verify whether blocking patents have expired or will expire
   before your product launch.
4. **Geographic scope:** Check where blocking patents are filed -- many academic patents
   are only filed in the US, leaving other markets open.
5. **Validity assessment:** Evaluate whether blocking patents could be challenged on
   grounds of prior art, obviousness, or insufficient disclosure.
6. **Landscape monitoring:** Subscribe to patent monitoring services (approximately
   150 new microfluidic device patent families are published monthly).

**Recommended resources:**
- Google Patents (free, comprehensive)
- USPTO PAIR (free, US-specific)
- EPO Espacenet (free, European focus)
- Knowmade patent landscape reports (paid, microfluidics-specific)
- Lens.org (free, integrates patents and scholarly literature)

### 2.4 Patent Filing Costs and Timelines

| Stage | Cost (USD) | Timeline |
|---|---|---|
| Provisional patent application (US) | $5,000-$15,000 | 1-2 months to prepare |
| Non-provisional utility patent (US) | $10,000-$25,000 | 2-4 years to grant |
| PCT international application | $5,000-$10,000 | 30-31 months before national phase |
| National phase entry (per country) | $3,000-$8,000 each | Varies by jurisdiction |
| European patent (EPO) | $15,000-$30,000 total | 3-5 years to grant |
| Patent maintenance/annuity fees | $1,000-$5,000/year | Ongoing for patent life |
| Design patent (US) | $2,000-$5,000 | 1-2 years to grant |
| FTO opinion (attorney) | $10,000-$50,000 | 4-8 weeks |

**Strategy tips for resource-constrained startups:**
- File provisional applications early to establish priority dates ($5K-$15K buys 12
  months of protection).
- Prioritize US filing first -- most microfluidics IP activity centers on the US.
- Use the PCT system to defer international costs by up to 30 months.
- Consider filing in the US and one additional key market (Europe or China) initially.
- Budget approximately $50K-$100K for the first 3 years of patent prosecution for a
  small portfolio of 2-3 patent families.

---

## 3. Major Patent Holders

### 3.1 Corporate Patent Portfolios

| Company | Focus Area | Patent Strength | Notes |
|---|---|---|---|
| **Standard BioTools** (formerly Fluidigm) | Integrated fluidic circuits, mass cytometry | Very strong (~5.8B portfolio value est.) | Pioneer in commercial microfluidics; cited by 700+ patent assignees |
| **10x Genomics** | Droplet-based single-cell genomics | Very strong | Extensive patent portfolio; major litigation with Bio-Rad |
| **Bio-Rad Laboratories** | Droplet digital PCR, single-cell | Strong | Licensed University of Chicago droplet patents |
| **Agilent Technologies** | High-throughput screening, analytical | Strong | Focus on analytical precision and fabrication |
| **Thermo Fisher Scientific** | Broad life sciences tools | Very strong | Acquired multiple microfluidics companies |
| **Roche/Genentech** | Diagnostics, sequencing | Strong | Point-of-care and sequencing cartridges |
| **Abbott** | Point-of-care diagnostics | Strong | i-STAT and other cartridge-based systems |
| **Danaher (Cepheid)** | Molecular diagnostics cartridges | Strong | GeneXpert system |
| **Samsung Electronics** | Consumer diagnostics | Growing | Increasing filings in microfluidic diagnostics |
| **3M Innovative Properties** | Materials, fabrication | Moderate | Focus on adhesive and film technologies |
| **Illumina** | Sequencing flow cells | Very strong | Includes acquired Advanced Liquid Logic IP |
| **Dolomite Microfluidics** | Droplet generation, modular systems | Moderate | Now part of Blacktrace Holdings |

### 3.2 University Patent Holders

| Institution | Strengths | Notable IP |
|---|---|---|
| **Caltech** | Ranked #1 in patent strength for microfluidics | Quake valve architecture, nucleic acid analysis |
| **University of California** | Worldwide IP strategy in diagnostics | Broad microfluidics diagnostic applications |
| **Harvard University** | Droplet microfluidics, organ-on-chip | Weitz lab droplets; Whitesides paper microfluidics; Ingber organ-on-chip |
| **MIT** | Pump technologies, open-source | Non-mechanical pumps, Metafluidics platform |
| **Stanford University** | Valve technology, cell sorting | Quake lab continuation patents |
| **Duke University** | Digital microfluidics (EWOD) | Foundational electrowetting patents |
| **University of Chicago** | Droplet generation | Patents licensed to Bio-Rad |

### 3.3 Licensing Opportunities

- **University tech transfer offices** often license on reasonable terms, especially to
  startups. Typical structures include:
  - Exclusive or non-exclusive licenses
  - Upfront fees ($10K-$100K) plus running royalties (2-5% of net sales)
  - Milestone payments tied to product development
  - Some universities offer equity-based licensing for startups
- **Cross-licensing** is common among large players (e.g., Bio-Rad and 10x Genomics
  resolved their dispute through cross-licensing).
- **Patent pools** are not yet common in microfluidics but may emerge as the field
  matures, particularly around standards for point-of-care testing.

---

## 4. Open Innovation and Technology Sharing

### 4.1 Metafluidics

[Metafluidics](https://metafluidics.org) is the most significant open-source initiative
in the microfluidics space:

- **What it is:** A not-for-profit, community-driven repository that hosts digital
  design files, assembly specifications, and open-source software for building,
  configuring, and operating microfluidic devices.
- **Origin:** Developed at the MIT Media Lab; published in *Nature Biotechnology*
  (2017).
- **Model:** Emulates open-source repositories like GitHub and Thingiverse, but
  focused specifically on microfluidics.
- **Community:** Enables a broad community including engineers, DIY enthusiasts, and
  non-traditional participants with limited fabrication skills to contribute to
  microfluidic research.
- **Features:** Users can submit designs, comment, like, and download design files to
  reproduce or improve featured devices.
- **Impact:** Addresses a critical gap in the field -- most published microfluidics
  research lacks the design files needed to reproduce devices.

### 4.2 Other Open Innovation Initiatives

- **OpenFluidics / open-source hardware movement:** Growing community of researchers
  sharing designs for pumps, controllers, and chip holders under open licenses
  (typically CC-BY or MIT license).
- **3D-printed microfluidics repositories:** Various groups share STL files for
  3D-printable microfluidic devices on platforms like GitHub, Thingiverse, and NIH
  3D Print Exchange.
- **The Microfluidic Circle** (ufluidix.com/circle): A community platform where
  microfluidics startups can register, access mentorship, and connect with the
  ecosystem. Not an incubator -- does not take equity.
- **Academic preprint sharing:** Increasing trend toward sharing fabrication protocols,
  CAD files, and control software alongside publications.

### 4.3 Standards and Interoperability

- **ISO standards:** ISO has working groups on microfluidics standardization, including
  interconnect standards (ISO 22916) for chip-to-world interfaces.
- **No standards-essential patents (SEPs):** Unlike telecommunications, microfluidics
  does not currently have FRAND-licensed SEPs. However, if ISO interconnect standards
  gain adoption, SEPs could emerge.
- **IPC standards:** Industry standards for microfluidic manufacturing quality are under
  development, with potential patent implications.

---

## 5. Microfluidics Startup Ecosystem

### 5.1 Recent Funding Activity (2024-2026)

#### Notable Funding Rounds

| Company | Round | Amount | Lead Investor(s) | Year | Focus |
|---|---|---|---|---|---|
| **Atrandi Biosciences** | Series A | $25M | Lux Capital | 2025 | Droplet microfluidics, single-cell analysis |
| **Xunming Biotech** | Series A | Tens of millions (RMB) | Undisclosed | 2025 | AI + microfluidics for antibody design |
| **iBioChips** | Various | Undisclosed | Various | 2024-25 | Biosensors, lab-on-chip bioassays |
| **mFluiDx** | Various | Undisclosed | Various | 2024-25 | Vacuum-based microfluidics diagnostics |

#### Investment Themes

Key areas attracting VC attention in 2025-2026:
- **Single-cell multi-omics:** Platforms combining microfluidics with genomics,
  proteomics, and metabolomics at single-cell resolution.
- **Point-of-care diagnostics:** Post-pandemic demand for rapid, decentralized testing
  continues to drive investment.
- **Organ-on-chip / microphysiological systems:** Growing interest from pharma for
  drug screening and toxicology.
- **Microfluidic manufacturing:** Production of lipid nanoparticles (LNPs) for mRNA
  therapeutics.
- **Semiconductor cooling:** Microfluidic cold plates for data center and AI chip
  cooling -- a new and rapidly growing application area.

### 5.2 Incubators and Accelerators

| Program | Location | Description |
|---|---|---|
| **CorMic Tech Hub** (Corvallis Microfluidics Technology Hub) | Corvallis, OR, USA | Led by Oregon State University; 80K sq ft of incubator space; access to training, funding, scale-up consulting; focused on semiconductor cooling, continuous flow processing, and biotech |
| **Microfluidics Innovation Hub (MIH)** | Europe | Consortium of 21 companies and research organizations; offers services from startups to large-scale industry across the full value chain |
| **EU EIC Accelerator** | Europe | European Innovation Council provides funding for microfluidics startups with tailored milestones for bio-assay transfer, manufacturability, and certification |
| **The Microfluidic Circle** | Global (online) | Community platform with mentorship; no equity taken |
| **General biotech accelerators** | Various | IndieBio, Y Combinator (bio track), JLABS, Illumina Accelerator all support microfluidics-adjacent startups |

### 5.3 Key Investors in Microfluidics

**Venture Capital Firms:**
- **Lux Capital** -- Led Atrandi Biosciences Series A; active in deep tech/life sciences
- **Casdin Capital** -- Led $250M investment in Fluidigm/Standard BioTools
- **Viking Global Investors** -- Co-invested in Fluidigm/Standard BioTools
- **Vsquared Ventures** -- Participated in Atrandi Biosciences
- **ARCH Venture Partners** -- Active in life sciences tools
- **Foresite Capital** -- Focus on healthcare and life sciences

**Corporate Venture Arms:**
- **Illumina Ventures** -- Invests in genomics-adjacent microfluidics
- **Roche Venture Fund** -- Diagnostics-focused microfluidics
- **Johnson & Johnson Innovation (JJDC)** -- Medical device microfluidics

### 5.4 Exit Strategies

#### Acquisition (Dominant Path)

M&A accounts for over 85% of VC-backed exits in life sciences tools. Key acquirers of
microfluidics companies include:

| Acquirer | Notable Acquisitions | Rationale |
|---|---|---|
| **Thermo Fisher Scientific** | Multiple platform acquisitions | Broad life sciences tools portfolio |
| **Danaher** | Cepheid ($4B, 2016) | Molecular diagnostics cartridges |
| **Illumina** | Advanced Liquid Logic | Digital microfluidics for sequencing |
| **Bio-Rad** | Licensed/partnered with multiple startups | Droplet digital PCR expansion |
| **Standard BioTools** | SomaLogic (merger, 2023); DVS Sciences (2014) | Multi-omics platform consolidation |
| **Blacktrace Holdings** | Dolomite Microfluidics | Modular microfluidics systems |

**Typical acquisition multiples:** Life sciences tools companies typically trade at
5-15x revenue, with premium valuations for companies with strong IP, recurring revenue
(reagent/consumable models), and growing installed bases.

#### IPO (Less Common but Possible)

- The IPO market for life sciences tools is recovering after a downturn in 2022-2023.
- 10x Genomics went public in 2019 (raised $390M); Fluidigm went public in 2011.
- IPO is typically viable for companies with >$50M annual revenue and clear path to
  profitability.
- SPACs have become less common as an exit route since 2022.

#### Strategic Considerations for Founders

1. **Build for acquisition:** Most microfluidics startups should plan for acquisition
   as the primary exit. Design products with clear integration points for acquirers'
   existing platforms.
2. **Consumable revenue model:** Develop a razor/blade model (instrument + consumable
   cartridges) to create recurring revenue, which commands higher acquisition multiples.
3. **IP portfolio as acquisition driver:** A strong, well-maintained patent portfolio
   significantly increases acquisition value, even if revenue is modest.
4. **Strategic partnerships:** Collaborations with potential acquirers (e.g., co-
   development agreements, OEM relationships) often precede acquisitions.
5. **Regulatory clearance as moat:** FDA 510(k) or CE-IVD clearance for diagnostic
   applications creates significant barriers to entry and increases acquisition value.

---

## 6. Practical Recommendations for New Entrants

### 6.1 IP Strategy Checklist

- [ ] Conduct a preliminary patent landscape search before beginning development
- [ ] File provisional patent applications early to establish priority dates
- [ ] Identify and document trade secrets with proper confidentiality protocols
- [ ] Perform FTO analysis before product launch (budget $10K-$50K for attorney opinion)
- [ ] Monitor competitor patent filings monthly using free tools (Google Patents alerts)
- [ ] Evaluate expired foundational patents that may enable your technology
- [ ] Consider defensive publications for innovations you do not plan to patent

### 6.2 Cost-Effective IP Protection Timeline

| Milestone | IP Action | Approximate Cost |
|---|---|---|
| Idea stage | Prior art search, landscape review | $2K-$5K |
| Prototype | File provisional patent application(s) | $5K-$15K per application |
| 12 months post-provisional | Convert to non-provisional or PCT | $10K-$25K per application |
| Pre-product launch | FTO analysis | $10K-$50K |
| 30 months post-priority | National phase entry (select countries) | $3K-$8K per country |
| Revenue generation | Ongoing maintenance and portfolio expansion | $5K-$20K/year |

### 6.3 Geographic IP Priority

1. **United States** -- Largest microfluidics patent landscape (800+ patents); most
   non-American applicants also file in the US first.
2. **Europe (EPO)** -- Second-largest filing jurisdiction (650+ patents); important for
   IVD market access.
3. **China** -- Rapidly growing market; increasing patent filings.
4. **Japan/Korea** -- Important for semiconductor-related microfluidics applications.

---

## 7. Key Risks and Emerging Trends

### 7.1 IP Risks

- **Patent trolls:** Non-practicing entities have begun acquiring expired and abandoned
  microfluidics patents. Monitor assignments of university and startup patents.
- **International enforcement:** Patent enforcement is difficult and expensive in some
  jurisdictions (particularly China), limiting the value of patents filed there.
- **Trade secret theft:** As microfluidics fabrication moves to contract manufacturers,
  protecting process know-how becomes critical.
- **AI-generated inventions:** Uncertainty around patentability of AI-designed
  microfluidic geometries; current US law requires a human inventor.

### 7.2 Emerging Patent Areas (2025-2026)

- **AI + microfluidics integration:** Patents combining machine learning with
  microfluidic control and analysis are surging.
- **3D-printed microfluidics:** New materials and multi-material printing methods are
  generating fresh IP.
- **Semiconductor cooling:** Microfluidic cold plates for chip cooling represent a
  rapidly expanding patent domain.
- **Wearable microfluidics:** Skin-interfacing microfluidic devices for continuous
  health monitoring.
- **Space/microgravity microfluidics:** Emerging niche with limited existing IP.

---

## Sources

- [3D-printed Quake-style microvalves and micropumps - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC7307877/)
- [Stephen Quake | Lemelson-MIT Prize](https://lemelson.mit.edu/award-winners/stephen-quake)
- [Microfluidics Market Size & Growth Forecast - MarketsandMarkets](https://www.marketsandmarkets.com/Market-Reports/microfluidics-market-1305.html)
- [Microfluidic Device Patent Landscape Report - Expert Market Research](https://www.expertmarketresearch.com/patent-analysis/microfluidic-device-patent-landscape)
- [Microfluidic Technologies for Diagnostic Applications Patent Landscape - GlobeNewsWire](https://www.globenewswire.com/news-release/2025/04/21/3064482/28124/en/Microfluidic-Technologies-for-Diagnostic-Applications-Patent-Landscape-Report-2024-2032-Patent-Surge-with-70-New-Entries-Filed-Highlighting-Advances-in-Portable-and-Automated-Diagn.html)
- [Patent protection and licensing in microfluidics - Lab on a Chip](https://pubs.rsc.org/en/content/articlelanding/2014/lc/c4lc00399c)
- [The Microfluidic Patent Landscape - Technology Networks](https://www.technologynetworks.com/tn/news/the-microfluidic-patent-landscape-286179)
- [Microfluidics Patent Landscape Report - Knowmade](https://www.knowmade.com/patent-analytics-services/patent-report/life-sciences-patent-landscape/microfluidic-technologies-for-diagnostic-applications-patent-landscape/)
- [Mapping the lab-on-a-chip patent landscape - ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0172219018301042)
- [Bio-Rad and University of Chicago Win Patent Case Against 10X Genomics](https://investors.bio-rad.com/press-releases/news-details/2018/Bio-Rad-and-the-University-of-Chicago-Win-Patent-Infringement-Case-Against-10X-Genomics-Related-to-Droplet-Microfluidics-Technologies-11-14-2018/default.aspx)
- [Bio-Rad and 10x Genomics Settle through Cross Licensing - IIPRD](https://www.iiprd.com/after-intense-patent-litigation-bio-rad-and-10x-genomics-settle-through-cross-licensing/)
- [Fluidigm Patent Portfolio Analysis - Knowmade](https://www.knowmade.com/patent-analytics-services/patent-report/life-sciences-patent-landscape/fluidigm-patent-portfolio-analysis/)
- [Open-source, community-driven microfluidics with Metafluidics - Nature Biotechnology](https://www.nature.com/articles/nbt.3873)
- [Microfluidics for the masses - MIT News](https://news.mit.edu/2017/open-source-microfluidics-0613)
- [Atrandi Biosciences Raises $25M Series A](https://atrandi.com/news/atrandi-biosciences-raises-25m-series-a-led-by-lux-capital)
- [Corvallis Microfluidics Tech Hub - US EDA](https://www.eda.gov/funding/programs/regional-technology-and-innovation-hubs/2023/Corvallis-Microfluidics-Tech-Hub)
- [Microfluidics Innovation Hub](https://www.microfluidicshub.eu/)
- [The Microfluidic Circle - Startups](https://www.ufluidix.com/circle/startups/)
- [Standard BioTools - Wikipedia](https://en.wikipedia.org/wiki/Standard_BioTools)
- [Fluidigm Rebrands to Standard BioTools - GlobeNewsWire](https://www.globenewswire.com/news-release/2022/04/04/2416137/0/en/Fluidigm-Completes-250-Million-Strategic-Capital-Infusion-and-Changes-Name-to-Standard-BioTools-Inc.html)
- [Standard BioTools Completes Merger with SomaLogic](https://investors.standardbio.com/news-releases/news-release-details/standard-biotools-completes-merger-somalogic-creating)
- [Microfluidics Research Report 2026-2035 - GlobeNewsWire](https://www.globenewswire.com/news-release/2026/02/23/3242409/28124/en/Microfluidics-Research-Report-2026-2035-A-20-73-Billion-Market-by-2030-with-Thermo-Fisher-Scientific-PerkinElmer-Dolomite-Agilent-Technologies-Bio-Rad-Laboratories-and-Fluidigm-Lea.html)
- [Pumps for Microfluidic Devices Patent Landscape Report 2026](https://www.expertmarketresearch.com/patent-analysis/pumps-for-microfluidic-devices-patent-landscape)
- [10x Genomics and Harvard Settle with Vizgen](https://www.thepatentplaybook.com/2025/02/10x-genomics-and-harvard-overcome-patent-and-antitrust-hurdles-after-settling-with-vizgen-inc/)
- [EIE Work Programme 2026-2027 - Microfluidics Innovation Center](https://microfluidics-innovation-center.com/calls-for-proposals/horizon-europe-2026-2027-ordered-by-microfluidic-relevance/eie-work-programme-2026-2027/)
- [Seedtable - Best Microfluidics Startups 2026](https://www.seedtable.com/best-microfluidics-startups)
