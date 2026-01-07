---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---


# Wall Sensor Detector Types

For the kinds of reflected-light sensors described her, there are two basic choices, each with their own pros and cons. By far the most common choice is a phototransistor with a single load resistor. Less frequently, you might find photodiodes used in place of phototransistors. They can be used with a single load resistor but may benefit from adding a simple amplifier.

## Phototransistors

A phototransistor is a specially constructed bipolar transistor that exposes the base-collector junction to the outside world. Light falling on this junction generates a small current (the photocurrent) that flows into the base as it would any other bipolar transistor. The normal transistor action amplifies the current significantly, perhaps by a factor of 100 although different devices can vary greatly in the transistor gain. By connecting a load resistor between the emitter and ground, with the collector directly connected to the positive supply, you are able to measure a voltage at the emitter that is approximately linearly dependent on the illumination. This is called an emitter-follower configuration and typical load resistor values may be between 470 Ohms and 2.2kOhm. Linearity will be compromised as the transistor becomes saturated and the gain will decrease. The available dynamic range then will be somewhat less than the available supply voltage and the gain will be greatly reduced as the voltage starts to get within about 0.5 Volts of the suppply voltage and the transistor begins to saturate, reducing the gain significantly. Some care is needed in calculating a emitter resistor for a given range of operation. Also, the emitter-follower arrangement is somewhat less linear than the alternative common-emitter configuration where the load resistor is between the collector and the supply. Even so, micromouse sensors frequently use the emitter-follower circuit because it is easier to reason about more light producing a higher voltage. Another benefit is that the output impedance of the emitter-follower is very small which makes the measurement by the controller's ADC faster.

The response of a phototransistor is slower than that of a photodiode though this is likely to be of little practical consequence in a micromouse. In a typical circuit, the response is likely to have reached its steady state value in 20$\mu$s or so.


## Photodiodes

A photodiode is a specially constructed diode with the junction exposed to the outside world. In typical use as a sensor, the diode is reverse-biased with the cathode connected to the supply and the anode connected through a load resistor to ground. This is the **photoconductive** mode. (Photodiodes can also be used in photovoltaic mode with no bias, but that configuration is slower and produces lower output.) When exposed to light, a small current (the photocurrent) is generated at the junction and will flow to ground through the load resistor. Photocurrents in typical photodiodes used in these sensors may be no more than a few tens of microAmps. Because the photocurrents are very small, the load resistor will generally be much larger than that used with an emitter-follower phototransistor detector. The load resistor may need to be in the range 15kOhm to 100kOhm. The resulting high source impedance can make reading the value with microcontroller rather slower. A large load resistor will also increase the noise in the system. It can also reduce the response time as the diodes junction capacitance must be charged and discharged. The ADC input must charge its internal sampling capacitor through the load resistor, so a high source impedance increases the RC time constant and slows the conversion.  The output can also be increased by using a photodiode with a larger area - photocurrent is proportional to area - or by using higher illuminations that would be needed for a phototransistor detector.

Photodiodes have two important benefits which may, or may not, be important for use in a sensor. Firstly, they are much faster than phototransistors when reponding to the illuminating pulses. That will make no practical difference if your processor's ADC cannot sample at speeds of 1MHz or more but, usage varies. Secondly, a photodiode is intrinsically more linear over a much greater range of illumination levels than would be the case for a phototransistor. The main benefit here is that the output voltage can more closely approach the supply voltage while still maintaining linearity. That is, the available dynamic range will be greater. Bear in mind though that the use of an amplifier may compromise both speed and dynamic range. If needed, amplifier design is not hard but it involves several components and so more board space.

## Summary

Phototransistor give larger signals and simplified circuits at the expense of slower responses, reduced dynamic range, and poorer linearity.
Photodiodes offer higher speeds, larger dynamic range, and greater linearity at the expense of weaker outputs and higher impedance.

| Feature | Phototransistor | Photodiode |
|--------|------------------|------------|
| Basic mechanism | Bipolar transistor with light‑sensitive base–collector junction; photocurrent is amplified by transistor gain | PN junction diode with exposed junction; photocurrent flows directly with no internal gain |
| Typical photocurrent | Tens to hundreds of µA (after gain) | Tens of µA (no gain) |
| Output resistor range | ~470 Ω to 2.2 kΩ | ~15 kΩ to 100 kΩ |
| Output impedance | Low (fast ADC sampling) | High (slower ADC sampling, more noise) |
| Linearity | Moderate; degrades near saturation and at high illumination | Excellent; maintains linearity over a wide illumination range |
| Dynamic range | Limited by saturation and gain collapse near supply voltage | High; output can approach supply voltage without distortion |
| Speed | Slower (tens of µs typical) | Very fast (ns–µs range) |
| Circuit simplicity | Very simple; emitter‑follower gives intuitive “more light → higher voltage” | Simple but requires larger resistors and attention to ADC impedance |
| Best use cases | When signal strength is more important than speed or linearity | When speed, linearity, or wide dynamic range matter |
| Common micromouse usage | Very common due to strong signal and easy ADC interfacing | Less common but useful for high‑performance or high‑speed sensing |
