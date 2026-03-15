# Fabrication Recipes & Process Parameters

> Last updated: March 2026

## SU-8 Photoresist Processing

### SU-8 2000 Series — Thickness vs Spin Speed

| SU-8 Grade | Target Thickness | Spin Speed | Viscosity |
|-----------|-----------------|------------|-----------|
| SU-8 2002 | 2 µm | 3000 rpm | 7.5 cSt |
| SU-8 2005 | 5 µm | 3000 rpm | 45 cSt |
| SU-8 2010 | 10 µm | 3000 rpm | 380 cSt |
| SU-8 2015 | 15 µm | 3000 rpm | 1,250 cSt |
| SU-8 2025 | 25 µm | 3000 rpm | 4,500 cSt |
| SU-8 2035 | 40 µm | 3000 rpm | 7,000 cSt |
| SU-8 2050 | 50 µm | 3000 rpm | 12,900 cSt |
| SU-8 2075 | 75 µm | 3000 rpm | 22,000 cSt |
| SU-8 2100 | 100 µm | 3000 rpm | 45,000 cSt |
| SU-8 2150 | 200 µm | 3000 rpm | 80,000 cSt |

*Note: Exact thickness depends on spin speed. Higher spin speed = thinner film. Consult Kayaku datasheet for spin curve.*

### SU-8 2000 Process Parameters (Typical for 50-100 µm)

| Step | Parameter | 50 µm (SU-8 2050) | 100 µm (SU-8 2100) | Notes |
|------|-----------|-------------------|---------------------|-------|
| **Dehydrate** | 200°C | 5 min | 5 min | Always do this |
| **Spin coat** | Step 1: 500 rpm | 10 sec, 100 rpm/s ramp | 10 sec, 100 rpm/s ramp | Spread step |
| | Step 2: Final rpm | 3000 rpm, 30 sec | 3000 rpm, 30 sec | 300 rpm/s ramp |
| **Soft bake** | 65°C | 3 min | 5 min | Ramp from RT |
| | 95°C | 6 min | 20 min | Critical: ramp slowly (~2°C/min) |
| **Exposure** | i-line (365 nm) | 150-215 mJ/cm² | 240-260 mJ/cm² | Contact mode. Hard contact preferred. |
| **PEB** | 65°C | 1 min | 1 min | Start immediately after exposure |
| | 95°C | 6 min | 10 min | Ramp slowly to minimize stress |
| **Develop** | PGMEA immersion | 6-8 min | 10-15 min | Gentle agitation. Fresh developer. |
| **Rinse** | IPA | 10 sec | 10 sec | White residue = underdeveloped |
| **Hard bake** | 150-200°C | 15-30 min | 15-30 min | Optional. Makes mold more durable. |

### Critical SU-8 Tips

1. **Ramp temperatures slowly** — thermal shock causes cracks and stress
2. **Don't skip the 65°C pre-bake step** — direct jump to 95°C causes bubbles
3. **Exposure dose matters** — underexposure: poor adhesion, features lift off. Overexposure: T-topping (overhangs)
4. **PEB immediately after exposure** — don't leave exposed wafer sitting
5. **White residue in IPA rinse** = underdeveloped — put back in developer
6. **Edge bead removal** — wipe edges with clean-room wipe + acetone before baking
7. **Always silanize before PDMS casting** — or PDMS will stick permanently

---

## Alternative Photoresists for Microfluidics

### Dry Film Resists (No Spin Coater Needed!)

| Resist | Manufacturer | Thickness Range | Resolution | Key Advantage |
|--------|-------------|----------------|-----------|---------------|
| **Ordyl SY300/SY550** | Elga Europe | 15-100 µm | ~20 µm | Cheap, laminates at low temp, double-bond |
| **ADEX** | DJ MicroLaminates | 5-100+ µm | ~10-20 µm | Equivalent to SUEX, good for microfluidics |
| **SUEX** | DJ MicroLaminates | 100-500+ µm | ~25 µm | Very thick films without spin coating |
| **Riston** | DuPont | 15-50 µm | ~50 µm | PCB standard, widely available |
| **WLP-1000** | DuPont | 25-100 µm | ~20 µm | Wafer-level packaging resist |

**Dry film resist process:**
1. Laminate film onto substrate using office laminator (80-100°C)
2. UV expose through mask
3. Develop in Na₂CO₃ solution (1% w/v) — much safer than SU-8 developer
4. Can stack multiple layers for thicker structures

**Advantages over SU-8:**
- No spin coater needed (laminator instead)
- No cleanroom required
- Much cheaper
- Safer developer (aqueous Na₂CO₃ vs PGMEA)
- Better thickness uniformity over large areas
- Can be done outside cleanroom

