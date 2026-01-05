# RD-55 HDZero AIO15 Retrofit Plan

**Status**: Verified - Ready for Execution
**Created**: December 2025
**Updated**: January 2026 (fact-checked against manufacturer specs)

---

## Overview

Converting RD-55 from failed Walksnail system to HDZero using the **HDZero AIO15** - a complete FC+ESC+VTX+RX replacement that simplifies the stack and reduces weight.

**Reason**: Walksnail VTX killed in crash. Owner exiting Walksnail ecosystem. AIO15 provides integrated solution with significant weight savings.

---

## Conversion Summary

| Aspect | Original | Proposed | Delta |
|--------|----------|----------|-------|
| Flight Controller | GOKU F405 HD 1-2S 12A AIO V2 | HDZero AIO15 | Integrated |
| ESC | Integrated 12A 4-in-1 | Integrated 15A 4-in-1 | +3A headroom |
| VTX | Walksnail Avatar HD Mini 1S Lite | HDZero (integrated) | Ecosystem change |
| Receiver | ELRS 2.4GHz (in FC) | ELRS 2.4GHz (in AIO15) | Compatible |
| Camera | Walksnail Lite (1.8g) | BetaFPV C03 (1.45g) | -0.35g |
| **Video+FC Weight** | **12.9g** | **8.65g** | **-4.25g** |

---

## Weight Analysis

### Components Removed

| Component | Weight | Source |
|-----------|--------|--------|
| GOKU F405 HD 1-2S 12A AIO V2 | 6.0g | Flywoo specs |
| Walksnail Avatar HD Mini 1S Lite VTX | 5.1g | Caddx specs |
| Walksnail Lite Camera | 1.8g | Caddx specs |
| **Total Removed** | **12.9g** | |

### Components Added

| Component | Weight | Source |
|-----------|--------|--------|
| HDZero AIO15 (FC+ESC+VTX+RX) | 7.2g | HDZero specs (with motor plugs) |
| BetaFPV C03 Camera | 1.45g | BetaFPV specs |
| **Total Added** | **8.65g** | |

### Net Result

| Metric | Value |
|--------|-------|
| **Weight Savings** | **4.25g** |
| Original Dry Weight | 53.9g |
| **New Dry Weight** | **~49.7g** |
| Weight Reduction | ~7.9% |

### Flight Time Implication

Weight reduction of ~8% on a 2S whoop typically translates to:
- **5-10% longer flight times** (reduced power draw for hover)
- Improved agility and responsiveness
- Reduced motor heat

---

## Physical Compatibility

### Board Dimensions

| Spec | GOKU F405 (Original) | HDZero AIO15 (Proposed) | Compatible? |
|------|---------------------|------------------------|-------------|
| Board Size | 30.0 x 30.0mm | 31.3 x 31.3mm | Tight (+1.3mm/side) |
| Mounting Pattern | 25.5 x 25.5mm | 25.5 x 25.5mm | Yes |
| Height | Single board | Single board | Yes (simpler) |

**Fitment Assessment**: The Flylens 75 frame accommodates a 30mm board. The AIO15 is 1.3mm wider per side. This is tight but likely fits. **Physical test-fit recommended before final commitment.**

### Electrical Compatibility

| Spec | Requirement | AIO15 Capability | Compatible? |
|------|-------------|------------------|-------------|
| Battery Voltage | 2S (7.4V nominal) | 2S-3S (7.4-11.1V) | Yes |
| ESC Current | 12A adequate | 15A (18A peak) | Yes (+headroom) |
| Camera Power | 3-5.5V | 5V/1A BEC output | Yes |
| Video Signal | Analog composite | Composite input | Yes |
| Motor Size | 1003 | Up to 1404 supported | Yes |

### Camera Compatibility

| Spec | BetaFPV C03 | AIO15 Requirement | Compatible? |
|------|-------------|-------------------|-------------|
| Video Output | CVBS (analog composite) | Composite video input | Yes |
| Voltage | 3-5.5V DC | 5V BEC available | Yes |
| Connector | JST-0.8 | Solder pads | Requires soldering |
| Dimensions | 11 x 14.1 x 13.5mm | 14mm cam bay | Yes |

---

## Parts Required

| Part | Status | Notes |
|------|--------|-------|
| HDZero AIO15 | TO ACQUIRE | ~$90-100 USD |
| BetaFPV C03 Camera | ON HAND | Multiple in inventory |
| 5.8GHz Antenna (u.FL) | CHECK INVENTORY | AIO15 uses u.FL connector |
| ELRS Antenna | INCLUDED | Pre-soldered on AIO15 |
| Mounting Hardware | REUSE | M2 screws from original |
| Camera Mount | TBD | May need TPU adapter for C03 |

