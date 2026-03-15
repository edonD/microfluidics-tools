# Photolithography for Microfluidics Fabrication

## Overview

Photolithography is the foundational patterning technique for microfluidics fabrication. It is used either to directly create device structures or, more commonly, to fabricate master molds (typically in SU-8 photoresist) from which PDMS or other polymer devices are replica-molded via soft lithography. This document covers mask-based UV lithography, maskless direct-write systems, photoresist selection, and photomask procurement.

---

## 1. Standard UV Lithography (Mask Aligners)

### What It Is

Contact/proximity UV lithography uses a photomask (chrome-on-glass or film) placed in contact with or near a photoresist-coated wafer. A UV lamp (typically i-line, 365 nm, or broadband) exposes the resist through the mask pattern. The mask aligner provides precision alignment between mask and substrate, controlled gap spacing, and uniform UV exposure.

### When to Use

- Fabricating SU-8 master molds for PDMS soft lithography
- Any microfluidics design with feature sizes above ~2 um
- Multi-layer devices requiring alignment between layers (mask aligners provide front/back-side alignment)
- Established designs where you will use the same mask repeatedly
- Higher throughput than direct-write (full wafer exposure in seconds)

### Key Equipment: Mask Aligners

#### SUSS MicroTec (formerly Karl Suss)

| Model | Wafer Size | Resolution | Mode | Notes |
|-------|-----------|------------|------|-------|
| MA/BA6 Gen4 | Up to 6" (150 mm) | 0.5 um (vacuum contact), 2.5 um (proximity) | Contact, proximity, vacuum contact | Workhorse of university cleanrooms worldwide. Front- and back-side alignment. Handles thick resist (MEMS/microfluidics). |
| MA8 Gen3 | Up to 8" (200 mm) | ~1 um (contact) | Contact, proximity | Larger wafer capacity. Top and bottom microscopes for dual-side alignment. |
| MA/BA8 Gen4 | Up to 8" | Sub-micron | Contact, proximity, vacuum contact | Latest generation with NanoImprint capability option. |
| MJB4 | Up to 4" | ~1 um | Contact, proximity | Compact benchtop model for smaller labs. |

**Price range (new):** $150,000--$400,000+ depending on model and options.
**Price range (used/refurbished):** $30,000--$120,000. Vendors like ClassOne Equipment and Machinio carry refurbished SUSS units (MA6, MA8, MA150, MA200, MJB3) at reportedly 60%+ savings off OEM. Older Karl Suss MA6/BA6 units from ~2012 are available on secondary markets.

#### EVG (EV Group)

| Model | Wafer Size | Resolution | Notes |
|-------|-----------|------------|-------|
| EVG 620 | Up to 6" | ~1 um | Research-grade mask aligner with high alignment accuracy. |
| EVG 6200 | Up to 8" | Sub-micron | Production-capable, automated features. |
| EVG 610 | Up to 6" | ~2 um | Entry-level model for universities and R&D. |

**Price range (new):** $200,000--$500,000+.
**Price range (used/refurbished):** $40,000--$150,000. ClassOne Equipment and Litho Support carry refurbished EVG mask aligners.

#### OAI (Optical Associates Inc.)

| Model | Notes |
|-------|-------|
| Model 200 | UV exposure system with mask alignment capability. More affordable entry point for labs doing basic microfluidics. |
| Model 500 | Higher-spec research mask aligner. |

**Price range:** Generally lower cost than SUSS/EVG -- estimated $50,000--$150,000 new.

### Pros and Cons of Mask-Based UV Lithography

**Pros:**
- Fast exposure (seconds per wafer)
- Well-established process with decades of published protocols
- Sub-micron resolution achievable in vacuum contact mode
- Large installed base means easy to find used equipment, spare parts, and training
- Excellent for thick-resist processing (SU-8 up to 500 um)

**Cons:**
- Requires a physical photomask (cost and lead time for each new design)
- Design changes require ordering a new mask ($200--$2,000+ per mask)
- Cleanroom environment typically required
- Equipment is large and requires installation infrastructure
- Contact mode can damage masks over time

---

## 2. Maskless Lithography / Direct-Write Systems

### What It Is

Maskless lithography projects a pattern directly onto the photoresist using either a laser beam (laser direct-write) or a digital micromirror device (DMD), eliminating the need for a physical photomask. The pattern is defined digitally (CAD/GDS) and written pixel-by-pixel or via projection of dynamic mask patterns.

