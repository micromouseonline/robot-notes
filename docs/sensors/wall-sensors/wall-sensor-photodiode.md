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


A photodiode is a specially constructed diode with its junction exposed to incoming light.

When light reaches the junction, a small current - the photocurrent - is generated and is able to flow through any load resistor. Typical photocurrents in these sensors may be only a few tens of microamps.

The diode produces almost no current in darkness, and the photocurrent is directly proportional to the amount of light absorbed by the active region. This behaviour leads to three key characteristics:

- photocurrent is proportional to the active region area
- photocurrent is very linear with changes in incident light
- photocurrent is typically very small

The dependence on active area is worth emphasising. A larger active region increases sensitivity but requires a physically larger package. Some photodiode packages omit a lens to maximise active area. This increases photocurrent but also widens the acceptance angle, making the device more susceptible to ambient light and reducing directional selectivity.

Photodiodes have wavelength‑dependent responsivity. As with phototransistors, you should choose a photodiode whose spectral response matches the wavelength of your emitter to maximise efficiency and signal‑to‑noise performance.

## Photoconductive Mode

For sensing applications, it is often used in photoconductive mode, where the diode is reverse‑biased with the cathode connected to the supply. The photocurrent is largely independent of the junction bias and is linearly proportional to illumination. This current can be passed through a resistor to generate a voltage.

![Photodiode Detector](../../assets/sensors/photodiode-detector.png)
/// caption
Simple Photodiode Detector in photoconductive mode
///

Because the photocurrent is small, The load resistor must be much larger than that used with a phototransistor detector. Values in the range of 10 kΩ to 100 kΩ are common. This kind of circuit naturally has a large source impedance which can be an issue when it is used to drive an ADC input since they require low source impedances. A buffer amplifier should be used for best results.

Reverse biasing the junction decreases the junction capacitance and so speeds up the response. Photodiodes used in this mode can have response times measured in nanoseconds.

Suitable transimpedance amplifiers for use with photoconductive mode are slightly more complicated than for photovoltaic mode and, for micromouse sensors, it is almost certainly not worth the extra work. IT will be easier to use the device in photovoltaic mode.


## Photovoltaic Mode

Alternatively, the photodiode can be used in photovoltaic mode where there is no bias across the junction. The photocurrent appears as a voltage across the diode - a little like a battery. The open circuit voltage can be measured and will be proportional not to the illumination but the _logarithm_ of the illumination. Connecting a load resistor in parallel allows the photocurrent to flow through the load resistor. The voltage then measured will be somewhat lower than the open-circuit voltage across the photodiode. In this mode, the response will be smaller, and slower than in photoconductive mode. Although the speed may be significantly slower, it will still be much faster than that of a phototransistor detector. Response speed is limited by junction capacitance. Larger junction areas have higher capacitance, which increases the time constant and reduces response time. Response times can still be in the tens to hundreds of nanoseconds.

Attempting to measure the output in this way is unlikely to be reliable as the source impedance is very high.

In photovoltaic mode, the photodiode must be held at (approximately) zero volts  across its junction and a transimpedance amplifier is normally used to convert the photocurrent into a low impedance voltage that the processor can easily convert through its ADC. An operational amplifier has its non-inverting input connected to ground and a feedback resistor connected between the output and the inverting input. The photodiode is connected with its anode to ground and the cathode to the inverting input. Since the (ideal) op-amp takes no current at its inputs, the photocurrent must also pass through the feedback resistor, The op-amp output voltage then will increase to ensure that current can flow. Feedback resistors are selected to provide a suitable range of output voltages.

![Photovoltaic Mode Detector](../../assets/sensors/photovoltaic-tia.png)
/// caption
Transimpedance Amplifier for Photovoltaic mode
///

The output voltage will now be linearly proportional to the illumination, up to the point where it is clipped by the op-amp output voltage limit. Unless the op-amp can bring its output all the way to the ground rail, the minimum output, even in the dark, will have some constant voltage.

A small capacitor is added in parallel with the feedback resistor to ensure stability at high frequencies.

This method is probably the simplest way to use a photodiode get a positive-going voltage that is linearly proportional to illumination. The output will have a low impedance, suitable for measurement by an ADC and cannot exceed the supply voltage so should be safe for the processor pin.

## Advantages

In general, photodiodes offer two important advantages over phototransistors. First, they are much faster when responding to pulsed illumination. This may not matter if your ADC cannot sample at hundreds of kilohertz or more, but it can be valuable in some designs. Second, photodiodes are intrinsically more linear over a wide range of illumination levels. However, in the simple circuit above, as the output voltage approaches the supply, the reverse bias is reduced and linearity suffers. When operated between supply and ground, the output will flatten as it nears the supply—much like a phototransistor—especially within the last 0.5–1.0 V.


