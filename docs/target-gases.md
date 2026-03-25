# Target Gases and Detection Specifications

## Primary Targets

| Gas | Formula | Absorption Band | Absorption Peak | PPLN Poling Period (est.) | SFG Output | Application |
|-----|---------|----------------|-----------------|--------------------------|------------|-------------|
| Methane | CH4 | 3.0-3.5 um | 3.27 um (C-H stretch) | ~18-20 um | ~803 nm | Natural gas leaks, pipeline monitoring, mining |
| Carbon dioxide | CO2 | 4.2-4.3 um | 4.26 um (asymmetric stretch) | ~20-22 um | ~852 nm | Emissions monitoring, greenhouse gas |
| Carbon monoxide | CO | 4.5-4.8 um | 4.6 um (fundamental band) | ~21-23 um | ~864 nm | Combustion monitoring, safety |
| Hydrogen sulfide | H2S | 3.8-4.0 um | 3.85-3.91 um | ~19-21 um | ~830 nm | Sour gas detection, refinery safety |
| Ethane | C2H6 | 3.3-3.4 um | 3.34-3.35 um | ~18-20 um | ~806 nm | Natural gas composition analysis |
| Nitric oxide | NO | 5.2-5.4 um | 5.26 um | At edge of PPLN range | ~868 nm | Combustion emissions |

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

## Cross-Sensitivity

A key advantage of PPLN-based detection: each waveguide is phase-matched to ONE specific wavelength. Wrong-wavelength suppression is 32-80 dB (from coupled-mode theory simulations). This means:

- CH4 crystal does NOT respond to CO2
- CO2 crystal does NOT respond to CH4
- No cross-talk between channels

This is better than NDIR optical filters, which pass a broad wavelength range and can confuse gases with overlapping absorption bands (e.g., methane and ethane both absorb near 3.3 um — NDIR struggles to distinguish them).
