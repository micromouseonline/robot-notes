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

# Sensor Part Selection

Parts suggested here are among those commonly used in micromouse wall sensors and have a degree of proven use. Other parts may be available and may prove a better match for your design. For half-size robots in particular, it might be worth searching out more appropriately sized devices.

## Possible Combinations

### IR Phototransistors:

- 850nm: SFH4550 or VLSY5850 with BPW85C or SFH309-FA
- 950nm: SFH4545 or VLSY5950 with TEFT4300 or LTR4206E

### IR Photodiodes:
- 850nm: SFH4550 or VLCY5850 with SFH213-FA or QSB34CGR
- 950nm: SFH4545 or VLSY5950 with SFH213-FA or QSB34CGR or LTR4206E

### Visible Phototransistors
- TLCR5800 or VLCS5830 with TEPT5600 or BPW85C or SFH309





## Emitters

The emitter device should, ideally, illuminate only the wall over the working range of the sensor. Any light spilling over the wall is wasted at best and may upset the results if it is reflected from the floor. For a sensor operating with 50mm high walls, 200mm away, the included angle is 14 degrees. Try to ensure that the great majority of the light output falls within a narrower beam than that.

### Visible Light

Visible light emitters are particularly nice to use because they are much less likely to cause eye damage, they are easy to align and it is very clear when they are operating.

Most visible light emitters are going to be red in colour with wavelengths in the range 610nm to 650nm. Choosing red gets you good efficiency and a better match to many detectors that are likely to be optimised for Infra Red. These kinds of emitters are frequently used for signage and signalling applications and are generally easy to find. 

Choose a part with a very narrow beamwidth of less than 10$^\circ$ total (5$^\circ$ half-angle). The projected spot on a wall will generally end up as a square image of the LED chip's die with a small dark spot in the centre. This is not a problem in practice but may seem odd at first sight. 

You should arrange for the spot to be centered vertically on the wall at the maximum working range.

Two parts stand out for this job. They are extremely bright and almost identical except that the VLCS5830 typically has twice the output of the TLCR5800. When you buy these parts, be aware that they are grouped into different output ratings ('bins'). The difference between the lowest and highest rated bins may be a factor of 4 with the VLCS5830 or a factor of 50 for the TLCR5800. Depending on who you buy from, the parts may not have been sorted so it is possible to get parts in the same order that differ greatly in their actual output.

The VLCS5830 has a lowest output bin that is equivalent to the top range of TLCR5800 bins. 

For consistency and high output, the VLCY5830 is probably the better part.

Both parts come in a standard, clear 5mm LED package. High brightness parts with a narrow beam are not easy to find in 3mm or surface mount packages. Carefully examine the polar pattern in the datasheet. Reject any parts that have multiple output lobes as these will give misleading results as the angle changes.

