# Technical Specs

|                                                   |                        Flux H1                        |                        Flux L1                        |                        Flux O1                        |
| ------------------------------------------------- | :---------------------------------------------------: | :---------------------------------------------------: | :---------------------------------------------------: |
| Scanner                                           |                       Hesai 32M                       |                       Livox Avia                      |                       Ouster OS1                      |
| Channels LiDAR                                    |                           32                          |                                                       |                          128                          |
| Range                                             |                         300 m                         |                         450 m                         |                         200 m                         |
| Field of View                                     |                       360° x 40°                      |                       70° x 77°                       |                      360° x 42.4°                     |
| Laser Returns                                     |                           3                           |                           3                           |                           2                           |
| Accuracy                                          |                     ±3 cm / 1.2 in                    |                      ±5 cm / 2 in                     |                     ±3 cm / 1.2 in                    |
| Precision                                         |                    0.5 cm / 0.2 in                    |                     2 cm / 0.8 in                     |                    0.5 cm / 0.2 in                    |
| Points per Second                                 |                       1,920,000                       |                        720,000                        |                       5,242,880                       |
| RGB Camera (Ximea 20mp)                           |                           ✔️                          |                           ✔️                          |                           ✔️                          |
| Internal precision IMU unit with 1°/hr gyroscopes |                           ✔️                          |                           ✔️                          |                           ✔️                          |
| GNSS (Dual Full-band Receivers L1/L2/L5/L6)       |                           ✔️                          |                           ✔️                          |                           ✔️                          |
| INS solution                                      |                        2000 Hz                        |                        2000 Hz                        |                        2000 Hz                        |
| **Storage**                                       |              USB-C drive (256gb included)             |              USB-C drive (256gb included)             |              USB-C drive (256gb included)             |
| Operating temperature range                       |                      -20C to +50C                     |                      -20C to +50C                     |                      -20C to +50C                     |
| Dimensions                                        |                      96x93x104 mm                     |                                                       |                                                       |
| Weight                                            |                         690 g                         |                         420 g                         |                         690 g                         |
| Hardware Interface                                |                 Freefly Smart Dovetail                |                 Freefly Smart Dovetail                |                 Freefly Smart Dovetail                |
| NDAA Compliant                                    |                           -                           |                           -                           |                           ✔️                          |
| Compatibility                                     | <p>Freefly Astro<br>Freefly Alta X<br>DJI Skyport</p> | <p>Freefly Astro<br>Freefly Alta X<br>DJI Skyport</p> | <p>Freefly Astro<br>Freefly Alta X<br>DJI Skyport</p> |
| Global accuracy\*                                 |                        +/-10cm                        |                        +/-10cm                        |                        +/-10cm                        |

\*This was tested using NTRIP corrections while flying the drone and for processing the Flux scan measured blind against ground control points. Actual accuracy may varry depending on a number of factors including GNSS signal quality, base station quality, and other environmental factors.&#x20;

## Operating Temperatures

Freefly Flux is designed to operating in temperatures between -20 °C to 40 °C. When operated in an ambient temperature > 40 °C, the metallic surfaces of the sensor may be hot enough to potentially cause skin burn. Avoid skin contact with the sensor’s base, lid and the heatsink when the sensor is operated under these conditions. The sensor should not be used in an ambient temperature above 40°C. The maximum safety certified ambient operating temperature is 40°C.

When the sensor reaches the maximum operating temperature specified below, the sensor may become inactive and shut off.

## Recommended Storage Conditions

Store the product in a dry, well-ventilated place. The recommended ambient temperature is 23±5°C, and the humidity between 30% and 70%.
