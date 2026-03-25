# Passive and Open-Path IR Source Options

## The Problem

Gas detection via absorption spectroscopy requires an IR source on one side and a detector on the other. The gas in between absorbs its signature wavelengths. Traditionally, this means powered equipment on both ends.

## Open-Path Monitoring

Place the IR source at one end of the monitored zone (pipeline segment, facility perimeter, fence-line) and the SFG detector at the other. Any gas in the path absorbs its signature wavelengths. The detector reads which channels attenuated and by how much.

**Range:** Depends on source power and atmospheric conditions. Thermal emitters work at tens to hundreds of meters. Laser sources work at kilometers.

## Source Options

### Powered Sources

**Globar (heated SiC rod)**
- Cost: ~$200-500
- Broadband mid-IR emission (matches blackbody curve)
- Standard lab equipment, well-characterized
- Needs electrical power (~50-100W)

**Mid-IR LED**
- Hamamatsu L15893: 3.3 um, ~$112
- Narrow emission band, good for single-gas targeting
- Low power consumption (~100 mW)

**Thermal emitter arrays**
- Commercial IR sources for spectroscopy
- Multiple wavelengths, modulated output for lock-in detection

### Passive Sources

**Solar radiation**
- The sun emits broadband mid-IR
- Solar occultation spectroscopy: point detector at sky through the monitored area
- Any gas in the path absorbs from the solar spectrum
- Same principle used by satellites for atmospheric gas measurements (e.g., ACE-FTS on SCISAT)
- Free, available during daytime
- Limitation: cloud cover reduces signal, unavailable at night

**Thermal mass (the "hot rock")**
- A dark, dense material (concrete, basite, dark stone) absorbs solar heat during the day
- Radiates broadband IR at night as it cools
- Maintains above-ambient temperature for hours after sunset
- In desert/arid environments: minimal rain, strong solar heating, excellent thermal mass performance
- Zero power consumption, zero maintenance on the emitter end
- Limitation: signal strength depends on temperature differential (source vs ambient); degrades as the mass cools

### Best Use Cases for Passive Sources

**Desert pipeline monitoring:** Plenty of sun, rocks everywhere, minimal rain. Thermal mass on one side, SFG detector with solar-powered electronics + satellite uplink on the other. Fully autonomous, no grid power needed anywhere.

**Remote facility perimeter:** Where running power to both ends of a fence-line is expensive. One powered end (detector) and one passive end (thermal mass or solar-facing reflector).

## Rain and Weather

Water droplets scatter and absorb mid-IR heavily. All open-path IR systems (not just SFG) lose signal in heavy rain. This is a known operating constraint:
- Log "low visibility" during rain events
- Resume monitoring when conditions clear
- Same limitation as commercial open-path FTIR and TDLAS systems
