# Build Plan — SFG Energy Monitor

Detailed procurement and assembly guide for the SFG multi-gas detection prototype. Designed for ease of manufacturing — start simple, upgrade iteratively.

## Bill of Materials

### A. Mid-IR Source

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| A1 | MEMS thermal emitter | Micro-Hybrid JSIR350 / Axetris | $50-100 | Broadband 2-10 um, pulsable, tiny |
| A2 | CaF2 collimating lens | Thorlabs LA5370 (25mm f/40mm) | $80-150 | Transparent 0.2-8 um |
| A3 | CaF2 windows (x2) | Thorlabs WG50530 | $60-100 ea | Gas cell windows |
| A4 | Alt: Mid-IR LED (CH4) | LED Microsensor NT / Roithner | $50-200 | Narrowband, single gas |

### B. Gas Cell

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| B1 | Single-pass cell | Custom aluminum tube + CaF2 windows | $50-200 | 10-30 cm path, good for % levels |
| B2 | Multi-pass Herriott cell | Thorlabs HC10L (10.4m path) | ~$3,000 | For ppm-level detection |
| B3 | Alt: Long-path Herriott | Thorlabs HC30L (31.2m path) | ~$4,500 | For ppb-level detection |

### C. PPLN Crystals

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| C1 | Bulk PPLN (start here) | Covesion MSFG976-0.5 multi-grating | $1,000-2,500 | Multiple QPM periods on one chip |
| C2 | PPLN temperature oven | Covesion PV40 + mount | $800-1,200 | Temp control +/- 0.1C |
| C3 | Alt: Custom waveguide chip | HC Photonics (4-period bare chip) | $3,000-8,000 | Higher efficiency, 8-16 wk lead |
| C4 | Alt: Custom waveguide chip | AdvR Inc (multi-channel array) | $3,000-10,000 | Best US supplier for custom QPM |

**Start with C1 (bulk crystal).** Alignment tolerance is ~100x more forgiving than waveguides (50 um beam vs 5 um). Validate SFG first, upgrade to waveguides later.

### D. Pump Laser (1064 nm)

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| D1 | Fiber-coupled DBR | Thorlabs DJ1064 (70mW, PM fiber) | $1,500-2,500 | Single-frequency, recommended |
| D2 | Alt: Higher power | CNI MGL-FN-1064 (500mW) | $800-1,500 | Budget option, free-space output |
| D3 | Alt: Yb fiber laser | IPG / NKT Koheras BASIK | $5,000-15,000 | Premium, highest stability |

### E. Detection

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| E1 | Si photodiode (x4) | Hamamatsu S1227-1010BQ | $20-50 ea | High QE at 800-870 nm |
| E2 | Bandpass filters (x4) | Thorlabs FB-series (10nm BW) | $80-120 ea | One per SFG channel |
| E3 | Amplified detector | Thorlabs PDA100A2 | $400-500 ea | Integrated TIA, easy to use |
| E4 | Alt: Si SPAD | Excelitas SPCM / Hamamatsu S14160 | $2,000-5,000 | Single-photon sensitivity |

### F. Coupling Optics

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| F1 | Mid-IR focusing lens | Thorlabs LA5714 (CaF2, f=40mm) | $100-150 | Couples mid-IR into PPLN |
| F2 | Dichroic combiner | Thorlabs DMSP1000 | $200-400 | Combines 1064nm pump + mid-IR |
| F3 | 1064nm cleanup filter | Thorlabs FEL0850 longpass | $80 | Blocks residual pump after PPLN |
| F4 | Fiber collimator (1064) | Thorlabs F220APC-1064 | $150-250 | PM fiber to free-space |

### G. Signal Recovery

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| G1 | Optical chopper | Thorlabs MC2000B | $800-1,200 | Modulates mid-IR source |
| G2 | Lock-in amplifier | Stanford Research SR830 (used) | $1,500-3,000 | ~100x SNR improvement |
| G3 | Alt: DIY lock-in | Software demodulation + chopper ref | $0 | Harder but free |

