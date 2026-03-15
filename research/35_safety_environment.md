# Safety and Environmental Guide for Microfluidics Labs

> Practical reference covering chemical, cleanroom, biological, and laser safety,
> along with environmental considerations and emergency procedures for microfluidics
> research facilities.

---

## 1. Chemical Safety in Microfluidics Labs

Microfluidics fabrication and operation involve a wide range of hazardous chemicals. Every researcher must complete chemical safety training and be familiar with Safety Data Sheets (SDS) for all materials in use before beginning work.

### 1.1 SU-8 Developer (PGMEA — Propylene Glycol Methyl Ether Acetate)

| Property | Detail |
|---|---|
| **Primary hazards** | Flammable liquid (flash point ~42 deg C), mild irritant |
| **Exposure routes** | Inhalation of vapors, skin and eye contact |
| **PPE required** | Nitrile gloves, safety goggles, lab coat; use in chemical fume hood |
| **Storage** | Away from ignition sources, in approved flammable-liquid cabinets |
| **Waste** | Collect as halogen-free organic solvent waste |

- PGMEA vapors can cause dizziness and respiratory irritation at elevated concentrations.
- Avoid skin contact; prolonged exposure may cause dermatitis.
- SU-8 photoresist itself is an epoxy resin and a skin sensitizer — once sensitized, even trace exposure can trigger allergic reactions.

### 1.2 Hydrofluoric Acid (HF) — Glass and Silicon Etching

HF is among the most dangerous chemicals encountered in any laboratory. It penetrates skin rapidly and sequesters calcium and magnesium ions in tissue, potentially causing fatal cardiac arrhythmia even from small area exposures.

**Mandatory protocols:**
- Never work with HF alone — the buddy system is required at all times.
- Calcium gluconate gel (2.5%) must be immediately accessible at the point of use.
- All users must complete HF-specific training before handling.
- Double gloving recommended: inner nitrile + outer neoprene or specialized HF-resistant gloves.
- Full face shield, chemical splash goggles, acid-resistant apron, and closed-toe shoes required.
- Use only in a dedicated fume hood with HF-compatible materials (polypropylene, PTFE).
- Concentrations above 1% require emergency eyewash and safety shower within 10 seconds of travel.

**Dilute vs. concentrated HF:**
- Buffered oxide etch (BOE, typically 6:1 NH4F:HF) is somewhat less aggressive but equally dangerous systemically.
- Even dilute HF (< 2%) can cause delayed burns that may not be noticed for hours.
- Any skin contact, regardless of concentration, should be treated as a medical emergency.

### 1.3 Piranha Solution (H2SO4 + H2O2)

Piranha solution is used for aggressive cleaning of organic contaminants from substrates. It is highly exothermic, extremely corrosive, and presents a genuine explosion risk.

**Preparation rules:**
- Always add H2O2 to H2SO4, never the reverse.
- Typical ratio: 3:1 to 7:1 (H2SO4:H2O2 by volume). Never exceed 50% H2O2 concentration — explosion risk increases dramatically.
- Any batch over 100 mL requires cooling in an ice bath during mixing.
- Prepare only in clean, dry Pyrex glassware or Teflon (PTFE) containers — piranha reacts violently with most plastics.
- Ensure all glassware is completely free of organic residues before contact.

**Critical safety rules:**
- Never store piranha solution in a closed container — gas evolution creates overpressure and explosion hazard.
- Use freshly prepared solution only; do not attempt to save or re-use.
- Do NOT use paper towels, rags, or other organic materials to absorb spills — spontaneous ignition may occur.
- Never work with piranha when alone in the lab.
- Keep near a safety shower and eyewash station.
- Dispose by allowing to cool, then neutralize per institutional hazardous waste procedures.

### 1.4 Fluorinated Oils (HFE-7500, FC-40, Fluorinert)

