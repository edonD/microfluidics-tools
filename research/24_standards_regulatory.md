# Standards, Regulations & Quality for Microfluidic Devices

> Last updated: March 2026

## Microfluidic Industry Standards

### ISO 22916:2022 — Microfluidic Device Interoperability

The first international standard specifically for microfluidics:

**Full title:** "Microfluidic devices — Interoperability requirements for dimensions, connections and initial device classification"

**What it covers:**
1. **Standardized dimensions** for microfluidic chips to enable cross-platform compatibility
2. **Connection specifications** — standard port positions, sizes, and thread types
3. **Device classification** — categories for identifying and comparing microfluidic devices

**Key chip dimensions defined:**
- Standard chip footprints (similar to well plate format compatibility)
- Port positions and numbering
- Connection interface specifications

**Status:** Published 2022. Revision in progress (ISO/AWI 22916).

**Why it matters:** Before this standard, every vendor had different chip sizes, port positions, and connector types. ISO 22916 begins to address interoperability — meaning a chip from Dolomite could potentially work with connectors from IDEX and holders from Micronit.

### Related Standards

| Standard | Title | Relevance |
|----------|-------|-----------|
| **ISO 22916:2022** | Microfluidic devices — Interoperability | Core microfluidics standard |
| **ISO 10991:2009** | Micro process engineering — Vocabulary | Terminology definitions |
| **IEC 62047** series | MEMS standards | Semiconductor-based devices |
| **ISO 14644** | Cleanrooms and controlled environments | Fabrication environment |
| **ISO 13485:2016** | Medical devices — Quality management | Required for medical microfluidics |
| **ISO 14971:2019** | Medical devices — Risk management | Risk analysis for medical devices |
| **ISO 10993** series | Biological evaluation of medical devices | Biocompatibility testing |
| **IEC 62304** | Medical device software lifecycle | Software in microfluidic instruments |

---

## Regulatory Pathways for Microfluidic Medical Devices

### US FDA Pathways

| Pathway | Risk Class | Timeline | Cost | When to Use |
|---------|-----------|----------|------|-------------|
| **510(k)** | Class II (moderate risk) | 90 days (review) + 4-6 months typical | $12,000-$50,000+ | Device is "substantially equivalent" to an existing cleared device |
| **De Novo** | Class I/II (novel, low-moderate risk) | 6-12 months | $30,000-$100,000+ | New device type, no predicate, but low risk |
| **PMA** | Class III (high risk) | 12-24+ months | $100,000-$500,000+ | Highest risk. Requires clinical trials. Rare for microfluidics. |
| **EUA** | Any | Weeks (emergency) | Variable | Emergency use only (e.g., COVID-19 diagnostics) |

**Most microfluidic diagnostics use 510(k)** — demonstrating substantial equivalence to existing cleared lab-on-chip or point-of-care devices.

### EU CE Marking (MDR/IVDR)

| Regulation | Scope | Key Requirements |
|-----------|-------|-----------------|
| **EU MDR 2017/745** | Medical devices | Technical documentation, clinical evaluation, post-market surveillance |
| **EU IVDR 2017/746** | In-vitro diagnostics | Performance evaluation, clinical evidence, notified body certification |

**Key changes since IVDR (2022):**
- Most IVD microfluidic devices now require **Notified Body** certification (previously self-certified)
- Higher requirements for clinical evidence
- Class A-D risk classification (Class D highest, e.g., blood screening)

### Regulatory Cost Estimates for Microfluidic Diagnostics

| Phase | Activity | Estimated Cost |
|-------|----------|---------------|
| **Design controls** | Design history file (DHF), design reviews | $20,000-50,000 |
| **Quality system** | ISO 13485 certification | $20,000-50,000 (initial) |
| **Risk analysis** | ISO 14971 risk management | $10,000-30,000 |
| **Biocompatibility** | ISO 10993 testing | $20,000-100,000 |
| **Performance testing** | Analytical validation | $30,000-100,000 |
| **Clinical evaluation** | Clinical studies (if needed) | $50,000-500,000+ |
| **Regulatory submission** | 510(k) preparation and review | $30,000-100,000 |
| **CE Marking** | Technical file + Notified Body | $50,000-200,000 |
| **Post-market surveillance** | Ongoing | $10,000-30,000/yr |
| **Total (US + EU)** | | **$250,000-1,200,000** |

---

## Quality Management for Microfluidic Manufacturing

### ISO 13485 Requirements

If manufacturing microfluidic devices for medical/diagnostic use:

1. **Quality Management System** — documented procedures for design, manufacturing, testing
2. **Design Controls** — design input/output/verification/validation/review
3. **Supplier Controls** — qualify material suppliers (PDMS, COC, reagents)
4. **Process Validation** — validate fabrication processes (IQ/OQ/PQ)
5. **Traceability** — track every chip from raw materials to customer
6. **CAPA** — corrective and preventive action system
7. **Management Review** — regular quality reviews

### Cleanroom Classification (ISO 14644)

| ISO Class | Particles ≥0.5 µm per m³ | Typical Use |
|-----------|--------------------------|-------------|
| ISO 1 | 10 | Semiconductor fab (not typical for microfluidics) |
| ISO 5 | 3,520 | Photolithography, critical processes |
| ISO 6 | 35,200 | General microfluidic fabrication |
| ISO 7 | 352,000 | Assembly, bonding, packaging |
| ISO 8 | 3,520,000 | General lab work |

**Most microfluidic fabrication:** ISO 5-7 cleanroom is sufficient. ISO 5 for photolithography, ISO 7 for assembly/bonding.

---

## Certification Bodies & Services

| Organization | Service | Location |
|-------------|---------|----------|
| **TÜV SÜD** | Notified Body (EU), ISO 13485 | Germany/Global |
| **BSI** | Notified Body (EU), ISO 13485 | UK/Global |
| **SGS** | Testing, certification | Switzerland/Global |
| **Intertek** | Testing, CE marking | UK/Global |
| **NSF International** | FDA registration support | USA |
| **Emergo by UL** | Regulatory consulting | Global |

---

## Good Practices for Research Labs (Pre-Regulatory)

Even for non-regulated research, adopting these practices early saves pain later:

1. **Document everything** — fabrication parameters, lot numbers, test results
2. **Use batch tracking** — label every chip with batch ID, date, operator
3. **Define acceptance criteria** — what makes a "good" chip? Document it.
4. **Validate your process** — show it's reproducible (n ≥ 3 batches, n ≥ 10 devices per batch)
5. **Control materials** — use same PDMS lot, same photoresist lot, same wafer supplier
6. **Calibrate instruments** — annual calibration of pumps, pressure controllers, flow sensors
7. **Keep a lab notebook** — physical or electronic, dated and signed

### Common Regulatory Pitfalls in Microfluidics

1. **PDMS not suitable for production** — Regulators prefer established manufacturing processes (injection molding). PDMS is fine for research but hard to validate for manufacturing.
2. **Material biocompatibility** — Even "biocompatible" materials need ISO 10993 testing in your specific device configuration.
3. **Lot-to-lot variability** — Photoresist batch changes, PDMS batch changes, resin batch changes can all affect device performance.
4. **Surface treatment shelf life** — Plasma-treated PDMS loses hydrophilicity in hours-days. Need stable surface treatment for products.
5. **Bonding reliability** — Must demonstrate bond strength doesn't degrade over shelf life.
6. **Sterilization validation** — Must prove sterilization doesn't alter device function.