### When to Use

- Rapid prototyping where designs change frequently
- When you cannot justify the cost and lead time of ordering masks
- Low-volume or one-off fabrication runs
- Writing masks directly (some systems double as mask writers)
- Academic labs iterating quickly on new designs

### Key Equipment

#### Heidelberg Instruments MLA150

- **Type:** DMD-based maskless aligner with 405 nm diode laser
- **Resolution:** 1 um minimum feature size (some sources report 0.5 um achievable)
- **Alignment accuracy:** Better than 200 nm overlay
- **Write speed:** Up to 285 mm^2/min at maximum speed
- **Wafer size:** Up to 6" wafers, pieces, and mask plates
- **Installed base:** Widely adopted at major universities (Stanford, Yale, Northwestern, UCSB, Notre Dame, Maryland, Illinois, NIST, UBC, DTU)
- **Price:** Not publicly listed. Estimated $400,000--$600,000 based on capital equipment budgets at purchasing institutions. Contact Heidelberg Instruments for quotes.

#### Heidelberg Instruments MLA300

- **Type:** Industrial-grade maskless aligner
- **Resolution:** 1.5 um (standard mode), 3 um (high-throughput mode)
- **Substrate size:** Up to 300 x 300 mm
- **Laser:** Long-lifetime diode laser (estimated 10-year lifespan in 24/7 production)
- **Target use:** Production environments, mask shops
- **Price:** Estimated $500,000--$800,000+.

#### Heidelberg Instruments uMLA

- **Type:** Tabletop maskless aligner
- **Resolution:** ~5 um
- **Target use:** Teaching labs, low-budget prototyping
- **Price:** Estimated $80,000--$150,000. Significantly more affordable entry point.

#### Raith EBPG5200+ (Electron Beam Lithography)

- **Type:** 100 kV electron beam lithography system
- **Resolution:** Sub-5 nm (features as small as 14 nm demonstrated)
- **Pattern generator:** 125 MHz
- **Maximum current:** 350 nA
- **Mainfield size:** 1 mm
- **When to use for microfluidics:** Rarely needed. Only for nanofluidics or when integrating nanoscale features (nanopores, nanochannels, photonic structures) into microfluidic devices.
- **Price:** $1M--$3M+ new. Extremely slow write speeds make it impractical for full microfluidic device patterning.

### Pros and Cons of Maskless / Direct-Write

**Pros:**
- No mask required -- design changes are instant (just update the CAD file)
- Eliminates mask cost and multi-week lead times
- Excellent for prototyping and iterative design
- Some systems (MLA150) provide good enough resolution for most microfluidics
- Can also be used to write masks on chrome blanks

**Cons:**
- Slower than mask-based exposure (serial writing vs. parallel exposure)
- Write time scales with pattern area -- large or dense patterns take much longer
- Higher capital cost than a basic mask aligner
- Resolution generally not as good as best contact lithography
- E-beam systems are extremely expensive and slow (niche use only)

---

## 3. Photoresists for Microfluidics

### SU-8 (Kayaku Advanced Materials, formerly MicroChem)

SU-8 is the dominant photoresist for microfluidics master mold fabrication.

**What it is:** Epoxy-based negative photoresist. UV-exposed regions cross-link and become insoluble; unexposed regions are dissolved in developer (PGMEA-based SU-8 developer).

**Key properties:**
- Thickness range: <1 um to >300 um in a single coat (spin coating); up to >1 mm with dry film lamination (TFDS)
- High optical transparency above 360 nm (enables thick-film processing with near-vertical sidewalls)
- High aspect ratio capability (>10:1 at 100 um thickness)
- Excellent chemical and thermal stability after cross-linking
- Very strong adhesion to silicon and glass substrates
- Biocompatible after full curing

**Product lines:**

| Product | Thickness Range | Notes |
|---------|----------------|-------|
| SU-8 2000 series (2002--2150) | 0.5--200+ um | Standard workhorse for microfluidics. Multiple viscosities for different thickness targets. |
| SU-8 3000 series | 5--100+ um | Improved adhesion and faster processing vs. 2000 series. |
| SU-8 XFT | 50--200+ um | Formulated for ultra-thick films. Improved adhesion, lower coating stress. |
| SU-8 TF 6000 | <1 um thin films | For thin-film applications (not typical for microfluidics). |
| SU-8 Dry Film (TFDS) | Up to >1 mm | Laminated rather than spin-coated. For very thick structures. |

