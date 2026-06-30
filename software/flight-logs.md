---
description: This guide covers all log types across the Freefly ecosystem.
hidden: true
---

# Flight Logs

### Downloading Flight Logs from the Aircraft

This is the most common request from Freefly Support and the most reliable way to get flight data. The aircraft stores flight logs as `.ulg` (ULog) files on the onboard SD card.

#### What You Need

* Your aircraft (Astro or Alta X Gen2)
* **One battery only** (using a single battery prevents the risk of accidentally arming the aircraft)
  * Astro / Astro Max: 1× SL8 battery
  * Alta X Gen2: 1× battery with the fused cable
* USB-C cable
* A PC with **AMC PC** (Auterion Mission Control) installed
  * You can download the latest AMC for desktop (Mac, Windows, Linux) from our software donwloads page [here](https://freeflysystems.com/support/astro-support).&#x20;

#### Step-by-Step: Download Logs via USB

1. **Connect the USB-C cable** from your PC to the aircraft's USB-C port.
   * Astro / Astro Max: The IO panel is on the **underside** of the aircraft. Otherwise, if you have the optional FPV cam using this port, you can use the passthrough USB port on the FPV camera housing. \
     ![](<../.gitbook/assets/image (29).png>)
   * Alta X Gen2: The USB-C port is located near the battery connectors.\
     ![](<../.gitbook/assets/image (28).png>)
2. **Install one battery** and power on the aircraft. Wait about 15 seconds for the aircraft to fully boot.
3. **Open AMC** on your computer (not the Pilot Pro)&#x20;
4. **Activate Advanced Mode**: Click the AMC icon in the top-left corner of the app approximately 6 times. A popup will ask if you want to switch to Advanced Mode. Confirm.
5. **Navigate to Analyze → Log Download**.
6. **Click "Refresh"** to load the list of available logs.
7. **Select the log files** you need and click **"Download"**.

{% file src="../.gitbook/assets/How To Download Logs AMC.mov" %}
A short video example of the log download process in AMC&#x20;
{% endfile %}

{% hint style="info" %}
**USB is strongly recommended.** While it is technically possible to download logs over WiFi, it is significantly slower and less reliable. Always prefer USB.
{% endhint %}

{% hint style="info" %}
If storage fills up, **the oldest logs are automatically deleted** to make room for new ones. Periodically back up and clear logs if you want to retain them, or use flight log management software.
{% endhint %}

#### Troubleshooting Connection Issues

If AMC won't connect to the aircraft over USB:

1. Verify the USB connection by browsing to [http://10.41.1.1](http://10.41.1.1/) in a web browser.
2. Try a different USB-C cable — some cables are charge-only and don't support data.
3. Reboot the aircraft and restart AMC

***

### Understanding the Different Log Types

Freefly aircraft and accessories generate several different types of logs. Each captures different information and is accessed differently. Here's how they compare:

#### 1. Flight Logs from the Aircraft (`.ulg` files)

These are the primary flight logs stored directly on the aircraft's onboard SD card. They are **ULog** format files used by PX4-based autopilots.

| Detail             | Description                                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------------------- |
| **Format**         | `.ulg` (ULog)                                                                                                 |
| **Location**       | In AMC under Analyze > Log Download                                                                           |
| **Logging window** | From **boot** to **power down.**                                                                              |
| **Contents**       | Flight path, attitude, GPS, sensor data, inputs/outputs, vibration, errors, parameter values, etc.            |
| **How to access**  | Via USB is strongly recommended, however, it is also possible via the radio. See instructions above.          |
| **How to analyze** | Upload to [PX4 Flight Review](https://logs.px4.io/), Auterion Suite, or use tools like PlotJuggler / `pyulog` |

{% hint style="info" %}
These are the most complete logs available and are what Freefly Support will ask for first when troubleshooting.
{% endhint %}

#### 2. Flight Logs from Auterion Suite

If your aircraft is registered with the [Auterion Suite](https://suite.auterion.com/), flight logs are automatically uploaded to the cloud when a WiFi or LTE connection is available. Sharing logs through the Suite is one of the fastest ways to get Freefly Support involved.

| Detail                        | Description                                                                                                                              |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Format**                    | `.ulg` (same ULog format, viewable in-browser)                                                                                           |
| **Location**                  | Auterion Suite cloud platform                                                                                                            |
| **Logging window**            | From **arm** to **disarm** (which can omit some important information, which is why we recommend the downloading from aircraft directly) |
| **Contents**                  | Same flight telemetry data as on-device logs                                                                                             |
| **How to access**             | Log in to Auterion Suite, navigate to the aircraft, and select a flight                                                                  |
| **How to share with Freefly** | Use the **"Share with Manufacturer"** toggle on any flight in the Suite                                                                  |

{% hint style="info" %}
**Key difference from on-device logs:** Suite logs only cover arm-to-disarm windows. They do not include any data from before arming or after disarming (boot-up diagnostics, pre-arm checks, etc.). If you're troubleshooting a problem that occurs before arming — such as GPS issues during initialization or pre-arm errors — the on-device logs may also only cover arm-to-disarm by default. However, the on-device file system can sometimes retain additional context depending on the `SDLOG_MODE` parameter setting.
{% endhint %}

#### 3. AuterionOS Diagnostic Report

The AuterionOS diagnostic report is a system-level export from the Skynode companion computer. It captures information that flight logs do not — OS-level service statuses, network state, peripheral connections, partition info, and more.

| Detail            | Description                                                                                                                                                                                   |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Format**        | `AuterionOS_report.zip` archive                                                                                                                                                               |
| **Location**      | Generated on-demand from the aircraft's web UI                                                                                                                                                |
| **Contents**      | System service status, software component status, network info, peripheral state, performance data, partition info, and other OS-level diagnostics                                            |
| **How to access** | Connect to the aircraft via USB, navigate to [http://10.41.1.1/diagnostics](http://10.41.1.1/diagnostics) and click **Download Report**.                                                      |
| **When to use**   | When Freefly Support asks for a diagnostic report — typically for issues related to connectivity, firmware updates, onboard apps, or system-level behavior that isn't captured in flight logs |

{% hint style="info" %}
This is not a flight log! It's a snapshot of the operating system state. Freefly Support may ask for this in addition to flight logs when troubleshooting issues like failed firmware updates, disk space problems, or networking/connectivity issues.
{% endhint %}

#### 4. Pilot Pro Logs

Pilot Pro has its own logging system, separate from the aircraft. These logs capture what the controller and its app are doing — useful for diagnosing controller-side issues like joystick input problems, radio behavior, app crashes, or display anomalies.

| Detail            | Description                                                                         |
| ----------------- | ----------------------------------------------------------------------------------- |
| **Format**        | `PILOT-PRO-LOG-YYYY-MM-DD.ulg`                                                      |
| **Location**      | Stored locally on the Pilot Pro tablet                                              |
| **Contents**      | MAVLink states, app commands, radio status, input events, controller-side telemetry |
| **How to access** | See procedure below                                                                 |

**How to Get Pilot Pro Logs**

1. Open the **Pilot Pro App**
2. Navigate to App Settings, and under App Logging, be sure to have this enabled.&#x20;
3. Tap **"OPEN PILOT LOGS"** to open the logs folder in the My Files app.
4. To transfer: Insert a **USB-C thumb drive** into one of the Pilot Pro USB-C data ports (right-most ports) and copy the files over. Then email them to Freefly Support from your PC.

{% hint style="info" icon="diamond-exclamation" %}
Pilot Pro manages log storage automatically. Oldest logs are deleted when space is needed. You can manually delete logs from the My Files app, but **reboot Pilot Pro afterward** to resume logging properly.
{% endhint %}

#### 5. Doodle Labs Radio Logs

The Doodle Labs radio module (used on Blue / NDAA-compliant Astro and Alta X Gen2 configurations) have their own internal logging. These logs are primarily useful for diagnosing radio-specific issues like signal loss, range problems, or pairing failures.

| Detail            | Description                                                                                                                                                                                                                                                                                                                            |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Format**        | Internal radio diagnostic data                                                                                                                                                                                                                                                                                                         |
| **Contents**      | Radio link statistics, signal strength, channel data, connection events                                                                                                                                                                                                                                                                |
| **How to access** | Doodle Labs radio logs are not directly user-accessible through the standard Freefly workflow. Freefly Support or engineering may request specific radio diagnostics. Starting in Pilot Pro App v2.6.2, detailed radio statistics (including scan diagnostics) are available under **Radio Settings → Advanced** in the Pilot Pro App. |
| **When to use**   | When Freefly Support is investigating radio range, signal quality, or connectivity issues specific to the Doodle Labs link                                                                                                                                                                                                             |

**How to get Doodle Radio logs**

1. In the Pilot Pro app, navigate to Radio Settings > Advanced
2. Ensure that Logging is enabled (disabled by default due to DIU Blue requirements).
3. If you are having an issue with the Doodle radio at the moment, you can tap on "Save Log Snapshot" to timestamp the current radio log.
4. Tap on "Open Doodle Logs" to view all the available Doodle radio logs to share with support.

{% hint style="info" %}
If you're experiencing radio range or signal issues, the most helpful thing you can do is provide Freefly Support with your **aircraft flight logs**, and **Doodle radio logs**. Details about your environment and antenna setup are also helpful. Freefly Support can coordinate with engineering if deeper radio-level diagnostics are needed.
{% endhint %}

***

### DIU Blue / NDAA Drone Considerations

Blue-variant aircraft (Astro Blue, Alta X Gen2 Blue) have several important differences in how logging works. These are security measures designed for government and defense use cases.

#### Stealth Logging (Default on Blue Drones)

Blue aircraft ship with **stealth logging enabled** by default. When stealth logging is active (parameter `SDLOG_NO_POS_DAT` set to `Enabled`):

* The aircraft **stops recording any positional data** to logs.
* Image capture metadata (EXIF geotags) will **not contain location data**.
* **PPK mapping workflows are broken** — the logs won't contain the GPS data needed for post-processing.

Stealth logging protects operational security but significantly limits the usefulness of flight logs for troubleshooting and for any geospatial workflow.

**How to Disable Stealth logging:**

Administrators can restore full logging:

1. Connect Astro to PC with USB, login to https://10.41.1.1, go to settings, **enable Cloud Services**. This enables the log streaming service that is required. In the future we will make it a separate setting so they are not tied together.
2. Open **AMC** and activate **Advanced Mode** (tap the AMC icon in the top-left \~6 times).
3. Go to **Advanced → Parameters** and change the following parameters:
   1. `SDLOG_NO_POS_DAT` = Disabled.
   2. `GPS_DUMP_COMM` = RTCM output (PPK) (note this is only necessary if you wish to have PPK files generated. For more info on PPK, see [PPK Software](https://docs.freeflysystems.com/ecosystem/workflows/photogrammetry-mapping/ppk-software).
4. Save the changes, and power cycle the Astro.
