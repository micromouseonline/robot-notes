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

---

## Example Impeller Geometry for a 32 mm Centrifugal Fan

### 1. Core Dimensions
- **Outer diameter (Do):** 32 mm → **outer radius (ro):** 16 mm  
- **Eye diameter (De):** 14 mm → **inner radius (ri):** 7 mm  
- **Blade length (L):** ro − ri = **9 mm**  
- **Blade width (b):** ~4 mm (axial height between shrouds)  
- **Blade count (Z):** 12 blades  

These values fit comfortably inside your 80 mm × 50 mm plenum while maximizing pressure capability.

---

### 2. Blade Angles
Angles are measured relative to the **tangential direction** (direction of rotation).

- **Inlet angle (β₁):** **75°**  
  - Slightly backward‑leaning at the eye  
  - Reduces inlet losses and improves low‑flow efficiency  

- **Outlet angle (β₂):** **30°**  
  - Strongly backward‑curved at the tip  
  - Produces high static pressure and stable operation near shut‑off  

This combination is ideal for high‑pressure, low‑flow operation.

---

### 3. Blade Shape Construction
1. Draw inner and outer circles at **ri = 7 mm** and **ro = 16 mm**.  
2. Divide the outer circle into **12 equal sectors** (every 30°).  
3. At each outer point, draw a line at **30°** to the tangent (leaning backward).  
4. At each corresponding inner point, draw a line at **75°** to the tangent.  
5. Connect each inner–outer pair with a **smooth curved blade** (spline or circular arc) that is tangent to both angle constraints.

This produces a backward‑curved blade with fixed length (9 mm) and controlled inlet/outlet geometry.

---

### 4. Expected Behaviour
- High static pressure at low flow (ideal for vacuum downforce).  
- Good efficiency for a small coreless motor (<10 W).  
- Stable operation near the shut‑off region.  
- Lower noise and smoother flow than straight radial blades.

---

### 5. Why This Geometry Works
- **Large diameter** maximizes tip speed.  
- **Small eye** increases blade length and pressure capability.  
- **Backward‑curved outlet** improves pressure and efficiency.  
- **Moderate blade count** reduces slip without excessive blockage.  
- **Smooth curvature** minimizes turbulence and loss.

---

## 32 mm Impeller at 10 000 RPM – What It Means

### 1. Tip Speed

Given:
- **Outer diameter (Do):** 32 mm → **radius (ro):** 0.016 m  
- **Speed:** 10 000 RPM → 10 000 / 60 ≈ 166.7 rps  

Tip speed:


$$
U = 2\pi r_o n \approx 2\pi \cdot 0.016 \cdot 166.7 \approx 16.8\ \text{m/s}
$$



So the blade tips are moving at **≈17 m/s**.

---

### 2. Order‑of‑Magnitude Pressure Estimate

A rough scaling for the available dynamic pressure is:


$$
q = \tfrac{1}{2} \rho U^2
$$


With air density $\rho \approx 1.2\ \text{kg/m}^3$:


$$
q \approx 0.5 \cdot 1.2 \cdot 16.8^2 \approx 170\ \text{Pa}
$$



A well‑designed small centrifugal fan can convert a significant fraction of this into **static pressure**, so a **plenum pressure** on the order of **100–300 Pa** is a reasonable target at 10 000 RPM.

---

### 3. Downforce Estimate

Effective vacuum area (inside rigid skirt):
- Assume ≈ **80 mm × 50 mm** →  
  

$$
  A \approx 0.08 \cdot 0.05 = 0.004\ \text{m}^2
$$



Downforce:


$$
F = \Delta P \cdot A
$$



For $\Delta P$ in the range 100–300 Pa:
- **100 Pa:** $F \approx 0.4\ \text{N}$ (≈40 g‑force)  
- **300 Pa:** $F \approx 1.2\ \text{N}$ (≈120 g‑force)

So you’re plausibly in the **tens to low hundreds of grams of extra downforce**, depending on how well the skirts seal and how efficient the fan and housing are.

---

### 4. Design Implications at 10 000 RPM

- The **32 mm, backward‑curved impeller** is well‑matched to this speed for a compact robot.  
- To push toward the upper end of the pressure range:
  - Keep **clearances tight** (impeller–volute, impeller–shrouds).  
  - Use a **proper housing/scroll**, not free‑space discharge.  
  - Tune the **aperture diameter** (≈eye size, slightly smaller) to bias toward low flow / high pressure.  
  - Minimize leakage under and around the skirts.


