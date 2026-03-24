---
description: This guide covers all log types across the Freefly ecosystem.
hidden: true
---

# Flight Logs

### Downloading Flight Logs from the Aircraft

This is the most common request from Freefly Support and the most reliable way to get flight data. The aircraft stores flight logs as `.ulg` (ULog) files on the onboard SD card.

#### What You Need

* Your aircraft (Astro, Astro Max, or Alta X Gen2)
* **One battery only** (using a single battery prevents the risk of accidentally arming the aircraft)
  * Astro / Astro Max: 1× SL8 battery
  * Alta X Gen2: 1× battery with the fused cable
* USB-C cable
* A PC with **AMC PC** (Auterion Mission Control) installed
  * An [Auterion Suite account](https://suite.auterion.com/) is required to download AMC PC — the Basic tier is free

#### Step-by-Step: Download Logs via USB

1. **Connect the USB cable** from your PC to the aircraft's IO panel.
   * Astro / Astro Max: The IO panel is on the **underside** of the aircraft.
   * Alta X Gen2: The IO panel is on the **bottom side near the nose**.
2. **Install one battery** and power on the aircraft. Wait about 15 seconds for the aircraft to fully boot.
3. **Verify the connection** by opening a web browser and navigating to [http://10.41.1.1](http://10.41.1.1/). The aircraft's information page should load. If it doesn't, try rebooting the aircraft, reseating the cable, and restarting AMC.
4. **Open AMC PC** on your computer.
5. **Activate Advanced Mode**: Tap the AMC icon in the top-left corner of the app approximately 6 times. A popup will ask if you want to switch to Advanced Mode. Confirm.
6. **Navigate to Analyze → Log Download**.
7. **Click "Refresh"** to load the list of available logs.
8. **Select the log files** you need and click **"Download"**.

{% hint style="info" %}
**USB is strongly recommended.** While it is technically possible to download logs over WiFi, it is significantly slower and less reliable. Always prefer USB.
{% endhint %}

#### Understanding the Log Files

Log files are stored in date-stamped subdirectories on the onboard SD card. Each file has a `.ulg` extension and a timestamp in the filename.

* Very small files (under \~1 MB) are typically created by brief arm/disarm cycles and usually aren't useful.
* If the aircraft never acquired GPS, folders may be labeled `sess001`, `sess002`, etc. instead of a date. The highest number is the most recent.
* The SD card holds between 8 GB and 32 GB of data (hundreds of hours of flight logs). If storage fills up, **the oldest logs are automatically deleted** to make room for new ones. Periodically back up and clear logs if you want to retain them.

#### Troubleshooting Connection Issues

If AMC won't connect to the aircraft over USB:

1. Verify the USB connection by browsing to [http://10.41.1.1](http://10.41.1.1/) in a web browser.
2. Try a different USB-C cable — some cables are charge-only and don't support data.
3. Reboot the aircraft and restart AMC.
4. Make sure you're only using one battery.

***

### Understanding the Different Log Types

Freefly aircraft and accessories generate several different types of logs. Each captures different information and is accessed differently. Here's how they compare:

#### 1. Flight Logs from the Aircraft (`.ulg` files)

These are the primary flight logs stored directly on the aircraft's onboard SD card. They are **ULog** format files used by PX4-based autopilots.

| Detail             | Description                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Format**         | `.ulg` (ULog)                                                                                                                               |
| **Location**       | Onboard SD card, under `/logs/` subdirectories                                                                                              |
| **Logging window** | From **boot** to **power down**                                                                                                             |
| **Contents**       | Full autopilot telemetry: flight path, attitude, GPS, sensor data, inputs/outputs, vibration, errors, parameter values, software build info |
| **How to access**  | Via USB using AMC PC or QGC (see procedure above)                                                                                           |
| **How to analyze** | Upload to [PX4 Flight Review](https://logs.px4.io/), Auterion Suite, or use tools like PlotJuggler / `pyulog`                               |

These are the most complete logs available and are what Freefly Support will ask for first when troubleshooting.

#### 2. Flight Logs from Auterion Suite

If your aircraft is registered with the [Auterion Suite](https://suite.auterion.com/), flight logs are automatically uploaded to the cloud when a WiFi or LTE connection is available.

| Detail                        | Description                                                             |
| ----------------------------- | ----------------------------------------------------------------------- |
| **Format**                    | `.ulg` (same ULog format, viewable in-browser)                          |
| **Location**                  | Auterion Suite cloud platform                                           |
| **Logging window**            | From **arm** to **disarm**                                              |
| **Contents**                  | Same flight telemetry data as on-device logs                            |
| **How to access**             | Log in to Auterion Suite, navigate to the aircraft, and select a flight |
| **How to share with Freefly** | Use the **"Share with Manufacturer"** toggle on any flight in the Suite |

{% hint style="info" %}
**Key difference from on-device logs:** Suite logs only cover arm-to-disarm windows. They do not include any data from before arming or after disarming (boot-up diagnostics, pre-arm checks, etc.). If you're troubleshooting a problem that occurs before arming — such as GPS issues during initialization or pre-arm errors — the on-device logs may also only cover arm-to-disarm by default. However, the on-device file system can sometimes retain additional context depending on the `SDLOG_MODE` parameter setting.
{% endhint %}

Sharing logs through the Suite is the **fastest way to get Freefly Support involved** — it gives us immediate access without needing to transfer large files.

#### 3. AuterionOS Diagnostic Report

The AuterionOS diagnostic report is a system-level export from the Skynode companion computer. It captures information that flight logs do not — OS-level service statuses, network state, peripheral connections, partition info, and more.

| Detail            | Description                                                                                                                                                                                      |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Format**        | `.tar` archive                                                                                                                                                                                   |
| **Location**      | Generated on-demand from the aircraft's web UI                                                                                                                                                   |
| **Contents**      | System service status, software component status, network info, peripheral state, performance data, partition info, and other OS-level diagnostics                                               |
| **How to access** | Connect to the aircraft via USB, navigate to [http://10.41.1.1](http://10.41.1.1/), enable **Advanced Mode**, open **"Show additional information"**, and click **"Generate diagnostic report"** |
| **When to use**   | When Freefly Support asks for a diagnostic report — typically for issues related to connectivity, firmware updates, onboard apps, or system-level behavior that isn't captured in flight logs    |

{% hint style="info" %}
This is not a flight log! It's a snapshot of the operating system state. Freefly Support may ask for this in addition to flight logs when troubleshooting issues like failed firmware updates, disk space problems, or networking/connectivity issues.
{% endhint %}

#### 4. Pilot Pro Logs

Pilot Pro has its own logging system, separate from the aircraft. These logs capture what the controller and its app are doing — useful for diagnosing controller-side issues like joystick input problems, radio behavior, app crashes, or display anomalies.

| Detail            | Description                                                                         |
| ----------------- | ----------------------------------------------------------------------------------- |
| **Format**        | `.ulg`                                                                              |
| **Location**      | Stored locally on the Pilot Pro tablet                                              |
| **Contents**      | MAVLink states, app commands, radio status, input events, controller-side telemetry |
| **How to access** | See procedure below                                                                 |

**How to Get Pilot Pro Logs**

1. Open the **Pilot Pro App** and go to **ADVANCED**.
2. Make sure the toggle shows **"APP LOGGING ENABLED"**. Logging must have been enabled _when the issue occurred_ for the bug to be captured.
3. If you are currently seeing an issue, tap **"SAVE LOG SNAPSHOT"** to save the current session immediately. This creates a timestamped file with `USER-TRIGGERED` in the filename.
4. Tap **"OPEN PILOT LOGS"** to open the logs folder in the My Files app.
5. Select the log files you need:
   * For the current session, choose the newest file with `USER-TRIGGERED` in the name.
   * For previous sessions, sort by date and select the relevant files.
6. To transfer: Insert a **USB-C thumb drive** into one of the Pilot Pro USB-C data ports and copy the files over. Then email them to Freefly Support from your PC.

{% hint style="info" icon="diamond-exclamation" %}
Pilot Pro manages log storage automatically with a **3 GB cap**. Oldest logs are deleted when space is needed. You can manually delete logs from the My Files app, but **reboot Pilot Pro afterward** to resume logging properly.
{% endhint %}

#### 5. Doodle Labs Radio Logs

The Doodle Labs radio module (used on Blue / NDAA-compliant Astro and Alta X Gen2 configurations) have their own internal logging. These logs are primarily useful for diagnosing radio-specific issues like signal loss, range problems, or pairing failures.

| Detail            | Description                                                                                                                                                                                                                                                                                                                            |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Format**        | Internal radio diagnostic data                                                                                                                                                                                                                                                                                                         |
| **Contents**      | Radio link statistics, signal strength, channel data, connection events                                                                                                                                                                                                                                                                |
| **How to access** | Doodle Labs radio logs are not directly user-accessible through the standard Freefly workflow. Freefly Support or engineering may request specific radio diagnostics. Starting in Pilot Pro App v2.6.2, detailed radio statistics (including scan diagnostics) are available under **Radio Settings → Advanced** in the Pilot Pro App. |
| **When to use**   | When Freefly Support is investigating radio range, signal quality, or connectivity issues specific to the Doodle Labs link                                                                                                                                                                                                             |

{% hint style="info" %}
If you're experiencing radio range or signal issues, the most helpful thing you can do is provide Freefly Support with your **Pilot Pro logs** (which include radio status data as of recent firmware versions), the **aircraft flight logs**, and details about your environment and antenna setup. Freefly Support can coordinate with engineering if deeper radio-level diagnostics are needed.
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

**How to Disable Stealth Logging**

Administrators can restore full logging:

1. Connect the aircraft to a PC with USB.
2. Navigate to [https://10.41.1.1](https://10.41.1.1/) and log in.
3. Go to **Settings** and **enable Cloud Services**. (This currently also enables some advanced features — Freefly plans to separate these in a future update.)
4. Open **AMC** and activate **Advanced Mode** (tap the AMC icon in the top-left \~6 times).
5. Go to **Advanced → Parameters** and search for `SDLOG_NO_POS_DAT`.
6. Set it to **Disabled**.
7. **Power cycle** the aircraft.

#### WiFi Disabled at the OS Level

Blue drones have **WiFi permanently disabled at the operating system level**. This means:

* You **cannot download logs over WiFi** — USB is the only option.
* The aircraft **will not connect to WiFi networks** for Suite uploads or LTE fallback.
* You **cannot use WiFi-based workflows** (e.g., connecting AMC on a tablet over WiFi).
* Automatic log upload to Auterion Suite requires an **LTE connection with a SIM card installed** — WiFi upload is not available.

{% hint style="info" %}
Because WiFi is disabled, it is especially important to regularly download and back up flight logs via USB on Blue aircraft, if you wish to preserve logs. Without WiFi or LTE, logs only exist on the aircraft's internal storage, and they will be overwritten when storage fills up.
{% endhint %}

#### Controller and Payload Logging Disabled by Default

On Blue configurations, logging is also **disabled by default on the controller and payloads**. Freefly recommends that administrators enable all logging to assist with any future support requests.

***

### Sharing Logs with Freefly Support

When contacting Freefly Support, the best approach depends on what you have available:

| Method                                         | Best For                                                                             |
| ---------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Auterion Suite → "Share with Manufacturer"** | Fastest and easiest. One click and Freefly Support has access.                       |
| **Upload `.ulg` files to a support ticket**    | When Suite isn't available or when Support asks for the on-device logs specifically. |
| **Diagnostic report (`.tar`)**                 | When Support asks for it — typically for OS-level or connectivity issues.            |
| **Pilot Pro logs**                             | When troubleshooting controller-side issues.                                         |

{% hint style="info" %}
**Freefly treats your flight data as your property.** Logs are not shared with Freefly unless you explicitly choose to share them through the Suite or by sending them to Support. Auterion employees do not have access to your data. See the [Auterion Privacy Policy](https://auterion.com/privacy) for details.
{% endhint %}

***

### Log Analysis Tools

| Tool                                                        | Description                                                                                                        |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| [PX4 Flight Review](https://logs.px4.io/)                   | Free web tool. Upload a `.ulg` file to see plots of attitude, position, GPS, vibration, errors, and more.          |
| [Auterion Suite](https://suite.auterion.com/)               | Built-in viewer for aircraft registered with the Suite. Same data as Flight Review with fleet management features. |
| [PlotJuggler](https://github.com/facontidavide/PlotJuggler) | Desktop app for detailed time-series analysis of ULog files.                                                       |
| `pyulog`                                                    | Python library for programmatic ULog parsing and analysis.                                                         |
