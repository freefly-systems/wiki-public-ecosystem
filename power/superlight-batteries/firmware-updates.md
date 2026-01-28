# Firmware Updates

## SL4 Firmware v2.1

* **Summary**: SL4 bugfixes and improvements
* **Release Date**: December 2024
* **Release Notes:** Please see [#sl8-firmware-v2.1](firmware-updates.md#sl8-firmware-v2.1 "mention")
* #### How to Update: Open [this webpage](http://freeflysystems.com/sl8_v2-1) on a computer and follow instructions



## SL8 Firmware v2.1

* **Summary**: SL8 bugfixes and improvements
* **Release Date**: August 2024

#### How to Update

* Open this webpage on a computer and follow instructions -> [freeflysystems.com/sl8\_v2-1](http://freeflysystems.com/sl8_v2-1)

#### **Release Notes**

* **Improved State of Charge (SOC) Estimation:**&#x20;
  * **This is an important feature that addresses a critical weakness of the old firmware, where a battery could suddenly report 0% in flight, triggering critical fail safes on Astro.**
  * Coulomb Counting SOC Estimation: If a fuel gauge error is detected, the system will now switch to Coulomb counting for SOC estimation. This ensures more accurate battery monitoring in case of fuel gauge issues.
* **Expanded Operating Temperature Range**: The operating temperature requirement has been reduced from 10°C to 0°C, allowing the battery to function in colder environments. This feature requires the new State of Charge (SOC) estimation method.
* **Active Cell Balancing**: A new feature has been added to perform active cell balancing during the battery's transition to standby mode. Previously, cell balancing only occurred while the pack was charging. Now, if the cells in a pack are out of balance (exceeding a 10mV threshold) when the pack attempts to enter standby mode, the system will instead turn off the display and shift into a low-power run mode. In this mode, the battery continues to balance the cells until they are within the acceptable threshold or for a maximum of 10 days. Once the cells are balanced or the time limit is reached, the battery will then enter true standby mode. This extended balancing process ensures more consistent performance and longer battery life.
* **Enhanced Security**: A new lock-out feature has been added to enhance security. This ensures that unauthorized access to the command line interface (CLI) is restricted.
* **USB and Standby Mode Improvements:** A timer has been added to delay entry into standby mode for 10 seconds after the USB cable is unplugged, allowing users to switch the cable to another device without the battery powering down.
* **Alarm System Update:** The alarm buzzer will now activate immediately upon detecting a fault, addressing the previous delay caused by timer setup issues.