| Property | Detail |
|---|---|
| **Use** | Continuous phase in droplet microfluidics |
| **Primary hazards** | Inhalation risk (displaces oxygen in poorly ventilated areas), mild skin irritation |
| **Thermal decomposition** | Produces toxic hydrogen fluoride gas at elevated temperatures (> 200 deg C) |
| **Environmental** | Persistent in environment; some are potent greenhouse gases |

- Always use in well-ventilated areas or fume hoods.
- Avoid heating above manufacturer-recommended temperatures.
- FC-40 and similar perfluorinated compounds have long atmospheric lifetimes; minimize waste and explore alternatives where possible.

### 1.5 Silane Coupling Agents (APTES, OTS, TMCS)

- **Moisture sensitivity:** React vigorously with water; store under inert atmosphere (nitrogen or argon).
- **Toxic vapors:** Chlorosilanes (e.g., TMCS, trichlorosilanes) release HCl gas upon hydrolysis. Use exclusively in a fume hood.
- **Flammability:** Many silanes are flammable; keep away from ignition sources.
- **PPE:** Chemical splash goggles, nitrile gloves, lab coat. For volatile silanes, consider a respirator with organic vapor cartridges.

### 1.6 PDMS Curing Agent (Sylgard 184 Part B and Similar)

- The curing agent (platinum-catalyzed crosslinker) is a mild skin irritant and sensitizer.
- Always wear nitrile gloves during mixing and handling.
- Uncured PDMS base and curing agent can release trace amounts of siloxanes — mix and degas in a ventilated area.
- Cured PDMS is generally regarded as non-toxic, but uncured oligomers can leach into surrounding media and have been shown to alter gene expression in cultured cells.

### 1.7 Organic Solvents for Bonding and Surface Treatment

| Solvent | Key Hazards | Notes |
|---|---|---|
| **Chloroform (CHCl3)** | Toxic by inhalation, suspected carcinogen, liver damage | Use only in fume hood; TWA 10 ppm |
| **Dichloromethane (DCM)** | Toxic, suspected carcinogen, CNS depressant | Penetrates many glove materials — use laminated or Silver Shield gloves |
| **Cyclohexane** | Highly flammable, CNS depressant | Flash point -20 deg C; keep away from all ignition sources |
| **Acetone** | Highly flammable, irritant | Common but often underestimated; flash point -20 deg C |
| **Isopropanol (IPA)** | Flammable, mild irritant | Flash point 12 deg C |
| **Toluene** | Flammable, toxic, reproductive hazard | Chronic exposure limits are strict (TWA 20 ppm) |

- Check glove compatibility for each solvent — nitrile is not universally protective.
- Collect all halogenated and non-halogenated waste separately.

---

## 2. Cleanroom Safety

### 2.1 General Cleanroom Protocols

- **Gowning:** Full cleanroom garments (bunny suit or coveralls, hood, booties, gloves, safety glasses) are required. Gowning must follow a defined sequence to prevent contamination.
- **Buddy system:** Many facilities require a buddy for student users and anyone with fewer than 5 logged hours of experience.
- **No food, drink, cosmetics, or personal electronics** inside the cleanroom.
- **Emergency exits:** Know the location of all exits, safety showers, eyewash stations, fire extinguishers, and spill kits before beginning work.

### 2.2 UV Exposure from Mask Aligners

- Mask aligners (e.g., Karl Suss/SUSS MicroTec MA6, MJB4) emit broadband UV including UV-A (365 nm), UV-B, and UV-C wavelengths.
- **Eye hazard:** Even brief unprotected exposure to UV-C can cause photokeratitis (welders flash).
- **Skin hazard:** UV exposure causes burns and increases long-term cancer risk.
- **Controls:**
  - Never look directly at the UV source during exposure.
  - Use UV-blocking safety glasses or face shields rated for the emission wavelength.
  - Keep the shutter closed except during active exposure.
  - Some modern aligners have interlocked enclosures — never bypass safety interlocks.

### 2.3 Spin Coater Safety

