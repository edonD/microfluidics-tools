# Commercializing a Microfluidic Product

A practical guide covering the full journey from laboratory prototype to commercial product launch.

---

## 1. Technology Readiness Levels (TRL) for Microfluidics

The TRL framework, originally developed by NASA, provides a structured way to assess the maturity of a microfluidic technology as it advances from concept to commercial product. A significant "transformation gap" exists between academic prototyping (typically PDMS-based soft lithography) and large-scale commercial manufacturing (typically thermoplastic injection molding). Understanding this gap at each TRL stage is essential.

### TRL 1-3: Concept and Proof of Concept

**TRL 1 -- Basic Principles Observed**
- Scientific literature review identifies a new fluidic phenomenon or assay opportunity
- Initial hypothesis: "a microfluidic device could solve this problem"
- No hardware exists yet; only theoretical analysis and paper studies
- Microfluidics milestone: identification of target analyte, clinical need, or process bottleneck

**TRL 2 -- Technology Concept Formulated**
- Preliminary device architecture sketched (channel layout, functional zones)
- Basic feasibility calculations (flow rates, mixing times, reaction kinetics)
- Initial COMSOL or CFD simulations of key fluid behaviors
- Microfluidics milestone: concept design with defined inputs, outputs, and functional requirements

**TRL 3 -- Experimental Proof of Concept**
- PDMS prototyping via soft lithography in academic cleanroom
- Demonstration that the core fluidic function works (mixing, separation, detection)
- Bench-top experiments with surrogate fluids and analytes
- First publication or patent filing
- Microfluidics milestone: working PDMS chip demonstrating core function with laboratory-grade reagents

**Typical activities at TRL 1-3:**
- Rapid prototyping with PDMS (turnaround: days to weeks)
- Academic collaboration or in-house R&D
- Low cost ($5K-$100K), grant-funded or self-funded
- Key output: proof-of-concept data, preliminary IP filing

### TRL 4-5: Laboratory Validation

**TRL 4 -- Component Validation in Laboratory Environment**
- Individual subsystems validated (fluidic handling, detection, thermal control)
- Assay performance characterized with real clinical or industrial samples
- Initial design freeze for core fluidic architecture
- Material selection begins: evaluating thermoplastics (COC, COP, PMMA, polycarbonate) as alternatives to PDMS
- Surface chemistry compatibility testing with candidate production materials
- Microfluidics milestone: demonstrated analyte detection in clinical matrix with defined sensitivity/specificity targets

**TRL 5 -- Integrated System Validation in Relevant Environment**
- Full device integration: fluidics + optics + electronics + software
- Testing with real-world sample types (whole blood, saliva, environmental water)
- Reproducibility studies (n >= 30) establishing coefficient of variation
- Design for manufacturability (DFM) review begins
- First thermoplastic prototypes (CNC-machined or hot-embossed) for material compatibility
- User interface and workflow usability assessment
- Microfluidics milestone: integrated prototype achieving target analytical performance in relevant sample matrix; preliminary DFM assessment complete

**Typical activities at TRL 4-5:**
- Material translation studies (PDMS to thermoplastic)
- Engagement with contract development and manufacturing organizations (CDMOs)
- Assay optimization and reagent stabilization (lyophilization, bead drying)
- Cost: $500K-$3M; typically seed or Series A funded
- Key output: design freeze, material selection, preliminary manufacturing plan

### TRL 6-7: Prototype Demonstration

**TRL 6 -- System Demonstration in Relevant Environment**
- Engineering prototypes manufactured using production-intent processes
- Injection-molded thermoplastic chips (pilot tooling, typically single-cavity)
- Instrument prototype with production-grade components
- Performance verification across operating conditions (temperature, humidity, altitude)
- Reagent shelf-life studies initiated (target: 12-24 months)
- Design verification testing per ISO 13485 / 21 CFR 820
- Microfluidics milestone: injection-molded device meets analytical specifications; manufacturing yield > 80%

**TRL 7 -- System Prototype Demonstration in Operational Environment**
- Pilot production run (100-1,000 units)
- Multi-site beta testing with Key Opinion Leaders (KOLs)
- Clinical validation study design and IRB/ethics approval
- Manufacturing process validation (IQ/OQ/PQ)
- Supply chain qualification (resin suppliers, bonding adhesives, reagent sources)
- Reliability and accelerated aging studies
- Microfluidics milestone: pilot-scale production with consistent yield > 90%; beta-site feedback incorporated

