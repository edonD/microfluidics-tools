# Practical Guide: Setting Up a Microfluidics Lab from Scratch

> A comprehensive guide covering space requirements, equipment procurement at every budget
> level, vendor negotiation strategies, cleanroom access, and lab management best practices.

---

## Table of Contents

1. [Lab Space Requirements](#1-lab-space-requirements)
2. [Equipment Shopping List by Budget](#2-equipment-shopping-list-by-budget)
3. [Vendor Negotiation Tips](#3-vendor-negotiation-tips)
4. [Setting Up Cleanroom Access](#4-setting-up-cleanroom-access)
5. [Lab Management Best Practices](#5-lab-management-best-practices)

---

## 1. Lab Space Requirements

### 1.1 Minimum Bench and Floor Space

A functional microfluidics lab can operate in a surprisingly modest footprint, but planning
the layout carefully from day one prevents expensive rearrangements later.

| Zone | Minimum Area | Purpose |
|------|-------------|---------|
| Wet bench | 8-12 linear ft (2.4-3.6 m) | PDMS mixing, bonding, chemical handling |
| Dry bench / optics | 6-8 linear ft (1.8-2.4 m) | Microscope, flow control, imaging |
| Fume hood | 1 standard 4-6 ft hood | Solvent work, SU-8 processing, piranha cleaning |
| Equipment rack | ~15 sq ft (1.4 sq m) | Pumps, pressure controllers, power supplies |
| Storage | ~30 sq ft (2.8 sq m) | Chemicals, consumables, wafer storage |
| Desk/analysis area | ~40 sq ft (3.7 sq m) | Data analysis, design work |
| **Total minimum** | **~200-300 sq ft (18-28 sq m)** | **Functional single-researcher lab** |

**Key layout principles:**
- Keep the microscope/imaging station away from doors and high-traffic zones (vibration)
- Place the fume hood near an exterior wall for ductwork access
- Separate wet chemistry from sensitive optics/electronics
- Plan for expansion: cable trays, extra electrical circuits, additional gas drops

### 1.2 Utilities

**Compressed air / nitrogen:**
- Pressure-driven flow control requires clean, dry compressed air (60-100 psi at the regulator)
- Nitrogen for inerting, drying substrates, and operating plasma cleaners
- Budget for a small oil-free compressor (~$500-1,500) if building-supplied air is unavailable
- Nitrogen: cylinder with regulator ($200-400 initial, ~$50-80 per refill) or building supply

**Vacuum:**
- Needed for degassing PDMS, spin coating, and substrate handling
- A small diaphragm vacuum pump ($300-800) is adequate for most microfluidics work
- Building vacuum (if available) saves bench space but is often unreliable

**DI water:**
- Essential for cleaning substrates, rinsing devices, and preparing solutions
- Minimum: a benchtop DI water system (Millipore Milli-Q or equivalent, ~$5,000-8,000 new)
- Alternative for tight budgets: purchase DI water in carboys from a chemical supplier

**Electrical:**
- Plan for 20A circuits minimum; plasma cleaners and ovens can pull significant current
- At least 2-3 dedicated circuits for equipment to avoid tripping shared breakers
- Uninterruptible power supply (UPS) recommended for microscope computers and controllers

### 1.3 Environmental Controls

**Temperature:**
- PDMS curing is temperature-sensitive; a lab oven (65-80 C typical) is essential
- Ambient temperature stability (+/- 2 C) improves reproducibility of flow experiments
- Standard HVAC with thermostat control is usually adequate

**Vibration isolation:**
- Microscopes (especially fluorescence and confocal) are sensitive to building vibration
- Options from least to most expensive:
  - Sorbothane pads under the microscope ($30-50)
  - Passive vibration isolation table ($500-2,000)
  - Active vibration isolation optical table ($5,000-15,000)
- Avoid upper floors of buildings near elevators, HVAC equipment, or heavy foot traffic
- If high-resolution imaging is critical, invest in at least a passive isolation table

**Humidity:**
- Typically not critical for standard PDMS work
- Can affect photolithography (if done in-lab) and surface treatments
- A simple hygrometer ($20) to monitor is sufficient for most labs

**Air cleanliness:**
- Full cleanroom not required for most microfluidics assembly
- A laminar flow hood or clean bench ($2,000-5,000) is valuable for dust-sensitive bonding steps
- HEPA-filtered portable units work well as a low-cost alternative

---

## 2. Equipment Shopping List by Budget

### 2.1 Budget Tier: $5,000-15,000 (Bootstrap / Student Lab)

This tier gets you started with functional microfluidics using DIY approaches and basic
commercial equipment. Ideal for proof-of-concept work and learning.

| Item | Est. Cost | Notes |
|------|-----------|-------|
| **Flow Control** | | |
| DIY syringe pump (open-source, Arduino-based) | $100-200 | Multiple open-source designs available; ~$110-120 per pump |
| Basic commercial syringe pump (e.g., New Era NE-300) | $500-800 | Single-channel infusion; good entry point |
| Syringes (various sizes) + tubing | $100-200 | Stock 1 mL, 5 mL, 10 mL; Tygon and PEEK tubing |
| **Microscopy** | | |
| Basic stereo microscope | $500-1,500 | For device inspection and alignment |
| USB microscope camera | $200-500 | Adequate for time-lapse and basic imaging |
| **Fabrication** | | |
| PDMS kit (Sylgard 184, multiple kits) | $150-300 | 10:1 base-to-curing-agent ratio |
| Plasma cleaner (basic, e.g., Harrick PDC-32G) | $2,000-3,500 | Essential for PDMS-glass bonding |
| Lab oven or hot plate | $200-500 | For PDMS curing (65-80 C) |
| Spin coater (basic or DIY) | $500-2,000 | Can build from a computer fan motor for ~$50 |
| **Consumables & Supplies** | | |
| Glass slides, coverslips, petri dishes | $100-200 | |
| Biopsy punches (various sizes) | $50-100 | For inlet/outlet holes in PDMS |
| Connectors, fittings (Luer, barbed) | $100-200 | |
| **General** | | |
| Analytical balance | $200-500 | For weighing PDMS components |
| Vacuum desiccator + hand pump | $100-200 | For degassing PDMS |
| **Total** | **$5,000-10,000** | |

**What to buy first (priority order):**
1. Syringe pump (even a DIY one) and tubing/connectors
2. Plasma cleaner (hard to substitute; critical for bonding)
3. PDMS supplies and basic fabrication tools
4. Microscope for device inspection

**What can wait:**
- Spin coater (can pour PDMS without one initially)
- Fancy microscope camera (smartphone adapter works in a pinch)
- Automated pressure controllers

### 2.2 Mid Tier: $30,000-80,000 (Established Research Group)

This tier enables publication-quality work with reliable, calibrated equipment.

| Item | Est. Cost | Notes |
|------|-----------|-------|
| **Flow Control** | | |
| Commercial syringe pump, dual-channel | $1,500-3,000 | e.g., Harvard Apparatus PHD 2000, Chemyx Fusion |
| Pressure controller (e.g., Elveflow OB1, Fluigent MFCS) | $5,000-8,000 | Single or dual channel; far better flow stability than syringe pumps |
| Flow sensors | $2,000-4,000 | Real-time flow rate measurement |
| **Microscopy** | | |
| Inverted fluorescence microscope | $15,000-30,000 | e.g., Nikon Eclipse Ti2, Olympus IX73; buy used if possible |
| Scientific camera (sCMOS or CCD) | $5,000-15,000 | e.g., Hamamatsu ORCA, Andor Zyla |
| Objective lenses (10x, 20x, 40x) | $2,000-5,000 | Plan fluorite or plan apochromat |
| **Fabrication** | | |
| Plasma cleaner (higher-end) | $3,000-6,000 | More consistent treatments |
| Spin coater (programmable) | $2,000-5,000 | Precise thickness control for resist and thin PDMS |
| UV exposure system (for in-lab photolithography) | $3,000-8,000 | If you want to make your own masters |
| Profilometer or contact angle goniometer | $5,000-15,000 | For surface characterization |
| **General** | | |
| Laminar flow hood / clean bench | $2,000-5,000 | Dust-free bonding |
| Lab oven (forced convection) | $500-1,500 | Better temperature uniformity |
| DI water system | $5,000-8,000 | e.g., Millipore Milli-Q |
| **Total** | **$45,000-80,000** | |

**What to buy first:**
1. Good microscope with fluorescence (this unlocks most assay types)
2. Pressure controller (dramatically improves flow stability over syringe pumps)
3. Clean bench for reliable bonding

### 2.3 Premium Tier: $150,000-300,000 (Full Capability Lab)

This tier provides end-to-end capability from device design through high-end characterization.

| Item | Est. Cost | Notes |
|------|-----------|-------|
| **Flow Control** | | |
| Multi-channel pressure controller | $15,000-25,000 | 4-8 channels, integrated flow sensing |
| Automated valve manifolds | $5,000-10,000 | For complex protocols |
| Temperature-controlled chip holders | $3,000-8,000 | For cell culture on-chip |
| **Microscopy** | | |
| Research-grade inverted microscope | $40,000-80,000 | Motorized stage, multiple filter sets |
| High-speed camera | $15,000-40,000 | For droplet generation, fast dynamics |
| Confocal module or add-on | $30,000-60,000 | For 3D imaging |
| **Fabrication** | | |
| Mask aligner (entry-level) | $30,000-60,000 | e.g., SUSS MJB4; for multi-layer photolithography |
| Reactive ion etcher (tabletop) | $20,000-40,000 | For glass/silicon etching |
| 3D printer for microfluidics (high-res) | $5,000-15,000 | e.g., Formlabs Form 3+, Asiga |
| **Characterization** | | |
| Surface profiler (stylus or optical) | $15,000-40,000 | Dektak, Zygo |
| Contact angle measurement system | $10,000-20,000 | Surface energy characterization |
| **Total** | **$190,000-400,000** | |

**When to invest at this level:**
- When you have a dedicated microfluidics program (not just one project)
- When shared facility wait times or travel costs justify dedicated equipment
- When you need 24/7 access for time-sensitive experiments (e.g., cell culture)

### 2.4 Decision Framework: Buy vs. Use Shared Facility

| Factor | Buy Your Own | Use Shared Facility |
|--------|-------------|-------------------|
| Usage >20 hrs/month | Likely cost-effective | Fees add up quickly |
| Usage <5 hrs/month | Wasteful | Much cheaper |
| Need 24/7 access | Required | Often limited hours |
| Specialized training needed | You maintain expertise | Facility staff can help |
| Maintenance burden | On you | On the facility |
| Publication timeline pressure | No waiting | May face queues |

---

## 3. Vendor Negotiation Tips

### 3.1 Academic Discounts

Most scientific equipment vendors offer significant academic pricing, but you often have to
ask explicitly:

- **Typical discounts:** 30-60% off list price for academic/nonprofit customers
- **How to access:** Provide a purchase order on university letterhead; some vendors require
  a valid .edu email or institutional verification
- **Best timing:** End of fiscal quarters (March, June, September, December) when sales
  representatives are trying to hit targets
- **Bundle deals:** Buying a microscope body + objectives + camera as a package yields better
  discounts than purchasing individually
- **Grant leverage:** Mention specific grant funding and budget constraints; vendors would
  rather sell at a discount than lose the sale entirely

### 3.2 Demo and Loaner Programs

- Many instrument companies (Nikon, Olympus, Zeiss, Elveflow, Fluigent) offer demo units
  for 1-4 week evaluation periods at no cost
- **Strategy:** Request demos from 2-3 competing vendors; use each demo period to generate
  preliminary data while evaluating the equipment
- **After the demo:** Use your experience with competing products as negotiation leverage
- Some vendors offer extended demo periods for labs writing grant applications that include
  their equipment

### 3.3 Buying Used Equipment

Used equipment can save 40-70% over new prices. Key sources:

| Source | Best For | Tips |
|--------|----------|------|
| [LabX](https://www.labx.com/) | Broad selection of lab instruments | LabX has been a marketplace leader since 1995; verify seller reputation |
| [BioSurplus](https://www.biosurplus.com/) | High-end biotech equipment | Communicate your needs and budget openly; they often negotiate |
| eBay | Commodity items (pumps, power supplies) | Risky for precision instruments; good for accessories |
| [Surplus Solutions (SSLLC)](https://ssllc.com/) | Auction-based purchasing | Can get excellent deals; requires patience |
| University surplus stores | Local bargains | Check your own and neighboring universities |
| Lab closures / PI retirements | Complete setups at steep discounts | Network through department contacts |
| [Excedr](https://www.excedr.com/) | Equipment leasing alternative | Lease-to-own programs for expensive instruments |

**Due diligence for used equipment:**
- Request calibration records and maintenance history
- Ask about the reason for sale (lab closure vs. malfunction)
- Factor in shipping costs for heavy items (microscopes, ovens)
- Budget for professional installation and recalibration ($500-2,000 for complex instruments)
- Check if the manufacturer will still service the model (end-of-life support)

### 3.4 Service Contracts vs. Pay-Per-Incident

| Approach | Pros | Cons | Best When |
|----------|------|------|-----------|
| Multi-year service contract | Predictable costs; priority service; includes preventive maintenance | Expensive ($3,000-10,000/yr for microscopes); may pay for service you never use | Equipment is mission-critical; downtime is very costly |
| Pay-per-incident | Only pay when something breaks; lower cost if equipment is reliable | Unpredictable costs; longer wait times; no preventive maintenance included | Equipment is relatively new; you have backup instruments |
| Self-maintenance | Lowest cost; builds in-house expertise | Risk of voiding warranty; requires training | Simple equipment (pumps, hot plates); expired warranty |

**Rule of thumb:** Service contracts are worth it for instruments costing >$50,000 that are in
daily use. For everything else, pay-per-incident is usually more cost-effective.

### 3.5 Other Cost-Saving Strategies

- **Consortium purchasing:** Join institutional buying groups (e.g., Biocom members get
  preferred vendor discounts)
- **Repeat business leverage:** Vendors track customer history; consolidating purchases with
  fewer vendors builds relationships that yield better pricing
- **Trade-in programs:** Some vendors offer credit for trading in old equipment when upgrading
- **Grant equipment supplements:** NSF and NIH sometimes allow equipment supplements to
  existing grants; check with your program officer
- **Startup packages:** New faculty should negotiate aggressively for equipment in their
  startup package, as this is the best funding you will ever receive (no overhead, no reporting)

---

## 4. Setting Up Cleanroom Access

### 4.1 When You Actually Need a Cleanroom

**You NEED a cleanroom for:**
- Photolithography to create SU-8 masters (feature sizes <50 um)
- Thin-film deposition (metal sputtering, evaporation)
- Reactive ion etching of glass or silicon
- Multi-layer aligned lithography
- Any process involving photoresist that is dust-sensitive

**You DON'T need a cleanroom for:**
- PDMS casting from existing masters (a clean bench is sufficient)
- PDMS-glass bonding with a benchtop plasma cleaner
- 3D-printed microfluidic devices
- Laser-cut or CNC-milled devices
- Xurography (craft-cutter) based devices
- Hot embossing with existing molds
- Devices with feature sizes >100 um (a homebrew photolithography setup on the bench can
  achieve ~85 um resolution without a cleanroom)

**Bottom line:** Many microfluidics researchers use cleanroom access only for master
fabrication (a few hours per month) and do everything else on the bench.

### 4.2 University Shared Facilities

Most research universities operate shared micro/nanofabrication facilities open to all
campus researchers and often to external users.

**Typical fee structures:**

| User Type | Hourly Rate | Monthly Access Fee | Notes |
|-----------|-------------|-------------------|-------|
| Internal (same university) | $25-75/hr | $0-200/month | Varies by tool and facility |
| External academic | $50-200/hr | $100-500/month | Often 2-3x internal rates |
| Industry user | $100-400/hr | $200-1,000/month | Highest tier; includes IP protections |

**Examples of well-known shared facilities:**
- Princeton MNFC: Requires safety training + 20 hours supervised time before independent access
- UChicago Pritzker Nanofab: One-time fee covers all training, garments, PPE, and admin
- Yale Cleanroom: Transitioning to hard-cap fee model in FY26
- Georgia Tech IEN: Multiple cleanroom spaces with graduated access levels
- UCSD Nano3: Provides dedicated microfluidics device labs alongside cleanroom

**Getting started at a shared facility:**
1. Contact the facility manager; explain your project and expected tool usage
2. Complete required safety training (typically 4-16 hours of classes)
3. Complete tool-specific training (1-4 hours per tool, with a staff member)
4. Pass qualification runs before independent access is granted
5. Budget 2-4 weeks from first contact to independent access

### 4.3 National and Regional Networks

**United States: NNCI (National Nanotechnology Coordinated Infrastructure)**

The [NNCI](https://nnci.net/) is a network of 16 sites across the US, all open to external
users from academia and industry. Key features:
- Facilities staffed by ~24+ professionals (technicians, engineers, admin) per site
- Supports academic research and commercial product/process development
- Hands-on introductory training courses in microfabrication and microfluidics
- Some sites offer remote fabrication services (you send designs, they fabricate)
- Contact individual sites for specific rate cards; most offer academic pricing

Notable NNCI sites for microfluidics:
- Cornell CNF (Cornell NanoScale Facility)
- Stanford SNF (Stanford Nanofabrication Facility)
- Georgia Tech IEN
- University of Michigan LNF
- UCSD Nano3

**Canada: CMC Microsystems**

[CMC Microsystems](https://www.cmc.ca/) provides access to design tools, manufacturing
technologies, and engineering support:
- **MicroFAB Access program:** Reimburses 80% of eligible fabrication costs, up to $4,000
  for graduate students or postdoctoral fellows at Canadian universities
- Faculty supervisor must hold a CMC Research Subscription
- Applications accepted monthly (deadline: 10th of each month)
- 4-month fabrication window after approval
- Also offers professional microfluidics training courses (3-day crash course format)

**Europe:**
- Europractice (multi-project wafer runs)
- National cleanroom networks in France (RENATECH), Germany (Helmholtz Nano Facility),
  Netherlands (NanoLabNL), and UK (Henry Royce Institute)

### 4.4 Cost Optimization for Cleanroom Use

- **Batch your work:** Prepare everything at the bench and enter the cleanroom with a clear
  plan; minimize "thinking time" at $50-200/hr
- **Share masters:** One photolithography session can produce a master mold that yields
  hundreds of PDMS replicas at the bench
- **Use multi-project runs:** Some facilities batch multiple users' designs onto a single
  wafer, splitting costs
- **Off-peak hours:** Some facilities offer reduced rates for evening/weekend access
- **Train students efficiently:** Have experienced users train new ones to minimize expensive
  supervised cleanroom time

---

## 5. Lab Management Best Practices

### 5.1 Inventory Management for Consumables

**Critical consumables to always have in stock:**

| Category | Items | Min. Stock Level |
|----------|-------|-----------------|
| PDMS | Sylgard 184 kits | 2 kits |
| Substrates | Glass slides (75x25 mm), coverslips | 2 boxes each |
| Tubing | Tygon (various ID), PEEK tubing | 5 m per size |
| Connectors | Luer fittings, barbed connectors, PDMS plugs | 20 of each type |
| Punches | Biopsy punches (0.75, 1.0, 1.5 mm) | 5 per size |
| Syringes | 1 mL, 5 mL, 10 mL, 20 mL | 10 per size |
| Chemicals | Isopropanol, acetone, ethanol | 1 L each |
| Gloves | Nitrile, powder-free | 2 boxes |
| Tape | Scotch tape (for dust removal), Kapton tape | 2 rolls each |

**Inventory management system:**
- Maintain a shared spreadsheet or use LIMS software (Quartzy is free for academics)
- Set reorder points: when stock drops below minimum, trigger a purchase order
- Assign one person per month as "inventory manager" on a rotating basis
- Conduct a full physical inventory quarterly
- Track lot numbers for PDMS and critical chemicals (batch-to-batch variation matters)

### 5.2 Equipment Maintenance Schedules

| Equipment | Daily | Weekly | Monthly | Annually |
|-----------|-------|--------|---------|----------|
| Syringe pumps | Wipe down; check for leaks | Inspect syringes for wear | Calibrate flow rates | Full service / motor check |
| Pressure controller | Check for leaks | Verify calibration | Clean pressure lines | Manufacturer calibration |
| Microscope | Clean objectives after use; cover when not in use | Check illumination alignment | Clean condenser; check filters | Professional alignment service |
| Plasma cleaner | Wipe chamber | Check vacuum level | Clean electrodes | Replace vacuum pump oil; check RF generator |
| Spin coater | Clean chuck and bowl | Check vacuum hold | Calibrate RPM | Belt/motor inspection |
| Fume hood | Verify airflow indicator | Wipe down surfaces | Check sash cord/cable | Annual certification (required by EHS) |
| Oven | Check temperature setting | Verify with external thermometer | Clean interior | Calibrate thermocouple |

**Maintenance log:** Keep a bound notebook or digital log at each major instrument. Record
date, user, observation, and any corrective action taken.

### 5.3 Standard Operating Procedures (SOPs)

Every lab should develop and maintain SOPs for its key processes. A good SOP includes:

**Essential SOPs for a microfluidics lab:**
1. PDMS mixing and curing
2. Plasma treatment and PDMS-glass bonding
3. Device priming and flow setup
4. Syringe pump operation
5. Pressure controller operation
6. Microscope startup and shutdown
7. Chemical waste disposal
8. Emergency procedures (spills, equipment failure)

**SOP format template:**
```
TITLE: [Process Name]
VERSION: [X.Y]          DATE: [YYYY-MM-DD]
AUTHOR: [Name]          APPROVED BY: [PI Name]

1. PURPOSE
   Brief description of what this SOP covers and why.

2. SCOPE
   What equipment/processes this applies to.

3. SAFETY
   PPE required, hazards, emergency procedures.

4. MATERIALS AND EQUIPMENT
   Complete list with part numbers and locations.

5. PROCEDURE
   Step-by-step instructions with parameters.
   Include photos or diagrams where helpful.

6. TROUBLESHOOTING
   Common problems and solutions.

7. REVISION HISTORY
   Date, author, description of changes.
```

**SOP management tips:**
- Store SOPs in a shared location (Google Drive, lab wiki, or binder near the instrument)
- Review and update all SOPs at least annually
- Have new lab members read relevant SOPs before using equipment
- Include a sign-off sheet for training verification

### 5.4 Lab Notebook Best Practices

**Physical notebooks:**
- Use bound, numbered-page notebooks (not loose-leaf)
- Write in permanent ink; never tear out pages
- Date every entry; sign at the bottom of each page
- Cross out mistakes with a single line (do not obscure original text)
- Include sample IDs, device IDs, and cross-references to digital data files

**Electronic lab notebooks (ELNs):**
- Options: Benchling (free for academics), LabArchives, RSpace, SciNote
- Advantages: searchable, easily include images and data, automatic timestamps, backup
- Disadvantages: requires internet access, potential vendor lock-in, data export concerns
- Many institutions now require or strongly encourage ELN use

**Microfluidics-specific notebook entries should include:**
- Device design version and fabrication date
- PDMS batch/lot number, mixing ratio, cure time and temperature
- Plasma treatment parameters (power, time, gas)
- Flow rates or pressures used, with timestamps
- Microscope settings (objective, exposure, filters)
- Links to image files, videos, and analysis scripts
- Observations: leaks, bubbles, delamination, unexpected behavior

### 5.5 Data Management and Backup

**File organization structure:**
```
/lab-data/
  /projects/
    /project-name/
      /raw-data/
        /YYYY-MM-DD_experiment-description/
          images/
          videos/
          flow-data/
          metadata.yaml
      /analysis/
      /figures/
      /manuscripts/
  /device-designs/
    /version-X.Y/
      CAD-files/
      mask-files/
      fabrication-notes.md
  /protocols/
  /equipment-logs/
```

**Backup strategy (3-2-1 rule):**
- **3** copies of all data
- **2** different storage media (e.g., local drive + cloud)
- **1** offsite backup

**Practical implementation:**
- Primary: Lab workstation or NAS (network-attached storage)
- Secondary: Institutional cloud storage (Google Drive, OneDrive, Box -- check storage limits)
- Tertiary: External hard drive stored off-site, updated monthly
- Microscopy data can be enormous (100s of GB per experiment); plan storage accordingly
- Use checksums (md5sum) to verify backup integrity for critical datasets

**Data retention:**
- Follow your institution's data retention policy (typically 7-10 years minimum)
- NIH and NSF require data be available for at least 3 years after the end of funding
- Metadata is as important as the data itself -- always record experimental parameters

---

## Quick-Start Checklist

For a new PI or researcher setting up from zero, here is a recommended 6-month timeline:

**Month 1-2: Foundation**
- [ ] Secure lab space with fume hood access
- [ ] Install utilities (compressed air/nitrogen, vacuum, DI water access)
- [ ] Order basic consumables (PDMS, slides, tubing, connectors)
- [ ] Purchase or build first syringe pump
- [ ] Set up lab notebook system (physical or ELN)

**Month 2-3: Core Equipment**
- [ ] Purchase and install plasma cleaner
- [ ] Acquire basic microscope (stereo or basic inverted)
- [ ] Set up workstation for data analysis and design
- [ ] Apply for cleanroom access at nearest shared facility
- [ ] Complete cleanroom safety training

**Month 3-4: First Devices**
- [ ] Fabricate or obtain first SU-8 master mold (via cleanroom)
- [ ] Cast and bond first PDMS devices
- [ ] Establish and test flow control setup
- [ ] Write first batch of SOPs
- [ ] Set up data management and backup system

**Month 4-6: Optimization**
- [ ] Refine device designs based on initial results
- [ ] Upgrade equipment based on identified bottlenecks
- [ ] Train additional lab members
- [ ] Establish inventory management system
- [ ] Begin routine maintenance schedules

---

## Sources

- [Implementing Microfluidics in Any Lab - Standard BioTools](https://standardbio.com/microfluidics-explained/implementing-microfluidics-in-any-lab/)
- [Guide to Microfluidics and Lab-on-a-Chip Manufacturing - Formlabs](https://formlabs.com/blog/microfluidics-millifluidics-lab-on-a-chip-manufacturing/)
- [Low-cost Feedback-Controlled Syringe Pressure Pumps for Microfluidics - PLOS ONE](https://pmc.ncbi.nlm.nih.gov/articles/PMC5378403/)
- [Syringe Pumps for Microfluidics - Darwin Microfluidics](https://darwin-microfluidics.com/categories/syringe-pump/)
- [Common Flow Control for Microfluidics - ELEXAN Scientific](https://elexansci.com/blog/common-flow-control-for-microfluidics-in-the-lab/)
- [How to Fabricate a PDMS Microfluidic Chip - Darwin Microfluidics](https://blog.darwin-microfluidics.com/step-by-step-guide-to-make-your-pdms-microfluidic-chip/)
- [Homebrew Photolithography for Rapid Prototyping of Microfluidic Devices - ACS Omega](https://pubs.acs.org/doi/10.1021/acsomega.3c05544)
- [Multilayer Soft Photolithography with Custom Equipment - PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC9412704/)
- [Princeton MNFC - How to Become a User](https://mnfc.princeton.edu/how-become-user)
- [UChicago Pritzker Nanofab Rates](https://pnf.uchicago.edu/about/rates/)
- [VINSE Microfluidic Device Fabrication Short Course - Vanderbilt](https://www.vanderbilt.edu/vinse/2024/12/23/short-course-summer-2025-microfluidic-device-fabrication/)
- [About the NNCI](https://nnci.net/about-nnci)
- [CMC Microsystems MicroFAB Access](https://www.cmc.ca/mnt/)
- [CMC Microsystems Microfluidics Professional Course](https://www.cmc.ca/events/microfluidics-professional-course/)
- [Enabling Microfluidics: from Clean Rooms to Makerspaces - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S016777991730001X)
- [Negotiating on Used Lab Equipment - Lab Manager](https://www.labmanager.com/negotiating-on-used-lab-equipment-2934)
- [LabX Marketplace](https://www.labx.com/)
- [BioSurplus Used Lab Equipment](https://www.biosurplus.com/)
- [Surplus Solutions (SSLLC)](https://ssllc.com/)
- [Lab Inventory Management Best Practices - Lab Manager](https://www.labmanager.com/lab-inventory-management-guide-12258)
- [Lab Inventory Management - LabKey](https://www.labkey.com/lab-inventory-management/)
- [What Makes a Good Laboratory SOP - MSE Supplies](https://www.msesupplies.com/blogs/news/what-makes-a-good-laboratory-standard-operating-procedure-sop)
- [Georgia Tech Shared Cleanrooms - IEN](https://dev.ien.gatech.edu/shared-cleanrooms)
- [Soft Lithography - LNF Wiki (University of Michigan)](https://lnf-wiki.eecs.umich.edu/wiki/Soft_lithography)
- [Introduction to Soft Lithography - Elveflow](https://elveflow.com/microfluidic-reviews/introduction-about-soft-lithography-and-polymer-molding-for-microfluidic/)