- **Mechanical hazard:** Spinning chucks rotate at up to 6,000+ RPM; loose items or improperly secured substrates become projectiles.
- **Chemical hazard:** Solvents and photoresists are flung off during spinning, generating aerosols.
- **Protocols:**
  - Always close the spin coater lid before starting.
  - Verify vacuum chuck seal before spinning.
  - Dispense photoresist with the lid open, then close before spin.
  - Clean the bowl regularly to prevent chemical buildup.
  - Use in a ventilated enclosure or fume hood when spinning solvent-based resists.

### 2.4 Compressed Gas Handling

- **Cylinder storage:** Secure all cylinders with chains or straps to wall or bench. Segregate oxidizers from flammables.
- **Transport:** Use cylinder carts; never roll or drag cylinders.
- **Regulators:** Use gas-specific regulators only (never interchange between incompatible gases).
- **Toxic gases** (e.g., silane SiH4, chlorine, boron trichloride): Require gas cabinets with exhaust, gas monitors with alarms, and emergency shutoff capability.
- **Inert gases** (N2, Ar): Asphyxiation hazard in enclosed spaces — ensure adequate ventilation and install oxygen monitors.

### 2.5 Vacuum System Safety

- **Implosion hazard:** Glass desiccators and bell jars under vacuum can implode violently. Use only equipment rated for vacuum service; inspect for cracks before each use.
- **Pump oil mist:** Rotary vane pumps produce oil mist — use exhaust filters and vent to fume hood or facility exhaust.
- **Backstreaming:** Oil from mechanical pumps can contaminate processes. Use foreline traps for sensitive applications.
- **Cryogenic traps:** Liquid nitrogen cold traps can condense oxygen from leaks, creating an explosion hazard with organic solvents. Never use LN2 traps on systems that may contain organics without proper safeguards.

### 2.6 Chemical Fume Hoods

- Verify face velocity (typically 80-120 fpm / 0.4-0.6 m/s) before use.
- Keep sash at or below the indicated working height.
- Do not store chemicals in the fume hood — it reduces airflow effectiveness.
- Never put your head inside the hood.
- Report any alarms or abnormal airflow immediately.

---

## 3. Biological Safety

### 3.1 Biosafety Levels for Microfluidics

**BSL-1 (Basic):**
- Work with well-characterized, non-pathogenic organisms (e.g., non-pathogenic E. coli K-12, S. cerevisiae).
- Standard microbiological practices: lab coats, gloves, eye protection.
- Open bench work is acceptable; no special containment equipment required.
- Hand washing required; no eating or drinking in lab.

**BSL-2 (Enhanced):**
- Required for any work with human-derived materials, including blood, primary tissue, and all human cell lines (even "established" lines like HeLa).
- Required for moderate-risk pathogens (e.g., Staphylococcus aureus, Salmonella, HIV, Hepatitis B/C).
- Work must be performed in a Class II biosafety cabinet (BSC) when procedures may generate aerosols or splashes.
- Access restricted to authorized personnel.
- Sharps precautions and biohazard signage mandatory.
- Microfluidic devices handling human blood or pathogenic organisms must be treated as BSL-2 materials throughout their lifecycle, including disposal.

### 3.2 Working with Blood Samples

- Treat all human blood as potentially infectious (Universal/Standard Precautions).
- Bloodborne pathogen training is required before handling any human blood products.
- Use a biosafety cabinet for any open manipulation (loading into devices, sample preparation).
- Microfluidic chips that have contacted blood are biohazardous waste — dispose in red biohazard bags or sharps containers as appropriate.
- Decontaminate work surfaces with 10% bleach or approved disinfectant after each use.
- Report any needlestick or splash exposure immediately per institutional exposure control plan.

### 3.3 Cell Culture Contamination Prevention

- Perform all cell culture manipulation in a certified Class II biosafety cabinet.
- Microfluidic cell culture platforms should be assembled inside the BSC using aseptic technique.
- Sterilize microfluidic devices before use: autoclaving (if material-compatible), UV exposure, ethanol (70%) wash, or ethylene oxide.
- PDMS is gas-permeable — advantageous for cell culture (CO2/O2 exchange) but increases contamination risk if the environment is not controlled.
- Use antibiotic-free media periodically to detect low-level contamination.
- Test for mycoplasma regularly — it is the most common and insidious contaminant.

