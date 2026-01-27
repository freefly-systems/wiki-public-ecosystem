# Safety Information and Technical Specifications

This section contains important information about safety and legal notices while using any of Flux sensor. Please read them carefully before operating any of the sensors. Contact Freefly in case of any doubts.



## Specifications

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



## Safety & Legal Notices

Flux H1 features a Hesai XT32M2X sensor that has been evaluated to be **Class 1 laser product** per **60825-1:2104 (Ed. 3)** and operates in the 905 nm band.

Flux O1 features an Ouster OS1 sensor that has been evaluated to be **Class 1 laser products** per **60825-1: 2014 (Ed. 3)** and operates in the 865nm band.

Flux L1 features a Livox Avia sensor that has been evaluated to be **Class 1 laser product** per **60825-1:2104 (Ed. 3)**&#x61;nd operates in the 905 nm band.

### Laser Radiation

<figure><img src="../../.gitbook/assets/Class 1.png" alt="" width="375"><figcaption><p>Class 1 Laser Product</p></figcaption></figure>

The XT32M2X, Ouster OS1, and Livox Avia sensors featured in Flux emit Class 1 invisible laser radiation.&#x20;

The entire window is considered to be the laser aperture. While Class 1 lasers are considered "eye safe", avoid prolonged direct viewing of the laser and do not use optical instruments to view the laser.

This product does not have a power switch. It starts operating once connected to power. During operation, the entire cover lens can be regarded as the product's laser emitting window; looking at the cover lens can be regarded as looking into the transmitting laser.

{% hint style="danger" %}
Use of controls, or adjustments, or performance of procedures other than those specified herein may result in hazardous radiation exposure.
{% endhint %}

### Hot Surfaces

<figure><img src="../../.gitbook/assets/Hot Surfaces.png" alt="" width="375"><figcaption><p>Hot Surfaces</p></figcaption></figure>

{% hint style="danger" %}
Flux can get **very hot** - use caution when handling Flux or removing it from the payload connector
{% endhint %}

When operated in an ambient temperature > 40 °C, the metallic surfaces of the sensor may be hot enough to potentially cause skin burn. Avoid skin contact with the sensor’s base, lid and the heatsink when the sensor is operated under these conditions. The sensor should not be used in an ambient temperature above 50°C. The maximum safety certified ambient operating temperature is 50°C.

### Installation and Operation

Before powering on the product, make sure the electrical interfaces are dry and clean. Do **NOT** power on Flux with wet connectors on the Smart Dovetail or GNSS modules

{% hint style="danger" %}
Do not "hotswap" (remove or insert) Flux from the Smart Dovetail connector when the aircraft is powered on. Doing so may damage the aircraft and/or Flux
{% endhint %}

### LiDAR Cover Lens

Do not touch the plastic or glass covering over the LiDAR sensor. Fingerprints or other contaminates such as grease or dirt can cause issues with the point cloud collection on Flux. The LiDAR cover can be gently wiped down as needed with the included microfiber cloth. Avoid scratching the glass or plastic lens covering.&#x20;

### Operating Temperatures

Freefly Flux is designed to operating in temperatures between -20 °C to 40 °C. When operated in an ambient temperature > 40 °C, the metallic surfaces of the sensor may be hot enough to potentially cause skin burn. Avoid skin contact with the sensor’s base, lid and the heatsink when the sensor is operated under these conditions. The sensor should not be used in an ambient temperature above 40°C. The maximum safety certified ambient operating temperature is 40°C.

When the sensor reaches the maximum operating temperature specified below, the sensor may become inactive and shut off.

### Recommended Storage Conditions

Store the product in a dry, well-ventilated place. The recommended ambient temperature is 23±5°C, and the humidity between 30% and 70%.&#x20;
