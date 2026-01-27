---
description: Default input and output mapping values
---

# Input Output Mapping

## Visual for Default Functions

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-02 at 1.38.05 PM.png" alt=""><figcaption></figcaption></figure>



## Configuring the Pilot Pro Buttons

The Pilot Pro has a few buttons that are not mapped to any input by default and can be assigned in the GCS software to provide additional functions

The following elements are not specific to drone functionality and can be remapped in AMC:

| Buttons Unmapped by Default | AMC Button Number           | Default Mapping in AMC |
| --------------------------- | --------------------------- | ---------------------- |
| L1                          | 14                          | No Action              |
| L2                          | 3                           | No Action              |
| R1                          | 13                          | Trigger Camera / Video |
| R2                          | 5                           | No Action              |
| S2                          | <p>Up - 10<br>Down - 11</p> | No Action              |

{% hint style="warning" %}
Any button that is being handled by the GCS will not send if the tablet is unpowered or GCS is not running
{% endhint %}



When using AMC, these inputs are available under Controller > Joystick, and can be assigned through each button's dropdown menu. To see what number a button is associated with, just press the button or flip the switch and look for which number turns blue

<figure><img src="../../../../.gitbook/assets/AMC Button Mapping.gif" alt=""><figcaption><p>How to map a button using AMC on the Pilot Pro</p></figcaption></figure>

{% hint style="info" %}
Input mapping on the Pilot Pro can happen at multiple levels. The base level would edit the actual radio commands being sent and what they're mapped to. To read more about this, please see our [Advanced Input Mapping](advanced-input-mapping.md) page.&#x20;
{% endhint %}

## Input Mapping On Various Output Types

_This is the latest with Astro v1.6 and Pilot Pro v1.3_

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-06 at 12.22.29 PM.png" alt=""><figcaption></figcaption></figure>

## SBUS Mapping (Detailed)

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-08-06 at 12.21.02 PM.png" alt=""><figcaption></figcaption></figure>