If you later find you can safely run faster than 10 000 RPM, pressure will rise roughly with **RPM²**, but power demand will rise with **RPM³**, so you’ll quickly hit your 10 W limit.

---

## Compact Scroll Design for a 32 mm Impeller

### 1. Key Geometry

Assume:
- **Impeller outer diameter:** $D_o = 32\ \text{mm}$ ($r_o = 16\ \text{mm}$)  
- **Blade width (axial):** $b \approx 4\ \text{mm}$  
- **Plenum footprint:** fits within 80 mm × 50 mm

#### Casing and Scroll

- **Casing inner radius:**  
  $r_c \approx r_o + 1.5\ \text{mm} \Rightarrow r_c \approx 17.5\ \text{mm}$  
  (gives $\approx 1.5\ \text{mm}$ radial clearance)

- **Tongue (cut‑off) radius:**  
  $r_t \approx r_o + 0.5\ \text{mm} \Rightarrow r_t \approx 16.5\ \text{mm}$

- **Outlet (scroll) height:**  
  Same as blade width: $b \approx 4\ \text{mm}$

- **Outlet width (tangential):**  
  Start with $W_{\text{out}} \approx 8$–$10\ \text{mm}$

- **Scroll angle coverage:**  
  About $240^\circ$–$270^\circ$ around the impeller before the outlet.

---

### 2. Scroll Shape (Plan View)

Define:
- Center at $(0,0)$  
- Tongue at angle $\theta = 0^\circ$ (pointing toward outlet)

#### Simple Logarithmic‑Like Expansion

Let the scroll inner radius $r_s(\theta)$ grow from $r_t$ to $r_c$ over $\theta = 0^\circ$ to $\theta = 240^\circ$:

$$
r_s(\theta) = r_t + (r_c - r_t)\,\frac{\theta}{240^\circ},\quad 0^\circ \le \theta \le 240^\circ
$$

- **Inner scroll wall:** radius $r_s(\theta)$  
- **Outer scroll wall:** radius $r_s(\theta) + b_{\text{eff}}$  
  where $b_{\text{eff}}$ is the effective radial thickness of the flow passage (e.g. 4–5 mm in plan).

At $\theta \approx 240^\circ$–$270^\circ$, open into a **rectangular outlet** of width $W_{\text{out}}$.

---

### 3. Axial Section

- **Impeller sandwiched** between:
  - Bottom plate (plenum roof)  
  - Top cover (fan housing lid)

- **Axial clearances:**  
  $0.2$–$0.5\ \text{mm}$ between blade tips and each shroud/plate.

- **Outlet duct height:**  
  Same as impeller width ($\approx 4\ \text{mm}$).

---

### 4. Practical CAD Modelling Procedure

1. **Set reference circles**
   - Draw circles of radius $r_i = 7\ \text{mm}$ and $r_o = 16\ \text{mm}$ for the impeller.
   - Draw casing circle $r_c \approx 17.5\ \text{mm}$.

2. **Place the tongue**
   - On the $+x$ axis, set the tongue point at radius $r_t \approx 16.5\ \text{mm}$.
   - Create a short flat segment normal to the radius to form the cut‑off.

3. **Create the scroll**
   - For $\theta$ from $0^\circ$ to $240^\circ$, sample a few angles (e.g. every $30^\circ$) and plot points at radius $r_s(\theta)$.
   - Fit a smooth spline through these points for the **inner scroll wall**.
   - Offset this spline outward by $b_{\text{eff}}$ (4–5 mm) to form the **outer scroll wall**.

4. **Define the outlet**
   - At $\theta \approx 240^\circ$–$270^\circ$, trim the scroll and attach a rectangular outlet:
     - Height (axial): $4\ \text{mm}$  
     - Width (plan): $8$–$10\ \text{mm}$, tangential to the scroll.

5. **Add the impeller cavity**
   - Extrude the scroll region to the impeller width plus clearances.
   - Add the central inlet (eye) hole aligned with your aperture.

6. **Integrate with plenum**
   - Place this scroll/fan module over the plenum so the **eye aligns with the plate aperture**.
   - Ensure smooth internal transitions from plenum to eye (fillets or chamfers).