### 3.4 Biological Waste Disposal

| Waste Type | Disposal Method |
|---|---|
| Solid biohazardous waste (chips, tubing, gloves) | Red biohazard bag, autoclave before disposal |
| Liquid biological waste | Chemical disinfection (bleach, 30 min contact) then drain, or autoclave |
| Sharps (needles, broken glass, cut tubing) | Puncture-resistant sharps container |
| Mixed chemical-biological waste | Consult EHS — may require special handling |
| Genetically modified organisms | Follow institutional IBC (Institutional Biosafety Committee) protocols |

---

## 4. Laser Safety

### 4.1 CO2 Laser Cutters (Class 4)

CO2 lasers (typically 10.6 um wavelength, 25-150 W) are widely used for cutting and engraving acrylic, PMMA, and paper microfluidic devices. They are Class 4 — the most hazardous classification.

**Hazards:**
- **Eye injury:** Invisible beam (mid-infrared) causes corneal and skin burns instantly. Standard safety glasses do NOT protect — specific CO2-rated laser safety eyewear (OD 5+ at 10.6 um) is required.
- **Fire:** Laser ignites flammable materials (acrylic, paper, wood, tape). Never leave a running laser unattended.
- **Fumes:** Cutting acrylic produces methyl methacrylate and other toxic fumes. Cutting PVC releases chlorine gas (never cut PVC).
- **Skin burns:** Direct or reflected beam causes immediate burns.

**Required controls:**
- Fully enclosed beam path with safety interlocks on all access panels.
- Dedicated exhaust/filtration system with HEPA and activated carbon filters.
- Fire extinguisher (CO2 type) within arm's reach.
- Laser safety training for all operators.
- Warning signs and indicator lights at all entrances.
- Never override or bypass safety interlocks.

### 4.2 Femtosecond Lasers

Ultrafast femtosecond lasers (typically Ti:sapphire, ~800 nm, or fiber lasers at 1030 nm) are used for precision ablation and direct writing of microfluidic channels in glass and polymers.

**Additional hazards beyond standard Class 4:**
- **Multiphoton absorption:** Even nominally "eye-safe" wavelengths become hazardous at femtosecond pulse durations due to nonlinear absorption.
- **Broadband emission:** Frequency-doubled and white-light continuum generation can produce hazardous visible and UV light.
- **Scattered pulses:** High peak power makes even diffuse reflections potentially dangerous.

**Controls:**
- Enclosed beam paths are mandatory.
- Remove all reflective surfaces (watches, rings, tools) from the beam vicinity.
- Use wavelength-specific laser safety eyewear covering all fundamental and harmonic wavelengths.
- Beam blocks must withstand peak power without damage or scattering.
- Designated Laser Safety Officer (LSO) oversight required.

### 4.3 Eye Protection Requirements Summary

| Laser Type | Wavelength | Minimum Eyewear OD | Lens Color (typical) |
|---|---|---|---|
| CO2 | 10,600 nm | OD 5+ at 10.6 um | Clear (special coating) |
| Nd:YAG / fiber | 1,064 nm | OD 5+ at 1064 nm | Green or blue-green |
| Ti:sapphire (fs) | 800 nm | OD 5+ at 800 nm | Orange or red |
| Frequency-doubled | 400-532 nm | OD 5+ at specific wavelength | Amber or orange |
| UV excimer | 193-351 nm | OD 5+ at UV wavelength | UV-blocking clear |

- Eyewear must be stamped with the rated wavelength and OD value.
- Inspect eyewear regularly for damage or coating degradation.
- Prescription glasses alone provide NO laser protection.

---

## 5. Environmental Considerations

### 5.1 PDMS Waste

