---
layout: default
title: Ambient Illumination and Noise
parent: Sensors
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
---


# Ambient Illumination and Noise

This section will show you how to understand, measure and mitigate various sources of interference found in micromouse wall sensor systems.

Wall sensors do not operate in a controlled, sterile, laboratory environment. Instead, they must deal with interference from other light sources as well as noise in the measurement system itself.

While there are many options available, the most common types of micromouse wall sensors determine the distance to nearby walls by measuring the amount of light reflected from them when illuminated by an LED. In any real contest environment, there are other sources of light that also illuminate the walls and so we need a way to account for that. Some of those sources are going to have a constant, or slowly changing value. Think of daylight from outside the room and how that can change as cloud cover changes. People moving around the room can cast variable shadows. Other sources might include room lighting that may flicker at twice the mains frequency. Dimmable lighting may be flickering at several thousand Hz. Much is often made of the effect of camera flashes or Infra Red range finders. These can be potent sources of interference but are usually transient.

Even if you can account for, and eliminate, the effect of ambient illuminations, the measurement process itself has various sources of uncertainty. The timing of ADC operations and emitter pulses are critical and must be handled consistently. Processor interrupts can disrupt that timing. The ADC itself has inevitable quantisation errors because it can only record discrete values and the other parts of the robot may generate electrical interference through the power supply or by coupling in signal lines.

the good news is that most of these sources of error can at least be reduced and, in some cases effectively eliminated. Other sources of error may be simply ignored as having little practical effect. The trick is knowing what you can prevent, what you can fix and what you can ignore.

If you read around, you will find that all these sources of interference can be considered as different types of noise and can be categorized into one of two types. Doing that lets us devise corrective measures appropriate to the source. Each category requires a different strategy to mitigate.

- **Measurement Noise**

    This is noise in the measured signal that is a result of some aspect of the whole sensor measurement system. It may be the behaviour of the ADC, power supply noise, interference from other circuits on the robot or poor PCB layout. Measurement noise comes from inside the robot.

- **Process Noise**

    This is noise caused by unpredictable changes in light level caused by the environment - including ambient illumination, robot motion and variations in the walls. Process noise comes from outside the robot.


For the time being, we'll treat all these as just 'noise'. Later, some of these sources might be isolated and, hopefully, reduced or eliminated.

With that in mind, we can look at how to measure the sensor signals in a way that lets us separate useful information from the noise:

- [Software Methods](./software-methods.md)
- [Filtering](./wall-sensor-filtered-data.md)
- [AC coupling]()
- [Duncanplexer](./duncanplexer.md)