---

### 5. Iterative Refinement

- **CFD or simple tests:**  
  - Vary $W_{\text{out}}$ and $r_c$ slightly to see effects on pressure and power.
- **Physical tuning:**  
  - Start with the above geometry, then adjust:
    - Tongue clearance ($r_t - r_o$)  
    - Outlet width  
    - Aperture diameter  
  to maximize measured plenum pressure at your fixed 10 000 RPM.

This minimal scroll gives you real **pressure recovery** without consuming much of your 80 mm × 50 mm footprint.

---

## Ways to Increase Downforce Beyond RPM and Area

You’re basically capped on **speed** and **area**, so the game becomes: **get more usable ΔP for the same power** and **turn more of that ΔP into effective hold‑down**.

---

### 1. Reduce Leakage and Raise Effective ΔP

- **Tighter primary gap**
  - Reduce the rigid skirt gap from 1 mm toward **0.5 mm or less** if terrain allows.
  - Smaller gap → higher flow resistance → higher achievable plenum pressure for the same fan.

- **Smarter flexible skirt**
  - Use a **very compliant, low‑friction material** (thin silicone, PTFE‑coated fabric) so it conforms with minimal lift.
  - Add **multiple lips or ribs** on the underside to create **serial restrictions** instead of one big leak path.

- **Edge shaping**
  - Slight chamfer or radius on the rigid skirt edge can reduce local leakage jets and help the flexible skirt seal.

---

### 2. Improve Fan and Housing Efficiency

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

---

### 3. Optimize Aperture and Flow Regime

- **Tune aperture diameter**
  - Use the aperture as a **throttle** to push the fan toward its **max‑pressure, low‑flow** point.
  - Experiment with a few diameters (e.g. 8, 10, 12 mm) and pick the one that gives **highest measured plenum pressure** at your fixed RPM.

- **Control internal flow paths**
  - Avoid narrow, high‑loss passages between different parts of the plenum.
  - Aim for **uniform pressure** under the whole footprint so all area contributes to downforce.

---

### 4. Mechanical and Structural Tweaks

- **Stiffen the base**
  - If the robot base flexes under vacuum, the gap changes and you lose control of leakage.
  - A **stiff, flat plate** maintains a consistent gap and pressure distribution.

- **Mass distribution**
  - Put some mass near the skirt perimeter so the skirt maintains contact and doesn’t “hover” locally.

---

### 5. Use “Dynamic” Tricks

- **Textured underside**
  - Very fine, shallow textures can help the flexible skirt avoid sticking while still sealing.
- **Segmented skirts**
  - Divide the outer skirt into **sections** that can independently conform to local bumps, improving average sealing.

---

In short: with RPM and area fixed, your biggest wins come from **leakage reduction**, **fan/scroll efficiency**, and **careful tuning of the aperture and skirt system** so that as much of your limited power as possible becomes **uniform, high ΔP** under the robot.

#### Overview

You want **maximum static pressure** in the plenum. The **fan diameter $D_f$**, **eye diameter $D_e$**, and **aperture diameter $D_a$** together control:

- How much pressure the fan can theoretically generate (mainly $D_f$ and speed),
- How “pressure‑oriented” the impeller is (ratio $D_e / D_f$),
- How much flow is actually allowed into the fan (strongly influenced by $D_a$).

Static pressure is maximized when the fan operates near its **peak‑pressure, low‑flow** point, without wasting too much pressure across the aperture.

---

#### 1. Fan diameter $D_f$ and eye diameter $D_e$

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

#### 2. Aperture diameter $D_a$ vs eye diameter $D_e$

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

#### 3. Combined design logic for maximum static pressure

1. **Maximize $D_f$** within your layout → higher potential $\Delta P$.
2. **Choose $D_e$** so $D_e / D_f$ is on the **pressure‑oriented side** (about $0.4$–$0.6$).
3. **Set $D_a$ close to $D_e$** and tune it slightly smaller to:
   - Push the operating point toward the **high‑pressure, low‑flow** region,
   - Avoid burning most of the pressure across the aperture itself.

In short:
- $D_f$ sets how much pressure you *could* have,
- $D_e$ biases the impeller toward pressure vs flow,
- $D_a$ decides how much of that potential pressure actually appears in the **plenum** instead of being lost at the inlet.

