# RD-55 HDZero AOI5 Retrofit Plan

**Status**: Planning (bench work pending)
**Created**: December 2025

---

## Overview

Converting RD-55 from dead Walksnail Avatar HD Mini 1S Lite to HDZero AOI5.

**Reason**: VTX killed in crash, no spare Avatar HD Mini available, AOI5 on hand.

---

## Current State

| Component | Status |
|-----------|--------|
| Walksnail VTX | DEAD (crash damage) |
| Walksnail Camera | UNKNOWN - needs bench test |
| Airframe | UNKNOWN - needs inspection |
| FC/ESC | UNKNOWN - needs power-up test |
| Motors | UNKNOWN - needs spin test |
| ELRS RX | UNKNOWN - needs bind test |

---

## Bench Work Required

### Phase 1: Assessment

- [ ] Visual inspection of crash damage
- [ ] Power up FC (without VTX) - does it boot?
- [ ] Test motors - all 4 spin?
- [ ] Test ELRS bind - does RX connect?
- [ ] Assess Walksnail camera - physically separate from VTX? Damaged?

### Phase 2: HDZero Fitment

- [ ] Compare AOI5 dimensions to original VTX mount
- [ ] Determine mounting solution:
  - Direct fit?
  - TPU adapter needed?
  - Double-sided tape/foam?
- [ ] Check AOI5 wiring requirements vs FC pinout
- [ ] Camera decision (see below)

### Phase 3: Camera Solution

**Open Question**: What camera for the AOI5?

Options:
1. **Salvage Walksnail camera** - Only if physically separate AND undamaged. NOT compatible with HDZero - would need different HDZero camera anyway.
2. **HDZero Nano Lite** - Purpose-built for whoops, light
3. **HDZero Nano 90** - Wider FOV option
4. **Other HDZero cam** - What's in inventory?

**Action**: Check if Papa has HDZero camera in parts bin.

---

## Parts Required

| Part | Status | Notes |
|------|--------|-------|
| HDZero AOI5 | ON HAND | |
| HDZero Camera | TBD | Nano Lite or similar |
| Mounting hardware | TBD | May need TPU print |
| Antenna | TBD | Check compatibility |

---

## Technical Comparison

| Spec | Walksnail Avatar HD Mini 1S Lite | HDZero AOI5 |
|------|----------------------------------|-------------|
| Weight | ~4g (with cam) | ~5g (VTX only) |
| Size | Larger | Smaller |
| Camera | Integrated | Separate (not included) |
| Input Voltage | 3.3-6V (1S-2S) | TBD - verify |
| Connector | ? | ? |

---

## Wiring Notes

**Original Walksnail wiring**: TBD - document during teardown

**AOI5 requirements**: TBD - check HDZero docs

---

## Next Steps

1. Schedule bench session
2. Complete Phase 1 assessment
3. Decision gate: Is airframe worth retrofitting or too damaged?
4. If go: Complete Phase 2 & 3 planning
5. Order any missing parts (camera?)
6. Execute retrofit
7. Test flight

---

## References

- [RotorVillage Original Spec](https://rotorvillage.ca/flywoo-flylens-75-2s-walksnail-v1-3-elrs2-4/)
- HDZero AOI5 documentation: TBD
- Flywoo FlyLens75 frame specs: TBD