- Cured PDMS (polydimethylsiloxane) is a thermoset silicone elastomer — it **cannot be recycled** through conventional processes.
- Most cured PDMS ends up in landfill. It is not biodegradable and persists indefinitely in the environment.
- Uncured PDMS waste (base and curing agent) should be collected as chemical waste.
- Biologically contaminated PDMS must be autoclaved before disposal.
- Strategies to reduce waste:
  - Optimize mold design to minimize failed castings.
  - Use thinner PDMS layers where possible (spin-coated membranes vs. thick slabs).
  - Consider reusable or recyclable alternatives (thermoplastics, glass) for production-scale devices.

### 5.2 Solvent Waste Management

- Segregate waste into categories: halogenated solvents, non-halogenated solvents, aqueous acid, aqueous base, and mixed waste.
- Never pour solvents down the drain.
- Label all waste containers with contents, date, and hazard information.
- Fluorinated solvents (HFE-7500, FC-40) may require specialized disposal due to environmental persistence and high global warming potential.
- Track solvent consumption and waste generation — many institutions now require sustainability reporting.

### 5.3 Energy Consumption of Cleanrooms

Cleanrooms are among the most energy-intensive laboratory environments:
- A typical Class 100 (ISO 5) cleanroom consumes 5-10x more energy per square meter than a standard lab, driven by HVAC, HEPA filtration, and humidity control.
- Strategies for reduction:
  - Use mini-environments or laminar flow benches for critical steps rather than maintaining an entire room at high classification.
  - Implement setback modes during unoccupied periods (reduced air changes).
  - Adopt cleanroom-free fabrication methods where possible (e.g., soft lithography can be performed on an open bench for many applications).
  - Consolidate fabrication runs to minimize cleanroom operating hours.

### 5.4 Water Consumption

- Ultra-pure water (UPW/DI water) production and substrate rinsing consume significant water volumes.
- Reclaim rinse water where quality permits.
- Monitor DI water system for leaks and waste.

### 5.5 Sustainable Alternatives

**Paper-based microfluidics:**
- Cellulose paper is renewable, biodegradable, and low-cost.
- Fabricated by wax printing, laser cutting, or photolithography — often without a cleanroom.
- Well-suited for point-of-care diagnostics, environmental monitoring, and educational use.
- Limitations: lower resolution, limited pressure tolerance, not reusable.

**Biodegradable polymers:**
- **PLA (polylactic acid):** Derived from renewable resources (corn starch, sugarcane). Compatible with 3D printing, laser cutting, and injection molding. Biodegradable under industrial composting conditions.
- **PLGA (poly(lactic-co-glycolic acid)):** Biodegradable membranes reaching >90% degradation within 6 weeks in wet conditions. Suitable for disposable diagnostic devices.
- **Cellulose derivatives, alginate, and chitosan:** Natural polymers offering biodegradability and biocompatibility for biological applications.

**Thermoplastics (recyclable):**
- PMMA, COC, COP, and polycarbonate are thermoplastics that can be recycled.
- Suitable for mass production via injection molding or hot embossing.
- Increasingly preferred over PDMS for commercial and high-volume applications.

**Other approaches:**
- Flexdym and other elastomeric alternatives designed for lower environmental impact.
- Digital microfluidics (electrowetting) can reduce reagent and device material consumption.

---

## 6. Emergency Procedures

### 6.1 HF Burns — Calcium Gluconate Treatment Protocol

**Immediate actions (do not delay — seconds matter):**

1. **Remove contaminated clothing** while flushing the affected area with copious water for at least 5 minutes (do not delay flushing to remove clothing if clothing removal is difficult).
2. **Apply 2.5% calcium gluconate gel** liberally to the affected area. Massage continuously for 15-30 minutes. Reapply every 10-15 minutes.
3. **Call emergency services and poison control** immediately, even if the burn appears minor. HF can cause systemic toxicity (hypocalcemia, cardiac arrhythmia) that may not manifest for hours.
4. **Monitor for pain relief.** If there is no significant pain relief within 30-40 minutes of gel application, subcutaneous injection of 5% calcium gluconate (0.5 mL per cm2 of affected area) may be necessary — this is a medical procedure performed by trained personnel.
5. **Hospital transport is mandatory** for:
   - Any exposure to concentrated HF (> 50%)
   - Burns covering more than 25 cm2 (roughly the size of a hand)
   - Any inhalation exposure
   - Any ingestion
   - Burns to the face, hands, feet, or groin

