---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---


# Wall Sensor Detector Types

For the kinds of reflected-light sensors described her, there are two basic choices, each with their own pros and cons. By far the most common choice is a phototransistor with a single load resistor. Less frequently, you might find photodiodes used in place of phototransistors. They can be used with a single load resistor but may benefit from adding a simple amplifier.

## Phototransistors



## Photodiodes



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