**Cost:** ~$200--$600 per 500 mL bottle depending on formulation. Developer ~$80--$150 per 4L.

**Limitations:**
- Difficult to remove once cross-linked (essentially permanent on the wafer -- fine for master molds)
- Internal stress can cause cracking or delamination in very thick films
- Requires careful baking protocol (ramp rates matter)
- Above ~500 um, UV absorption causes sidewall undercuts and poor curing at substrate interface

### AZ Photoresist Series (Merck / AZ Electronic Materials)

**What it is:** Family of positive photoresists (exposed regions become soluble). The AZ 40XT, AZ 4620, and AZ 9260 are relevant for microfluidics.

**When to use:**
- When you need a removable/dissolvable mold (sacrificial resist processing)
- Rounded channel cross-sections (positive resists reflow when heated)
- Thinner channel depths (typically 1--100 um per coat)

**Key products:**
- **AZ 4620:** Thick positive resist, up to ~20 um per coat. Good for electroplating molds.
- **AZ 9260:** Up to ~100 um with multiple coats. Good sidewall quality.
- **AZ 40XT:** Single-coat up to ~100 um. Designed for thick-film applications.
- **AZ 1500/1512:** Thin positive resists (~1--2 um). Used for thin patterning, not mold fabrication.

**Pros:** Easy to strip/remove; reflow capability for rounded channels.
**Cons:** Lower aspect ratios than SU-8; not as chemically robust; thinner maximum layers.

### KMPR 1000 Series (Kayaku Advanced Materials)

**What it is:** Epoxy-based negative photoresist, similar chemistry to SU-8 but designed to be removable with commercial chemical strippers.

**Key properties:**
- Thickness: 4--110 um in a single coat (five standard viscosities)
- High resolution, high aspect ratio (comparable to SU-8)
- Can be chemically stripped after use -- major advantage over SU-8 for electroplating molds and sacrificial layers

**When to use:** When you need SU-8-like performance but must remove the resist afterward (e.g., electroplating molds, sacrificial structures). Less common for microfluidic master molds since SU-8 permanence is usually acceptable.

### Dry Film Photoresists

#### Ordyl (Elga Europe)

- **Type:** Negative dry film resist
- **Thickness:** Available in various thicknesses (typically 20--100 um per layer)
- **Resolution:** ~20--50 um minimum feature size (lower than SU-8)
- **Application:** Laminated onto substrate (no spin coating, no solvents)
- **Advantages:** No liquid handling, excellent thickness uniformity, fast processing, good conformability, near-vertical sidewalls, low cost
- **Limitations:** Lower resolution and aspect ratio than SU-8; limited thickness range per layer

#### DuPont Riston

- **Type:** Dry film photoresist (various formulations)
- **Thickness:** 15--75 um per layer
- **Application:** Laminated; used extensively in PCB industry
- **Advantages:** Widely available, well-established supply chain, inexpensive
- **Limitations:** Not optimized for high-resolution microfluidics

#### PerMX (DuPont)

- **Type:** Permanent dry film resist
- **Thickness:** 5--100 um
- **Application:** Can be used as structural layers in microfluidic devices (not just molds)

**When to use dry film resists:** Quick prototyping when resolution requirements are relaxed (>20 um features); when you want to avoid spin coating and solvent handling; for multilayer laminated structures; when cost is a primary concern.

### Photoresist Comparison Summary

| Property | SU-8 | AZ 40XT | KMPR | Ordyl (DFR) |
|----------|------|---------|------|-------------|
| Type | Negative | Positive | Negative | Negative |
| Max thickness (single coat) | 200+ um | ~100 um | 110 um | ~100 um |
| Min feature size | ~2 um | ~5 um | ~5 um | ~20 um |
| Aspect ratio | >10:1 | ~5:1 | ~8:1 | ~3:1 |
| Removable? | No | Yes | Yes | No |
| Application method | Spin coat | Spin coat | Spin coat | Laminate |
| Relative cost | Medium | Medium | Medium-High | Low |
| Complexity | High (critical bakes) | Medium | High | Low |

---

## 4. Photomask Fabrication and Procurement

### Mask Types

#### Chrome-on-Glass (Hard Masks)

- **Substrate:** Soda-lime glass (standard) or fused silica/quartz (for DUV or high-precision)
- **Chrome layer:** 80--120 nm Cr with optional CrOx anti-reflective coating
- **Resolution:** 0.5--2 um (laser-written), <0.25 um (e-beam written)
- **Sizes:** Standard 4" x 4", 5" x 5", 6" x 6", 7" x 7"
- **Durability:** Thousands of contact exposures

