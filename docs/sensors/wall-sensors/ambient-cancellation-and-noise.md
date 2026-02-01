---
layout: default
title: Ambient Illumination and Noise
parent: Sensors
# icon: octicons/dot-fill-16
icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
---


# Ambient Illumination and Noise

Measuring the ambient light is essential so that we can eliminate eliminate it from our measurements and isolate only the signal caused by the proximity of the walls. In principle is is very easy to do with two measurements. One measurement is taken with the emitter off (the 'dark' reading, $A_{dark}$) and then another is taken with the emitter on (the 'lit' reading , $A_{lit}$). Now the raw distance reading , $A_{raw}$, is just the difference between them

$$
A_{raw} = A_{lit} - A_{dark}
$$

In a perfect world, $A_{raw}$ would be a single, stable number related to the distance to the wall. Real sensor systems are very unlikely to behave that well. The whole sensor system has several sources of noise and interference which can be divided into two broad categories:

- **Measurement Noise**

    This is noise in the measured signal that is a result of some aspect of the whole sensor measurement system. It may be the behaviour of the ADC, power supply noise, interference from other circuits on the robot or poor PCB layout.

- **Process Noise**

    This is noise caused by unpredictable changes in light level caused by the environment - including ambient illumination, robot motion and variations in the walls.

For the time being, we we'll treat all these as just 'noise'. Later, some of these sources might be isolated and, hopefully, reduced or eliminated.

## Noise

Inevitably, any measurement system will have some noise. Some possible sources of that noise have already been listed. An experiment will let us see how significant that might be in a basic micromouse wall sensor.

For simple experiments, a circuit is built on a breadboard so that some of these effects can be examined. A processor module carries the STM32U575 processor, a constant-current source provides the drive for an emitter LED and a phototransistor detector has a load resistor to ground, providing a voltage proportional to the photocurrent. The emitter is a SFH4550 with 100mA pulses and the detector is a SFH409-FA. The -FA suffix indicates that the part has a filter that blocks visible light.

![Test Rig](../../assets/sensors/test-setup.jpg)
/// caption
Sensor Test Rig
///

The system operates the sensor exactly as it might on a micromouse. The emitter pulses are 25us long and the ADC is sampled before and at the end of the emitter pulse. The dark an lit readings are then printed out to the serial port followed by the raw value and a filtered version of the raw value. Four numbers altogether.

A Python script reads these numbers and draws a live-updating frequency histogram for each. In the charts below, the x-axis is ADC counts and the converter has a 16 bit resolution. Each count then is worth just 0.2mV and the minor grid lines are 20 counts (4mV) apart. To keep things visible on one chart, the wall is placed 70mm away and the detector load adjusted to give readings in a useable range.

### Noise Baseline

To get an idea of how well the processor and its ADC are working, we start by connecting the ADC input to a nearby low impedance voltage divider and recording the results for a minute or two:

![Noise Baseline](../../assets/sensors/potential-divider-baseline.png)
/// caption
Noise Baseline
///

There are actually four lines on the chart though they are drawn one over another so you may not always see them all.

- Red: the dark reading $A_{dark}$
- Blue: the lit reading $A_{lit}$
- Green: the raw reading $A_{raw}$
- Magenta: the filtered raw reading $A_{filt}$

In this chart you can see that the lit and dark readings are nearly identical, so the raw and filtered readings are (pretty much) zero. There is some noise as evidenced by the spread in the lit and dark readings. This appears to be purely random (Gaussian) noise. Because this noise is not identical for the lit and dark values there is also some small spread in the raw value.

Note that in a chart like this, the area under the line is the number of readings taken. That means that a signal with a lot of noise will appear to have a wider spread and lower peak compared to one that has very little noise where you would see a narrower, but higher, peak.

Because the lit and dark readings have the same underlying value, subtracting them removes the common part of the signal - that would be the ambient illumination and any other constant offset voltage. The noise itself doesn’t cancel - it adds - but since the mean is zero, the result is a narrow, high peak.

Another important observation is that the lit and dark values have almost identical averages. That tells us that switching the emitter on and off is not disturbing the processor or the ADC in any measurable way.

### Basic Range Measurement

Now we have some idea about the noise that appears to be intrinsic to the measurement system, and we are confident that the emitter pulses are not causing any side effects in the detected signal.

The next step is to connect the ADC input to the detector and perform a measurement against a fixed wall. For now, the ambient illumination is an LED lamp in the ceiling. This has almost no IR output and so it should not affect the detector owing to the filter on the SFH409-FA. This, and all future runs, capture exactly 50,000 results in the histogram.

![LED Ambient](../../assets/sensors/LED-ambient-illumination.png)
/// caption
Record with LED lighting
///

