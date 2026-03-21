---
hidden: true
---

# RFD900 Solo

The Pilot Pro RFD900 Solo is a standalone Pilot Pro controller configured with an RFD900 radio module. It is designed for both integrators and customers who want to upgrade or integrate a Pilot Pro into an existing UXV workflow without replacing the aircraft-side radio.

**The Alta X's Blue firmware is not aware of the RFD900 configuration on firmware's below the 2.1 beta. Upgrading to the Pilot Pro will require updating the Alta to** [**beta firmware**](https://docs.freeflysystems.com/products/products/alta-x/untitled-4/alta-x-v2.1-beta-quick-start)**.**&#x20;

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
* A computer or the Pilot Pro itself running **Auterion Mission Control**
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
4. The aircraft should detect the Pilot Pro's RFD900 and connect automatically within a few seconds.

#### Disable Encryption — Required

Once connected, re-open RFD Configurator on the Pilot Pro and **disable the encryption key**, then save.

{% hint style="danger" %}
An active encryption key between the RFD900ux-SMT in the Pilot Pro and RFD900x air side from the UXV configuration causes 10–15 second telemetry delays that will affect situational awareness and GCS usability. The Net ID and frequency channel settings provide sufficient link exclusivity for normal operations
{% endhint %}

***

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

***

### Part 7 — Final Verification

Before first flight, confirm the following:

* [ ] Aircraft connects to Pilot Pro automatically on power-up
* [ ] Telemetry is live with no significant delay (encryption confirmed disabled)
* [ ] All flight mode buttons respond correctly: **POS**, **ALT**, **MAN**, **RTL**, **SLOW**
* [ ] Kill switch activates as expected
* [ ] No red sensor warnings in AMC

***

**Need help?** Contact Freefly support at support.freeflysystems.com or reach out to your dealer.
