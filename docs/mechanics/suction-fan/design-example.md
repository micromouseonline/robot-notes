---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
title: Fan Design Example
subtitle: 
description:
# icon: octicons/dot-fill-16
icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---


## Example Impeller Geometry for a 32 mm Centrifugal Fan


!!! warning

    Summarised responses from CoPilot

    These notes are unverified and not tested


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

## 32 mm Impeller at 10 000 RPM

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

### 2. Pressure Estimate

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

(Note that D5A can manage 200-300g downforce)

---

### 4. Design Implications

- The **32 mm, backward‑curved impeller** is well‑matched to this speed for a compact robot.  To push toward the upper end of the pressure range:
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

***Casing and Scroll***

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

**Simple Logarithmic‑Like Expansion**

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

### 4. Practical CAD Modelling

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

