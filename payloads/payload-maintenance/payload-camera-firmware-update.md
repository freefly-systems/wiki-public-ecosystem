# Payload Camera Firmware Update

## LR1 Payload

LR1 cameras have shipped on versions 1.0, 2.0, and 3.0.

{% hint style="info" %}
To use APS-C mode, [update your LR1 camera to firmware v3.0 or later.](https://www.sony.com/electronics/support/camcorders-and-video-cameras-interchangeable-lens-camcorders/ilx-lr1/downloads) LR1 cameras on firmware v1.0.0 do not reliably accept the APS-C command. Early-batch LR1s (unit shipped before October 2024) are most likely to be on v1.0.0. APS-C mode is available on [Astro firmware 2.2](https://docs.freeflysystems.com/astro/maintenance/software-release-notes/astro-software-v2.2-whats-new)
{% endhint %}

To update your camera:

| Step                                                                                                          | Image                                                                        | Notes                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Download the firmware file from Sony and put it on to an _**empty**_ SD card. Insert the SD card into the LR1 |                                                                              | [Sony LR1 Firmware](https://www.sony.com/electronics/support/camcorders-and-video-cameras-interchangeable-lens-camcorders/ilx-lr1/downloads)     |
| Remove the two screws on the back cover of the LR1 camera                                                     | <img src="../../.gitbook/assets/image (18).png" alt="" data-size="original"> |                                                                                                                                                  |
| Unplug the upper section of the GH cable on the payload. Remove any accessory module cables                   | <img src="../../.gitbook/assets/image (21).png" alt="" data-size="original"> | This will prevent the aircraft from interfering with the camera during the update                                                                |
| Gently remove the circuit board from the back of the camera, but keep the cables plugged in                   | <img src="../../.gitbook/assets/image (22).png" alt="" data-size="original"> |                                                                                                                                                  |
| Connect an HDMI cable and monitor to the camera                                                               | <img src="../../.gitbook/assets/image (23).png" alt="" data-size="original"> | We recommend [this cable](https://store.freeflysystems.com/products/lightweight-right-angle-micro-to-standard-cable?_pos=7&_sid=10d9896d4&_ss=r) |
| Install the LR1 payload on the aircraft and power it on                                                       |                                                                              |                                                                                                                                                  |
| Using the buttons on the camera, press Menu and navigate to the Setup -> Setup Option -> Version page         | <img src="../../.gitbook/assets/image (24).png" alt="" data-size="original"> |                                                                                                                                                  |
| Follow the prompts to update the firmware                                                                     | <img src="../../.gitbook/assets/image (25).png" alt="" data-size="original"> |                                                                                                                                                  |
| Reinstall the circuit board, cables, and cover                                                                |                                                                              |                                                                                                                                                  |

## A7R4 Payload

We do not recommend updating the firmware on the A7R4. Most cameras were shipped with v1.10&#x20;

## Wiris Pro Payload

{% content-ref url="../wiris-pro-thermal/camera-software.md" %}
[camera-software.md](../wiris-pro-thermal/camera-software.md)
{% endcontent-ref %}

## Ventus OGI Payload

We do not recommend updating the firmware on the Ventus OGI Payload.
