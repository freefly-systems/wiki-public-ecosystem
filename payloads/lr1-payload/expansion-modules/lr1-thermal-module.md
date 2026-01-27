---
description: Add LWIR thermal imaging to your LR1 payload on Astro!
---

# LR1 Thermal Module

<figure><img src="../../../../.gitbook/assets/bosonExample1.png" alt=""><figcaption></figcaption></figure>

## [Thermal Module](https://store.freeflysystems.com/products/lr1-thermal-upgrade)

#### Mounting

<table><thead><tr><th width="95"></th><th width="311"></th><th></th></tr></thead><tbody><tr><td>1</td><td>Loosen the thumbscrews and slide the LR1 all the way back. This will make it easier to plug in the cable</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090026.png" alt="" data-size="original"></td></tr><tr><td>2</td><td>Mount the counterweight to the bottom of the LR1 using the M3 x 5 FHCS screws and a 2.0mm hex driver</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090128 (1).png" alt="" data-size="original"></td></tr><tr><td>3</td><td>Mount the Thermal Module to the top of the LR1 using the M3 x 10 SHCS screws and a 2.5mm hex driver. Ensure the module is snug against the camera. Do not pinch the cable.</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090302.png" alt="" data-size="original"></td></tr><tr><td>4</td><td>Plug the cable into the expansion port. Gently push the cable into the cable guide hook.</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090440 (1).png" alt="" data-size="original"></td></tr><tr><td>5</td><td>Balance the tilt axis of the gimbal by shifting the payload forward and back, then tighten the thumbscrews.  Torque the screws up to 0.3Nm to prevent the adjustment from slipping.</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090832.png" alt="" data-size="original"></td></tr></tbody></table>

{% hint style="info" %}
If you are adding multiple modules to the LR1 Payload at the same time, a combined counterweight is required, which is included with the thermal module.
{% endhint %}

#### Software

{% hint style="success" %}
Ensure your Astro and controller are [up to date](https://freefly.gitbook.io/astro-public/maintenance/software-release-notes)! The Thermal Module is compatible with Astro firmware 1.7 and later&#x20;
{% endhint %}

Switching between cameras views can be done by tapping the camera name, or by mapping 'Next Camera' to a button on the controller

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-07-16 102001.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-07-16 102051.png" alt=""><figcaption><p>How to map Pilot Pro buttons to change camera views</p></figcaption></figure>

#### Features

* Contrast - Auto, Custom
* Color pallet selection - White hot, Black hot, Ironbow, Rainbow, Rainbow HC, Lava, Arctic, Glowbow, Graded Fire, Hottest&#x20;
* Zoom - digital up to 8x
* Image capture - Jpeg, Radiometric Tiff, both
* Spot temperature readout&#x20;
  * Mix/max temperatures of region
  * Adjustable region size
  * Selectable Fahrenheit, Celsius, Kelvin&#x20;
* Togglable settings - Radiometric settings, Spot Metering, Isotherms
* Auto and manual Flat-Field-Correction (FFC)
* Geotagged photos

{% hint style="info" %}
Currently, thermal mapping with the Thermal Module is not supported
{% endhint %}

### Camera Options in AMC

<figure><img src="../../../../.gitbook/assets/1 (1).jpg" alt=""><figcaption><p>Basic settings for Boson camera 1 of 2</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/2.jpg" alt=""><figcaption><p>Basic Settings for Boson camera 2 of 2</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/3 (2).jpg" alt=""><figcaption><p>Settings with isotherms enabled</p></figcaption></figure>

### Example Data:

{% file src="../../../../.gitbook/assets/LR1 Thermal Module - Example Images.zip" %}
JPEGs and TIFFs from Thermal Module and some LR1 + 75mm images
{% endfile %}

<figure><img src="../../../../.gitbook/assets/240723_191309_745 (1).jpg" alt=""><figcaption></figcaption></figure>



{% embed url="https://youtu.be/ycyOmL6Vf_M" %}

### Variants

We have shipped three variants of the thermal module. The field of view of the lenses are all the same. The image quality/sensor performance are the same between the Boson 13.6mm and Boson 14mm. The Boson+ 13.6 has increased sensitivity and overall better image quality . The mass is different between the 13.6mm and 14mm lens variants, which means a matching counterweight should be used to ensure good gimbal balance and stabilization.&#x20;

<figure><img src="../../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

