# Competitive Analysis — Gas Detection Technologies

## Technology Comparison

### NDIR (Non-Dispersive Infrared)
- **How it works:** Broadband IR source → gas sample → optical bandpass filter → IR detector
- **Cost:** $80-300 per sensor
- **Detection limit:** ~100 ppm
- **Pros:** Cheap, simple, well-established, no consumables
- **Cons:** Single gas per sensor, poor selectivity (broad filter), no specificity between similar gases (CH4 vs ethane)
- **Market:** Dominant for single-gas applications (residential CO detectors, industrial point sensors)

### TDLAS (Tunable Diode Laser Absorption Spectroscopy)
- **How it works:** Tunable laser scans across gas absorption line → measures absorption dip
- **Cost:** $5,000-50,000
- **Detection limit:** ppb to ppt
- **Pros:** Extremely sensitive, species-specific, fast response
- **Cons:** One gas per laser, expensive, complex alignment
- **Market:** High-end process monitoring, emissions compliance

### QEPAS (Quartz-Enhanced Photoacoustic Spectroscopy)
- **How it works:** QCL laser excites gas molecules → acoustic wave detected by quartz tuning fork
- **Cost:** $10,000-30,000
- **Detection limit:** ppb
- **Pros:** Very sensitive, compact
- **Cons:** Requires expensive QCL source, single gas per laser, vibration-sensitive
- **Market:** Research, specialized applications

### FTIR (Fourier Transform Infrared Spectroscopy)
- **How it works:** Broadband IR → Michelson interferometer (moving mirror) → sample → IR detector → Fourier transform
- **Cost:** $30,000-150,000
- **Detection limit:** Low ppm
- **Pros:** Sees entire spectrum, identifies unknown gases, multi-gas, well-established
- **Cons:** Moving mirror (failure point in harsh environments), expensive MCT detector needs cooling, complex data processing, bulky, requires trained operator
- **Market:** Lab analysis, open-path fence-line monitoring, HazMat identification

### SFG Detection Platform (This Device)
- **How it works:** Mid-IR → PPLN waveguide array + pump laser → SFG upconversion → silicon detector array
- **Cost:** ~$16,000-30,000 (estimated)
- **Detection limit:** TBD (target: match NDIR at minimum, approach TDLAS with optimization)
- **Pros:** Multi-gas simultaneous, no moving parts, cheap silicon detectors (room temp), physics-based selectivity (32-80 dB), simple output ("which channel dimmed"), field-rugged
- **Cons:** Higher cost than NDIR, detection limits not yet proven, limited to pre-tuned gases (can't detect unknowns like FTIR), new technology (no field track record)

## Where SFG Wins

1. **vs NDIR:** Multi-gas from one device. Better selectivity (32-80 dB suppression vs broad optical filter). Can distinguish CH4 from ethane.
2. **vs TDLAS:** Multi-gas simultaneous (TDLAS needs one laser per gas). Much simpler system.
3. **vs FTIR:** No moving parts. Room-temperature detectors. Survives vibration, impacts, temperature cycling. No trained spectroscopist needed.
4. **vs all:** Solid-state durability for harsh environments where other instruments fail.

## Where SFG Loses

1. **vs NDIR on cost:** NDIR is 10-50x cheaper for single-gas detection.
2. **vs TDLAS on sensitivity:** TDLAS reaches parts-per-trillion. SFG probably tops out at low ppm or ppb.
3. **vs FTIR on flexibility:** FTIR sees the entire spectrum. New gas shows up? FTIR catches it. SFG only sees pre-tuned wavelengths.

## Market Positioning

The SFG device is not the cheapest, most sensitive, or most flexible option. It is the most durable multi-gas detector for environments that destroy conventional instruments.

**Target customer:** Anyone who needs multi-gas detection in harsh environments where FTIR breaks and NDIR can't tell gases apart.