**Typical costs:**
- Soda-lime substrate blank: ~$45--$70 per 5" x 5" plate
- Quartz substrate blank: ~$500--$1,100 per 5" x 5" plate
- Custom-written chrome mask (soda-lime): $300--$1,500 depending on complexity, size, and vendor
- Custom-written chrome mask (quartz): $800--$3,000+
- E-beam written masks: $2,000--$10,000+ (for sub-micron features)

**Lead time:** 1--3 weeks typical; rush service available at premium cost

#### Film/Transparency Masks (Soft Masks)

- **Substrate:** Mylar or transparency film
- **Printing:** High-resolution inkjet or laser photoplotting
- **Resolution:** 8--50 um (depending on printer/service)
- **Cost:** $5--$100 per mask
- **Lead time:** Same day to a few days

**When to use:** Prototyping microfluidic designs with features >20 um. Fast and cheap for iterating on designs before committing to a chrome mask.

### Mask Vendors

#### Front Range Photomask (Las Vegas, NV, USA)
- Specializes in direct-write photomasks
- Fast turnaround, competitive pricing
- Chrome-on-glass and emulsion/Mylar masks
- Pricing available on website (frontrangephotomask.com/pricing)
- Good option for academic and prototyping work

#### Compugraphics (MacDermid Alpha, global)
- Over 50 years in photomask fabrication
- High-quality production masks and reticles
- Offers contact-print copies (lower cost than new master)
- Global facilities with broad capability range
- Better for production-grade masks; higher cost for small orders

#### Photo Sciences Inc. (Torrance, CA, USA)
- Laser-patterned photomasks
- Wide range of substrates and sizes
- Strong in MEMS/microfluidics applications

#### Benchmark Technologies (Lynnfield, MA, USA)
- Photomasks and reticles
- Good for academic customers

#### JD Photo-Data (UK)
- Chrome photomasks, competitive pricing for European customers

#### UniversityWafer
- Chrome-on-glass and quartz photomasks/reticles
- Targets academic customers
- Online ordering

#### In-House Mask Writing
- If your lab has a Heidelberg MLA150 or similar, you can write masks directly onto chrome blanks
- Eliminates vendor lead time; cost is only the blank + machine time
- Resolution depends on the direct-write system (~1 um for MLA150)

### Mask Selection Decision Tree

1. **Features >20 um, early prototyping?** --> Film/transparency mask ($10--$50, same-day)
2. **Features 5--20 um, design mostly stable?** --> Chrome-on-soda-lime glass ($300--$800, 1--2 weeks)
3. **Features 2--5 um?** --> High-quality chrome mask, laser-written ($500--$1,500, 1--2 weeks)
4. **Features <2 um?** --> E-beam written chrome-on-quartz ($2,000--$10,000, 2--4 weeks)
5. **Frequent design changes?** --> Use maskless aligner (MLA150) or write masks in-house

---

## 5. Soft Lithography Process: SU-8 Master to PDMS Device

This is the complete workflow from photomask design to working PDMS microfluidic device.

### Step 1: Design

- Draw channel layout in CAD software (AutoCAD, L-Edit, KLayout, or CleWin)
- Export as GDS-II (for mask vendors/direct-write) or high-resolution PDF/DXF (for film masks)
- Design rules: minimum feature size depends on resist and exposure system; typical microfluidics channels are 20--500 um wide, 10--200 um deep

### Step 2: Photomask Procurement

- Order chrome mask or film mask from vendor (see Section 4)
- Or use maskless aligner to skip this step entirely

### Step 3: Substrate Preparation

- Start with a clean silicon wafer (typically 3" or 4" diameter, single-side polished)
- Clean with piranha solution (H2SO4:H2O2 3:1) or solvent rinse (acetone, IPA, DI water, N2 dry)
- Dehydration bake: 200 C for 5 min on hotplate
- Optional: spin coat adhesion promoter (OmniCoat or HMDS) if adhesion is problematic

### Step 4: SU-8 Spin Coating

- Select SU-8 formulation based on target thickness (e.g., SU-8 2050 for 50--100 um, SU-8 2100 for 100--250 um)
- Pour resist onto center of wafer (sufficient to cover ~60--70% of area)
- Spin coat: typically 500 rpm for 10 s (spread), then 1000--4000 rpm for 30 s (final thickness)
- Spin speed determines final thickness (consult Kayaku datasheet for exact speed-thickness curves)

