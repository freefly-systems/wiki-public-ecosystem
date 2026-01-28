# Technical Specs

## General Info

<table data-header-hidden><thead><tr><th width="253"></th><th></th></tr></thead><tbody><tr><td>Weight (g)</td><td><p>Astro's maximum payload weight is 1500 grams.</p><p>Wiris Pro Payload (including gimbal) is ~940g</p></td></tr><tr><td>Dimensions (mm)</td><td>When upright and forward facing, the Wiris Pro payload alone has the maximum outer dimensions as follows: 150(width) x 157(length) x 162(height)</td></tr><tr><td>Ingress Protection</td><td>None</td></tr><tr><td>Mount</td><td>Smart Dovetail</td></tr><tr><td>Operation Temperature</td><td>-20C to +50C</td></tr></tbody></table>

#### Range of Motion:

Numbers are maximums from a forward-facing and horizon-leveled position.

| Pan                         | Roll                | Tilt              |
| --------------------------- | ------------------- | ----------------- |
| +/- 170°. No continuous pan | 52° Left, 92° Right | 50° Up, 120° Down |

#### Flight Time

A single flight with Astro carrying the Wiris Pro Payload is typically 25-30 minutes. Note that the time presented in AMC is an estimate. The exact time depends on a number of factors such as temperature, air density, wind speed, and direction, as well as the flight profile of the aircraft.

{% hint style="info" %}
To extend flight times while focusing on a fixed area of interest, consider having Astro orbit around the area. In our testing, Astro is most efficient when orbiting at 7 m/s, rather than hovering. The orbit flight mode can be found by clicking on the map while on the ‘Fly’ screen, then clicking the orbit icon:

<img src="../../.gitbook/assets/image (83).png" alt="" data-size="original">
{% endhint %}

## Wiris Pro Camera Specs

#### Thermal Infrared Camera:

| Camera Modes                 | Photos at 640x512p, Video at 640x512p 30 FPS                                                                                                                                                                                           |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| File Formats                 | <p>JPEG images</p><p>Radiometric TIFF images</p><p>Radiometric full-frame IR recording (raw data recording in 30 Hz)</p>                                                                                                               |
| Exposure Modes               | Auto, Manual, Custom Incremental                                                                                                                                                                                                       |
| Color Pallets                | BlackRed, BlueRed, BWIron, BWIronI, BWRainbow, BWRainbowHC, BWRGB, Fire, Gradient, Gray, GraySlowFade, Iron1, Iron2, Natural, Rainbow, RainbowHC, Sepia, Steps, Temperature, WBRGB                                                     |
| Sensor Resolution (pixels)   | 640px x 512px                                                                                                                                                                                                                          |
| Lens Field of View (degrees) | <p>Wiris Pro Payload ships with a 13mm lens, approximately 45 x 37 degrees FOV (horizontal by vertical).</p><p><br><a href="https://workswell-thermal-camera.com/field-of-view-calculator/">Workswell Field of View Calculator</a></p> |

#### Visible Electro-Optic Camera:

| Camera Modes                            | Photo are 1920x1080px, video records at 720p 20 FPS                                                                                                                                      |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| File Formats                            | <p>JPEG images<br><br>h.264 (.mp4) video</p>                                                                                                                                             |
| Focus Mode                              | Continuous autofocus                                                                                                                                                                     |
| Sensor Resolution (pixels)              | 1920px x 1080px                                                                                                                                                                          |
| Sensor Size (mm)                        | 8.46mm (diagonal)                                                                                                                                                                        |
| Lens Horizontal Field of View (degrees) | <p>1x zoom → HFOV = 93.5 degrees</p><p>1.5x zoom → HFOV = 74.8 degrees</p><p>3x zoom → HFOV = 40.6 degrees</p><p>6x zoom → HFOV = 21.5 degrees</p><p>10x zoom → HFOV = 11.92 degrees</p> |

#### SSD capacity: 128GB

A full list of Wiris Pro specifications can be found on [Workswell’s website](https://workswell.eu/thermal-drone-camera-inspection-wiris-pro/).
