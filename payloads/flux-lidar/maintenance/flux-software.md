# Flux Software

## Latest Versions

| Item                        | Latest Version | How to Update                                                                                                                                     |
| --------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Flux Firmware               | v1.4.1         | [Download](#flux-firmware-release-notes) the file and [update from the USB drive](#updating-flux-firmware)                                        |
| Flux Mobile App (Pilot Pro) | v0.5.3         | Check the ["updates"](../../../controller/pilot-pro/maintenance/software-and-firmware-updates/README.md#app-updates) section in the Freefly Updater |
| Freefly Flow (iPad)         | App Store      | [App Store](https://apps.apple.com/us/app/freefly-flow/id1522046404?platform=ipad)                                                                |
| Flux Desktop App            | Beta           | [\[Beta\] Flux Desktop App](../beta-flux-desktop-app.md)                                                                                          |

{% hint style="info" %}
The Flux Mobile App requires Flux Firmware v1.4.1 or later.
{% endhint %}

## Flux Firmware Release Notes

### v1.4.1

* **New:** Support for the Flux Mobile App on Pilot Pro.
* **Fix:** Scan files are now dated from GPS time, so they no longer show up as created in 2024.
* **Improvement:** SBAS is removed from the GNSS configuration, so a mid-flight SBAS shift no longer affects processing.
* **New:** Support for Ouster firmware v3.2 (Flux O1).

<a href="https://freeflyeng.s3.us-west-2.amazonaws.com/_SoftwareReleases/flux-update-flux-te0821-rev-b-v1.4.1.0-uee2c8c31-b120-g457cad15.swu" class="button primary">DOWNLOAD v1.4.1</a>

### v1.3.1

* Improves IMU timing
* Improves production processes
* Adds build metadata

{% file src="../../../.gitbook/assets/flux-update-flux-te0821-rev-b-v1.3.1-uee2c8c31-b117-g8f809855.swu" %}

### v1.2.14

* Fixes an issue where sometimes H1 units produce 0 pt scans
* Add support for new IMU variant

{% file src="../../../.gitbook/assets/flux-update-flux-te0821-rev-b-v1.2.14-uee2c8c31-b104-g6a4bd0c9.swu" %}

### v1.1.0

* Minor update to support hardware revision

### v1.0.0

* Initial release for Freefly Flux L1, O1, and H1

## Flux Mobile App Release Notes

### v0.5.3 (September 2026)

* Initial release, listed as **Freefly Flux** in the Freefly Updater. Monitor Flux and start and stop recording from the Pilot Pro, with no iPad or ethernet cable.
* Requires Flux Firmware v1.4.1 or later.

## Checking the Flux Firmware Version

* In the **Flux Mobile App** on the Pilot Pro, the firmware version is listed under **SYSTEM** next to **FW**.
* In the **Freefly Flow** app on an iPad connected to the Pilot Pro.
* On the Flux web page (see [Troubleshooting](#troubleshooting-the-flux-web-page) below).

## Updating Flux Firmware

Flux updates its firmware from the USB drive.

1. Download the firmware file (`.swu`) from the release notes above.
2. Copy the file to the root of the Flux USB drive. This is the same exFAT drive you record scans to.
3. Insert the drive into Flux and power on the aircraft, or power-cycle it if it is already on.
4. Flux installs the update and reboots. This takes a few seconds and needs no monitoring.
5. Confirm the new version in the Flux Mobile App under **SYSTEM**.

{% hint style="info" %}
Flux only installs a firmware file that is newer than the version it is running. To install the same or an older version, use the forced update below.
{% endhint %}

### Forced Update and System Recovery

Hold the REC button on Flux while powering on the aircraft. Flux boots its factory software instead of the installed update. If a firmware file is on the USB drive, Flux installs it regardless of version and reboots.

Use this to:

* Roll back to an older firmware version.
* Reinstall the current version.
* Recover from a failed or invalid update. With no firmware file on the drive, Flux keeps running the factory software so you can copy a file to the drive and update again.

## Troubleshooting: The Flux Web Page

If the USB drive update does not take, or the Flux Mobile App does not connect, the Flux web page shows the firmware version and can install a firmware file over the link.

{% embed url="https://youtu.be/7wSAYtP65fs" %}

* Power on the aircraft with Flux attached and wait for the Pilot Pro to link.
* On the Pilot Pro tablet, open a browser and go to [192.168.144.233](http://192.168.144.233:8080/).

<figure><img src="../../../.gitbook/assets/Screenshot_20251016_085945_Chrome.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The webpage may need to be forced refreshed to see the current firmware version. This can be done by holding control + shift + R on windows or command + shift + R on mac
{% endhint %}

The Flux software version is listed at the top of the page:

<div align="right"><figure><img src="../../../.gitbook/assets/Screenshot_20251016_085945_Chrome (1).jpg" alt=""><figcaption></figcaption></figure></div>

To update from the web page:

* Provide the Flux software file
* The update will validate the file and install it
* Flux will reboot once the install is complete
* Refresh the web browser for the version to update

<figure><img src="../../../.gitbook/assets/Screenshot_20251016_085945_Chrome (2).jpg" alt=""><figcaption></figcaption></figure>
