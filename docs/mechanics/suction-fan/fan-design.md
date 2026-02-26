---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
title: Centrifugal Fan Design
subtitle: 
description:
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---
# Centrifugal Fan Design Summary for a Vacuum Downforce Robot


!!! note

    Summarised responses from CoPilot
    These notes are unverified and not tested


## Core Objective
Generate **maximum static pressure** (ΔP) with **minimal airflow** to create strong **downforce** inside an 80 mm × 50 mm plenum using a **single centrifugal fan** driven by a **≤10 W coreless motor**.

---

## Critical Features for High Downforce

### 1. **Impeller Diameter (Most Important)**
- Larger diameter → higher tip speed → **much higher static pressure**.
- Choose the **largest diameter that fits** the plenum (≈25–40 mm practical range).

### 2. **Blade Geometry**
- **Backward‑curved blades**: higher efficiency, smoother flow, strong pressure at low flow.
- **Straight/radial blades**: simpler, can reach high pressure but with more loss and noise.
- **Blade count**: 8–16 blades gives good pressure with manageable blockage.

### 3. **Blade Height (Width)**
- Narrower impeller → **higher pressure, lower flow**.
- Wider impeller → more flow but lower pressure.
- For this application: **moderately narrow** (≈3–6 mm).

### 4. **Blade Length / Eye Size**
- Smaller eye → longer blades → **higher pressure**, lower flow.
- Larger eye → more flow, less pressure.
- Aim for eye diameter ≈40–60% of impeller diameter.

---

## Aperture and Inlet

### 5. **Aperture Diameter**
- Acts as a throttle feeding the eye.
- Slightly smaller than the eye → shifts fan toward **high‑pressure, low‑flow** operation.
- Too small → inlet losses waste pressure.
- Typical starting point: **8–15 mm** depending on impeller size.

### 6. **Aperture–Eye Relationship**
- Aperture ≈ eye diameter gives best balance.
- Aperture much smaller → pressure lost at the orifice.
- Aperture larger → fan runs at higher flow, reducing ΔP.

---

## Housing and Pressure Recovery

### 7. **Scroll / Volute (Essential)**
- Converts tangential velocity into **static pressure**.
- Without a scroll (“free‑space impeller”), static pressure collapses and downforce becomes weak.
- Even a simple circular housing with a small diffuser region is far superior to free discharge.

---

## Plenum and Skirts

### 8. **Plenum**
- Height ≈5–10 mm to avoid choking while keeping volume low.
- Smooth flow path from 1 mm floor gap to the fan inlet.

### 9. **Skirts**
- **Rigid 1 mm skirt** defines the vacuum area.
- **Flexible outer skirt** reduces leakage over bumps (<0.5 mm).
- Leakage through the 1 mm gap is the dominant load on the fan.

---

## Motor and Speed

### 10. **RPM**
- Pressure ∝ rpm²; power ∝ rpm³.
- Run the motor as fast as safely possible within the **10 W** limit.
- Match aperture and impeller geometry so the operating point lies near **shut‑off pressure**.
