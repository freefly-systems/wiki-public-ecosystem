# Software Release Notes

## Current Versions

<details>

<summary>Pilot Pro Software Bundle v2.7.4</summary>

* **Summary:** New RTK/NTRIP feature in Pilot Pro App
* **Release Date**: April 2026
* **Versions in this package**:
  * Pilot Pro Firmware: v2.2.0
  * Pilot Pro App: v2.7.4

**Notes**

* **New:** RTK and NTRIP can now be run from Pilot Pro on MAVLink-over-ethernet vehicles.
* **New:** Customizable Pilot Pro Status page for integrators.
* **New:** Pilot Pro now always verifies all input-output parameters to ensure the applied config matches controller state.
* **Improvement:** Android battery optimization configured so critical Freefly apps are not killed when backgrounded.
* **Improvement:** Graceful tablet shutdown so Android settings persist across boot.
* **Improvement:** Software update UX.
* **Improvement:** Better vehicle and serial connection state management.
* **Fix:** Log pruning is now capped at 3 GB.
* **Fix (Freefly Updater):** Auto-fetch on app start now works reliably.
* **New (Freefly Updater):** Pop-up warning when there is no internet connectivity.

</details>

## Previous Versions

<details>

<summary>Pilot Pro Software Bundle v2.6.2</summary>

* **Summary:** Doodle Channel Scaning Update
* **Release Date**: March 2026
* **Versions in this package**:
  * Pilot Pro Firmware: v2.2.0
  * Pilot Pro App: v2.6.2

**Notes**

* New channel scan for Doodle radios — scans all channels and scores each one based on airtime activity.
* Added pre-scan warnings for air unit connection and 2.4 GHz WiFi interference
* Improved Doodle radio settings UI

</details>

<details>

<summary>Pilot Pro Software Bundle v2.3.8</summary>

* **Summary:** Update Power Sequence for New Tablet
* **Release Date**: November 2025
* **Versions in this package**:
  * Pilot Pro Firmware: v2.2.0
  * Pilot Pro App: v2.3.8

**Notes**

* Power on/off behavior fix for newer tablets

</details>

<details>

<summary>Pilot Pro Software Bundle v2.3.7</summary>

* **Summary:** UI/UX hotfix for v2.3.4
* **Release Date**: September 2025
* **Versions in this package**:
  * Pilot Pro Firmware: v2.2.0
  * Pilot Pro App: v2.3.7

**Notes**

* Fixed Doodle Channel scan UI bug
* Fixed regression to hide certain features when drone is armed
* Fix navigation drawer sometimes not displaying all menu items
* Removed irrelevant warnings for Alta X users to switch GCS

</details>

<details>

<summary>Pilot Pro Software Bundle v2.3.4</summary>

