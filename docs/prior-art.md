# Prior Art — SFG Upconversion Gas Detection

Published work validating the exact architecture used in this project: PPLN sum-frequency generation to upconvert mid-IR gas absorption signals to silicon-detectable wavelengths.

## Demonstrated Systems

### CO Detection via PPLN SFG Upconversion (2025)

**Source:** arXiv:2601.15981 — "Mid-infrared high-sensitive cavity-free in-situ CO gas sensing based on up-conversion detection"

- Architecture: DFG in 20mm PPLN (period 27.21 um) generates mid-IR, passes through CO gas, upconverted in 40mm PPLN (period 23 um) to **861 nm**, detected by Si photodetector
- **Detection limit: 79.6 ppb** with 14 cm path length and 70s integration
- Real-time detection at 1 kHz achieved **1.47 ppm precision**
- No cryogenic detectors, no optical cavity, room-temperature silicon detection
- Directly validates our approach for CO at 4.6 um

### Methane Remote Sensing via PPLN Waveguide Upconversion (2025)

**Source:** ResearchGate — "Remote methane sensing using single-photon PPLN-waveguide upconversion lidar"

- PPLN waveguide upconversion of 1651 nm methane absorption to **799 nm**
- Detected by silicon single-photon counting detector (SPAD)
- **Internal upconversion efficiency: 86%** in waveguide geometry
- Demonstrates that PPLN waveguides achieve dramatically higher efficiency than bulk crystals
- Validates our upgrade path from bulk PPLN to waveguide chips

### CO2 Upconversion Detection (2023)

**Source:** ScienceDirect — "Ultra-sensitive mid-wavelength-infrared upconversion detector"

- QCL signal photons at 4604-4616 nm upconverted to **864 nm** using PPLN with 1064 nm pump
- Detected by silicon single-photon avalanche detector (SPAD)
- Demonstrates SFG upconversion of mid-IR CO2 absorption wavelengths to silicon range
- Uses the same 1064 nm pump wavelength as our design

### Broadband Mid-IR Upconversion Spectroscopy

**Source:** ResearchGate — "Broadband mid-infrared frequency upconversion and spectroscopy with an aperiodically poled LiNbO3 waveguide"

- Aperiodically poled LiNbO3 waveguide provides broadband phase matching
- Enables simultaneous upconversion of multiple mid-IR wavelengths
- Relevant to our multi-gas concept: one aperiodic waveguide could replace multiple single-period waveguides

### MWIR Upconversion for Gas Spectroscopy — Fraunhofer (2023)

**Source:** Fraunhofer — "MWIR upconversion detection for infrared gas spectroscopy"

- Mid-wavelength infrared upconversion detection specifically for gas spectroscopy applications
- Institutional validation from a major applied research organization

## Funded Projects

### NUTMEG — Nonlinear Upconversion Technique for Monitoring Environmental Gases

**Source:** Covesion (covesion.com/knowledge-hub/) — Innovate UK funded project

- Partners: Covesion + QLM Technology
- Started: August 2024, 18-month project
- Goal: **Briefcase-sized portable sensor** for CO2, CH4, NOx, and NH3
- Architecture: PPLN waveguide upconversion to silicon single-photon detectors
- Expected commercial availability: ~2026
- **This is our exact architecture, funded by the UK government, being built by PPLN manufacturers themselves**

### MIRUS — Mid-IR Upconversion Single-Photon Detection

**Source:** Covesion (covesion.com/about-us/research-projects/)

- Developing packaged PPLN waveguide modules for upconversion from 3.4 um to ~1 um
- Focus on module packaging for practical deployment
- Directly relevant to our transition from lab prototype to field device

## Key Validation Points

1. **The physics works.** Multiple independent groups have demonstrated PPLN SFG upconversion of mid-IR gas absorption to silicon-detectable wavelengths.

2. **The sensitivity is real.** 79.6 ppb CO detection with only 14 cm path — our multi-pass Herriott cell (10-31 m) would improve this by 70-220x.

3. **The efficiency scales.** 86% internal upconversion efficiency in PPLN waveguides — validates our upgrade path from bulk crystals to waveguide chips.

4. **Industry is building this.** Covesion (a PPLN manufacturer) is building a portable multi-gas sensor using this exact approach with UK government funding.

5. **Room-temperature silicon detection.** Every cited system uses silicon detectors (photodiodes or SPADs) at room temperature. No cryogenic cooling required.

## Competitive Implications

The NUTMEG project (Covesion + QLM) is the closest competitor — same architecture, funded, with PPLN manufacturing capability in-house. Their timeline suggests commercial devices by 2026.

Our differentiation:
- **Harsh environment focus** — NUTMEG targets environmental monitoring; we target offshore O&G, military CBRN, mining
- **Directional detection** — our spherical array concept adds source localization, which no one else is pursuing
- **Dual-use platform** — same PPLN hardware serves energy, environmental, telecom, and health applications

## Citation Format

For papers referencing this prior art:

```bibtex
@article{sfg_co_2025,
  title={Mid-infrared high-sensitive cavity-free in-situ CO gas sensing based on up-conversion detection},
  year={2025},
  journal={arXiv},
  eprint={2601.15981}
}

@article{sfg_ch4_lidar_2025,
  title={Remote methane sensing using single-photon PPLN-waveguide upconversion lidar},
  year={2025},
  journal={ResearchGate},
  note={DOI pending}
}

@article{sfg_co2_spad_2023,
  title={Ultra-sensitive mid-wavelength-infrared upconversion detector},
  year={2023},
  journal={Optics and Laser Technology},
  publisher={ScienceDirect}
}
```
