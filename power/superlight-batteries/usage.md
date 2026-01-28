# Usage



{% embed url="https://www.youtube.com/watch?v=q5SivNxO0jA" %}

## Battery Management System

Each SuperLight pack has a built-in Battery Management System (BMS) that manages charging and discharging. As a result, the experience of using SuperLight Batteries is similar to using a smartphone or laptop computer battery, rather than a hobby-style lipo pack.&#x20;

## User Interface

Press the button once to check state of charge. Press again to turn on the battery.

Press the button to cycle through top-level screens. Hold for detail, when available (see table below). Press to return to top level.

Standby: When a battery is ejected from a device, it will automatically enter standby. After 30 seconds of inactivity, the battery will revert to standby automatically. To activate standby manually, press and hold the button.

### Display Navigation

| 1 - Top Level        | 2 - Detail         | 3 - Detail        | 4 - Detail  |
| -------------------- | ------------------ | ----------------- | ----------- |
| State of Charge      |                    |                   |             |
| Voltage              | Cell voltages      |                   |             |
| Current              |                    |                   |             |
| Temperature          | Individual sensors |                   |             |
| Last Charge/Capacity |                    |                   |             |
| USB                  |                    |                   |             |
| Health               | Lifetime health    | Manufacturer Data | Debug       |

## States

* **Standby:** This is a low power state where the screen is turned off and the batteryt will consume less than 100uA.&#x20;
  * Deep sleep: The battery enters a mode called ship mode when it has been discharged to a minimum voltage level (2.7 V). It will consume less than 10uA in this mode, and should allow the cells to last for 3 years or more.
* **SoC:** This is a quick display screen that shows battery percentage, as well as the firmware version number. Batteries will go back to standby after 5 seconds.
* **On**
  * ID Sense: In this state the batteries are searching for a smart host, such as Astro
  * Hotswap: In this state the batteries are active and are supplying current to a smart host, such as Astro
  * Enabled: In this state the batteries are active and are supplying current to a passive host, such as Movi Pro SuperLight Battery adapters
*   **Airmode**: When a smart host, such as an Astro, commands batteries to go to Airmode, SuperLight batteries will bypass all protections and provide power without any interruption. If there are any faults during a flight, error messages will be displayed, but the output will not be affected. Once batteries are commanded to leave Airmode, protections reactivate, thus batteries may shut off to protect themselves.



## USB Power Output

The USB-C port offers Power Delivery, which means the SuperLight battery will negotiate with a connected device to send power at a voltage best for your device. It will provide up to 60W power. For instance, it will charge your:

* Macbook Pro
* iPhone
* iPad
* Astro Controller

#### How to use:

* Plug USB C cable to battery and other end to a device you want to charge.&#x20;
* Turn on the battery to start charging the device.&#x20;
* You can also press to cycle through screens until you see the USB screen to see more details about the USB charging state.
* Simply remove the USB cable from the battery and the battery will power off automatically.



## Weather and Temperature

### Temperature

Specified ambient operating temperature is -2&#x30;**°**&#x43; to 5&#x30;**°**&#x43;.&#x20;

* Note, the battery temperature may be significantly different than the ambient air temperature due to thermal mass of the cells. They take a significant amount of time to change temperature.&#x20;
* Cells heat during discharge, especially during flight. The amount of heating is heavily dependent upon starting temperature, discharge rate, etc. 30 degrees C of heating during a flight is common.&#x20;
* Batteries perform optimally around room temperature. If possible, keeping them near room temp before use is encouraged, but not required.&#x20;
* Cold Operation:&#x20;
  * Charging: If the battery cell temperature is less than &#x30;**°**&#x43; and charging is attempted, the battery will display a fault ("Under Temp Chg") and not re-allow charge until the temperature is raised above &#x35;**°**&#x43;.
  * Discharging: If the battery cell temperature is less than 1&#x30;**°**&#x43; and discharging is attempted, the battery will display a fault ("Under Temp Dsg") and not allow discharge until the temperature is raised above 1&#x35;**°**&#x43;.
* Hot Operation:&#x20;
  * Charging: If the battery cell temperature exceeds 5&#x30;**°**&#x43; during charging, the battery will display a fault ("Over Temp Chg") and not re-allow charge until the temperature is lowers below 4&#x35;**°**&#x43;.
  * Discharging: If the battery cell temperature exceeds 7&#x30;**°**&#x43; during discharge, a warning will be triggered telling the operator to reduce output and land or halt battery use ASAP. If the battery cell temperature exceeds 8&#x30;**°**&#x43; during discharge, the battery will display a fault ("Over Temp Dsg") and not re-allow discharge until the temperature is lowers below 6&#x30;**°**&#x43;.



### Weather

SuperLight batteries are water resistant. Not for submerged use. Not for use in salt spray or water.

The connectors cannot be mated while wet. Water must be blown out before mating the connectors.

If you fly in rain, it is important to ensure you dry the pack off before attempting to plug into it's USB-C port or to plug the pack into a charger. Blow out the connectors to ensure you don't trap any water inside.

{% hint style="info" %}
The USB-C dust cap is intended to keep out debris. It is not intended to form a water-tight seal.
{% endhint %}