**Limitations:**
- Lower aspect ratios than SU-8
- Fewer thickness options
- Less established in literature

### AZ Photoresists (Positive Tone)

| Resist | Type | Thickness | Use in Microfluidics |
|--------|------|-----------|---------------------|
| **AZ 4620** | Positive, thick | 5-20 µm | Sacrificial layers, thin channels |
| **AZ 50XT** | Positive, ultra-thick | 10-100 µm | Rounded channel profiles (reflow for Quake valves) |
| **AZ 40XT** | Positive | 5-40 µm | General purpose |
| **AZ nLOF** | Negative lift-off | 1-10 µm | Metal lift-off for electrodes |

### KMPR

- Kayaku (formerly MicroChem) negative photoresist
- Alternative to SU-8 with easier stripping
- Good for sacrificial structures
- Available in 10-100+ µm thicknesses

---

## PDMS (Sylgard 184) Casting Protocol

### Materials Needed

| Item | Source | Approx. Cost |
|------|--------|--------------|
| Sylgard 184 kit (1.1 kg) | Dow (via Fisher/Ellsworth/Darwin) | ~$150-300 |
| Plastic cups for mixing | Lab supply | $5/100 |
| Stir stick | Lab supply | — |
| Vacuum desiccator + pump | Lab supply | $300-1,500 |
| Hot plate or oven | Lab supply | $200-2,000 |
| Biopsy punches (1.0, 1.5 mm) | Miltex/Harris | $30-50/pack |
| Scotch tape | Office supply | $5 |
| Scalpel/razor blade | Lab supply | $5 |
| Aluminum foil (for mold dish) | Kitchen | $5 |

### Standard Protocol

```
1. WEIGH
   - Base : Curing agent = 10:1 by weight
   - Typical batch: 30g base + 3g curing agent = 33g total
   - 33g ≈ fills a 100mm petri dish to ~5mm depth

2. MIX
   - Stir vigorously for 3-5 minutes
   - Will become very bubbly — this is normal
   - Ensure complete mixing (streaks visible = not mixed enough)

3. DEGAS
   - Place in vacuum desiccator
   - Pump down slowly (bubbles will rise and expand)
   - If bubbles threaten to overflow: release vacuum briefly, then re-pump
   - Continue until all bubbles are gone (30-60 minutes)
   - Tip: Larger containers degas faster (more surface area)

4. POUR
   - Pour slowly over mold to minimize new bubble introduction
   - Target thickness: ~5mm for handling (thinner = harder to peel)
   - Tip: Use aluminum foil dish around mold to contain PDMS

5. DEGAS AGAIN (optional)
   - Brief vacuum (10-15 min) to remove any bubbles from pouring
   - Especially important if mold has deep features that trap air

6. CURE
   - 65°C for 4 hours (standard)
   - 80°C for 2 hours (faster)
   - 100°C for 45 min (fastest, may cause some feature distortion)
   - Room temperature for 48 hours (if no oven available)

7. PEEL
   - Let cool to room temperature
   - Cut around mold with scalpel
   - Peel from one corner, slowly
   - If stuck: soak edge with IPA to help release

8. PUNCH PORTS
   - Use sharp biopsy punch (1.0 or 1.5 mm)
   - Punch from feature side (channels facing up)
   - Push straight through, don't twist
   - Remove plug with tweezers
   - Tip: Use punches once or twice only — dull punches tear PDMS

9. CLEAN
   - Remove debris: press scotch tape on channel side, peel off
   - Blow with N₂ gun
   - Optional: rinse with IPA, dry with N₂
```

### Alternative PDMS Ratios

| Ratio (Base:Curing) | Young's Modulus | Notes |
|---------------------|-----------------|-------|
| **5:1** | ~3-4 MPa | Stiffer, less gas permeable |
| **10:1** (standard) | ~1.5-2 MPa | Standard, well-characterized |
| **15:1** | ~0.5-1 MPa | Softer, better for valves |
| **20:1** | ~0.1-0.5 MPa | Very soft, used for mechanobiology |
| **30:1** | <0.1 MPa | Ultra-soft, limited use |

---

## Plasma Bonding Protocol

### O₂ Plasma Bonding (Recommended)

**Equipment options:**
- Harrick PDC-32G (~$5,000) — most common in academia
- Harrick PDC-001 (~$3,500) — lower power version
- Diener Zepto (~$8,000-12,000) — higher throughput
- Henniker HPT-100 (~$10,000) — variable gas input

