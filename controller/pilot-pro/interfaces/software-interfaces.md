# Software Interfaces

### Apps

The Pilot Pro controller runs a modified Android firmware on its Samsung tablet, and provides users with the opportunity to customize their setup. Apps can be installed on the tablet to enhance functionality. The Samsung device is running an Android 13 base image. Most APK files will be compatible with it, offering a variety of possibilities such as installing a weather app, or a flight restriction app, or even a custom app to interact with the drone.

{% hint style="warning" %}
The user is responsible for ensuring that additional applications don't interfere with drone operations.&#x20;
{% endhint %}

The user will need to enter their google credentials and use the play store, or download an apk and install by using a trusted installer app the user has assigned.

### Google account

The Pilot Pro's tablet does not ship with a default google account. This somewhat restricts the ability to communicate with the google appstore and other google services. Users can opt in to this functionality by providing their google account information to the tablet, which will allow appstore, personalized settings, and all the other Google ecosystem benefits of having an account logged in.&#x20;

### Debugging

USB debugging is available on this device, but it is not enabled by default. Users can enable it at their peril...

Pilot Pro has a Host Swap mode that will activate the bottom right USB port as the host, and make the Tablet a device in the USB hub. This allows for:

* ADB access over USB to the Tablet for App development
* HID device access for reading joysticks, rockers and buttons

To enter Host Swap mode, either select ‘Restart Controller with Host Swap’ from the Advanced Menu in the Pilot Pro App. While in this mode, the screen will display "External USB Host".  To exit Host Swap mode, simply reboot the controller.

{% hint style="info" %}
While in Host Swap mode, the controller and tablet are no longer linked. The Pilot Pro App will not detect the controller and the tablet's power button cannot be used to power it off.
{% endhint %}

{% hint style="info" %}
If you're trying to connect the controller to a computer as an HID input, you will need to set AuthKeyEN to 0 in the Pilot Pro app -> Controller Settings
{% endhint %}

### Drone connection

The Pilot Pro offers a mechanism for external devices to connect to the drone directly. See the [Connecting to the drone via the RJ45 cable](../operating-handbook/ecosystem/#connecting-to-the-drone-via-the-rj45-cable) section for information on connecting to the drone from 3rd party devices.

### Payload connection

It is also possible to connect a payload to the network as well and access it directly on some drones such as Astro.

Using Astro as an example, a lidar could be mounted to Astro's smart dovetail and connect its ethernet port to the ethernet pins in the connector. The lidar would be assigned an IP address in the range specified by the [connectivity section](../operating-handbook/ecosystem/#rj45-ethernet-cable), ensuring there are no IP conflicts. Then, a web browser or app on the tablet could access it directly through its 192.168.144.\* ip address for configuration or monitoring. A computer or tablet connected through the RJ45 port could also access it.



{% hint style="danger" %}
It is the integrators responsibility to ensure that their device doesn't saturate the radio link, which would interrupt the drone's native video and telemetry.&#x20;
{% endhint %}

### Block Diagram

To support integration efforts, the following block diagram details the controller's internal connections.

<figure><img src="../../../.gitbook/assets/Pilot Pro Block Diagram.png" alt="Block diagram of the controller&#x27;s data paths"><figcaption><p>Block diagram of the controller's internal data paths</p></figcaption></figure>
