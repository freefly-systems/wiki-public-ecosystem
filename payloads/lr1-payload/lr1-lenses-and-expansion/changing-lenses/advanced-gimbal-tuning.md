# Advanced Gimbal Tuning

## Default Tuning

When power is on, the LR1 gimbal wakes in a low-tuning state. The gimbal polls Astro for the lens information about the camera. Then, the gimbal selects the correct tuning parameters for the installed lens. Most uses will not need to change the gimbal settings from this default.&#x20;

## Custom

Users can run Autotune or set custom tuning parameters using AMC.

First, the user must enter Advanced mode by quickly tapping on the triangle icon in the upper-left corner of AMC. Then, the user selects Advanced > Parameters. Scrolling down to the bottom of the parameter groups, the user will find Component 154. Tapping the group expands the gimbal parameters labeled GMBL.

<figure><img src="https://lh7-us.googleusercontent.com/zharYFxiWW5tRmPRUne0UXJIsNcMgUvAlcRbpX5h-kz9uIUc7jM560EZ2OAbaTci7QXKUbzAROFEUmtXFygkYNrzpGseB4HNhwfunbfbxy9MjonyfU9V5GWJEEy98SOECWmDHqAbNQtlP9g3YWR6OCU" alt="" width="375"><figcaption><p>AMC with gimbal parameters</p></figcaption></figure>

### Autotune

GMBL\_TUNE\_% sets the autotune backoff percentage; 50 is a good starting point. The user starts Autotune by setting GMBL\_TUNE\_START to 0.

### Custom Values

Stiffness, hold strength, and motor filters may be set as required.

### Saving Parameters

1. Set GMBL\_LENS\_ON to turn off lens-based tuning.
2. Set GMBL\_PRMS\_SAVE to 1 to write parameters to memory.

### Reset Parameters

1. Set GMBL\_PRMS\_RESET to 1 to default all gimbal parameters.
2. Set GMBL\_PRMS\_SAVE to 1 to write parameters to memory.
3. Reboot Astro.

The reset procedure restores lens-based tuning.



If you have issues tuning your gimbal, reach out to [support ](https://freeflysystems.com/contact)and we can help!<br>