**Protocol:**
```
1. PREPARE SURFACES
   - Clean PDMS with scotch tape + N₂ blow
   - Clean glass slide: acetone → IPA → DI water → N₂ dry
   - Both surfaces must be DUST-FREE

2. PLASMA TREAT
   - Place PDMS (channel side up) and glass in plasma chamber
   - Pump down to base pressure (<200 mTorr)
   - Introduce O₂ (if available) or use air plasma
   - Settings: 30 W power, 30-60 seconds
   - For Harrick: use "Medium" power setting

3. BOND
   - Remove from plasma within 10-20 seconds
   - Bring PDMS channel side down onto glass
   - Place carefully — once surfaces touch, they bond immediately
   - Press gently to remove trapped air
   - DO NOT slide surfaces — this smears the bond

4. POST-BOND BAKE
   - Place on hot plate at 65°C for 10-30 minutes
   - Overnight at 65°C gives strongest bond (>300 kPa)

5. VERIFY
   - Try to peel corner — should be very difficult to separate
   - If easy to peel: plasma time was too short, power too low,
     or surfaces were dirty
```

### Corona Discharge Bonding (Cheap Alternative)

**Equipment:** Electro-Technic BD-20AC handheld corona treater (~$200)

**Protocol:**
```
1. Clean surfaces as above
2. Hold BD-20AC ~1 cm from surface
3. Wave slowly over PDMS surface for 30-60 seconds
4. Wave slowly over glass surface for 30-60 seconds
5. Bring into contact within 30 seconds
6. Press gently, bake at 65°C for 1 hour
```

**Notes:**
- Cheaper than plasma cleaner but less reproducible
- Bond strength ~70-80% of O₂ plasma
- Good enough for most prototyping
- Replace tip regularly

### Bond Strength Comparison

| Method | Bond Strength | Reproducibility | Cost |
|--------|-------------|-----------------|------|
| O₂ plasma (30W, 30s) | >300 kPa | High | $5,000-12,000 (equipment) |
| O₂ plasma (+ bake 65°C overnight) | >400 kPa | High | Same |
| Corona discharge (BD-20AC) | 200-300 kPa | Medium | ~$200 |
| UV ozone | 200-300 kPa | Medium | $3,000-8,000 |
| APTES treatment | >400 kPa | High | Chemicals + plasma |
| No treatment (just pressing) | <50 kPa | Low | Free (reversible bond) |

---

## Mask Design Tips

### For Film Masks (Printed)

| Parameter | Recommendation |
|-----------|---------------|
| Minimum feature | >10 µm (practical: >20 µm) |
| Format | High-resolution PDF or DXF at 20,000+ DPI |
| Polarity | Dark-field for negative resist (SU-8): features are clear |
| Border | Add 5mm clear border around design |
| Alignment marks | Include on every layer |
| Scale bar | Always include for verification |

### For Chrome Masks

| Parameter | Recommendation |
|-----------|---------------|
| Minimum feature | 1-2 µm |
| Format | GDSII or CIF |
| Substrate | 4" or 5" soda-lime glass, 0.090" thick |
| Chrome thickness | ~100 nm Cr + ~200 nm anti-reflection coating |
| Defect spec | <1 defect/cm² for critical features |

### Where to Order

| Vendor | Type | Typical Price | Lead Time | Resolution |
|--------|------|-------------|-----------|-----------|
| **CAD/Art Services** | Film (transparency) | $50-100 | 2-3 days | 10-20 µm |
| **OutputCity** | Film | $30-80 | 3-5 days | 15-25 µm |
| **Front Range Photomask** | Chrome | $200-500 | 1-2 weeks | 1-2 µm |
| **Compugraphics** | Chrome | $300-800 | 1-2 weeks | 0.5-1 µm |
| **Photo Sciences** | Chrome | $200-600 | 1-2 weeks | 1-2 µm |
| **Heidelberg Instruments** (in-house) | Direct write | — | Same day | 0.5-1 µm |

---

## Quick Reference: Common Channel Dimensions

| Application | Typical Width | Typical Height | Material |
|------------|--------------|----------------|----------|
| Simple mixer | 100-500 µm | 50-100 µm | PDMS |
| Droplet generator | 20-100 µm | 20-50 µm | PDMS, glass |
| Cell culture | 200-1000 µm | 100-200 µm | PDMS, COC |
| Capillary electrophoresis | 20-50 µm | 10-20 µm | Glass |
| Particle sorting (inertial) | 50-200 µm | 25-100 µm | PDMS |
| Organ-on-chip | 200-1000 µm | 100-500 µm | PDMS, COC |
| Gradient generator | 100-300 µm | 50-100 µm | PDMS |
| PCR on chip | 50-200 µm | 20-100 µm | Glass, COC |
| Nanofluidics | 0.01-1 µm | 0.01-1 µm | Silicon, glass |