---

## Pre-Conversion Assessment

Before proceeding, verify:

- [ ] AIO15 physical test-fit in frame (1.3mm clearance check)
- [ ] Airframe structural integrity post-crash
- [ ] Motor function (all 4 spin freely)
- [ ] Battery connector (XT30) condition
- [ ] C03 camera mounting solution identified

---

## Conversion Procedure

### Phase 1: Disassembly

1. **Document original wiring** - photograph before disconnecting
2. **Remove canopy/top shell**
3. **Disconnect battery lead** from FC
4. **Disconnect motors** from FC (note motor order: 1-4)
5. **Remove GOKU F405 FC** (4x M2 mounting screws)
6. **Remove Walksnail VTX** and camera assembly
7. **Remove Walksnail antenna**
8. **Inspect frame** for crash damage

### Phase 2: AIO15 Installation

1. **Test-fit AIO15** in frame - verify clearance
2. **Mount AIO15** using 25.5mm pattern (reuse M2 screws)
3. **Connect motors** to AIO15 motor pads (match original order)
4. **Connect battery lead** to AIO15 power input
5. **Route ELRS antenna** - maintain 3mm clearance from board per HDZero specs
6. **Install VTX antenna** (u.FL) - route outward, not inward

### Phase 3: Camera Installation

1. **Prepare C03 wiring**:
   - Red: 5V (from AIO15 5V BEC)
   - Black: GND
   - Yellow: Video signal (to AIO15 composite input)
2. **Solder camera wires** to AIO15 camera pads
3. **Mount C03 camera** in frame camera bay
   - May require TPU adapter if C03 form factor differs from original mount
4. **Secure camera wiring** - avoid pinching

### Phase 4: Configuration

1. **Connect to Betaflight Configurator** via USB-C
2. **Verify gyro orientation** - may differ from GOKU F405
3. **Set motor resource mapping** if different from default
4. **Configure ELRS** - should auto-bind if using same model ID
5. **Set VTX power** (start at 25mW for bench testing)
6. **Verify OSD elements** display correctly

### Phase 5: Testing

1. **Bench power-up** - verify no smoke, LEDs normal
2. **Motor test** - verify correct spin direction and order
3. **Receiver bind test** - verify ELRS link
4. **Video test** - verify HDZero feed on goggles
5. **Range test** - walk-away test before flight
6. **Maiden hover** - indoor or calm conditions, check for vibration/oscillation
7. **PID tune** if needed (AIO15 defaults may differ from GOKU F405)

---

## Wiring Diagram

```
HDZero AIO15 Connections:

BATTERY ──────► [BAT+] [BAT-]
                   │      │
                   └──────┴── 2S LiPo (XT30)

MOTORS ───────► [M1] [M2] [M3] [M4]
                 │    │    │    │
                 └────┴────┴────┴── 1003 Motors (match original order)

CAMERA ───────► [5V] [GND] [VID]
                 │     │     │
                 └─────┴─────┴── BetaFPV C03 (JST wires or direct solder)

ANTENNAS ─────► [VTX ANT] (u.FL) - 5.8GHz whip or dipole
                [ELRS ANT] - Pre-soldered, lift 3mm from board
```

---

## Risk Mitigations

| Risk | Likelihood | Mitigation |
|------|------------|------------|
| AIO15 doesn't fit frame | Low | Test-fit before soldering; 1.3mm margin is tight but workable |
| C03 mount incompatible | Medium | TPU adapter print, or foam tape mount |
| Motor mapping wrong | Low | Document original order; Betaflight motor test before flight |
| PID instability | Medium | Start conservative; AIO15 has different gyro than GOKU F405 |
| ELRS bind fails | Low | Re-flash if needed; same protocol |

---

## Rollback Plan

If conversion fails:
1. Original GOKU F405 FC can be reinstalled (preserve it)
2. Would need new VTX regardless (Walksnail dead)
3. Alternative: HDZero Whoop Lite bundle + keep GOKU FC

---

## References

- [HDZero AIO15 Product Page](https://www.hd-zero.com/product-page/hdzero-aio15)
- [HDZero AIO15 Documentation](https://docs.hd-zero.com/aio15-introduction)
- [BetaFPV C03 Specs](https://betafpv.com/products/c03-fpv-micro-camera)
- [Flywoo GOKU F405 HD 1-2S AIO V2](https://flywoo.net/products/goku-f405-hd-1-2s-elrs-aio-v2)
- [Walksnail Avatar HD Mini 1S Lite Kit Review](https://oscarliang.com/walksnail-avatar-hd-mini-1s-lite-kit/)

---

## Approval

- [ ] Parts acquired
- [ ] Physical test-fit confirmed
- [ ] Proceed with conversion