* **Summary**: Support for [Astro Software v2.1](https://freeflysystems.com/astroversions)
* **Release Date**: September 2025
* **Versions in this package**:
  * Pilot Pro Firmware: v2.2.0
  * Pilot Pro App: v2.3.4

**Notes**

* New: Aircraft Settings page to configure Astro Max for high-altitude flights.
* New: Added RC\_CHANNELS message support in MAVLink mode (enables use cases such as flying the Hovermap payload with Astro Blue). [Link to instructions](../../../../payloads/third-party-payloads/hovermap-st-x-and-st-lidar/hovermap-setup-on-astro.md#hovermap-configuration-with-pilot-pro-doodle-radio).
* Fixed: HID devices not working in Host Swap mode.
* Fixed: Pilot Pro not entering bootloader mode for firmware updates.
* Fixed: Doodle Labs radio toggles no longer show an incorrect state before data is fetched.

</details>

<details>

<summary>Pilot Pro Software Bundle v2.1.3</summary>

* **Summary**: Support for [Astro Software v2.0](https://freeflysystems.com/astroversions)
* **Release Date**: May 2025
* **Versions in this package**:
  * Pilot Pro Firmware: v2.1.1
  * Pilot Pro App: v2.1.3

**Required User Actions**

* Update Pilot Pro firmware to v2.1.1.
  * Note: Turn off drone before initiating firmware update because Pilot Pro may prevent you from doing a firmware update while it has a live connection to a drone.

**New Features**

* Support for Astro Software v2.0
* Added drone status info and ability to launch AMC for Astro users.
* Support ability to add Pilot Pro as an asset on Auterion Suite.
* Enabled native screen mirroring from the tablet to an external display. (since v2.0.24)
* Support new Doodle FW v1.7 and hardware revisions.
* Improve pairing process and channel scanning UX for Doodle integration.

\
**Improvements**

* Apply optimal tablet display refresh rate for AMC video

</details>

<details>

<summary>Pilot Pro Software Bundle v2.0.24</summary>

* **Summary**: Pilot Pro Screen Mirroring
* **Release Date**: February 2025
* **Versions in this package**:
  * Pilot Pro Firmware: v2.0.27
  * Pilot Pro App: v2.0.24

**Notes**

* Pilot Pro App
  * Unlocked ability to do tablet screen mirroring

</details>

<details>

<summary>Pilot Pro Software Bundle v2.0.23 (All Pilot Pros)</summary>

* **Summary**: Pilot Pro Solo Capabilities (Input Output Mapping), Unification of Software for Pilot Pro Tab Active5 and Tab Active3
* **Release Date**: November 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v2.0.27
  * Pilot Pro App: v2.0.23

**Notes**

* Pilot Pro App
  * Ability to apply manufacturer and custom input/output mapping preset.
  * Power ON/OFF Pilot Pro with the main power button on the controller instead of tablet.
  * Pilot Pro Tab Active5 and Pilot Pro Tab Active3 hardware variants can be put back on the same Pilot Pro App and firmware version with this update
  * New version of app opened comes with a release note that user has to acknowledge
  * Input calibration mode.
  * Better radio management messaging.
  * Improved software version / module tracking.
  * App logging bugfixes.
  * Risky features are disabled when drone is armed
* Pilot Pro Firmware
  * Ability to remap any input or output using MAVLink parameters
  * Ability to apply expo, smoothing and window to any analog input
  * Ability to choose the MAVLink system ID and component ID of the vehicle
  * TLog logging
  * Ardupilot mode parsing
  * Improved power on UX

</details>

<details>

<summary>Pilot Pro Software Bundle v1.4.8 (Pilot Pro Tab Active5) / v1.2.40 (Pilot Pro Tab Active3)</summary>

* **Summary**: Pilot Pro Doodle Configuration Hotfix release
* **Release Date**: October 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v1.4.5 / v1.2.2
  * Pilot Pro App: v1.4.8 / v1.2.40

**Notes**

* Fixed a configuration bug that caused some settings to not be set correctly. Users were requested to go through the pairing process again.

</details>

<details>

<summary>Pilot Pro Software Bundle v1.4.6 (Pilot Pro Tab Active5)</summary>

* **Summary**: Support for Pilot Pro RFD radio
* **Release Date**: September 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v1.4.5
  * Pilot Pro App: v1.4.6

**Notes**

* The primary change for this release was to support Pilot Pro RFD900 variant

</details>

<details>

<summary>Pilot Pro Software Bundle v1.3</summary>

* **Summary**: Support for Pilot Pros that have Samsung Active5
* **Release Date**: July 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v1.3.1
  * Pilot Pro App: v1.3.2

**Notes**

* Support for Active5 tablet. Samsung has end of lifed the Active3 tablet. New Pilot Pros are manufactured with the Active5 tablet starting late July 2024
* Power On/Off behavior has changed: Entire system (Pilot Pro + Tablet) should now be powered on / off from the Pilot Pro power button. (This is only valid for Active5 variant right now, but it will also come to the Active3 variant in future release.)
* New Freefly Updater UI with backend changes for improved app update/install experience
* Improved messaging in the Pilot Pro app for radio channel changes

</details>

<details>

<summary>Pilot Pro Software Bundle v1.2</summary>

* **Summary**: Support for Astro (Blue/NDAA) with the Doodle radio module
* **Release Date**: July 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v1.2.2
  * Pilot Pro App: v1.2.13

**Notes**

* App: New Radio settings screen for Doodle radio management. It includes
  * Status display
  * Channel selection
  * Pairing manager
  * Firmware updates
  * Advanced settings
* Firmware:
  * Mavlink based control support for Doodle radio
  * Map S1 to SBUS channel 15
  * Feature to only start radio comms if the App has granted permission
  * Blue security improvements

</details>

<details>

<summary>Pilot Pro Software Bundle v1.1</summary>

* **Summary**: Pilot Pro Bugfixes and Improvements
* **Release Date**: May 2024
* **Versions in this package**:
  * Pilot Pro Firmware: v1.1.11
  * Pilot Pro App: v1.1.4

**Notes**

* Fixed a bug where letting the Pilot Pro get to low power could make the unit inoperable. This was due to under voltage battery state sometimes causing a radio fault that doesn’t clear when power cycled.
* Rockers and joysticks can now be configured to have various levels of smoothing applied
* Added a self check feature that automatically checks user inputs during boot
* More:
  * New Host Swap mode for easier development. Read more about it [here](../../interfaces/software-interfaces.md#debugging)
  * Added a warning for when a low power USB C charger is used
  * Added a warning for when too much power is being drawn from the controller
  * Added separate warnings for when radio is not programmed, corrupted or disconnected
  * Made the battery undervoltage warning more urgent
  * Added Battery cycle counting
  * Adjustable radio UART and SBUS UART baud rates
  * Improved state of charge estimation
  * Improved SD card logging reliability
  * Increased the amount of information logged
  * Fixed bug which allowed over-voltage external batteries to briefly charge the controller

</details>

<details>

<summary>Pilot Pro Software Bundle v1.0 Bugfix</summary>

* **Summary**: Pilot Pro Bugfixes and Improvements
* **Release Date**: October 2023
* **Versions in this package**:
  * Pilot Pro Firmware: v1.0.7
  * Pilot Pro App: v1.0.10

**Notes**

Pilot Pro Firmware v1.0.7

* New Features:
  * Added audible low battery and undervoltage warnings
  * Introduced a dedicated warning screen
  * Added support for new PCBA hardware version (rev D)
* Improvements:
  * Renamed "NO CONN." to "NO LINK" for better clarity
  * Enhanced battery state of charge calculation.
  * Added logging for MAVLink states, app commands and radio status
  * Power off and reboot is now quicker
* Fixes:
  * Fixed issue where the controller failed to parse shutdown commands from the App
  * Resolved problem with external battery charging in low power charge mode
  * Multiple bug fixes for power management

Pilot Pro App v1.0.10

* Added Pilot Pro logging! It includes:
  * Toggle to enable or disable Pilot Pro logging on the tablet
  * Easily access logs to share with Freefly Customer Support
  * Automatically prunes the oldest logs to keep total Pilot Pro logs to less than 3GB
  * Here is [how you can share logs](../troubleshooting.md#how-to-share-logs-with-freefly)
* Improved notification for when Pilot Pro firmware update is available
* Updated available Pilot Pro firmware version to v1.0.7

</details>

<details>

<summary>Pilot Pro Software Bundle v1.0</summary>

* **Summary**: Initial Pilot Pro release
* **Release Date**: September 2023
* **Versions in this package**:
  * Pilot Pro Firmware: v0.17
  * Pilot Pro App: v1.0.0

</details>
