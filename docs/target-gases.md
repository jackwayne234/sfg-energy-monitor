# Target Gases and Detection Specifications

## Primary Targets

QPM periods calculated using the Zelmon (1997) Sellmeier equation for MgO:LiNbO3 extraordinary ray at 25C. SFG output calculated via 1/lambda_SFG = 1/lambda_pump + 1/lambda_signal with lambda_pump = 1064 nm.

| Gas | Formula | Absorption Peak | Wavenumber (cm-1) | QPM Period (um) | SFG Output (nm) | Application |
|-----|---------|-----------------|-------------------|-----------------|-----------------|-------------|
| Methane | CH4 | 3.31 um (v3 C-H stretch) | 3021 | **22.0** | **805 nm** | Natural gas leaks, pipeline monitoring, mining |
| Carbon dioxide | CO2 | 4.26 um (v3 asymmetric stretch) | 2347 | **22.9** | **851 nm** | Emissions monitoring, greenhouse gas |
| Carbon monoxide | CO | 4.67 um (fundamental v=1-0) | 2141 | **22.7** | **867 nm** | Combustion monitoring, safety |
| Hydrogen sulfide | H2S | 3.98 um (v1 S-H stretch) | 2513 | **22.9** | **840 nm** | Sour gas detection, refinery safety |
| Ethane | C2H6 | 3.34-3.35 um (v7 C-H stretch) | 2985 | **22.1** | **806 nm** | Natural gas composition analysis |
| Nitric oxide | NO | 5.26 um (fundamental) | 1901 | **21.8** | **889 nm** | Combustion emissions (at edge of PPLN range) |

**Note:** CO2 and H2S share nearly identical QPM periods (22.9 um). A single crystal could address both with temperature tuning (~0.5 nm/C). All QPM periods fall in the 22-23 um range — standard for commercial PPLN fabrication (Covesion, HC Photonics, AdvR).

## PPLN Transparency

Lithium niobate is transparent from 0.42-5.2 um. All primary target gases (CH4, CO2, CO, H2S, ethane) fall within range. NO at 5.26 um is at the edge and may require alternative nonlinear crystals (AgGaS2 or orientation-patterned GaAs).

## Detection Limits (Estimated)

Actual detection limits depend on path length, pump power, and noise floor. Targets for comparison with existing technology:

| Gas | NDIR Typical | TDLAS Typical | Our Target (initial) | Our Target (optimized) |
|-----|-------------|--------------|---------------------|----------------------|
| CH4 | ~100 ppm | 0.1-1 ppb | 100 ppm (match NDIR) | <10 ppm |
| CO2 | ~50 ppm | 0.1-1 ppb | 50 ppm | <10 ppm |
| CO | ~5-10 ppm | 0.1-1 ppb | 10 ppm | <1 ppm |
| H2S | ~1-5 ppm | 0.1-1 ppb | 5 ppm | <1 ppm |

### Beer-Lambert Sensitivity Analysis

Using Beer-Lambert (I = I0 * exp(-alpha * C * L)) with a conservative minimum detectable absorbance of 10^-4 (standard Si photodiode + lock-in amplifier):

| Gas | Absorption Cross-Section | LOD @ 1m path | LOD @ 10m | LOD @ 100m |
|-----|------------------------|--------------|----------|-----------|
| CH4 | 1.5e-17 cm2 | 2 ppb | 0.2 ppb | 0.02 ppb |
| CO2 | 1.3e-17 cm2 | 3 ppb | 0.3 ppb | 0.03 ppb |
| CO | 5.0e-19 cm2 | 74 ppb | 7.4 ppb | 0.74 ppb |
| H2S | 5.0e-19 cm2 | 74 ppb | 7.4 ppb | 0.74 ppb |

With a Thorlabs HC10L Herriott cell (10.4m effective path), all four primary gases are detectable at low-ppb levels. With lock-in amplification (MDA ~10^-6), these improve by another 100x.

**Prior art validation:** A 2025 paper (arXiv:2601.15981) demonstrated 79.6 ppb CO detection with only a 14 cm path length using this exact approach. Our multi-pass cell (10-31m path) would improve on this by 70-220x. See [Prior Art](prior-art.md) for full citations.

## Cross-Sensitivity

A key advantage of PPLN-based detection: each waveguide is phase-matched to ONE specific wavelength. Wrong-wavelength suppression is 32-80 dB (from coupled-mode theory simulations). This means:

- CH4 crystal does NOT respond to CO2
- CO2 crystal does NOT respond to CH4
- No cross-talk between channels

This is better than NDIR optical filters, which pass a broad wavelength range and can confuse gases with overlapping absorption bands (e.g., methane and ethane both absorb near 3.3 um — NDIR struggles to distinguish them).
