---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---


# Photodiode Detectors


A photodiode is a specially constructed diode with its junction exposed to incoming light. For sensing applications, it is almost always used in photoconductive mode, where the diode is reverse‑biased with the cathode connected to the supply and the anode connected through a load resistor to ground. (Photovoltaic mode, with no bias, is possible but slower and produces lower output.)

When light reaches the junction, a small current—the photocurrent—is generated and flows through the load resistor. Typical photocurrents in these sensors may be only a few tens of microamps, so the load resistor must be much larger than that used with an emitter‑follower phototransistor detector. Values in the range of 10 kΩ to 100 kΩ are common.

![Photodiode Detector](../../assets/sensors/photodiode-detector.png)
/// caption
Simple Photodiode Detector in photoconductive mode
///

Because the photocurrent is small, the circuit has a high source impedance. This slows ADC readings, since the ADC’s sampling capacitor must charge through the load resistor, increasing the RC time constant. A large load resistor also increases noise and can reduce response speed, as the diode’s junction capacitance must be charged and discharged. Output can be increased by using a photodiode with a larger active area—photocurrent is proportional to area—or by using higher illumination levels than would be required for a phototransistor detector.

Photodiodes offer two important advantages. First, they are much faster than phototransistors when responding to pulsed illumination. This may not matter if your ADC cannot sample at hundreds of kilohertz or more, but it can be valuable in some designs. Second, photodiodes are intrinsically more linear over a wide range of illumination levels. However, as the output voltage approaches the supply, the reverse bias is reduced and linearity suffers. When operated between supply and ground, the output will flatten as it nears the supply—much like a phototransistor—especially within the last 0.5–1.0 V.

Under reverse bias, the diode produces almost no current in darkness, and the photocurrent is directly proportional to the amount of light absorbed by the active region. This behaviour leads to three key characteristics:

photocurrent is proportional to the active region area

photocurrent is very linear with changes in incident light

photocurrent is typically very small

The dependence on active area is worth emphasising. A larger active region increases sensitivity but requires a physically larger package. Some photodiode packages omit a lens to maximise active area; this increases photocurrent but also widens the acceptance angle, making the device more susceptible to ambient light and reducing directional selectivity.

Finally, photodiodes have wavelength‑dependent responsivity. As with phototransistors, you should choose a photodiode whose spectral response matches the wavelength of your emitter to maximise efficiency and signal‑to‑noise performance.