### Step 5: Soft Bake (Pre-Exposure Bake)

- Ramp hotplate from 65 C to 95 C (ramp at ~5 C/min to avoid thermal shock)
- Hold at 65 C for time dependent on thickness (e.g., 5 min for 50 um)
- Ramp to 95 C, hold for longer time (e.g., 15--20 min for 50 um, 45+ min for 100 um)
- Cool slowly on hotplate (do not remove abruptly -- thermal stress causes cracking)
- Film should appear uniform and free of bubbles

### Step 6: UV Exposure

- Load mask into mask aligner
- Align mask to wafer (or to previous layer marks for multi-layer devices)
- Expose with appropriate dose (typically 150--250 mJ/cm^2 for 50--100 um SU-8 at 365 nm)
- Use i-line filter if available (removes sub-350 nm wavelengths that cause surface overexposure)
- Contact or proximity mode (5--25 um gap)

### Step 7: Post-Exposure Bake (PEB)

- Ramp from 65 C to 95 C (similar protocol to soft bake)
- 65 C hold: 1--5 min depending on thickness
- 95 C hold: 5--15 min depending on thickness
- The exposed SU-8 cross-links during this bake -- pattern should become visible
- Cool slowly to room temperature

### Step 8: Development

- Immerse in SU-8 developer (PGMEA) with agitation
- Development time depends on thickness (e.g., 6--10 min for 50 um, 15--20 min for 100 um)
- Rinse with fresh developer, then IPA
- If white residue appears during IPA rinse, the wafer is under-developed -- return to developer
- Dry gently with N2 gun

### Step 9: Hard Bake (Optional)

- Bake at 150--200 C for 15--30 min to further cross-link SU-8
- Improves mold durability and chemical resistance
- Recommended if mold will be used for many PDMS castings

### Step 10: Silanization (Anti-Stick Treatment)

- Treat SU-8 master with fluorosilane vapor (e.g., trichloro(1H,1H,2H,2H-perfluorooctyl)silane)
- Place master and a drop of silane in a vacuum desiccator for 1--2 hours
- Creates a hydrophobic monolayer that prevents PDMS from sticking to SU-8
- Essential for mold longevity -- without this, PDMS will eventually tear the SU-8 features off the wafer

### Step 11: PDMS Casting (covered in detail in 05_fabrication_soft_litho.md)

- Mix PDMS (Sylgard 184) 10:1 base:curing agent
- Degas, pour over master, cure, peel, punch ports, bond

---

## 6. Cost Summary and Decision Guide

### Total Cost to Set Up Photolithography (Approximate)

| Approach | Equipment Cost | Per-Design Cost | Resolution | Turnaround |
|----------|---------------|-----------------|------------|------------|
| Film mask + borrowed mask aligner (university cleanroom) | $0 (user fees ~$20--$80/hr) | $10--$50 (mask) + fees | 10--50 um | 1--3 days |
| Chrome mask + university cleanroom | $0 (user fees) | $300--$1,500 (mask) + fees | 2--10 um | 1--3 weeks |
| Used mask aligner (own lab) | $30,000--$120,000 | $300--$1,500 (mask) | 1--5 um | 1--3 weeks (mask) |
| Maskless aligner (MLA150) | $400,000--$600,000 | ~$0 (no mask needed) | 1 um | Same day |
| Outsource SU-8 master fabrication | $0 | $200--$2,000 per master | 2--50 um | 1--4 weeks |

### Recommended Approach by Lab Stage

**Starting out / low budget:**
- Use university cleanroom facilities (most charge $20--$80/hr for external users)
- Start with film/transparency masks for prototyping
- Upgrade to chrome masks once design is finalized
- Total cost per master: $50--$300

**Established academic lab:**
- Invest in cleanroom access or shared facility membership
- Use chrome masks for production masters
- Consider a maskless aligner (MLA150 or uMLA) if design iteration is frequent
- Total cost per master: $200--$1,000

**Startup / commercial:**
- Outsource master fabrication initially
- Invest in maskless aligner when throughput justifies it
- Transition to injection molding (thermoplastics) for production scale

---

## 7. Troubleshooting Common Issues

