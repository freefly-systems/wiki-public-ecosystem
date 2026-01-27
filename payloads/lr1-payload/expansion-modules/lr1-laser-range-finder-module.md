---
description: Add live distance readouts up to 100m away to your Astro!
---

# LR1 Laser Range Finder Module

## [Laser Range Finder](https://store.freeflysystems.com/collections/astro/products/lr1-laser-range-finder-upgrade)

#### Mounting&#x20;

<table><thead><tr><th width="71"></th><th></th><th></th></tr></thead><tbody><tr><td>1</td><td>Loosen the thumbscrews and slide the LR1 all the way back. This will make it easier to plug in the cable</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 090026 (1).png" alt="" data-size="original"></td></tr><tr><td>2</td><td>Mount the counterweight to the bottom of the LR1 using the M3 x 8 flathead screws and a 2.0mm hex driver</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 093753 (1).png" alt="" data-size="original"></td></tr><tr><td>3</td><td>Mount the Laser Range Finder Module to the side of the LR1 using the M3 x 5 button head screw. Then attach the M3 x 10 socket head screw to the top of the camera. Ensure the module is snug against the camera and do not pinch the cable.</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 094514 (3).png" alt="" data-size="original"></td></tr><tr><td>4</td><td>Plug the cable into the expansion port. You may need to temporarily unplug the LR1 cable to run the LRF cable behind it </td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 100549.png" alt="" data-size="original"></td></tr><tr><td>5</td><td>Balance the tilt axis of the gimbal by shifting the payload forward and back, then tighten the thumbscrews</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-15 100720.png" alt="" data-size="original"></td></tr></tbody></table>

{% hint style="info" %}
If you are adding multiple modules to the LR1 Payload at the same time, a combined counterweight is required, available [here](https://store.freeflysystems.com/collections/astro).&#x20;
{% endhint %}

#### Software Setup

Install the Distance Sensor App on your Astro, which can be found [here](https://suite.auterion.com/store). Version 1.0.1 is needed to work with the Laser Range Finder Module

{% hint style="warning" %}
For NDAA/Blue Astros, you will need to **enable Cloud Services** before Astro will connect to the Auterion Suite for app download



Power on Astro and connect to a PC via a USB-C cable, then open 10.41.1.1 in a web browser. Under 'Settings', turn on the 'Cloud Services' toggle and reboot the aircraft.



The Distance Sensor app will not install if Admin mode is enable. Be sure to **disable Admin Mode on 10.41.1.1 webpage** before attempting the install.
{% endhint %}

To install the app:

<table><thead><tr><th width="65"></th><th width="128"></th><th></th></tr></thead><tbody><tr><td>1</td><td><a href="https://suite.auterion.com/vehicles/activate?process=amc">Connect Astro to the Auterion Suite</a></td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-16 103846.png" alt="" data-size="original"></td></tr><tr><td>2</td><td>Click on your Astro in the Suite</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-16 102839 (1).png" alt="" data-size="original"></td></tr><tr><td>3</td><td>Under Software, install the 'Precise Distance LRF' app</td><td><img src="../../../../.gitbook/assets/Screenshot 2024-07-16 103055.png" alt="" data-size="original"></td></tr></tbody></table>

Turn on Astro with LR1 and the Laser Range Findermodule. Once connected, in AMC > Settings > Enable 'Show Distance Sensor App Data'. The distance readout should now be displayed on the Fly screen in AMC&#x20;

{% embed url="https://youtu.be/5oVe8wvDPvs" %}
How to enable Laser Range Finder readout
{% endembed %}

{% hint style="warning" %}
For NDAA/Blue versions of Astro, you will need to enable 'Mavlink USB-C Connectivity' for the LRF sensor to work.&#x20;



Power on Astro and connect to a PC via a USB-C cable, then open 10.41.1.1 in a web browser. Under 'Settings', turn on the 'Mavlink USB-C Connectivity' toggle and reboot the aircraft.
{% endhint %}

#### Features

* Live distance readout (in meters) in AMC at \~5Hz
* Range up to 100m on objects with >70% reflectivity at +/-10cm
  * Below 10m, we have found the error to be within +/-4cm
  * When mounted, the front of the Laser Range Finder Module is 44mm forward the LR1 sensor, which should be accounted for when sizing objects in frame based on the range finder data.&#x20;
* LRF value saved in LR1 image metadata (in meters)

{% hint style="info" %}
The Laser Range Finder Module does not adjust the LR1 focus settings at this time
{% endhint %}