Lock-in detection is critical for extracting weak SFG signals from noise. A used SR830 on eBay is the single best investment for signal quality.

### H. Infrastructure

| # | Component | Part / Supplier | Est. Cost | Notes |
|---|-----------|----------------|-----------|-------|
| H1 | Optical breadboard | Thorlabs MB1218 (12"x18") | $200-400 | |
| H2 | Post holders, mounts | Thorlabs assorted | $200-400 | |
| H3 | Arduino/RPi + ADC | Arduino Mega + ADS1115 | $30-60 | Data acquisition |
| H4 | Calibration gases | Cal Gas Direct | $100-200 | Per gas, per canister |

## Cost Summary

| Build Level | Scope | Estimated Total |
|-------------|-------|----------------|
| **Minimum viable** | 1 gas (CO2), bulk PPLN, single-pass cell, Si photodiode | **$4,000-7,000** |
| **3-4 gas prototype** | Multi-period bulk PPLN, Herriott cell, lock-in detection | **$12,000-20,000** |
| **Full 4-gas demo** | PPLN waveguide array, SPAD detection, all calibration gases | **$25,000-45,000** |

These estimates are 20-40% lower than original testing-plan.md projections because of the "start with bulk PPLN" strategy and specific part selection.

## Supplier Directory

| Component | Primary Supplier | Alt Supplier | How to Order |
|-----------|-----------------|-------------|-------------|
| PPLN waveguide chips | HC Photonics (hcphotonics.com) | AdvR Inc (advr-inc.com) | Email RFQ, 8-16 wk lead |
| Bulk PPLN crystals | Covesion (covesion.com) | Raicol Crystals (raicol.com) | Online store or RFQ |
| PPLN oven/mount | Covesion PV40 series | HC Photonics | Online store |
| 1064 nm laser | Thorlabs (thorlabs.com) | CNI Laser (cnilaser.com) | Online store |
| MEMS IR emitter | Micro-Hybrid (micro-hybrid.de) | Axetris (axetris.com) | Email/distributor |
| Mid-IR LEDs | LED Microsensor NT (lmsnt.com) | Roithner Laser (roithner-laser.com) | Online store |
| CaF2/ZnSe optics | Thorlabs | Edmund Optics, ISP Optics | Online store |
| Si photodiodes | Hamamatsu | Thorlabs, ON Semi | Online/distributor |
| Si SPADs | Excelitas SPCM series | Hamamatsu S14160 | Distributor/RFQ |
| Lock-in amplifier | Stanford Research SR830 | Zurich Instruments | New or used (eBay) |
| Breadboard/mounts | Thorlabs | Newport/MKS | Online store |
| Calibration gases | Cal Gas Direct | MESA Gas | Online store |

## Assembly Instructions