**Lab preparedness:**
- Calcium gluconate gel must be stored at the point of use and checked for expiration monthly.
- All personnel in HF-use areas must know the location of calcium gluconate and be trained in its application.
- Post the emergency protocol visibly at every HF work station.
- Blood sampling should be taken at the hospital to monitor fluoride, potassium, and calcium levels.

### 6.2 Chemical Spill Protocols

**Small spills (< 100 mL, non-HF, known composition):**

1. Alert nearby personnel.
2. Don appropriate PPE (gloves, goggles, lab coat at minimum).
3. Contain the spill with appropriate absorbent:
   - Acids: sodium bicarbonate or commercial acid neutralizer
   - Bases: citric acid or commercial base neutralizer
   - Solvents: vermiculite, chemical-specific absorbent pads, or commercial spill pillows
   - **Never use paper towels for piranha or strong oxidizer spills.**
4. Collect absorbed material into a compatible waste container.
5. Clean the area with appropriate solvent or water.
6. Report the spill per institutional requirements.

**Large spills (> 100 mL, unknown composition, or high-hazard chemicals):**

1. Evacuate the immediate area.
2. Alert others and restrict access.
3. If safe to do so, turn off ignition sources and close fume hood sashes.
4. Call institutional EHS/emergency response.
5. Do not attempt cleanup without professional assistance.

**HF spills — special protocol:**
- Evacuate immediately — even small HF spills generate dangerous vapor concentrations.
- Do not attempt cleanup unless specifically trained and equipped.
- Call emergency response and report as an HF incident.

### 6.3 Fire in Cleanroom

**Immediate actions:**
1. **Activate the fire alarm** using the nearest pull station.
2. **Evacuate** via the nearest safe exit. Do not stop to save experiments or equipment.
3. **Close doors** behind you to contain the fire and slow its spread.
4. **Do not use elevators.**
5. **Assemble** at the designated meeting point and report to emergency personnel.

**If the fire is small and you are trained:**
- Use the appropriate fire extinguisher:
  - **Class B (CO2 or dry chemical):** For solvent fires
  - **Class D (specialized):** For metal fires (lithium, magnesium, sodium)
  - **Never use water** on solvent fires, metal fires, or electrical fires
- Use the PASS technique: Pull pin, Aim at base, Squeeze handle, Sweep side to side.
- If the fire is not controlled within 30 seconds, evacuate immediately.

**Cleanroom-specific considerations:**
- HEPA filters and plastic cleanroom materials can generate toxic fumes when burning.
- Compressed gas cylinders in the fire zone are an explosion hazard — report their location to emergency responders.
- Chemical storage areas within the cleanroom may contain incompatible materials — inform firefighters of chemical inventories.

---

## Quick Reference: Emergency Contact Template

| Emergency | Contact |
|---|---|
| Fire / medical / hazmat | 911 (or local equivalent) |
| Institutional EHS | [Insert number] |
| Poison Control (US) | 1-800-222-1222 |
| HF Exposure Hotline | [Insert institutional protocol] |
| Laser Safety Officer | [Insert name and number] |
| Biosafety Officer | [Insert name and number] |
| After-hours emergency | [Insert number] |

> **Post this information visibly in every lab space. Every lab member should know these numbers.**

---

## References and Further Reading

