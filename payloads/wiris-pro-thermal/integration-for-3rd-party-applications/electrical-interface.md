# Electrical Interface

## Connector

Wiris Pro Payload uses the Smart Dovetail interface for power, data, and control. Pinouts for this connector can be found at both links bellow:

{% content-ref url="https://github.com/freefly-systems/wiki-public-ecosystem/blob/main/ecosystem/development-tools/payload-mounting-interfaces.md" %}
[https://github.com/freefly-systems/wiki-public-ecosystem/blob/main/ecosystem/development-tools/payload-mounting-interfaces.md](https://github.com/freefly-systems/wiki-public-ecosystem/blob/main/ecosystem/development-tools/payload-mounting-interfaces.md)
{% endcontent-ref %}

{% embed url="https://github.com/pixhawk/Pixhawk-Standards/blob/master/DS-014%20Pixhawk%20Payload%20Bus%20Standard.pdf" %}
Pixhawk Payload Bus specs
{% endembed %}

The Wiris video and control is passed through over the ethernet pins on the smart dovetail. Info on communicating with the camera can be found in the document bellow.

{% file src="../../../.gitbook/assets/WWP_ETHERNET_SDK_document_07_19_2022 (1).pdf" %}
Wiris Ethernet SDK
{% endfile %}

The gimbal utilizes Mavlink for control from the aircraft over the UART pins.

## Power requirements:

The Wiris is powered directly from the gimbal, these specs account for the entire package in operation. Power is drawn from the V\_BATT pins on the Smart Dovetail pinout.

| Voltage           | 18-25.2V                                |
| ----------------- | --------------------------------------- |
| Current (Nominal) | 0.7-1.5A depending on flight conditions |
| Current (Max)     | 5A                                      |