### Phase 1: Optical Bench Setup
1. Mount breadboard on a vibration-damped surface (rubber feet on solid table is fine for prototyping)
2. Establish a single optical axis along the length of the board
3. All components mount at the same beam height (use 3" posts + post holders)

### Phase 2: Mid-IR Source
1. Mount the MEMS emitter (A1) in a Thorlabs lens tube
2. Place CaF2 collimating lens (A2) one focal length from emitter
3. Place optical chopper (G1) in the collimated beam for lock-in detection
4. **Verify:** Thermal power meter should show ~1-5 mW broadband mid-IR in collimated beam

### Phase 3: Gas Cell
**Simple single-pass cell (start here):**
1. Aluminum tube, 20-30 cm long, 1" diameter
2. Epoxy CaF2 windows on each end (Torr Seal or similar vacuum-compatible epoxy)
3. Drill and tap two holes for gas inlet/outlet (1/4" Swagelok fittings)
4. Connect to calibration gas cylinder via regulator

**Upgrade path:** Replace with Thorlabs HC10L/HC30L Herriott cell for 100-300x longer path length.

**Rapid prototyping option:** 3D print the cell body. For atmospheric-pressure single-pass at room temperature, PLA or PETG works fine. Machine aluminum only when you need leak-tight or multi-pass.

### Phase 4: PPLN + Pump Laser

This is the trickiest part. The mid-IR signal and 1064 nm pump must be spatially overlapped and co-propagate through the crystal.

1. Mount PPLN crystal in its temperature-controlled oven (C2). Set to 25C initially.
2. Collimate pump laser using fiber collimator (F4). Align along the optical axis.
3. Combine beams using dichroic mirror (F2): reflects 1064 nm, transmits mid-IR.
4. Focus both beams into PPLN crystal using CaF2 lens (F1). Target beam waist: ~50-100 um for bulk PPLN.
5. **Alignment procedure:**
   - First: align 1064 nm pump through crystal (visible with IR card at output)
   - Then: overlap mid-IR beam using dichroic mirror adjusters
   - Monitor output with silicon detector — signal at 800-870 nm = SFG achieved
6. Temperature tune oven to maximize SFG output for target gas wavelength (~0.5 nm/C tuning rate)

### Phase 5: Detection / Readout
1. After PPLN, place short-pass filter to block residual 1064 nm pump and unconverted mid-IR
2. For single-gas: bandpass filter + Si photodiode directly
3. For multi-gas: diffraction grating or prism to spatially separate SFG wavelengths, then bandpass filter + Si photodiode at each output
4. Connect photodiodes to transimpedance amplifiers -> ADC -> microcontroller
5. Feed chopper reference to lock-in amp; demodulate each channel at chopper frequency

### Phase 6: Multi-Gas Operation

**Option A — Sequential (simplest, start here):**
- Single bulk PPLN with one QPM period
- Temperature-tune to scan across different gas lines (~1-2 sec per gas)
- Cheapest, validates full signal chain

**Option B — Multi-grating (recommended upgrade):**
- Covesion multi-grating chip: slide crystal laterally to select different QPM periods
- Each position monitors a different gas
- Faster than temperature scanning

**Option C — Parallel waveguide array (target design):**
- Multi-period PPLN waveguide chip (HC Photonics or AdvR)
- Split mid-IR beam into parallel channels
- All gases monitored simultaneously
- Requires custom chip order

## Phased Build Schedule

| Phase | Duration | Activities | Long-Lead Orders |
|-------|----------|-----------|-----------------|
| Week 1-2 | Procurement | Order optics + laser + bulk PPLN from Thorlabs/Covesion | PPLN waveguides from HC Photonics (8-16 wk) |
| Week 2-4 | Source + Cell | Build mid-IR source chain, build gas cell, validate transmission | |
| Week 4-6 | SFG Core | Add PPLN + pump, achieve first SFG signal | |
| Week 6-8 | Calibration | Calibrate against known CO2 concentrations | |
| Week 8+ | Multi-gas | Add second gas channel, begin expansion | Waveguide chips arrive |

## Mid-IR Fiber Options (For Packaged System)

Skip fiber coupling during prototyping (use free-space optics). When packaging:

| Fiber Type | Wavelength Range | Supplier | Cost | Use For |
|-----------|-----------------|----------|------|---------|
| InF3 (fluoroindate) | 0.3-5.5 um | Thorlabs | $200-800/cable | CH4, CO2, CO, H2S (all < 5 um) |
| ZBLAN (ZrF4) | 0.3-4.5 um | Thorlabs | $150-600/cable | CH4, H2S only |
| Chalcogenide (As2Se3) | 1.5-10 um | IRflex IRF-Se series | $500-2,000/cable | NO2 (6.17 um), SO2 (7.35 um) |

For the energy application (all targets < 5 um), Thorlabs InF3 fiber covers everything.
