---
hidden: true
---

# RFD900 Solo

The Pilot Pro RFD900 Solo is a standalone Pilot Pro controller configured with an RFD900 radio module. It is designed for both integrators and customers who want to upgrade or integrate a Pilot Pro into an existing UXV workflow without replacing the aircraft-side radio.

**The Alta X's Blue firmware is not aware of the RFD900 configuration on firmware's below 1.3.114 stable blue firmware. Upgrading to the Pilot Pro will require** [**updating the Alta X**](https://docs.freeflysystems.com/products/products/alta-x/untitled-4#updating-firmware) **if using older firmware**

For integrators, we are running the standard RFD900 firmware with NetID's for pairing

***

### Tested Configurations

| Module       | Use Case                                                                        |
| ------------ | ------------------------------------------------------------------------------- |
| RFD900x      | Factory-installed on UXV Alta X aircraft                                        |
| RFD900ux-SMT | Installed by Freefly during Pilot Pro RFD900 integration on Alta X NDAA Variant |

***

### Known Issues & Limitations

| Affected Hardware     | Issue                                           | Notes                                                                  |
| --------------------- | ----------------------------------------------- | ---------------------------------------------------------------------- |
| RFD900x (old airside) | Encryption causes 10–15 second telemetry delays | Encryption must be disabled after pairing — see setup guide below      |
| RFD900x (old airside) | Encryption key cannot be reliably set remotely  | Commands fail silently; key must be configured locally                 |
| Both RFD900 modules   | No digital channel passthrough                  | Kill switch is remapped to SBUS Channel 16 in firmware as a workaround |

***

## Pilot Pro + RFD900 — Alta X (UXV) Setup Guide

***

### Before You Start

**You will need:**

* Pilot Pro controller with RFD900 module installed
* UXV Alta X (with RFD900 already installed on the aircraft)
* The UXV ground controller (temporarily, to read its RFD settings)
* A computer running [**Auterion Mission Control**](https://docs.freeflysystems.com/products/products/alta-x/untitled-4/alta-x-v2.1-beta-quick-start#quick-start) **or** [**QgroundControl**](https://freeflysystems.com/support/alta-x-support)
* RFD Tools configurator app (on the Pilot Pro and UXV controller)
* [Alta X updated to 2.1 Beta firmware](https://docs.freeflysystems.com/products/products/alta-x/untitled-4/alta-x-v2.1-beta-quick-start)

***

### Part 1 — Match the RFD900 Radio Settings

The Pilot Pro's RFD900 must be configured to match the settings on the aircraft-side RFD900. The easiest way to get those settings is from the UXV controller the aircraft shipped with.

#### Step 1 — Read the UXV Controller's RFD Settings

1. Power on the **UXV ground controller**.
2. Close any running instances of QGroundControl, AMC, and the MAVLink router.
3. Open the **RFD Configurator** app and connect to the ground module.
4. Take a screenshot or write down the following values:
   * **Net ID**
   * **Channels / Min Freq / Max Freq**
   * **Encryption Key** (if enabled)
5. Power off the UXV controller.

#### Step 2 — Configure the Pilot Pro's RFD900

1. On the **Pilot Pro**, close any running instances of QGroundControl, AMC, and the MAVLink router.
2. Open the **RFD Configurator** app and connect to the ground module.
3. Enter the **Net ID**, channels, and frequencies from the UXV controller.
4. If the Pilot Pro has encryption enabled, it must be disabled — Encryption keys can only be entered when encryption is saved in a disabled state
   1. If the Pilot Pro currently has encryption enabled, **disable it** and tap Apply.&#x20;
5. With encryption now saved as _disabled_, **re-enable encryption**, enter the key from the UXV controller, and tap Apply.
6. Confirm all settings match, then close the RFD Configurator.

***

### Part 2 — Connect to the Aircraft

1. Make sure the UXV controller is **powered off**.
2. Power on the **Alta X**.
3. Power on the **Pilot Pro**.
4. The aircraft should detect the Pilot Pro's RFD900 and connect automatically

#### Disable Encryption — Required

Once connected, re-open RFD Configurator on the Pilot Pro and **disable the encryption key**, then save.

{% hint style="danger" %}
An active encryption key between the RFD900ux-SMT in the Pilot Pro and RFD900x air side from the UXV configuration causes 10–15 second telemetry delays that will affect situational awareness and GCS usability. The Net ID and frequency channel settings provide sufficient link exclusivity for normal operations
{% endhint %}

***

### Firmware Dependent Steps

Once fully connected with encryption disabled, you'll want to reset the parameters on the aircraft to ensure you're starting from a known state when configuring the controller. The methods to do this vary between firmware version

{% tabs %}
{% tab title="v1.3.114" %}
### Firmware v1.3.114 — Parameter Setup & Calibration

***

### Step 3 — Preparing the Temperature Calibration

Alta X stores a unique thermal calibration file on its SD card. This calibration compensates rate gyros, accelerometers, and the barometric pressure sensor for temperature-induced bias. Loading default parameters removes this calibration — it must be reloaded before flight.

1. With the Alta X unpowered, connect a USB-C cable to your computer. Leave the other end disconnected from the Alta X for now.
2. Remove the chassis closeout panel between **Booms 1 and 2** to expose the expansion board.
3. **Hold the USB MSC button** on the expansion board while plugging in the USB-C cable. Nav lights should remain **solid blue**. The Alta X will appear as a USB drive named `FF-ALTA`.
4. Locate the file named `[SerialNumber]_Tempcal.params` and copy it to your computer
5. Eject the USB drive and unplug the cable.

### Step 4 — Set the Airframe

1. Reconnect the USB-C cable without pressing the button. The Alta X will boot normally — lights will cycle blue → white → red/green directional.
2. Open **Alta QGroundControl** and wait for the aircraft to connect.
3. Navigate to **Vehicle Setup** (three-gear icon, top left) → **Parameters** tab (two-gear icon, left sidebar).
4. In the search bar, search for `SYS_AUTOSTART`.
5. Set the value to **`4512`** (Alta X — Pilot Pro with RFD900).

### Step 5 — Load Default Parameters

**On Pilot Pro (using QGC):**

* Tap the **Tools** button (top right of the Parameters tab) → **Load Defaults**.

**On a computer (using QGC):**

* Search for `SYS_AUTOCONFIG` and set it to **`2`**. _(You may need to select "Manual Entry" → "Force Save" to apply this.)_

### Step 6 — Shutdown the Aircraft

* Remove power from the aircraft to shutdown

### Step 7 — Apply Temperature Calibration

1. Reconnect the USB-C cable without pressing the button. The Alta X will boot normally — lights will cycle blue → white → red/green directional.
2. Open Alta QGC and wait for the aircraft to connect.
3. Navigate to **Vehicle Setup** → **Parameters** → **Tools** → **Load from File** and select the `Tempcal.params` file.
4. **Reboot the aircraft.**
5. Reconnect in QGC and navigate to **Parameters** → **Thermal Compensation** tab (bottom left). Confirm the majority of values are **non-zero**. Zero values indicate the calibration did not load — repeat this section before continuing.
6. **Shutdown the aircraft.**

***

### Step 8 — Sensor Calibration

1. Mount and plug in the **Alta X batteries** to power the aircraft.
2. Open Alta QGC and wait for the aircraft to connect.
3. Navigate to **Vehicle Setup** → **Sensors** tab.
4. Rotations should be auto configured, but for reference they are the following settings:
   * **Autopilot Orientation:** `ROTATION_YAW_180`
   * **External Compass (Here2 GPS):** `ROTATION_YAW_270`
   * **External Compass (RTK / F9P GPS):** `NO_ROTATION`
5. Work through each sensor marked **red** and follow the on-screen calibration instructions. Sensors marked green are already calibrated.
6. **Reboot the aircraft** after all calibrations are complete.
{% endtab %}

{% tab title="v2.1 Beta" %}
## Firmware v2.1 Beta — Parameter Reset & Selecting Radio

### Part 3 — Default Parameters

After the RFD900 is connected, a parameter reset confirms that the aircraft is in a known state

1. [Activate Advanced Mode in Auterion Mission Control (AMC)](https://docs.freeflysystems.com/ecosystem/software/auterion-mission-control/amc-vehicle-setup/parameters#accessing-advanced-parameters)
2. [Reset the parameters to the vehicle configuration defaults via the tools menu under parameters](https://docs.freeflysystems.com/ecosystem/software/auterion-mission-control/amc-vehicle-setup/parameters#resetting-parameters-to-factory-defaults)
3. Reboot the aircraft by removing power

{% hint style="info" %}
If you cannot download parameters from the Pilot Pro after connecting, try connecting via a **computer running AMC.** This may persist until the controller type is selected.&#x20;
{% endhint %}

***

### Part 4 —Selecting the Controller Type

After the parameter reset and reboot, the controller type must be manually selected. It will not be detected automatically on first setup.

1. Open **Auterion Mission Control (AMC)** on the Pilot Pro.
2. Navigate to **Vehicle Overview** (top left, next to the app icon) → **Select Controller**.
3. Select **Pilot Pro (RFD900)**.
4. Reboot the aircraft and reconnect.
{% endtab %}
{% endtabs %}

***

### Final Verification

Before first flight, confirm the following:

* [ ] Aircraft connects to Pilot Pro automatically on power-up
* [ ] Telemetry is live with no significant delay (encryption confirmed disabled)
* [ ] All flight mode buttons respond correctly: **POS**, **ALT**, **MAN**, **RTL**, **SLOW (slow is only enabled on 2.1 beta firmware)**
* [ ] Kill switch activates as expected
* [ ] No red sensor warnings in AMC

***

**Need help?** Contact Freefly support at support.freeflysystems.com or reach out to your dealer.
