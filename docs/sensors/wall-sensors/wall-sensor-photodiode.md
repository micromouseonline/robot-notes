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

Alternatively, the photodiode can be used in photovoltaic mode where there is no bias across the junction. The photocurrent appears as a voltage across the diode - a little like a battery. The open circuit voltage can be measured and will be proportional not to the illumination but the _logarithm_ of the illumination. Connecting a load resistor in parallel allows the photocurrent to flow through the load resistor. The voltage then measured will be somewhat lower than the open-circuit voltage across the photodiode. In this mode, th photocurrent will be the same, but the rise time will be slower than in photoconductive mode. Although the speed may be significantly slower, it will still be much faster than that of a phototransistor detector. Response speed is limited by junction capacitance. Larger junction areas have higher capacitance, which increases the time constant and reduces response time. Response times can still be in the tens to hundreds of nanoseconds.

Attempting to measure the output in this way is unlikely to be reliable as the source impedance is very high.


## Transimpedance Amplifier (TIA)

We can, however, make use of the photovoltaic mode by forcing the bias to be very close to zero and then the photocurrent can be used as part of a feedback loop with an operational amplifier. A transimpedance amplifier is commonly used to convert the photocurrent into a voltage. The op‑amp’s non‑inverting input is grounded, and the photodiode is connected with its anode at ground and its cathode at the inverting input. 

The voltage across the diode remains near zero because the op‑amp, through negative feedback, forces the inverting input to match the grounded non‑inverting input. A feedback resistor connects the op‑amp output to the inverting input. 

When illuminated, the photodiode wants current to flow internally from its cathode to its anode. Because the op‑amp input draws negligible current, all the photocurrent must flow through the feedback resistor from the output of the op-amp. For that to happen, the op-amp must take its output positive. The value of the feedback resistor sets the transimpedance gain and therefore the output voltage range.

![transimpedance amplifier](../../assets/sensors/photovoltaic-tia.png)
/// caption
Simple Transimpedance Amplifier for Photodiode
///

The output voltage will now be linearly proportional to the illumination, up to the point where it is clipped by the op-amp output voltage limit. Unless the op-amp can bring its output all the way to the ground rail, the minimum output, even in the dark, will have some constant voltage.

$$
V_{out} = I_p \times R_f
$$

Where $I_p$ is the photocurrent and $R_f$ is the feedback resistance.

Practical implementations require a small capacitor is added in parallel with the feedback resistor to ensure stability at high frequencies. Note also that the op-amp must have a very high input impedance and a very low input offset current.

While the op-amp tries to keep the inputs identical, in reality, there is always a few millivolts of difference (the offset). In photovoltaic mode, this small offset acts as a tiny unintended bias across the diode. If $V_{os}$ is high, it can actually introduce a small "dark current" even though you've grounded the anode. This is why high-precision TIAs use "zero-drift" or "chopper-stabilized" op-amps.

This method is probably the simplest way to use a photodiode with an operational amplifier to get a positive-going voltage that is linearly proportional to illumination. The output will have a low impedance, suitable for measurement by an ADC and cannot exceed the supply voltage so should be safe for the processor pin. Some op-amps may have an output range that is a fraction of a volt above the power supply voltage but this should not be a problem in practice. Add a resistor of perhaps 1k in series between the op-amp and the GPIO pin to limit any current that may flow.



## Photodiode Advantages

In general, photodiodes offer two important advantages over phototransistors. 
 
 - First, they are much faster when responding to pulsed illumination. This may not matter if your ADC cannot sample at hundreds of kilohertz or more, but it can be valuable in some designs. 

 - Second, photodiodes are intrinsically more linear over a wide range of illumination levels. This means that the pulse current in very high ambient illumination is going to pretty much the same as the pulse current in very low ambient illumination. Of course, if the ambient has used up all the headroom in your circuit, that is still a problem.

## Disadvantages

Primarily, the problem with photodiodes is the very small photocurrent which may be only microamps in magnitude. This means you must either have large load resistors - which are bad for driving the ADC input - or very large pulse currents to ensure an adequate response. The transimpedance amplifier makes it easier to interface with an ADC but does not help with the DC offset problem. There are, however, circuits and devices that can remove DC offset using another op-amp. There is always a way to 'fix' some shortcoming by adding more hardware. For other approaches, have a look at the pages on [interference cancellation](./ambient-cancellation-and-noise.md).

The desirability of larger pulse currents to mitigate the effect of ambient illumination is also somewhat true for phototransistors.