| Problem | Likely Cause | Solution |
|---------|-------------|----------|
| SU-8 cracking | Thermal stress during baking | Slow ramp rates (2--5 C/min); do not remove wafer from hot plate abruptly |
| SU-8 delamination | Poor adhesion | Dehydration bake; use adhesion promoter (OmniCoat); ensure substrate is clean |
| Undercut sidewalls | Over-exposure or wrong wavelength | Reduce dose; use i-line filter; check exposure uniformity |
| Incomplete development | Insufficient time or agitation | Increase development time; use gentle agitation; replace spent developer |
| Bubbles in SU-8 film | Resist not degassed; spin speed too low | Allow resist to settle after pouring; optimize spin recipe |
| PDMS stuck to mold | No silanization | Treat with fluorosilane; re-silanize periodically |
| Poor feature fidelity | Mask resolution too low | Switch from film mask to chrome mask |
| Non-uniform thickness | Poor spin coating | Check resist viscosity; level spin coater; ensure wafer is centered |

---

## Sources

- [SUSS MicroTec Mask Aligners](https://www.suss.com/en/products-solutions/mask-aligner)
- [SUSS MA/BA6 Gen4 at NIST](https://www.nist.gov/laboratories/tools-instruments/nanofab-tool-suss-microtec-maba6-gen4-mask-aligner)
- [Columbia CNI SUSS MA6](https://cni.columbia.edu/sussmicrotecma6)
- [Heidelberg MLA150 Product Page](https://heidelberg-instruments.com/product/mla150/)
- [Heidelberg MLA300 Product Page](https://heidelberg-instruments.com/product/mla300/)
- [Heidelberg uMLA Product Page](https://heidelberg-instruments.com/product/%CE%BCmla/)
- [MLA150 Fact Sheet (PDF)](https://heidelberg-instruments.com/wp-content/uploads/2021/10/fact-sheet-MLA150.pdf)
- [MLA150 at UCSB Nanofab](https://wiki.nanofab.ucsb.edu//wiki/Maskless_Aligner_(Heidelberg_MLA150))
- [MLA150 at University of Illinois](https://mrl.illinois.edu/facilities/equipment/heidelberg-mla150-aligner-maskless-photolithography)
- [Raith EBPG Product Page](https://raith.com/products/ebpg/)
- [Raith EBPG5200+ at Stanford](https://snsf.stanford.edu/facilities/fab/npc/ebpg)
- [Kayaku SU-8 Product Page](https://kayakuam.com/su-8/)
- [SU-8 Wikipedia](https://en.wikipedia.org/wiki/SU-8_photoresist)
- [SU-8 MEMS Encyclopedia](https://memscyclopedia.org/su8.html)
- [Kayaku KMPR 1000](https://kayakuam.com/kmpr-1000-product/)
- [KMPR 1000 Series at Microresist](https://microresist.de/en/produkt/kmpr-1000-series/)
- [SU-8 Mold Lithography - Elveflow](https://elveflow.com/microfluidic-reviews/soft-lithography-microfabrication/su-8-mold-lithography/)
- [SU-8 Baking - Elveflow](https://elveflow.com/microfluidic-reviews/soft-lithography-su-8-baking/)
- [Introduction to Photomask in Microfluidics - Elveflow](https://www.elveflow.com/microfluidic-reviews/soft-lithography-microfabrication/introduction-about-photomask-in-microfluidic/)
- [Front Range Photomask](https://www.frontrangephotomask.com/)
- [Front Range Photomask Pricing](https://www.frontrangephotomask.com/pricing)
- [Compugraphics Photomasks](https://www.compugraphics-photomasks.com/)
- [Photo Sciences Photomasks](https://www.photo-sciences.com/photomask-and-patterned-optics-services/photomasks/)
- [UniversityWafer Photomasks](https://www.universitywafer.com/photomasks.html)
- [ClassOne Equipment Refurbished Aligners](https://www.classoneequipment.com/suss-and-evg)
- [Used Mask Aligners on Machinio](https://www.machinio.com/mask-aligners)
- [Compact Low-Cost Mask Aligner (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6105338/)
- [Ordyl Dry Film Resist Discussion (ResearchGate)](https://www.researchgate.net/post/What_would_be_the_minimum_resolution_if_we_use_ordyl_dry_film_photoresist_what_would_be_the_advantage_of_ordyl_photoresist_over_other_photorsist)
- [Dry Film Resist for Microfluidics (ResearchGate)](https://www.researchgate.net/publication/8059927_Microfluidic_channel_fabrication_in_dry_film_resist_for_production_and_prototyping_of_hybrid_chips)
