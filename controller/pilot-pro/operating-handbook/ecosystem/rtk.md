---
description: >-
  This quick tutorial will walk you through how to setup RTK with your Astro or
  Alta X using the Pilot Pro with the Herelink or Doodle Labs radio module
---

# RTK

Things you need:

* Astro / Alta X
* Pilot Pro with Herelink / Doodle Labs
* Freefly RTK Base Station
* Laptop / computer
* Ethernet Cable
* USB to Ethernet adapter (only if your laptop does not have an ethernet port)
* USB-C cable (USB-C on the RTK side, whatever your computer accepts on the other)

{% hint style="info" %}
If using a Doodle Labs radio (found on Blue/NDAA configurations), you will need to[ enable the RJ45 ethernet port ](../radio-modules/doodle-labs-radio-module/doodle-rj45-ethernet-port.md)on the back of the module
{% endhint %}

### Setting Up Hardware Connections

First, connect all required devices. You will need to connect the following connections:

* Pilot Pro connected to the computer with an ethernet cable
* Freefly RTK Base Station connected to the computer with a USB cable

<figure><img src="../../../../.gitbook/assets/RTK Pilot Pro hardware setup.png" alt=""><figcaption><p>RTK plugged into the computer over USB, with the Pilot Pro being connected to the computer over ethernet</p></figcaption></figure>

### Setup Computer Networking

[Video Link: Setting up an ethernet connection on your computer with Pilot Pro](https://www.loom.com/share/2dffce4dbba84941b147b0d292017473)

* On the computer, configure ethernet adapter IPv4 properties to a static IP:
  * IP: 192.168.144.199
  * Subnet mask: 255.255.255.0

<figure><img src="../../../../.gitbook/assets/Astro Static IP.png" alt=""><figcaption><p>Windows example of Static IP configuration</p></figcaption></figure>

### Configure AMC/QGC

{% tabs %}
{% tab title="Astro or Alta X (Gen2 ONLY)" %}
#### Comm Link Configuration

In AMC on your companion device, Navigate to Settings > Comm Links > add to add a TCP comm link with the following settings:\
\
Name: \<User Specified>\
Type: TCP\
Host Address: 192.168.144.20\
TCP Port: 5790

<figure><img src="../../../../.gitbook/assets/Astro Comm Link.png" alt=""><figcaption><p>Comm link setting</p></figcaption></figure>

Once this Comm Link is configured, you will need to enable it.

#### Base Station Location

Under Settings > General > RTK GPS, you'll have the option for how the RTK base station location is determined. This setting will only appear when you activate [AMC Advanced mode](https://docs.auterion.com/hardware-integration/flight-controller-customization/amcs-advanced-mode#enable-advanced-mode-in-amc). Survey-In will listen for GPS for the specified observation time, and then allow RTK if the accuracy is below the specified number. If you know the exact base position, we would recommend to use the specified base position for higher accuracy

<figure><img src="../../../../.gitbook/assets/Recommended RTK (Specified Base).png" alt=""><figcaption><p>Recommended RTK option</p></figcaption></figure>
{% endtab %}

{% tab title="Alta X (Gen1)" %}
After going through the above settings, QGC is set to automatically connect by default, but if you do not see a connection, please follow the instructions below:

**Adding a UDP Comm Link**

In QGC on your companion device, Navigate to Application Settings > Comm Links > add to add a UDP comm link:

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-06-12 092641 hl.png" alt=""><figcaption><p>Where to add a comm link</p></figcaption></figure>

When adding a comm link, use the following settings:\
Name: \<User Specified>\
Type: UDP\
Host Address: 192.168.144.12\
UDP Port: 14553

<figure><img src="../../../../.gitbook/assets/alta x udp comm.png" alt=""><figcaption><p>Comm link settings</p></figcaption></figure>

**Bypassing Firewall**

If you already have a connection in QGC, you can skip this section. If you are still having trouble connecting the secondary device after going through the steps above, you may need to add an inbound firewall rule to allow QGC to receive the stream. Operating systems may vary in how this is done, we will go through a windows example below:\
\
This will require Admin permissions on the computer.

1. Open up "Windows Defender Firewall with Advanced Security"
2. Under "Inbound Rules" on the left, select "New Rule..." on the right
3. Create a rule with the following settings:\
   \- Port Rule\
   \- UDP Rule\
   \- Specific local ports: 14553\
   \- Allow the connection\
   \- Rule applies to Domain, Private, Public\
   \- Give the Rule a name, and save!

**RTK Options**

Under Application Settings > General > RTK GPS, you'll have the option for how the RTK base station location is determined. Survey-In will listen for GPS for the specified observation time, and then allow RTK if the accuracy is below the specified number. If you know the exact base position, we would recommend to use the specified base position for higher accuracy

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-06-12 093618.png" alt=""><figcaption><p>Recommended RTK option</p></figcaption></figure>
{% endtab %}
{% endtabs %}