#### TLCR5800 
   - [datasheet](https://www.vishay.com/docs/83178/tlcr5800.pdf){target="_blank"}

#### VLCS5830
   - [datasheet](https://www.vishay.com/docs/81892/vlcs5830.pdf){target="_blank"}

Possible SMD parts might include:

 - APDA3020SECK/J3-PF - [datasheet](https://www.kingbrightusa.com/images/catalog/SPEC/APDA3020SECK-J3-PF.pdf){target="_blank"}


### Infra Red

As with the visible emitters, high-intensity output devices with well-define, narrow beams are relatively rare. Some of these are used in sensors or as remote control transmitters. 

!!! warning "Eye Safety"

    IR emitters are invisible to the human eys and will not trigger a blink reflex. The light emitted by a sensor LED can be surprisingly powerful and there is risk oor eye damage if you look into an active emitter. 

Aside from the output level, package and beam shape, you also have to choose between two wavelength groups, determined by the material used in the LED junction. The selection is between outputs centred around 850nm and 940nm. Consider the choice carefully because typical detectors are similarly grouped and there is a considerable loss involved in using mismatched emitters and detectors. You might also find that 850nm emitters are faintly visible on some camera types and that 940nm detectors are a little less prone to ambient interference.

These too are likely to be much more readily available in a 5mm LED package rather than 3mm or SMT.

#### 850nm

##### SFH4550 
- [datasheet](https://look.ams-osram.com/m/7d214b223a9adb85/original/SFH-4550.pdf){target="_blank"}
- Comes in a 5mm clear package. 
- Peak wavelength 860nm. 
- Radiant intensity 1100mW/sr @ 100mA; 8500 mW/sr @ 1 Amp, 100$\mu s$
- Irradiance @ 100mA and 100mm $\approx 11mW/cm^2$
- Total Radiant Flux, 70mW @ 100mA
- 100mA continuous, $V_F = 1.5 V$
- 1 Amp peak, $V_F = 2.4 V$
- 3$^\circ$ half angle, no lobes

##### VLSY5850 
- [datasheet](https://www.vishay.com/doc/?83160){target="_blank"}
- Comes in a 5mm clear package. 
- Peak wavelength 850nm. 
- Radiant intensity 600mW/sr @ 100mA; 5100 mW/sr @ 1 Amp, 100$\mu s$
- Irradiance @ 100mA and 100mm $\approx 6mW/cm^2$
- Total Radiant Flux, 70mW @ 100mA
- 100mA continuous, $V_F = 1.65 V$
- 1 Amp peak, $V_F = 2.9 V$
- 3$^\circ$ half angle, no lobes


#### 940nm


##### SFH4545 
- [datasheet](https://look.ams-osram.com/m/3456970c8eccd2cb/original/SFH-4545.pdf){target="_blank"}
- Comes in a 5mm black, **conical** package. 
- Peak wavelength 950nm. 
- Radiant intensity 550mW/sr @ 100mA; 4200mW/sr @ 1 Amp, 25$\mu s$
- Irradiance @ 100mA and 100mm $\approx 5mW/cm^2$
- Total Radiant Flux, 55mW @ 100mA
- 100mA continuous, $V_F = 1.5 V$
- 1 Amp peak, $V_F = 2.3 V$
- 5$^\circ$ half angle, no lobes

##### VLSY5940 
- [datasheet](https://www.vishay.com/doc/?84240){target="_blank"}
- Comes in a 5mm clear package. 
- Peak wavelength 940nm. 
- Radiant intensity 600mW/sr @ 100mA; 5100mW/sr @ 1 Amp
- Irradiance @ 100mA and 100mm $\approx 6mW/cm^2$
- Total Radiant Flux, 55mW @ 100mA
- 100mA continuous, $V_F = 1.65 V$
- 1 Amp peak, $V_F = 2.9 V$
- 3$^\circ$ half angle, no lobes

## Detectors

The detector device needs to be able to see all of the illumination provided by the emitter and so will generally have a larger acceptance angle. Not so wide that it can see an excess of ambient illumination though. Having a wider acceptance angle not only makes it easier to manage the emitter and detector alignment, it will also help with the close-in, short-range response. The two deices will be placed with their axes close but not collinear. When the wall is very close, the detector may not be able to see the now tiny spot made by the emitter. To an extent, this is can be mitigated by pointing the detector slightly towards the emitter. It is also a good idea to make sure that the sensors, at the point of closest approach, do not suffer from a reduction in response. This is most easily achieved by placing the sensors well away from the edges of the robot. At all ranges, the response must be monotonic.

It is much easier to find suitable detectors in 3mm packages and these are, generally, more attractive when building a sensor assembly.

Detectors should be closely matched in wavelength where possible - something which is harder to manage with visible light emitters. When using IR emitters, you will be able to find a matching detector with very close to the same peak wavelength for sensitivity.

Some detectors are available in black, filtered packages intended to reduce the effect of ambient illumination. For IR emitters, these are a great idea but be careful not to select them in error for visible light emitters. Some parts have the same base number but are available in versions with and without the daylight filter. The SFH309 is a good example.

As with the emitters, parts may come from a range of sensitivity 'bins' and it is possible to receive, in one order, parts with a 4:1 range of sensitivities. Either buy carefully selected parts or be prepared to measure them before fitting so that you get reasonably well matched responses.

As with the emitters, check the datasheet for the shape of the polar response to make sure there are no side lobes. 

Sensitivity can be particularly hard to evaluate as the units are not always consistent and may include $mW/cm^2$ or lux, or both. 

### Phototransistors

#### SFH309 
- [datasheet](https://look.ams-osram.com/m/48f3c58ae57c5dfc/original/SFH-309.pdf){target="_blank"}
- 3mm clear package
- 860nm peak sensitivity
- Photocurrent typical: 3mA @ 1.0mW/cm^2; 4500uA @ 1000 lux
- Response > 80% @ 700nm - 1000nm 
- Response > 60% @ 620nm - 1050nm 
- Risetime: 7$\mu s$
- Saturation Voltage 0.2 Volts
- Half Angle $\pm$12 deg, no lobes

#### SFH309-FA 
- [datasheet](https://look.ams-osram.com/m/ce14b97f1982f0f/original/SFH-309-FA.pdf){target="_blank"}
- 3mm black package, daylight filtered
- 950nm peak sensitivity
- Photocurrent typical: 3mA @ 1.0mW/cm^2
- Response > 80% @ 800nm - 1000nm 
- Response > 60% @ 750nm - 1050nm 
- Risetime: 7$\mu s$
- Saturation Voltage 0.2 Volts
- Half Angle $\pm$12 deg, no lobes

#### BPW85C 
- [datasheet](https://www.vishay.com/docs/81531/bpw85a.pdf){target="_blank"}
- 3mm clear package
- 850nm peak sensitivity
- Photocurrent typical: 5mA @ 1.0mW/cm^2
- Response > 80% @ 750nm - 950nm 
- Response > 60% @ 650nm - 980nm 
- Risetime: 2$\mu s$
- Saturation Voltage 0.3 Volts
- Half Angle $\pm$ 25 deg, no lobes
  - BPW85A and BPW85B are lower sensitivity groups of same product

#### TEFT4300 
- [datasheet](https://www.vishay.com/docs/81549/teft4300.pdf){target="_blank"}
- 3mm black package, daylight filtered
- 925nm peak sensitivity
- Photocurrent typical: 3mA @ 1.0mW/cm^2
- Response > 80% @ 890nm - 970nm 
- Response > 60% @ 870nm - 990nm 
- Risetime: 2$\mu s$
- Saturation Voltage 0.3 Volts
- Half Angle $\pm$ 30 deg, no lobes, flat response
  - No response at <= 850nm

#### TEPT5600 
- [datasheet](https://www.vishay.com/docs/84768/tept5600.pdf){target="_blank"}
- 5mm clear package
- 570nm peak sensitivity, human eye response
- Photocurrent typical: 630uA @ 100lux, 3mA @ 1000lux
- Response > 80% @ 500nm - 700nm 
- Response > 60% @ 450nm - 770nm 
- Risetime: ??$\mu s$ (not given)
- Saturation Voltage 0.2 Volts
- Half Angle $\pm$ 20 deg, no lobes
  - Very Poor IR response

#### LTR4206E 
- [datasheet](https://www.mouser.com/catalog/specsheets/LTR-4206E.pdf){target="_blank"}
- 3mm black package with daylight filter
- 940nm peak sensitivity
- Photocurrent typical: 3mA @ 1.0mW/cm^2
- Response > 80% @ XXXnm - XXXXnm (not shown)
- Response > 60% @ XXXnm - XXXXnm (not shown)
- Risetime: 10$\mu s$
- Saturation Voltage 0.4 Volts
- Half Angle $\pm$ 10 deg, no lobes (estimated)
  - Narrow acceptance, oor datasheet missing spectral response




### Photodiodes


Photodiodes have a wavelength-dependent sensitivity. Like phototransistors, you need to select your photodiode to match the spectral characteristics of the emitter.


The devices shown here are mostly through-hole parts in lensed packages. Photodiodes are relatively uncommon in micromouse wall sensors. Only a few representative parts have been included. These have not been thoroughly tested.

#### SFH213 
- [datasheet](https://look.ams-osram.com/m/236756eb2a4c9193/original/SFH-213.pdf){target="_blank"}
- 5mm clear package
- 850nm peak sensitivity
- Sensitive Area 1mm^2
- Photocurrent typical: 0.135mA @ 1000 lux
- Response > 80% @ 700nm - 950nm 
- Response > 60% @ 600nm - 1000nm 
- Risetime: 5ns
- Half Angle $\pm$ 10 deg, no lobes
- broad response

#### SFH213-FA
- [datasheet](https://look.ams-osram.com/m/3798e9afd3f63ea8/original/SFH-213-FA.pdf){target="_blank"}
- 5mm black package, daylight filtered
- 900nm peak sensitivity
- Sensitive Area 1mm^2
- Photocurrent typical: 0.090mA @ 1.0mW/cm^2
- Response > 80% @ 810nm - 980nm 
- Response > 60% @ 790nm - 1020nm 
- Risetime: 5ns
- Half Angle $\pm$ 10 deg, no lobes
- no response below 700nm


#### SFH229
- [datasheet](https://look.ams-osram.com/m/2a0be50605895dac/original/SFH-229.pdf){target="_blank"}
- 3mm clear package
- 900nm peak sensitivity
- Sensitive Area 0.31mm^2
- Photocurrent typical: 0.038mA @ 1000 lux; 0.028mA @ 1mW/cm^2
- Response > 80% @ 700nm - 980nm 
- Response > 60% @ 590nm - 1020nm 
- Risetime: 1us
- Half Angle $\pm$ 15 deg, no lobes
- broad response

#### SFH229-FA
- [datasheet](https://look.ams-osram.com/m/594c1e47800b9bb9/original/SFH-229-FA.pdf){target="_blank"}
- 3mm black package, daylight filtered
- 900nm peak sensitivity
- Sensitive Area 0.31mm^2
- Photocurrent typical: 0.025mA @ 1mW/cm^2
- Response > 80% @ 800nm - 1000nm 
- Response > 60% @ 750nm - 1020nm 
- Risetime: 6us
- Half Angle $\pm$ 15 deg, no lobes
- no response below 700nm

#### QSB34CGR
- [datasheet](https://www.onsemi.com/download/data-sheet/pdf/qsb34-d.pdf){target="_blank"}
- 4mmx6mm SMT package
- 940nm peak sensitivity
- Sensitive Area 6.5mm^2
- Photocurrent typical: 0.037mA @ 1mW/cm^2
- Response > 80% @ 650nm - 1050nm 
- Response > 60% @ 500nm - 1050nm 
- Risetime: 50ns
- Half Angle $\pm$ 60 deg, no lobes
- Also available filtered as QSB34GR