**Typical activities at TRL 6-7:**
- Transition from prototype tooling to production tooling (multi-cavity molds)
- Quality management system (QMS) implementation
- Clinical study execution
- Cost: $3M-$15M; typically Series A or Series B funded
- Key output: clinical data package, validated manufacturing process, regulatory submission-ready documentation

### TRL 8-9: Product Qualification and Launch

**TRL 8 -- Actual System Completed and Qualified**
- Regulatory submission (FDA 510(k), De Novo, or PMA; CE-IVDR in EU)
- Manufacturing scale-up to commercial volumes (multi-cavity injection molding, automated assembly)
- Final design transfer to manufacturing
- Labeling, packaging, and shipping validation
- Training materials and service documentation
- Microfluidics milestone: regulatory clearance/approval obtained; manufacturing at commercial scale with yield > 95%

**TRL 9 -- Actual System Proven in Operational Environment**
- Commercial launch and market entry
- Post-market surveillance and complaint handling
- Continuous improvement and cost reduction
- Menu expansion (additional assays on the same platform)
- Geographic regulatory expansion (CE marking, Health Canada, TGA, PMDA)
- Microfluidics milestone: sustained commercial sales; post-market data confirms field performance

**Typical activities at TRL 8-9:**
- Regulatory affairs management and post-market obligations
- Sales and distribution infrastructure
- Customer support and field service
- Cost: $10M-$50M+; Series B/C or revenue-funded
- Key output: cleared/approved product on the market generating revenue

### The PDMS-to-Thermoplastic Translation Challenge

This is the single most underestimated technical risk in microfluidics commercialization:

| Property | PDMS | Thermoplastics (COC/COP) |
|---|---|---|
| Gas permeability | High (good for cell culture, bad for reagent stability) | Low |
| Surface chemistry | Hydrophobic (modifiable with plasma) | Variable; requires coatings |
| Protein absorption | High (problematic for immunoassays) | Lower |
| Optical clarity | Good | Excellent (COC/COP) |
| Manufacturing method | Soft lithography (manual) | Injection molding (automated) |
| Cost at scale | $10-50/chip | $0.50-$5/chip |
| Minimum feature size | ~10 um | ~50 um (injection molding) |
| Bonding | Plasma bonding, reversible | Thermal, solvent, adhesive, laser welding |

Key translation challenges:
- **Surface wetting behavior changes** -- PDMS is inherently hydrophobic; thermoplastics vary. Assays optimized on PDMS may fail on thermoplastics without surface treatment.
- **Channel geometry fidelity** -- injection molding has different constraints than soft lithography (draft angles, wall thickness uniformity, gate locations).
- **Bonding reliability** -- PDMS-to-glass plasma bonds do not translate. Thermoplastic bonding (thermal, ultrasonic, laser, adhesive) must be optimized for each design.
- **Reagent stability** -- PDMS absorbs small molecules; switching to thermoplastics changes reagent-surface interactions.
- **Timeline** -- material translation typically adds 12-18 months to the development timeline.

---

## 2. Business Models in Microfluidics

The global microfluidics market was valued at approximately $24 billion in 2025 and is projected to reach $37 billion by 2030 (CAGR ~8.3%). Several proven business models exist.

### 2.1 Razor-and-Blade Model (Instrument + Disposable Chips)

This is the dominant model in microfluidic diagnostics and life sciences.

**Structure:**
- Sell or place an instrument (reader/analyzer) at low margin or at cost
- Generate recurring revenue from disposable microfluidic cartridges and reagents
- Cartridge margins typically 60-80%; instrument margins 0-30%

**Examples:**
- Abbott (i-STAT): handheld analyzer + single-use cartridges for blood chemistry
- Cepheid (GeneXpert): PCR instrument + self-contained cartridges
- Agilent (Bioanalyzer): instrument + microfluidic chips for electrophoresis
- 10x Genomics (Chromium): instrument + single-cell encapsulation chips

**Financial characteristics:**
- High upfront capital requirement (instrument development)
- Revenue ramp is slow (install base must grow before consumable revenue scales)
- Highly predictable recurring revenue once installed base is established
- Customer switching costs are high (locked into the platform)
- Typical target: 3-5x consumable revenue vs. instrument revenue within 3 years

**Key considerations:**
- Cartridge cost of goods must be low enough to maintain margins at competitive pricing
- Manufacturing scale-up for consumables is the critical path
- Menu expansion (more tests per platform) drives consumable pull-through
- Instrument reliability is paramount -- downtime stops consumable revenue

