# Proposal: Flywoo Flylens 75 (2S) Conversion from Walksnail to HDZero

## Purpose

This document proposes a practical repair and conversion path for a **Flywoo Flylens 75 2S Walksnail (ELRS 2.4)** whose Walksnail VTX has failed due to crash damage. The goal is to restore the aircraft to flight using existing hardware while transitioning away from the Walksnail ecosystem.

The proposed solution replaces the Walksnail digital video system with an **HDZero AIO15** paired with a **BetaFPV C03 analog camera**.

---

## Background

- The original Flylens 75 configuration uses a **Walksnail Avatar digital camera + VTX** system.
- Walksnail camera and VTX communicate via a **digital MIPI-style interface** and cannot be reused independently.
- The VTX is no longer functional.
- The owner is intentionally exiting the Walksnail ecosystem.
- Multiple **BetaFPV C03** cameras are already available.

---

## Proposed Solution

Replace the Walksnail video system entirely with:

- **HDZero AIO15** (flight controller + ESC + ELRS RX + HDZero VTX)
- **BetaFPV C03** analog FPV camera

This results in a compact, integrated control and video solution suitable for a 2S 75 mm whoop-class aircraft.

---

## Technical Compatibility Summary

### Power

- Flylens battery: **2S LiPo**
- HDZero AIO15 input range: **2S–3S compatible**
- HDZero AIO15 provides a regulated **5 V output**, suitable for the C03 camera (3–5.5 V rated)

### Video Signal

- BetaFPV C03 outputs **standard composite (CVBS) analog video**
- HDZero AIO15 accepts **composite video input** and digitizes it for HDZero transmission
- Walksnail digital components are fully removed

### Control

- HDZero AIO15 includes an **integrated ELRS 2.4 GHz receiver**
- Existing radio control setup remains compatible

---

## Resulting System Architecture

| Component | Original | Proposed |
|---------|---------|----------|
| Camera | Walksnail digital | BetaFPV C03 (analog) |
| Video Transmission | Walksnail Avatar | HDZero digital |
| Flight Controller | Flywoo FC | HDZero AIO15 |
| Receiver | ELRS (external or onboard) | ELRS integrated |
| Battery | 2S | 2S |

---

## Advantages of This Approach

- Restores flight capability without replacing Walksnail hardware
- Uses already-owned cameras (C03)
- Moves fully into the HDZero ecosystem
- Reduces system complexity via AIO integration
- Appropriate weight and power profile for a 75 mm 2S platform

---

## Tradeoffs / Considerations

- Walksnail digital video quality and features are not retained
- Camera must be physically remounted (C03 form factor differs)
- Minor soldering required (camera power, ground, video)
- HDZero goggles or receiver required for viewing

---

## Conclusion

The proposed HDZero AIO15 + BetaFPV C03 configuration is a technically sound and cost-effective method to repair and modernize the Flywoo Flylens 75 following Walksnail VTX failure. It aligns with the stated goal of leaving the Walksnail ecosystem while reusing existing components and maintaining 2S performance characteristics.

This conversion is recommended for pilots comfortable with light soldering and minor mechanical adaptation.

