# SFG Energy Monitor — Multi-Gas Leak Detection

Solid-state, multi-gas detection platform using SFG (sum-frequency generation) in PPLN (periodically poled lithium niobate) waveguides. Simultaneously identifies methane, CO2, CO, and H2S from a single device with no moving parts.

Part of the **SFG Detection Platform** — same core hardware (PPLN chamber + pump laser + Si detectors), different tuning per application.

| Application | Repo |
|---|---|
| Telecom (fiber monitoring) | [sfg-fiber-monitor](https://github.com/jackwayne234/sfg-fiber-monitor) |
| Energy (this repo) | [sfg-energy-monitor](https://github.com/jackwayne234/sfg-energy-monitor) |
| Environmental (water/air quality) | [sfg-environmental-monitor](https://github.com/jackwayne234/sfg-environmental-monitor) |
| Healthcare (breath analysis) | [sfg-health-diagnostics](https://github.com/jackwayne234/sfg-health-diagnostics) |
| Market Research | [sfg-market-research](https://github.com/jackwayne234/sfg-market-research) |
| Directional Detection | [directional-gas-detector](https://github.com/jackwayne234/directional-gas-detector) |

## How It Works

1. A broadband mid-IR source (thermal emitter, LED, or sunlight) shines through the monitored area
2. Target gases absorb their signature mid-IR wavelengths as the light passes through
3. The transmitted light enters an array of PPLN waveguides, each tuned to a different gas absorption line
4. A 1064 nm pump laser combines with the mid-IR signal via SFG
5. Each PPLN waveguide produces an SFG output in the 800-870 nm range (silicon-detectable)
6. Whichever SFG output dims → that gas is present and absorbing its signature wavelength
7. Degree of dimming → gas concentration (Beer-Lambert law)

## Target Gases

SFG output calculated via 1/lambda_SFG = 1/lambda_pump + 1/lambda_signal (pump = 1064 nm). QPM periods from Zelmon (1997) Sellmeier equation for MgO:LiNbO3 at 25C.

| Gas | Absorption Peak | QPM Period | SFG Output | Application |
|-----|----------------|------------|------------|-------------|
| Methane (CH4) | 3.31 um | 22.0 um | **805 nm** | Pipeline leaks, mining safety |
| CO2 | 4.26 um | 22.9 um | **851 nm** | Emissions monitoring |
| CO | 4.67 um | 22.7 um | **867 nm** | Combustion monitoring, safety |
| H2S | 3.98 um | 22.9 um | **840 nm** | Sour gas detection |
| Ethane | 3.34 um | 22.1 um | **806 nm** | Natural gas composition |

All SFG outputs land in the 800-870 nm range — silicon APDs work for all of them. No expensive cooled mid-IR detectors needed. CO2 and H2S share nearly identical QPM periods (22.9 um) — one crystal, temperature-tuned.

## Key Advantages Over Existing Technology

| | NDIR | TDLAS | FTIR | SFG (this device) |
|---|---|---|---|---|
| Gases per unit | 1 | 1 per laser | Many | Many (one per PPLN waveguide) |
| Moving parts | None | None | Yes (scanning mirror) | None |
| Detector cooling | No | No | Yes (MCT) | No (silicon) |
| Field durability | Good | Good | Poor (mirror alignment) | Excellent (solid-state) |
| Cost | $80-300 | $5-50K | $30-150K | ~$16-30K (est.) |

## Passive IR Source Options

For remote deployments where powered IR sources are impractical:

- **Thermal emitter (globar):** Heated silicon carbide rod, a few hundred dollars, standard lab equipment
- **Mid-IR LED:** Hamamatsu L15893 at 3.3 um, ~$112
- **Solar radiation:** The sun is a free broadband mid-IR source. Solar occultation spectroscopy (same principle satellites use for atmospheric gas measurement, ground-based)
- **Passive thermal mass:** A dark rock or concrete block absorbs solar heat during the day and radiates broadband IR at night. Fully passive, zero power on the emitter end.

## Documentation

- [Target Gases](docs/target-gases.md) — Detailed gas properties, QPM periods, and detection specifications
- [Build Plan](docs/build-plan.md) — Full BOM with part numbers, suppliers, costs, and assembly instructions
- [Prior Art](docs/prior-art.md) — Published papers and funded projects validating this architecture
- [Testing Plan](docs/testing-plan.md) — Experimental validation: single-gas through multi-gas prototype
- [Competition](docs/competition.md) — Detailed comparison with NDIR, TDLAS, QEPAS, FTIR
- [Passive IR Source](docs/passive-ir-source.md) — Open-path monitoring and passive source concepts
- [Regulatory](docs/regulatory.md) — EPA, OSHA, MSHA regulations driving demand

## Status

- [x] Target gas wavelengths mapped to PPLN parameters
- [x] SFG output wavelengths confirmed in Si detector range
- [x] QPM periods calculated from Sellmeier equations (22.0-22.9 um range)
- [x] Competition analysis complete
- [x] Prior art validated — multiple published systems confirm architecture (see [Prior Art](docs/prior-art.md))
- [x] Build plan with specific BOM, part numbers, and suppliers (see [Build Plan](docs/build-plan.md))
- [x] Beer-Lambert sensitivity analysis with path-length projections
- [ ] Single-gas SFG upconversion experiment (CO2 — start here, strongest cross-section)
- [ ] Two-gas discrimination experiment (CO2 + CH4)
- [ ] Multi-gas prototype (4-channel)
- [ ] Field testing

## Author

Christopher Riner | Active Duty U.S. Navy
ORCID: [0009-0008-9448-9033](https://orcid.org/0009-0008-9448-9033) | GitHub: [jackwayne234](https://github.com/jackwayne234)