It should be clear that the dark readings (red) are still able to pick up some interference from somewhere, even with LED lighting. The variance (spread of values) is larger than we saw with the potential divider and the curve is not very neat. This may be due to some power supply noise since the layout on breadboards is less than ideal. The lit response (blue) has a similar shape though it is not so easy to see in this record because the low ambient illumination  means that the raw value (green) is close to the lit value.

You should notice that the raw reading still has a similar variance to that seen in the lit value but the shape is much cleaner. Any external or other noise that does not change much between sample intervals (25us) will be cancelled out by the raw reading calculation. The filtered raw values (magenta) are very clean as you might expect.

The ambient illumination can be increased significantly by lighting the rig with a LED table lamp about 15cm from the wall surface. When the run is repeated under these conditions, this is the result.

![Bright LED Ambient](../../assets/sensors/LED-ambient-illumination-bright.png)
/// caption
Record with Bright LED lighting
///

This result is almost indistinguishable from the previous experiment, and demonstrates the effectiveness of the visible light filtering on the SFH409-FA.

### Steady Ambient IR illumination

Modern LED interior lighting often produces little IR radiation and so it can be easy to underestimate the effect of sunlight and other lighting types that do emit IR. It would be very optimistic to expect a sensor like this to operate reliably in direct sunlight but there may be indirect, or partially occluded, sunlight falling on the walls of a contest maze. An easy way to simulate this is with an old-fashioned flashlight containing an incandescent bulb. 

The wall is illuminated in this way and another run is made.

![Flashlight Ambient](../../assets/sensors/flashlight-ambient-illumination.png)
/// caption
Record with IR illumination from a flashlight.
///

The flashlight produces a almost constant level of illumination and the effect of that is very clear from the result chart. With the flashlight dominating the readings, even when the emitter is off, the noise variance returns to the intrinsic measurement noise level seen earlier. Remember that one minor division on these charts is only about 4mV variation in the reading. The dark readings are all clustered around about the 180 mark and the lit readings are also shifted up by the same amount. Since both the dark and the lit readings have been shifted by the same amount, the raw reading, being the difference between them remains almost exactly the same. Close inspection reveals it to be slightly higher than before because, with this type of sensor, there is a small change in gain with the level of illumination. For this particular example, the change is about 1.5% and the level of IR illumination at the wall is quite significant.

### Variable Ambient IR illumination

Suppose now that the contest illumination is not LEDs but some other type that does emit significant IR. Incandescent bulbs are very rare now but may still be present in older values or houses. These types of bulb actually flash on and off at 100Hz as the 50Hz AC mains flows back and forth through the filament, producing light pulses in each half cycle. Now lets use a small (15W) incandescent bulb in a table lamp about 20cm away from the wall in an attempt to get similar average levels of illumination as those seen with the flashlight.

![Incandescent Ambient](../../assets/sensors/incandescent-ambient-illumination.png)
/// caption
Record with IR illumination from an incandescent bulb.
///

Notice how both the dark and lit responses are much more spread out. Each has two peaks because more samples correspond to the brighter portions of each cycle than the darker portions that correspond to the current through the lamp passing through zero. The filament does not cool down enough to stop glowing, it just puts out a little less light.

In spite of that spreading, the raw value response is very clean and looks exactly like that for the steady IR illumination from the flashlight. Although the table lamp is clearly varying a lot in intensity, those changes are very slow compared to the 25us interval between readings that the sensors can manage.

### Visible Light Sensors

Some builders prefer to use a detector that does not have a visible light filter. These can be more sensitive and are essential if a visible light emitter is used. For comparison then, the sensor in the test rig was replaced with a BPW85C. The load resistor is reduced to just 220 Ohms because of the increased sensitivity of theis phototransistor. The emitter device current remains as before.

Repeating the basic run with only the room's LED ambient light immediately reveals that the phototransistor has a noticeable response to visible light.

![LED Ambient, Visible detector](../../assets/sensors/LED-ambient-BPW85.png)
/// caption
Record with LED room lighting and the BPW85C detector.
///

The measurement noise, as indicated by the width of the response, is still the same but the dark reading's average value is distinctly greater.

Now see what happens with the incandescent lamp:

![LED Ambient, Visible detector](../../assets/sensors/incandescent-ambient-BPW85.png)
/// caption
Record with incandescent lighting and the BPW85C detector.
///

To get a similar response to the SFH409-FA experiment, the lamp had to be moved back to 36cm, demonstrating how much more the BPW85 is susceptible to ambient interference. without the filter, it is able to respond to a much wider range of wavelengths and they are all being emitted by the incandescent bulb. You should notice that the responses are wider again but that the raw and filtered responses are just as clean as they were before.

## Summary

It should be clear that the ambient cancellation technique is very good at reducing, or eliminating the effects of ambient illumination (process noise) but it cannot eliminate measurement noise that is an intrinsic part of the sensor system. However, the measurement noise can be significantly reduced by filtering so long as we are prepared to accept a delay in the response.
