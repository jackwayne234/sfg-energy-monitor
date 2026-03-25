# Experimental Validation — Energy Application

## Strategy: Start with Bulk PPLN, Upgrade to Waveguides

Previous estimates assumed waveguide-grade PPLN from the start ($5-8K per crystal). Revised strategy: start with a bulk Covesion multi-grating PPLN chip ($1-2.5K) to validate SFG signal at lower cost and with much more forgiving alignment (~50 um beam waist vs ~5 um for waveguides). Upgrade to HC Photonics or AdvR waveguide chips after core physics is proven.

Also revised: start with CO2 (4.26 um) instead of CH4 — CO2 has the strongest absorption cross-section (1.3e-17 cm2), the most published prior art, and ambient CO2 (~420 ppm) provides a free test gas for initial alignment.

See [Build Plan](build-plan.md) for full BOM with specific part numbers and suppliers.

## Experiment 1: Single-Gas PPLN SFG Upconversion
**Revised cost: $4,000-7,000 | Time: 2-3 weeks**

Detect CO2 at 4.26 um using SFG upconversion to ~851 nm.

**Setup (specific parts):**
- Broadband mid-IR source: Micro-Hybrid JSIR350 MEMS emitter (~$50-100) + Thorlabs LA5370 CaF2 lens (~$100)
- Gas cell: custom single-pass (aluminum tube + CaF2 windows) or ambient air for initial test (~$100-200)
- PPLN crystal: Covesion MSFG976-0.5 multi-grating bulk chip, QPM period ~22.9 um (~$1,000-2,500)
- PPLN oven: Covesion PV40 temperature controller (~$800-1,200)
- 1064 nm pump laser: Thorlabs DJ1064 fiber-coupled DBR, 70mW (~$1,500-2,500) or CNI MGL-FN-1064 500mW (~$800-1,500)
- Fiber collimator: Thorlabs F220APC-1064 (~$150-250)
- Dichroic combiner: Thorlabs DMSP1000 (~$200-400)
- CaF2 focusing lens: Thorlabs LA5714 f=40mm (~$100-150)
- Silicon detector: Hamamatsu S1227-1010BQ photodiode (~$30) + Thorlabs PDA100A2 amplified detector (~$450)
- Bandpass filter: Thorlabs FB850-10 (~$100)
- Optical chopper: Thorlabs MC2000B (~$800-1,200)
- Lock-in amplifier: Stanford Research SR830 (used on eBay, ~$1,500-2,500) — provides ~100x SNR improvement
- Optical breadboard + mounts: Thorlabs MB1218 + assorted (~$400-800)

**Why this is cheaper than original estimate:**
- Bulk PPLN ($1-2.5K) instead of waveguide chip ($5-8K)
- 70mW DBR laser ($1.5-2.5K) instead of 1W fiber laser ($5-8K) — sufficient for bulk crystal
- Lock-in amp recovers signal that raw detection would miss, compensating for lower pump power

**Procedure:**
1. Establish baseline SFG signal with empty gas cell (or N2-purged cell)
2. Fill cell with ambient air (~420 ppm CO2) — this is a free first test
3. Fill cell with 1000 ppm CO2 calibration gas (Cal Gas Direct, ~$130)
4. Measure SFG signal attenuation (should decrease due to CO2 absorption)
5. Progressive dilution to find minimum detectable concentration
6. Record signal-to-noise ratio at each concentration

**Go/No-Go:** If the device can detect 50 ppm CO2 (comparable to NDIR), proceed. If it reaches 10 ppm, you're competitive with better sensors. If sub-ppm, you're in TDLAS territory at a fraction of the cost.

**Prior art benchmark:** A 2025 paper (arXiv:2601.15981) achieved 79.6 ppb CO detection with only 14 cm path using this architecture. Our longer path should do better.

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

| Path | Cost (revised) | Cost (original) | What You Validate |
|------|---------------|-----------------|-------------------|
| Minimum (Exp 1) | **$4-7K** | $15-25K | Single-gas SFG detection works |
| + Exp 2 | +$3-5K | +$5-8K | Multi-gas discrimination proven |
| + Exp 3 | +$10-18K | +$15-25K | 4-channel demo-ready prototype |
| **Total** | **$17-30K** | $35-58K | **Full energy application validated** |

Revised costs reflect: bulk PPLN instead of waveguides, lower-power pump laser, shared lock-in amplifier, and specific part selection. See [Build Plan](build-plan.md) for full BOM.

Note: If core SFG validation is done first via the telecom experiments, energy experiments share the pump laser, temperature controller, lock-in amp, and optical bench — reducing incremental cost significantly.