### 2.2 Service / Test Model (Send Sample, Get Result)

The company runs the microfluidic technology internally and sells results rather than devices.

**Structure:**
- Customer sends a sample (blood, tissue, water, food)
- Company processes it on their microfluidic platform
- Customer receives a result (report, data, actionable insight)

**Examples:**
- Clinical reference laboratories using proprietary microfluidic platforms
- Environmental testing services
- Cell therapy characterization services

**Financial characteristics:**
- Lower capital barrier than razor-and-blade (no instrument manufacturing)
- Revenue scales with sample volume
- Margins depend on throughput and automation
- Geographic expansion requires new lab sites or shipping logistics

**When to use this model:**
- Technology is too complex for end-user operation
- Regulatory pathway is simpler as a laboratory-developed test (LDT)
- Market is too small to justify instrument manufacturing
- Speed to revenue is more important than scale

### 2.3 OEM Component Supplier Model

The company sells microfluidic chips, modules, or subsystems to other device manufacturers.

**Structure:**
- Develop and manufacture standardized or custom microfluidic components
- Sell to OEMs who integrate them into their own branded products
- Revenue from component sales, NRE (non-recurring engineering), and licensing

**Examples:**
- Dolomite Microfluidics: modular microfluidic components
- Micralyne/Teledyne MEMS: custom microfluidic chip fabrication
- ALine Inc.: rapid prototyping and low-volume production of microfluidic devices
- Contract manufacturers offering injection-molded microfluidic chips

