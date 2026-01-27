# Gremsy Pixy PE

<figure><img src="../../.gitbook/assets/pixype (2).png" alt=""><figcaption></figcaption></figure>

The Gremsy Pixy PE is compatible with the Pixhawk Payload Bus standard and can be integrated with Astro to fly custom payloads. The dovetail mount of the Pixy PE fits into the dovetail mount on Astro and can communicate via Mavlink.&#x20;

## Tips for Integration:

Gremsy gimbal setup documentation is linked [here](https://docs.gremsy.com/pixy-and-mio/pixy-u).&#x20;

*   Astro's stock landing gear is a bit too short for the height of the gimbal, to extend the gear we recommend using standoffs between the aircraft chassis and the landing gear plastic mount. Note that one fastener on each landing gear is longer than the other two. The setup we have used is: &#x20;

    * QTY 8 [M3x50 SHCS](https://www.mcmaster.com/screws/system-of-measurement~metric/thread-size~m3/head-type~socket/length~50mm/)
    * QTY 4 [M3x55 SHCS](https://www.mcmaster.com/screws/system-of-measurement~metric/thread-size~m3/head-type~socket/length~55mm/)
    * QTY 12 [M3 40mm standoff](https://www.mcmaster.com/94669A123/)
    * Blue loctite

    Each leg needs 3 of the 40mm standoffs, 2 of the 50mm bolts and 1 of the 55mm bolts. The bolts mount to the same holes as the existing landing gear. We haven't extensively tested this configuration, so be gentle on landings to avoid torquing the threaded mounts inside the lower chassis plate.&#x20;

## Tips to Setup Mavlink Control:&#x20;

{% hint style="info" %}
Make sure to use the Freefly cable and Smart Dovetail mount. We have confirmed that mavlink control currently doesn't work with the Gremsy cable and dovetail mount.
{% endhint %}

On the latest Gremsy gimbal software (version v7.7.3), set the gimbal to Mavlink mode, make sure the baud rate of the gimbal is 230400, and confirm that it saves.&#x20;

Recommended Gremsy software settings:&#x20;

* Baud Rate: 230400
* Stiffness: Gyro filter to 1 or 2
* Follow Controls > Pan > Airborne on
* Settings > Mode Settings > Turn Reduce drift by drone > Pan Axis to the far right

The behavior of the gimbal pan changes when the aircraft is armed or disarmed, so if you need to change something be aware that you will likely need to fly the aircraft/gimbal to see how the change affects behavior.&#x20;

{% hint style="warning" %}
We have had issues where the gimbal sometimes incorrectly reports a successful change of baud rate, so reboot the gimbal and check the settings to make sure it was changed correctly.&#x20;
{% endhint %}

This will allow tilt control by using the wheel on the Herelink after rebooting the gimbal.

{% hint style="info" %}
If tilt control is not working, check that the SER\_EXT2\_BAUD parameter is set correctly to 230400 baud rate. This can be found by going to [**Advanced mode** ](https://freefly.gitbook.io/astro-public/astro/pilots-operating-handbook/software/auterion-mission-control/amc-vehicle-setup/advanced-vehicle-setup#activating-advanced-mode)--> Parameters
{% endhint %}

{% hint style="warning" %}
The 'Pan Window' setting in the current Pixy firmware does not appear to be working as intended. We have reached out to Gremsy about this issue.
{% endhint %}

{% hint style="warning" %}
Astro firmwares 1.5 and earlier will use a baud rate of 912600
{% endhint %}