- [UCSB Microfluidics Lab — Laser Cutter Training SOP](https://microfluidics.cnsi.ucsb.edu/wiki/doku.php?id=laser_cutter_training_sop)
- [Stanford Nanofabrication Facility — Microfluidic Device Fabrication Protocol](https://snfguide.stanford.edu/guide/projects/microfluidic-device-fabrication-protocol-and-troubleshooting-guide-in-stanford-flexible-cleanroom)
- [Yale University Cleanroom Core User Handbook](https://research.yale.edu/documents/cleanroom-handbook-40)
- [Auckland Microfab — Cleanroom Entry Guide](https://www.microfab.auckland.ac.nz/protocols/cleanroom-entry-guide/)
- [Weizmann Institute — Cleanroom Safety and Etiquette Regulations](https://www.weizmann.ac.il/ChemicalResearchSupport/sites/ChemicalResearchSupport/files/Wiezmann%20Cleanroom%20Training%20Manual%20Rev23.pdf)
- [University of Kentucky — Chemical Hazards for Piranha Solution](https://researchsafety.uky.edu/lab-safety/chemical-hazards-information/piranha-solution)
- [University of Illinois — Piranha Solutions Safety Library](https://drs.illinois.edu/page/safetylibrary/piranhasolutions)
- [Concordia University — Piranha Solution Safety Guidelines](https://www.concordia.ca/content/dam/concordia/services/safety/docs/EHS-DOC-019_PiranhaSolutionSafetyGuidelines.pdf)
- [Air Products — HF Burns Treatment Protocol (Safetygram 29)](https://www.airproducts.com/-/media/files/en/900/900-14-012-us-hydrofluoric-acid-burns-safetygram-29.pdf)
- [NCBI StatPearls — Hydrofluoric Acid Burns](https://www.ncbi.nlm.nih.gov/books/NBK441829/)
- [CDC NIOSH — Hydrogen Fluoride Emergency Response](https://www.cdc.gov/niosh/ershdb/emergencyresponsecard_29750030.html)
- [OSHA — Guidelines for Laser Safety and Hazard Assessment](https://www.osha.gov/enforcement/directives/std-01-05-001)
- [Cornell EHS — Human-Derived Materials Biological Agent Reference Sheet](https://ehs.cornell.edu/research-safety/biosafety-biosecurity/biological-safety-manuals-and-other-documents/bars-other/human-derived-materials)
- [Stanford EHS — Biosafety Manual: Tissue Culture](https://ehs.stanford.edu/manual/biosafety-manual/tissue-culture-human-and-primate-tissue)
- [University of Nevada Reno — Biosafety Manual Chapter 9: Human Tissue and Cell Culture](https://www.unr.edu/ehs/policies-manuals/biosafety-manual/chapter-9)
- [Thermo Fisher — Aseptic Laboratory Techniques and Safety in Cell Culture](https://www.thermofisher.com/us/en/home/references/gibco-cell-culture-basics/cell-culture-laboratory-safety.html)
- [ACS Sustainable Chemistry & Engineering — Environmental Impacts of Microfluidic Devices](https://pubs.acs.org/doi/10.1021/acssuschemeng.5c01511)
- [RSC Lab on a Chip — Engineering a Sustainable Future for Point-of-Care Diagnostics](https://pubs.rsc.org/en/content/articlehtml/2022/lc/d2lc00380e)
- [Frontiers — Lab-on-a-Chip: Fostering a Sustainable Future](https://www.frontiersin.org/journals/lab-on-a-chip-technologies/articles/10.3389/frlct.2023.1239134/full)
- [ScienceDirect — Biodegradable Polymer-Based Microfluidic Membranes](https://www.sciencedirect.com/science/article/pii/S1385894722031266)
- [Wiley Small — Biodegradable Polymers for Micro Elastofluidics](https://onlinelibrary.wiley.com/doi/full/10.1002/smll.202303435)
- [Elveflow — Biocompatible Polymers in Microfluidics](https://www.elveflow.com/blog/biocompatible-polymers-in-microfluidics-applications-insights/)
- [PMC — PDMS Microfabrication and Design for Microfluidics: Review](https://pmc.ncbi.nlm.nih.gov/articles/PMC8625467/)
