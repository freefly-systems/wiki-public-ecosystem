# Gimbal Firmware

## Latest gimbal firmware

|                                 | LR1 Payload   | OGI Payload   | Wiris Pro Payload | A7R4 Payload |
| ------------------------------- | ------------- | ------------- | ----------------- | ------------ |
| **Astro Firmware 1.6 or later** | v2.2.1        | v2.2.0        | v1.7.2            | v1.7.2       |
| **Astro Firmware 1.5 or older** | Not supported | Not supported | v1.6.2            | v1.6.2       |



{% hint style="info" %}
Make sure to update Astro and AMC to the latest FW too!
{% endhint %}

## How to check gimbal firmware

<figure><img src="../../../.gitbook/assets/ezgif.com-video-to-gif-converter (3).gif" alt="" width="563"><figcaption><p>Note: Payload must be connected to Astro to check version number</p></figcaption></figure>

Older gimbal software versions are displayed as Model Mongoose. You will need to download the latest gimbal firmware that matches your payload type (Wiris Pro, LR1, A7R4, etc.) even if it is below version 2.0.0

<figure><img src="../../../.gitbook/assets/image (171).png" alt="" width="563"><figcaption></figcaption></figure>

Gimbal firmware versions are also included in gimbal log files

{% content-ref url="gimbal-logs.md" %}
[gimbal-logs.md](gimbal-logs.md)
{% endcontent-ref %}

## Gimbal firmware release notes

### v2.2.1

* Maintenance release to support new accelerometer calibration

{% file src="../../../.gitbook/assets/minigimbal_lr1_v2.2.1.zip" %}

### v2.2.0

* Change: Increased upward tilt limit from +30 degrees --> +90 degrees
* New: Added support for Skyview/Top mount
* New: Added support for Sony FE 50mm F2.5 G lens

{% hint style="info" %}
Support for Sony FE 50mm F2.5 G lens requires Astro Firmware 2.0.22 or later as well
{% endhint %}

{% file src="../../../.gitbook/assets/minigimbal_lr1_v2.2.0.zip" %}

{% file src="../../../.gitbook/assets/minigimbal_ogi_v2.2.0.zip" %}

### v2.1.0

* Initial Release for OGI Payload
* Updated 75mm tuning for LR1 on Astro with large motors

{% file src="../../../.gitbook/assets/minigimbal_lr1_v2.1.0 (1).zip" %}

{% file src="../../../.gitbook/assets/minigimbal_ogi_v2.1.0 (1).zip" %}

### v2.0.2

* Initial release for LR1 Payload

{% file src="../../../.gitbook/assets/minigimbal_lr1_v2.0.2.zip" %}

### v1.7.2 <a href="#v1.7.2" id="v1.7.2"></a>

{% file src="../../../.gitbook/assets/minigimbal_a7r4_v1.7.2.zip" %}

{% file src="../../../.gitbook/assets/minigimbal_wiris_pro_v1.7.2.zip" %}

* Change: baud rate to enable reliable parameter forwarding
* Bugfix: now handles mavlink forwarding turned on

This is a required firmware update for Astro's running firmware 1.6 or later. This gimbal firmware will only work on Astro FW 1.6 and later

### v1.6.2 <a href="#v1.6.2" id="v1.6.2"></a>

{% file src="../../../.gitbook/assets/minigimbal_a7r4_v1.6.2.zip" %}

{% file src="../../../.gitbook/assets/minigimbal_wiris_pro_v1.6.2.zip" %}

* **Bugfix: Fixed the SD card corruption issue, preventing the gimbal from powering on**
* New: Added tilt limits to mongoose of -90 and +30 degrees tilt
* Improvements:
  * Improved heading control
  * Calibration and process updates to improve attitude performance
  * Added GPS date time as supplied by Astro to log

### v1.0.1 <a href="#v1.0.1" id="v1.0.1"></a>

* Initial Release

## Updating Gimbal Software

1. Download the firmware package.
   * Extract the .zip folder contents.
   * Open the extracted folder- the top level folder that you will need to copy onto the gimbal will be called "freefly". Do not copy the folder that states the firmware version.<br>
2. To upgrade Gimbal firmware, connect the gimbal to a laptop using a USB-C cable.&#x20;
   * The USB-C connector is located on the Smart Dovetail of the gimbal
   * Ensure the gimbal is not powered by the aircraft
   * The gimbal will show up on the computer as an external drive called "FREEFLY"

<figure><img src="../../../.gitbook/assets/Mouse Highlight Overlay 2023-01-19 15.29.53.png" alt=""><figcaption></figcaption></figure>

3. Open that drive and you will see a folder named "freefly". This is the current firmware file that you need to replace.&#x20;
   * Delete this folder and replace it with the new firmware folder "freefly' that you downloaded in Step 1

<figure><img src="../../../.gitbook/assets/Mouse Highlight Overlay 2023-01-19 15.32.51.png" alt=""><figcaption></figcaption></figure>

4. Remove the USB-C cable from the gimbal and connect the gimbal to an Astro using the Smart Dovetail to power on the gimbal.&#x20;
5. Insert 1 SL8 Battery into the aircraft and fully latch the battery, but **do not** power on the aircraft at this time.
6. Use a paperclip or small screwdriver to hold down the Firmware Load button on the gimbal- this button must be pressed and held for 10 seconds while powering on the aircraft.
   * This small button is recessed into the gimbal housing and is located next to the USB-C connector on the Smart Dovetail.
7. Power on the aircraft by double clicking the button on the SL8 battery.&#x20;
   * Ensure that the Firmware Load button is held down during this time for 10 seconds while the new firmware is loaded onto the gimbal.
8. When firmware is successfully updated, the gimbal should stabilize correctly and video feed will show on the controller.

## Camera Software

We have tested LR1 cameras on 1.00 FW. We do not recommend any updates to the camera as it may cause compatibility issues with Astro and AMC.&#x20;

## Gimbal Logs

With Astro off or with the gimbal removed from the aircraft, connect a USB-C cable between a computer and the USB-C port on the payload side of the dovetail. A drive will mount on your computer. The logs are located under "freefly\movi\logs".

## Gimbal Baud Rate

If you're experiencing a limp gimbal upon powering on or during flight, this could be caused by a baud rate mismatch between your gimbal and Astro system. To resolve the issue, ensure that both your gimbal and Astro are running compatible firmware versions.

**Firmware Changes:** Starting with Astro firmware version 1.6, the baud rate for communication between the Astro system and the gimbal was updated. In Astro firmware 1.5 and earlier, the baud rate was set to **921600 8N1**. However, with the release of firmware 1.6, the baud rate was increased to **230400 8N1**. This should update automatically by applying firmware 1.6 or later

**How to Check Gimbal Baud Rate:** To verify your gimbal's baud rate, [access the advanced parameters](https://freefly.gitbook.io/astro-public/pilots-operating-handbook/essential-software/auterion-mission-control/amc-vehicle-setup/parameters#accessing-advanced-parameters) in your system and locate the **SER\_EXT2\_BAUD** parameter. This will indicate the current baud rate setting on your gimbal.

By ensuring that both your gimbal and Astro firmware are using compatible baud rates, you can prevent any communication issues and maintain proper gimbal functionality.
