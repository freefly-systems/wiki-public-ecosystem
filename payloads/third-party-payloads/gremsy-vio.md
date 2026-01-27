# Gremsy Vio

<figure><img src="../../.gitbook/assets/thumbnail_image001.jpg" alt=""><figcaption></figcaption></figure>

The Gremsy VIO with the Smart Dovetail adaptor is compatible with the Pixhawk Payload Bus standard and can be integrated to work on Astro.

## Gremsy VIO Configuration

Please refer to the [Gremsy VIO wiki](https://docs.gremsy.com/payloads/vio) on how to configure the following settings:&#x20;

* [Set the static IP](https://docs.gremsy.com/payloads/vio/hardware-configuration/computers-ip-configuration)
  * VIO Address = 192.168.144.232
  * Netmask = 255.255.255.0
  * Gateway = 192.168.144.20
* [Update the VIO firmware](https://docs.gremsy.com/payloads/general/upgrade-firmware-and-software)

{% hint style="success" %}
Download the [VIO software package 3.1.07](https://drive.google.com/file/d/1vcwQ5kw-nArm4zr_C6ryonUsaV42gMmh/view?usp=sharing)
{% endhint %}

{% hint style="info" %}
The latest supported version with Astro is:&#x20;

* Vio Payload App v3.1.0.7
* Video Streaming App v3.2.1
* Vio Setting App v2.3.1
* Gimbal Firmware v7.8.6
{% endhint %}

## Astro Configuration

{% hint style="success" %}
Astro and AMC need to updated to the latest version, at least Astro software version 2.0 or later
{% endhint %}

The following parameters need to be configured for Astro to communicate with the VIO. Click [here](https://freefly.gitbook.io/astro-public/pilots-operating-handbook/essential-software/auterion-mission-control/amc-vehicle-setup/parameters) to learn to set parameters on Astro.&#x20;

* #### MNT\_RATE\_YAW = 0
  * You will need to check 'force save'
* #### MAV\_2\_MODE = Normal
  * This will allow GPS information to be passed to the VIO, both for the LRF and for geotagging .JPEG images. TIFF images are not geotagged
    * If your aircraft needs to maintain Blue List compliance, do not change MAV\_2\_MODE. The VIO will not receive GPS information
* Reboot Astro

{% hint style="info" %}
If switching back to other Smart Dovetail payloads like the LR1 Payload or Sentera 6X, perform a [parameter reset](https://freefly.gitbook.io/astro-public/pilots-operating-handbook/essential-software/auterion-mission-control/amc-vehicle-setup/parameters#resetting-parameters-to-factory-defaults) on Astro.
{% endhint %}

## Connect to Astro

Plug VIO into the Smart Dovetail on Astro and boot up the aircraft. VIO should stabilize after about 15s and the light on the front of the gimbal will turn blue if connected to Astro.&#x20;

Wait another 30-60s for the VIO video feed to appear in AMC

### Camera Settings

Once connected to the VIO through AMC, the following settings need to be applied in the VIO camera settings menu:

* RC mode = Standard
* Setting target = Gimbal Device
  * Then set Gimbal Mode = FOLLOW

### VIO Webpage Settings

On Pilot Pro, open a web browser like Chrome, and go to 192.168.144.232:8000. This will load a webpage hosted by the VIO payload. Under the Systems menu, we recommend loading the following default parameters for Astro:

{% file src="../../.gitbook/assets/payload_config_for_astro.vio" %}

If this doesn't work, you can manually set the following parameters:&#x20;

* Video Streaming
  * Auto connect = Enable
  * Bitrate = 2 Mbps
  * Port = 8554
  * Resolution = 1280x720
  * Codec: H.264
* Gimbal Control
  * Auto speed = DISABLE
* Mavlink
  * Baudrate = 230400
  * Camera Component ID = Camera 1 (100)&#x20;

Then reboot Astro and the VIO. This process should only need to be applied once.&#x20;

## Operational Notes

{% hint style="info" %}
Gremsy VIO is a 3rd party payload with some known limitations/issues:&#x20;

* When running AMC on Tab 3 tablets with the VIO, the video feed can be choppy with default settings. It is recommended to set the RTSP Buffer Size (ms) = 250 to smooth out the video playback. **Tab 5 tablets do not have this issue**
  * Tab 5 tablets have a green button on the side, Tab 3 tablets have a red button on the side
  * RSTP Buffer size can be set while in Advanced Mode under Camera > Settings
* Photo counter below the shutter button doesn't increment, but photos are triggered
* Triggering the VIO in mapping mode is currently not supported
{% endhint %}