**Financial characteristics:**
- Faster time to revenue (no end-user regulatory path needed)
- Lower margins than end-product companies (typically 30-50%)
- Revenue concentration risk (dependent on OEM customers' success)
- NRE revenue can fund operations during development phase

### 2.4 Platform Licensing Model

The company licenses its microfluidic technology to partners who commercialize end products.

**Structure:**
- Develop a core microfluidic platform technology (e.g., droplet generation, digital microfluidics)
- License the technology to partners for specific applications
- Revenue from upfront licensing fees, milestone payments, and royalties

**Examples:**
- Fluidigm (now Standard BioTools): licensed integrated fluidic circuit technology
- RainDance Technologies (acquired by Bio-Rad): licensed droplet microfluidics patents
- University spin-outs licensing foundational IP

**Financial characteristics:**
- Low capital intensity (partner bears manufacturing and commercialization costs)
- Revenue is lumpy (milestone-dependent)
- Requires strong IP position (broad, defensible patents)
- Risk: partners may develop around the IP or the licensed technology may not succeed

### 2.5 Hybrid Models

Most successful microfluidics companies employ hybrid approaches:
- Razor-and-blade for primary market + OEM supply for adjacent markets
- Platform licensing for fields outside core focus + direct commercialization for primary application
- Service model for early revenue + transition to razor-and-blade as technology matures

---

## 3. Fundraising and Investment

### 3.1 Typical Funding Stages for a Microfluidics Company

| Stage | Typical Amount | Use of Funds | Investors | TRL |
|---|---|---|---|---|
| Pre-seed / Friends & Family | $100K-$500K | Proof of concept, IP filing | Founders, angels | 1-3 |
| Seed | $500K-$3M | Prototype, early clinical data, team | Angels, micro-VCs, grants | 3-4 |
| Series A | $5M-$25M | Clinical validation, pilot manufacturing, regulatory prep | Venture capital | 4-6 |
| Series B | $20M-$60M | Manufacturing scale-up, regulatory submission, commercial launch prep | Venture capital, strategic investors | 6-8 |
| Series C+ | $50M-$150M+ | Commercial launch, geographic expansion, menu expansion | Late-stage VC, PE, strategic partners | 8-9 |

### 3.2 Key Investors in Microfluidics and Diagnostics

**Venture capital firms active in microfluidics/diagnostics:**
- Lux Capital -- invested in Atrandi Biosciences ($25M Series A for droplet microfluidics)
- Danaher Ventures -- strategic investor aligned with diagnostics portfolio
- Illumina Ventures -- life sciences tools focus
- ARCH Venture Partners -- early-stage life sciences
- Versant Ventures -- life sciences tools and diagnostics
- Vsquared Ventures -- deep tech, including microfluidics
- 8VC -- applied science and engineering
- KdT Ventures -- hard-tech life sciences

**Strategic / corporate investors:**
- Abbott, Roche, Siemens Healthineers, Hologic, Becton Dickinson
- These companies often invest as part of M&A pipeline scouting

### 3.3 What Investors Look For

**Technical de-risking:**
- Proof that the core microfluidic function works with real samples
- Evidence of material translatability (PDMS to production material)
- Clear manufacturing pathway with identified CDMO partners
- Freedom-to-operate (FTO) analysis and IP strategy

**Clinical/market validation:**
- Unmet clinical need with quantifiable market size
- Preliminary clinical data (even pilot-scale) with real patient samples
- Defined regulatory pathway with timeline and cost estimates
- Competitive differentiation beyond "we use microfluidics"

**Team:**
- Founder with deep domain expertise (microfluidics + application area)
- Regulatory and quality leadership (especially post-seed)
- Commercial leadership with industry relationships (Series B+)
- Advisory board with KOLs in the target clinical area

**Business model clarity:**
- Clear path to recurring revenue (consumables, tests, subscriptions)
- Unit economics that work at scale (cartridge COGS < 20-30% of selling price)
- Reimbursement strategy (if applicable): CPT code, coverage pathway
- Identified beachhead market with clear expansion plan

### 3.4 Grant Funding

**United States:**
- **NIH SBIR/STTR**: Historically the primary non-dilutive funding source for biomedical microfluidics startups. Phase I: up to $275K for feasibility; Phase II: up to $1.75M for development. Note: as of early 2026, the SBIR/STTR program's legislative authority expired on October 1, 2025, and reauthorization is pending in Congress. A 1-year extension bill (H.R. 5100) passed the House but awaits Senate action. Monitor sbir.gov for updates.
- **NSF SBIR/STTR**: Similar structure; relevant programs include Engineering of Biomedical Systems (EBMS) and Chemical, Bioengineering, Environmental, and Transport Systems (CBET).
- **BARDA/DARPA**: Mission-driven funding for diagnostics relevant to biodefense, pandemic preparedness, or military applications. Larger awards ($1M-$25M+) but specific requirements.
- **NIH RADx**: Rapid Acceleration of Diagnostics program (established during COVID-19); supported numerous microfluidic diagnostic platforms.

**European Union:**
- **Horizon Europe**: EIC Accelerator provides up to EUR 2.5M grant + EUR 15M equity for breakthrough technologies. Relevant calls in health, digital technologies.
- **Eurostars**: For R&D-performing SMEs collaborating across borders.
- **National programs**: Innovate UK, Bpifrance, BMBF (Germany) each have life sciences and medtech funding streams.

**Other:**
- **Canadian IRAP/NRC**: Industrial Research Assistance Program
- **Australian MRFF**: Medical Research Future Fund
- **Singapore A*STAR**: Active in microfluidics research and translation

---

## 4. Team Building

### 4.1 Key Roles by Stage

**Seed stage (5-10 people):**
- CEO/Founder -- vision, fundraising, business development
- CTO / Chief Scientist -- core technology, IP, scientific direction
- Microfluidics engineer (1-2) -- chip design, prototyping, testing
- Assay / application scientist (1-2) -- assay development, clinical sample testing
- Firmware / software engineer (1) -- instrument control, data acquisition

**Series A (10-25 people):**
- VP Engineering -- design for manufacturing, system integration
- Quality / Regulatory lead -- QMS implementation, regulatory strategy
- Manufacturing engineer -- process development, CDMO management
- Additional microfluidics engineers and assay scientists
- Clinical affairs manager -- study design, site management
- Operations / supply chain (1)

**Series B (25-75 people):**
- VP Quality / Regulatory Affairs -- QMS maturation, regulatory submissions
- VP Commercial / Sales -- go-to-market execution
- VP Manufacturing / Operations -- production scale-up
- Field application scientists -- customer support, KOL management
- Marketing and product management
- Finance and HR

### 4.2 Finding Microfluidics Talent

Microfluidics is a niche field, and experienced talent is scarce. Typical salary ranges for microfluidics engineers in the US are $80,000-$200,000 depending on experience and location.

**Where to recruit:**
- **Academic labs**: PhD and postdoc programs at leading microfluidics research institutions (Stanford, MIT, UC Berkeley, University of Michigan, ETH Zurich, KAIST, University of Tokyo, University of Twente)
- **Industry alumni**: Engineers from established microfluidics companies (10x Genomics, Standard BioTools/Fluidigm, Cepheid, Abbott, Danaher operating companies)
- **Adjacent fields**: MEMS engineers, semiconductor process engineers, polymer processing engineers -- these skills translate well
- **Job platforms**: LinkedIn (134+ microfluidics jobs typically listed), Glassdoor, specialized scientific job boards
- **Conferences**: MicroTAS (Chemical and Biological Microsystems Society), Lab-on-a-Chip World Congress, SLAS (Society for Laboratory Automation and Screening)

**Key skills to look for:**
- CAD/CAM for microfluidic design (AutoCAD, SolidWorks, L-Edit)
- Microfabrication (cleanroom processes, soft lithography, hot embossing)
- CFD simulation (COMSOL Multiphysics)
- Injection molding and thermoplastic processing knowledge
- Assay development (immunoassay, molecular diagnostics, cell-based)
- Surface chemistry and bonding techniques

### 4.3 Academic Collaboration Strategies

Academic partnerships are valuable throughout the commercialization journey:

**Early stage (TRL 1-4):**
- Sponsored research agreements (SRAs) with university labs
- Joint IP ownership or exclusive license to university IP
- Access to cleanroom facilities and specialized equipment
- Student internships as a talent pipeline
- Typical cost: $100K-$300K/year per lab partnership

**Mid stage (TRL 4-7):**
- Clinical collaborations for sample access and validation studies
- KOL engagement for clinical advisory roles
- Adjunct faculty appointments for company scientists (credibility)
- Grant co-applications (company + university as subcontractor)

**Pitfalls to avoid:**
- Unclear IP ownership (negotiate upfront, get it in writing)
- Academic timelines that do not match commercial urgency
- Publication restrictions that conflict with patent filing strategy (file provisional patent before any public disclosure)
- Over-reliance on a single academic partner

### 4.4 Contract Research Organizations (CROs) and CDMOs

**Microfluidic chip design and prototyping CROs:**
- Micralyne (Teledyne MEMS) -- custom chip development
- ALine Inc. -- rapid prototyping, design for manufacturing
- Dolomite Microfluidics -- design services and components
- MiniFAB (Anatoli) -- end-to-end microfluidic device development
- microfluidic ChipShop -- prototyping and low-volume production

**Injection molding CDMOs for microfluidics:**
- Stratec (formerly STRATEC Consumables) -- high-volume microfluidic cartridge production
- Yole Group companies -- various production services
- Nolato -- precision injection molding for medical devices
- Gerresheimer -- specialty plastics for diagnostics

**Assay development CROs:**
- BioFluidix -- microfluidic assay development
- Contract labs specializing in IVD assay development

**When to use CROs/CDMOs:**
- Lack of in-house expertise in a specific domain
- Need for specialized equipment (e.g., injection molding machines, cleanrooms)
- Bridging capacity before building internal manufacturing
- Regulatory requirement for validated manufacturing processes
- Cost-effective alternative to building full internal capabilities at early stage

---

## 5. Go-to-Market Strategy

### 5.1 Clinical Validation Pathway

Clinical validation is the gating step for any diagnostic microfluidic product.

**Study design considerations:**
- Prospective vs. retrospective sample testing
- Sample size powered for intended claims (sensitivity, specificity)
- Comparison to reference/gold-standard method
- Multi-site studies strengthen regulatory submissions
- IRB/ethics committee approval required
- Informed consent for prospective collection

**Regulatory pathways (US FDA):**

| Pathway | When to Use | Timeline | Cost |
|---|---|---|---|
| 510(k) | Substantially equivalent to a predicate device | 3-12 months | $50K-$500K |
| De Novo | Novel device, low-to-moderate risk, no predicate | 6-18 months | $200K-$1M |
| PMA | High-risk device (Class III) | 1-3 years | $1M-$10M+ |
| LDT (CLIA) | Laboratory-developed test (run in own lab) | 2-6 months | $50K-$200K |
| EUA | Emergency use (pandemic, biodefense) | Weeks-months | Variable |

The De Novo pathway is increasingly used for novel microfluidic diagnostics (25.9% of De Novo submissions are for IVDs). It creates a new classification that can serve as a predicate for future 510(k) submissions.

**EU regulatory pathway:**
- IVDR (In Vitro Diagnostic Regulation, EU 2017/746) replaced the IVD Directive in May 2022
- Risk-based classification (Class A through D)
- Notified Body involvement required for Class B and above
- Performance evaluation studies required
- Timeline: 12-24 months for Class B/C; longer for Class D
- Key notified bodies: BSI, TUV, DEKRA

### 5.2 Key Opinion Leader (KOL) Engagement

KOLs are critical for clinical validation, market access, and commercial adoption.

**KOL engagement stages:**
1. **Discovery (TRL 3-4)**: Identify 3-5 KOLs in target clinical area; informal conversations about unmet needs
2. **Advisory (TRL 4-6)**: Formal scientific advisory board (SAB); compensated consulting agreements; input on assay design and clinical study design
3. **Validation (TRL 6-7)**: Beta site hosting; clinical study investigators; conference presentations and publications
4. **Advocacy (TRL 8-9)**: Early adopters; reference sites for new customers; peer-to-peer education programs

**Compensation models:**
- Consulting fees ($2,000-$10,000/day depending on prominence)
- Equity or stock options (especially for SAB members at startups)
- Research funding support
- Authorship on publications

**Finding KOLs:**
- PubMed analysis of publication leaders in the target clinical area
- Conference speaker rosters (AACC, ECCMID, ASM, AMP)
- Professional society leadership
- Hospital/health system innovation committees

### 5.3 Distribution Strategy: Distributor vs. Direct Sales

**Direct sales advantages:**
- Higher margins (no distributor markup)
- Direct customer relationship and feedback
- Control over messaging and positioning
- Better for complex, high-value instrument sales
- Preferred for US market where margins justify dedicated sales team

**Direct sales disadvantages:**
- Expensive to build (sales reps cost $150K-$300K fully loaded)
- Slow to scale geographically
- Requires field service and application support infrastructure

**Distributor advantages:**
- Rapid geographic coverage
- Established customer relationships
- Lower fixed cost (commission-based: typically 20-40% of selling price)
- Local regulatory and logistical knowledge
- Essential for international markets (especially initially)

**Distributor disadvantages:**
- Lower margins
- Less control over customer relationship
- Distributor may prioritize larger product lines
- Training and motivation challenges

**Recommended approach by stage:**
- **Launch**: Direct sales in primary market (US or home market); 3-5 dedicated sales/application specialists
- **Growth**: Add distributors for secondary markets; retain direct for key accounts
- **Scale**: Hybrid model -- direct in top markets, distributor network elsewhere

### 5.4 Geographic Launch Strategy

**Phase 1: United States (Year 1-2)**
- Largest single IVD market (~40% of global)
- FDA clearance/approval is the most recognized regulatory credential
- Highest reimbursement rates
- Concentrated customer base (large reference labs, health systems)
- Launch with 3-5 beta sites, expand to 20-50 sites in first year
- Focus: top 20 metropolitan areas, academic medical centers

**Phase 2: European Union (Year 2-3)**
- Second largest IVD market (~25% of global)
- IVDR compliance required (significant regulatory investment)
- Fragmented market (multiple languages, health systems, reimbursement schemes)
- Distributor partnerships essential
- Consider UK separately (UKCA marking post-Brexit)
- Priority countries: Germany, France, UK, Italy, Spain, Nordics

**Phase 3: Rest of World (Year 3-5)**
- **China**: Large and growing market; NMPA approval required; local partner or JV typically needed
- **Japan**: High-value market; PMDA approval; preference for validated, established technologies
- **Canada**: Health Canada approval; often uses FDA clearance as basis
- **Australia**: TGA approval; relatively straightforward if FDA-cleared
- **Middle East / Africa**: WHO prequalification important for global health applications
- **Latin America**: ANVISA (Brazil) is the key regulatory body; market access through distributors

### 5.5 Pricing Strategy

**Cost-plus pricing:**
- Calculate fully loaded COGS (materials, labor, manufacturing overhead, yield loss)
- Apply target gross margin (65-80% for consumables; 40-60% for instruments)
- Validate against competitive pricing and willingness-to-pay research

**Value-based pricing:**
- Calculate value delivered vs. current standard of care
- Faster time to result, reduced labor, improved outcomes
- Payer willingness-to-pay analysis (especially for reimbursed tests)
- Example: if a microfluidic test saves $500 in downstream costs, pricing at $50-$100 captures 10-20% of value created

**Reimbursement (for clinical diagnostics):**
- Identify applicable CPT code(s)
- Research Medicare reimbursement rate (Clinical Lab Fee Schedule)
- Private payer coverage decisions
- Health technology assessment (for EU markets)
- Consider: if no CPT code exists, a new code application to AMA takes 12-18 months

### 5.6 Launch Checklist

Pre-launch (6-12 months before commercial availability):
- [ ] Regulatory clearance/approval in primary market
- [ ] Manufacturing validated and at required capacity
- [ ] Quality management system (ISO 13485) certified
- [ ] Supply chain qualified (dual-source critical components)
- [ ] Sales team hired and trained
- [ ] Marketing materials developed (website, collateral, conference presence)
- [ ] KOL reference sites generating data and publications
- [ ] Customer service and field support infrastructure in place
- [ ] Pricing and reimbursement strategy finalized
- [ ] Distribution agreements signed for non-direct markets
- [ ] Post-market surveillance plan in place
- [ ] Complaint handling and adverse event reporting system operational

Launch (first 90 days):
- [ ] Announce at major industry conference
- [ ] Press release and media engagement
- [ ] First commercial orders shipped
- [ ] KOL presentations at conferences / webinars
- [ ] Monitor field performance closely (daily failure rate tracking)
- [ ] Rapid response team for any field issues

---

## 6. Common Commercialization Pitfalls

### 6.1 Technical Pitfalls

1. **Underestimating PDMS-to-thermoplastic translation**: Budget 12-18 months and $500K-$1M for this transition. Assay performance will change; plan for re-optimization.
2. **Reagent stability**: Liquid reagents on a microfluidic chip have limited shelf life. Lyophilization, bead drying, or blister pack integration adds complexity but is essential for commercial viability.
3. **Manufacturing yield**: Early injection molding runs commonly achieve 60-70% yield. Budget for yield improvement programs; target >95% at commercial scale.
4. **Bonding failures**: The #1 manufacturing defect in microfluidic devices. Invest heavily in bonding process development and quality control (leak testing every unit).
5. **Sample preparation**: The "dirty secret" of microfluidics -- most devices work beautifully with buffer but struggle with real clinical samples. Integrate sample prep early.

### 6.2 Business Pitfalls

1. **Technology in search of a problem**: The most common failure mode. Start with a clear clinical or industrial unmet need, not with a cool microfluidic technology.
2. **Ignoring reimbursement**: A clinically validated, FDA-cleared test with no reimbursement pathway will not sell. Investigate reimbursement before Series A.
3. **Premature scaling**: Building manufacturing capacity before clinical validation and regulatory clearance wastes capital. Use CDMOs for pilot production.
4. **Single-application platform**: Investors want to see platform potential. Design for menu expansion from the beginning.
5. **Underestimating regulatory timelines and costs**: FDA De Novo submissions currently average 12-15 months; IVDR compliance can take 18-24 months. Budget accordingly.

### 6.3 Team Pitfalls

1. **All scientists, no operators**: Technical founders must hire business, regulatory, and quality leaders early. These hires feel premature but are essential.
2. **Delaying manufacturing expertise**: Hire or contract manufacturing engineers at TRL 4, not TRL 7. DFM decisions made early save millions later.
3. **KOL neglect**: Start KOL engagement at TRL 3-4, not TRL 7-8. By the time you need clinical data, you need established KOL relationships.

---

## 7. Key Metrics and Milestones by Stage

| Metric | Seed | Series A | Series B | Commercial |
|---|---|---|---|---|
| TRL | 3-4 | 4-6 | 6-8 | 8-9 |
| Chip manufacturing yield | N/A (PDMS) | >70% (pilot) | >90% (production) | >95% |
| Assay CV (%) | <20% | <15% | <10% | <10% |
| Reagent shelf life | Weeks | 3-6 months | 12+ months | 18-24 months |
| Clinical samples tested | 10-50 | 50-200 | 200-1000+ | Ongoing |
| Regulatory status | Pre-submission | Pre-sub meeting | Submission filed | Cleared/approved |
| Team size | 3-8 | 10-25 | 25-75 | 75+ |
| Revenue | $0 | $0-$500K (grants/NRE) | $0-$2M (early sales) | $5M+ |

---

## 8. Resources and References

### Industry Conferences
- **MicroTAS** (Micro Total Analysis Systems): Premier academic microfluidics conference
- **SLAS** (Society for Laboratory Automation and Screening): Industry-focused
- **AACC** (American Association for Clinical Chemistry): Clinical diagnostics
- **Lab-on-a-Chip World Congress**: Applied microfluidics
- **MD&M** (Medical Design & Manufacturing): Medical device manufacturing
- **MEDICA/COMPAMED**: Largest medical device trade show (Dusseldorf)

### Industry Organizations
- **CBMS** (Chemical and Biological Microsystems Society): Organizes MicroTAS
- **IVD Industry Connectivity Consortium (IICC)**: IVD standards
- **AdvaMed**: US medical device industry association
- **MedTech Europe**: EU medical device industry association

### Regulatory Guidance
- FDA: "Recommended Content and Format of a De Novo Request"
- FDA: "In Vitro Diagnostic Products: Guidance for Industry and FDA Staff"
- EU IVDR (2017/746): Full text available at EUR-Lex
- ISO 13485: Quality management systems for medical devices
- ISO 14971: Risk management for medical devices
- IEC 62304: Medical device software lifecycle processes

### Market Reports
- MarketsandMarkets: Microfluidics Market (forecast to $37.2B by 2030)
- Grand View Research: Microfluidics Market
- Yole Developpement: Microfluidic technologies and applications

### Key Publications on Commercialization
- "Perspectives in translating microfluidic devices from laboratory prototyping into scale-up production" (Biomicrofluidics, 2022)
- "Transformation gap from research findings to large-scale commercialized products in microfluidic field" (ScienceDirect, 2024)

---

*This document provides a framework for commercializing microfluidic products. Specific timelines, costs, and strategies will vary based on application area (diagnostics, drug discovery, industrial), regulatory classification, geographic focus, and competitive landscape. Engage experienced regulatory, quality, and commercial advisors early in the process.*

Sources:
- [Technology Readiness Levels - NASA](https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/)
- [Medical Countermeasures TRLs for Diagnostics and Medical Devices](https://medicalcountermeasures.gov/trl/trls-for-medical-devices)
- [Microfluidics Market Size & Growth Forecast to 2030 - MarketsandMarkets](https://www.marketsandmarkets.com/Market-Reports/microfluidics-market-1305.html)
- [Perspectives in translating microfluidic devices - Biomicrofluidics](https://pubs.aip.org/aip/bmf/article/16/2/021301/2835411/Perspectives-in-translating-microfluidic-devices)
- [Transformation gap in microfluidic field - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2590006424004344)
- [Transformation gap in microfluidic field - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11647665/)
- [PDMS for Microfluidics: Limitations and Alternatives - Micronit](https://micronit.com/expertise/manufacturing-expertise/pdms-for-microfluidics)
- [Microfluidics: Evolution from PDMS to Thermoplastics - Potomac Laser](https://www.potomac-laser.com/blog/microfluidics-the-evolution-from-pdms-to-thermoplastics-for-enhanced-scalability-and-cost-effectiveness/)
- [Considerations When Switching from PDMS to Thermoplastic - Edge Precision](https://www.edgeprecision.com/news-and-insights/considerations-when-switching-from-pdms-to-thermoplastic-microfluidics)
- [Razor and Blade Business Model - BusinessModelNavigator](https://businessmodelnavigator.com/pattern?id=39)
- [Top 10 Largest Microfluidics Companies in 2025](https://www.polarismarketresearch.com/blog/top-10-largest-microfluidics-companies-in-2025)
- [Atrandi Biosciences raises $25M Series A](https://www.vestbee.com/insights/articles/atrandi-biosciences-raises-25-m)
- [Best Microfluidics Startups 2026 - SeedTable](https://www.seedtable.com/best-microfluidics-startups)
- [SBIR/STTR Reauthorization 2026](https://fundinglandscape.com/answers/sbir-sttr-reauthorization-2026)
- [NIH SBIR/STTR Notice NOT-OD-26-006](https://grants.nih.gov/grants/guide/notice-files/NOT-OD-26-006.html)
- [FDA De Novo Classification Request](https://www.fda.gov/medical-devices/premarket-submissions-selecting-and-preparing-correct-submission/de-novo-classification-request)
- [510(k) vs De Novo FDA Pathways](https://www.doclabinc.com/blog/510k-vs-de-novo-fda-pathways/)
- [De Novo pathway and innovation incentives - Nature Digital Medicine](https://www.nature.com/articles/s41746-024-01021-y)
- [Startup mFluiDx for Point-of-Care MDx - GenomeWeb](https://www.genomeweb.com/infectious-disease/startup-mfluidx-developing-integrated-microfluidic-point-care-infectious-disease)
- [Microfluidic Chip Case Study - Fast Radius](https://fastradius.com/expertise/case-studies/microfluidic-chip/)
