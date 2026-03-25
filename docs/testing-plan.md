# Experimental Validation — Energy Application

## Experiment 1: Single-Gas PPLN SFG Upconversion
**Cost: $15-25K | Time: 2-3 weeks**

Detect methane (CH4) at 3.27 um using SFG upconversion to ~803 nm.

**Setup:**
- Broadband mid-IR source: globar/thermal emitter (~$500-1K) or mid-IR LED at 3.3 um (Hamamatsu L15893, ~$112)
- Gas cell with methane calibration gas (1000 ppm CH4 in N2, Cal Gas Direct, ~$130)
- PPLN crystal with poling period for 3.27 um + 1064 nm pump → ~803 nm output (~$1.5-3K)
- 1064 nm pump laser (1W CW, fiber-coupled, ~$5-8K)
- Silicon APD detector (~$2.5K)
- Temperature controller for PPLN (~$2-3K)
- Optical mounts, filters, breadboard (~$1-2K)

**Procedure:**
1. Establish baseline SFG signal with empty gas cell
2. Fill cell with 1000 ppm CH4 calibration gas
3. Measure SFG signal attenuation (should decrease due to CH4 absorption)
4. Progressive dilution to find minimum detectable concentration
5. Record signal-to-noise ratio at each concentration

**Go/No-Go:** If the device can detect 100 ppm CH4 (comparable to NDIR), proceed. If it reaches 10 ppm, you're competitive with better sensors. If sub-ppm, you're in TDLAS territory at a fraction of the cost.

## Experiment 2: Two-Gas Discrimination
**Incremental cost: $5-8K | Time: 2 weeks**

- Add CO2 gas cell + second PPLN crystal tuned to 4.26 um
- CO2 calibration gas (~$100-200)
- Show crystal A responds to CH4, crystal B responds to CO2, independently
- Measure cross-talk: does CH4 in the path affect the CO2 channel? (Should be <-30 dB)

## Experiment 3: Multi-Gas Prototype
**Incremental cost: $15-25K | Time: 1-2 months**

- 4 PPLN crystals (CH4, CO2, CO, H2S)
- Mixed calibration gas: 2.5% CH4 + 50 ppm CO + 25 ppm H2S + 20.9% O2 (~$100-200)
- Simultaneous 4-channel detection from a single gas mixture
- This is demo-ready for pipeline operators

## Total Cost

| Path | Cost | What You Validate |
|------|------|-------------------|
| Minimum (Exp 1) | $15-25K | Single-gas SFG detection works |
| + Exp 2 | +$5-8K | Multi-gas discrimination proven |
| + Exp 3 | +$15-25K | 4-channel demo-ready prototype |
| **Total** | **$35-58K** | **Full energy application validated** |

Note: If core SFG validation is done first via the telecom experiments ($22-35K), energy experiments share the pump laser, temperature controller, and optical bench — reducing incremental cost significantly.
