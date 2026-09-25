# Doodle Firmware Update

### ⚠️ Read this first

{% hint style="danger" %}
Make sure to update the Drone to latest firmware (v2.3.7) before attempting to update the Doodle Radio Firmware
{% endhint %}

**Do not power off the drone, the Pilot Pro, or close the app while an update is running.** The drone powers the air radio and the Pilot Pro powers the ground radio. Cutting power to either while its radio is being flashed can **permanently damage (brick) that radio**.

The most dangerous moment is the **"flashing..."** stage, when the progress bar appears to sit still. The radio is still writing firmware even though nothing seems to be happening. Wait for the app to show a success or failure result before touching anything. It will always show one, even if the update fails.

## Quick Start

1. Make sure you are on the **latest** [**drone software**](https://app.gitbook.com/s/8dwrGJhxGd9cIvsStziq/maintenance/software-release-notes#latest-versions) **and** [**Pilot Pro app**](../../../maintenance/software-and-firmware-updates/#latest-software-versions)**.**
2. Charge the **Pilot Pro and drone batteries above 50%**, and keep the Pilot Pro plugged in
3. Power on the drone, disarmed, a couple of meters from the Pilot Pro, radios paired and connected
4. On the **Channel Select** tab, scan and switch to the cleanest channel
5. Open **Radio Settings > Radio Firmware**, tap **"Update both to v2.0"**, confirm
6. Wait **8 to 12 minutes**. Do not power anything off or close the app — this can brick a radio
   * The progress bar barely moves during **"flashing…"**. This is normal
   * Wait for the success or failure result. The app always shows one
7. [**Re-pair**](doodle-binding-pairing.md) **the radios.** The update resets them to factory settings, so pairing is always required
8. Confirm the Radio Firmware tab shows **"Radios are up to date - Both units running firmware v2.0"**

If an update fails, power-cycle both the Pilot Pro and the drone before retrying — see[ If something goes](doodle-firmware-update.md#if-something-goes-wrong) wrong in the [full guide](doodle-firmware-update.md#doodle-radio-firmware-update-v2.0).

> Note: Drone firmware 2.3.7 or later is needed to put the drone's radio into\
> pairing mode when it runs Doodle firmware v2.0.

***

## Doodle Radio Firmware Update (v2.0)

This guide covers updating your drone's Doodle radios to firmware **v2.0** using the Pilot Pro app. There are two radios: the **ground radio** inside the Pilot Pro, and the **air radio** inside the drone. The app updates both.

The whole process typically takes **8 to 12 minutes**.

***

### Before you start

Check all of these before tapping Update:

1. **Pilot Pro app v2.8.6 or later.**
2. **Drone firmware 2.3.7 or later.** Older drone firmware cannot pair with radios running v2.0. If you skip this, the radio update itself will complete normally, but afterward you will be unable to pair the radios until you update the drone firmware.
3. **Both batteries above 50%.** The app checks the Pilot Pro and the drone and will refuse to start below 50%. Keep the **Pilot Pro plugged in** during the update.
4. **The drone is powered on and disarmed.** We recommend powering the drone with just one battery for the update. The radios must be paired and connected. The app will show that both units have an update available when it can see both.
5. **Drone and Pilot Pro are a couple of meters apart.** Keep the two in the same room, roughly a couple of meters apart for optimal radio connection during the update.
6. **A clean channel.** Stay away from busy Wi-Fi areas and other transmitting radios. Before updating, run a scan on the **Channel Select** tab and switch to the best channel available (taller bar = cleaner channel).

***

### Updating

1. Open the Pilot Pro app menu, go to **Radio Settings**, and open the **Radio Firmware** tab.
2. If both radios are on and connected, you'll see **"Both units update available"**. Tap **"Update both to v2.0"**.

<figure><img src="../../../../../.gitbook/assets/image (21).png" alt="" width="375"><figcaption></figcaption></figure>

* If only the ground radio is shown, power on the drone and wait for the air radio to connect so both update together:

<figure><img src="../../../../../.gitbook/assets/image (44).png" alt="" width="375"><figcaption></figcaption></figure>

1. Tap **Update** in the confirmation dialog. The app locks to the Radio Firmware tab until it finishes. Once the update has started, avoid switching pages and do not close the app, as interrupting it can risk bricking a radio.
2.  Watch the progress. Each radio goes through: **transferring → verifying → flashing**. The air radio is updated first, then the ground radio. The whole process typically takes **8 to 12 minutes** — the exact time varies with signal quality, since the air radio's firmware is sent over the radio link. During "flashing…" the bar won't move much — this is normal. **Do not power anything off.**

    | Transferring the firmware                            | Flashing (radios go offline — normal)                |
    | ---------------------------------------------------- | ---------------------------------------------------- |
    | ![](<../../../../../.gitbook/assets/image (45).png>) | ![](<../../../../../.gitbook/assets/image (46).png>) |
3.  When it finishes you'll see **"Both units updated — Proceed to pairing"** and a dialog offering **Pair now**.

    | Update complete dialog                               | Redirect to Pairing Page                             |
    | ---------------------------------------------------- | ---------------------------------------------------- |
    | ![](<../../../../../.gitbook/assets/image (47).png>) | ![](<../../../../../.gitbook/assets/image (49).png>) |

### After the update, [re-pairing](doodle-binding-pairing.md) is required

The update resets both radios to factory settings, so they always need to be re-paired.

Tap **Pair now** (or open the Pairing Manager), and [pair as usual](doodle-binding-pairing.md). If the app told you to power-cycle first, restart the Pilot Pro and turn the drone off and on before scanning.

Once paired, double-check the result by leaving and then returning to the Radio Settings page. The Radio Firmware tab should now show **"Radios are up to date - Both units running firmware v2.0"**.

<figure><img src="../../../../../.gitbook/assets/image (51).png" alt="" width="375"><figcaption></figcaption></figure>

***

### If something goes wrong

First, know two things:

* **Failed update attempts are normally recoverable.** In the case of most failures, the radio has not started flashing and remains on its old firmware.
* **After any failure, power-cycle both radios before retrying.** Power-cycle both the Pilot Pro and the drone. A failed update attempt can leave the radios in a state that requires reboot. Only power-cycle after the app has shown a failure message, never while it's still updating.

#### Messages before the update starts

| Message                                                                                      | What it means / what to do                                                                                                                                                                                                                                                                                                 |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "PILOT PRO BATTERY AT xx%. CHARGE ABOVE 50% BEFORE FW UPDATE!"                               | Charge the Pilot Pro above 50%, keep it plugged in, retry.                                                                                                                                                                                                                                                                 |
| "DRONE BATTERY AT xx%. CHARGE ABOVE 50% BEFORE FW UPDATE!"                                   | Charge or swap the drone battery, retry.                                                                                                                                                                                                                                                                                   |
| "COULD NOT READ DRONE BATTERY AT x.x.x.x. CHECK DRONE POWER AND VEHICLE IP IN APP SETTINGS." | The app couldn't reach the drone to check its battery. Make sure the drone is powered on and fully booted, and that the Vehicle IP in app settings is correct. Quick check: on the Pilot Pro home page, the **SKYNODE CONNECTION** dot should be green — green means the drone is reachable and the Vehicle IP is correct. |

#### Messages during or after the update

| Message                                                                                   | What it means / what to do                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "Couldn't send the firmware to either radio…"                                             | The transfer failed before anything was flashed — both radios are untouched. Check that the drone is powered and close by, power-cycle both radios, and retry.                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| "Couldn't send the firmware to the air unit — make sure it's powered and in close range." | The air radio couldn't be reached. Move the drone closer to the Pilot Pro and check for interference — if the area is RF-noisy, move somewhere quieter or switch to a cleaner channel (see the checklist). Then power-cycle both radios and retry.                                                                                                                                                                                                                                                                                                                                                             |
| "Couldn't send the firmware to the ground unit — check the connection."                   | The ground radio didn't respond. Power-cycle both radios and retry.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| "The firmware file failed verification."                                                  | The file arrived corrupted and was **not** flashed — the radios are safe. Power-cycle both radios and retry.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <p>"The ground update didn't start."<br>"The air update didn't start."</p>                | The radio received the command but never began flashing — it is still on its old firmware. Power-cycle both radios and retry.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| "The ground unit didn't come back."                                                       | The ground radio went offline to update but didn't reappear in time. It may or may not have taken the new firmware. Power-cycle the Pilot Pro, then check the Radio Firmware tab to see which version the ground radio is on: if it shows v2.0 the update worked; if it still shows v1.7, retry the update. **Leave the drone powered on.** If you were updating both radios, the air radio started its update before the ground radio and finishes on its own. Don't power the drone off until at least 10 minutes have passed since the update began. If the ground radio never comes back, contact support. |
| "Couldn't confirm the air unit"                                                           | The app can't talk to the air radio while it reboots, and the ground radio's scan can also miss the air unit (range, interference), so an unconfirmed result often does not mean the update failed. Wait until at least 10 minutes have passed since the update began (the air radio may still be finishing), then power-cycle both radios and scan in the Pairing Manager. The air radio's entry shows its firmware version. If it shows v2.0, the update worked - just pair. If it still shows v1.7, radios on different versions can still pair - pair first, then retry the update for just the air unit.  |
| "Ground Doodle settings are not optimal. Please repair…" (or Air)                         | Indicates that the radios are on factory settings. Resolved by pairing the radios.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| "Firmware update in progress, cannot switch tabs"                                         | Expected. The app locks to the firmware page during an update.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

#### The update worked, but pairing can't find the drone

If both radios updated to v2.0 successfully but the Pairing Manager scan never finds your drone, the most likely cause is that the drone firmware is older than 2.3.7. Older drone firmware can't put a v2.0 air radio into pairing mode, so the drone never shows up in the scan. There is no error message for this; the scan just comes up empty.

To fix, update the drone to firmware 2.3.7 or later and pair. The radios themselves don't need to be re-updated.

If you can't update the drone right away, reverting both radios to [v1.7](doodle-firmware-update.md#reverting-to-v1.7-not-recommended) restores pairing with older drone firmware.

#### Still stuck?

If a radio doesn't come back after a power-cycle and a retry (the Radio Firmware tab shows "No radios connected" for the ground radio, or the Pairing Manager scan never finds the air radio) stop and contact Freefly [support](https://freeflysystems.com/contact) **.** Please provide us details of what each radio is doing now, the firmware version each one shows, the exact message the app gave, and the steps you followed.

***

### Reverting to v1.7 (not recommended)

Radios on v2.0 can be reverted to v1.7 from the same Radio Firmware tab (a small gray **"Revert both to v1.7"** link appears once the radios are up to date). We don't recommend reverting unless Freefly support instructs you to. v2.0 performs better and reverting is only useful as a fallback. Reverting to versions older than v1.7 is not possible.

The process, warnings, and re-pairing requirement are exactly the same as the update. **Do not power anything off while it runs.**
