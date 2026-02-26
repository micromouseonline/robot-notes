---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
title: Increasing Downforce
subtitle: 
description:
# icon: octicons/dot-fill-16
icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---




## Ways to Increase Downforce

If you’re basically capped on **speed** and **area**, the game becomes: **get more usable ΔP for the same power** and **turn more of that ΔP into effective hold‑down**.

### 1. Reduce Leakage

- **Tighter primary gap**
    - Reduce the rigid skirt gap from 1 mm toward **0.5 mm or less** if terrain allows.
    - Smaller gap → higher flow resistance → higher achievable plenum pressure for the same fan.

- **Smarter flexible skirt**
    - Use a **very compliant, low‑friction material** (thin silicone, PTFE‑coated fabric) so it conforms with minimal lift.
    - Add **multiple lips or ribs** on the underside to create **serial restrictions** instead of one big leak path.

- **Edge shaping**
    - Slight chamfer or radius on the rigid skirt edge can reduce local leakage jets and help the flexible skirt seal.

### 2. Improve Fan Efficiency

- **Better blade geometry**
    - Use **backward‑curved blades** with well‑chosen inlet/outlet angles (like the 75°/30° example).
    - Keep blades **thin and smooth** to reduce friction and separation.

- **Tighter clearances**
    - Minimize:
        - Tip clearance to casing,
        - Axial clearance to shrouds,
        - Leakage paths around the hub.
    - Every bypass path is lost ΔP.

- **Cleaner scroll and inlet**
  - Smooth scroll expansion, no sharp corners.
  - Rounded inlet (small bellmouth) at the eye/aperture to cut inlet losses.

### 3. Better Aperture and Flow

- **Tune aperture diameter**
  - Use the aperture as a **throttle** to push the fan toward its **max‑pressure, low‑flow** point.
  - Experiment with a few diameters (e.g. 8, 10, 12 mm) and pick the one that gives **highest measured plenum pressure** at your fixed RPM.

- **Control internal flow paths**
  - Avoid narrow, high‑loss passages between different parts of the plenum.
  - Aim for **uniform pressure** under the whole footprint so all area contributes to downforce.

### 4. Use “Dynamic” Tricks

- **Textured underside**
  - Very fine, shallow textures can help the flexible skirt avoid sticking while still sealing.
- **Segmented skirts**
  - Divide the outer skirt into **sections** that can independently conform to local bumps, improving average sealing.

---

In short: with RPM and area fixed, your biggest wins come from **leakage reduction**, **fan/scroll efficiency**, and **careful tuning of the aperture and skirt system** so that as much of your limited power as possible becomes **uniform, high ΔP** under the robot.

### 5. Aperture and Eye

You want **maximum static pressure** in the plenum. The **fan diameter $D_f$**, **eye diameter $D_e$**, and **aperture diameter $D_a$** together control:

- How much pressure the fan can theoretically generate (mainly $D_f$ and speed),
- How “pressure‑oriented” the impeller is (ratio $D_e / D_f$),
- How much flow is actually allowed into the fan (strongly influenced by $D_a$).

Static pressure is maximized when the fan operates near its **peak‑pressure, low‑flow** point, without wasting too much pressure across the aperture.

- **Fan diameter $D_f$ and eye diameter $D_e$**

    - **Fan diameter $D_f$** sets tip speed and potential pressure:
      $$\Delta P_{\text{ideal}} \propto \rho D_f^2 n^2$$

    - **Eye diameter $D_e$** sets inlet area:
      $$A_e = \frac{\pi D_e^2}{4}$$

      For a given flow $Q$:
      $$V_e = \frac{Q}{A_e}$$

      Smaller $D_e$:
      - Higher $V_e$ → more inlet loss,
      - Longer blades (smaller $D_e / D_f$) → more pressure‑oriented design.

    **For high static pressure:**
    - Choose a **moderately small eye**, e.g. $D_e \approx 0.4$–$0.6\,D_f$, to favor pressure over flow without excessive inlet loss.

---

- **Aperture diameter $D_a$ vs eye diameter $D_e$**

The aperture is an orifice feeding the eye:

- Aperture area:
  $$A_a = \frac{\pi D_a^2}{4}$$

- If $A_a \ll A_e$:
  - The aperture is the **dominant restriction**.
  - Flow $Q$ drops, pushing the fan toward **higher static pressure / lower flow**.
  - But aperture velocity:
    $$V_a = \frac{Q}{A_a}$$
    becomes large → **orifice losses** consume a lot of pressure.

- If $A_a \gg A_e$:
  - The **eye** is the main restriction; the aperture is almost invisible.
  - Aperture losses are small, but the fan may run at **higher flow, lower pressure** than desired.

**For maximum plenum static pressure:**
- You want the fan **slightly flow‑starved**, not choked by the aperture.
- That typically means:
  $$D_a \lesssim D_e$$
  i.e. aperture diameter **similar to or slightly smaller than the eye**.

Use $D_a$ as a **tuning knob**:
1. Start with $D_a \approx D_e$.
2. Reduce $D_a$ in small steps and measure plenum pressure.
3. Stop when further reduction **no longer increases** plenum pressure (aperture losses are taking over).

---

- **Combined design logic for maximum static pressure**

1. **Maximize $D_f$** within your layout → higher potential $\Delta P$.
2. **Choose $D_e$** so $D_e / D_f$ is on the **pressure‑oriented side** (about $0.4$–$0.6$).
3. **Set $D_a$ close to $D_e$** and tune it slightly smaller to:
   - Push the operating point toward the **high‑pressure, low‑flow** region,
   - Avoid burning most of the pressure across the aperture itself.

In short:
- $D_f$ sets how much pressure you *could* have,
- $D_e$ biases the impeller toward pressure vs flow,
- $D_a$ decides how much of that potential pressure actually appears in the **plenum** instead of being lost at the inlet.

